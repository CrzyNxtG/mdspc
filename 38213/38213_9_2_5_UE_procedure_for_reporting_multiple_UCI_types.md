### 9.2.5 UE procedure for reporting multiple UCI types

This clause is applicable to the case that a UE has resources for PUCCH
transmissions or for PUCCH and PUSCH transmissions that overlap in time
and each PUCCH transmission is over a single slot without repetitions.
Any case that a PUCCH transmission is with repetitions over multiple
slots is described in clause 9.2.6. If a UE is configured with multiple
PUCCH resources in a slot to transmit CSI reports

\- if the UE is not provided *multi-CSI-PUCCH-ResourceList* or if PUCCH
resources for transmissions of CSI reports do not overlap in the slot,
the UE determines a first resource corresponding to a CSI report with
the highest priority \[6, TS 38.214\]

\- if the first resource includes PUCCH format 2, and if there are
remaining resources in the slot that do not overlap with the first
resource, the UE determines a CSI report with the highest priority,
among the CSI reports with corresponding resources from the remaining
resources, and a corresponding second resource as an additional resource
for CSI reporting

\- if the first resource includes PUCCH format 3 or PUCCH format 4, and
if there are remaining resources in the slot that include PUCCH format 2
and do not overlap with the first resource, the UE determines a CSI
report with the highest priority, among the CSI reports with
corresponding resources from the remaining resources, and a
corresponding second resource as an additional resource for CSI
reporting

\- if the UE is provided *multi-CSI-PUCCH-ResourceList* and if any of
the multiple PUCCH resources overlap, the UE multiplexes all CSI reports
in a resource from the resources provided by
*multi-CSI-PUCCH-ResourceList*, as described in clause 9.2.5.2.

A UE multiplexes DL HARQ-ACK information, with or without SR, and CSI
report(s) in a same PUCCH if the UE is provided
*simultaneousHARQ-ACK-CSI*; otherwise, the UE drops the CSI report(s)
and includes only DL HARQ-ACK information, with or without SR, in the
PUCCH. If the UE would transmit multiple PUCCHs in a slot that include
DL HARQ-ACK information and CSI report(s), the UE expects to be provided
a same configuration for *simultaneousHARQ-ACK-CSI* each of PUCCH
formats 2, 3, and 4.

If a UE would multiplex CSI reports that include Part 2 CSI reports in a
PUCCH resource, the UE determines the PUCCH resource and a number of
PRBs for the PUCCH resource or a number of Part 2 CSI reports assuming
that each of the CSI reports and, if any, each CSI sub-report included
in a CSI report, indicates rank 1, or rank combination of {1, 1} if
applicable. If the higher layer parameter *csi-ReportMode* of CSI
reports is set to \'Mode2\', the UE determines the PUCCH resource and a
number of PRBs for the PUCCH resource or a number of Part 2 CSI reports
assuming that each CRI in the CSI report is associated with a resource
pair.

If a UE would transmit multiple overlapping PUCCHs in a slot or
overlapping PUCCH(s) and PUSCH(s) in a slot and, when applicable as
described in clauses 9.2.5.1, 9.2.5.2, 9.2.5.3 and 18, the UE is
configured to multiplex different UCI types or UCI of different priority
indexes in one PUCCH, and at least one of the multiple overlapping
PUCCHs or PUSCHs is in response to a DCI format detection by the UE, the
UE multiplexes all corresponding UCI types or UCI of different priority
indexes if the following conditions are met. If one of the PUCCH
transmissions or PUSCH transmissions is in response to a DCI format
detection by the UE, the UE expects that the first symbol $S_{0}$ of the
earliest PUCCH or PUSCH, among a group overlapping PUCCHs and PUSCHs in
the slot, satisfies the following timeline conditions

