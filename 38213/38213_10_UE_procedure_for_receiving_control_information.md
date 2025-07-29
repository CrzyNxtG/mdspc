# 10 UE procedure for receiving control information

If the UE is configured with a SCG, the UE shall apply the procedures
described in this clause for both MCG and SCG except for PDCCH
monitoring in Type0/0A/0B/2/2A -PDCCH CSS sets where the UE is not
required to apply the procedures in this clause for the SCG

\- When the procedures are applied for MCG, the terms \'secondary
cell\', \'secondary cells\' , \'serving cell\', \'serving cells\' in
this clause refer to secondary cell, secondary cells, serving cell,
serving cells belonging to the MCG respectively.

\- When the procedures are applied for SCG, the terms \'secondary
cell\', \'secondary cells\', \'serving cell\', \'serving cells\' in this
clause refer to secondary cell, secondary cells (not including PSCell),
serving cell, serving cells belonging to the SCG respectively. The term
\'primary cell\' in this clause refers to the PSCell of the SCG.

A UE monitors a set of PDCCH candidates in one or more CORESETs on the
active DL BWP on each activated serving cell configured with PDCCH
monitoring according to corresponding search space sets where monitoring
implies receiving each PDCCH candidate and decoding according to the
monitored DCI formats.

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

If a UE is provided *monitoringCapabilityConfig* for a serving cell, the
UE obtains an indication to monitor PDCCH on the active DL BWP of the
serving cell for a maximum number of PDCCH candidates and
non-overlapping CCEs

\- per slot, as in Tables 10.1-2 and 10.1-3, if
*monitoringCapabilityConfig* = *r15monitoringcapability*, or

\- per span, as in Tables 10.1-2A and 10.1-3A, if
*monitoringCapabilityConfig* = *r16monitoringcapability*, or

\- per group of $X_{s}$ slots according to combination
$\left( X_{s},Y_{s} \right)$, as in Tables 10.1-2B and 10.1-3B, if
*monitoringCapabilityConfig* = *r17monitoringcapability*

The remaining of this clause, including clause 10.1, considers that a UE
is provided *monitoringCapabilityConfig* for a serving cell. If the UE
is not provided *monitoringCapabilityConfig* for the serving cell,
corresponding statements that the UE is provided
*monitoringCapabilityConfig* for the serving cell are substituted as
follows

\- for SCS configuration $\mu \in \left\{ 0,\ 1,\ 2,\ 3 \right\}$, the
UE monitors PDCCH on the active DL BWP of the serving cell for maximum
numbers of PDCCH candidates and non-overlapping CCEs per slot as in
Tables 10.1-2 and 10.1-3.

\- for SCS configuration $\mu \in \left\{ 5,\ 6 \right\}$, the UE
monitors PDCCH on the active DL BWP of the serving cell for maximum
numbers of PDCCH candidates and non-overlapping CCEs per group of
$X_{s}$ slots according to combination
$\left( X_{s},Y_{s} \right) = (4,\ 1)$ for $\mu = 5$ and
$\left( X_{s},Y_{s} \right) = (8,\ 1)$ for $\mu = 6$ as in Tables
10.1-2B and 10.1-3B.

The UE does not expect to monitor PDCCH with SCS configuration $\mu = 6$
before the UE is provided dedicated higher layer parameters.

A UE can indicate a capability to monitor PDCCH according to one or more
of the combinations $(X,Y)$ = (2, 2), (4, 3), and (7, 3) per SCS
configuration of $\mu = 0$ and $\mu = 1$. A span is a number of
consecutive symbols in a slot where the UE is configured to monitor
PDCCH. Each PDCCH monitoring occasion is within one span. If a UE
monitors PDCCH on a cell according to combination $(X,Y)$, the UE
supports PDCCH monitoring occasions in any symbol of a slot with minimum
time separation of $X$ symbols between the first symbol of two
consecutive spans, including across slots. A span starts at a first
symbol where a PDCCH monitoring occasion starts and ends at a last
symbol where a PDCCH monitoring occasion ends, where the number of
symbols of the span is up to $Y$.

If a UE indicates a capability to monitor PDCCH according to multiple
$(X,Y)$ combinations and a configuration of search space sets to the UE
for PDCCH monitoring on a cell results to a separation of every two
consecutive PDCCH monitoring spans that is equal to or larger than the
value of $X$ for more than one of the multiple combinations $(X,Y)$, the
UE monitors PDCCH on the cell according to the combination $(X,Y)$, from
the more than one combinations $(X,Y)$, that is associated with the
largest maximum number of $M_{PDCCH}^{max,(X,Y),\mu}$ and
$C_{PDCCH}^{max,(X,Y),\mu}$ defined in Table 10.1-2A and Table 10.1-3A.
The UE expects to monitor PDCCH according to the same combination
$(X,Y)$ in every slot on the active DL BWP of a cell.

For SCS configuration $\mu = 5$ or $\mu = 6$, a UE can indicate a
capability to monitor PDCCH according to one or more combinations
$\left( X_{s},Y_{s} \right)$, where $X_{s}$ and $Y_{s}$ are numbers of
consecutive slots. Groups of $X_{s}$ slots are consecutive and
non-overlapping and the $Y_{s}$ slots are within the $X_{s}$ slots. The
first group of $X_{s}$ slots starts from the beginning of a subframe.
The start of two consecutive groups of $Y_{s}$ slots is separated by
$X_{s}$ slots.

If a UE monitors PDCCH on a cell according to combination
$\left( X_{s},Y_{s} \right)$, the UE can monitor PDCCH for Type1-PDCCH
CSS set provided by dedicated higher layer signalling, Type3-PDCCH CSS
sets, and USS sets in any slot of the $Y_{s}$ slots, and the UE can
monitor PDCCH for Type0/0A/2-PDCCH CSS set and Type1-PDCCH CSS set
provided in *SIB1* in any slot of the $X_{s}$ slots. The UE determines
the number of monitored PDCCH candidates and the number of
non-overlapped CCEs for combination $\left( X_{s},Y_{s} \right)$ based
on all search space sets within the $X_{s}$ slots, as applicable
according to the search space set configurations, and maximum
corresponding values are provided in Table 10.1-2B and Table 10.1-3B,
respectively.

For $\mu = 6$, if the UE indicates a capability to monitor PDCCH
according to multiple combinations $\left( X_{s},Y_{s} \right)$ and a
configuration of search space sets to the UE for PDCCH monitoring on a
serving cell results to a separation of every two consecutive groups of
$Y_{s}$ slots that is not smaller than $X_{s}$ for more than one
combinations $\left( X_{s},Y_{s} \right)$, of the multiple combinations
$\left( X_{s},Y_{s} \right)$, the UE monitors PDCCH on the cell
according to the combination $\left( X_{s},Y_{s} \right)$, from the more
than one combinations $\left( X_{s},Y_{s} \right)$, that is associated
with the largest maximum number of $M_{PDCCH}^{max,X_{s},\mu}$ and
$C_{PDCCH}^{max,X_{s},\mu}$ defined in Table 10.1-2B and Table 10.1-3B.

A UE capability for PDCCH monitoring per slot, or per group of $X_{s}$
slots according to combination $\left( X_{s},Y_{s} \right)$, or per span
on an active DL BWP of a serving cell is defined by a maximum number of
PDCCH candidates and non-overlapped CCEs the UE can monitor per slot, or
per group of $X_{s}$ slots according to combination
$\left( X_{s},Y_{s} \right)$, or per span, respectively, on the active
DL BWP of the serving cell.

For monitoring of a PDCCH candidate by a UE, if the UE

\- has received *ssb-PositionsInBurst* in *SIB1* and has not received
*ssb-PositionsInBurst* in *ServingCellConfigCommon* for a serving cell,
and

\- does not monitor PDCCH candidates in a Type0-PDCCH CSS set, and

\- at least one RE for a PDCCH candidate overlaps with at least one RE
of a candidate SS/PBCH block, after puncturing if applicable,
corresponding to a SS/PBCH block index provided by
*ssb-PositionsInBurst* in *SIB1*,

