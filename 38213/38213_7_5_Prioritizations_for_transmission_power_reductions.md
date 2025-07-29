## 7.5 Prioritizations for transmission power reductions

For single cell operation with two uplink carriers or for operation with
carrier aggregation or for operation with a candidate cell configured by
*LTM-Config* or for operation with a single cell configured with
*sTx-2Panel*, if a total UE transmit power for PUSCH or PUCCH or PRACH
or SRS transmissions on serving cell(s) or on a candidate cell, if any,
in a frequency range in a respective transmission occasion $i$ would
exceed ${\widehat{P}}_{CMAX}(i)$, where ${\widehat{P}}_{CMAX}(i)$ is the
linear value of $P_{CMAX}(i)$ in transmission occasion $i$ as defined in
\[8-1, TS 38.101-1\] for FR1 and \[8-2, TS 38.101-2\] for FR2, the UE
allocates power to PUSCH/PUCCH/PRACH/SRS transmissions according to the
following priority order (in descending order) so that the total UE
transmit power for transmissions on serving cell(s) or on a candidate
cell, if any, in the frequency range is smaller than or equal to
${\widehat{P}}_{CMAX}(i)$ for that frequency range in every symbol of
transmission occasion $i$. If the UE transmits SRS on multiple SRS
resources according to Clause 6.2.1.4 of \[6, TS 38.214\], the UE
allocates power so that all REs of the SRS transmission have same power.

For the purpose of power allocation in this clause, if a UE is provided
*uci-MuxWithDiffPrio* and the UE multiplexes HARQ-ACK information in a
PUSCH, a priority index of the PUSCH is the larger of (a) the priority
index of the PUSCH according to clause 9 and (b) the larger priority
index of the HARQ-ACK information. When determining a total transmit
power for serving cells or a candidate cell, if any, as described in
Clause 21 in a frequency range in a symbol of transmission occasion $i$,
the UE does not include power for transmissions starting after the
symbol of transmission occasion $i$. The total UE transmit power in a
symbol of a slot is defined as the sum of the linear values of UE
transmit powers for PUSCH, PUCCH, PRACH, and SRS in the symbol of the
slot.

\- PRACH transmission on a candidate cell, if any, as described in
Clause 21

\- PRACH transmission on the PCell

\- PUCCH or PUSCH transmissions with larger priority index

\- For PUCCH or PUSCH transmissions with same priority index

\- PUCCH transmission with HARQ-ACK information, and/or SR, and/or LRR,
or PUSCH transmission with HARQ-ACK information of the priority index

\- PUCCH transmission with CSI or PUSCH transmission with CSI

\- PUSCH transmission without HARQ-ACK information of the priority index
or CSI and, for Type-2 random access procedure, PUSCH transmission on
the PCell

\- If the UE is configured with prioSCellPRACH-OverSP-PeriodicSRS-r17

\- Aperiodic SRS transmission or PRACH transmission on a serving cell
other than the PCell

\- Semi-persistent and/or periodic SRS transmission

\- otherwise,

\- SRS transmission, with aperiodic SRS having higher priority than
semi-persistent and/or periodic SRS, or PRACH transmission on a serving
cell other than the PCell

In case of same priority order and for operation with carrier
aggregation, the UE prioritizes power allocation for transmissions on
the primary cell of the MCG or the SCG over transmissions on a secondary
cell. In case of same priority order and for operation with two UL
carriers, the UE prioritizes power allocation for transmissions on the
carrier where the UE is configured to transmit PUCCH. If PUCCH is not
configured for any of the two UL carriers, the UE prioritizes power
allocation for transmissions on the non-supplementary UL carrier.