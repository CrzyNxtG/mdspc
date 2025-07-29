### 11.1.1 UE procedure for determining slot format

This clause applies for a serving cell that is included in a set of
serving cells configured to a UE by *slotFormatCombToAddModList* and
*slotFormatCombToReleaseList*, *availableRB-SetsToAddModList* and
*availableRB-SetsToReleaseList*, *switchTriggerToAddModList* and
*switchTriggerToReleaseList*, or *co-DurationsPerCellToAddModList* and
*co-DurationsPerCellToReleaseList*.

If a UE is configured by higher layers with parameter
*SlotFormatIndicator*, the UE is provided an SFI-RNTI by *sfi-RNTI* and
with a payload size of DCI format 2_0 by *dci-PayloadSize*.

The UE is also provided in one or more serving cells with a
configuration for a search space set
![](media/image170.wmf){width="0.13541666666666666in"
height="0.13541666666666666in"} and a corresponding CORESET $p$ for
monitoring $M_{p,s}^{\left( L_{SFI} \right)}$ PDCCH candidates for DCI
format 2_0 with a CCE aggregation level of $L_{SFI}$ CCEs as described
in clause 10.1. The $M_{p,s}^{\left( L_{SFI} \right)}$ PDCCH candidates
are the first $M_{p,s}^{\left( L_{SFI} \right)}$ PDCCH candidates for
CCE aggregation level $L_{SFI}$ for search space set $s$ in CORESET $p$.

For each serving cell in the set of serving cells, the UE can be
provided:

\- an identity of the serving cell by *servingCellId*

\- a location of a SFI-index field in DCI format 2_0 by *positionInDCI*

\- a set of slot format combinations by *slotFormatCombinations*, where
each slot format combination in the set of slot format combinations
includes

\- one or more slot formats indicated by a respective *slotFormats* for
the slot format combination, and

\- a mapping for the slot format combination provided by *slotFormats*
to a corresponding SFI-index field value in DCI format 2_0 provided by
*slotFormatCombinationId*

\- for unpaired spectrum operation, a reference SCS configuration
$\mu_{SFI}$ by *subcarrierSpacing* and, when a supplementary UL carrier
is configured for the serving cell, a reference SCS configuration
$\mu_{SFI,SUL}$ by *subcarrierSpacing2* for the supplementary UL carrier

\- for paired spectrum operation, a reference SCS configuration
$\mu_{SFI,DL}$ for a DL BWP by *subcarrierSpacing* and a reference SCS
configuration $\mu_{SFI,UL}$ for an UL BWP by *subcarrierSpacing2*

\- a location of an available RB set indicator field in DCI format 2_0,
by *availableRB-SetsPerCell*, where the field is

\- one bit, if *intraCellGuardBandsDL-List* for the serving cell
indicates no intra-cell guard-bands are configured, where a value of
\'1\' indicates that the serving cell is available for receptions, a
value of \'0\' indicates that the serving cell is not available for
receptions, and the serving cell remains available or unavailable for
reception until the end of the remaining channel occupancy duration; or,

\- a bitmap having a one-to-one mapping with the RB sets \[6, TS
38.214\] of the serving cell, if *intraCellGuardBandsDL-List* for the
serving cell indicates intra-cell guard-bands are configured or if
*intraCellGuardBandsDL-List* is not provided for the serving cell, where
the bitmap includes $N_{RB,set,DL}$ bits and $N_{RB,set,DL}$ is the
number of RB sets in the serving cell, a value of \'1\' indicates that
an RB set is available for receptions, a value of \'0\' indicates that
an RB set is not available for receptions, and a RB set remains
available or unavailable for receptions until the end of the remaining
channel occupancy duration

\- a location of a channel occupancy duration field in DCI format 2_0,
by *CO-DurationsPerCell*, where the field indicates a remaining channel
occupancy duration for the serving cell starting from a first symbol of
a slot where the UE detects the DCI format 2_0 by providing a value from
*co-DurationList*. The channel occupancy duration field includes
$\max\left\{ \left\lceil \log_{2}(COdurationListSize) \right\rceil,1 \right\}$
bits, where $COdurationListSize$ is the number of values provided by
*co-DurationList*. If *CO-DurationsPerCell* is not provided, the
remaining channel occupancy duration for the serving cell is a number of
slots, starting from the slot where the UE detects the DCI format 2_0,
that the SFI-index field value provides corresponding slot formats