the UE is not required to monitor the PDCCH candidate.

For monitoring of a PDCCH candidate by a UE, if the UE

\- has received *ssb-PositionsInBurst* in *ServingCellConfigCommon* for
a serving cell, and

\- does not monitor PDCCH candidates in a Type0-PDCCH CSS set, and

\- at least one RE for a PDCCH candidate overlaps with at least one RE
of a candidate SS/PBCH block, after puncturing if applicable,
corresponding to a SS/PBCH block index provided by
*ssb-PositionsInBurst* in *ServingCellConfigCommon*,

the UE is not required to monitor the PDCCH candidate.

For monitoring of a PDCCH candidate by a UE, if the UE

\- has received *ssb-PositionsInBurst* in *SSB-MTCAdditionalPCI* for a
serving cell, and

\- at least one RE for a PDCCH candidate overlaps with at least one RE
of a candidate SS/PBCH block, after puncturing if applicable,
corresponding to a SS/PBCH block index provided by
*ssb-PositionsInBurst* in *SSB-MTCAdditionalPCI* with same physical cell
identity as the one associated with a RS having same quasi-collocation
properties as a CORESET for the PDCCH candidate,

the UE is not required to monitor the PDCCH candidate.

A UE is not required to monitor PDCCH candidates for a Type0/0A/0B/1/1A
/2/2A -PDCCH CSS set when the active TCI state for a corresponding
CORESET is not associated with *physCellId* in
*ServingCellConfigCommon*.

If a UE monitors the PDCCH candidate for a Type0-PDCCH CSS set on the
serving cell according to the procedure described in clause 13, the UE
may assume that no SS/PBCH block is transmitted in REs used for
monitoring the PDCCH candidate on the serving cell.

If at least one RE of a PDCCH candidate for a UE on the serving cell
overlaps with at least one RE of *lte-CRS-ToMatchAround* or of
*LTE-CRS-PatternList*, the UE

\- is not required to monitor the PDCCH candidate if the UE is not
provided *pdcchCandidateReception-WithCRSOverlap*,

\- monitors the PDCCH candidate if the UE is provided
*pdcch-CandidateReceptionWithCRSOverlap* and the UE indicates an
associated capability corresponding to the configuration of
*lte-CRS-ToMatchAround* or of *LTE-CRS-PatternList* \[18, TS 38.306\].

If a UE is provided *availableRB-SetsPerCell,* the UE is not required to
monitor PDCCH candidates that overlap with any RB from RB sets that are
indicated as unavailable for receptions by an available RB set indicator
field in DCI format 2_0 as described in clause 11.1.1. If the UE does
not obtain the available RB set indicator for a symbol, the UE monitors
PDCCH candidates on all RB sets in the symbol.

If a UE can support

\- a first set of $N_{\text{cells,0}}^{\text{DL}}$ serving cells where
the UE is either not provided *coresetPoolIndex* or is provided
*coresetPoolIndex* with a single value for all CORESETs on all DL BWPs
of each scheduling cell from the first set of serving cells, and

\- a second set of $N_{\text{cells,1}}^{\text{DL}}$ serving cells where
the UE is not provided *coresetPoolIndex* or is provided
*coresetPoolIndex* with a value 0 for a first CORESET, and with a value
1 for a second CORESET on any DL BWP of each scheduling cell from the
second set of serving cells

the UE determines, for the purpose of reporting
*pdcch-BlindDetectionCA*, *pdcch-BlindDetectionCA1*, and
*pdcch-BlindDetectionCA3*, a number of serving cells as
$N_{\text{cells,0}}^{\text{DL}} + R \cdot N_{\text{cells,1}}^{\text{DL}}$
where $R$ is a value reported by the UE.

If a UE indicates in *UE-NR-Capability* a carrier aggregation capability
larger than 4 serving cells and the UE is not provided
*monitoringCapabilityConfig* for any downlink cell or if the UE is
provided *monitoringCapabilityConfig* = *r15monitoringcapability* for
all downlink cells where the UE monitors PDCCH, the UE includes in
*UE-NR-Capability* an indication for a maximum number of PDCCH
candidates and for a maximum number of non-overlapped CCEs the UE can
monitor per slot when the UE is configured for carrier aggregation
operation over more than 4 cells. When a UE is not configured for NR-DC
operation, the UE determines a capability to monitor a maximum number of
PDCCH candidates and a maximum number of non-overlapped CCEs per slot
that corresponds to $N_{\text{cells}}^{\text{cap}}$ downlink cells,
where

\- $N_{\text{cells}}^{\text{cap}}$ is
$N_{\text{cells,0}}^{\text{DL}} + R \cdot N_{\text{cells,1}}^{\text{DL}}$
if the UE does not provide *pdcch-BlindDetectionCA* where
$N_{\text{cells,0}}^{\text{DL}} + N_{\text{cells,1}}^{\text{DL}}$ is the
number of configured downlink serving cells

\- otherwise, $N_{\text{cells}}^{\text{cap}}$ is the value of
*pdcch-BlindDetectionCA*

When a UE is configured for NR-DC operation, the UE determines a
capability to monitor a maximum number of PDCCH candidates and a maximum
number of non-overlapped CCEs per slot that corresponds to
$N_{\text{cells}}^{\text{cap}} = N_{\text{cells}}^{\text{MCG}}$ downlink
cells for the MCG where $N_{\text{cells}}^{\text{MCG}}$ is provided by
*pdcch-BlindDetection* for the MCG and determines a capability to
monitor a maximum number of PDCCH candidates and a maximum number of
non-overlapped CCEs per slot that corresponds to
$N_{\text{cells}}^{\text{cap}} = N_{\text{cells}}^{\text{SCG}}$ downlink
cells for the SCG where $N_{\text{cells}}^{\text{SCG}}$ is provided by
*pdcch-BlindDetection* for the SCG. When the UE is configured for
carrier aggregation operation over more than 4 cells, or for a cell
group when the UE is configured for NR-DC operation, the UE does not
expect to monitor per slot a number of PDCCH candidates or a number of
non-overlapped CCEs that is larger than the maximum number as derived
from the corresponding value of $N_{\text{cells}}^{\text{cap}}$.

When a UE is configured for NR-DC operation with a total of
$N_{NR - DC}^{DL,cells}$ downlink cells on both the MCG and the SCG, the
UE expects to be provided *pdcch-BlindDetection* for the MCG and
*pdcch-BlindDetection* for the SCG with values that satisfy

\- *pdcch-BlindDetection* for the MCG + *pdcch-BlindDetection* for the
SCG \<= *pdcch-BlindDetectionCA*, if the UE reports
*pdcch-BlindDetectionCA*, or

\- *pdcch-BlindDetection* for the MCG + *pdcch-BlindDetection* for the
SCG \<= $N_{NR - DC}^{DL,cells}$, if the UE does not report
*pdcch-BlindDetectionCA*.

For NR-DC operation, the UE may indicate, through
*pdcch-BlindDetectionMCG-UE* and *pdcch-BlindDetectionSCG-UE*,
respective maximum values for *pdcch-BlindDetection* for the MCG and
*pdcch-BlindDetection* for the SCG.

If the UE reports *pdcch-BlindDetectionCA*,

\- the value range of *pdcch-BlindDetectionMCG-UE* or of
*pdcch-BlindDetectionSCG-UE* is \[1, ..., *pdcch-BlindDetectionCA*-1\],
and

\- *pdcch-BlindDetectionMCG-UE* + *pdcch-BlindDetectionSCG-UE* \>=
*pdcch-BlindDetectionCA*.

Otherwise, if $N_{NR - DC,max}^{DL,cells}$ is a maximum total number of
downlink cells that the UE can be configured on both the MCG and the SCG
for NR-DC as indicated in *UE-NR-Capability*,

\- the value range of *pdcch-BlindDetectionMCG-UE* or of
*pdcch-BlindDetectionSCG-UE* is \[1, 2, 3\], and

\- *pdcch-BlindDetectionMCG-UE* + *pdcch-BlindDetectionSCG-UE* \>=
$N_{NR - DC,max}^{DL,cells}$.

