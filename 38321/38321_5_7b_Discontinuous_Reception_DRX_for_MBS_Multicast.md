## 5.7b Discontinuous Reception (DRX) for MBS Multicast

For MBS multicast, the MAC entity may be configured by RRC with a DRX
functionality per G-RNTI or per G-CS-RNTI that controls the UE\'s PDCCH
monitoring activity for the MAC entity\'s G-RNTI(s) and G-CS-RNTI(s) as
specified in TS 38.331 \[5\]. When in RRC_CONNECTED, if multicast DRX is
configured for a G-RNTI or G-CS-RNTI, the MAC entity is allowed to
monitor the PDCCH for this G-RNTI or G-CS-RNTI discontinuously using the
multicast DRX operation specified in this clause; otherwise the MAC
entity monitors the PDCCH for this G-RNTI or G-CS-RNTI as specified in
TS 38.213 \[6\]. When in RRC_INACTIVE, if the UE is configured to
receive multicast in RRC_INACTIVE and multicast DRX is configured for a
G-RNTI, the MAC entity is allowed to monitor the PDCCH for this G-RNTI
discontinuously using the multicast DRX operation specified in this
clause; otherwise the MAC entity monitors the PDCCH for this G-RNTI as
specified in TS 38.213 \[6\]. The multicast DRX operation specified in
this clause is performed independently for each G-RNTI or G-CS-RNTI and
independently from the DRX operation specified in clauses 5.7 and 5.7a.

RRC controls multicast DRX operation per G-RNTI or per G-CS-RNTI by
configuring the following parameters:

\- *drx-onDurationTimerPTM*: the duration at the beginning of a DRX
cycle;

\- *drx-SlotOffsetPTM*: the delay before starting the
*drx-onDurationTimerPTM*;

\- *drx-InactivityTimerPTM*: the duration after the PDCCH occasion in
which a PDCCH indicates a new DL multicast transmission for the MAC
entity;

\- *drx-LongCycleStartOffsetPTM*: the long DRX cycle *drx-LongCycle-PTM*
and *drx-StartOffset-PTM* which defines the subframe where the long DRX
cycle starts;

\- *drx-RetransmissionTimerDL-PTM* (per DL HARQ process for MBS
multicast): the maximum duration until a DL multicast retransmission is
received;

\- *drx-HARQ-RTT-TimerDL-PTM* (per DL HARQ process for MBS multicast):
the minimum duration before a DL multicast assignment for HARQ
retransmission is expected by the MAC entity.

The following MAC timer is used for DRX operation in a non-terrestrial
network:

\- *HARQ-RTT-TimerDL-PTM-NTN* (per DL HARQ process for MBS multicast):
the minimum duration before a DL multicast assignment for HARQ
retransmission is expected by the MAC entity.

When multicast DRX is configured for a G-RNTI or G-CS-RNTI, the Active
Time includes the time while:

\- *drx-onDurationTimerPTM* or *drx-InactivityTimerPTM* or
*drx-RetransmissionTimerDL-PTM* for this G-RNTI or G-CS-RNTI is running.

When multicast DRX is not configured for a G-RNTI or G-CS-RNTI, and the
*cfr-ConfigMulticast* is configured for at least one of the active
BWP(s) of the Serving Cell(s), and unicast DRX is configured, the MAC
entity shall for this G-RNTI or G-CS-RNTI:

1\> monitor the PDCCH as specified in TS 38.213 \[6\];

1\> if the PDCCH indicates a DL multicast transmission; or

1\> if a MAC PDU is received in a configured downlink multicast
assignment:

2\> stop the *drx-RetransmissionTimerDL* for the corresponding HARQ
process.

1\> if the PDCCH addressed to G-RNTI indicates a DL multicast
transmission; or

1\> if the PDCCH addressed to G-CS-RNTI indicates a DL multicast
transmission and CS-RNTI is configured; or

1\> if a MAC PDU is received in a configured downlink multicast
assignment and CS-RNTI is configured:

2\> if the first HARQ-ACK reporting mode (i.e. ack-nack) is used as
specified in TS 38.213 \[6\]; and

2\> if HARQ feedback for MBS multicast is enabled:

3\> if the MAC PDU is received on a non-terrestrial network and the UE
supports *harq-RTT-TimerDL-ForNTN-MulticastMBS-r17*:

4\> set *HARQ-RTT-TimerDL-NTN* for the corresponding HARQ process equal
to *drx-HARQ-RTT-TimerDL* plus the latest available UE-gNB RTT value;

4\> start the *HARQ-RTT-TimerDL-NTN* for the corresponding HARQ process
in the first symbol after the end of the corresponding transmission
carrying the DL HARQ feedback.

3\> else:

4\> start the *drx-HARQ-RTT-TimerDL* for the corresponding HARQ process
in the first symbol after the end of the corresponding transmission
carrying the DL HARQ feedback.

