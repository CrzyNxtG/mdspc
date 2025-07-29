# 9 UE procedure for reporting control information

If a UE is configured with a SCG, the UE shall apply the procedures
described in this clause for both MCG and SCG.

\- When the procedures are applied for MCG, the terms \'secondary
cell\', \'secondary cells\', \'serving cell\', \'serving cells\' in this
clause refer to secondary cell, secondary cells, serving cell, serving
cells belonging to the MCG respectively.

\- When the procedures are applied for SCG, the terms \'secondary
cell\', \'secondary cells\', \'serving cell\', \'serving cells\' in this
clause refer to secondary cell, secondary cells (not including PSCell),
serving cell, serving cells belonging to the SCG respectively. The term
\'primary cell\' in this clause refers to the PSCell of the SCG.

If a UE is configured with a PUCCH-SCell, the UE shall apply the
procedures described in this clause for both primary PUCCH group and
secondary PUCCH group

\- When the procedures are applied for the primary PUCCH group, the
terms \'secondary cell\', \'secondary cells\', \'serving cell\',
\'serving cells\' in this clause refer to secondary cell, secondary
cells, serving cell, serving cells belonging to the primary PUCCH group
respectively.

\- When the procedures are applied for secondary PUCCH group, the terms
\'secondary cell\', \'secondary cells\', \'serving cell\', \'serving
cells\' in this clause refer to secondary cell, secondary cells (not
including the PUCCH-SCell), serving cell, serving cells belonging to the
secondary PUCCH group respectively. The term \'primary cell\' in this
clause refers to the PUCCH-SCell of the secondary PUCCH group. If
*pdsch-HARQ-ACK-Codebook-secondaryPUCCHgroup-r16* is provided,
*pdsch-HARQ-ACK-Codebook* is replaced by
*pdsch-HARQ-ACK-Codebook-secondaryPUCCHgroup-r16*. If
*harq-ACK-SpatialBundlingPUCCH-secondaryPUCCHgroup* is provided,
*harq-ACK-SpatialBundlingPUCCH* is replaced by
*harq-ACK-SpatialBundlingPUCCH-secondaryPUCCHgroup*. If
*harq-ACK-SpatialBundlingPUSCH-secondaryPUCCHgroup* is provided,
*harq-ACK-SpatialBundlingPUSCH* is replaced by
*harq-ACK-SpatialBundlingPUSCH-secondaryPUCCHgroup*. If
*uci-MuxWithDiffPrioSecondaryPUCCHgroup* is provided,
*uci-MuxWithDiffPrio* is replaced by
*uci-MuxWithDiffPrioSecondaryPUCCHgroup*. If
*simultaneousPUCCH-PUSCH-secondaryPUCCHgroup* is provided,
*simultaneousPUCCH-PUSCH* is replaced by
*simultaneousPUCCH-PUSCH-SecondaryPUCCHgroup*. If
*simultaneousPUCCH-PUSCH-SamePriority-secondaryPUCCHgroup* is provided,
*simultaneousPUCCH-PUSCH-SamePriority* is replaced by
*simultaneousPUCCH-PUSCH- SamePriority-SecondaryPUCCHgroup*. If
*pucch-sSCellSecondaryPUCCHgroup* is provided, *pucch-sSCell* is
replaced by *pucch-sSCellSecondaryPUCCHgroup*. If
*pucch-sSCellPatternSecondaryPUCCHgroup* is provided,
*pucch-sSCellPattern* is replaced by
*pucch-sSCellPatternSecondaryPUCCHgroup*. If
*pucch-sSCellDynSecondaryPUCCHgroup* is provided, *pucch-sSCellDyn* is
replaced by *pucch-sSCellDynSecondaryPUCCHgroup*. If
*pdsch-HARQ-ACK-EnhType3SecondaryToAddModList* is provided,
*pdsch-HARQ-ACK-EnhType3ToAddModList* is replaced by
*pdsch-HARQ-ACK-EnhType3SecondaryToAddModList*. If
*pdsch-HARQ-ACK-RetxSecondaryPUCCHgroup* is provided,
*pdsch-HARQ-ACK-Retx* is replaced by
*pdsch-HARQ-ACK-RetxSecondaryPUCCHgroup*.

If a UE is provided *MC-DCI-SetofCells* for scheduling by a DCI format
PDSCH receptions or PUSCH transmissions on serving cells from a set of
more than one serving cells, the UE expects the more than one serving
cells to be in a same PUCCH group. The UE provides HARQ-ACK information
in a same HARQ-ACK codebook for sets of serving cells that are
associated with a same PUCCH group. The UE does not expect to be
configured to receive multicast PDSCH on serving cells of the same PUCCH
group as serving cells from the sets of serving cells.

For unpaired spectrum operation, if a UE is provided a PUCCH-sSCell as
described in clause 9.A, the UE shall apply the procedures described in
this clause for both the primary cell and the PUCCH-sSCell.

If a UE is provided *pdsch-HARQ-ACK-CodebookList-r16*,
*pdsch-HARQ-ACK-Codebook* is replaced by the relevant entry in
*pdsch-HARQ-ACK-CodebookList-r16*.

In the remaining of this clause, when a PDCCH reception by a UE includes
two PDCCH candidates from corresponding search space sets, as described
in clause 10.1

\- a PDCCH monitoring occasion is the union of the PDCCH monitoring
occasions for the two PDCCH candidates

\- the start of the PDCCH reception is the start of the earlier PDCCH
candidate

\- the end of the PDCCH reception is the end of the PDCCH candidate that
ends later

The PDCCH reception includes the two PDCCH candidates also when the UE
is not required to monitor one of the two PDCCH candidates as described
in clauses 10 (except clause 10.4), 11.1, 11.1.1 and 17.2.