If a UE indicates in *UE-NR-Capability* a carrier aggregation capability
larger than two downlink cells, the UE includes in *UE-NR-Capability* an
indication for a maximum number of PDCCH candidates and a maximum number
of non-overlapped CCEs that the UE can monitor per span when the UE is
configured for carrier aggregation operation over more than two downlink
cells with *monitoringCapabilityConfig* = *r16monitoringcapability*.
When a UE is not configured for NR-DC operation and the UE is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* for all
downlink cells where the UE monitors PDCCH, the UE determines a
capability to monitor a maximum number of PDCCH candidates and a maximum
number of non-overlapped CCEs per span that corresponds to
$N_{cells}^{cap - r16}$ downlink cells, where

\- $N_{cells}^{cap - r16}$ is the number of configured downlink cells if
the UE does not provide *pdcch-MonitoringCA*

\- otherwise, $N_{cells}^{cap - r16}$ is the value of
*pdcch-MonitoringCA*

When a UE is configured for NR-DC operation and the UE is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* for all
downlink cells where the UE monitors PDCCH, the UE determines a
capability to monitor a maximum number of PDCCH candidates and a maximum
number of non-overlapped CCEs per span that corresponds to

\- $N_{cells}^{cap - r16} = \ N_{cells,\ r16}^{MCG}$ downlink cells for
the MCG where $N_{cells,\ r16}^{MCG}$ is provided by
*pdcch-BlindDetection2* for the MCG, and

\- $N_{cells}^{cap - r16} = \ N_{cells,\ r16}^{SCG}$ downlink cells for
the SCG where $N_{cells,\ r16}^{SCG}$ is provided by
*pdcch-BlindDetection2* for the SCG

When the UE is configured for carrier aggregation operation over more
than 2 cells, or for a cell group when the UE is configured for NR-DC
operation, the UE does not expect to monitor per span a number of PDCCH
candidates or a number of non-overlapped CCEs that is larger than the
maximum number as derived from the corresponding value of
$N_{cells}^{cap - r16}$.

When a UE is configured for NR-DC operation with a total of
$N_{NR - DC}^{DL,cells}$ downlink cells on both the MCG and the SCG and
the UE is provided *monitoringCapabilityConfig* =
*r16monitoringcapability* for all downlink cells where the UE monitors
PDCCH, the UE expects to be provided *pdcch-BlindDetection2* for the MCG
and *pdcch-BlindDetection2* for the SCG with values that satisfy

\- *pdcch-BlindDetection2* for the MCG + *pdcch-BlindDetection2* for the
SCG \<= *pdcch-MonitoringCA*, if the UE reports *pdcch-MonitoringCA*, or

\- *pdcch-BlindDetection2* for the MCG + *pdcch-BlindDetection2* for the
SCG \<= $N_{NR - DC}^{DL,cells}$, if the UE does not report
*pdcch-MonitoringCA*

When a UE is configured for NR-DC operation and the UE is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* for all
downlink cells where the UE monitors PDCCH, the UE may indicate, through
*pdcch-BlindDetectionMCG-UE-r16* and *pdcch-BlindDetectionSCG-UE-r16*,
respective maximum values for *pdcch-BlindDetection* for the MCG and
*pdcch-BlindDetection* for the SCG.

If the UE reports *pdcch-MonitoringCA*,

\- the value range of *pdcch-BlindDetectionMCG-UE-r16* or of
*pdcch-BlindDetectionSCG-UE-r16* is \[1, ..., *pdcch-MonitoringCA*-1\],
and

\- *pdcch-BlindDetectionMCG-UE-r16* + *pdcch-BlindDetectionSCG-UE-r16*
\>= *pdcch-MonitoringCA.*

Otherwise, if $N_{NR - DC,\ \ max,\ r16}^{DL,cells}$ is a maximum total
number of downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* and the UE is
configured on both the MCG and the SCG for NR-DC as indicated in
*UE-NR-Capability*

\- the value of *pdcch-BlindDetectionMCG-UE-r16* or of
*pdcch-BlindDetectionSCG-UE-r16* is 1,

\- *pdcch-BlindDetectionMCG-UE-r16* + *pdcch-BlindDetectionSCG-UE-r16*
\>= $N_{NR - DC,\ \ max,\ r16}^{DL,cells}$.

If a UE indicates in *UE-NR-Capability* a carrier aggregation capability
larger than four downlink cells, the UE includes in *UE-NR-Capability*
an indication for a maximum number of PDCCH candidates and a maximum
number of non-overlapped CCEs that the UE can monitor per group of
$X_{s}$ slots when the UE is configured for carrier aggregation
operation over more than four downlink cells for which the UE is
provided *monitoringCapabilityConfig* = *r17monitoringcapability*. When
a UE is not configured for NR-DC operation for all downlink cells where
the UE monitors PDCCH, the UE determines a capability to monitor a
maximum number of PDCCH candidates and a maximum number of
non-overlapped CCEs per group of $X_{s}$ slots that corresponds to
$N_{cells}^{cap - r17}$ downlink cells, where

\- $N_{cells}^{cap - r17}$ is
$N_{\text{cells,0}}^{\text{DL}} + R \cdot N_{\text{cells,1}}^{\text{DL}}$if
the UE does not provide *pdcch-MonitoringCA-r17* where
$N_{\text{cells,0}}^{\text{DL}} + N_{\text{cells,1}}^{\text{DL}}$ is the
number of configured downlink serving cells

\- otherwise, $N_{cells}^{cap - r17}$ is the value of
*pdcch-MonitoringCA-r17*

When the UE is configured for carrier aggregation operation over more
than 4 cells, the UE does not expect to monitor per group of $X_{s}$
slots a number of PDCCH candidates or a number of non-overlapped CCEs
that is larger than the maximum number as derived from the corresponding
value of $N_{cells}^{cap - r17}$.

When a UE is configured for NR-DC operation and the UE is provided
*monitoringCapabilityConfig* = *r17monitoringcapability* for all
downlink cells where the UE monitors PDCCH, the UE determines a
capability to monitor a maximum number of PDCCH candidates and a maximum
number of non-overlapped CCEs per group of $X_{s}$ slots that
corresponds to

\- $N_{cells}^{cap - r17} = \ N_{cells,\ r17}^{MCG}$ downlink cells for
the MCG where $N_{cells,\ r17}^{MCG}$ is provided by
*pdcch-BlindDetection4* for the MCG, and

\- $N_{cells}^{cap - r17} = \ N_{cells,\ r17}^{SCG}$ downlink cells for
the SCG where $N_{cells,\ r17}^{SCG}$ is provided by
*pdcch-BlindDetection4* for the SCG

When a UE is configured for NR-DC operation with a total of
$N_{NR - DC}^{DL,cells}$ downlink cells on both the MCG and the SCG and
the UE is provided *monitoringCapabilityConfig* =
*r17monitoringcapability* for all downlink cells where the UE monitors
PDCCH, the UE expects to be provided *pdcch-BlindDetection4* for the MCG
and *pdcch-BlindDetection4* for the SCG with values that satisfy

\- *pdcch-BlindDetection4* for the MCG + *pdcch-BlindDetection4* for the
SCG \<= *pdcch-MonitoringCA-r17*, if the UE reports
*pdcch-MonitoringCA-r17*, or

\- *pdcch-BlindDetection4* for the MCG + *pdcch-BlindDetection4* for the
SCG \<= $N_{NR - DC}^{DL,cells}$, if the UE does not report
*pdcch-MonitoringCA-r17*

When a UE is configured for NR-DC operation and the UE is provided
*monitoringCapabilityConfig* = *r17monitoringcapability* for all
downlink cells where the UE monitors PDCCH, the UE may indicate, through
*pdcch-BlindDetectionMCG-UE-r17* and *pdcch-BlindDetectionSCG-UE-r17*,
respective maximum values for *pdcch-BlindDetection4* for the MCG and
*pdcch-BlindDetection4* for the SCG.

If the UE reports *pdcch-MonitoringCA-r17*,

