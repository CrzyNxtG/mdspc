### 5.15.1 Downlink and Uplink

In addition to clause 12 of TS 38.213 \[6\], this clause specifies
requirements on BWP operation.

A Serving Cell may be configured with one or multiple BWPs, and the
maximum number of BWP per Serving Cell is specified in TS 38.213 \[6\].

The BWP switching for a Serving Cell is used to activate an inactive BWP
and deactivate an active BWP at a time. The BWP switching is controlled
by the PDCCH indicating a downlink assignment or an uplink grant, by the
*bwp-InactivityTimer*, by RRC signalling, or by the MAC entity itself
upon initiation of Random Access procedure or upon detection of
consistent LBT failure on SpCell. Upon RRC (re-)configuration of
*firstActiveDownlinkBWP-Id* and/or *firstActiveUplinkBWP-Id* for SpCell
except for PSCell when SCG is deactivated (see clause 5.29) or
activation of an SCell, the DL BWP and/or UL BWP indicated by
*firstActiveDownlinkBWP-Id* and/or *firstActiveUplinkBWP-Id*
respectively (as specified in TS 38.331 \[5\]) is active without
receiving PDCCH indicating a downlink assignment or an uplink grant.
Upon RRC (re-)configuration of *firstActiveDownlinkBWP-Id* for PSCell
when SCG is deactivated, the DL BWP is switched to the
*firstActiveDownlinkBWP-Id* as specified in TS 38.331 \[5\]. The active
BWP for a Serving Cell is indicated by either RRC or PDCCH (as specified
in TS 38.213 \[6\]). For unpaired spectrum, a DL BWP is paired with a UL
BWP, and BWP switching is common for both UL and DL.

For each SCell a dormant BWP may be configured with *dormantBWP-Id* by
RRC signalling as described in TS 38.331 \[5\]. Entering or leaving
dormant BWP for SCells is done by BWP switching per SCell or per
dormancy SCell group based on instruction from PDCCH (as specified in TS
38.213 \[6\]). The dormancy SCell group configurations are configured by
RRC signalling as described in TS 38.331 \[5\]. Upon reception of the
PDCCH indicating leaving dormant BWP, the DL BWP indicated by
*firstOutsideActiveTimeBWP-Id* or by *firstWithinActiveTimeBWP-Id* (as
specified in TS 38.331 \[5\] and TS 38.213 \[6\]) is activated. Upon
reception of the PDCCH indicating entering dormant BWP, the DL BWP
indicated by *dormantBWP-Id* (as specified in TS 38.331 \[5\]) is
activated. The dormant BWP configuration for SpCell or PUCCH SCell is
not supported.

BWP for SRS for positioning Tx frequency hopping can be configured for a
Serving Cell in TS 38.331 \[5\]. BWP for SRS Tx frequency hopping is
considered as activated when it is configured. BWP switching is not
applicable for BWP for SRS Tx frequency hopping.

For each activated Serving Cell configured with a BWP, the MAC entity
shall:

1\> if a BWP is activated and the active DL BWP for the Serving Cell is
not the dormant BWP and the Serving Cell is not the PSCell of
deactivated SCG:

2\> transmit on UL-SCH on the BWP;

2\> transmit on RACH on the BWP, if PRACH occasions are configured;

2\> monitor the PDCCH on the BWP;

2\> transmit PUCCH on the BWP, if configured;

2\> report CSI for the BWP;

2\> transmit SRS on the BWP, if configured;

2\> receive DL-SCH on the BWP;

2\> (re-)initialize any suspended configured uplink grants of configured
grant Type 1 on the active BWP according to the stored configuration, if
any, and to start in the symbol according to rules in clause 5.8.2;

2\> if *lbt-FailureRecoveryConfig* is configured:

3\> stop the *lbt-FailureDetectionTimer*, if running;

3\> set *LBT_COUNTER* to 0;

3\> monitor LBT failure indications from lower layers as specified in
clause 5.21.2.

1\> if a BWP is activated and the active DL BWP for the Serving Cell is
dormant BWP:

2\> stop the *bwp-InactivityTimer* of this Serving Cell, if running.

2\> not monitor the PDCCH on the BWP;

2\> not monitor the PDCCH for the BWP;

2\> not receive DL-SCH on the BWP;

2\> not report CSI on the BWP, report CSI except aperiodic CSI for the
BWP;

2\> not transmit SRS on the BWP;

2\> not transmit on UL-SCH on the BWP;

2\> not transmit on RACH on the BWP;

2\> not transmit PUCCH on the BWP;

2\> clear any configured downlink assignment and any configured uplink
grant Type 2 associated with the SCell respectively;

2\> suspend any configured uplink grant Type 1 associated with the
SCell;

2\> if configured, perform beam failure detection and beam failure
recovery for the SCell if beam failure is detected;

