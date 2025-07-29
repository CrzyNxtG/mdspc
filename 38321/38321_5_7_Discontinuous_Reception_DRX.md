## 5.7 Discontinuous Reception (DRX)

The MAC entity may be configured by RRC with a DRX functionality that
controls the UE\'s PDCCH monitoring activity for the MAC entity\'s
C-RNTI, CI-RNTI, CS-RNTI, INT-RNTI, SFI-RNTI, SP-CSI-RNTI,
TPC-PUCCH-RNTI, TPC-PUSCH-RNTI, TPC-SRS-RNTI, AI-RNTI, SL-RNTI,
SL-CS-RNTI, SL-PRS-RNTI, SL-PRS-CS-RNTI, SL Semi-Persistent Scheduling
V-RNTI and cellDTRX-RNTI. When using DRX operation, the MAC entity shall
also monitor PDCCH according to requirements found in other clauses of
this specification. When in RRC_CONNECTED, if DRX is configured, for all
the activated Serving Cells, the MAC entity may monitor the PDCCH
discontinuously using the DRX operation specified in this clause;
otherwise the MAC entity shall monitor the PDCCH as specified in TS
38.213 \[6\].

NOTE 1: Void

RRC controls DRX operation by configuring the following parameters:

\- *drx-onDurationTimer*: the duration at the beginning of a DRX cycle;

\- *drx-SlotOffset*: the delay before starting the
*drx-onDurationTimer*;

\- *drx-InactivityTimer*: the duration after the PDCCH occasion in which
a PDCCH indicates a new UL, DL or SL transmission for the MAC entity;

\- *drx-RetransmissionTimerDL* (per DL HARQ process except for the
broadcast process): the maximum duration until a DL retransmission is
received;

\- *drx-RetransmissionTimerUL* (per UL HARQ process): the maximum
duration until a grant for UL retransmission is received;

\- *drx-LongCycleStartOffset*: the Long DRX cycle and *drx-StartOffset*
which defines the subframe where the Long and Short DRX cycle starts;

\- *drx-NonIntegerLongCycleStartOffset* (optional): the Long DRX cycle
and *drx-StartOffset* which defines the subframe where the Long and
Short DRX cycle start, when the length of the Long DRX cycle and/or the
short DRX cycle is not an integer;

\- *drx-ShortCycle* (optional): the Short DRX cycle;

\- *drx-NonIntegerShortCycle* (optional): the Short DRX cycle whose
length is not an integer;

\- *drx-ShortCycleTimer* (optional): the duration the UE shall follow
the Short DRX cycle;

\- *drx-HARQ-RTT-TimerDL* (per DL HARQ process except for the broadcast
process): the minimum duration before a DL assignment for HARQ
retransmission is expected by the MAC entity;

\- *drx-HARQ-RTT-TimerUL* (per UL HARQ process): the minimum duration
before a UL HARQ retransmission grant is expected by the MAC entity;

\- *drx-RetransmissionTimerSL* (per sidelink process): the maximum
duration until a grant for SL retransmission is received;

\- *drx-HARQ-RTT-TimerSL* (per sidelink process): the minimum duration
before an SL retransmission grant is expected by the MAC entity;

\- *drx-LastTransmissionUL* (optional): the configuration to start
*drx-HARQ-RTT-TimerUL* after the last transmission within a bundle;

\- *ps-Wakeup* (optional): the configuration to start associated
*drx-onDurationTimer* in case DCP is monitored but not detected;

\- *ps-TransmitOtherPeriodicCSI* (optional): the configuration to report
periodic CSI that is not L1-RSRP on PUCCH during the time duration
indicated by *drx-onDurationTimer* in case DCP is configured but
associated *drx-onDurationTimer* is not started;

\- *ps-TransmitPeriodicL1-RSRP* (optional): the configuration to
transmit periodic CSI that is L1-RSRP on PUCCH during the time duration
indicated by *drx-onDurationTimer* in case DCP is configured but
associated *drx-onDurationTimer* is not started;

\- *downlinkHARQ-FeedbackDisabled* (optional): the configuration to
disable HARQ feedback per DL HARQ process;