\- the value range of *pdcch-BlindDetectionMCG-UE-r17* or of
*pdcch-BlindDetectionSCG-UE-r17* is \[1, ...,
*pdcch-MonitoringCA-r17*-1\], and

\- *pdcch-BlindDetectionMCG-UE-r17* + *pdcch-BlindDetectionSCG-UE-r17*
\>= *pdcch-MonitoringCA-r17.*

Otherwise, if $N_{NR - DC,\ \ max,\ r17}^{DL,cells}$ is a maximum total
number of downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r17monitoringcapability* and the UE is
configured on both the MCG and the SCG for NR-DC as indicated in
*UE-NR-Capability*

\- the value range of *pdcch-BlindDetectionMCG-UE-r17* or of
*pdcch-BlindDetectionSCG-UE-r17* is \[1, 2, 3\], and

\- *pdcch-BlindDetectionMCG-UE-r17* + *pdcch-BlindDetectionSCG-UE-r17*
\>= $N_{NR - DC,\ \ max,\ r17}^{DL,cells}$.

If a UE indicates in *UE-NR-Capability* a carrier aggregation capability
larger than one downlink cell with *monitoringCapabilityConfig* =
*r15monitoringcapability* or larger than one downlink cell with
*monitoringCapabilityConfig* = *r16monitoringcapability*, the UE
includes in *UE-NR-Capability* an indication for a maximum number of
PDCCH candidates and a maximum number of non-overlapped CCEs the UE can
monitor for downlink cells with *monitoringCapabilityConfig* =
*r15monitoringcapability* or for downlink cells with
*monitoringCapabilityConfig* = *r16monitoringcapability* when the UE is
configured for carrier aggregation operation over more than two downlink
cells with at least one downlink cell with *monitoringCapabilityConfig*
= *r15monitoringcapability* and at least one downlink cell with
*monitoringCapabilityConfig* = *r16monitoringcapability*. When a UE is
not configured for NR-DC operation, the UE determines a capability to
monitor a maximum number of PDCCH candidates and a maximum number of
non-overlapped CCEs per slot or per span that corresponds to
$N_{cells,r15}^{cap - r16}$ downlink cells or to
$N_{cells,r16}^{cap - r16}$ downlink cells, respectively, where

\- $N_{cells,r15}^{cap - r16}$ is the number of configured downlink
cells if the UE does not provide *pdcch-BlindDetectionCA1*

\- otherwise,

\- if the UE reports only one combination of (*pdcch-BlindDetectionCA1*,
*pdcch-BlindDetectionCA2*), $N_{cells,r15}^{cap - r16}$ is the value of
*pdcch-BlindDetectionCA1*

\- else, $N_{cells,r15}^{cap - r16}$ is the value of
*pdcch-BlindDetectionCA1* from a combination of
(*pdcch-BlindDetectionCA1, pdcch-BlindDetectionCA2*) that is provided by
*pdcch-BlindDetectionCA-CombIndicator*

and

\- $N_{cells,r16}^{cap - r16}$ is the number of configured downlink
cells if the UE does not provide *pdcch-BlindDetectionCA2*

\- otherwise,

\- if the UE reports only one combination of (*pdcch-BlindDetectionCA1,
pdcch-BlindDetectionCA2*), $N_{cells,r16}^{cap - r16}$ is the value of
*pdcch-BlindDetectionCA2*

\- else, $N_{cells,r16}^{cap - r16}$ is the value of
*pdcch-BlindDetectionCA2* from a combination of
(*pdcch-BlindDetectionCA1, pdcch-BlindDetectionCA2*) that is provided by
*pdcch-BlindDetectionCA-CombIndicator*

If a UE indicates in *UE-NR-Capability* a carrier aggregation capability
larger than one downlink cell with *monitoringCapabilityConfig* =
*r15monitoringcapability* or larger than one downlink cell with
*monitoringCapabilityConfig* = *r17monitoringcapability*, the UE
includes in *UE-NR-Capability* an indication for a maximum number of
PDCCH candidates and a maximum number of non-overlapped CCEs the UE can
monitor for downlink cells with *monitoringCapabilityConfig* =
*r15monitoringcapability* or for downlink cells with
*monitoringCapabilityConfig* = *r17monitoringcapability* when the UE is
configured for carrier aggregation operation over more than two downlink
cells with at least one downlink cell with *monitoringCapabilityConfig*
= *r15monitoringcapability* and at least one downlink cell with
*monitoringCapabilityConfig* = *r17monitoringcapability*. When a UE is
not configured for NR-DC operation, the UE determines a capability to
monitor a maximum number of PDCCH candidates and a maximum number of
non-overlapped CCEs per slot or per group of $X_{s}$ slots that
corresponds to $N_{cells,r15/r17}^{cap - r17}$ downlink cells or to
$N_{cells,r17/r15}^{cap - r17}$ downlink cells, respectively, where

\- $N_{cells,r15/r17}^{cap - r17}$ is
$N_{\text{cells,0}}^{\text{DL}} + R \cdot N_{\text{cells,1}}^{\text{DL}}$
if the UE does not provide *pdcch-BlindDetectionCA1* in
*pdcch-BlindDetectionMixedList1*, where
$N_{\text{cells,0}}^{\text{DL}} + N_{\text{cells,1}}^{\text{DL}}$ is the
number of configured downlink serving cells

\- otherwise,

\- if the UE reports only one combination of (*pdcch-BlindDetectionCA1*,
*pdcch-BlindDetectionCA2*) in *pdcch-BlindDetectionMixedList1*,
$N_{cells,r15/r17}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA1*

\- else, $N_{cells,r15/r17}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA1* from a combination of
(*pdcch-BlindDetectionCA1, pdcch-BlindDetectionCA3*) that is provided by
*pdcch-BlindDetectionCA-CombIndicator-r17*

and

\- $N_{cells,r17/r15}^{cap - r17}$ is
$N_{\text{cells,0}}^{\text{DL}} + R \cdot N_{\text{cells,1}}^{\text{DL}}$
if the UE does not provide *pdcch-BlindDetectionCA2* in
*pdcch-BlindDetectionMixedList1*, where
$N_{\text{cells,0}}^{\text{DL}} + N_{\text{cells,1}}^{\text{DL}}$ is the
number of configured downlink serving cells

\- otherwise,

\- if the UE reports only one combination of (*pdcch-BlindDetectionCA1,
pdcch-BlindDetectionCA2*) in *pdcch-BlindDetectionMixedList1*,
$N_{cells,r17/r15}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA2*

\- else, $N_{cells,r17/r15}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA3* from a combination of
(*pdcch-BlindDetectionCA1, pdcch-BlindDetectionCA3*) that is provided by
*pdcch-BlindDetectionCA-CombIndicator-r17*

If a UE indicates in *UE-NR-Capability* a carrier aggregation capability
larger than one downlink cell with *monitoringCapabilityConfig* =
*r16monitoringcapability* or larger than one downlink cell with
*monitoringCapabilityConfig* = *r17monitoringcapability*, the UE
includes in *UE-NR-Capability* an indication for a maximum number of
PDCCH candidates and a maximum number of non-overlapped CCEs the UE can
monitor for downlink cells with *monitoringCapabilityConfig* =
*r16monitoringcapability* or for downlink cells with
*monitoringCapabilityConfig* = *r17monitoringcapability* when the UE is
configured for carrier aggregation operation over more than two downlink
cells with at least one downlink cell with *monitoringCapabilityConfig*
= *r16monitoringcapability* and with at least one downlink cell with
*monitoringCapabilityConfig* = *r17monitoringcapability*. When a UE is
not configured for NR-DC operation, the UE determines a capability to
monitor a maximum number of PDCCH candidates and a maximum number of
non-overlapped CCEs per span or per group of $X_{s}$ slots that
corresponds to $N_{cells,r16/r17}^{cap - r17}$ downlink cells or to
$N_{cells,r17/r16}^{cap - r17}$ downlink cells, respectively, where

\- $N_{cells,r16/r17}^{cap - r17}$ is the number of configured downlink
cells if the UE does not provide *pdcch-BlindDetectionCA1* in
*pdcch-BlindDetectionMixedList2*

\- otherwise,

