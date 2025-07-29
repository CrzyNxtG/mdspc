## 10.4 Search space set group switching and skipping of PDCCH monitoring

A UE can be provided

\- a group index for a respective Type3-PDCCH CSS set or USS set by
*searchSpaceGroupIdList* for PDCCH monitoring on a serving cell,

\- a group index for a respective Type3-PDCCH CSS set or USS set by
*searchSpaceGroupIdList-r17* for PDCCH monitoring on an active DL BWP of
a serving cell.

If the UE is not provided *searchSpaceGroupIdList* or
*searchSpaceGroupIdList-r17* for a search space set, the following
procedures that are based on search space set group switching are not
applicable for PDCCH monitoring according to the search space set.

A UE can be provided a set of durations by *pdcch-SkippingDurationList*
for Type3-PDCCH CSS set or USS set for PDCCH monitoring on an active DL
BWP of a serving cell. If the UE is not provided
*pdcch-SkippingDurationList*, the following procedures related to
skipping of PDCCH monitoring are not applicable.

If a UE is provided *cellGroupsForSwitchList*, indicating one or more
groups of serving cells, the following procedures apply to all serving
cells within each group; otherwise, the following procedures apply only
to a serving cell for which the UE is provided *searchSpaceGroupIdList*.

When a UE is provided *searchSpaceGroupIdList* or
*searchSpaceGroupIdList-r17*, the UE resets PDCCH monitoring according
to search space sets with group index 0, if provided by
*searchSpaceGroupIdList* or *searchSpaceGroupIdList-r17*.

A UE can be provided by *searchSpaceSwitchDelay* or
*searchSpaceSwitchDelay-r17* a number of symbols $P_{switch}$ where a
minimum value of $P_{switch}$ is provided in Table 10.4-1 for UE
processing capability 1 and UE processing capability 2 and SCS
configuration $\mu$. UE processing capability 1 for SCS configuration
$\mu$ applies unless the UE indicates support for UE processing
capability 2.

Table 10.4-1: Minimum value of $\mathbf{P}_{\mathbf{switch}}$
\[symbols\]

+------------------+---------------------------------+---------------------------------+
| $$\mathbf{\mu}$$ | Minimum                         | Minimum                         |
|                  | $\mathbf{P}_{\mathbf{switch}}$  | $\mathbf{P}_{\mathbf{switch}}$  |
|                  | value for                       | value for                       |
|                  |                                 |                                 |
|                  | UE processing capability 1      | UE processing capability 2      |
|                  | \[symbols\]                     | \[symbols\]                     |
+------------------+---------------------------------+---------------------------------+
| 0                | 25                              | 10                              |
+------------------+---------------------------------+---------------------------------+
| 1                | 25                              | 12                              |
+------------------+---------------------------------+---------------------------------+
| 2                | 25                              | 22                              |
+------------------+---------------------------------+---------------------------------+
| 3                | 40                              | \-                              |
+------------------+---------------------------------+---------------------------------+
| 5                | 160                             | \-                              |
+------------------+---------------------------------+---------------------------------+
| 6                | 320                             | \-                              |
+------------------+---------------------------------+---------------------------------+

A UE can be provided, by *searchSpaceSwitchTimer*, a timer value for a
serving cell that the UE is provided *searchSpaceGroupIdList* or, if
provided, for a set of serving cells provided by
*cellGroupsForSwitchList*. The UE decrements the timer value by one
after each slot based on a reference SCS configuration that is the
smallest SCS configuration $\mu$ among all configured DL BWPs in the
serving cell, or in the set of serving cells. The UE maintains the
reference SCS configuration during the timer decrement procedure.

If a UE is provided by *SearchSpaceSwitchTrigger* a location of a search
space set group switching flag field in a DCI format 2_0, as described
in clause 11.1.1, for a serving cell where the UE has active DL BWP with
SCS configuration $\mu$

\- if the UE detects a DCI format 2_0 and a value of the search space
set group switching flag field in the DCI format 2_0 is 0, the UE starts
monitoring PDCCH according to search space sets with group index 0, and
stops monitoring PDCCH according to search space sets with group index
1, for the serving cell

\- at the beginning of the first slot that is at least $P_{switch}$
symbols after the last symbol of the PDCCH with the DCI format 2_0 when
$\mu \in \left\{ 0,\ 1,\ 2,\ 3 \right\}$