\- $S_{0}$ is not before a symbol with CP starting after
$T_{proc,1}^{mux}$ after a last symbol of any corresponding PDSCH,
$T_{proc,1}^{mux}$ is given by maximum of
$\left\{ T_{proc,1}^{mux,1},\cdots,T_{proc,1}^{mux,i},\cdots \right\}$
where for the i-th PDSCH with corresponding HARQ-ACK transmission on a
PUCCH which is in the group of overlapping PUCCHs and PUSCHs,
$T_{proc,1}^{mux,i} = \left( N_{1} + d_{1,1} + 1 \right) \cdot (2048 + 144) \cdot \kappa \cdot 2^{- \mu} \cdot T_{C}$,
$d_{1,1}$ is selected for the i-th PDSCH following \[6, TS 38.214\],
$N_{1}$ is selected based on the UE PDSCH processing capability of the
i-th PDSCH and SCS configuration $\mu$, where $\mu$ corresponds to the
smallest SCS configuration among the SCS configurations used for the
PDCCH scheduling the i-th PDSCH if any, the i-th PDSCH, the PUCCH with
corresponding HARQ-ACK transmission for the i-th PDSCH, and all PUSCHs
in the group of overlapping PUCCHs and PUSCHs.

\- $S_{0}$ is not before a symbol with CP starting after
$T_{proc,release}^{mux}$ after a last symbol of a PDCCH reception
providing a DCI format having associated HARQ-ACK information without
scheduling a PDSCH reception. $T_{proc,release}^{mux}$ is given by
maximum of
$\left\{ T_{proc,release}^{mux,1},\cdots,T_{proc,release}^{mux,i},\cdots \right\}$
where for the i-th PDCCH providing the DCI format with corresponding
HARQ-ACK transmission on a PUCCH which is in the group of overlapping
PUCCHs and PUSCHs,
$T_{proc,release}^{mux,i} = (N + 1) \cdot (2048 + 144) \cdot \kappa \cdot 2^{- \mu} \cdot T_{C}$,
$N$ as described in clause 10.2, where $\mu$ corresponds to the smallest
SCS configuration among the SCS configurations used for the PDCCH, the
PUCCH with corresponding HARQ-ACK information, and all PUSCHs in the
group of overlapping PUCCHs and PUSCHs.

\- if there is no aperiodic CSI report multiplexed in a PUSCH in the
group of overlapping PUCCHs and PUSCHs, $S_{0}$ is not before a symbol
with CP starting after $T_{proc,2}^{mux}$ after a last symbol of

\- any PDCCH with the DCI format scheduling an overlapping PUSCH, and

\- any PDCCH providing a DCI format with corresponding HARQ-ACK
information in an overlapping PUCCH in the slot

If there is at least one PUSCH in the group of overlapping PUCCHs and
PUSCHs, $T_{proc,2}^{mux}$ is given by maximum of
$\left\{ T_{proc,2}^{mux,1},\cdots,T_{proc,2}^{mux,i},\cdots \right\}$
where for the i-th PUSCH which is in the group of overlapping PUCCHs and
PUSCHs,
$T_{proc,2}^{mux,i} = \max\left( \left( N_{2} + d_{2,1} + 1 \right) \cdot (2048 + 144) \cdot \kappa \cdot 2^{- \mu} \cdot T_{C} + T_{switch},d_{2,2} \right)$,
$d_{2,1}$, $d_{2,2}$ and $T_{switch}$ are selected for the i-th PUSCH
following \[6, TS 38.214\], $N_{2}$ is selected based on the UE PUSCH
processing capability of the i-th PUSCH and SCS configuration $\mu$,
where $\mu$ corresponds to the smallest SCS configuration among the SCS
configurations used for the PDCCH scheduling the i-th PUSCH, the PDCCHs
scheduling the PDSCHs, or providing the DCI formats without scheduling
PDSCHs, with corresponding HARQ-ACK information on a PUCCH which is in
the group of overlapping PUCCHs/PUSCHs, and all PUSCHs in the group of
overlapping PUCCHs and PUSCHs.

