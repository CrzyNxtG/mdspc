## 10.6 Activation/Deactivation Mechanism

To enable reasonable UE battery consumption when CA is configured, an
activation/deactivation mechanism of Cells is supported. When an SCell
is deactivated, the UE does not need to receive the corresponding PDCCH
or PDSCH, cannot transmit in the corresponding uplink, nor is it
required to perform CQI measurements. Conversely, when an SCell is
active, the UE shall receive PDSCH and PDCCH (if the UE is configured to
monitor PDCCH from this SCell) and is expected to be able to perform CQI
measurements. NG-RAN ensures that while PUCCH SCell (a Secondary Cell
configured with PUCCH) is deactivated, SCells of secondary PUCCH group
(a group of SCells whose PUCCH signalling is associated with the PUCCH
on the PUCCH SCell) should not be activated. NG-RAN ensures that SCells
mapped to PUCCH SCell are deactivated before the PUCCH SCell is changed
or removed.

When reconfiguring the set of serving cells:

\- SCells added to the set are initially activated or deactivated;

\- SCells which remain in the set (either unchanged or reconfigured) do
not change their activation status (*activated* or *deactivated*).

At handover, LTM cell switch execution or connection resume from
RRC_INACTIVE:

\- SCells are activated or deactivated.

To enable reasonable UE battery consumption when BA is configured, only
one UL BWP for each uplink carrier and one DL BWP or only one DL/UL BWP
pair can be active at a time in an active serving cell, all other BWPs
that the UE is configured with being deactivated. On deactivated BWPs,
the UE does not monitor the PDCCH, does not transmit on PUCCH, PRACH and
UL-SCH.

To enable fast SCell activation when CA is configured, one dormant BWP
can be configured for an SCell. If the active BWP of the activated SCell
is a dormant BWP, the UE stops monitoring PDCCH and transmitting
SRS/PUSCH/PUCCH on the SCell but continues performing CSI measurements,
AGC and beam management, if configured. A DCI is used to control
entering/leaving the dormant BWP for one or more SCell(s) or one or more
SCell group(s).

The dormant BWP is one of the UE\'s dedicated BWPs configured by network
via dedicated RRC signalling. The SpCell and PUCCH SCell cannot be
configured with a dormant BWP.

To enable fast SCell activation when CA is configured, aperiodic CSI-RS
for tracking for fast SCell activation can be configured for an SCell to
assist AGC and time/frequency synchronization. A MAC CE is used to
trigger activation of one or more SCell(s) and trigger the aperiodic
CSI-RS for tracking for fast SCell activation for a (set of) deactivated
SCell(s).

To reduce unknown SCell activation delay, the measurement reporting for
fast unknown SCell activation can be configured. The RRC measurement
report is initiated when UE receives SCell Activation MAC CE to
activate, at least, one SCell which is unknown SCell and has the valid
L3 measurement result according to the requirements specified in clause
6.3 of TS 38.133 \[13\]. In addition, the delay requirement of unknown
SCell activation can be reduced by beam sweeping factor reduction or
shorter measurement interval based on UE capability as specified in TS
38.133 \[13\].