In the remaining of this clause, a last DCI format is from a set of
detected DCI formats for which the UE would provide HARQ-ACK information
in a PUCCH in a same slot. Detected DCI formats are first indexed in
ascending order across indexes of respective scheduled cells for a same
PDCCH monitoring occasion, and are then indexed in ascending order
across indexes of PDCCH monitoring occasions. For indexing a detected
DCI format associated with two or more scheduled cells, a respective
scheduled cell is the one with the smallest index among the two or more
scheduled cells. For a PDCCH monitoring occasion and a scheduled cell,
if a UE is not provided *coresetPoolIndex* or is provided
*coresetPoolIndex* with value 0 for one or more first CORESETs and is
provided *coresetPoolIndex* with value 1 for one or more second CORESETs
on an active DL BWP of a serving cell, and is provided
*ackNackFeedbackMode* = *joint* for the active UL BWP, detected DCI
formats from PDCCH receptions in the first CORESETs are indexed prior to
detected DCI formats from PDCCH receptions in the second CORESETs.

For the purpose of determining timeline conditions in this clause,

\- if a UE would transmit a PUCCH with HARQ-ACK information in response
to a first SPS PDSCH reception after an activation of SPS PDSCH
receptions, the PUCCH is considered as a PUCCH transmission in response
to a DCI format detection;

\- if a UE would transmit a configured grant Type 2 PUSCH in the first
transmission occasion after an activation of configured grant Type 2
PUSCH transmissions, the PUSCH is considered as a PUSCH transmission in
response to a DCI format detection.

If a UE

\- is not provided *coresetPoolIndex* or is provided *coresetPoolIndex*
with a value of 0 for first CORESETs on active DL BWPs of serving cells,
and

\- is provided *coresetPoolIndex* with a value of 1 for second CORESETs
on active DL BWPs of the serving cells, and

\- is provided *ackNackFeedbackMode* = *separate*

the UE shall separately apply the procedures described in clauses 9.1
and 9.2.3 for reporting HARQ-ACK information associated with the first
CORESETs on active DL BWP of the serving cells and for reporting
HARQ-ACK information associated with the second CORESETs on active DL
BWP of the serving cells, and the UE does not expect to be provided with
*subslotLengthForPUCCH* or to be indicated by
*pdsch-HARQ-ACK-CodebookList* to generate two HARQ-ACK codebooks on
active DL BWP of the serving cells. HARQ-ACK information reporting is
associated with a CORESET through a reception of a PDCCH with a DCI
format triggering the reporting of the HARQ-ACK information by the UE.

For NR-DC when both the MCG and the SCG operate either in FR1 or in FR2
and for a power headroom report transmitted on the MCG or the SCG, the
UE computes *PH* assuming that the UE does not transmit PUSCH/PUCCH on
any serving cell of the SCG or the MCG, respectively.

If a UE is configured for NR-DC operation, the UE does not expect to be
configured with a PUCCH-SCell.

A PUSCH or a PUCCH transmission other than PUCCH transmissions with SL
HARQ-ACK reports, including repetitions if any, can be of priority index
0 or of priority index 1. For a configured grant PUSCH transmission, a
UE determines a priority index from *phy-PriorityIndex*, if provided.
For a PUCCH transmission with HARQ-ACK information corresponding to a
SPS PDSCH reception or a SPS PDSCH release, a UE determines a priority
index from *harq-CodebookID*, if provided. For a PUCCH transmission with
SR, a UE determines the corresponding priority as described in clause
9.2.4. For a PUSCH transmission with semi-persistent CSI report, a UE
determines a priority index from a priority indicator field, if
provided, in a DCI format that activates the semi-persistent CSI report.
If a priority index is not provided to a UE for a PUSCH or a PUCCH
transmission other than PUCCH transmissions with SL HARQ-ACK reports,
the priority index is 0.

If a UE is provided one *PUCCH-Config*

\- if the UE is provided *subslotLengthForPUCCH* in the *PUCCH-Config*,
the PUCCH resource for any SR configuration with priority index 0 or any
CSI report configuration in the *PUCCH-Config* is within the
*subslotLengthForPUCCH* symbols in the *PUCCH-Config*

If a UE is provided two *PUCCH-Config*

\- if the UE is provided *subslotLengthForPUCCH* in the first
*PUCCH-Config*, the PUCCH resource for any SR configuration with
priority index 0 or any CSI report configuration in any *PUCCH-Config*
is within the *subslotLengthForPUCCH* symbols in the first
*PUCCH-Config*

\- if the UE is provided *subslotLengthForPUCCH* in the second
*PUCCH-Config*, the PUCCH resource for any SR configuration with
priority index 1 in any *PUCCH-Config* is within the
*subslotLengthForPUCCH* symbols in the second *PUCCH-Config*

If a UE is provided *subslotLengthForPUCCH* in a *PUCCH-Config* of a
given priority index, in a slot of $N_{\text{sym}}^{\text{slot}}$
symbols \[4, TS 38.211\] with HARQ-ACK, the UE does not expect that
HARQ-ACK information in response to SPS PDSCH reception(s) only (if any)
or SR (if any) of the given priority index in a slot of
*subslotLengthForPUCCH* symbols is moved to a different slot of
*subslotLengthForPUCCH* symbols after multiplexing overlapping PUCCHs.

If in an active DL BWP a UE monitors PDCCH for detection of DCI format
that includes a priority indicator field, a priority index can be
provided by the priority indicator field. If a UE indicates a capability
to monitor, in an active DL BWP, PDCCH for detection of DCI format that
includes a priority indicator field, the DCI format can schedule PUSCH
transmissions of any priority, or PDSCH receptions and/or trigger a
PUCCH transmission with corresponding HARQ-ACK information of any
priority, and DCI format 1_1 or DCI format 1_2 with a Transmission
Configuration Indication field can indicate a TCI state update and
trigger a PUCCH transmission with corresponding HARQ-ACK information of
any priority.

A DCI format indicating a SPS PDSCH release, or SCell dormancy without
scheduling a PDSCH reception, or indicating a TCI state update without
scheduling PDSCH reception, is referred to as a DCI format having
associated HARQ-ACK information without scheduling a PDSCH reception.

For the remaining of this clause, when a UE