When multicast DRX is configured for a G-RNTI or G-CS-RNTI, and the
*cfr-ConfigMulticast* is configured for at least one of the active
BWP(s) of the Serving Cell(s), or when multicast DRX is configured for a
G-RNTI for multicast in RRC_INACTVE, the MAC entity shall for this
G-RNTI or G-CS-RNTI:

1\> if a MAC PDU is received in a configured downlink multicast
assignment:

2\> if HARQ feedback for MBS multicast is enabled:

3\> if the MAC PDU is received on a non-terrestrial network and the UE
supports *harq-RTT-TimerDL-ForNTN-MulticastMBS-r17*:

4\> set *HARQ-RTT-TimerDL-PTM-NTN* for the corresponding HARQ process
equal to *drx-HARQ-RTT-TimerDL-PTM* plus the latest available UE-gNB RTT
value;

4\> start the *HARQ-RTT-TimerDL-PTM-NTN* for the corresponding HARQ
process in the first symbol after the end of the corresponding
transmission carrying the DL HARQ feedback.

3\> else:

4\> start the *drx-HARQ-RTT-TimerDL-PTM* for the corresponding HARQ
process in the first symbol after the end of the corresponding
transmission carrying the DL HARQ feedback;

3\> if the first HARQ-ACK reporting mode (i.e. ack-nack) is used as
specified in TS 38.213 \[6\]; and

3\> if CS-RNTI is configured:

4\> if the MAC PDU is received on a non-terrestrial network and the UE
supports *harq-RTT-TimerDL-ForNTN-MulticastMBS-r17*:

5\> set *HARQ-RTT-TimerDL-NTN* for the corresponding HARQ process equal
to *drx-HARQ-RTT-TimerDL* plus the latest available UE-gNB RTT value;

5\> start the *HARQ-RTT-TimerDL-NTN* for the corresponding HARQ process
in the first symbol after the end of the corresponding transmission
carrying the DL HARQ feedback.

4\> else:

5\> start the *drx-HARQ-RTT-TimerDL* for the corresponding HARQ process
in the first symbol after the end of the corresponding transmission
carrying the DL HARQ feedback.

2\> else if *drx-HARQ-RTT-TimerDL-PTM* is configured:

3\> if the MAC PDU is received on a non-terrestrial network and the UE
supports *harq-RTT-TimerDL-ForNTN-MulticastMBS-r17*:

4\> set *HARQ-RTT-TimerDL-PTM-NTN* for the corresponding HARQ process
equal to *drx-HARQ-RTT-TimerDL-PTM* plus the latest available UE-gNB RTT
value;

4\> start the *HARQ-RTT-TimerDL-PTM-NTN* for the corresponding HARQ
process in the first symbol after the end of the corresponding
transmission carrying the DL HARQ feedback that would be performed if
HARQ feedback were enabled.

3\> else:

4\> start the *drx-HARQ-RTT-TimerDL-PTM* for the corresponding HARQ
process in the first symbol after the end of the corresponding
transmission carrying the DL HARQ feedback that would be performed if
HARQ feedback were enabled.

2\> stop the *drx-RetransmissionTimerDL-PTM* for the corresponding HARQ
process;

2\> stop the *drx-RetransmissionTimerDL* for the corresponding HARQ
process.

1\> if a *drx-HARQ-RTT-TimerDL-PTM* expires:

2\> if the data of the corresponding HARQ process was not successfully
decoded:

3\> start the *drx-RetransmissionTimerDL-PTM* for the corresponding HARQ
process in the first symbol after the expiry of
*drx-HARQ-RTT-TimerDL-PTM*.

1\> if a *HARQ-RTT-TimerDL-PTM-NTN* expires:

2\> if the data of the corresponding HARQ process was not successfully
decoded:

3\> start the *drx-RetransmissionTimerDL-PTM* for the corresponding HARQ
process in the first symbol after the expiry of
*HARQ-RTT-TimerDL-PTM-NTN*.

1\> if a DRX Command MAC CE indicated by PDCCH addressed to a G-RNTI or
G-CS-RNTI, or by a configured downlink multicast assignment is received:

2\> stop *drx-onDurationTimerPTM* of the DRX for this G-RNTI or
G-CS-RNTI, or the corresponding G-CS-RNTI;

2\> stop *drx-InactivityTimerPTM* of the DRX for this G-RNTI or
G-CS-RNTI, or the corresponding G-CS-RNTI.

1\> if \[(SFN × 10) + subframe number\] modulo (*drx-LongCycle-PTM*) =
*drx-StartOffset-PTM*:

2\> start *drx-onDurationTimerPTM* after *drx-SlotOffsetPTM* from the
beginning of the subframe.

1\> if the MAC entity is in Active Time for this G-RNTI or G-CS-RNTI:

2\> monitor the PDCCH for this G-RNTI or G-CS-RNTI as specified in TS
38.213 \[6\];