\- if the UE reports only one combination of (*pdcch-BlindDetectionCA1*,
*pdcch-BlindDetectionCA2*) in *pdcch-BlindDetectionMixedList2*,
$N_{cells,r16/r17}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA1*

\- else, $N_{cells,r16/r17}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA2* from a combination of
(*pdcch-BlindDetectionCA2, pdcch-BlindDetectionCA3*) that is provided by
*pdcch-BlindDetectionCA-CombIndicator-r17*

and

\- $N_{cells,r17/r16}^{cap - r17}$ is the number of configured downlink
cells if the UE does not provide *pdcch-BlindDetectionCA2* in
*pdcch-BlindDetectionMixedList2*

\- otherwise,

\- if the UE reports only one combination of (*pdcch-BlindDetectionCA1,
pdcch-BlindDetectionCA2*) in *pdcch-BlindDetectionMixedList2*,
$N_{cells,r17/r16}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA2*

\- else, $N_{cells,r17/r16}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA3* from a combination of
(*pdcch-BlindDetectionCA2, pdcch-BlindDetectionCA3*) that is provided by
*pdcch-BlindDetectionCA-CombIndicator-r17*

If a UE indicates in *UE-NR-Capability* a carrier aggregation capability
larger than one downlink cell with *monitoringCapabilityConfig* =
*r15monitoringcapability*, or larger than one downlink cell with
*monitoringCapabilityConfig* = *r16monitoringcapability*, or larger than
one downlink cell with *monitoringCapabilityConfig* =
*r17monitoringcapability*, the UE includes in *UE-NR-Capability* an
indication for a maximum number of PDCCH candidates and a maximum number
of non-overlapped CCEs the UE can monitor for downlink cells with
*monitoringCapabilityConfig* = *r15monitoringcapability*, or for
downlink cells with *monitoringCapabilityConfig* =
*r16monitoringcapability*, or for downlink cells with
*monitoringCapabilityConfig* = *r17monitoringcapability* when the UE is
configured for carrier aggregation operation over more than three
downlink cells with at least one downlink cell with
*monitoringCapabilityConfig* = *r15monitoringcapability*, at least one
downlink cell with *monitoringCapabilityConfig* =
*r16monitoringcapability* and at least one downlink cell with
*monitoringCapabilityConfig* = *r17monitoringcapability*. When a UE is
not configured for NR-DC operation, the UE determines a capability to
monitor a maximum number of PDCCH candidates and a maximum number of
non-overlapped CCEs per slot or per span or per group of $X_{s}$ slots
that corresponds to $N_{cells,r15/\{ r16,r17\}}^{cap - r17}$ downlink
cells or to $N_{cells,r16/\{ r15,r17\}}^{cap - r17}$ downlink cells or
to $N_{cells,r17/\{ r15,r16\}}^{cap - r17}$ downlink cells,
respectively, where

\- $N_{cells,r15/\{ r16,r17\}}^{cap - r17}$ is the number of configured
downlink cells if the UE does not provide *pdcch-BlindDetectionCA1* in
*pdcch-BlindDetectionMixedList3*

\- otherwise,

\- if the UE reports only one combination of (*pdcch-BlindDetectionCA1*,
*pdcch-BlindDetectionCA2*, *pdcch-BlindDetectionCA3*) in
*pdcch-BlindDetectionMixedList3*,
$N_{cells,r15/\{ r16,r17\}}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA1*

\- else, $N_{cells,r15/\{ r16,r17\}}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA1* from a combination of
(*pdcch-BlindDetectionCA1*, *pdcch-BlindDetectionCA2,
pdcch-BlindDetectionCA3*) that is provided by
*pdcch-BlindDetectionCA-CombIndicator-r17*

\- $N_{cells,r16/\{ r15,r17\}}^{cap - r17}$ is the number of configured
downlink cells if the UE does not provide *pdcch-BlindDetectionCA2* in
*pdcch-BlindDetectionMixedList3*

\- otherwise,

\- if the UE reports only one combination of (*pdcch-BlindDetectionCA1*,
*pdcch-BlindDetectionCA2*, *pdcch-BlindDetectionCA3*) in
*pdcch-BlindDetectionMixedList3*,
$N_{cells,r16/\{ r15,r17\}}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA2*

\- else, $N_{cells,r16/\{ r15,r17\}}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA2* from a combination of
(*pdcch-BlindDetectionCA1*, *pdcch-BlindDetectionCA2,
pdcch-BlindDetectionCA3*) that is provided by
*pdcch-BlindDetectionCA-CombIndicator-r17*

and

\- $N_{cells,r17/\{ r15,r16\}}^{cap - r17}$ is the number of configured
downlink cells if the UE does not provide *pdcch-BlindDetectionCA3* in
*pdcch-BlindDetectionMixedList3*

\- otherwise,

\- if the UE reports only one combination of (*pdcch-BlindDetectionCA1*,
*pdcch-BlindDetectionCA2, pdcch-BlindDetectionCA3*) in
*pdcch-BlindDetectionMixedList3*,
$N_{cells,r17/\{ r15,r16\}}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA3*

\- else, $N_{cells,r17/\{ r15,r16\}}^{cap - r17}$ is the value of
*pdcch-BlindDetectionCA3* from a combination of
(*pdcch-BlindDetectionCA1*, *pdcch-BlindDetectionCA2,
pdcch-BlindDetectionCA3*) that is provided by
*pdcch-BlindDetectionCA-CombIndicator-r17*

When a UE is configured for NR-DC operation and is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* for at least
one downlink cell and *monitoringCapabilityConfig* =
*r16monitoringcapability* for at least one downlink cell where the UE
monitors PDCCH, the UE determines a capability to monitor a maximum
number of PDCCH candidates and a maximum number of non-overlapped CCEs
that corresponds to

\- $N_{cells,r15}^{cap - r16} = \ N_{cells,\ r15}^{MCG}$ downlink cells
for the MCG where $N_{cells,\ r15}^{MCG}$ is provided by
*pdcch-BlindDetection3* for the MCG,

\- $N_{cells,r15}^{cap - r16} = \ N_{cells,\ r15}^{SCG}$ downlink cells
for the SCG where $N_{cells,\ r15}^{SCG}$ is provided by
*pdcch-BlindDetection3* for the SCG, and

\- $N_{cells,r16}^{cap - r16} = \ N_{cells,\ r16}^{MCG}$ downlink cells
for the MCG where $N_{cells,\ r16}^{MCG}$ is provided by
*pdcch-BlindDetection2* for the MCG,

\- $N_{cells,r16}^{cap - r16} = \ N_{cells,\ r16}^{SCG}$ downlink cells
for the SCG where $N_{cells,\ r16}^{SCG}$ is provided by
*pdcch-BlindDetection2* for the SCG

When a UE is configured for carrier aggregation operation over more than
two downlink cells with at least one downlink cell with
*monitoringCapabilityConfig* = *r15monitoringcapability*, at least one
downlink cell with *monitoringCapabilityConfig* =
*r16monitoringcapability*, and no downlink cell has SCS configuration
$\mu \in \left\{ 5,\ 6 \right\}$, or for a cell group when the UE is
configured for NR-DC operation, the UE does not expect to

\- monitor per slot a number of PDCCH candidates or a number of
non-overlapped CCEs that is larger than the maximum number as derived
from the corresponding value of $N_{cells,r15}^{cap - r16}$, and

\- monitor per span a number of PDCCH candidates or a number of
non-overlapped CCEs that is larger than the maximum number as derived
from the corresponding value of $N_{cells,r16}^{cap - r16}$

When the UE is configured for carrier aggregation operation over more
than two downlink cells with at least one downlink cell with
*monitoringCapabilityConfig* = *r15monitoringcapability*, at least one
downlink cell with *monitoringCapabilityConfig* =
*r17monitoringcapability*, and no downlink cell with
*monitoringCapabilityConfig* = *r16monitoringcapability*, the UE does
not expect to

\- monitor per slot a number of PDCCH candidates or a number of
non-overlapped CCEs that is larger than the maximum number as derived
from the corresponding value of $N_{cells,r15/r17}^{cap - r17}$, and