\- a reference SCS configuration for *co-DurationList*, by
*subcarrierSpacing*

\- a location of a search space set group switching flag field in DCI
format 2_0, by *SearchSpaceSwitchTrigger*, where the field indicates a
group from two groups of search space sets for PDCCH monitoring for
scheduling for the serving cell or the set of serving cells, provided by
*CellGroupsForSwitching*, as described in clause 10.4.

If neither *CO-DurationsPerCell* nor *SlotFormatCombinationsPerCell* are
provided and if *channelAccessMode* = \"*semiStatic*\" is provided, the
procedures in this clause apply with assuming a channel occupancy time
defined in clause 4.3 of \[15, TS 37.213\] is the remaining channel
occupancy duration if a DL transmission burst(s) is detected within the
channel occupancy time.

A SFI-index field value in a DCI format 2_0 indicates to a UE a slot
format for each slot in a number of slots for each DL BWP or each UL BWP
starting from a slot where the UE detects the DCI format 2_0. The number
of slots is equal to or larger than a PDCCH monitoring periodicity for
DCI format 2_0. The SFI-index field includes
![](media/image171.wmf){width="1.8854166666666667in"
height="0.22916666666666666in"} bits where maxSFIindex is the maximum
value of the values provided by corresponding *slotFormatCombinationId*.
A slot format is identified by a corresponding format index as provided
in Table 11.1.1-1 where \'D\' denotes a downlink symbol, \'U\' denotes
an uplink symbol, and \'F\' denotes a flexible symbol.

If a PDCCH monitoring periodicity for DCI format 2_0, provided to a UE
for the search space set
![](media/image170.wmf){width="0.10416666666666667in"
height="0.19791666666666666in"} by *monitoringSlotPeriodicityAndOffset*,
is smaller than a duration of a slot format combination the UE obtains
at a PDCCH monitoring occasion for DCI format 2_0 by a corresponding
SFI-index field value, and the UE detects more than one DCI formats 2_0
indicating a slot format for a slot, the UE expects each of the more
than one DCI formats 2_0 to indicate a same format for the slot.

A UE does not expect to be configured to monitor PDCCH for DCI format
2_0 on a second serving cell that uses larger SCS than the serving cell.

Table 11.1.1-1: Slot formats for normal cyclic prefix

+------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Format** | **Symbol number in a slot**                                                                                                                             |
|            +----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
|            | **0**    | **1**    | **2**    | **3**    | **4**    | **5**    | **6**    | **7**    | **8**    | **9**    | **10**   | **11**   | **12**   | **13**   |
+:==========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+
| 0          | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 1          | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 2          | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 3          | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 4          | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 5          | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 6          | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 7          | D        | D        | D        | D        | D        | D        | D        | D        | D        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 8          | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 9          | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 10         | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 11         | F        | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 12         | F        | F        | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 13         | F        | F        | F        | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 14         | F        | F        | F        | F        | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 15         | F        | F        | F        | F        | F        | F        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 16         | D        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 17         | D        | D        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 18         | D        | D        | D        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 19         | D        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 20         | D        | D        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 21         | D        | D        | D        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 22         | D        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 23         | D        | D        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 24         | D        | D        | D        | F        | F        | F        | F        | F        | F        | F        | F        | F        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 25         | D        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 26         | D        | D        | F        | F        | F        | F        | F        | F        | F        | F        | F        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 27         | D        | D        | D        | F        | F        | F        | F        | F        | F        | F        | F        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 28         | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | F        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 29         | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | F        | F        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 30         | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | F        | F        | F        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 31         | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | F        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 32         | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | F        | F        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 33         | D        | D        | D        | D        | D        | D        | D        | D        | D        | F        | F        | F        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 34         | D        | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 35         | D        | D        | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 36         | D        | D        | D        | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 37         | D        | F        | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 38         | D        | D        | F        | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 39         | D        | D        | D        | F        | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 40         | D        | F        | F        | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 41         | D        | D        | F        | F        | F        | U        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 42         | D        | D        | D        | F        | F        | F        | U        | U        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 43         | D        | D        | D        | D        | D        | D        | D        | D        | D        | F        | F        | F        | F        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 44         | D        | D        | D        | D        | D        | D        | F        | F        | F        | F        | F        | F        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 45         | D        | D        | D        | D        | D        | D        | F        | F        | U        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 46         | D        | D        | D        | D        | D        | F        | U        | D        | D        | D        | D        | D        | F        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 47         | D        | D        | F        | U        | U        | U        | U        | D        | D        | F        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 48         | D        | F        | U        | U        | U        | U        | U        | D        | F        | U        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 49         | D        | D        | D        | D        | F        | F        | U        | D        | D        | D        | D        | F        | F        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 50         | D        | D        | F        | F        | U        | U        | U        | D        | D        | F        | F        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 51         | D        | F        | F        | U        | U        | U        | U        | D        | F        | F        | U        | U        | U        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 52         | D        | F        | F        | F        | F        | F        | U        | D        | F        | F        | F        | F        | F        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 53         | D        | D        | F        | F        | F        | F        | U        | D        | D        | F        | F        | F        | F        | U        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 54         | F        | F        | F        | F        | F        | F        | F        | D        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 55         | D        | D        | F        | F        | F        | U        | U        | U        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 56 -- 254  | Reserved                                                                                                                                                |
+------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
| 255        | UE determines the slot format for the slot based on *tdd-UL-DL-ConfigurationCommon*, or *tdd-UL-DL-ConfigurationDedicated* and, if any, on detected DCI |
|            | formats                                                                                                                                                 |
+------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+