2\> if the PDCCH indicates a DL multicast transmission:

3\> if HARQ feedback for MBS multicast is enabled:

4\> if the PDCCH is indicated on a non-terrestrial network and the UE
supports *harq-RTT-TimerDL-ForNTN-MulticastMBS-r17*:

5\> set *HARQ-RTT-TimerDL-PTM-NTN* for the corresponding HARQ process
equal to *drx-HARQ-RTT-TimerDL-PTM* plus the latest available UE-gNB RTT
value;

5\> start the *HARQ-RTT-TimerDL-PTM-NTN* for the corresponding HARQ
process in the first symbol after the end of the corresponding
transmission carrying the DL HARQ feedback.

4\> else:

5\> start the *drx-HARQ-RTT-TimerDL-PTM* for the corresponding HARQ
process in the first symbol after the end of the corresponding
transmission carrying the DL HARQ feedback;

4\> if the first HARQ-ACK reporting mode (i.e. ack-nack) is used as
specified in TS 38.213 \[6\]:

5\> if the PDCCH addressed to G-RNTI indicates a DL multicast
transmission; or

5\> if the PDCCH addressed to G-CS-RNTI indicates a DL multicast
transmission and CS-RNTI is configured:

6\> if the PDCCH is indicated on a non-terrestrial network and the UE
supports *harq-RTT-TimerDL-ForNTN-MulticastMBS-r17*:

7\> set *HARQ-RTT-TimerDL-NTN* for the corresponding HARQ process equal
to *drx-HARQ-RTT-TimerDL* plus the latest available UE-gNB RTT value;

7\> start the *HARQ-RTT-TimerDL-NTN* for the corresponding HARQ process
in the first symbol after the end of the corresponding transmission
carrying the DL HARQ feedback.

6\> else:

7\> start the *drx-HARQ-RTT-TimerDL* for the corresponding HARQ process
in the first symbol after the end of the corresponding transmission
carrying the DL HARQ feedback.

3\> else if *drx-HARQ-RTT-TimerDL-PTM* is configured for multicast in
RRC_INACTIVE:

4\> if the PDCCH is indicated on a non-terrestrial network and the UE
supports *ptm-RetransmissionInactive*:

5\> set *HARQ-RTT-TimerDL-PTM-NTN* for the corresponding HARQ process
equal to *drx-HARQ-RTT-TimerDL-PTM* plus the latest available UE-gNB RTT
value;

5\> start the *HARQ-RTT-TimerDL-PTM-NTN* for the corresponding HARQ
process in the first symbol after the end of the corresponding multicast
transmission.

4\> else if the UE supports *ptm-RetransmissionInactive*:

5\> start the *drx-HARQ-RTT-TimerDL-PTM* for the corresponding HARQ
process in the first symbol after the end of the corresponding multicast
transmission.

3\> else if *drx-HARQ-RTT-TimerDL-PTM* is configured:

4\> if the PDCCH is indicated on a non-terrestrial network and the UE
supports *harq-RTT-TimerDL-ForNTN-MulticastMBS-r17*:

5\> set *HARQ-RTT-TimerDL-PTM-NTN* for the corresponding HARQ process
equal to *drx-HARQ-RTT-TimerDL-PTM* plus the latest available UE-gNB RTT
value;

5\> start the *HARQ-RTT-TimerDL-PTM-NTN* for the corresponding HARQ
process in the first symbol after the end of the corresponding
transmission carrying the DL HARQ feedback that would be performed if
HARQ feedback were enabled.

4\> else:

5\> start the *drx-HARQ-RTT-TimerDL-PTM* for the corresponding HARQ
process in the first symbol after the end of the corresponding
transmission carrying the DL HARQ feedback that would be performed if
HARQ feedback were enabled.

3\> stop the *drx-RetransmissionTimerDL-PTM* for the corresponding HARQ
process;

3\> stop the *drx-RetransmissionTimerDL* for the corresponding HARQ
process.

2\> if the PDCCH indicates a new multicast transmission for this G-RNTI
or G-CS-RNTI:

3\> start or restart *drx-InactivityTimerPTM* in the first symbol after
the end of the PDCCH reception.

NOTE 1: A PDCCH indicating activation of multicast SPS is considered to
indicate a new transmission.

NOTE 2: The UE may start the *drx-HARQ-RTT-TimerDL* or
*HARQ-RTT-TimerDL-NTN* after receiving a PTM transmission only if
*ptp-Retx-Multicast* or *ptp-Retx-SPS-Multicast* was included in the
*UECapabilityInformation* message to network.

The MAC entity needs not to monitor the PDCCH for a G-RNTI or a
G-CS-RNTI if it is not a complete PDCCH occasion (e.g. the Active Time
for a G-RNTI or a G-CS-RNTI starts or ends in the middle of a PDCCH
occasion).