2\> if the SCell is configured as a scheduled cell in
*MC-DCI-SetOfCells* and with the search space for DCI to schedule
multiple cells (as specified in TS 38.213 \[6\]) of the same
*searchSpaceId* as the serving cell in which *MC-DCI-SetOfCells*
containing the SCell is configured:

3\> not monitor the PDCCH for scheduling multiple cells (as specified in
TS 38.213 \[6\]) for the set of cells in *MC-DCI-SetOfCells* including
the SCell.

1\> if a BWP is deactivated or the Serving Cell is PSCell of deactivated
SCG:

2\> not transmit on UL-SCH on the BWP;

2\> not transmit on RACH on the BWP;

2\> not monitor the PDCCH on the BWP;

2\> not transmit PUCCH on the BWP;

2\> not report CSI for the BWP;

2\> not transmit SRS on the BWP;

2\> not receive DL-SCH on the BWP;

2\> clear any configured downlink assignment and configured uplink grant
of configured grant Type 2 on the BWP;

2\> suspend any configured uplink grant of configured grant Type 1 on
the inactive BWP.

Upon initiation of the Random Access procedure on a Serving Cell, after
the selection of carrier for performing Random Access procedure as
specified in clause 5.1.1, the MAC entity shall for the selected carrier
of this Serving Cell:

1\> if PRACH occasions are not configured for the active UL BWP:

2\> if the UE is an (e)RedCap UE; and

2\> if *initialUplinkBWP-RedCap* is configured:

3\> switch the active UL BWP to BWP indicated by
*initialUplinkBWP-RedCap*.

2\> else:

3\> switch the active UL BWP to BWP indicated by *initialUplinkBWP*.

2\> if the Serving Cell is an SpCell:

3\> if the UE is an (e)RedCap UE; and

3\> if *initialDownlinkBWP-RedCap* is configured:

4\> switch the active DL BWP to BWP indicated by
*initialDownlinkBWP-RedCap*.

3\> else:

4\> switch the active DL BWP to BWP indicated by *initialDownlinkBWP*.

1\> else:

2\> if the Serving Cell is an SpCell:

3\> if the active DL BWP does not have the same *bwp-Id* as the active
UL BWP:

4\> switch the active DL BWP to the DL BWP with the same *bwp-Id* as the
active UL BWP.

1\> stop the *bwp-InactivityTimer* associated with the active DL BWP of
this Serving Cell, if running.

1\> if the Serving Cell is SCell:

2\> stop the *bwp-InactivityTimer* associated with the active DL BWP of
SpCell, if running.

1\> perform the Random Access procedure on the active DL BWP of SpCell
and active UL BWP of this Serving Cell.

If the MAC entity receives a PDCCH for BWP switching of a Serving Cell,
the MAC entity shall:

1\> if there is no ongoing Random Access procedure associated with this
Serving Cell; or

1\> if the ongoing Random Access procedure associated with this Serving
Cell is successfully completed upon reception of this PDCCH addressed to
C-RNTI (as specified in clauses 5.1.4, 5.1.4a, and 5.1.5):

2\> cancel, if any, triggered consistent LBT failure for this Serving
Cell;

2\> perform BWP switching to a BWP indicated by the PDCCH.

If the MAC entity receives a PDCCH for BWP switching for a Serving
Cell(s) or a dormancy SCell group(s) while a Random Access procedure
associated with that Serving Cell is ongoing in the MAC entity, it is up
to UE implementation whether to switch BWP or ignore the PDCCH for BWP
switching, except for the PDCCH reception for BWP switching addressed to
the C-RNTI for successful Random Access procedure completion (as
specified in clauses 5.1.4, 5.1.4a, and 5.1.5) in which case the UE
shall perform BWP switching to a BWP indicated by the PDCCH. Upon
reception of the PDCCH for BWP switching other than successful
contention resolution, if the MAC entity decides to perform BWP
switching, the MAC entity shall stop the ongoing Random Access procedure
and initiate a Random Access procedure after performing the BWP
switching; if the MAC decides to ignore the PDCCH for BWP switching, the
MAC entity shall continue with the ongoing Random Access procedure on
the Serving Cell.

Upon reception of RRC (re-)configuration for BWP switching for a Serving
Cell while a Random Access procedure associated with that Serving Cell
is ongoing in the MAC entity, the MAC entity shall stop the ongoing
Random Access procedure and initiate a Random Access procedure after
performing the BWP switching.

Upon reception of RRC (re-)configuration for BWP switching for a Serving
Cell, cancel any triggered consistent LBT failure in this Serving Cell.

The MAC entity shall for each activated Serving Cell configured with
*bwp-InactivityTimer*:

1\> if the *defaultDownlinkBWP-Id* is configured, and the active DL BWP
is not the BWP indicated by the *defaultDownlinkBWP-Id*, and the active
DL BWP is not the BWP indicated by the *dormantBWP-Id* if configured; or