If there is no PUSCH in the group of overlapping PUCCHs and PUSCHs,
$T_{proc,2}^{mux}$ is given by maximum of
$\left\{ T_{proc,2}^{mux,1},\cdots,T_{proc,2}^{mux,i},\cdots \right\}$
where for the i-th PDSCH, or the i-th PDCCH providing a DCI format
without scheduling PDSCH, with corresponding HARQ-ACK information on a
PUCCH which is in the group of overlapping PUCCHs,
$T_{proc,2}^{mux,i} = \left( N_{2} + 1 \right) \cdot (2048 + 144) \cdot \kappa \cdot 2^{- \mu} \cdot T_{C}$,
$N_{2}\ $ is selected based on the UE PUSCH processing capability of the
PUCCH serving cell if configured. $N_{2}$ is selected based on the UE
PUSCH processing capability 1, if PUSCH processing capability is not
configured for the PUCCH serving cell. $\mu$ is selected based on the
smallest SCS configuration between the SCS configuration used for the
PDCCH scheduling the i-th PDSCH, or providing the i-th DCI format
without scheduling PDSCH, with corresponding HARQ-ACK information on a
PUCCH which is in the group of overlapping PUCCHs, and the SCS
configuration for the PUCCH serving cell.

\- if there is an aperiodic CSI report multiplexed in a PUSCH in the
group of overlapping PUCCHs and PUSCHs, $S_{0}$ is not before a symbol
with CP starting after
$T_{proc,CSI}^{mux} = \max\left( (Z + d) \cdot (2048 + 144) \cdot \kappa \cdot 2^{- \mu} \cdot T_{C} + T_{switch},d_{2,2} \right)$
after a last symbol of

\- any PDCCH with the DCI format scheduling an overlapping PUSCH, and

\- any PDCCH scheduling a PDSCH, or providing a DCI format , with
corresponding HARQ-ACK information in an overlapping PUCCH in the slot

where $\mu$ corresponds to the smallest SCS configuration among the SCS
configuration of the PDCCHs, the smallest SCS configuration for the
group of the overlapping PUSCHs, and the smallest SCS configuration of
CSI-RS associated with the DCI format scheduling the PUSCH with the
multiplexed aperiodic CSI report, and $d = 2$ for $\mu = 0,1$, $d = 3$
for $\mu = 2$, and $d = 4$ for $\mu \geq 3$. $T_{switch}$ is defined in
\[6, TS 38.214\] and it is applied only if $Z_{1}$ of Table 5.4-1 in
\[6, TS 38.214\] is applied to the determination of $Z$.

\- $N_{1}$, $N_{2}$, $d_{1,1}$, $d_{2,1}$, $d_{2,2}$, and $Z$ $\ $are
defined in \[6, TS 38.214\] and $\kappa$ and $T_{C}$ are defined in \[4,
TS 38.211\].

If a UE would transmit multiple overlapping PUCCHs in a slot or
overlapping PUCCH(s) and PUSCH(s) in a slot, one of the PUCCHs includes
HARQ-ACK information in response to an SPS PDSCH reception, and any
PUSCH is not in response to a DCI format detection, the UE expects that
the first symbol $S_{0}$ of the earliest PUCCH or PUSCH satisfies the
first of the previous timeline conditions with the exception that
components associated to a SCS configuration for a PDCCH scheduling a
PDSCH or a PUSCH are absent from the timeline conditions.

A UE does not expect a PUCCH or a PUSCH that is in response to a DCI
format detection to overlap with any other PUCCH or PUSCH that does not
satisfy the above timing conditions.

A UE that

\- is not provided *coresetPoolIndex* or is provided *coresetPoolIndex*
with a value of 0 for first CORESETs on active DL BWPs of serving cells,
and

\- is provided *coresetPoolIndex* with a value of 1 for second CORESETs
on active DL BWPs of the serving cells, and

\- is provided *ackNackFeedbackMode* = *separate*

does not expect a PUCCH or a PUSCH transmission triggered by a detection
of a DCI format in a PDCCH received in a CORESET from the first CORESETs
to overlap in time with a PUCCH or a PUSCH transmission triggered by a
detection of a DCI format in a PDCCH received in a CORESET from the
second CORESETs if the UE is not provided *sTx-2Panel*; else, if the UE
is provided *sTx-2Panel*, the UE does not expect to transmit a PUCCH
that includes HARQ-ACK information and is associated with either the
first or the second CORESETs to overlap with a PUSCH transmission
associated with either the second or the first CORESETs and not overlap
with a PUSCH transmission associated with either the first or the second
CORESETs, respectively.

