## 5.7a Discontinuous Reception (DRX) for MBS Broadcast

For MBS broadcast, the MAC entity may be configured by RRC with a DRX
functionality per G-RNTI that controls the UE\'s PDCCH monitoring
activity for the MAC entity\'s G-RNTI(s) as specified in TS 38.331
\[5\]. When in RRC_IDLE or RRC_INACTIVE or RRC_CONNECTED, if broadcast
DRX is configured for a G-RNTI, the MAC entity is allowed to monitor the
PDCCH for this G-RNTI discontinuously using the broadcast DRX operation
specified in this clause; otherwise the MAC entity monitors each PDCCH
for this G-RNTI as specified in TS 38.213 \[6\]. The broadcast DRX
operation specified in this clause is performed independently for each
G-RNTI and independently from the DRX operation specified in clauses 5.7
and 5.7b.

RRC controls broadcast DRX operation by configuring the following
parameters:

\- *drx-onDurationTimerPTM*: the duration at the beginning of a DRX
cycle;

\- *drx-SlotOffsetPTM*: the delay before starting the
*drx-onDurationTimerPTM*;

\- *drx-InactivityTimerPTM*: the duration after the PDCCH occasion in
which a PDCCH indicates a new DL broadcast transmission for the MAC
entity;

\- *drx-LongCycleStartOffsetPTM*: the long DRX cycle *drx-LongCycle-PTM*
and *drx-StartOffset-PTM* which defines the subframe where the DRX cycle
starts.

When broadcast DRX is configured for a G-RNTI, the Active Time includes
the time while:

*- drx-onDurationTimerPTM* or *drx-InactivityTimerPTM* for this G-RNTI
is running.

When broadcast DRX is configured for a G-RNTI, the MAC entity shall for
this G-RNTI:

1\> if \[(SFN × 10) + subframe number\] modulo (*drx-LongCycle-PTM*) =
*drx-StartOffset-PTM*:

2\> start *drx-onDurationTimerPTM* after *drx-SlotOffsetPTM* from the
beginning of the subframe.

1\> if the MAC entity is in Active Time for this G-RNTI:

2\> monitor the PDCCH for this G-RNTI as specified in TS 38.213 \[6\];

2\> if the PDCCH indicates a DL transmission for MBS broadcast:

3\> start or restart *drx-InactivityTimerPTM* in the first symbol after
the end of the PDCCH reception.

NOTE: If a cell is configured for MBS broadcast reception, the SFN of
this cell is used to calculate the DRX duration of MBS broadcast on this
cell.