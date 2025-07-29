## 10.3 PDCCH monitoring indication and dormancy/non-dormancy behaviour for SCells

A UE configured with DRX mode operation \[11, TS 38.321\] can be
provided the following for detection of a DCI format 2_6 in a PDCCH
reception on the PCell or on the SpCell \[12, TS 38.331\]

\- a PS-RNTI for DCI format 2_6 by *ps-RNTI*

\- a number of search space sets, by *dci-Format2-6*, to monitor PDCCH
for detection of DCI format 2_6 on the active DL BWP of the PCell or of
the SpCell according to a common search space as described in clause
10.1

\- a payload size for DCI format 2_6 by *sizeDCI-2-6*

\- a location in DCI format 2_6 of a Wake-up indication bit by
*ps-PositionDCI-2-6*

\- a \'0\' value for the Wake-up indication bit, when reported to higher
layers, indicates to not start the *drx-onDurationTimer* for the next
long DRX cycle \[11, TS 38.321\]

\- a \'1\' value for the Wake-up indication bit, when reported to higher
layers, indicates to start the *drx-onDurationTimer* for the next long
DRX cycle \[11, TS 38.321\]

\- a bitmap, when the UE is provided a number of groups of configured
SCells by *dormancyGroupOutsideActiveTime*, where

\- the bitmap location is immediately after the Wake-up indication bit
location

\- the bitmap size is equal to the number of groups of configured SCells
where each bit of the bitmap corresponds to a group of configured SCells
from the number of groups of configured SCells

\- a \'0\' value for a bit of the bitmap indicates an active DL BWP,
provided by *dormantBWP-Id*, for the UE \[11, TS 38.321\] for each
activated SCell in the corresponding group of configured SCells

\- a \'1\' value for a bit of the bitmap indicates

\- an active DL BWP, provided by *firstOutsideActiveTimeBWP-Id*, for the
UE for each activated SCell in the corresponding group of configured
SCells, if a current active DL BWP is the dormant DL BWP

\- a current active DL BWP, for the UE for each activated SCell in the
corresponding group of configured SCells, if the current active DL BWP
is not the dormant DL BWP

\- the UE sets the active DL BWP to the indicated active DL BWP

\- an offset by *ps-Offset* indicating a time, where the UE starts
monitoring PDCCH for detection of DCI format 2_6 according to the number
of search space sets, prior to a slot where the *drx-onDurationTimer*
would start on the PCell or on the SpCell \[11, TS 38.321\]

\- for each search space set, the PDCCH monitoring occasions are the
ones in the first $T_{\text{s}}$ slots indicated by *duration*, or
$T_{\text{s}} = 1$ slot if *duration* is not provided, starting from the
first slot of the first $T_{\text{s}}$ slots and ending prior to the
start of *drx-onDurationTimer*.

On PDCCH monitoring occasions associated with a same long DRX Cycle, a
UE does not expect to detect more than one DCI format 2_6 with different
values of the Wake-up indication bit for the UE or with different values
of the bitmap for the UE.

The UE does not monitor PDCCH for detecting DCI format 2_6 during Active
Time \[11, TS 38.321\].

If a UE reports for an active DL BWP a *MinTimeGap* or *MinTimeGapFR2-2*
value that is X slots prior to the beginning of a slot where the UE
would start the *drx-onDurationTimer*, the UE is not required to monitor
PDCCH for detection of DCI format 2_6 during the X slots, where X
corresponds to the *MinTimeGap* or *MinTimeGapFR2-2* value of the SCS of
the active DL BWP in Table 10.3-1.

Table 10.3-1 Minimum time gap value X

+-------------------+-----------------------------------------------------+
| SCS (kHz)         | Minimum Time Gap X (slots)                          |
|                   +--------------------------+--------------------------+
|                   | Value 1                  | Value 2                  |
+===================+==========================+==========================+
| 15                | 1                        | 3                        |
+-------------------+--------------------------+--------------------------+
| 30                | 1                        | 6                        |
+-------------------+--------------------------+--------------------------+
| 60                | 1                        | 12                       |
+-------------------+--------------------------+--------------------------+
| 120               | 2                        | 24                       |
+-------------------+--------------------------+--------------------------+
| 480               | 8                        | 96                       |
+-------------------+--------------------------+--------------------------+
| 960               | 16                       | 192                      |
+-------------------+--------------------------+--------------------------+

If a UE is provided search space sets to monitor PDCCH for detection of
DCI format 2_6 in the active DL BWP of the PCell or of the SpCell and
the UE detects DCI format 2_6, the physical layer of a UE reports the
value of the Wake-up indication bit for the UE to higher layers \[11, TS
38.321\] for the next long DRX cycle.

If a UE is provided search space sets to monitor PDCCH for detection of
DCI format 2_6 in the active DL BWP of the PCell or of the SpCell and
the UE does not detect DCI format 2_6, the physical layer of the UE does
not report a value of the Wake-up indication bit to higher layers for
the next long DRX cycle.

If a UE is provided search space sets to monitor PDCCH for detection of
DCI format 2_6 in the active DL BWP of the PCell or of the SpCell and
the UE

\- is not required to monitor PDCCH for detection of DCI format 2_6, as
described in clauses 10, 11.1, 12, and in clause 5.7 of \[11, TS
38.321\] for all corresponding PDCCH monitoring occasions outside Active
Time prior to a next long DRX cycle, or

\- does not have any PDCCH monitoring occasions for detection of DCI
format 2_6 outside Active Time of a next long DRX cycle

the physical layer of the UE reports a value of 1 for the Wake-up
indication bit to higher layers for the next long DRX cycle.