\- *uplinkHARQ-Mode* (optional): the configuration to set *HARQmodeA* or
*HARQmodeB* per UL HARQ process;

\- *disableCG-RetransmissionMonitoring* (optional): the configuration to
disable starting *drx-HARQ-RTT-TimerUL* for UL transmission over a
configured uplink grant;

\- *drx-TimeReferenceSFN* (optional): the configuration to indicate how
UE initializes of *DRX_SFN_COUNTER*.

The following UE variable is used for the DRX operation if
*drx-NonIntegerLongCycleStartOffset* is configured:

\- *DRX_SFN_COUNTER*: the counter that increments when SFN changes to 0.
The maximum value of this counter is at least 65535.

Serving Cells of a MAC entity may be configured by RRC in two DRX groups
with separate DRX parameters. When RRC does not configure a secondary
DRX group, there is only one DRX group and all Serving Cells belong to
that one DRX group. When two DRX groups are configured, each Serving
Cell is uniquely assigned to either of the two groups. The DRX
parameters that are separately configured for each DRX group are:
*drx-onDurationTimer*, *drx-InactivityTimer*. The DRX parameters that
are common to the DRX groups are: *drx-SlotOffset*,
*drx-RetransmissionTimerDL*, *drx-RetransmissionTimerUL*,
*drx-LongCycleStartOffset*, *drx-NonIntegerLongCycleStartOffset*,
*drx-ShortCycle* (optional), *drx-NonIntegerShortCycle* (optional),
*drx-ShortCycleTimer* (optional), *drx-HARQ-RTT-TimerDL*, and
*drx-HARQ-RTT-TimerUL*.

When DRX is configured, the Active Time for Serving Cells in a DRX group
includes the time while:

\- *drx-onDurationTimer* or *drx-InactivityTimer* configured for the DRX
group is running; or

\- *drx-RetransmissionTimerDL*, *drx-RetransmissionTimerUL* or
*drx-RetransmissionTimerSL* is running on any Serving Cell in the DRX
group; or

\- *ra-ContentionResolutionTimer* (as described in clause 5.1.5) or
*msgB-ResponseWindow* (as described in clause 5.1.4a) is running; or

\- a Scheduling Request is sent on PUCCH and is pending (as described in
clause 5.4.4 or 5.22.1.5). If this Serving Cell is part of a
non-terrestrial network, the Active Time is started after the Scheduling
Request transmission that is performed when the *SR_COUNTER* is 0 for
all the SR configurations with pending SR(s) plus the UE-gNB RTT; or

\- a PDCCH indicating a new transmission addressed to the C-RNTI of the
MAC entity has not been received after successful reception of a Random
Access Response for the Random Access Preamble not selected by the MAC
entity among the contention-based Random Access Preamble (as described
in clauses 5.1.4 and 5.1.4a); or

\- there is an ongoing RACH-less LTM cell switch; or

\- there is an ongoing RACH-less handover in a terrestrial network.

The following MAC timers are used for DRX operation in a non-terrestrial
network:

\- *HARQ-RTT-TimerDL-NTN* (per DL HARQ process configured with HARQ
feedback enabled): the minimum duration before a DL assignment for HARQ
retransmission is expected by the MAC entity;

\- *HARQ-RTT-TimerUL-NTN* (per UL HARQ process configured with
*HARQModeA*): the minimum duration before a UL HARQ retransmission grant
is expected by the MAC entity.

When DRX is not configured and multicast DRX is configured for a G-RNTI
or G-CS-RNTI, the MAC entity shall:

1\> monitor the PDCCH as specified in TS 38.213 \[6\];

1\> if a MAC PDU is received in a configured downlink assignment for
unicast; or

1\> if the PDCCH indicates a DL unicast transmission:

2\> stop the *drx-RetransmissionTimerDL-PTM* for the corresponding HARQ
process.

When DRX is configured, the MAC entity shall:

1\> if a MAC PDU is received in a configured downlink assignment for
unicast:

2\> if this Serving Cell is configured with
*downlinkHARQ-FeedbackDisabled*:

3\> if the corresponding HARQ process is configured with HARQ feedback
enabled:

4\> set *HARQ-RTT-TimerDL-NTN* for the corresponding HARQ process equal
to *drx-HARQ-RTT-TimerDL* plus the latest available UE-gNB RTT value;

4\> start the *HARQ-RTT-TimerDL-NTN* for the corresponding HARQ process
in the first symbol after the end of the corresponding transmission
carrying the DL HARQ feedback.

2\> else:

3\> start the *drx-HARQ-RTT-TimerDL* for the corresponding HARQ process
in the first symbol after the end of the corresponding transmission
carrying the DL HARQ feedback.

NOTE 1a: Void.

NOTE 1b: Void.

2\> stop the *drx-RetransmissionTimerDL* for the corresponding HARQ
process;

2\> stop the *drx-RetransmissionTimerDL-PTM* for the corresponding HARQ
process.

1\> if a MAC PDU is transmitted in a configured uplink grant and LBT
failure indication is not received from lower layers:

2\> if this Serving Cell is configured with *uplinkHARQ-Mode*:

3\> if the corresponding HARQ process is configured as *HARQModeA*:

4\> set *HARQ-RTT-TimerUL-NTN* for the corresponding HARQ process equal
to *drx-HARQ-RTT-TimerUL* plus the latest available UE-gNB RTT value;

4\> if *drx-LastTransmissionUL* is configured:

5\> start the *HARQ-RTT-TimerUL-NTN* for the corresponding HARQ process
in the first symbol after the end of the last transmission (within a
bundle) of the corresponding PUSCH transmission.

4\> else:

5\> start the *HARQ-RTT-TimerUL-NTN* for the corresponding HARQ process
in the first symbol after the end of the first transmission (within a
bundle) of the corresponding PUSCH transmission.

2\> else:

3\> if *disableCG-RetransmissionMonitoring* is not configured for the
configured uplink grant:

4\> if *drx-LastTransmissionUL* is configured:

5\> start the *drx-HARQ-RTT-TimerUL* for the corresponding HARQ process
in the first symbol after the end of the last transmission (within a
bundle) of the corresponding PUSCH transmission.

4\> else:

5\> start the *drx-HARQ-RTT-TimerUL* for the corresponding HARQ process
in the first symbol after the end of the first transmission (within a
bundle) of the corresponding PUSCH transmission.

2\> stop the *drx-RetransmissionTimerUL* for the corresponding HARQ
process at the first transmission (within a bundle) of the corresponding
PUSCH transmission.

1\> if a MAC PDU is transmitted in a configured sidelink grant:

2\> if the PUCCH resource is configured:

3\> start the *drx-HARQ-RTT-TimerSL* for the corresponding HARQ process
in the first symbol after the end of the corresponding PUCCH
transmission carrying the SL HARQ feedback; or

3\> start the *drx-HARQ-RTT-TimerSL* for the corresponding HARQ process
in the first symbol after the end of the corresponding PUCCH resource
for the SL HARQ feedback when the PUCCH is not transmitted;

3\> stop the *drx-RetransmissionTimerSL* for the corresponding HARQ
process.

2\> else:

3\> start the *drx-HARQ-RTT-TimerSL* for the corresponding HARQ process
at the first symbol after the end of the corresponding PSSCH
transmission;

3\> stop the *drx-RetransmissionTimerSL* for the corresponding HARQ
process.

1\> if a *drx-HARQ-RTT-TimerDL* expires:

2\> if the data of the corresponding HARQ process was not successfully
decoded:

3\> start the *drx-RetransmissionTimerDL* for the corresponding HARQ
process in the first symbol after the expiry of *drx-HARQ-RTT-TimerDL*.

1\> if a *HARQ-RTT-TimerDL-NTN* expires:

2\> if the data of the corresponding HARQ process was not successfully
decoded:

3\> start the *drx-RetransmissionTimerDL* for the corresponding HARQ
process in the first symbol after the expiry of *HARQ-RTT-TimerDL-NTN*.

1\> if a *drx-HARQ-RTT-TimerUL* expires:

2\> start the *drx-RetransmissionTimerUL* for the corresponding HARQ
process in the first symbol after the expiry of *drx-HARQ-RTT-TimerUL*.