For unpaired spectrum operation for a UE on a serving cell, the UE is
provided by *subcarrierSpacing* a reference SCS configuration
$\mu_{SFI}$ for each slot format in a combination of slot formats
indicated by an SFI-index field value in DCI format 2_0. The UE expects
that for a reference SCS configuration $\mu_{SFI}$ and for an active DL
BWP or an active UL BWP with SCS configuration $\mu$, it is
$\mu \geq \mu_{SFI}$. Each slot format in the combination of slot
formats indicated by the SFI-index field value in DCI format 2_0 is
applicable to $2^{\left( \mu - \mu_{SFI} \right)}$ consecutive slots in
the active DL BWP or the active UL BWP where the first slot starts at a
same time as a first slot for the reference SCS configuration
$\mu_{SFI}$ and each downlink or flexible or uplink symbol for the
reference SCS configuration $\mu_{SFI}$ corresponds to
![](media/image172.wmf){width="0.5in"
height="0.19791666666666666in"} consecutive downlink or flexible or
uplink symbols for the SCS configuration $\mu$.

For paired spectrum operation for a UE on a serving cell, the SFI-index
field in DCI format 2_0 indicates a combination of slot formats that
includes a combination of slot formats for a reference DL BWP and a
combination of slot formats for a reference UL BWP of the serving cell.
The UE is provided by *subcarrierSpacing* a reference SCS configuration
$\mu_{SFI,DL}$ for the combination of slot formats indicated by the
SFI-index field value in DCI format 2_0 for the reference DL BWP of the
serving cell. The UE is provided by *subcarrierSpacing2* a reference SCS
configuration $\mu_{SFI,UL}$ for the combination of slot formats
indicated by the SFI-index field value in DCI format 2_0 for the
reference UL BWP of the serving cell. If
$\mu_{SFI,DL} \geq \mu_{SFI,UL}$ and for each
$2^{\left( \mu_{SFI,DL} - \mu_{SFI,UL} \right)} + 1$ values provided by
a value of *slotFormats*, where the value of *slotFormats* is determined
by a value of *slotFormatCombinationId* in *slotFormatCombination* and
the value of *slotFormatCombinationId* is set by the value of the
SFI-index field value in DCI format 2_0, the first
$2^{\left( \mu_{SFI,DL} - \mu_{SFI,UL} \right)}$ values for the
combination of slot formats are applicable to the reference DL BWP and
the next value is applicable to the reference UL BWP. If
$\mu_{SFI,DL} < \mu_{SFI,UL}$ and for each
$2^{\left( \mu_{SFI,UL} - \mu_{SFI,DL} \right)} + 1$ values provided by
*slotFormats*, the first value for the combination of slot formats is
applicable to the reference DL BWP and the next
$2^{\left( \mu_{SFI,UL} - \mu_{SFI,DL} \right)}$ values are applicable
to the reference UL BWP.

