# 14 Integrated access-backhaul operation

Throughout this specification, unless otherwise noted, statements using
the term \"UE\" in clauses 4 through 13 are equally applicable to the
IAB-MT of an IAB node.

A procedure for an IAB-MT to perform cell search, system information
acquisition, or random access procedure is same as a corresponding one
for a UE except for the following.

For initial cell selection, an IAB-MT may assume that half frames with
SS/PBCH blocks occur with a periodicity of 16 frames.

For PRACH transmission, an IAB-MT determines frames and subframes/slots
within the frames containing PRACH occasions as described in \[4, TS
38.211\].

The IAB-MT determines an association period for mapping SS/PBCH blocks
to PRACH occasions based on a PRACH configuration period as described in
clause 8.1 and according to Table 14-1 instead of Table 8.1-1. An
association pattern period includes one or more association periods and
is determined so that a pattern between PRACH occasions and SS/PBCH
blocks repeats at most every 640 msec. A PRACH occasion in a PRACH slot
is valid according to the conditions in clause 8.1.

Table 14-1: Mapping between PRACH configuration period and SS/PBCH block
to PRACH occasion association period for an IAB-MT

  -----------------------------------------------------------------------
  PRACH configuration period (msec) Association period (number of PRACH
                                    configuration periods)
  --------------------------------- -------------------------------------
  10                                {1, 2, 4, 8, 16, 32, 64}

  20                                {1, 2, 4, 8, 16, 32}

  40                                {1, 2, 4, 8, 16}

  80                                {1, 2, 4, 8}

  160                               {1, 2, 4}

  320                               {1, 2}

  640                               {1}
  -----------------------------------------------------------------------

If an IAB-node is provided an index $T_{\text{delta}}$ in a Timing Delta
MAC CE \[11, TS 38.321\] from a serving cell, the IAB-node may assume
that
$T_{\text{TA}}/2 + \left( N_{\text{delta}} + T_{\text{delta}} \cdot G_{\text{step}}{- N}_{\text{TA,Offset}}/2 \right) \cdot T_{\text{c}}$
is a time difference between a DU transmission of a signal from the
serving cell and a reception of the signal by the IAB-MT when
$T_{\text{TA}}/2 + \left( N_{\text{delta}} + T_{\text{delta}} \cdot G_{\text{step}}{- N}_{\text{TA,Offset}}/2 \right) \cdot T_{\text{c}} > 0$,
where

\- $T_{\text{TA}}$ is the difference between the IAB-MT reception time
and the IAB-MT transmission time for IAB-MT transmission timing mode
\'Case-6\', and is defined in clause 4.3.1 of \[4, TS 38.211\] for
IAB-MT transmission timing mode \'Case-1\' and parent node reception
mode \'Case-7\'

\- $N_{\text{delta}}$ and $G_{\text{step}}$ are determined as

\- $N_{\text{delta}} = - 70528$ and $G_{step} = 64$, if the serving cell
providing the Timing Delta MAC CE operates in FR1

\- $N_{\text{delta}} = - 17664$ and $G_{step} = 32$, if the serving cell
providing the Timing Delta MAC CE operates in FR2

The IAB node may assume that a same value of index $T_{\text{delta}}$ is
provided from a serving cell for the IAB-MT transmission timing modes
\'Case-7\' and \'Case-1\'

The IAB-node may use the time difference to determine a DU transmission
time.

For a serving cell of an IAB-MT, the IAB-MT can be provided by Timing
Case Indication MAC CE \[11, TS 38.321\] an indication of the IAB-MT
transmission timing mode in a slot. Upon reception of the Timing Case
Indication for a serving cell in a TAG, the IAB-MT applies a same IAB-MT
transmission timing mode in a slot on all serving cells in the TAG.

If the indicated IAB-MT transmission timing mode in a slot is set to
\'Case-1\' or the IAB-MT transmission timing mode indication in a slot
is not provided, the IAB-MT transmission time is determined as for a
\"UE\" in clause 4.2.

If the indicated IAB-MT transmission timing mode in a slot is set to
\'Case-6\', the IAB-node sets the IAB-MT transmission time to the
transmission time of the IAB-DU.