\- is not provided *coresetPoolIndex* or is provided *coresetPoolIndex*
with a value of 0 for first CORESETs, and is provided *coresetPoolIndex*
with a value of 1 for second CORESETs, on active DL BWPs of serving
cells, and

\- is provided *sTx-2Panel*

the UE separately determines and resolves time overlapping among first
PUSCH transmissions that use respective first spatial domain filters
corresponding to first *TCI-State* or *TCI-UL-State* associated with the
first CORESETs, and among second PUSCH transmissions that use respective
second spatial domain filters corresponding to second *TCI-State* or
*TCI-UL-State* associated with the second CORESETs.

When a UE determines overlapping for PUCCH transmissions with SL
HARQ-ACK reports and PUCCH of larger and/or smaller priority index, the
UE resolves the overlapping for PUCCH transmissions with SL HARQ-ACK
reports and PUCCH of each priority index as described in clause 9.2.5
and 9.2.6 before resolving the overlapping for PUCCH transmissions
without SL HARQ-ACK or the overlapping for PUCCH transmissions and PUSCH
transmissions.

When a UE determines overlapping for PUCCH and/or PUSCH transmissions of
the same priority index other than PUCCH transmissions with SL HARQ-ACK
reports before considering limitations for UE transmission due to cell
DRX operation \[11, TS 38.321\] or as described in clauses 11.1, 11.1.1,
11.2A, 15 and 17.2 including repetitions if any,

\- first, the UE resolves the overlapping for PUCCHs with repetitions as
described in clause 9.2.6, if any

\- second, the UE resolves the overlapping for PUCCHs without
repetitions as described in clauses 9.2.5

\- third, the UE resolves the overlapping for PUSCHs and PUCCHs with
repetitions as described in clause 9.2.6

\- fourth, the UE resolves the overlapping for PUSCHs and PUCCHs without
repetitions as is subsequently described in this clause.

After resolving the overlapping for PUCCH and/or PUSCH transmissions,
and if cell DRX is activated for a serving cell and a PUCCH or PUSCH
transmission would overlap with the non-active period of cell DRX of the
serving cell, the UE does not transmit the PUCCH if HARQ-ACK information
is not multiplexed in the PUCCH, or does not transmit the PUSCH if
HARQ-ACK information is not multiplexed in the PUSCH and the PUSCH is
not associated with a corresponding PDCCH, respectively.

If a UE

\- is provided *simultaneousPUCCH-PUSCH* and would transmit a PUCCH with
a first priority index and PUSCHs with a second priority index that is
different than the first priority index, where the PUCCH and the PUSCHs
overlap in time on different respective cells

\- can simultaneously transmit the PUCCH and the PUSCHs with different
priority indexes \[18, TS 38.306\],

the UE excludes the PUSCHs for resolving the time overlapping between
the PUCCH and PUSCHs with different priority indexes, where the timeline
conditions for resolving the overlapping PUCCH and PUSCHs are not
required for the excluded PUSCHs.

If a UE

\- is provided *simultaneousPUCCH-PUSCH-SamePriority* and would transmit
a PUCCH and PUSCHs with same priority index, where the PUCCH and the
PUSCHs overlap in time on different respective cells,

\- can simultaneously transmit the PUCCH and the PUSCHs with same
priority index \[18, TS 38.306\],

the UE excludes the PUSCHs for resolving the time overlapping between
the PUCCH and PUSCHs with same priority index, where the timeline
conditions for resolving the overlapping PUCCH and PUSCHs are not
required for the excluded PUSCHs.

When a UE determines overlapping for PUCCH and/or PUSCH transmissions of
different priority indexes, other than PUCCH transmissions with SL
HARQ-ACK reports, before considering limitations for transmission due to
cell DRX operation or as described in clauses 11.1, 11.1.1, 11.2A, 15
and 17.2 including repetitions if any, if the UE is provided
*uci-MuxWithDiffPrio* and the timeline conditions in clause 9.2.5 for
multiplexing UCI in a PUCCH or a PUSCH are satisfied

\- first, the UE resolves overlapping for PUCCH and/or PUSCH
transmissions of a same priority index as described in clauses 9.2.5 and
9.2.6

\- second, the UE resolves the overlapping for PUCCH transmissions of
different priority indexes, and

\- if the UE is provided *subslotLengthForPUCCH* in the second
*PUCCH-Config*, a PUCCH transmission of smaller priority index is
associated with the first overlapping slot with *subslotLengthForPUCCH*
symbols of larger priority index; otherwise, the PUCCH transmission of
smaller priority index is associated with the overlapping slot with
$N_{\text{sym}}^{\text{slot}}$ symbols \[4, TS 38.211\] of larger
priority index.

\- the UE first resolves the overlapping for PUCCH transmissions, where
at least one of the PUCCH transmissions is with
$N_{\text{PUCCH}}^{\text{repeat}} > 1$ repetitions, within a slot of
larger priority index as is subsequently described in this clause, if
any, and then the UE resolves the overlapping for PUCCH transmissions
without repetitions within the slot using the pseudo-code in clause
9.2.5

\- if the UE determines that a first PUCCH transmission of the smaller
priority index is not dropped and the UCI of the first PUCCH
transmission is not multiplexed in a second PUCCH transmission of larger
priority index in an overlapping slot with *subslotLengthForPUCCH*
symbols, the first PUCCH transmission is associated with the next
overlapping slot with *subslotLengthForPUCCH* symbols for PUCCH
transmissions with the larger priority index

\- the UE does not expect a PUCCH transmission that includes UCI of
different priority indexes to overlap with a PUCCH transmission with
$N_{\text{PUCCH}}^{\text{repeat}} > 1$ repetitions after resolving the
overlapping for PUCCH transmissions without repetitions within a slot

\- the UE does not expect a PUCCH transmission with UCI of first and
second priority indexes to overlap with a PUCCH transmission with
HARQ-ACK information of the first priority index, or with a PUCCH
transmission or with a PUSCH transmission of the second priority index
when the second priority index is larger than the first priority index