\- at the beginning of the first slot, of a group of $X_{s}$ slots, that
is at least $P_{switch}$ symbols after the last symbol of the PDCCH with
the DCI format 2_0 when $\mu \in \left\{ 5,\ 6 \right\}$

\- if the UE detects a DCI format 2_0 and a value of the search space
set group switching flag field in the DCI format 2_0 is 1, the UE starts
monitoring PDCCH according to search space sets with group index 1, and
stops monitoring PDCCH according to search space sets with group index
0, for the serving cell

\- at the beginning of the first slot that is at least $P_{switch}$
symbols after the last symbol of the PDCCH with the DCI format 2_0, when
$\mu \in \left\{ 0,\ 1,\ 2,\ 3 \right\}$

\- at the beginning of the first slot, of a group of $X_{s}$ slots, that
is at least $P_{switch}$ symbols after the last symbol of the PDCCH with
the DCI format 2_0 when $\mu \in \left\{ 5,\ 6 \right\}$

and the UE sets the timer value to the value provided by
*searchSpaceSwitchTimer*

\- if the UE monitors PDCCH for a serving cell according to search space
sets with group index 1, the UE starts monitoring PDCCH for the serving
cell according to search space sets with group index 0, and stops
monitoring PDCCH according to search space sets with group index 1, for
the serving cell

\- at the beginning of the first slot that is at least $P_{switch}$
symbols after a slot where the timer expires or after a last symbol of a
remaining channel occupancy duration for the serving cell if indicated
by DCI format 2_0 when $\mu \in \left\{ 0,\ 1,\ 2,\ 3 \right\}$

\- at the beginning of the first slot, of a group of $X_{s}$ slots, that
is at least $P_{switch}$ symbols after a slot where the timer expires or
after a last symbol of a remaining channel occupancy duration for the
serving cell if indicated by DCI format 2_0 when
$\mu \in \left\{ 5,\ 6 \right\}$

If a UE is provided *searchSpaceGroupIdList* and is not provided
*SearchSpaceSwitchTrigger* for a serving cell,

\- if the UE detects a DCI format by monitoring PDCCH according to a
search space set with group index 0, the UE starts monitoring PDCCH
according to search space sets with group index 1, and stops monitoring
PDCCH according to search space sets with group index 0, for the serving
cell

\- at the beginning of the first slot that is at least $P_{switch}$
symbols after the last symbol of the PDCCH with the DCI format when
$\mu \in \left\{ 0,\ 1,\ 2,\ 3 \right\}$,

\- at the beginning of the first slot, of a group of $X_{s}$ slots, that
is at least $P_{switch}$ symbols after the last symbol of the PDCCH with
the DCI format when $\mu \in \left\{ 5,\ 6 \right\}$

the UE sets the timer value to the value provided by
*searchSpaceSwitchTimer* if the UE detects a DCI format by monitoring
PDCCH in any search space set

\- if the UE monitors PDCCH for a serving cell according to search space
sets with group index 1, the UE starts monitoring PDCCH for the serving
cell according to search space sets with group index 0, and stops
monitoring PDCCH according to search space sets with group index 1, for
the serving cell

\- at the beginning of the first slot that is at least $P_{switch}$
symbols after a slot where the timer expires or, if the UE is provided a
search space set to monitor PDCCH for detecting a DCI format 2_0, after
a last symbol of a remaining channel occupancy duration for the serving
cell if indicated by DCI format 2_0 when
$\mu \in \left\{ 0,\ 1,\ 2,\ 3 \right\}$

\- at the beginning of the first slot, of a group of $X_{s}$ slots, that
is at least $P_{switch}$ symbols after a slot where the timer expires
or, if the UE is provided a search space set to monitor PDCCH for
detecting a DCI format 2_0, after a last symbol of a remaining channel
occupancy duration for the serving cell if indicated by DCI format 2_0
when $\mu \in \left\{ 5,\ 6 \right\}$