If the indicated IAB-MT transmission timing mode in a slot is set to
\'Case-7\', the IAB-MT is provided a timing advance offset value
$N_{TA,offset,2}$ for a serving cell by Case-7 Timing advance offset MAC
CE \[11, TS 38.321\]. The IAB-MT determines its uplink transmission
timing as T~TA~ + N~TA,offset,2~ ·T~c~ where $T_{\text{TA}}$ is defined
in clause 4.3.1 of \[4, TS 38.211\] and
$N_{TA,offset,2} = T_{offset,2} \cdot 16 \cdot \frac{64}{2^{\mu}}$ where
$T_{offset,2}$ is provided by the Case-7 Timing advance offset MAC CE
\[11, TS 38.321\].

A slot format for an IAB-DU or an IAB-MT includes downlink symbols,
uplink symbols, and flexible symbols.

For each cell of an IAB-DU, the IAB-DU can be provided an indication for
a slot format over a number of slots by *gNB-DU Cell Resource
Configuration* \[16, TS 38.473\].

For each serving cell, an IAB-MT can be provided an indication for a
slot format over a number of slots by
*tdd-UL-DL-ConfigurationDedicated-IAB-MT*. If the IAB-MT is provided
*tdd-UL-DL-ConfigurationDedicated-IAB-MT*, the statements in clause 11.1
that include \"*tdd-UL-DL-ConfigurationDedicated*\" apply to the IAB-MT
of an IAB node by replacing \"*tdd-UL-DL-ConfigurationDedicated*\" with
\"*tdd-UL-DL-ConfigurationDedicated-IAB-MT*\" for the IAB-MT, except
that the *tdd-UL-DL-ConfigurationDedicated-IAB-MT* provides

\- a set of slot configurations by
*slotSpecificConfigurationsToAddModList-IAB-MT*

\- for each slot configuration from the set of slot configurations

\- a slot index for a slot provided by *slotIndex*

\- a set of symbols for a slot by *symbols-IAB-MT* where

\- if *symbols-IAB-MT* = *allDownlink*, all symbols in the slot are
downlink

\- if *symbols-IAB-MT* = *allUplink*, all symbols in the slot are uplink

\- if *symbols-IAB-MT* = *explicit*, *nrofDownlinkSymbols* provides a
number of downlink first symbols in the slot and *nrofUplinkSymbols*
provides a number of uplink last symbols in the slot. If
*nrofDownlinkSymbols* is not provided, there are no downlink first
symbols in the slot and if *nrofUplinkSymbols* is not provided, there
are no uplink last symbols in the slot. The remaining symbols in the
slot are flexible.

\- if *symbols-IAB-MT* = *explicit-IAB-MT*, *nrofUplinkSymbols* provides
a number of uplink first symbols in the slot and *nrofDownlinkSymbols*
provides a number of downlink last symbols in the slot. If
*nrofUplinkSymbols* is not provided, there are no uplink first symbols
in the slot and if *nrofDownlinkSymbols* is not provided, there are no
downlink last symbols in the slot. The remaining symbols in the slot are
flexible.

If an IAB-MT is configured with an MCG and an SCG, is not capable of
simultaneous transmission and reception, and would simultaneously
transmit and receive on the MCG and the SCG,

\- if flexible symbols are configured by both parent nodes for operation
with inter-donor NR-DC, the IAB-MT operates according to the scheduling
from the MCG

\- otherwise, if the IAB-MT is configured with multiple serving cells,
is provided *directionalCollisionHandling-*r17 = \'enabled\' for a set
of serving cell(s) from the multiple serving cells, and indicates
*half-DuplexTDD-CA-SameSCS* capability across MCG and SCG for NR-DC
operation, the IAB-MT applies the procedures for resolving directional
collisions as described in clause 11.1 for resolving directional
collisions across serving cells.

An IAB-MT can be provided, by *SlotFormatCombinationsPerCell*, a list of
slot format combinations applicable for one serving cell and, by
*SlotFormatIndicator*, a configuration for monitor a DCI format 2_0
indicating a slot format combination, from the list of slot format
combinations, over a number of slots as described in clause 11.1.1. In
addition to the slot formats in Table 11.1.1-1, an SFI field for an
IAB-MT in DCI format 2_0 can indicate to the IAB-MT a slot format from
the slot formats in Table 14-2.

Table 14-2: Slot formats for normal cyclic prefix