1\> if the UE is neither a RedCap nor an eRedCap UE, and if the
*defaultDownlinkBWP-Id* is not configured, and the active DL BWP is not
the *initialDownlinkBWP*, and the active DL BWP is not the BWP indicated
by the *dormantBWP-Id* if configured; or

1\> if the UE is an (e)RedCap UE, and if the *defaultDownlinkBWP-Id* is
not configured, and *initialDownlinkBWP-RedCap* is not configured, and
the active DL BWP is not the *initialDownlinkBWP*; or

1\> if the UE is an (e)RedCap UE, and if the *defaultDownlinkBWP-Id* is
not configured, and *initialDownlinkBWP-RedCap* is configured, and the
active DL BWP is not the *initialDownlinkBWP-RedCap*:

2\> if a PDCCH addressed to C-RNTI or CS-RNTI indicating downlink
assignment or uplink grant is received on the active BWP; or

2\> if a PDCCH addressed to G-RNTI or G-CS-RNTI configured for multicast
indicating downlink assignment is received on the active BWP; or

2\> if a PDCCH addressed to C-RNTI or CS-RNTI indicating downlink
assignment or uplink grant is received for the active BWP; or

2\> if a MAC PDU is transmitted in a configured uplink grant and LBT
failure indication is not received from lower layers; or

2\> if a MAC PDU is received in a configured downlink assignment for
unicast or MBS multicast:

3\> if there is no ongoing Random Access procedure associated with this
Serving Cell; or

3\> if the ongoing Random Access procedure associated with this Serving
Cell is successfully completed upon reception of this PDCCH addressed to
C-RNTI (as specified in clauses 5.1.4, 5.1.4a and 5.1.5):

4\> start or restart the *bwp-InactivityTimer* associated with the
active DL BWP.

2\> if the *bwp-InactivityTimer* associated with the active DL BWP
expires:

3\> if the *defaultDownlinkBWP-Id* is configured:

4\> perform BWP switching to a BWP indicated by the
*defaultDownlinkBWP-Id*.

3\> else:

4\> if the UE is a (e)RedCap UE; and

4\> if *initialDownlinkBWP-RedCap* is configured:

5\> perform BWP switching to the *initialDownlinkBWP-RedCap*.

4\> else:

5\> perform BWP switching to the *initialDownlinkBWP*.

NOTE: If a Random Access procedure is initiated on an SCell, both this
SCell and the SpCell are associated with this Random Access procedure.

1\> if a PDCCH for BWP switching is received, and the MAC entity
switches the active DL BWP:

2\> if the *defaultDownlinkBWP-Id* is configured, and the MAC entity
switches to the DL BWP which is not indicated by the
*defaultDownlinkBWP-Id* and is not indicated by the *dormantBWP-Id* if
configured; or

2\> if the UE is neither a RedCap nor an eRedCap UE, and if the
*defaultDownlinkBWP-Id* is not configured, and the MAC entity switches
to the DL BWP which is not the *initialDownlinkBWP* and is not indicated
by the *dormantBWP-Id* if configured; or

2\> if the UE is an (e)RedCap UE, and if the *defaultDownlinkBWP-Id* is
not configured, and *initialDownlinkBWP-RedCap* is not configured, and
the MAC entity switches to the DL BWP which is not the
*initialDownlinkBWP*; or

2\> if the UE is an (e)RedCap UE, and if the *defaultDownlinkBWP-Id* is
not configured, and *initialDownlinkBWP-RedCap* is configured, and the
MAC entity switches to the DL BWP which is not the
*initialDownlinkBWP-RedCap*:

3\> start or restart the *bwp-InactivityTimer* associated with the
active DL BWP.

Upon initiation of the Random Access procedure, after selection of the
carrier for performing Random Access procedure as specified in clause
5.1.1, if the UE is an (e)RedCap UE in RRC_IDLE or RRC_INACTIVE mode,
the MAC entity shall:

1\> if *initialUplinkBWP-RedCap* is configured for the selected carrier:

2\> perform the Random Access procedure as specified in clause 5.1 by
using the BWP configured by *initialUplinkBWP-RedCap*.

1\> else:

2\> perform the Random Access procedure as specified in clause 5.1 by
using the BWP configured by *initialUplinkBWP*.

1\> if *initialDownlinkBWP-RedCap* is configured:

> 2\> if the Random Access procedure was initiated for SI request (as
> specified in TS 38.331 \[5\]) and the Random Access Resources for SI
> request have been explicitly provided by RRC, and if the selected
> carrier is SUL carrier:
>
> 3\> monitor the PDCCH on the BWP configured by *initialDownlinkBWP*.
>
> 2\> else:

3\> monitor the PDCCH on the BWP configured by
*initialDownlinkBWP-RedCap*.

1\> else:

2\> monitor the PDCCH on the BWP configured by *initialDownlinkBWP*.