If there is one or more aperiodic CSI reports multiplexed on a PUSCH in
the group of overlapping PUCCHs and PUSCHs and if symbol $S_{0}$ is
before symbol ${Z'}_{ref}^{\ mux}$ that is a next uplink symbol with CP
starting after
${Z'}_{proc,CSI}^{\ mux} = (Z' + d) \cdot (2048 + 144) \cdot \kappa \cdot 2^{- \mu} \cdot T_{C}$
after the end of the last symbol of

\- the last symbol of aperiodic CSI-RS resource for channel
measurements, and

\- the last symbol of aperiodic CSI-IM used for interference
measurements, and

\- the last symbol of aperiodic NZP CSI-RS for interference measurements
for a *CSI-ReportConfig*, or for all triggered sub-configurations if
*CSI-ReportConfig* contains multiple sub-configurations, when aperiodic
CSI-RS is used for channel measurement for triggered CSI report $n$

the UE is not required to update the CSI report for the triggered CSI
report $n$*.* $Z'$ is defined in \[6, TS 38.214\] and $\mu$ corresponds
to the smallest SCS configuration among the SCS configurations of the
PDCCHs scheduling the PUSCHs, the smallest SCS configuration of
aperiodic CSI-RSs associated with DCI formats provided by the PDCCHs
triggering the aperiodic CSI reports, and the smallest SCS configuration
of the overlapping PUCCHs and PUSCHs and $d = 2$ for $\mu = 0,1$,
$d = 3$ for $\mu = 2,$ and $d = 4$ for $\mu \geq 3$.

If a UE would transmit multiple PUCCHs in a slot that include HARQ-ACK
information, and/or SR, and/or CSI reports and any PUCCH with HARQ-ACK
information in the slot satisfies the above timing conditions and does
not overlap with any other PUCCH or PUSCH in the slot that does not
satisfy the above timing conditions, the UE multiplexes the HARQ-ACK
information, and/or SR, and/or CSI reports and determines corresponding
PUCCH(s) for transmission in the slot according to the following
pseudo-code. If the multiple PUCCHs do not include HARQ-ACK information
and do not overlap with any PUSCH transmission by the UE in response to
a DCI format detection by the UE, the timing conditions do not apply.

If

\- a UE is not provided *multi-CSI-PUCCH-ResourceList*, and

\- a resource for a PUCCH transmission with HARQ-ACK information in
response to SPS PDSCH reception and/or a resource for a PUCCH associated
with a SR occasion overlap in time with two resources for respective
PUCCH transmissions with two CSI reports, and

\- there is no resource for a PUCCH transmission with HARQ-ACK
information in response to a DCI format detection that overlaps in time
with any of the previous resources, and

\- the following pseudo code results to the UE attempting to determine a
single PUCCH resource from the HARQ-ACK and/or the SR resource and the
two PUCCH resources with CSI reports

the UE

\- multiplexes the HARQ-ACK information and/or the SR in the resource
for the PUCCH transmission with the CSI report having the higher
priority, and

\- does not transmit the PUCCH with the CSI report having the lower
priority

Set $Q$ to the set of resources for transmission of corresponding PUCCHs
in a single slot without repetitions where

\- a resource with earlier first symbol is placed before a resource with
later first symbol

\- for two resources with same first symbol, the resource with longer
duration is placed before the resource with shorter duration

\- for two resources with same first symbol and same duration, the
placement is arbitrary

\- the above three steps for the set $Q$ are according to a subsequent
pseudo-code for a function $order(Q)$

\- a resource for negative SR transmission that does not overlap with a
resource for HARQ-ACK or CSI transmission is excluded from set $Q$

\- if the UE is not provided *simultaneousHARQ-ACK-CSI* and resources
for transmission of HARQ-ACK information include PUCCH format 0 or PUCCH
format 2, resources that include PUCCH format 2, or PUCCH format 3, or
PUCCH format 4 for transmission of CSI reports are excluded from the set
$Q$ if they overlap with any resource from the resources for
transmission of HARQ-ACK information

\- if the UE is not provided *simultaneousHARQ-ACK-CSI* and at least one
of the resources for transmission of HARQ-ACK information includes PUCCH
format 1, PUCCH format 3, or PUCCH format 4

\- resources that include PUCCH format 3 or PUCCH format 4 for
transmission of CSI reports are excluded from the set $Q$

\- resources that include PUCCH format 2 for transmission of CSI reports
are excluded from the set $Q$ if they overlap with any resource from the
resources for transmission of HARQ-ACK information

Set $\text{C}(Q)$ to the cardinality of $Q$

Set $Q(j,0)$ to be the first symbol of resource $Q(j)$ in the slot

Set $L\left( Q(j) \right)$ to be the number of symbols of resource
$Q(j)$ in the slot

Set $j = 0$ - index of first resource in set $Q$

Set $o = 0$ - counter of overlapped resources

while $j \leq \text{C}(Q) - 1$

if

$j < \text{C}(Q) - 1$ and resource $Q(j - o)$ overlaps with resource
$Q(j + 1)$ and the resources in set $Q$ are of same priority index, or

$j < \text{C}(Q) - 1$ and resource $Q(j - o)$ overlaps with resource
$Q(j + 1)$, $o = 0$, the resources in set $Q$ are of different priority
indexes, and the UE is provided *uci-MuxWithDiffPrio*

then

$o = o + 1$;

$j = j + 1$;

else

if $o > 0$

determine a single resource for multiplexing UCI associated with
resources $\left\{ Q(j - o),Q(j - o + 1),\ldots,Q(j) \right\}$ as
described in clauses 9, 9.2.5.0, 9.2.5.1, 9.2.5.2, 9.2.5.3, and 18

set the index of the single resource to $j$

$$Q = Q\backslash\left\{ Q(j - o),Q(j - o + 1),\ldots,Q(j - 1) \right\}$$

$j = 0$ % start from the beginning after reordering unmerged resources
at next step

$o = 0$;

$order(Q)$ % function that re-orders resources in current set $Q$

Set $\text{C}(Q)$ to the cardinality of $Q$

else

$j = j + 1$;

end if

end if

end while

The function $order(Q)$ performs the following pseudo-code

{

$k = 0$;

while $k < \text{C}(Q) - 1$ % the next two while loops are to re-order
the unmerged resources

$l = 0$;

while $l < \text{C}(Q) - 1 - k$

if $Q(l,0) > Q(l + 1,0)$ OR
$\left( Q(l,0) = Q(l + 1,0)\& L(Q(l)) < L(Q(l + 1)) \right)$

$temp = Q(l)$;

$Q(l) = Q(l + 1)$;

$Q(l + 1) = temp$;

end if

$l = l + 1$;

end while

$k = k + 1$;

end while

}

For each PUCCH resource in the set $Q$ that satisfies the aforementioned
timing conditions, when applicable,

\- the UE transmits a PUCCH using the PUCCH resource if the PUCCH
resource does not overlap in time with a PUSCH transmission after
multiplexing UCI following the procedures described in clauses 9,
9.2.5.1, 9.2.5.2, 9.2.5.3 and 18

\- the UE multiplexes HARQ-ACK information and/or CSI reports in a PUSCH
if the PUCCH resource overlaps in time with a PUSCH transmission, as
described in clause 9.3, and does not transmit SR. In case the PUCCH
resource overlaps in time with multiple PUSCH transmissions, the PUSCH
for multiplexing HARQ-ACK information and/or CSI is selected as
described in clause 9. If the PUSCH transmission by the UE is not in
response to a DCI format detection and the UE multiplexes only CSI
reports, the timing conditions are not applicable

\- the UE does not expect the resource to overlap with a second resource
of a PUCCH transmission over multiple slots if the resource is obtained
from a group of resources that do not overlap with the second resource

clauses 9.2.5.0, 9.2.5.1, 9.2.5.2, 9.2.5.3 and 18 assume the following

\- resources for transmissions of UCI types, prior to multiplexing or
dropping, overlap in a slot

\- multiplexing conditions of corresponding UCI types in a single PUCCH
are satisfied, and

\- the UE does not transmit any PUSCH time-overlapping with PUCCH in the
slot.