The UE is provided a reference SCS configuration $\mu_{SFI,DL}$ so that
for an active DL BWP with SCS configuration $\mu_{DL}$, it is
$\mu_{DL} \geq \mu_{SFI,DL}$. The UE is provided a reference SCS
configuration $\mu_{SFI,UL}$ so that for an active UL BWP with SCS
configuration $\mu_{UL}$, it is $\mu_{UL} \geq \mu_{SFI,UL}$. Each slot
format for a combination of slot formats indicated by the SFI-index
field value in DCI format 2_0 for the reference DL BWP, by indicating a
value for *slotFormatCombinationId* that is mapped to a value of
*slotFormats* in *slotFormatCombination*, is applicable to
$2^{\left( \mu_{DL} - \mu_{SFI,DL} \right)}$ consecutive slots for the
active DL BWP where the first slot starts at a same time as a first slot
in the reference DL BWP and each downlink or flexible symbol for the
reference SCS configuration $\mu_{SFI,DL}$ corresponds to
$2^{\left( \mu_{DL} - \mu_{SFI,DL} \right)}$ consecutive downlink or
flexible symbols for the SCS configuration $\mu_{DL}$. Each slot format
for the combination of slot formats for the reference UL BWP is
applicable to $2^{\left( \mu_{UL} - \mu_{SFI,UL} \right)}$ consecutive
slots for the active UL BWP where the first slot starts at a same time
as a first slot in the reference UL BWP and each uplink or flexible
symbol for the reference SCS configuration $\mu_{SFI,UL}$ corresponds to
$2^{\left( \mu_{UL} - \mu_{SFI,UL} \right)}$ consecutive uplink or
flexible symbols for the SCS configuration $\mu_{UL}$.

For unpaired spectrum operation with a second UL carrier for a UE on a
serving cell, the SFI-index field value in DCI format 2_0 indicates a
combination of slot formats that includes a combination of slot formats
for a reference first UL carrier of the serving cell and a combination
of slot formats for a reference second UL carrier of the serving cell.
The UE is provided by *subcarrierSpacing* a reference SCS configuration
$\mu_{SFI}$ for the combination of slot formats indicated by the
SFI-index field in DCI format 2_0 for the reference first UL carrier of
the serving cell. The UE is provided by *subcarrierSpacing2* a reference
SCS configuration $\mu_{SFI,SUL}$ for the combination of slot formats
indicated by the SFI-index field value in DCI format 2_0 for the
reference second UL carrier of the serving cell. For each
$2^{\left( \mu_{SFI} - \mu_{SFI,SUL} \right)} + 1$ values of
*slotFormats*, the first $2^{\left( \mu_{SFI} - \mu_{SFI,SUL} \right)}$
values for the combination of slot formats are applicable to the
reference first UL carrier and the next value is applicable to the
reference second UL carrier.

The UE expects to be provided a reference SCS configuration
$\mu_{SFI,SUL}$ so that for an active UL BWP in the second UL carrier
with SCS configuration $\mu_{SUL}$, it is
$\mu_{SUL} \geq \mu_{SFI,SUL}$. Each slot format for a combination of
slot formats indicated by the SFI-index field in DCI format 2_0 for the
reference first UL carrier is applicable to
$2^{\left( \mu - \mu_{SFI} \right)}$ consecutive slots for the active DL
BWP and the active UL BWP in the first UL carrier where the first slot
starts at a same time as a first slot in the reference first UL carrier.
Each slot format for the combination of slot formats for the reference
second UL carrier is applicable to
$2^{\left( \mu_{SUL} - \mu_{SFI,SUL} \right)}$ consecutive slots for the
active UL BWP in the second UL carrier where the first slot starts at a
same time as a first slot in the reference second UL carrier.

If a BWP in the serving cell is configured with $\mu = 2$ and with
extended CP, the UE expects $\mu_{SFI} = 0$, $\mu_{SFI} = 1$, or
$\mu_{SFI} = 2$. A format for a slot with extended CP is determined from
a format for a slot with normal CP. A UE determines an extended CP
symbol to be a downlink/uplink/flexible symbol if the overlapping normal
CP symbols that are downlink/uplink/flexible symbols, respectively. A UE
determines an extended CP symbol to be a flexible symbol if one of the
overlapping normal CP symbols is flexible. A UE determines an extended
CP symbol to be a flexible symbol if the pair of the overlapping normal
CP symbols includes a downlink and an uplink symbol.