A UE determines a slot and a symbol in the slot to start or stop PDCCH
monitoring according to search space sets for a serving cell that the UE
is provided *searchSpaceGroupIdList* or, if *cellGroupsForSwitchList* is
provided, for a set of serving cells, based on the largest $X_{s}$ if
the SCS configuration $\mu$ among all configured DL BWPs in the set of
serving cells equals to 6, otherwise, based on the smallest SCS
configuration $\mu$ among all configured DL BWPs in the serving cell or
in the set of serving cells and, if any, in the serving cell where the
UE receives a PDCCH and detects a corresponding DCI format 2_0
triggering the start or stop of PDCCH monitoring according to search
space sets.

A UE can be provided a set of durations by *pdcch-SkippingDurationList*
for PDCCH monitoring on an active DL BWP of a serving cell and, if the
UE is not provided *searchSpaceGroupIdList-r17* on the active DL BWP of
the serving cell, a DCI format 0_1/0_2/0_3 that schedules PUSCH
transmission, and a DCI format 1_1/1_2/1_3 that schedules PDSCH
reception, can include a PDCCH monitoring adaptation field of 1 bit or
of 2 bits.

If the field has 1 bit and for PDCCH monitoring by the UE according to
Type3-PDCCH CSS sets or USS sets on the active DL BWP of the serving
cell

\- a \'0\' value for the bit indicates no skipping in PDCCH monitoring

\- a \'1\' value for the bit indicates skipping PDCCH monitoring for a
duration provided by the first value in the set of durations

If the field has 2 bits and for PDCCH monitoring by the UE according to
Type3-PDCCH CSS sets or USS sets on the active DL BWP of the serving
cell

\- a \'00\' value for the bits indicates no skipping in PDCCH monitoring

\- a \'01\' value for the bits indicates skipping PDCCH monitoring for a
duration provided by the first value in the set of durations

\- a \'10\' value for the bits indicates skipping PDCCH monitoring for a
duration provided by the second value in the set of durations

\- a \'11\' value for the bits indicates skipping PDCCH monitoring for a
duration provided by the third value in the set of durations, if any;
otherwise, if the set of durations includes two values, a use of the
\'11\' value is reserved

A UE can be provided group indexes for a Type3-PDCCH CSS set or USS set
by *searchSpaceGroupIdList-r17* for PDCCH monitoring on an active DL BWP
of a serving cell and, if the UE is not provided
*pdcch-SkippingDurationList* for the active DL BWP of the serving cell,
a DCI format 0_1/0_2/0_3 that schedules PUSCH transmission, and a DCI
format 1_1/1_2/1_3 that schedules PDSCH reception, can include a PDCCH
monitoring adaptation field of 1 bit or of 2 bits for the serving cell.

If the field has 1 bit and for PDCCH monitoring by the UE according to
Type3-PDCCH CSS sets or USS sets on the active DL BWP of the serving
cell

\- a \'0\' value for the bit indicates start of PDCCH monitoring
according to search space sets with group index 0 and stop of PDCCH
monitoring according to search space sets with other group indexes, if
any

\- a \'1\' value for the bit indicates start of PDCCH monitoring
according to search space sets with group index 1 and stop of PDCCH
monitoring according to search space sets with other group indexes, if
any, and the UE sets the timer value to the one provided by
*searchSpaceSwitchTimer-r17*, if provided

If the field has 2 bits and for PDCCH monitoring by the UE according to
Type3-PDCCH CSS sets or USS sets on the active DL BWP of the serving
cell

\- a \'00\' value for the bit indicates start of PDCCH monitoring
according to search space sets with group index 0 and stop of PDCCH
monitoring according to search space sets with other group indexes, if
any

\- a \'01\' value for the bit indicates start of PDCCH monitoring
according to search space sets with group index 1 and stop of PDCCH
monitoring according to search space sets with other group indexes, if
any, and the UE sets the timer value to the one provided by
*searchSpaceSwitchTimer-r17*, if provided

\- a \'10\' value for the bit indicates start of PDCCH monitoring
according to search space sets with group index 2 and stop of PDCCH
monitoring according to search space sets with other group indexes, if
any, and the UE sets the timer value to the one provided by
*searchSpaceSwitchTimer-r17*, if provided

\- a \'11\' value is reserved

A UE can be provided a set of durations by *pdcch-SkippingDurationList*
and group indexes for a Type3-PDCCH CSS set or USS set by
*searchSpaceGroupIdList-r17* for PDCCH monitoring on an active DL BWP of
a serving cell and, a DCI format 0_1/0_2/0_3 that schedules PUSCH
transmission, and a DCI format 1_1/1_2/1_3 that schedules PDSCH
reception, can include a PDCCH monitoring adaptation field of 2 bits.