\- the UE does not expect a PUCCH transmission with HARQ-ACK information
of larger priority index to overlap with more than one PUCCH
transmissions with HARQ-ACK information of smaller priority index

\- third, the UE resolves the overlapping for PUCCH and PUSCH
transmissions of different priority indexes

\- the UE drops PUSCH transmissions of smaller priority index that
overlap with a PUCCH transmission with positive SR of larger priority
index prior to multiplexing UCI in a PUSCH transmission of smaller
priority index, if any

\- the UE drops PUSCH transmissions of smaller priority index that
overlap with a PUCCH transmission with
$N_{\text{PUCCH}}^{\text{repeat}} > 1$ repetitions of larger priority
index prior to multiplexing UCI in a PUSCH transmission of smaller
priority index, if any

\- the UE multiplexes HARQ-ACK information in a PUSCH transmission, as
is subsequently described in this clause for multiplexing HARQ-ACK
information from a PUCCH transmission in a PUSCH transmission of a same
priority index, if a PUCCH transmission with HARQ-ACK information of a
first priority index overlaps with one or more PUSCH transmissions of a
second priority index that is different than the first priority index

\- if // this is for cases the UE supports multiplexing information of
different priorities in a PUCCH/PUSCH transmission

\- a PUCCH transmission with HARQ-ACK information, without repetitions,
with smaller priority index overlaps with a PUCCH transmission only with
HARQ-ACK information, without repetitions, with larger priority index,
or

\- a PUCCH transmission without repetitions that includes HARQ-ACK
information of smaller priority index overlaps with a PUCCH transmission
without repetitions using a PUCCH resource with PUCCH format 2/3/4 with
HARQ-ACK information and SR of larger priority index, or

\- a PUCCH transmission with HARQ-ACK information, without repetitions,
with smaller or larger priority index overlaps, respectively, with a
PUSCH transmission with larger or smaller priority index

the UE

\- multiplexes HARQ-ACK information of different priority indexes and SR
information of larger priority index, if any, in a same PUCCH
transmission of larger priority index, or multiplexes HARQ-ACK
information the UE would provide in a PUCCH transmission of smaller or
larger priority index in a PUSCH transmission of larger or smaller
priority index, respectively, and applies the procedures in clause
9.2.5.3 or 9.3, respectively, and

\- drops CSI and/or SR carried in the PUCCH transmission of smaller
priority index, if any

\- drops negative SR carried in the PUCCH transmission of larger
priority index, if any, if the UE would multiplex the HARQ-ACK
information of larger priority index in a PUSCH transmission of smaller
priority index

\- drops HARQ-ACK information of smaller priority index if the UE would
multiplex the HARQ-ACK information of smaller priority index in a PUSCH
transmission where the UE multiplexes Part 1 CSI reports and Part 2 CSI
reports of larger priority index

\- drops Part 2 CSI reports of smaller priority index if the UE would
multiplex the HARQ-ACK information of smaller and larger priority
indexes in a PUSCH transmission where the UE multiplexes Part 1 CSI
reports and Part 2 CSI reports of smaller priority index

\- drops HARQ-ACK information of smaller priority index if the UE would
multiplex the HARQ-ACK information of smaller priority index in a PUCCH
transmission of larger priority index using a PUCCH resource provided by
*n1PUCCH-AN*

\- drops Part 2 CSI reports of smaller priority index if the UE would
multiplex the HARQ-ACK information of larger priority index in a PUSCH
transmission where the UE multiplexes CG-UCI, or UTO-UCI, Part 1 CSI
reports and Part 2 CSI reports of smaller priority index

\- else

\- if the UE would transmit the following channels that would overlap in
time where, if a channel transmission is with repetitions, the following
are applicable per repetition

\- a first PUCCH transmission of larger priority index and a second
PUCCH transmission of smaller priority index

\- a first PUCCH transmission of larger priority index and a second
PUSCH transmission of smaller priority index when the UE cannot
simultaneously transmit the first PUCCH and second PUSCH

\- a first PUCCH transmission of smaller priority index and a second
PUSCH transmission of larger priority index when the UE cannot
simultaneously transmit the first PUCCH and second PUSCH

the UE

\- transmits the PUCCH or the PUSCH of the larger priority index subject
to the limitations for UE transmissions due to cell DRX operation or as
described in clauses 11.1, 11.1.1, 11.2A, and 15 and

\- does not transmit a PUCCH or a PUSCH of smaller priority index

When a UE determines overlapping for PUCCH and/or PUSCH transmissions of
different priority indexes, other than PUCCH transmissions with SL
HARQ-ACK reports, before considering limitations for transmissions
including with repetitions, if any, due to cell DRX operation or as
described in clauses 11.1, 11.1.1, 11.2A, 15 and 17.2, if the UE is not
provided *uci-MuxWithDiffPrio*, the UE first resolves overlapping for
PUCCH and/or PUSCH transmissions of smaller priority index as described
in clauses 9.2.5 and 9.2.6. Then,

\- if a transmission of a first PUCCH of larger priority index scheduled
by a DCI format in a PDCCH reception would overlap in time with a
repetition of a transmission of a second PUSCH or a second PUCCH of
smaller priority index, the UE cancels the repetition of a transmission
of the second PUSCH or the second PUCCH before the first symbol that
would overlap with the first PUCCH transmission

\- if a transmission of a first PUSCH of larger priority index scheduled
by a DCI format in a PDCCH reception would overlap in time with a
repetition of the transmission of a second PUCCH of smaller priority
index, the UE cancels the repetition of the transmission of the second
PUCCH before the first symbol that would overlap with the first PUSCH
transmission

where

\- the overlapping is applicable before or after resolving overlapping
among channels of larger priority index, if any, as described in clauses
9.2.5 and 9.2.6

\- any remaining PUCCH and/or PUSCH transmission after overlapping
resolution is subjected to the limitations for UE transmission due to
cell DRX operation or as described in clauses 11.1, 11.1.1, 11.2A, 15
and 17.2