\- monitor per group of $X_{s}$ slots a number of PDCCH candidates or a
number of non-overlapped CCEs that is larger than the maximum number as
derived from the corresponding value of $N_{cells,r17/r15}^{cap - r17}$

When the UE is configured for carrier aggregation operation over more
than two downlink cells with at least one downlink cell with
*monitoringCapabilityConfig* = *r16monitoringcapability*, at least one
downlink cell with *monitoringCapabilityConfig* =
*r17monitoringcapability*, and no downlink cell with
*monitoringCapabilityConfig* = *r15monitoringcapability*, the UE does
not expect to

\- monitor per span a number of PDCCH candidates or a number of
non-overlapped CCEs that is larger than the maximum number as derived
from the corresponding value of $N_{cells,r16/r17}^{cap - r17}$, and

\- monitor per group of $X_{s}$ slots a number of PDCCH candidates or a
number of non-overlapped CCEs that is larger than the maximum number as
derived from the corresponding value of $N_{cells,r17/r16}^{cap - r17}$

When the UE is configured for carrier aggregation operation over more
than three downlink cells with at least one downlink cell with
*monitoringCapabilityConfig* = *r15monitoringcapability*, at least one
downlink cell with *monitoringCapabilityConfig* =
*r16monitoringcapability*, and at least one downlink cell with
*monitoringCapabilityConfig* = *r17monitoringcapability*, the UE does
not expect to

\- monitor per slot a number of PDCCH candidates or a number of
non-overlapped CCEs that is larger than the maximum number as derived
from the corresponding value of
$N_{cells,r15/\{ r16,r17\}}^{cap - r17}$, and

\- monitor per span a number of PDCCH candidates or a number of
non-overlapped CCEs that is larger than the maximum number as derived
from the corresponding value of
$N_{cells,r16/\{ r15,r17\}}^{cap - r17}$, and

\- monitor per group of $X_{s}$ slots a number of PDCCH candidates or a
number of non-overlapped CCEs that is larger than the maximum number as
derived from the corresponding value of
$N_{cells,r17/\{ r15,r16\}}^{cap - r17}$

When a UE is configured for NR-DC operation with a total of
$N_{NR - DC}^{DL,cells}$ downlink cells on both the MCG and the SCG and
the UE is provided *monitoringCapabilityConfig* =
*r15monitoringcapability* for* *$N_{NR - DC,r15}^{DL,cells}$ downlink
cells and *monitoringCapabilityConfig* = *r16monitoringcapability* for
$N_{NR - DC,r16}^{DL,cells}$ downlink cells where the UE monitors PDCCH,
the UE expects to be provided *pdcch-BlindDetection3* and
*pdcch-BlindDetection2* for the MCG, and *pdcch-BlindDetection3* and
*pdcch-BlindDetection2* for the SCG with values that satisfy

\- *pdcch-BlindDetection3* for the MCG + *pdcch-BlindDetection3* for the
SCG \<= *pdcch-BlindDetectionCA1*, if the UE reports
*pdcch-BlindDetectionCA1*, or

\- *pdcch-BlindDetection3* for the MCG + *pdcch-BlindDetection3* for the
SCG \<= $N_{NR - DC,r15}^{DL,cells}$, if the UE does not report
*pdcch-BlindDetectionCA1*

and

\- *pdcch-BlindDetection2* for the MCG + *pdcch-BlindDetection2* for the
SCG \<= *pdcch-BlindDetectionCA2*, if the UE reports
*pdcch-BlindDetectionCA2*, or

\- *pdcch-BlindDetection2* for the MCG + *pdcch-BlindDetection2* for the
SCG \<= $N_{NR - DC,r16}^{DL,cells}$, if the UE does not report
*pdcch-BlindDetectionCA2*

When a UE is configured for NR-DC operation and is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* for at least
one downlink cell and *monitoringCapabilityConfig* =
*r16monitoringcapability* for at least one downlink cell where the UE
monitors PDCCH, the UE may indicate, through
*pdcch-BlindDetectionMCG-UE1* and *pdcch-BlindDetectionSCG-UE1*,
respective maximum values for *pdcch-BlindDetection3* for the MCG and
*pdcch-BlindDetection3* for the SCG, and through
*pdcch-BlindDetectionMCG-UE2* and *pdcch-BlindDetectionSCG-UE2*
respective maximum values for *pdcch-BlindDetection2* for the MCG and
*pdcch-BlindDetection2* for the SCG.

If the UE reports *pdcch-BlindDetectionCA1*,

\- the value range of *pdcch-BlindDetectionMCG-UE1* or of
*pdcch-BlindDetectionSCG-UE1* is \[0, 1, ...,
*pdcch-BlindDetectionCA1*\], and

\- *pdcch-BlindDetectionMCG-UE1* + *pdcch-BlindDetectionSCG-UE1* \>=
*pdcch-BlindDetectionCA1*.

Otherwise, if $N_{NR - DC,\ \ max,\ r15}^{DL,cells}$ is a maximum total
number of downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* and the UE is
configured on both the MCG and the SCG for NR-DC as indicated in
*UE-NR-Capability*

\- the value range of *pdcch-BlindDetectionMCG-UE1* or of
*pdcch-BlindDetectionSCG-UE1* is \[0, 1, 2\],

\- *pdcch-BlindDetectionMCG-UE1* + *pdcch-BlindDetectionSCG-UE1* \>=
$N_{NR - DC,\ \ max,\ r15}^{DL,cells}$.

If the UE reports *pdcch-BlindDetectionCA2*

\- the value range of *pdcch-BlindDetectionMCG-UE2* or of
*pdcch-BlindDetectionSCG-UE2* is \[0, 1, ...,
*pdcch-BlindDetectionCA2*\], and

\- *pdcch-BlindDetectionMCG-UE2* + *pdcch-BlindDetectionSCG-UE2* \>=
*pdcch-BlindDetectionCA2.*

Otherwise, if $N_{NR - DC,\ \ max,\ r16}^{DL,cells}$ is a maximum total
number of downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* and the UE is
configured on both the MCG and the SCG for NR-DC as indicated in
*UE-NR-Capability*

\- the value range of *pdcch-BlindDetectionMCG-UE2* or of
*pdcch-BlindDetectionSCG-UE2* is \[0, 1\],

\- *pdcch-BlindDetectionMCG-UE2* + *pdcch-BlindDetectionSCG-UE2* \>=
$N_{NR - DC,\ \ max,\ r16}^{DL,cells}$.

When a UE is configured for NR-DC operation with a total of
$N_{NR - DC}^{DL,cells}$ downlink cells on both the MCG and the SCG and
the UE is provided *monitoringCapabilityConfig* =
*r15monitoringcapability* for* *$N_{NR - DC,r15}^{DL,cells}$ downlink
cells and *monitoringCapabilityConfig* = *r17monitoringcapability* for
$N_{NR - DC,r17}^{DL,cells}$ downlink cells where the UE monitors PDCCH,
the UE expects to be provided *pdcch-BlindDetection3* and
*pdcch-BlindDetection4* for the MCG, and *pdcch-BlindDetection3* and
*pdcch-BlindDetection4* for the SCG with values that satisfy

\- *pdcch-BlindDetection3* for the MCG + *pdcch-BlindDetection3* for the
SCG \<= *pdcch-BlindDetectionCA1*, if the UE reports
*pdcch-BlindDetectionCA1* in *pdcch-BlindDetectionMixedList1*, or

\- *pdcch-BlindDetection3* for the MCG + *pdcch-BlindDetection3* for the
SCG \<= $N_{NR - DC,r15}^{DL,cells}$, if the UE does not report
*pdcch-BlindDetectionCA1* in *pdcch-BlindDetectionMixedList1*

and

\- *pdcch-BlindDetection4* for the MCG + *pdcch-BlindDetection4* for the
SCG \<= *pdcch-BlindDetectionCA2*, if the UE reports
*pdcch-BlindDetectionCA2* in *pdcch-BlindDetectionMixedList1*, or