If the set of durations includes one value and for PDCCH monitoring by
the UE according to Type3-PDCCH CSS sets or USS sets on the active DL
BWP of the serving cell

\- a \'00\' value for the bits indicates start of PDCCH monitoring
according to search space sets with group index 0 and stop of PDCCH
monitoring according to search space sets with group index 1, if any

\- a \'01\' value for the bits indicates start of PDCCH monitoring
according to search space sets with group index 1 and stop of PDCCH
monitoring according to search space sets with group index 0, if any,
and the UE sets the timer value to the one provided by
*searchSpaceSwitchTimer-r17*, if provided

\- a \'10\' value for the bits indicates skipping PDCCH monitoring for a
duration provided by the value in the set of durations

\- a \'11\' value is reserved

If the set of durations includes two values and for PDCCH monitoring by
the UE according to Type3-PDCCH CSS sets or USS sets on active DL BWP of
the serving cell

\- a \'00\' value for the bits indicates start of PDCCH monitoring
according to search space sets with group index 0 and stop of PDCCH
monitoring according to search space sets with group index 1, if any

\- a \'01\' value for the bits indicates start of PDCCH monitoring
according to search space sets with group index 1 and stop of PDCCH
monitoring according to search space sets with group index 0, if any,
and the UE sets the timer value to the one provided by
*searchSpaceSwitchTimer-r17*, if provided

\- a \'10\' value for the bits indicates skipping PDCCH monitoring for a
duration provided by the first value in the set of durations

\- a \'11\' value for the bits indicates skipping PDCCH monitoring for a
duration provided by the second value in the set of durations

When the PDCCH monitoring adaptation field indicates to a UE to start
PDCCH monitoring according to search space sets with a first group index
and stop PDCCH monitoring according to search space sets with a second
group index, the UE applies the indication

\- at the beginning of a first slot that is at least $P_{switch}$
symbols after the last symbol of the PDCCH reception providing the DCI
format with the PDCCH monitoring adaptation field when
$\mu \in \left\{ 0,\ 1,\ 2,\ 3 \right\}$,

\- at the beginning of a first slot, of a slot group of $X_{s}$ slots,
that is at least $P_{switch}$ symbols after the last symbol of the PDCCH
reception providing the DCI format with the PDCCH monitoring adaptation
field when $\mu \in \left\{ 5,\ 6 \right\}$

When the PDCCH monitoring adaptation field indicates to a UE to skip
PDCCH monitoring for a duration on the active DL BWP of a serving cell,
the UE starts skipping of PDCCH monitoring at the beginning of a first
slot that is after the last symbol of the PDCCH reception providing the
DCI format with the PDCCH monitoring adaptation field.

\- If the UE transmits a PUCCH providing a positive SR before the UE
detects a DCI format providing the PDCCH monitoring adaptation field
indicating to the UE to skip PDCCH monitoring for the duration on the
active DL BWP of the serving cell, the UE shall monitor PDCCH regardless
of PDCCH skipping indication on all serving cells of the corresponding
Cell Group when the SR is pending \[11, TS 38.321\].

\- If the UE transmits a PUCCH providing a positive SR after the UE
detects a DCI format providing the PDCCH monitoring adaptation field
indicating to the UE to skip PDCCH monitoring for the duration on the
active DL BWP of the serving cell, the UE resumes PDCCH monitoring
starting at the beginning of a first slot that is after a last symbol of
the PUCCH transmission in all serving cells of the corresponding Cell
Group.

\- When the UE is provided *pdcch-MonitoringResumptionAfterNack*, after
the UE detects a DCI format providing the PDCCH monitoring adaptation
field indicating to the UE to skip PDCCH monitoring for the duration on
the active DL BWP of the serving cell, if the UE transmits a PUCCH or a
PUSCH providing a NACK value associated with a PDSCH reception that is
scheduled by a DCI format in a PDCCH reception on the serving cell, the
UE terminates PDCCH skipping, starting from the beginning of a first
slot that is after a last symbol of the PUCCH or PUSCH transmission on
the serving cell.