\- the UE expects that the transmission of the first PUCCH or the first
PUSCH, respectively, would not start before $T_{proc,2}$ after a last
symbol of the corresponding PDCCH reception

\- $T_{proc,2}\ $is the PUSCH preparation time for a corresponding UE
processing capability assuming $d_{2,1} = \ d_{1}$ \[6, TS 38.214\],
based on $\mu$ and $N_{2}$ as subsequently defined in this clause, and
$d_{1}$ is determined by a reported UE capability

If a UE is scheduled by a DCI format in a first PDCCH reception to
transmit a first PUCCH or a first PUSCH of larger priority index that
overlaps with a second PUCCH or a second PUSCH transmission of smaller
priority index that, if any, is scheduled by a DCI format in a second
PDCCH

\- $T_{proc,2}$ is based on a value of $\mu$ corresponding to the
smallest SCS configuration of the first PDCCH, the second PDCCHs, the
first PUCCH or the first PUSCH, and the second PUCCHs or the second
PUSCHs

\- if the overlapping group includes the first PUCCH

\- if *processingType2Enabled* of *PDSCH-ServingCellConfig* is set to
*enable* for the serving cell where the UE receives the first PDCCH and
for all serving cells where the UE receives the PDSCHs corresponding to
the second PUCCHs, and if *processingType2Enabled* of
*PUSCH-ServingCellConfig* is set to *enable* for the serving cells with
the second PUSCHs, $N_{2}\ $is 5 for $\mu = 0$, 5.5 for $\mu = 1$ and 11
for $\mu = 2$

\- else, $N_{2}\ $is 10 for $\mu = 0$*,* 12 for $\mu = 1$, 23 for
$\mu = 2$, 36 for $\mu = 3$, 144 for $\mu = 5$, and 288 for $\mu = 6$;

\- if the overlapping group includes the first PUSCH

\- if *processingType2Enabled* of *PUSCH-ServingCellConfig* is set to
*enable* for the serving cells with the first PUSCH and the second
PUSCHs and if *processingType2Enabled* of *PDSCH-ServingCellConfig* is
set to *enable* for all serving cells where the UE receives the PDSCHs
corresponding to the second PUCCHs, $N_{2}\ $is 5 for $\mu = 0$, 5.5 for
$\mu = 1$ and 11 for $\mu = 2$

\- else, $N_{2}\ $is 10 for $\mu = 0$*,* 12 for $\mu = 1$, 23 for
$\mu = 2$, 36 for $\mu = 3$, 144 for $\mu = 5$, and 288 for $\mu = 6$;

If a PUSCH of larger priority index scheduled by a DCI format overlaps
in time with a PUSCH of smaller priority index with SP-CSI report(s)
without a corresponding PDCCH in one or more symbols on the same
carrier, and if the earliest symbol of these PUSCH channels starts no
earlier than N~2~+d~2,1~ symbols after the last symbol of the DCI
scheduling the PUSCH of larger priority index where d~2,1~ is the
maximum of the d~2,1~ associated with PUSCH of larger priority index
scheduled by a DCI format and the PUSCH of smaller priority index with
SP-CSI report(s) without a corresponding PDCCH, the PUSCH of smaller
priority index with SP-CSI report(s) shall not be transmitted by the UE.
Otherwise, if the timeline requirement is not satisfied this is an error
case.

If a UE would transmit the following channels, including repetitions if
any, that would overlap in time

\- a first PUCCH of larger priority index with SR and a second PUCCH or
PUSCH of smaller priority index, or

\- a configured grant PUSCH of larger priority index and a PUCCH of
smaller priority index, or

\- a first PUCCH of larger priority index with HARQ-ACK information only
in response to PDSCH(s) reception without corresponding PDCCH(s) and a
second PUCCH of smaller priority index with HARQ-ACK information only in
response to PDSCH(s) reception without corresponding PDCCH(s), or a
second PUCCH of smaller priority index with SR and/or CSI, or a
configured grant PUSCH with smaller priority index, or a PUSCH of
smaller priority index with SP-CSI report(s) without a corresponding
PDCCH, or

\- a PUSCH of larger priority index with SP-CSI report(s) without a
corresponding PDCCH and a PUCCH of smaller priority index with SR, or
CSI, or HARQ-ACK information only in response to PDSCH(s) reception
without corresponding PDCCH(s), or

\- a configured grant PUSCH of larger priority index and a configured
grant PUSCH of smaller priority index or a PUSCH of smaller priority
index with SP-CSI report(s) without a corresponding PDCCH on a same
serving cell

\- a PUSCH of larger priority index with SP-CSI report(s) without a
corresponding PDCCH and a configured grant PUSCH of smaller priority
index or a PUSCH of smaller priority index with SP-CSI report(s) without
a corresponding PDCCH on a same serving cell

\- a PUSCH of smaller priority index scheduled by a DCI format and a
configured grant PUSCH of larger priority index on a same serving cell
if the UE is provided *prioLowDG-HighCG*

\- a PUSCH of larger priority index scheduled by a DCI format and a
configured grant PUSCH of smaller priority index on a same serving cell
if the UE is provided *prioHighDG-LowCG*

the UE is expected to cancel a repetition of the PUCCH/PUSCH
transmissions of smaller priority index before the first symbol
overlapping with the PUCCH/PUSCH transmission of larger priority index
if the repetition of the PUCCH/PUSCH transmissions of smaller priority
index overlaps in time with the PUCCH/PUSCH transmissions of larger
priority index. In case of a PUSCH of larger priority index scheduled by
a DCI format in a PDCCH reception and a configured grant PUSCH of
smaller priority index on a same serving cell and the UE is provided
*prioHighDG-LowCG*

\- the UE expects that the transmission of the PUSCH of larger priority
index would not start before $T_{proc,2}$ after a last symbol of the
corresponding PDCCH reception