\- *pdcch-BlindDetection4* for the MCG + *pdcch-BlindDetection4* for the
SCG \<= $N_{NR - DC,r17}^{DL,cells}$, if the UE does not report
*pdcch-BlindDetectionCA2* in *pdcch-BlindDetectionMixedList1*

When a UE is configured for NR-DC operation and is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* for at least
one downlink cell and *monitoringCapabilityConfig* =
*r17monitoringcapability* for at least one downlink cell where the UE
monitors PDCCH, the UE may indicate, through
*pdcch-BlindDetectionCG-UE1* in *pdcch-BlindDetectionMCG-UE-Mixed* and
*pdcch-BlindDetectionCG-UE1* in *pdcch-BlindDetectionSCG-UE-Mixed*,
respective maximum values for *pdcch-BlindDetection3* for the MCG and
*pdcch-BlindDetection3* for the SCG, and through
*pdcch-BlindDetectionCG-UE2* in *pdcch-BlindDetectionMCG-UE-Mixed* and
*pdcch-BlindDetectionCG-UE2* in *pdcch-BlindDetectionSCG-UE-Mixed*,
respective maximum values for *pdcch-BlindDetection4* for the MCG and
*pdcch-BlindDetection4* for the SCG.

If the UE reports *pdcch-BlindDetectionCA1* in
*pdcch-BlindDetectionMixedList1*,

\- the value range of *pdcch-BlindDetectionCG-UE1* for the MCG or of
*pdcch-BlindDetectionCG-UE1* for the SCG is \[0, 1, ...,
*pdcch-BlindDetectionCA1*\], and

\- *pdcch-BlindDetectionCG-UE1* for the MCG +
*pdcch-BlindDetectionCG-UE1* for the SCG \>= *pdcch-BlindDetectionCA1*.

Otherwise, if $N_{NR - DC,\ \ max,\ r15}^{DL,cells}$ is a maximum total
number of downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* and the UE is
configured on both the MCG and the SCG for NR-DC as indicated in
*UE-NR-Capability*

\- the value range of *pdcch-BlindDetectionCG-UE1* for the MCG or of
*pdcch-BlindDetectionCG-UE1* for the SCG is \[0, 1, 2\],

\- *pdcch-BlindDetectionCG-UE1* for the MCG +
*pdcch-BlindDetectionSCG-UE1* for the SCG \>=
$N_{NR - DC,\ \ max,\ r15}^{DL,cells}$.

If the UE reports *pdcch-BlindDetectionCA2* in
*pdcch-BlindDetectionMixedList1*

\- the value range of *pdcch-BlindDetectionCG-UE2* for the MCG or of
*pdcch-BlindDetectionCG-UE2* for the SCG is \[0, 1, ...,
*pdcch-BlindDetectionCA3*\], and

\- *pdcch-BlindDetectionCG-UE2* for the MCG +
*pdcch-BlindDetectionCG-UE2* for the SCG \>= *pdcch-BlindDetectionCA2.*

Otherwise, if $N_{NR - DC,\ \ max,\ r17}^{DL,cells}$ is a maximum total
number of downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r17monitoringcapability* and the UE is
configured on both the MCG and the SCG for NR-DC as indicated in
*UE-NR-Capability*

\- the value range of *pdcch-BlindDetectionCG-UE2* for the MCG or of
*pdcch-BlindDetectionCG-UE2* for the SCG is \[0, 1, 2\],

\- *pdcch-BlindDetectionCG-UE2* for the MCG +
*pdcch-BlindDetectionCG-UE2* for the SCG \>=
$N_{NR - DC,\ \ max,\ r17}^{DL,cells}$.

When a UE is configured for NR-DC operation with a total of
$N_{NR - DC}^{DL,cells}$ downlink cells on both the MCG and the SCG and
the UE is provided *monitoringCapabilityConfig* =
*r16monitoringcapability* for* *$N_{NR - DC,r16}^{DL,cells}$ downlink
cells and *monitoringCapabilityConfig* = *r17monitoringcapability* for
$N_{NR - DC,r17}^{DL,cells}$ downlink cells where the UE monitors PDCCH,
the UE expects to be provided *pdcch-BlindDetection2* and
*pdcch-BlindDetection4* for the MCG, and *pdcch-BlindDetection2* and
*pdcch-BlindDetection4* for the SCG with values that satisfy

\- *pdcch-BlindDetection2* for the MCG + *pdcch-BlindDetection2* for the
SCG \<= *pdcch-BlindDetectionCA1*, if the UE reports
*pdcch-BlindDetectionCA1* in *pdcch-BlindDetectionMixedList2*, or

\- *pdcch-BlindDetection2* for the MCG + *pdcch-BlindDetection2* for the
SCG \<= $N_{NR - DC,r16}^{DL,cells}$, if the UE does not report
*pdcch-BlindDetectionCA1* in *pdcch-BlindDetectionMixedList2*

and

\- *pdcch-BlindDetection4* for the MCG + *pdcch-BlindDetection4* for the
SCG \<= *pdcch-BlindDetectionCA2*, if the UE reports
*pdcch-BlindDetectionCA2* in *pdcch-BlindDetectionMixedList2*, or

\- *pdcch-BlindDetection4* for the MCG + *pdcch-BlindDetection4* for the
SCG \<= $N_{NR - DC,r17}^{DL,cells}$, if the UE does not report
*pdcch-BlindDetectionCA2* in *pdcch-BlindDetectionMixedList2*

When a UE is configured for NR-DC operation and is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* for at least
one downlink cell and *monitoringCapabilityConfig* =
*r17monitoringcapability* for at least one downlink cell where the UE
monitors PDCCH, the UE may indicate, through
*pdcch-BlindDetectionCG-UE1* in *pdcch-BlindDetectionMCG-UE-Mixed* and
*pdcch-BlindDetectionCG-UE1* in *pdcch-BlindDetectionSCG-UE-Mixed*,
respective maximum values for *pdcch-BlindDetection2* for the MCG and
*pdcch-BlindDetection2* for the SCG, and through
*pdcch-BlindDetectionCG-UE2* in *pdcch-BlindDetectionMCG-UE-Mixed* and
*pdcch-BlindDetectionCG-UE2* in *pdcch-BlindDetectionSCG-UE-Mixed*,
respective maximum values for *pdcch-BlindDetection4* for the MCG and
*pdcch-BlindDetection4* for the SCG.

If the UE reports *pdcch-BlindDetectionCA1* in
*pdcch-BlindDetectionMixedList2*,

\- the value range of *pdcch-BlindDetectionCG-UE1* for the MCG or of
*pdcch-BlindDetectionCG-UE1* for the SCG is \[0, 1, ...,
*pdcch-BlindDetectionCA1*\], and

\- *pdcch-BlindDetectionCG-UE1* for the MCG +
*pdcch-BlindDetectionCG-UE1* for the SCG \>= *pdcch-BlindDetectionCA1*.

Otherwise, if $N_{NR - DC,\ \ max,\ r16}^{DL,cells}$ is a maximum total
number of downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* and the UE is
configured on both the MCG and the SCG for NR-DC as indicated in
*UE-NR-Capability*

\- the value range of *pdcch-BlindDetectionCG-UE1* for the MCG or of
*pdcch-BlindDetectionCG-UE1* for the SCG is \[0, 1\],

\- *pdcch-BlindDetectionCG-UE1* for the MCG +
*pdcch-BlindDetectionCG-UE1* for the SCG \>=
$N_{NR - DC,\ \ max,\ r16}^{DL,cells}$.

If the UE reports *pdcch-BlindDetectionCA2* in
*pdcch-BlindDetectionMixedList2*

\- the value range of *pdcch-BlindDetectionCG-UE2* for the MCG or of
*pdcch-BlindDetectionCG-UE2* for the SCG is \[0, 1, ...,
*pdcch-BlindDetectionCA2*\], and

\- *pdcch-BlindDetectionCG-UE2* for the MCG +
*pdcch-BlindDetectionCG-UE2* for the SCG \>= *pdcch-BlindDetectionCA2.*