\- During the time of *ra-ResponseWindow* or *msgB-ResponseWindow* or
the duration where *ra-ContentionResolutionTimer* is running, the UE
shall not skip PDCCH monitoring on SpCell.

\- After the UE detects a DCI format providing the PDCCH monitoring
adaptation field indicating to the UE to skip PDCCH monitoring for the
duration on the active DL BWP of a SpCell, when contention resolution is
successful \[11, TS 38.321\], the UE resumes PDCCH monitoring on the
SpCell.

\- After the UE detects a DCI format providing the PDCCH monitoring
adaptation field indicating to the UE to skip PDCCH monitoring for the
duration on the active DL BWP of a serving cell, when a pending SR is
cancelled \[11, TS 38.321\], the UE resumes PDCCH monitoring in all
serving cells of the corresponding Cell Group.

\- If UE transmits a RACH due to positive SR, the UE shall not skip
PDCCH monitoring on any serving cell of the corresponding Cell Group
during the time of *ra-ResponseWindow* or *msgB-ResponseWindow* or the
duration where *ra-ContentionResolutionTimer* is running. If DRX is
configured and the DRX group of the serving cell enters outside Active
Time, the UE terminates PDCCH skipping for the serving cell.

If the UE changes to a new active DL BWP of the serving cell by the
expiration of *bwp-InactivityTimer*, or by RA procedure requested by
higher layers \[11, TS 38.321\], or by RRC configuration, the UE

\- resumes PDCCH monitoring according to the search space sets on the
new active BWP of the serving cell when UE is in a PDCCH skipping
duration, if the UE is not provided *searchSpaceGroupIdList-r17* on the
new active DL BWP

\- monitors PDCCH according to search space sets with group index 0 on
the new active BWP of the serving cell, if the UE is provided
*searchSpaceGroupIdList-r17*.

If a UE is provided group indexes for a Type3-PDCCH CSS set or a USS set
by *searchSpaceGroupIdList-r17* and a timer value by
*searchSpaceSwitchTimer-r17* for PDCCH monitoring an active DL BWP of on
a serving cell and the timer is running, the UE

\- resets the timer after a slot of the active DL BWP of the serving
cell if the UE detects a DCI format in a PDCCH reception in the slot for
with CRC scrambled by C-RNTI/CS-RNTI/MCS-C-RNTI/G-RNTI for
multicast/G-CS-RNTI

\- otherwise, decrements the timer value by one after a slot of the
active DL BWP of the serving cell

When the timer expires in a first slot, the UE monitors PDCCH on the
serving cell according to search space sets with group index 0 starting
in a second slot that

\- is not earlier than $P_{switch}$ symbols after the first slot when
$\mu \in \left\{ 0,\ 1,\ 2,\ 3 \right\}$,

\- is a first slot in a slot group of $X_{s}$ slots that is not earlier
than $P_{switch}$ symbols after the first slot when
$\mu \in \left\{ 5,\ 6 \right\}$,

\- is not earlier than a slot where a PDCCH skipping duration expires,
if applicable

When a UE receives

\- a first PDCCH in a first slot that provides a DCI format with a PDCCH
monitoring adaptation field having a first value indicating skipping
PDCCH monitoring, or indicating start of PDCCH monitoring according to a
search space sets with a first group index and stop of PDCCH monitoring
according to search space sets with a second group index, for an active
DL BWP and

\- a second PDCCH that provides a DCI format with a PDCCH monitoring
adaptation field having a second value indicating skipping PDCCH
monitoring, or indicating start of PDCCH monitoring according to search
space sets with a first group index and stop of PDCCH monitoring
according to search space sets with a second group index different than
the first group index, for the active DL BWP where the second PDCCH is
received

\- in the first slot if the first value indicates skipping PDCCH
monitoring

\- before a slot that is at least $P_{switch}$ symbols after the first
slot if the first value indicates start of PDCCH monitoring according to
search space sets with a first group index

the UE does not expect the second value to be different than the first
value.

A UE does not expect to receive in a second slot a PDCCH on an active DL
BWP that provides a DCI format indicating skipping PDCCH monitoring, or
start of PDCCH monitoring according to search space sets with group
index 1 or 2 for the active DL BWP, if the second slot is not at least
$P_{switch}$ symbols after a first slot where the timer expires.