If a UE is provided search space sets to monitor PDCCH for detection of
DCI format 0_1/0_3/1_1/1_3 and if any of DCI format 0_1/0_3/1_1/1_3
includes a SCell dormancy indication field,

\- the SCell dormancy indication field is a bitmap with size equal to a
number of groups of configured SCells, provided by
*dormancyGroupWithinActiveTime*,

\- each bit of the bitmap corresponds to a group of configured SCells
from the number of groups of configured SCells

\- if the UE detects a DCI format 0_1/1_1 that does not include a
carrier indicator field, or a DCI format 0_1/1_1 that includes a carrier
indicator field with value equal to 0, and if the DCI format 0_1 does
not indicate UL grant Type 2 release nor deactivate semi-persistent CSI
report(s) on PUSCH, or if the DCI format 1_1 does not indicate SPS PDSCH
release, or if the DCI format 1_1 does not indicate a TCI state update
without scheduling PDSCH reception, or if the UE detects a DCI format
0_3/1_3

\- a \'0\' value for a bit of the bitmap indicates an active DL BWP,
provided by *dormantBWP-Id*, for the UE for each activated SCell in the
corresponding group of configured SCells

\- a \'1\' value for a bit of the bitmap indicates

\- an active DL BWP, provided by *firstWithinActiveTimeBWP-Id*, for the
UE for each activated SCell in the corresponding group of configured
SCells, if a current active DL BWP is the dormant DL BWP

\- a current active DL BWP, for the UE for each activated SCell in the
corresponding group of configured SCells, if the current active DL BWP
is not the dormant DL BWP

\- the UE sets the active DL BWP to the indicated active DL BWP

If a UE is provided search space sets to monitor PDCCH for detection of
DCI format 1_1, or of DCI format 1_3, and if

\- the CRC of DCI format 1_1 or of DCI format 1_3 is scrambled by a
C-RNTI or an MCS-C-RNTI, and if

\- a one-shot HARQ-ACK request field is not present or has a \'0\'
value, and if

\- for DCI format 1_3, a HARQ-ACK retransmission indicator field is not
present or has a \'0\' value, and if

\- the UE detects a DCI format 1_1 on the primary cell that does not
include a carrier indicator field, or detects a DCI format 1_1 on the
primary cell that includes a carrier indicator field with value equal to
0, or detects a DCI format 1_3 on the primary cell,

and if

\- *resourceAllocation* = *resourceAllocationType0* and all bits of the
frequency domain resource assignment field in DCI format 1_1, or for one
or more blocks of the frequency domain resource assignment field in DCI
format 1_3, are equal to 0, or

\- *resourceAllocation* = *resourceAllocationType1* and all bits of the
frequency domain resource assignment field in DCI format 1_1, or for one
or more blocks of the frequency domain resource assignment field in DCI
format 1_3, are equal to 1, or

\- *resourceAllocation = dynamicSwitch* and all bits of the frequency
domain resource assignment field in DCI format 1_1, or for one or more
blocks of the frequency domain resource assignment field in DCI format
1_3, are equal to 0 or 1

the UE considers the DCI format 1_1 or the DCI format 1_3 as indicating
SCell dormancy, not scheduling a PDSCH reception on a serving cell,
where for DCI format 1_3 the serving cell is the one with the smallest
index that is associated with a block from the one or more blocks of the
frequency domain resource assignment field, and for transport block 1
interprets the sequence of fields of

\- modulation and coding scheme

\- new data indicator

\- redundancy version

and of

\- HARQ process number

\- antenna port(s) for DCI format 1_1, or for DCI format 1_3 if
*AntennaPortsDCI1-3* is configured as \'*type2*\'

\- DMRS sequence initialization for DCI format 1_1

as providing a bitmap to each configured SCell, in an ascending order of
the SCell index, where

\- a \'0\' value for a bit of the bitmap indicates an active DL BWP,
provided by *dormantBWP-Id*, for the UE for a corresponding activated
SCell

\- a \'1\' value for a bit of the bitmap indicates

\- an active DL BWP, provided by *firstWithinActiveTimeBWP-Id*, for the
UE for a corresponding activated SCell, if a current active DL BWP is
the dormant DL BWP

\- a current active DL BWP, for the UE for a corresponding activated
SCell, if the current active DL BWP is not the dormant DL BWP

\- the UE sets the active DL BWP to the indicated active DL BWP

If an active DL BWP provided by *dormantBWP-Id* for a UE on an activated
SCell is not a default DL BWP for the UE on the activated SCell, as
described in clause 12, the BWP inactivity timer is not used for
transitioning from the active DL BWP provided by *dormantBWP-Id* to the
default DL BWP on the activated SCell.

A UE is expected to provide HARQ-ACK information in response to a
detection of a DCI format 1_1/1_3 indicating SCell dormancy after
$N$ symbols from the last symbol of a PDCCH providing the DCI format
1_1/1_3. If *processingType2Enabled* of *PDSCH-ServingCellConfig* is set
to *enable* for the serving cell with the PDCCH providing the DCI format
1_1/1_3, $N = 7$ for $\mu = 0$, $N = 7.5$ for $\mu = 1$, and $N = 15$
for $\mu = 2$; otherwise, $N = 14$ for $\mu = 0$, $N = 16$ for
$\mu = 1$, $N = 27$ for $\mu = 2$, $N = 31$ for $\mu = 3$, $N = 124$ for
$\mu = 5$, and $= 248$ for $\mu = 6$, where $\mu$ is the smallest SCS
configuration between the SCS configuration of the PDCCH providing the
DCI format 1_1/1_3 and the SCS configuration of a PUCCH with the
HARQ-ACK information in response to the detection of the DCI format
1_1/1_3.