A reference SCS configuration $\mu_{SFI}$, or $\mu_{SFI,DL}$, or
$\mu_{SFI,UL}$, or $\mu_{SFI,SUL}$ is either 0, or 1, or 2 for FR1 and
is either 2 or 3 for FR2.

For a set of symbols of a slot, a UE does not expect to detect a DCI
format 2_0 with an SFI-index field value indicating the set of symbols
of the slot as uplink and to detect a DCI format indicating to the UE to
receive PDSCH or CSI-RS in the set of symbols of the slot.

For a set of symbols of a slot, a UE does not expect to detect a DCI
format 2_0 with an SFI-index field value indicating the set of symbols
in the slot as downlink and to detect a DCI format, a RAR UL grant,
fallbackRAR UL grant, or successRAR indicating to the UE to transmit
PUSCH, PUCCH, PRACH, or SRS in the set of symbols of the slot.

For a set of symbols of a slot that are indicated by a DCI format 2_0 as
being within a remaining channel occupancy duration either by a channel
occupancy duration field or by an SFI-index field, a UE does not expect
to detect at a later time a DCI format 2_0 indicating, either by a
channel occupancy duration field or by an SFI-index field, that any
symbol from the set of symbols is not within a remaining channel
occupancy duration.

For a set of symbols of a slot that are indicated as downlink/uplink by
*tdd-UL-DL-ConfigurationCommon*, or *tdd-UL-DL-ConfigurationDedicated*,
the UE does not expect to detect a DCI format 2_0 with an SFI-index
field value indicating the set of symbols of the slot as
uplink/downlink, respectively, or as flexible.

For a set of symbols of a slot corresponding to SS/PBCH blocks with
candidate SS/PBCH block indices corresponding to the SS/PBCH block
indexes indicated to a UE by *ssb-PositionsInBurst* in *SIB1,* or by
*ssb-PositionsInBurst* in *ServingCellConfigCommon*, as described in
clause 4.1, or by *NonCellDefiningSSB* or, if the UE is not provided
*dl-OrJointTCI-StateList*, by *ssb-PositionsInBurst* in
*SSB-MTCAdditionalPCI* associated to physical cell ID with active TCI
states for PDCCH or PDSCH, or for a set of symbols of a slot
corresponding to SS/PBCH blocks configured for L1 beam
measurement/reporting, the UE does not expect to detect a DCI format 2_0
with an SFI-index field value indicating the set of symbols of the slot
as uplink.

For a set of symbols of a slot corresponding to a valid PRACH occasion
and $N_{gap}$ symbols before the valid PRACH occasion, as described in
clause 8.1, the UE does not expect to detect a DCI format 2_0 with an
SFI-index field value indicating the set of symbols of the slot as
downlink.

For a set of symbols of a slot indicated to a UE by *pdcch-ConfigSIB1*
in *MIB* for a CORESET for Type0-PDCCH CSS set, the UE does not expect
to detect a DCI format 2_0 with an SFI-index field value indicating the
set of symbols of the slot as uplink.

For a set of symbols of a slot indicated to a UE as flexible by
*tdd-UL-DL-ConfigurationCommon* and *tdd-UL-DL-ConfigurationDedicated*
if provided, or when *tdd-UL-DL-ConfigurationCommon* and
*tdd-UL-DL-ConfigurationDedicated* are not provided to the UE, and if
the UE detects a DCI format 2_0 providing a format for the slot using a
slot format value other than 255

\- if one or more symbols from the set of symbols are symbols in a
CORESET configured to the UE for PDCCH monitoring, the UE receives PDCCH
in the CORESET only if an SFI-index field value in DCI format 2_0
indicates that the one or more symbols are downlink symbols

\- if an SFI-index field value in DCI format 2_0 indicates the set of
symbols of the slot as flexible and the UE detects a DCI format
indicating to the UE to receive PDSCH or CSI-RS in the set of symbols of
the slot, the UE receives PDSCH or CSI-RS in the set of symbols of the
slot