Otherwise, if $N_{NR - DC,\ \ max,\ r17}^{DL,cells}$ is a maximum total
number of downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r17monitoringcapability* and the UE is
configured on both the MCG and the SCG for NR-DC as indicated in
*UE-NR-Capability*

\- the value range of *pdcch-BlindDetectionCG-UE2* for the MCG or of
*pdcch-BlindDetectionCG-UE2* for the SCG is \[0, 1, 2\],

\- *pdcch-BlindDetectionCG-UE2* for the MCG +
*pdcch-BlindDetectionCG-UE2* for the SCG \>=
$N_{NR - DC,\ \ max,\ r17}^{DL,cells}$.

When a UE is configured for NR-DC operation with a total of
$N_{NR - DC}^{DL,cells}$ downlink cells on both the MCG and the SCG and
the UE is provided *monitoringCapabilityConfig* =
*r15monitoringcapability* for* *$N_{NR - DC,r15}^{DL,cells}$ downlink
cells, *monitoringCapabilityConfig* = *r16monitoringcapability*
for* *$N_{NR - DC,r16}^{DL,cells}$ downlink cells, and
*monitoringCapabilityConfig* = *r17monitoringcapability* for
$N_{NR - DC,r17}^{DL,cells}$ downlink cells where the UE monitors PDCCH,
the UE expects to be provided *pdcch-BlindDetection3*,
*pdcch-BlindDetection2*, and *pdcch-BlindDetection4* for the MCG, and
*pdcch-BlindDetection3*, *pdcch-BlindDetection2*, and
*pdcch-BlindDetection4* for the SCG with values that satisfy

\- *pdcch-BlindDetection3* for the MCG + *pdcch-BlindDetection3* for the
SCG \<= *pdcch-BlindDetectionCA1*, if the UE reports
*pdcch-BlindDetectionCA1* in *pdcch-BlindDetectionMixedList3*, or

\- *pdcch-BlindDetection3* for the MCG + *pdcch-BlindDetection3* for the
SCG \<= $N_{NR - DC,r15}^{DL,cells}$, if the UE does not report
*pdcch-BlindDetectionCA1* in *pdcch-BlindDetectionMixedList3*

and

\- *pdcch-BlindDetection2* for the MCG + *pdcch-BlindDetection2* for the
SCG \<= *pdcch-BlindDetectionCA2*, if the UE reports
*pdcch-BlindDetectionCA2* in *pdcch-BlindDetectionMixedList3*, or

\- *pdcch-BlindDetection2* for the MCG + *pdcch-BlindDetection2* for the
SCG \<= $N_{NR - DC,r16}^{DL,cells}$, if the UE does not report
*pdcch-BlindDetectionCA2* in *pdcch-BlindDetectionMixedList3*

and

\- *pdcch-BlindDetection4* for the MCG + *pdcch-BlindDetection4* for the
SCG \<= *pdcch-BlindDetectionCA3*, if the UE reports
*pdcch-BlindDetectionCA3* in *pdcch-BlindDetectionMixedList3*, or

\- *pdcch-BlindDetection4* for the MCG + *pdcch-BlindDetection4* for the
SCG \<= $N_{NR - DC,r17}^{DL,cells}$, if the UE does not report
*pdcch-BlindDetectionCA3* in *pdcch-BlindDetectionMixedList3*

When a UE is configured for NR-DC operation and is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* for at least
one downlink cell, *monitoringCapabilityConfig* =
*r16monitoringcapability* for at least one downlink cell, and
*monitoringCapabilityConfig* = *r17monitoringcapability* for at least
one downlink cell where the UE monitors PDCCH, the UE may indicate,
through *pdcch-BlindDetectionCG-UE1* in
*pdcch-BlindDetectionMCG-UE-Mixed1* and *pdcch-BlindDetectionCG-UE1* in
*pdcch-BlindDetectionSCG-UE-Mixed1* respective maximum values for
*pdcch-BlindDetection3* for the MCG and *pdcch-BlindDetection3* for the
SCG, through *pdcch-BlindDetectionCG-UE2* in
*pdcch-BlindDetectionMCG-UE-Mixed1* and *pdcch-BlindDetectionCG-UE2* in
*pdcch-BlindDetectionSCG-UE-Mixed1* respective maximum values for
*pdcch-BlindDetection2* for the MCG and *pdcch-BlindDetection2* for the
SCG, and through *pdcch-BlindDetectionCG-UE3* in
*pdcch-BlindDetectionMCG-UE-Mixed1* and *pdcch-BlindDetectionCG-UE3* in
*pdcch-BlindDetectionSCG-UE-Mixed1* respective maximum values for
*pdcch-BlindDetection4* for the MCG and *pdcch-BlindDetection4* for the
SCG.

If the UE reports *pdcch-BlindDetectionCA1* in
*pdcch-BlindDetectionMixedList3*,

\- the value range of *pdcch-BlindDetectionCG-UE1* for the MCG or of
*pdcch-BlindDetectionCG-UE1* for the SCG is \[0, 1, ...,
*pdcch-BlindDetectionCA1*\], and

\- *pdcch-BlindDetectionCG-UE1* for the MCG +
*pdcch-BlindDetectionCG-UE1* for the SCG \>= *pdcch-BlindDetectionCA1*.

Otherwise, if $N_{NR - DC,\ \ max,\ r15}^{DL,cells}$ is a maximum total
number of downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* and the UE is
configured on both the MCG and the SCG for NR-DC as indicated in
*UE-NR-Capability*

\- the value range of *pdcch-BlindDetectionCG-UE1* for the MCG or of
*pdcch-BlindDetectionCG-UE1* for the SCG is \[0, 1, 2\],

\- *pdcch-BlindDetectionCG-UE1* for the MCG +
*pdcch-BlindDetectionCG-UE1* for the SCG \>=
$N_{NR - DC,\ \ max,\ r15}^{DL,cells}$.

If the UE reports *pdcch-BlindDetectionCA2* in
*pdcch-BlindDetectionMixedList3*,

\- the value range of *pdcch-BlindDetectionCG-UE2* for the MCG or of
*pdcch-BlindDetectionCG-UE2* for the SCG is \[0, 1, ...,
*pdcch-BlindDetectionCA2*\], and

\- *pdcch-BlindDetectionCG-UE2* for the MCG +
*pdcch-BlindDetectionCG-UE2* for the SCG \>= *pdcch-BlindDetectionCA2*.

Otherwise, if $N_{NR - DC,\ \ max,\ r16}^{DL,cells}$ is a maximum total
number of downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* and the UE is
configured on both the MCG and the SCG for NR-DC as indicated in
*UE-NR-Capability*

\- the value range of *pdcch-BlindDetectionCG-UE2* for the MCG or of
*pdcch-BlindDetectionCG-UE2* for the SCG is \[0, 1\],

\- *pdcch-BlindDetectionCG-UE2* for the MCG +
*pdcch-BlindDetectionCG-UE2* for the SCG \>=
$N_{NR - DC,\ \ max,\ r16}^{DL,cells}$.

If the UE reports *pdcch-BlindDetectionCA3* in
*pdcch-BlindDetectionMixedList3*

\- the value range of *pdcch-BlindDetectionCG-UE3* for the MCG or of
*pdcch-BlindDetectionCG-UE3* for the SCG is \[0, 1, ...,
*pdcch-BlindDetectionCA3*\], and

\- *pdcch-BlindDetectionCG-UE3* for the MCG +
*pdcch-BlindDetectionCG-UE3* for the SCG \>= *pdcch-BlindDetectionCA3.*

Otherwise, if $N_{NR - DC,\ \ max,\ r17}^{DL,cells}$ is a maximum total
number of downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r17monitoringcapability* and the UE is
configured on both the MCG and the SCG for NR-DC as indicated in
*UE-NR-Capability*

\- the value range of *pdcch-BlindDetectionCG-UE3* for the MCG or of
*pdcch-BlindDetectionCG-UE3* for the SCG is \[0, 1, 2\],

\- *pdcch-BlindDetectionCG-UE3* for the MCG +
*pdcch-BlindDetectionCG-UE3* for the SCG \>=
$N_{NR - DC,\ \ max,\ r17}^{DL,cells}$.