+------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Slot**   | **Symbol number in a slot**                                                                                                                             |
|            |                                                                                                                                                         |
| **Format** |                                                                                                                                                         |
|            +----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
|            | **0**    | **1**    | **2**    | **3**    | **4**    | **5**    | **6**    | **7**    | **8**    | **9**    | **10**   | **11**   | **12**   | **13**   |
+:==========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+:========:+
| 56         | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 57         | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 58         | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 59         | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 60         | U        | U        | U        | U        | U        | U        | U        | U        | U        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 61         | U        | U        | U        | U        | U        | U        | U        | U        | F        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 62         | U        | U        | U        | U        | U        | U        | U        | F        | F        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 63         | U        | U        | U        | U        | U        | U        | F        | F        | F        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 64         | U        | U        | U        | U        | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 65         | U        | U        | U        | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 66         | U        | U        | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 67         | U        | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 68         | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 69         | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 70         | U        | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 71         | U        | U        | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 72         | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 73         | U        | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 74         | U        | U        | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 75         | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        | F        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 76         | U        | U        | F        | F        | F        | F        | F        | F        | F        | F        | F        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 77         | U        | U        | U        | F        | F        | F        | F        | F        | F        | F        | F        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 78         | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | F        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 79         | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | F        | F        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 80         | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | F        | F        | F        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 81         | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | F        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 82         | U        | U        | U        | U        | U        | U        | U        | U        | U        | U        | F        | F        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 83         | U        | U        | U        | U        | U        | U        | U        | U        | U        | F        | F        | F        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 84         | U        | F        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 85         | U        | U        | F        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 86         | U        | U        | U        | F        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 87         | U        | F        | F        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 88         | U        | U        | F        | F        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 89         | U        | U        | U        | F        | F        | D        | D        | D        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 90         | U        | F        | F        | F        | D        | D        | D        | D        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 91         | U        | U        | F        | F        | F        | D        | D        | D        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 92         | U        | U        | U        | F        | F        | F        | D        | D        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 93         | U        | U        | U        | U        | U        | U        | U        | U        | U        | F        | F        | F        | F        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 94         | U        | U        | U        | U        | U        | U        | F        | F        | F        | F        | F        | F        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 95         | U        | U        | U        | U        | U        | U        | F        | F        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+
| 96         | U        | U        | U        | U        | U        | U        | U        | D        | D        | D        | D        | D        | D        | D        |
+------------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+----------+

For a serving cell of an IAB-MT, the IAB-MT can be provided by Provided
Guard Symbols MAC CE, for Case-1, Case-6 and Case-7 timing modes,
respectively, a number of symbols that will not be used for the IAB-MT
in slots where the IAB-node transitions between IAB-MT and IAB-node DU
and a SCS configuration for the number of symbols \[11, TS 38.321\].

With reference to slots of an IAB-DU cell, a symbol in a slot of an
IAB-DU cell can be configured to be of hard, soft, or unavailable type
by *HSNA Slot Configuration List* in *gNB-DU Cell Resource
Configuration* \[16, TS 38.473\].

When a downlink, uplink, or flexible symbol is configured as hard, the
IAB-DU cell can respectively transmit, receive, or either transmit or
receive in the symbol. A symbol of a slot is equivalent to being
configured as hard if an IAB-DU would transmit a SS/PBCH block, PDCCH
for Type0-PDCCH CSS sets configured by *pdcchConfigSIB1*, or a periodic
CSI-RS in the symbol of the slot, or would receive a PRACH or a SR in
the symbol of the slot.

When a downlink, uplink, or flexible symbol is configured as soft, the
IAB-DU cell can respectively transmit, receive or either transmit or
receive in the symbol only if

\- the IAB-MT does not transmit or receive during the symbol of the
IAB-DU cell, or

\- with respect to all serving cells, the IAB-MT would transmit or
receive during the symbol of the IAB-DU cell, and the transmission or
reception during the symbol of the IAB-DU cell is not changed due to a
use of the symbol by the IAB-DU, or

\- the IAB-MT detects a DCI format 2_5 with an AI index field value
indicating the soft symbol as available if the IAB-MT is not configured
with an SCG, or

\- the IAB-MT detects two DCI formats 2_5 with an AI index field
indicating the soft symbol as available from the MCG and SCG,
respectively, or

\- the IAB-MT detects a DCI format 2_5 with an AI index field value
indicating the soft symbol as available from one cell group and with
respect to all serving cells of the other cell group

\- the IAB-MT does not transmit or receive during the symbol of the
IAB-DU cell, or

\- the IAB-MT would transmit or receive during the symbol of the IAB-DU
cell, and the transmission or reception during the symbol of the IAB-DU
cell does not change due to a use of the symbol by the IAB-DU.

