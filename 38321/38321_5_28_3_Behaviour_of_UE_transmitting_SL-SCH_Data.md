### 5.28.3 Behaviour of UE transmitting SL-SCH Data

The UE transmitting SL-SCH Data should keep aligned with its intended UE
receiving the SL-SCH Data regarding the SL DRX Active time as specified
in clause 5.28.2.

Furthermore, the UE transmitting SL-SCH Data determines the SL DRX
Active time based on SL DRX timers that are running (e.g.,
*sl-drx-onDurationTimer*/*sl-DRX-GC-BC-OnDurationTimer*,
*sl-drx-InactivityTimer*/*sl-DRX-GC-InactivityTimer*,
*sl-drx-RetransmissionTimer*/*sl-DRX-GC-RetransmissionTimer*) or will be
running in the future (e.g.,
*sl-drx-onDurationTimer*/*sl-DRX-GC-BC-OnDurationTimer*,
*sl-drx-InactivityTimer*/*sl-DRX-GC-InactivityTimer*,
*sl-drx-RetransmissionTimer*/*sl-DRX-GC-RetransmissionTimer*) at the
UE(s) receiving SL-SCH data. The UE may select resource for the initial
transmission of groupcast within the time when
*sl-DRX-GC-BC-OnDurationTimer* or *sl-DRX-GC-InactivityTimer* of the
destination is running.

NOTE 1: A UE may assume that a resource for retransmission is in the
Active time if an initial transmission causes the
*sl-drx-RetransmissionTimer*/*sl-DRX-GC-RetransmissionTimer* to be
started at the receiving UE.

NOTE 2: A UE may send SL DRX Command MAC CE to receiving UE for unicast
and when to send SL DRX Command MAC CE is up to UE implementation.

The MAC entity shall for each Destination Layer-2 ID associated with
groupcast that is interested in NR sidelink transmision:

1\> if the SCI indicates a new transmission where the cast type is set
to groupcast is transmitted:

2\> start or restart *sl-DRX-GC-InactivityTimer* for the corresponding
Destination Layer-2 ID in the first slot after SCI transmission.

The MAC entity shall for each pair of the Source Layer-2 ID and the
Destination Layer-2 ID corresponding to each PC5-RRC connection which
has been established by upper layers:

1\> if the SL DRX Command indication has been triggered by the UE:

2\> if the MAC entity has SL resources allocated for new transmission
and the SL-SCH resources can accommodate the SL DRX Command MAC CE and
its subheader as a result of logical channel prioritization:

3\> instruct the Multiplexing and Assembly procedure to generate a
Sidelink DRX Command MAC CE as defined in clause 6.1.3.52;

3\> cancel the triggered SL DRX Command indication.

2\> else if the MAC entity has been configured with Sidelink resource
allocation mode 1:

3\> trigger a Scheduling Request.