1\> if a *HARQ-RTT-TimerUL-NTN* expires:

2\> start the *drx-RetransmissionTimerUL* for the corresponding HARQ
process in the first symbol after the expiry of *HARQ-RTT-TimerUL-NTN*.

1\> if a *drx-HARQ-RTT-TimerSL* expires:

2\> if a HARQ NACK feedback for the corresponding HARQ process is
transmitted on PUCCH; or

2\> if a HARQ NACK feedback for the corresponding HARQ process is
generated but not transmitted on PUCCH; or

2\> if the PUCCH resource is not configured for the SL grant:

3\> start the *drx-RetransmissionTimerSL* for the corresponding HARQ
process in the first symbol after the expiry of *drx-HARQ-RTT-TimerSL*.

NOTE 1c: The UE handles the *drx-RetransmissionTimerSL* operation when
*sl-PUCCH-Config* is configured by RRC but PUCCH resource is not
scheduled same as when *sl-PUCCH-Config* is not configured.

1\> if a DRX Command MAC CE indicated by PDCCH addressed to C-RNTI or
CS-RNTI, or by a configured downlink assignment for unicast transmission
or a Long DRX Command MAC CE is received:

2\> stop *drx-onDurationTimer* for each DRX group;

2\> stop *drx-InactivityTimer* for each DRX group.

1\> if *drx-InactivityTimer* for a DRX group expires:

2\> if the Short DRX cycle is configured:

3\> start or restart *drx-ShortCycleTimer* for this DRX group in the
first symbol after the expiry of *drx-InactivityTimer*;

3\> use the Short DRX cycle for this DRX group.

2\> else:

3\> use the Long DRX cycle for this DRX group.

1\> if a DRX Command MAC CE indicated by PDCCH addressed to C-RNTI or
CS-RNTI, or by a configured downlink assignment for unicast transmission
is received:

2\> if the Short DRX cycle is configured:

3\> start or restart *drx-ShortCycleTimer* for each DRX group in the
first symbol after the end of DRX Command MAC CE reception;

3\> use the Short DRX cycle for each DRX group.

2\> else:

3\> use the Long DRX cycle for each DRX group.

1\> if *drx-ShortCycleTimer* for a DRX group expires:

2\> use the Long DRX cycle for this DRX group.

1\> if a Long DRX Command MAC CE is received:

2\> stop *drx-ShortCycleTimer* for each DRX group;

2\> use the Long DRX cycle for each DRX group.

1\> if the *drx-NonIntegerLongCycleStartOffset* is configured:

2\> increment *DRX_SFN_COUNTER* by 1 in the first symbol of a slot in
which SFN changes to 0;

2\> if DRX is (re-)configured by RRC:

3\> if *drx-TimeReferenceSFN* is included in the RRC (re-)configuration
which is received during the first half of a hyper frame (i.e., SFN is
between 0 and 511):

4\> set *DRX_SFN_COUNTER* to 1.

3\> else:

4\> set *DRX_SFN_COUNTER* to 0.

1\> if the Short DRX cycle is used for a DRX group and the
*drx-NonIntegerShortCycle* is not configured, and \[(SFN × 10) +
subframe number\] modulo (*drx-ShortCycle*) = (*drx-StartOffset*) modulo
(*drx-ShortCycle*); or

1\> if the Short DRX cycle is used for a DRX group and the
*drx-NonIntegerShortCycle* is configured, and floor(\[(*DRX_SFN_COUNTER*
× 10240) + (SFN × 10) + subframe number − *drx-StartOffset*\] modulo
(*drx-NonIntegerShortCycle*)) = 0:

2\> start *drx-onDurationTimer* for this DRX group after
*drx-SlotOffset* from the beginning of the subframe.

1\> if the Long DRX cycle is used for a DRX group and the
*drx-NonIntegerLongCycleStartOffset* is not configured, and \[(SFN ×
10) + subframe number\] modulo (*drx-LongCycle*) = *drx-StartOffset*; or

1\> if the Long DRX cycle is used for a DRX group and the
*drx-NonIntegerLongCycleStartOffset* is configured, and
floor(\[(*DRX_SFN_COUNTER* × 10240) + (SFN × 10) + subframe number\]
modulo (*drx-NonIntegerLongCycle*)) = *drx-StartOffset*:

2\> if DCP monitoring is configured for the active DL BWP as specified
in TS 38.213 \[6\], clause 10.3:

3\> if DCP indication associated with the current DRX cycle received
from lower layer indicated to start *drx-onDurationTimer*, as specified
in TS 38.213 \[6\]; or

3\> if all DCP occasion(s) in time domain, as specified in TS 38.213
\[6\], associated with the current DRX cycle occurred in Active Time
considering grants/assignments/DRX Command MAC CE/Long DRX Command MAC
CE received and Scheduling Request sent until 4 ms prior to start of the
last DCP occasion, or during a measurement gap, or when the MAC entity
monitors for a PDCCH transmission on the search space indicated by
*recoverySearchSpaceId* of the SpCell identified by the C-RNTI while the
*ra-ResponseWindow* is running (as specified in clause 5.1.4); or

3\> if *ps-Wakeup* is configured with value *true* and DCP indication
associated with the current DRX cycle has not been received from lower
layers:

4\> start *drx-onDurationTimer* after *drx-SlotOffset* from the
beginning of the subframe.

2\> else:

3\> start *drx-onDurationTimer* for this DRX group after
*drx-SlotOffset* from the beginning of the subframe.

NOTE 2: In case of unaligned SFN across carriers in a cell group, the
SFN of the SpCell is used to calculate the DRX duration.

1\> if a DRX group is in Active Time:

2\> monitor the PDCCH on the Serving Cells in this DRX group as
specified in TS 38.213 \[6\];

2\> if the PDCCH indicates a DL transmission; or

2\> if the PDCCH indicates a one-shot HARQ feedback as specified in
clause 9.1.4 of TS 38.213 \[6\]; or

2\> if the PDCCH indicates a retransmission of HARQ feedback as
specified in clause 9.1.5 of TS 38.213 \[6\]:

3\> if this Serving Cell is configured with
*downlinkHARQ-FeedbackDisabled*:

4\> if at least one of the corresponding HARQ process(es) is configured
with HARQ feedback enabled:

5\> set *HARQ-RTT-TimerDL-NTN* for the corresponding HARQ process(es)
equal to *drx-HARQ-RTT-TimerDL* plus the latest available UE-gNB RTT
value;

5\> if the UE is configured with one-shot HARQ Feedback:

6\> start or restart the *HARQ-RTT-TimerDL-NTN* for the corresponding
HARQ process(es) whose HARQ feedback is enabled and reported in the
first symbol after the end of the corresponding transmission carrying
the DL HARQ feedback.

5\> else:

6\> start the *HARQ-RTT-TimerDL-NTN* for the corresponding HARQ process
in the first symbol after the end of the corresponding transmission
carrying the DL HARQ feedback.

3\> else:

4\> start or restart the *drx-HARQ-RTT-TimerDL* for the corresponding
HARQ process(es) whose HARQ feedback is reported in the first symbol
after the end of the corresponding transmission carrying the DL HARQ
feedback.

NOTE 3: When HARQ feedback is postponed by PDSCH-to-HARQ_feedback timing
indicating an inapplicable k1 value, as specified in TS 38.213 \[6\],
the corresponding transmission opportunity to send the DL HARQ feedback
is indicated in a later PDCCH requesting the HARQ-ACK feedback.

3\> stop the *drx-RetransmissionTimerDL* for the corresponding HARQ
process(es) whose HARQ feedback is reported;

3\> stop the *drx-RetransmissionTimerDL-PTM* for the corresponding HARQ
process;

3\> if the PDSCH-to-HARQ_feedback timing indicate an inapplicable k1
value as specified in TS 38.213 \[6\]:

4\> start the *drx-RetransmissionTimerDL* in the first symbol after the
(end of the last) PDSCH transmission (within a bundle) for the
corresponding HARQ process.

2\> if the PDCCH indicates a UL transmission:

3\> if this Serving Cell is configured with *uplinkHARQ-Mode*:

4\> if the corresponding HARQ process is configured as *HARQModeA*:

5\> set *HARQ-RTT-TimerUL-NTN* for the corresponding HARQ process equal
to *drx-HARQ-RTT-TimerUL* plus the latest available UE-gNB RTT value;

5\> if *drx-LastTransmissionUL* is configured:

6\> start the *HARQ-RTT-TimerUL-NTN* for the corresponding HARQ process
in the first symbol after the end of the last transmission (within a
bundle) of the corresponding PUSCH transmission.

5\> else:

6\> start the *HARQ-RTT-TimerUL-NTN* for the corresponding HARQ process
in the first symbol after the end of the first transmission (within a
bundle) of the corresponding PUSCH transmission.

3\> else:

4\> if *drx-LastTransmissionUL* is configured:

5\> start the *drx-HARQ-RTT-TimerUL* for the corresponding HARQ process
in the first symbol after the end of the last transmission (within a
bundle) of the corresponding PUSCH transmission.

4\> else:

5\> start the *drx-HARQ-RTT-TimerUL* for the corresponding HARQ process
in the first symbol after the end of the first transmission (within a
bundle) of the corresponding PUSCH transmission.

3\> stop the *drx-RetransmissionTimerUL* for the corresponding HARQ
process.

2\> if the PDCCH indicates an SL transmission:

3\> if the PUCCH resource is configured:

4\> start the *drx-HARQ-RTT-TimerSL* for the corresponding HARQ process
in the first symbol after the end of the corresponding PUCCH
transmission carrying the SL HARQ feedback; or

4\> start the *drx-HARQ-RTT-TimerSL* for the corresponding HARQ process
in the first symbol after the end of the corresponding PUCCH resource
for the SL HARQ feedback when the PUCCH is not transmitted;

4\> stop the *drx-RetransmissionTimerSL* for the corresponding HARQ
process.

3\> else:

4\> start the *drx-HARQ-RTT-TimerSL* for the corresponding HARQ process
at the first symbol after end of PDCCH occasion;

4\> stop the *drx-RetransmissionTimerSL* for the corresponding HARQ
process.

2\> if the PDCCH indicates a new transmission (DL, UL or SL) on a
Serving Cell in this DRX group:

3\> start or restart *drx-InactivityTimer* for this DRX group in the
first symbol after the end of the PDCCH reception.

NOTE 3a: A PDCCH indicating activation of SPS, configured grant type 2,
or configured sidelink grant of configured grant Type 2 is considered to
indicate a new transmission.

NOTE 3b: If the PDCCH reception includes two PDCCH candidates from
corresponding search spaces, as described in clause 10.1 in TS 38.213
\[6\], start or restart *drx-InactivityTimer* for this DRX group in the
first symbol after the end of the PDCCH candidate that ends later in
time.

2\> if a HARQ process receives downlink feedback information and
acknowledgement is indicated:

3\> stop the *drx-RetransmissionTimerUL* for the corresponding HARQ
process.

1\> if DCP monitoring is configured for the active DL BWP as specified
in TS 38.213 \[6\], clause 10.3; and

1\> if the current symbol n occurs within *drx-onDurationTimer*
duration; and

1\> if *drx-onDurationTimer* associated with the current DRX cycle is
not started as specified in this clause:

2\> if the MAC entity would not be in Active Time considering
grants/assignments/DRX Command MAC CE/Long DRX Command MAC CE received
and Scheduling Request sent until 4 ms prior to symbol n when evaluating
all DRX Active Time conditions as specified in this clause; and

2\> if *allowCSI-SRS-Tx-MulticastDRX-Active* is not configured, or if
*cfr-ConfigMulticast* is not configured for any of the active BWP(s) of
the Serving Cell(s), or if all multicast DRXes would not be in Active
Time considering multicast assignments/DRX Command MAC CE for MBS
multicast received until 4 ms prior to symbol n when evaluating all DRX
Active Time conditions as specified in Clause 5.7b and all multicast
sessions are configured with multicast DRX:

3\> not transmit periodic SRS and semi-persistent SRS defined in TS
38.214 \[7\];

3\> not report semi-persistent CSI configured on PUSCH;

3\> not report semi-persistent CSI on PUCCH;