\- $T_{proc,2}\ $is the PUSCH preparation time for a corresponding UE
processing capability assuming $d_{2,1} = \ d_{1} + d_{3}$ \[6, TS
38.214\], based on $\mu$ and $N_{2}$ as subsequently defined in this
clause, and $d_{1}$ and $d_{3}$ are determined by a reported UE
capability

When a UE determines overlapping for PUCCH transmissions with SL
HARQ-ACK reports and PUSCH of smaller priority index, including
repetitions if any, after resolving the overlapping PUCCH other than
PUCCH transmissions with SL HARQ-ACK reports and/or PUSCH transmissions,
if the PUSCH includes no UCI, the UE resolves the overlapping for PUCCH
transmissions with SL HARQ-ACK reports and PUSCH of smaller priority
index as described in clauses 9.2.5 and 9.2.6.

When a UE determines overlapping for PUCCH transmissions with SL
HARQ-ACK reports and PUSCH of larger priority index only, including
repetitions if any, after resolving the overlapping PUCCH other than
PUCCH transmissions with SL HARQ-ACK reports and/or PUSCH transmissions,
the UE does not transmit the PUCCH with SL HARQ-ACK reports

where

> \- the UE expects that the transmission of the PUSCH would not start
> before $T_{proc,2} + d_{1}$ after a last symbol of the corresponding
> PDCCH reception;
>
> \- $T_{proc,2}\ $is the PUSCH preparation time for a corresponding UE
> processing capability assuming $d_{2,1} = 0$ \[6, TS 38.214\], based
> on $\mu$ and $N_{2}$ as subsequently defined in this clause, and
> $d_{1}$ is determined by a reported UE capability.

The UE expects the PUCCH and PUSCH transmissions to fulfill the
conditions in clause 9 and clause 9.2.5 for UCI multiplexing replacing
the reference time of \"end of PDSCH\" with \"end of the last symbol of
a last PSFCH reception occasion\" as described in 16.5 and *T~proc,~*~1~
with *T~prep~*.

A UE does not expect that a PUCCH carrying SL HARQ-ACK reports overlaps
with PUSCH with aperiodic or semi-persistent CSI reports.

A UE does not expect to be scheduled to transmit a PUCCH or a PUSCH with
smaller priority index that would overlap in time with a PUCCH of larger
priority index with HARQ-ACK information only in response to a PDSCH
reception without a corresponding PDCCH unless the UE is provided
*uci-MuxWithDiffPrio*. A UE does not expect to be scheduled to transmit
a PUCCH of smaller priority index that would overlap in time with a
PUSCH of larger priority index with SP-CSI report(s) without a
corresponding PDCCH unless the UE is provided *uci-MuxWithDiffPrio*.

In the remaining of this clause, a UE multiplexes UCIs with same
priority index in a PUCCH or a PUSCH before considering limitations for
UE transmission due to cell DRX operation or as described in clauses
11.1, 11.1.1, 11.2A, 15 and 17.2. A PUCCH or a PUSCH is assumed to have
a same priority index as a priority index of UCIs a UE multiplexes in
the PUCCH or the PUSCH.

In the remaining of this clause, the multiplexing or prioritization for
overlapping channels are for overlapping channels with same priority
index or for overlapping channels with a PUCCH carrying SL HARQ-ACK
information unless stated otherwise.

In the remaining of this clause, if a UE is provided
*subslotLengthForPUCCH* for a cell for PUCCH transmission, a slot for an
associated PUCCH resource of a PUCCH transmission with HARQ-ACK
information on the cell includes a number of symbols indicated by
*subslotLengthForPUCCH*, unless stated otherwise.

If a UE would transmit on a serving cell a PUSCH without UL-SCH that
overlaps with a PUCCH transmission on a serving cell that includes
positive SR information, the UE does not transmit the PUSCH.

If a UE would transmit CSI reports on overlapping physical channels, the
UE applies the priority rules described in \[6, TS 38.214\] for the
multiplexing of CSI reports.

If a UE

\- would multiplex UCI in a PUCCH transmission that overlaps with a
PUSCH transmission, and

\- the PUSCH and PUCCH transmissions fulfil the conditions in clause
9.2.5 for UCI multiplexing,

the UE

\- multiplexes only HARQ-ACK information, if any, from the UCI in the
PUSCH transmission and does not transmit the PUCCH if the UE multiplexes
aperiodic or semi-persistent CSI reports in the PUSCH;

\- multiplexes only HARQ-ACK information and CSI reports, if any, from
the UCI in the PUSCH transmission and does not transmit the PUCCH if the
UE does not multiplex aperiodic or semi-persistent CSI reports in the
PUSCH.

A UE does not expect to multiplex in a PUSCH transmission in one slot
with SCS configuration $\mu_{1}$ UCI of same type that the UE would
transmit in PUCCHs in different slots with SCS configuration $\mu_{2}$
if $\mu_{1} < \mu_{2}$.

A UE does not expect to multiplex in a PUSCH transmission or in a PUCCH
transmission HARQ-ACK information that the UE would transmit in
different PUCCHs of a same priority index.

A UE does not expect a PUCCH resource that results from multiplexing
overlapped PUCCH resources, if applicable, to overlap with more than one
PUSCHs if each of the more than one PUSCHs includes aperiodic CSI
reports.

A UE does not expect to detect a first DCI format having associated
HARQ-ACK information without scheduling a PDSCH reception, and
indicating a resource for a PUCCH transmission with a HARQ-ACK codebook
that would include the HARQ-ACK information in a slot if the UE

\- detects a second DCI format in a PDCCH monitoring occasion, that
starts before a PDCCH monitoring occasion for the first DCI format, that
schedules a PUSCH transmission in the slot, and

\- multiplexes the HARQ-ACK codebook in the PUSCH transmission in the
slot.

If a UE

\- is not provided any of
*enableType1HARQ-ACK-MuxForDL-AssignmentAfterUL-Grant* , or
*enableType2HARQ-ACK-MuxForDL-AssignmentAfterUL-Grant*, or
*enableType3HARQ-ACK-MuxForDL-AssignmentAfterUL-Grant*, or