\- if an SFI-index field value in DCI format 2_0 indicates the set of
symbols of the slot as flexible and the UE detects a DCI format, a RAR
UL grant, fallbackRAR UL grant, or successRAR indicating to the UE to
transmit PUSCH, PUCCH, PRACH, or SRS in the set of symbols of the slot
the UE transmits the PUSCH, PUCCH, PRACH, or SRS in the set of symbols
of the slot

\- if an SFI-index field value in DCI format 2_0 indicates the set of
symbols of the slot as flexible, and the UE does not detect a DCI format
indicating to the UE to receive PDSCH or CSI-RS, or the UE does not
detect a DCI format, a RAR UL grant, fallbackRAR UL grant, or successRAR
indicating to the UE to transmit PUSCH, PUCCH, PRACH, or SRS in the set
of symbols of the slot, the UE does not transmit or receive in the set
of symbols of the slot

\- if the UE is configured by higher layers to receive PDSCH or CSI-RS
in the set of symbols of the slot, the UE receives the PDSCH or the
CSI-RS in the set of symbols of the slot only if an SFI-index field
value in DCI format 2_0 indicates the set of symbols of the slot as
downlink and, if applicable, the set of symbols is within remaining
channel occupancy duration

\- if the UE is configured by higher layers to receive DL PRS in the set
of symbols of the slot, the UE receives the DL PRS in the set of symbols
of the slot only if an SFI-index field value in DCI format 2_0 indicates
the set of symbols of the slot as downlink or flexible.

\- if the UE is configured by higher layers to transmit PUCCH, or PUSCH,
or PRACH in the set of symbols of the slot, the UE transmits the PUCCH,
or the PUSCH, or the PRACH in the slot only if an SFI-index field value
in DCI format 2_0 indicates the set of symbols of the slot as uplink

\- if the UE is configured by higher layers to transmit SRS in the set
of symbols of the slot, the UE transmits the SRS only in a subset of
symbols from the set of symbols of the slot indicated as uplink symbols
by an SFI-index field value in DCI format 2_0

\- a UE does not expect to detect an SFI-index field value in DCI format
2_0 indicating the set of symbols of the slot as downlink and also
detect a DCI format, a RAR UL grant, fallbackRAR UL grant, or successRAR
indicating to the UE to transmit SRS, PUSCH, PUCCH, or PRACH, in one or
more symbols from the set of symbols of the slot

\- a UE does not expect to detect an SFI-index field value in DCI format
2_0 indicating the set of symbols of the slot as downlink or flexible if
the set of symbols of the slot includes symbols corresponding to any
repetition of a PUSCH transmission activated by an UL Type 2 grant PDCCH
as described in clause 10.2

\- a UE does not expect to detect an SFI-index field value in DCI format
2_0 indicating the set of symbols of the slot as uplink and also detect
a DCI format indicating to the UE to receive PDSCH or CSI-RS in one or
more symbols from the set of symbols of the slot

If a UE is configured by higher layers to receive a CSI-RS or a PDSCH in
a set of symbols of a slot and the UE detects a DCI format 2_0 with a
slot format value other than 255 that indicates a slot format with a
subset of symbols from the set of symbols as uplink or flexible, or the
UE detects a DCI format indicating to the UE to transmit PUSCH, PUCCH,
SRS, or PRACH in at least one symbol in the set of the symbols, the UE
cancels the CSI-RS reception in the set of symbols of the slot or
cancels the PDSCH reception in the slot.

For a UE operation with shared spectrum channel access in FR1, or in
FR2-2 when the UE is provided *ChannelAccessMode2* = \'*enabled*\', if a
UE is configured by higher layers to receive a CSI-RS and the UE is
provided *CO-DurationsPerCell*, for a set of symbols of a slot that are
indicated as downlink or flexible by *tdd-UL-DL-ConfigurationCommon* or
*tdd*-*UL-DL-ConfigurationDedicated*, or when
*tdd-UL-DL-ConfigurationCommon* and *tdd*-*UL-DL-ConfigurationDedicated*
are not provided, the UE cancels the CSI-RS reception in the set of
symbols of the slot that are not within the remaining channel occupancy
duration.