3\> if *ps-TransmitPeriodicL1-RSRP* is not configured with value *true*:

4\> not report periodic CSI that is L1-RSRP on PUCCH.

3\> if *ps-TransmitOtherPeriodicCSI* is not configured with value
*true*:

4\> not report periodic CSI that is not L1-RSRP on PUCCH.

1\> else:

2\> in current symbol n, if a DRX group would not be in Active Time
considering grants/assignments scheduled on Serving Cell(s) in this DRX
group and DRX Command MAC CE/Long DRX Command MAC CE received and
Scheduling Request sent until 4 ms prior to symbol n when evaluating all
DRX Active Time conditions as specified in this clause; and

2\> if *allowCSI-SRS-Tx-MulticastDRX-Active* is not configured, or if
*cfr-ConfigMulticast* is not configured for any of the active BWP(s) of
the Serving Cell(s), or, in current symbol n, if all multicast DRXes
corresponding to the DRX group would not be in Active Time considering
multicast assignments/DRX Command MAC CE for MBS multicast received
until 4 ms prior to symbol n when evaluating all DRX Active Time
conditions as specified in Clause 5.7b and all multicast sessions
corresponding to the DRX group are configured with multicast DRX:

3\> not transmit periodic SRS and semi-persistent SRS defined in TS
38.214 \[7\] in this DRX group;

3\> not report CSI on PUCCH and semi-persistent CSI configured on PUSCH
in this DRX group.

2\> if CSI masking (*csi-Mask*) is setup by upper layers:

3\> in current symbol n, if *drx-onDurationTimer* of a DRX group would
not be running considering grants/assignments scheduled on Serving
Cell(s) in this DRX group and DRX Command MAC CE/Long DRX Command MAC CE
received until 4 ms prior to symbol n when evaluating all DRX Active
Time conditions as specified in this clause; and

3\> if *allowCSI-SRS-Tx-MulticastDRX-Active* is not configured, or if
*cfr-ConfigMulticast* is not configured for any of the active BWP(s) of
the Serving Cell(s), or, in current symbol n, if
*drx-onDurationTimerPTM(s)* of all multicast DRXes corresponding to the
DRX group would not be running considering DRX Command MAC CE for MBS
multicast received until 4 ms prior to symbol n when evaluating all DRX
Active Time conditions as specified in Clause 5.7b and all multicast
sessions corresponding to the DRX group are configured with multicast
DRX:

4\> not report CSI on PUCCH in this DRX group.

NOTE 4: If a UE multiplexes a CSI configured on PUCCH with other
overlapping UCI(s) according to the procedure specified in TS 38.213
\[6\] clause 9.2.5 and this CSI multiplexed with other UCI(s) would be
reported on a PUCCH resource either outside DRX Active Time of the DRX
group in which this PUCCH is configured or outside the on-duration
period of the DRX group in which this PUCCH is configured if CSI masking
is setup by upper layers, it is up to UE implementation whether to
report this CSI multiplexed with other UCI(s).

NOTE 5: In NTN, if a DRX group would not be in Active Time or
*drx-onDurationTimer* would not be running prior to symbol n, it is up
to UE implementation whether to report periodic and semi-persistent
CSI/SRS.

The MAC entity shall ensure no rounding error is generated when
performing the modulus operation with *drx-NonIntegerShortCycle* or
*drx-NonIntegerLongCycle* as the divisor.

Regardless of whether the MAC entity is monitoring PDCCH or not on the
Serving Cells in a DRX group, the MAC entity transmits HARQ feedback,
aperiodic CSI on PUSCH, and aperiodic SRS defined in TS 38.214 \[7\] on
the Serving Cells in the DRX group when such is expected.

The MAC entity needs not to monitor the PDCCH if it is not a complete
PDCCH occasion (e.g. the Active Time starts or ends in the middle of a
PDCCH occasion).

When *drx-LastTransmissionUL* is configured, *drx-HARQ-RTT-TimerUL* or
*HARQ-RTT-TimerUL-NTN* is started after the last PUSCH transmission
occasion of a bundle regardless of whether that last PUSCH transmission
occasion is used for a PUSCH transmission for that bundle or not.