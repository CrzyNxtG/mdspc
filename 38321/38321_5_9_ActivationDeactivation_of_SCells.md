## 5.9 Activation/Deactivation of SCells

If the MAC entity is configured with one or more SCells, the network may
activate and deactivate the configured SCells. Upon configuration of an
SCell, the SCell is deactivated unless the parameter *sCellState* is set
to *activated* for the SCell by upper layers.

The configured SCell(s) is activated and deactivated by:

\- receiving the SCell Activation/Deactivation MAC CE described in
clause 6.1.3.10;

\- receiving the Enhanced SCell Activation/Deactivation MAC CE described
in clause 6.1.3.55;

\- configuring *sCellDeactivationTimer* timer per configured SCell
(except the SCell configured with PUCCH, if any): the associated SCell
is deactivated upon its expiry;

\- configuring *sCellState* per configured SCell: if configured, the
associated SCell is activated upon SCell configuration;

\- receiving *scg-State*: the SCells of SCG are deactivated.

The MAC entity shall for each configured SCell:

1\> if an SCell is configured with *sCellState* set to *activated* upon
SCell configuration, or an SCell Activation/Deactivation MAC CE or an
Enhanced SCell Activation/Deactivation MAC CE is received activating the
SCell:

2\> if the SCell was deactivated prior to receiving this Enhanced SCell
Activation/Deactivation MAC CE and a TRS is indicated for this SCell:

> 3\> indicate to lower layers the information regarding the TRS.

2\> if the SCell was deactivated prior to receiving this SCell
Activation/Deactivation MAC CE or this Enhanced SCell
Activation/Deactivation MAC CE; or

2\> if the SCell is configured with *sCellState* set to *activated* upon
SCell configuration:

3\> if *firstActiveDownlinkBWP-Id* is not set to dormant BWP:

4\> activate the SCell according to the timing defined in TS 38.213
\[6\] for MAC CE activation and according to the timing defined in TS
38.133 \[11\] for direct SCell activation; i.e. apply normal SCell
operation including:

5\> SRS transmissions on the SCell;

5\> CSI reporting for the SCell;

5\> PDCCH monitoring on the SCell;

5\> PDCCH monitoring for the SCell;

5\> PUCCH transmissions on the SCell, if configured.

3\> else (i.e. *firstActiveDownlinkBWP-Id* is set to dormant BWP):

4\> stop the *bwp-InactivityTimer* of this Serving Cell, if running.

3\> activate the DL BWP and UL BWP indicated by
*firstActiveDownlinkBWP-Id* and *firstActiveUplinkBWP-Id* respectively.

2\> start or restart the *sCellDeactivationTimer* associated with the
SCell according to the timing defined in TS 38.213 \[6\] for MAC CE
activation and according to the timing defined in TS 38.133 \[11\] for
direct SCell activation;

2\> if the active DL BWP is not the dormant BWP:

3\> (re-)initialize any suspended configured uplink grants of configured
grant Type 1 associated with this SCell according to the stored
configuration, if any, and to start in the symbol according to rules in
clause 5.8.2;

3\> trigger PHR according to clause 5.4.6.

1\> else if an SCell Activation/Deactivation MAC CE or an Enhanced SCell
Activation/Deactivation MAC CE is received deactivating the SCell; or

1\> if the *sCellDeactivationTimer* associated with the activated SCell
expires; or

1\> if the SCG associated with the activated SCell is deactivated:

2\> deactivate the SCell according to the timing defined in TS 38.213
\[6\];

2\> stop the *sCellDeactivationTimer* associated with the SCell;

2\> stop the *bwp-InactivityTimer* associated with the SCell;

2\> deactivate any active BWP associated with the SCell;

2\> clear any configured downlink assignment and any configured uplink
grant Type 2 associated with the SCell respectively;

2\> clear any PUSCH resource for semi-persistent CSI reporting
associated with the SCell;

2\> suspend any configured uplink grant Type 1 associated with the
SCell;

2\> flush all HARQ buffers associated with the SCell;

2\> cancel, if any, triggered consistent LBT failure for the SCell.

1\> if PDCCH on the activated SCell indicates an uplink grant or
downlink assignment; or

1\> if PDCCH on the Serving Cell scheduling the activated SCell
indicates an uplink grant or a downlink assignment for the activated
SCell; or

1\> if a MAC PDU is transmitted in a configured uplink grant and LBT
failure indication is not received from lower layers; or

1\> if a MAC PDU is received in a configured downlink assignment:

2\> restart the *sCellDeactivationTimer* associated with the SCell.

1\> if the SCell is deactivated:

2\> not transmit SRS on the SCell;

2\> not report CSI for the SCell;

2\> not transmit on UL-SCH on the SCell;

2\> not transmit on RACH on the SCell;

2\> not monitor the PDCCH on the SCell;

2\> not monitor the PDCCH for the SCell;

2\> not transmit PUCCH on the SCell;

2\> if the SCell is configured as a scheduled cell in
*MC-DCI-SetOfCells* and with the search space for DCI to schedule
multiple cells (as specified in TS 38.213 \[6\]) of the same
*searchSpaceId* as the serving cell in which *MC-DCI-SetOfCells*
containing the SCell is configured:

3\> not monitor the PDCCH for scheduling multiple cells (as specified in
TS 38.213 \[6\]) for the set of cells in *MC-DCI-SetOfCells* including
the SCell.

When the measurement reporting for fast unknown SCell activation is
configured by RRC, the MAC entity shall:

1\> if SCell Activation/Deactivation MAC CE or an Enhanced SCell
Activation/Deactivation MAC CE is received activating the SCell(s):

2\> if SCell(s) was deactivated prior to receiving this SCell
Activation/Deactivation MAC CE or this Enhanced SCell
Activation/Deactivation MAC CE:

3\> indicate to upper layers SCell(s) activation indication.

HARQ feedback for the MAC PDU containing SCell Activation/Deactivation
MAC CE or Enhanced SCell Activation/Deactivation MAC CE shall not be
impacted by PCell, PSCell and PUCCH SCell interruptions due to SCell
activation/deactivation in TS 38.133 \[11\].

When SCell is deactivated, the ongoing Random Access procedure on the
SCell, if any, is aborted.