When the IAB-MT receives a DCI format 2_5 from a serving cell in a cell
group, the IAB-MT applies the information of the DCI format 2_5 to all
serving cells of the cell group.

When a symbol is configured as unavailable, the IAB-DU neither transmits
nor receives in the symbol.

With reference to slots of an IAB-DU cell, the IAB-DU can be provided an
indication of hard, soft or unavailable type per RB set for symbols
configured as downlink, uplink or flexible in a slot by
*Frequency-Domain HSNA Configuration List* \[16, TS 38.473\]. The RB set
size and the number of RB sets are configured by *RB Set Configuration*
\[16, TS 38.473\]. The IAB-node can assume the RB set size for the
IAB-DU cell is larger than or equal to the IAB-MT\'s smallest RBG size
of the configured BWPs of the FDM required IAB-MT\'s serving cell(s) as
indicated in Multiplexing Info \[16, TS 38.473\] of the DU cell. If an
indication of hard, soft or unavailable type is not provided for an RB
set of a symbol in a slot, the IAB-DU applies the configuration of hard,
soft or unavailable type provided by *HSNA Slot Configuration List* in
*gNB-DU Cell Resource Configuration* \[16, TS 38.473\] for the RB set of
the symbol in the slot. If an indication of hard, soft, or unavailable
type is provided for an RB set in a symbol of a slot, the IAB-DU applies
the configuration of hard, soft, or unavailable type provided by
*Frequency-Domain HSNA Configuration List* \[16, TS 38.473\] unless the
symbol is configured as soft type in *HSNA Slot Configuration List* in
*gNB-DU Cell Resource Configuration* \[16, TS 38.473\] and the IAB-DU
cell can transmit or receive in the symbol.

When an RB set of a downlink, uplink, or flexible symbol is configured
as hard, the IAB-DU cell can respectively transmit, receive, or either
transmit or receive on the RB set in the symbol. An RB set of a symbol
is equivalent to being configured as hard if an IAB-DU would transmit a
SS/PBCH block, PDCCH for Type0-PDCCH CSS sets configured by
*pdcchConfigSIB1*, or a periodic CSI-RS in the RB set of the symbol, or
would receive a PRACH or a SR in the RB set of the symbol.

When an RB set of a downlink, uplink, or flexible symbol is configured
as soft, the IAB-DU cell can respectively transmit, receive or either
transmit or receive on the RB set in the symbol only if

\- the IAB-MT does not transmit or receive on the RB set during the
symbol of the IAB-DU cell, or

> \- with respect to all serving cells, the IAB-MT would transmit or
> receive on the RB set during the symbol of the IAB-DU cell, and the
> transmission or reception on the RB set or any RB set that is
> configured as unavailable or configured as soft and not indicated as
> available during the symbol of the IAB-DU cell is not changed due to a
> use of the RB set in the symbol by the IAB-DU, or
>
> \- the IAB-MT detects a DCI format 2_5 with an AI index field value
> indicating the soft RB set as available if the IAB-MT is not
> configured with an SCG, or
>
> \- the IAB-MT detects two DCI formats 2_5 with an AI index field value
> indicating the soft RB set as available from the MCG and SCG,
> respectively, or
>
> \- the IAB-MT detects a DCI format 2_5 with an AI index field value
> indicating the soft RB set as available from one cell group and with
> respect to all serving cells of the other cell group, the IAB-MT would
> transmit or receive on the RB set during the symbol of the IAB-DU
> cell, and the transmission or reception on the RB set during the
> symbol of the IAB-DU cell does not change due to a use of the RB set
> in the symbol by the IAB-DU.

When an RB set of a downlink, uplink, or flexible symbol is configured
as unavailable, the IAB-DU neither transmits nor receives in the RB set
in the symbol.

If an IAB-node is provided an *AvailabilityIndicator*, the IAB-node is
provided an AI-RNTI by *ai-RNTI* and a payload size of a DCI format 2_5
by *dci-PayloadSizeAI*. The IAB-node is also provided a search space set
configuration, by *SearchSpace*, for monitoring PDCCH.

For each cell of an IAB-DU in a set of cells of the IAB-DU, the IAB-DU
can be provided:

\- an identity of the IAB-DU cell by *iab-DU-CellIdentity*

\- a location of an availability indicator (AI) index field in DCI
format 2_5 by *positionInDCI-AI-r16* and/or by
*positionInDCI-AI-RBGroups-v1720*