If a UE is configured by higher layers to receive a DL PRS in a set of
symbols of a slot and the UE detects a DCI format 2_0 with a slot format
value other than 255 that indicates a slot format with a subset of
symbols from the set of symbols as uplink, or the UE detects a DCI
format indicating to the UE to transmit PUSCH, PUCCH, SRS, or PRACH in
at least one symbol in the set of the symbols, the UE cancels the DL PRS
reception in the set of symbols of the slot.

If a UE is configured by higher layers to transmit SRS, or PUCCH, or
PUSCH, or PRACH in a set of symbols of a slot and the UE detects a DCI
format 2_0 with a slot format value other than 255 that indicates a slot
format with a subset of symbols from the set of symbols as downlink or
flexible, or the UE detects a DCI format indicating to the UE to receive
CSI-RS or PDSCH in a subset of symbols from the set of symbols, then

> \- If the UE does not indicate the capability of
> *partialCancellationPUCCH-PUSCH-PRACH-TX*, the UE does not expect to
> cancel the transmission of the PUCCH or PUSCH or PRACH in the set of
> symbols if the first symbol in the set occurs within $T_{proc,2}$
> relative to a last symbol of a PDCCH reception where the UE detects
> the DCI format; otherwise, the UE cancels the PUCCH, or the PUSCH, or
> an actual repetition of the PUSCH \[6, TS 38.214\], determined from
> clauses 9, 9.2.5 and 9.2.6 or clause 6.1 of \[6, TS 38.214\], or the
> PRACH transmission in the set of symbols.

\- If the UE indicates the capability of
*partialCancellationPUCCH-PUSCH-PRACH-TX*, the UE does not expect to
cancel the transmission of the PUCCH or PUSCH or PRACH in symbols from
the set of symbols that occur within $T_{proc,2}$ relative to a last
symbol of a PDCCH reception where the UE detects the DCI format. The UE
cancels the PUCCH, or the PUSCH, or an actual repetition of the PUSCH
\[6, TS 38.214\], determined from clauses 9, 9.2.5 and 9.2.6 or clause
6.1 of \[6, TS 38.214\], or the PRACH transmission in remaining symbols
from the set of symbols.

\- The UE does not expect to cancel the transmission of SRS in symbols
from the subset of symbols that occur within $T_{proc,2}$ relative to a
last symbol of a PDCCH reception where the UE detects the DCI format.
The UE cancels the SRS transmission in remaining symbols from the subset
of symbols.

$T_{proc,2}$ is the PUSCH preparation time for the corresponding UE
processing capability \[6, TS 38.214\] assuming $d_{2,1} = 1$ and $\mu$
corresponds to the smallest SCS configuration between the SCS
configuration of the PDCCH carrying the DCI format and the SCS
configuration of the SRS, PUCCH, PUSCH or $\mu_{r}$, where $\mu_{r}$
corresponds to the SCS configuration of the PRACH if it is 15kHz or
higher; otherwise $\mu_{r} = 0$.

If a UE is configured by higher layers to receive a CSI-RS or detects a
DCI format 0_1 indicating to the UE to receive a CSI-RS in one or more
RB sets and a set of symbols of a slot, and the UE detects a DCI format
2_0 with bitmap indicating that any RB set from the one or more RB sets
is not available for reception, the UE cancels the CSI-RS reception in
the set of symbols of the slot.

A UE assumes that flexible symbols in a CORESET configured to the UE for
PDCCH monitoring are downlink symbols if the UE does not detect an
SFI-index field value in DCI format 2_0 indicating the set of symbols of
the slot as flexible or uplink and the UE does not detect a DCI format
indicating to the UE to transmit SRS, PUSCH, PUCCH, or PRACH in the set
of symbols.

For a set of symbols of a slot that are indicated as flexible by
*tdd-UL-DL-ConfigurationCommon*, and *tdd-UL-DL-ConfigurationDedicated*
if provided, or when *tdd-UL-DL-ConfigurationCommon*, and
*tdd-UL-DL-ConfigurationDedicated* are not provided to the UE, and if
the UE does not detect a DCI format 2_0 providing a slot format for the
slot

\- the UE receives PDSCH or CSI-RS in the set of symbols of the slot if
the UE receives a corresponding indication by a DCI format

\- the UE transmits PUSCH, PUCCH, PRACH, or SRS in the set of symbols of
the slot if the UE receives a corresponding indication by a DCI format,
a RAR UL grant, fallbackRAR UL grant, or successRAR

