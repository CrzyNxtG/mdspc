### 4.2.2 MAC Entities

The MAC entity of the UE handles the following transport channels:

\- Broadcast Channel (BCH);

\- Downlink Shared Channel(s) (DL-SCH);

\- Paging Channel (PCH);

\- Uplink Shared Channel(s) (UL-SCH);

\- Random Access Channel(s) (RACH).

When the UE is configured with SCG, two MAC entities are configured to
the UE: one for the MCG and one for the SCG.

When the UE is configured with DAPS handover, two MAC entities are used
by the UE: one for the source cell (source MAC entity) and one for the
target cell (target MAC entity).

The functions of the different MAC entities in the UE operate
independently unless otherwise specified. The timers and parameters used
in each MAC entity are configured independently unless otherwise
specified. The Serving Cells, C-RNTI, radio bearers, logical channels,
upper and lower layer entities, LCGs, and HARQ entities considered by
each MAC entity refer to those mapped to that MAC entity unless
otherwise specified.

If the MAC entity is configured with one or more SCells, there are
multiple DL-SCH and there may be multiple UL-SCH as well as multiple
RACH per MAC entity; one DL-SCH, one UL-SCH, and one RACH on the SpCell,
one DL-SCH, zero or one UL-SCH and zero or one RACH for each SCell.

If the MAC entity is not configured with any SCell, there is one DL-SCH,
one UL-SCH, and one RACH per MAC entity.

If the UE is configured with LTM candidate cell(s), there may be zero or
one RACH for each LTM candidate cell, which shares the same
corresponding MAC entity with Serving Cell.

Figure 4.2.2-1 illustrates one possible structure of the MAC entity when
SCG is not configured and for each MAC entity during DAPS handover.

![](media/image3.emf)

Figure 4.2.2-1: MAC structure overview

Figure 4.2.2-2 illustrates one possible structure for the MAC entities
when MCG and SCG are configured.

![](media/image4.emf)

Figure 4.2.2-2: MAC structure overview with two MAC entities

In addition, the MAC entity of the UE handles the following transport
channel for sidelink:

\- Sidelink Shared Channel (SL-SCH);

\- Sidelink Broadcast Channel (SL-BCH).

Figure 4.2.2-3 illustrates one possible structure for the MAC entity
when sidelink is configured.

![](media/image5.emf)

Figure 4.2.2-3: MAC structure overview for sidelink