\- a set of availability combinations by *availabilityCombinations-r16*
or by *availabilityCombinationsRB-Groups-r17*, where each availability
combination in the set of availability combinations includes

\- *resourceAvailability-r16* indicating availability of soft symbols in
one or more slots for the IAB-DU cell, or one *resourceAvailability-r17*
indicating availability of soft resources in all RB sets in one or more
slots for the IAB-DU cell, or one or multiple RB set groups by
*rb-SetGroups-r17* with each RB set groups by *RB-SetGroup-r17*
indicating *resourceAvailability-r17* for soft resources in one or more
slots for the associated *rb-Sets-r17*, and

\- a mapping for the soft symbol, and/or for soft resources,
availability combinations provided by *resourceAvailability-r16 or
resourceAvailability-r17* to a corresponding AI index field value in DCI
format 2_5 provided by *availabilityCombinationId-r16 or
availabilityCombinationId-r17, respectively*

With reference to a slot of an IAB-DU cell, if the IAB-DU is not
provided an indication of hard, soft or unavailable type per RB set by
*Frequency-Domain HSNA Configuration List* \[16, TS 38.473\], the
indication of availability for the slot is based solely on
*availabilityCombinations-r16*.

The IAB-DU can assume a same SCS configuration for
*availabilityCombinations-r16* or
*availabilityCombinationsRB-Groups-r17* for slots of a cell as an SCS
configuration provided by *gNB-DU Cell Resource Configuration* for the
cell.

The IAB-DU can assume a same SCS configuration for
*availabilityCombinationsRB-Groups-r17* for RB sets of a cell as a SCS
configuration provided by *RB Set Configuration* for the cell.

An AI index field value in a DCI format 2_5 indicates to an IAB-DU a
soft symbol and/or a soft RB set in an RB set group availability in each
slot for a number of slots starting from the earliest slot of the IAB-DU
which overlaps in time with the slot of the IAB-MT where the IAB-MT
detects the DCI format 2_5. The number of slots is equal to or larger
than a PDCCH monitoring periodicity for DCI format 2_5 as provided by
*SearchSpace*. The AI index field includes
$\max\left\{ \left\lceil \log_{2}(maxAIindex + 1) \right\rceil,1 \right\}$
bits where maxAIindex is the maximum of the values provided by
corresponding *availabilityCombinationId*. An availability for a soft
symbol or a soft RB set in an RB set group in a slot is identified by a
corresponding value *resourceAvailability* as provided in Table 14-3.

Table 14-3: Mapping between values of *resourceAvailability* elements
and types of soft symbol or soft RB set availability in a slot

+----------+-----------------------------------------------------------+
| Value    | Indication                                                |
+==========+===========================================================+
| 0        | No indication of availability for soft symbols or soft RB |
|          | sets in an RB set group                                   |
+----------+-----------------------------------------------------------+
| 1        | DL soft symbols or soft RB sets in an RB set group are    |
|          | indicated available                                       |
|          |                                                           |
|          | No indication of availability for UL and Flexible soft    |
|          | symbols or soft RB sets in an RB set group                |
+----------+-----------------------------------------------------------+
| 2        | UL soft symbols or soft RB sets in an RB set group are    |
|          | indicated available                                       |
|          |                                                           |
|          | No indication of availability for DL and Flexible soft    |
|          | symbols or soft RB sets in an RB set group                |
+----------+-----------------------------------------------------------+
| 3        | DL and UL soft symbols or soft RB sets in an RB set group |
|          | are indicated available                                   |
|          |                                                           |
|          | No indication of availability for Flexible soft symbols   |
|          | or soft RB sets in an RB set group                        |
+----------+-----------------------------------------------------------+
| 4        | Flexible soft symbols or soft RB sets in an RB set group  |
|          | are indicated available                                   |
|          |                                                           |
|          | No indication of availability for DL and UL soft symbols  |
|          | or soft RB sets in an RB set group                        |
+----------+-----------------------------------------------------------+
| 5        | DL and Flexible soft symbols or soft RB sets in an RB set |
|          | group are indicated available                             |
|          |                                                           |
|          | No indication of availability for UL soft symbols or soft |
|          | RB sets in an RB set group                                |
+----------+-----------------------------------------------------------+
| 6        | UL and Flexible soft symbols or soft RB sets in an RB set |
|          | group are indicated available                             |
|          |                                                           |
|          | No indication of availability for DL soft symbols or soft |
|          | RB sets in an RB set group                                |
+----------+-----------------------------------------------------------+
| 7        | DL, UL, and Flexible soft symbols or soft RB sets in an   |
|          | RB set group are indicated available                      |
+----------+-----------------------------------------------------------+