\- the UE receives PDCCH as described in clause 10.1

\- if the UE is configured by higher layers to receive PDSCH in the set
of symbols of the slot, the UE does not receive the PDSCH in the set of
symbols of the slot

\- if the UE is configured by higher layers to receive CSI-RS in the set
of symbols of the slot, the UE does not receive the CSI-RS in the set of
symbols of the slot, except when UE is provided *CO-DurationsPerCell*
and the set of symbols of the slot are within the remaining channel
occupancy duration.

\- if the UE is configured by higher layers to receive DL PRS in the set
of symbols of the slot, the UE receives the DL PRS

\- if the UE is configured by higher layers to transmit SRS, or PUCCH,
or PUSCH, or PRACH in the set of symbols of the slot and the UE is not
provided *enableConfiguredUL*, then

\- if the UE does not indicate the capability of
*partialCancellationPUCCH-PUSCH-PRACH-TX*, the UE does not expect to
cancel the transmission of the PUCCH, or the PUSCH, or an actual
repetition of the PUSCH \[6, TS 38.214\], as determined in clauses 9,
9.2.5 and 9.2.6 or in clause 6.1 of \[6. TS 38.214\], or the PRACH in
the slot if the first symbol of the PUCCH or the PUSCH or actual
repetition of the PUSCH or the PRACH in the slot occurs within
$T_{proc,2}$ relative to a last symbol of a PDCCH reception where the UE
is configured to monitor PDCCH for DCI format 2_0; otherwise, the UE
cancels the PUCCH, or the PUSCH, or an actual repetition of the PUSCH
\[6, TS 38.214\], as determined in clauses 9, 9.2.5 and 9.2.6 or in
clause 6.1 of \[6. TS 38.214\], or the PRACH in the slot;

\- if the UE indicates the capability of
*partialCancellationPUCCH-PUSCH-PRACH-TX*, the UE does not expect to
cancel the transmission of the PUCCH, or the PUSCH, or an actual
repetition of the PUSCH \[6, TS 38.214\], as determined in clauses 9,
9.2.5 and 9.2.6 or in clause 6.1 of \[6. TS 38.214\], or the PRACH in
symbols from the set of symbols that occur within $T_{proc,2}$ relative
to a last symbol of a PDCCH reception where the UE is configured to
monitor PDCCH for DCI format 2_0. The UE cancels the PUCCH, or the
PUSCH, or an actual repetition of the PUSCH \[6, TS 38.214\], as
determined in clauses 9, 9.2.5 and 9.2.6 or in clause 6.1 of \[6. TS
38.214\], or the PRACH transmission in remaining symbols from the set of
symbols;

\- the UE does not expect to cancel the transmission of SRS in symbols
from the set of symbols that occur within $T_{proc,2}\ $relative to a
last symbol of a PDCCH reception where the UE is configured to monitor
PDCCH for DCI format 2_0. The UE cancels the SRS transmission
in remaining symbols from the set of symbols;

\- $T_{proc,2}$ is the PUSCH preparation time for the corresponding UE
processing capability \[6, TS 38.214\] assuming $d_{2,1} = 1$ and $\mu$
corresponds to the smallest SCS configuration between the SCS
configuration of the PDCCH carrying the DCI format 2_0 and the SCS
configuration of the SRS, PUCCH, PUSCH or $\mu_{r}$, where $\mu_{r}$
corresponds to the SCS configuration of the PRACH if it is 15kHz or
higher; otherwise $\mu_{r} = 0$;

\- if the UE is configured by higher layers to transmit SRS, or PUCCH,
or PUSCH, or PRACH in the set of symbols of the slot and the UE is
provided *enableConfiguredUL*, the UE can transmit the SRS, or PUCCH, or
PUSCH, or PRACH, respectively.

For unpaired spectrum operation for a UE on a cell in a frequency band
of FR1, and when the scheduling restrictions due to RRM measurements
\[10, TS 38.133\] are not applicable, if the UE detects a DCI format
indicating to the UE to transmit in a set of symbols, the UE is not
required to perform RRM measurements \[10, TS 38.133\] based on a
SS/PBCH block or CSI-RS reception on a different cell in the frequency
band if the SS/PBCH block or CSI-RS reception includes at least one
symbol from the set of symbols.