\- is provided *uci-MuxWithDiffPrio*, or

\- transmits a PUSCH without repetitions or transmits a first repetition
of a PUSCH transmission,

the UE does not expect to detect a first DCI format scheduling a PDSCH
reception and indicating a resource for a PUCCH transmission with
corresponding HARQ-ACK information that would be included in a HARQ-ACK
codebook in a slot if the UE

\- previously detects a second DCI format scheduling the PUSCH
transmission in the slot, and

\- multiplexes the HARQ-ACK codebook in the PUSCH transmission in the
slot.

If a UE

\- is provided *enableType1HARQ-ACK-MuxForDL-AssignmentAfterUL-Grant*,
or *enableType2HARQ-ACK-MuxForDL-AssignmentAfterUL-Grant*, or
*enableType3HARQ-ACK-MuxForDL-AssignmentAfterUL-Grant*, and

\- is not provided *uci-MuxWithDiffPrio*, and

\- transmits a repetition of a PUSCH transmission in a slot other than a
first repetition,

the UE includes, in a HARQ-ACK codebook, HARQ-ACK information associated
with a PDSCH reception scheduled by a first DCI format, in a first PDCCH
monitoring occasion, indicating a first resource for a first PUCCH
transmission in the slot, when

\- the first resource overlaps with the repetition of the PUSCH
transmission

\- the PUSCH transmission is scheduled by a second DCI format in a
second PDCCH monitoring occasion, and

\- the UE multiplexes the HARQ-ACK codebook in the PUSCH transmission in
the slot, and

\- the timeline conditions in clause 9.2.3 for PUCCH resource
determination and the timeline conditions of $T_{proc,1}^{mux}$ and
$T_{proc,2}^{mux}$ for multiplexing the HARQ-ACK information in the
PUSCH, as described in clause 9.2.5, are satisfied,

where

\- the first PUCCH resource is same in the time domain as a second PUCCH
resource that the UE determines for the PUCCH transmission with the
HARQ-ACK information in the slot if the UE is not provided
*enableDiffPUCCH-Resource* and the first PDCCH monitoring occasion
starts after the second PDCCH monitoring occasion, and

\- the second PUCCH resource

\- is indicated by the last DL DCI format in a third PDCCH monitoring
occasion that starts no later than the second PDCCH monitoring occasion,
or

\- is for the PUCCH transmission with the HARQ-ACK information
associated only with SPS PDSCHs activated by DCI formats in PDCCH
monitoring occasions that start no later than the second PDCCH
monitoring occasion

\- UE expects that the size of the HARQ-ACK codebook based on a DAI
value of the second DCI format remains the same if the UE is not
provided *enableDiffCB-Size*.

If a UE multiplexes aperiodic CSI in a PUSCH and the UE would multiplex
UCI that includes HARQ-ACK information in a PUCCH that overlaps with the
PUSCH and the timing conditions for overlapping PUCCHs and PUSCHs in
clause 9.2.5 are fulfilled, the UE multiplexes only the HARQ-ACK
information in the PUSCH and does not transmit the PUCCH.

When a UE transmits multiple PUSCHs on respective serving cells in a
slot with reference to slots for PUCCH transmissions and the multiple
PUSCHs overlap with a PUCCH carrying UCI in the slot, the UE selects all
the PUSCHs overlapping with the PUCCH as the candidate PUSCHs for UCI
multiplexing within the slot.

If a UE would transmit a single PUSCH scheduled by a DCI format that
includes a DAI field on a serving cell in a slot with reference to slots
for PUCCH transmissions without any other PUSCH that would be
transmitted on any serving cell in the slot and the UE does not
determine any PUCCH carrying HARQ-ACK information in the slot, or if the
UE indicates the corresponding capability
*mux-HARQ-ACK-withoutPUCCH-onPUSCH* and the UE transmits multiple PUSCHs
on respective serving cells in a slot with reference to slots for PUCCH
transmissions and the UE does not determine any PUCCH carrying HARQ-ACK
information in the slot and at least one of the multiple PUSCHs is
scheduled by a DCI format that includes a DAI field, the UE selects the
single PUSCH or all the multiple PUSCHs in the slot as the candidate
PUSCHs for HARQ-ACK multiplexing within the slot except for any PUSCH
among the multiple PUSCHs that is scheduled by a DCI format that
indicates a DAI value that is equal to 4 for each DAI value indicated by
2 bits, if any, and is equal to 0 for each DAI value indicated by 1 bit,
if any.

If a Msg3 PUSCH scheduled by a RAR UL grant or a DCI with CRC scrambled
by TC-RNTI overlaps with a PUCCH, the UE does not multiplex UCI on the
Msg3 PUSCH.

The UE determines the PUSCH for UCI multiplexing by applying the
following procedure on the candidate PUSCHs as described in this clause:

\- If the UE is provided *sTx-2Panel*, is provided *ackNackFeedbackMode*
= *separate*, and would multiplex UCI that includes HARQ-ACK information
in a PUSCH, candidate PUSCHs for the UCI multiplexing are the ones
associated with same *coresetPoolIndex* value as for a PUCCH
transmission with the HARQ-ACK information.

\- If the candidate PUSCHs that include first PUSCHs that are scheduled
by DCI formats and second PUSCHs configured by respective
*ConfiguredGrantConfig* or *semiPersistentOnPUSCH*, and the UE would
multiplex UCI in one of the candidate PUSCHs, and the candidate PUSCHs
fulfil the conditions in clause 9.2.5 for UCI multiplexing, the UE
multiplexes the UCI in a PUSCH from the first PUSCHs.