If a PDCCH monitoring periodicity for DCI format 2_5 is smaller than a
duration of an availability combination of soft symbols over a number of
slots that the IAB-MT obtains at a PDCCH monitoring occasion for DCI
format 2_5 by a corresponding AI index field value, and the IAB-MT
detects more than one DCI formats 2_5 indicating an availability
combination of soft symbols or of soft RB sets in RB set groups in a
slot, the IAB-MT expects that each of the more than one DCI formats 2_5
indicates a same value for the availability combination of the soft
symbols or of soft RB sets in an RB set group in the slot. An IAB-MT
monitors PDCCH candidates for a DCI format 2_5 with CRC scrambled by
AI-RNTI in one or both of the following search space sets:

\- a Type3-PDCCH CSS set configured by *SearchSpace* in *PDCCH-Config*
with *searchSpaceType* = *common*;

\- a USS set configured by SearchSpace in PDCCH-Config with
searchSpaceType = ue-Specific.

The IAB-node can be provided by the parent node a set of RS resource
indexes that indicate quasi co-location properties of an IAB-DU cell
where simultaneous transmission/reception from the IAB-MT and
transmission from the IAB-DU cells is restricted by Child IAB-DU
Restricted Beam Indication MAC CE as described in \[11, TS 38.321\]. The
IAB-DU does not transmit on a cell if the IAB node is operating in a
non-TDM multiplexing mode using an indicated RS resource index on a
symbol or RB set configured as soft in an IAB-DU cell

\- when it is not indicated as available by *resourceAvailability*

\- when the IAB-MT is operating on an associated carrier, if that
indication is provided

\- when the current IAB-DU transmission mode corresponds to an
associated multiplexing mode, if that indication is provided

\- when one of the associated TCI states, RS resource indexes, or SRI of
the IAB-MT, if provided, is simultaneously used for reception or
transmission of the IAB-MT

\- when simultaneous transmission/reception by the IAB-MT and
transmission from the IAB-DU cell occur in non-overlapping frequency
resources, if such indication is provided, or when simultaneous
transmission/reception by the IAB-MT and transmission from the IAB-DU
cell occur in overlapping frequency resources

\- in a given slot, if that indication is provided

For a serving cell of an IAB-MT, the IAB-MT can be provided a set of TCI
states or a set of RS resource indexes corresponding to a SS/PBCH block
or to a CSI-RS resource index for a slot where a PDSCH EPRE adjustment
is indicated by DL Tx Power Adjustment MAC CE as described in \[11, TS
38.321\]. The PDSCH EPRE can be derived from a downlink CSI-RS EPRE as
described in \[6, TS 38.214\] and a power offset provided by the *DL Tx
Power adjustment* field in *DL TX Power Adjustment* MAC CE as described
in \[11, TS 38.321\]. The downlink CSI-RS EPRE refers to the CSI-RS
indicated by Reference CSI-RS ID in *DL Tx Power Adjustment* MAC CE as
described in \[11, TS 38.321\]. The *DL TX Power Adjustment* provides
the offset between PDSCH EPRE and CSI-RS EPRE. For a downlink DM-RS
and/or PT-RS associated with a PDSCH, the IAB-MT may assume that the
ratio of PDSCH EPRE to DM-RS EPRE, and/or PT-RS EPRE to PDSCH EPRE, is
obtained as for a \"UE\" in \[6, TS 38.214\]. If no TCI state or RS
resource index is provided to the IAB-MT, the IAB-MT may assume that a
same PDSCH EPRE adjustment applies to all TCI states or RS resource
indexes configured for the IAB-MT. A PDSCH EPRE adjustment provided by
DL Tx Power Adjustment MAC CE may be associated with

\- multiplexing mode of the IAB-node, if provided, and/or

\- when simultaneous reception by the IAB-MT and transmission/reception
by an IAB-DU cell occur in non-overlapping frequency resources, if
provided, or when simultaneous reception by the IAB-MT and
transmission/reception by an IAB-DU cell occur in overlapping frequency
resources, if provided, and/or

\- slots indicated by slot indexes, if provided.