\- If the UE would multiplex UCI in one of the candidate PUSCHs and the
UE does not multiplex aperiodic CSI in any of the candidate PUSCHs, the
UE multiplexes the UCI in a PUSCH of the serving cell with the smallest
*ServCellIndex* subject to the conditions in clause 9.2.5 for UCI
multiplexing being fulfilled. If the UE transmits more than one PUSCHs
in the slot on the serving cell with the smallest *ServCellIndex* that
fulfil the conditions in clause 9.2.5 for UCI multiplexing, the UE
multiplexes the UCI in the earliest PUSCH that the UE transmits in the
slot. If the UE is provided *sTx-2Panel*, is provided
*ackNackFeedbackMode* = *joint* or the UCI does not include HARQ-ACK
information, and the UE would transmit two PUSCHs in the slot that start
at a same symbol on the serving cell with smallest *ServCellIndex* and
fulfil the conditions in clause 9.2.5 for UCI multiplexing, the UE
multiplexes the UCI in the PUSCH from the two PUSCHs associated with
CORESETs that the UE is not provided *coresetPoolIndex* or is provided
*coresetPoolIndex* with a value of 0.

If a UE transmits a PUSCH over one or more slots or multiple PUSCHs over
one or more slots that are scheduled by a DCI format, and the UE would
transmit a PUCCH with HARQ-ACK and/or CSI information over a single slot
that overlaps with the PUSCH transmission in the one or more slots, and
the PUSCH transmission in the one or more slots fulfills the conditions
in clause 9.2.5 for multiplexing the HARQ-ACK and/or CSI information,
the UE multiplexes the HARQ-ACK and/or CSI information in the PUSCH
transmission in the one or more slots. The UE does not multiplex
HARQ-ACK and/or CSI information in the PUSCH transmission in a slot from
the one or more slots if the UE would not transmit a single-slot PUCCH
with HARQ-ACK and/or CSI information in the slot in case the PUSCH
transmission was absent.

If a UE transmits a PUSCH with repetition Type B and the UE would
transmit a PUCCH with HARQ-ACK and/or CSI information over a single slot
that overlaps with the PUSCH transmission in one or more slots, the UE
expects all actual repetitions of the PUSCH transmission \[6, TS
38.214\] that would overlap with the PUCCH transmission to fulfill the
conditions in clause 9.2.5 for multiplexing the HARQ-ACK and/or CSI
information, and the UE multiplexes the HARQ-ACK and/or CSI information
in the earliest actual PUSCH repetition of the PUSCH transmission that
would overlap with the PUCCH transmission and includes more than one
symbol. The UE does not expect that all actual repetitions that would
overlap with the PUCCH transmission do not include more than one symbol.

If the PUSCH transmission over the one or more slots is scheduled by a
DCI format that includes a DAI field, or if the multiple PUSCH
transmissions over the one or more slots are scheduled by a DCI format
that includes a DAI field, the value of the DAI field is applicable for
multiplexing HARQ-ACK information in any PUSCH transmission in any slot
from the one or more slots where the UE multiplexes HARQ-ACK
information.

When a UE would multiplex HARQ-ACK information in a PUSCH transmission
that is configured by a *ConfiguredGrantConfig*, and includes CG-UCI
\[5, TS 38.212\], the UE multiplexes the HARQ-ACK information in the
PUSCH transmission if the UE is provided *cg-UCI-Multiplexing*;
otherwise, if the HARQ-ACK information and the PUSCH have same priority
index, the UE does not transmit the PUSCH and multiplexes the HARQ-ACK
information in a PUCCH transmission or in another PUSCH transmission; if
the HARQ-ACK information and the PUSCH have different priority indexes,
the UE does not transmit the channel with the smaller priority index.

In the following, DCI formats with CRC scrambled by C-RNTI or CS-RNTI or
MCS-C-RNTI are also referred to as unicast DCI formats and DCI formats
with CRC scrambled by Multicast MCCH-RNTI, G-RNTI for multicast or
G-CS-RNTI are also referred to as multicast DCI formats. Corresponding
unicast DCI formats are DCI formats 0_0/0_1/0_2/0_3/1_0/1_1/1_2/1_3 and
multicast DCI formats are DCI formats 4_0/4_1/4_2 \[4, TS 38.212\].
PDSCH receptions scheduled by unicast or multicast DCI formats are
referred as unicast or multicast PDSCH receptions. HARQ-ACK information
associated with unicast or multicast DCI formats for PDCCH receptions in
RRC_CONNECTED state are also respectively referred as unicast or
multicast HARQ-ACK information.

For the remaining of this clause, if a UE is provided $K_{cell,offset}$
by *cellSpecificKoffset* or $K_{UE,offset}$ by a MAC CE command,
reference to a slot $n + k$ for a PUCCH transmission or PUSCH
transmission corresponds to a slot
$n + k + 2^{\mu - \mu_{K_{offset}}} \bullet K_{offset}$ for the PUSCH or
the PUCCH transmission, and reference to a slot $n_{U} - K_{1,k}$
corresponds to slot
$n_{U} - K_{1,k} - 2^{\mu - \mu_{K_{offset}}} \bullet K_{offset}$, where
$\mu$ is the SCS configuration for the PUCCH transmission or PUSCH
transmission, $K_{offset}$ is defined in clause 4.2, and
$\mu_{K_{offset}} = 0$ in FR1 and in FR2-NTN. If *cellSpecificKoffset*
or if the MAC CE command is not provided, $K_{cell,offset} = 0$ or
$K_{UE,offset} = 0$, respectively. If the PUCCH or PUSCH transmission is
scheduled by a DCI format, or if SRS transmission is triggered by a DCI
format, the value of $K_{UE,offset}$ is the one that is applicable at
the slot overlapping with the last symbol of the PDCCH reception
providing the DCI format. If the PUCCH transmission or the PUSCH
transmission is scheduled by a DCI format with CRC scrambled by TC-RNTI,
$K_{UE,offset} = 0$. If the UE is provided a $K_{UE,offset}$ value by a
MAC CE command, the UE applies the MAC CE command in the first slot that
is after slot $k + 3N_{slot}^{subframe,\mu}$ where $k$ is the slot where
the UE would transmit a PUCCH with HARQ-ACK information for the PDSCH
providing the MAC CE command, $\mu$ is the SCS configuration for the
PUCCH transmission that is determined in the slot when the MAC CE
command is applied.