### 5.2.3 CSI reporting using PUSCH

A UE shall perform aperiodic CSI reporting using PUSCH on serving cell c
upon successful decoding of a DCI format 0_1 or DCI format 0_2 which
triggers an aperiodic CSI trigger state. A UE shall perform aperiodic
CSI reporting using PUSCH on the serving cell with the smallest serving
cell index scheduled by DCI format 0_3 which triggers an aperiodic CSI
trigger state.

When a DCI format 0_1 schedules two PUSCH allocations, the aperiodic CSI
report is carried on the second scheduled PUSCH. When a DCI format 0_1
schedules more than two PUSCH allocations, the aperiodic CSI report is
carried on the penultimate scheduled PUSCH.

An aperiodic CSI report carried on the PUSCH supports wideband, and
sub-band frequency granularities. An aperiodic CSI report carried on the
PUSCH supports Type I, Type II, Enhanced Type II, Further Enhanced Type
II Port Selection CSI, Enhanced Type II for CJT, Further Enhanced Type
II Port Selection for CJT, Enhanced Type II for predicted PMI, Further
Enhanced Type II Port Selection for predicted PMI and TDCP reporting.

A UE shall perform semi-persistent CSI reporting on the PUSCH upon
successful decoding of a DCI format 0_1 or DCI format 0_2 which
activates a semi-persistent CSI trigger state. DCI format 0_1 and DCI
format 0_2 contains a CSI request field which indicates the
semi-persistent CSI trigger state to activate or deactivate.
Semi-persistent CSI reporting on the PUSCH supports Type I, Type II with
wideband, and sub-band frequency granularities, Enhanced Type II,
Further Enhanced Type II Port Selection CSI, Enhanced Type II for CJT,
Further Enhanced Type II Port Selection for CJT, Enhanced Type II for
predicted PMI and Further Enhanced Type II Port Selection for predicted
PMI. The PUSCH resources and MCS shall be allocated semi-persistently by
an uplink DCI.

CSI reporting on PUSCH can be multiplexed with uplink data on PUSCH
except that semi-persistent CSI reporting on PUSCH activated by a DCI
format is not expected to be multiplexed with uplink data on the PUSCH.
CSI reporting on PUSCH can also be performed without any multiplexing
with uplink data from the UE.

Type I CSI feedback is supported for CSI Reporting on PUSCH. Type I
wideband and sub-band CSI is supported for CSI Reporting on the PUSCH.
Type II CSI is supported for CSI Reporting on the PUSCH.

For Type I, Type II, Enhanced Type II, Further Enhanced Type II Port
Selection CSI, Enhanced Type II for CJT, Further Enhanced Type II Port
Selection for CJT, Enhanced Type II for predicted PMI and Further
Enhanced Type II Port Selection for predicted PMI feedback on PUSCH, a
CSI report comprises of two parts. Part 1 has a fixed payload size and
is used to identify the number of information bits in Part 2. Part 1
shall be transmitted in its entirety before Part 2.

\- For Type I CSI feedback, Part 1 contains RI (if reported), CRI (if
reported), CQI for the first codeword (if reported). Part 2 contains PMI
(if reported), LI (if reported) and contains the CQI for the second
codeword (if reported) when RI is larger than 4. For a
*CSI-ReportConfig* configured with *codebookType* set to
\'typeI-SinglePanel\' and the corresponding CSI-RS Resource Set for
channel measurement configured with two Resource Groups and $N$ Resource
Pairs, Part 1 contains RI(s), CRI(s), CQI(s) for the first codeword and
is zero padded to a fixed payload size (if needed). Part 2 contains the
CQI(s) for the second codeword (if reported) when RI is larger than 4,
LIs (if reported) and PMI(s). For a *CSI-ReportConfig* that contains a
list of sub-configurations provided by
*csi-ReportSubConfigToAddModList*, for Type I CSI feedback for one or
more of the sub-configurations, Part 1 for a sub-configuration contains
corresponding RI (if reported), CRI (if reported) and CQI for the first
codeword (if reported). Part 2 for a sub-configuration contains the
corresponding CQI for the second codeword (if reported) when RI is
larger than 4, LI (if reported) and PMI (if reported).

\- For Type II CSI feedback, Part 1 contains RI (if reported), CQI, and
an indication of the number of non-zero wideband amplitude coefficients
per layer for the Type II CSI (see Clause 5.2.2.2.3). The fields of Part
1 -- RI (if reported), CQI, and the indication of the number of non-zero
wideband amplitude coefficients for each layer -- are separately
encoded. Part 2 contains the PMI and LI (if reported) of the Type II
CSI. The elements of $i_{1,1}$ are reported in the increasing order of
their indices, where the element of the lowest index is mapped to the
most significant bits and the element of the highest index is mapped to
the least significant bits. The elements of $i_{1,4,l}$, $i_{2,1,l}$ (if
reported) and $i_{2,2,l}$ (if reported) are reported in the increasing
order of their indices, $i = 0,1,\ldots,\ 2L - 1$, where the element of
the lowest index is mapped to the most significant bits and the element
of the highest index is mapped to the least significant bits. Part 1 and
2 are separately encoded.

\- For Enhanced Type II CSI feedback (see Clause 5.2.2.2.5), Further
Enhanced Type II Port Selection CSI feedback (see Clause 5.2.2.2.7),
Enhanced Type II for predicted PMI with $N_{4} = 1$ (see Clause
5.2.2.2.10) and Further Enhanced Type II Port Selection for predicted
PMI (see Clause 5.2.2.2.11), Part 1 contains RI (if reported), CQI, and
the total number of reported non-zero amplitude coefficients across
layers. The fields of Part 1 -- RI (if reported), CQI, and the total
number of reported non-zero amplitude coefficients across layers -- are
separately encoded. Part 2 contains the PMI of the Enhanced Type II,
Further Enhanced Type II Port Selection CSI, Enhanced Type II for
predicted PMI with $N_{4} = 1$ or Further Enhanced Type II Port
Selection for predicted PMI. Part 1 and 2 are separately encoded.

\- For Enhanced Type II for CJT (see Clause 5.2.2.2.8) and Further
Enhanced Type II Port Selection for CJT (see Clause 5.2.2.2.9), Part 1
contains RI (if reported), CQI, the total number of reported non-zero
amplitude coefficients across layers, the bitmap selecting $N$ CSI-RS
resources (if reported) and the selected combination of
$\{ L_{1},\ldots,L_{N_{TRP}}\}$ or
$\{\alpha_{1},\ldots,\alpha_{N_{TRP}}\}$ (if reported). The fields of
Part 1 -- RI (if reported), CQI, the total number of reported non-zero
amplitude coefficients across layers, the bitmap selecting $N$ CSI-RS
resources (if reported) and the selected combination of
$\{ L_{1},\ldots,L_{N_{TRP}}\}$ or
$\{\alpha_{1},\ldots,\alpha_{N_{TRP}}\}$ (if reported) -- are separately
encoded. Part 2 contains the PMI of the Enhanced Type II for CJT or
Further Enhanced Type II Port Selection for CJT. Part 1 and 2 are
separately encoded.

\- For Enhanced Type II for predicted PMI with $N_{4} > 1$ (see Clause
5.2.2.2.10), Part 1 contains RI (if reported), the CQI (if the higher
layer parameter *tdCQI* is set to \'1-1\' or \'1-2\') or the first CQI
(if the higher layer parameter *tdCQI* is set to \'2\') and the total
number of reported non-zero amplitude coefficients across layers. The
fields of Part 1 -- RI (if reported), CQI, and the total number of
reported non-zero amplitude coefficients across layers -- are separately
encoded. Part 2 contains the second CQI (if the higher layer parameter
*tdCQI* is set to \'2\') and the PMI of the Enhanced Type II for
predicted PMI with $N_{4} > 1$. Part 1 and 2 are separately encoded.

A Type II CSI report that is carried on the PUSCH shall be computed
independently from any Type II CSI report that is carried on the PUCCH
formats 3 or 4 (see Clause 5.2.4 and 5.2.2).

When the higher layer parameter *reportQuantity* is configured with one
of the values \'cri-RSRP\', \'ssb-Index-RSRP\', \'cri-SINR\' or
\'ssb-Index-SINR\', or \'cri-RSRP-Index\', \'ssb-Index-RSRP-Index\',
\'cri-SINR-Index\', \'ssb-Index-SINR-Index\', \'tdcp\', the CSI feedback
consists of a single part.

For both Type I and Type II reports configured for PUCCH but transmitted
on PUSCH, the determination of the payload for CSI part 1 and CSI part 2
follows that of PUCCH as described in Clause 5.2.4.

When CSI reporting on PUSCH comprises two parts, the UE may omit a
portion of the Part 2 CSI. Omission of Part 2 CSI is according to the
priority order shown in Table 5.2.3-1, where ![](media/image673.wmf) is
the number of CSI reports configured to be carried on the PUSCH.
Priority 0 is the highest priority and priority ![](media/image674.wmf)
is the lowest priority and the CSI report *n* corresponds to the CSI
report with the *n*th smallest Pri~i,CSI~(*y,k,c,s*) value among the
![](media/image673.wmf) CSI reports as defined in Clause 5.2.5. The
subbands for a given CSI report *n* indicated by the higher layer
parameter *csi-ReportingBand* with value \'1\' are numbered continuously
in increasing order with the lowest subband of *csi-ReportingBand* with
value set to \'1\' as subband 0. When omitting Part 2 CSI information
for a particular priority level, the UE shall omit all of the
information at that priority level, except for Part 2 subband CSI when
the corresponding CSI report contains one or more CSI sub-reports with
Part 2 each corresponding to a sub-configuration from a list of
sub-configurations provided by *csi-ReportSubConfigToAddModList*
contained in the *CSI-ReportConfig* as described in Clause 5.2.1.1.

\- For Enhanced Type II reports and Enhanced Type II for predicted PMI
configured with higher layer parameter $N_{4} = 1$, for a given CSI
report $n$, each reported element of indices $i_{2,4,l}$
$i_{2,5,l}\ $and $i_{1,7,l}$, indexed by $l,i$ and $f$, is associated
with a priority value
$Pri(l,i,f) = 2 \cdot L \cdot \upsilon \cdot \pi(f) + \upsilon \cdot i + l$,
with
$\pi(f) = min(2 \cdot n_{3,l}^{(f)},2 \cdot \left( N_{3} - n_{3,l}^{(f)} \right) - 1)$
with $l = 1,2,\ldots,\upsilon$, $i = 0,1,\ldots,2L - 1$, and
$f = 0,1,\ldots,M_{\upsilon} - 1$, and where $n_{3,l}^{(f)}$ is defined
in Clause 5.2.2.2.5. The element with the highest priority has the
lowest associated value $Pri(l,i,f)$. Omission of Part 2 CSI is
according to the priority order shown in Table 5.2.3-1, where

\- Group 0 includes indices $i_{1,1}$ (if reported), $i_{1,2}$ (if
reported) and $i_{1,8,l}$ ($l = 1,\ldots,\upsilon$).

\- Group 1 includes indices $i_{1,5}$ (if reported), $i_{1,6,l}$ (if
reported), the
$\upsilon 2LM_{\upsilon} - \left\lfloor K^{NZ}/2 \right\rfloor$ highest
priority elements of $i_{1,7,l}$, $i_{2,3,l}$, the
$\max\left( 0,\left\lceil \frac{K^{NZ}}{2} \right\rceil - \upsilon \right)$
highest priority elements of $i_{2,4,l}$ and the
$\max\left( 0,\left\lceil \frac{K^{NZ}}{2} \right\rceil - \upsilon \right)$
highest priority elements of $i_{2,5,l}$ ($l = 1,\ldots,\upsilon$).

\- Group 2 includes the $\left\lfloor K^{NZ}/2 \right\rfloor$ lowest
priority elements of $i_{1,7,l}$, the
$\min\left( K^{NZ} - \upsilon,\left\lfloor \frac{K^{NZ}}{2} \right\rfloor \right)$
lowest priority elements of $i_{2,4,l}$ and the
$\min\left( K^{NZ} - \upsilon,\left\lfloor \frac{K^{NZ}}{2} \right\rfloor \right)$
lowest priority elements of $i_{2,5,l}$ ($l = 1,\ldots,\upsilon$).

\- For Further Enhanced Type II Port Selection reports and Further
Enhanced Type II Port Selection for predicted PMI, for a given CSI
report $n$, each reported element of $i_{2,4,l}$ $i_{2,5,l}\ $and
$i_{1,7,l}$, indexed by $l$, $i$ and $f$, is associated with a priority
value
$Pri(l,i,f) = K_{1} \cdot \upsilon \cdot f + \upsilon \cdot i + l$, with
$l = 1,2,\ldots,\upsilon$, $i = 0,1,\ldots,K_{1} - 1$ and
$f = 0,\ldots,M - 1$. The element with the highest priority has the
lowest associated value $Pri(l,i,f)$. Omission of Part 2 CSI is
according to the priority order shown in Table 5.2.3-1, where:

\- Group 0 includes $i_{1,2}$ (if reported), $i_{1,8,l}$
($l = 1,\ldots,\upsilon$) and $i_{1,6}$ (if reported).

\- Group 1 includes the
$\upsilon K_{1}M - \left\lfloor K^{NZ}/2 \right\rfloor$ highest priority
elements of $i_{1,7,l}$ (if reported), $i_{2,3,l}$, the
$\max\left( 0,\left\lceil \frac{K^{NZ}}{2} \right\rceil - \upsilon \right)$
highest priority elements of $i_{2,4,l}$ and the
$\max\left( 0,\left\lceil \frac{K^{NZ}}{2} \right\rceil - \upsilon \right)$
highest priority elements of $i_{2,5,l}$ ($l = 1,\ldots,\upsilon$).

\- Group 2 includes the $\left\lfloor K^{NZ}/2 \right\rfloor$ lowest
priority elements of $i_{1,7,l}$ (if reported), the
$\min\left( K^{NZ} - \upsilon,\left\lfloor \frac{K^{NZ}}{2} \right\rfloor \right)$
lowest priority elements of $i_{2,4,l}$ and the
$\min\left( K^{NZ} - \upsilon,\left\lfloor \frac{K^{NZ}}{2} \right\rfloor \right)$
lowest priority elements of $i_{2,5,l}$ ($l = 1,\ldots,\upsilon$).

\- For Enhanced Type II for CJT reports, for a given CSI report $n$,
each reported element of $i_{2,4,l}$ $i_{2,5,l}\ $and $i_{1,7,l}$,
indexed by $l,i_{j}$, $f$ and $j$, is associated with a priority value
$Pri\left( l,i_{j},f,j \right) = 2 \cdot \sum_{k = 1}^{N_{0}}L_{\sigma_{k}} \cdot \upsilon \cdot \pi(f) + \upsilon \cdot \left( 2\sum_{k = 1}^{j - 1}L_{\sigma_{k}} + i_{j} \right) + l$,
with
$\pi(f) = min(2 \cdot n_{3,l}^{(f)},2 \cdot \left( N_{3} - n_{3,l}^{(f)} \right) - 1)$,
for $l = 1,\ldots,\upsilon$, $i_{j} = 0,1,\ldots,2L_{\sigma_{j}} - 1$,
$f = 0,1,\ldots,M_{\upsilon} - 1$ and $j = 1,\ldots,N_{0}$, and where
$n_{3,l}^{(f)}$ and $L_{\sigma_{j}}$ are defined in Clause 5.2.2.2.8.
The element with the highest priority has the lowest associated value
$Pri\left( l,i_{j},f,j \right)$. Omission of Part 2 CSI is according to
the priority order shown in Table 5.2.3-1, where

\- Group 0 includes indices $i_{1,1}$ (if reported), $i_{1,2}$ (if
reported) and $i_{1,8,l}$ ($l = 1,\ldots,\upsilon$).

\- Group 1 includes indices $i_{1,5}$ (if reported), $i_{1,6,l}$ (if
reported), the
$\upsilon 2M_{\upsilon}\sum_{k = 1}^{N_{0}}L_{\sigma_{k}} - \left\lfloor K^{NZ}/2 \right\rfloor$
highest priority elements of $i_{1,7,l}$, $i_{2,3,l}$, the
$\max\left( 0,\left\lceil \frac{K^{NZ}}{2} \right\rceil - \upsilon \right)$
highest priority elements of $i_{2,4,l}$, the
$\max\left( 0,\left\lceil \frac{K^{NZ}}{2} \right\rceil - \upsilon \right)$
highest priority elements of $i_{2,5,l}$ ($l = 1,\ldots,\upsilon$) and
$i_{1,9}$ (if reported).

\- Group 2 includes the $\left\lfloor K^{NZ}/2 \right\rfloor$ lowest
priority elements of $i_{1,7,l}$, the
$\min\left( K^{NZ} - \upsilon,\left\lfloor \frac{K^{NZ}}{2} \right\rfloor \right)$
lowest priority elements of $i_{2,4,l}$ and the
$\min\left( K^{NZ} - \upsilon,\left\lfloor \frac{K^{NZ}}{2} \right\rfloor \right)$
lowest priority elements of $i_{2,5,l}$ ($l = 1,\ldots,\upsilon$).

\- For Further Enhanced Type II Port Selection for CJT reports, for a
given CSI report $n$, each reported element of $i_{2,4,l}$
$i_{2,5,l}\ $and $i_{1,7,l}$, indexed by $l$, $i_{j}$, $f$ and $j$, is
associated with a priority value
$Pri\left( l,i_{j},f,j \right) = \sum_{k = 1}^{N_{0}}K_{1,\sigma_{k}} \cdot \upsilon \cdot f + \upsilon \cdot \left( \sum_{k = 1}^{j - 1}K_{1,\sigma_{k}} + i_{j} \right) + l$,
for $l = 1,\ldots,\upsilon$, $i_{j} = 0,1,\ldots,K_{1,\sigma_{j}} - 1$,
$f = 0,\ldots,M - 1$ and $j = 1,\ldots,N_{0}$, and where
$K_{1,\sigma_{j}}$ is defined in Clause 5.2.2.2.8. The element with the
highest priority has the lowest associated value
$Pri\left( l,i_{j},f,j \right)$. Omission of Part 2 CSI is according to
the priority order shown in Table 5.2.3-1, where:

\- Group 0 includes $i_{1,2}$ (if reported), $i_{1,8,l}$
($l = 1,\ldots,\upsilon$) and $i_{1,6}$ (if reported).

\- Group 1 includes the
$\upsilon M\sum_{k = 1}^{N_{0}}K_{1,\sigma_{k}} - \left\lfloor K^{NZ}/2 \right\rfloor$
highest priority elements of $i_{1,7,l}$ (if reported), $i_{2,3,l}$, the
$\max\left( 0,\left\lceil \frac{K^{NZ}}{2} \right\rceil - \upsilon \right)$
highest priority elements of $i_{2,4,l}$, the
$\max\left( 0,\left\lceil \frac{K^{NZ}}{2} \right\rceil - \upsilon \right)$
highest priority elements of $i_{2,5,l}$ ($l = 1,\ldots,\upsilon$) and
$i_{1,9}$ (if reported).

\- Group 2 includes the $\left\lfloor K^{NZ}/2 \right\rfloor$ lowest
priority elements of $i_{1,7,l}$ (if reported), the
$\min\left( K^{NZ} - \nu,\left\lfloor \frac{K^{NZ}}{2} \right\rfloor \right)$
lowest priority elements of $i_{2,4,l}$ and the
$\min\left( K^{NZ} - \upsilon,\left\lfloor \frac{K^{NZ}}{2} \right\rfloor \right)$
lowest priority elements of $i_{2,5,l}$ ($l = 1,\ldots,\upsilon$).

\- For Enhanced Type II for predicted PMI configured with $N_{4} > 1$,
for a given CSI report $n$, each reported element of $i_{2,4,l}$
$i_{2,5,l}\ $and $i_{1,7,l}$, indexed by $l,i$, $f$ and $j$, is
associated with a priority value
$Pri(l,i,f,j) = 2L \cdot \upsilon \cdot M_{\nu} \cdot \tau + 2L \cdot \upsilon \cdot f + \upsilon \cdot i + l$,
for $l = 1,\ldots,\upsilon$, $i = 0,1,\ldots,2L - 1$,
$f = 0,1,\ldots,M_{\upsilon} - 1$ and $\tau = 0,1$. The element with the
highest priority has the lowest associated value $Pri(l,i,f,j)$.
Omission of Part 2 CSI is according to the priority order shown in Table
5.2.3-1, where

\- Group 0 includes indices $i_{1,1}$ (if reported), $i_{1,2}$ (if
reported), $i_{1,8,l}$ ($l = 1,\ldots,\upsilon$) and the second wideband
CQI (if reported).

\- Group 1 includes indices $i_{1,5}$ (if reported), $i_{1,6,l}$ (if
reported), the
$\upsilon 2LM_{\upsilon}Q - \left\lfloor K^{NZ}/2 \right\rfloor$ highest
priority elements of $i_{1,7,l}$, $i_{2,3,l}$, the
$\max\left( 0,\left\lceil \frac{K^{NZ}}{2} \right\rceil - \upsilon \right)$
highest priority elements of $i_{2,4,l}$, the
$\max\left( 0,\left\lceil \frac{K^{NZ}}{2} \right\rceil - \upsilon \right)$
highest priority elements of $i_{2,5,l}$ ($l = 1,\ldots,\upsilon$),
$i_{1,10,l}$ (if reported) and the second subband CQI of even subbands
(if reported).

\- Group 2 includes the $\left\lfloor K^{NZ}/2 \right\rfloor$ lowest
priority elements of $i_{1,7,l}$, the
$\min\left( K^{NZ} - \upsilon,\left\lfloor \frac{K^{NZ}}{2} \right\rfloor \right)$
lowest priority elements of $i_{2,4,l}$, the
$\min\left( K^{NZ} - \upsilon,\left\lfloor \frac{K^{NZ}}{2} \right\rfloor \right)$
lowest priority elements of $i_{2,5,l}$ ($l = 1,\ldots,\upsilon$) and
the second subband CQI of odd subbands (if reported).

\- For a Reporting Setting for which the *CSI-ReportConfig* contains a
list of sub-configurations provided by
*csi-ReportSubConfigToAddModList*, for a corresponding CSI report $n$
which contains one or more CSI sub-reports, omission of Part 2 subband
CSI is done at a sub-configuration level within the same priority level
defined by Table 5.2.3-1 where a sub-configuration with an index,
provided by *reportSubConfigId*, with lower value has higher priority.

Table 5.2.3-1: Priority reporting levels for Part 2 CSI

+-----------------------------------------------------------------------+
| Priority 0:                                                           |
|                                                                       |
| For CSI reports 1 to $N_{Rep}$, Group 0 CSI for CSI reports           |
| configured as \'typeII-r16\', \'typeII-PortSelection-r16\',           |
| \'typeII-PortSelection-r17\', \'typeII-CJT-r18\',                     |
| \'typeII-CJT-PortSelection-r18\', \'typeII-Doppler-r18\' or           |
| \'typeII-Doppler-PortSelection-r18\'; Part 2 wideband CSI for CSI     |
| reports configured otherwise                                          |
+:=====================================================================:+
| Priority 1:                                                           |
|                                                                       |
| Group 1 CSI for CSI report 1, if configured as \'typeII-r16\',        |
| \'typeII-PortSelection-r16\', \'typeII-PortSelection-r17\',           |
| \'typeII-CJT-r18\', \'typeII-CJT-PortSelection-r18\',                 |
| \'typeII-Doppler-r18\' or \'typeII-Doppler-PortSelection-r18\'; Part  |
| 2 subband CSI of even subbands for CSI report 1, if configured        |
| otherwise                                                             |
+-----------------------------------------------------------------------+
| Priority 2:                                                           |
|                                                                       |
| Group 2 CSI for CSI report 1, if configured as \'typeII-r16\',        |
| \'typeII-PortSelection-r16\', \'typeII-PortSelection-r17\',           |
| \'typeII-CJT-r18\', \'typeII-CJT-PortSelection-r18\',                 |
| \'typeII-Doppler-r18\' or \'typeII-Doppler-PortSelection-r18\'; Part  |
| 2 subband CSI of odd subbands for CSI report 1, if configured         |
| otherwise                                                             |
+-----------------------------------------------------------------------+
| Priority 3:                                                           |
|                                                                       |
| Group 1 CSI for CSI report 2, if configured as \'typeII-r16\',        |
| \'typeII-PortSelection-r16\', \'typeII-PortSelection-r17\',           |
| \'typeII-CJT-r18\', \'typeII-CJT-PortSelection-r18\',                 |
| \'typeII-Doppler-r18\' or \'typeII-Doppler-PortSelection-r18\'; Part  |
| 2 subband CSI of even subbands for CSI report 2, if configured        |
| otherwise                                                             |
+-----------------------------------------------------------------------+
| Priority 4:                                                           |
|                                                                       |
| Group 2 CSI for CSI report 2, if configured as \'typeII-r16\',        |
| \'typeII-PortSelection-r16\', \'typeII-PortSelection-r17\',           |
| \'typeII-CJT-r18\', \'typeII-CJT-PortSelection-r18\',                 |
| \'typeII-Doppler-r18\' or \'typeII-Doppler-PortSelection-r18\'; Part  |
| 2 subband CSI of odd subbands for CSI report 2, if configured         |
| otherwise                                                             |
+-----------------------------------------------------------------------+
| ⁞                                                                     |
+-----------------------------------------------------------------------+
| Priority $2N_{Rep} - 1$:                                              |
|                                                                       |
| Group 1 CSI for CSI report $N_{Rep}$, if configured as                |
| \'typeII-r16\', \'typeII-PortSelection-r16\',                         |
| \'typeII-PortSelection-r17\', \'typeII-CJT-r18\',                     |
| \'typeII-CJT-PortSelection-r18\', \'typeII-Doppler-r18\' or           |
| \'typeII-Doppler-PortSelection-r18\'; Part 2 subband CSI of even      |
| subbands for CSI report $N_{Rep}$, if configured otherwise            |
+-----------------------------------------------------------------------+
| Priority $2N_{Rep}$:                                                  |
|                                                                       |
| Group 2 CSI for CSI report $N_{Rep}$, if configured as                |
| \'typeII-r16\', \'typeII-PortSelection-r16\',                         |
| \'typeII-PortSelection-r17\', \'typeII-CJT-r18\',                     |
| \'typeII-CJT-PortSelection-r18\', \'typeII-Doppler-r18\' or           |
| \'typeII-Doppler-PortSelection-r18\'; Part 2 subband CSI of odd       |
| subbands for CSI report $N_{Rep}$, if configured otherwise            |
+-----------------------------------------------------------------------+

When the UE is scheduled to transmit a transport block on PUSCH not
using repetition type B multiplexed with a CSI report(s) and if
*numberOfSlotsTBoMS* is not present in the resource allocation table, or
if *numberOfSlotsTBoMS* is present in the resource allocation table and
the value of *numberOfSlotsTBoMS* in the row indicated by the Time
domain resource assignment field in DCI is equal to 1, Part 2 CSI is
omitted only when ![](media/image675.wmf){width="2.8506944444444446in"
height="0.4673611111111111in"} is larger than
$\left\lceil \alpha \bullet \sum_{l = 0}^{N_{\text{symb,all}}^{\text{PUSCH}} - 1}{M_{\text{sc}}^{\text{UCI}}(l)} \right\rceil - Q_{ACK/CG - UCI}' - Q_{\text{CSI-1}}'$
or
$\left\lceil \alpha \bullet \sum_{l = 0}^{N_{\text{symb,all}}^{\text{PUSCH}} - 1}{M_{\text{sc}}^{\text{UCI}}(l)} \right\rceil - Q_{ACK/UTO - UCI}' - Q_{\text{CSI-1}}'\ $when
the higher layer parameter *nrofBitsInUTO-UCI* is configured, where
parameters ![](media/image676.wmf){width="0.38958333333333334in"
height="0.2534722222222222in"}, ![](media/image677.wmf){width="0.325in"
height="0.23402777777777778in"},
![](media/image678.wmf){width="0.49375in"
height="0.2465277777777778in"},
![](media/image679.wmf){width="0.4284722222222222in"
height="0.2534722222222222in"},
![](media/image680.wmf){width="0.50625in"
height="0.2534722222222222in"},
![](media/image681.wmf){width="0.5194444444444445in"
height="0.2534722222222222in"},
![](media/image682.wmf){width="0.22708333333333333in"
height="0.2534722222222222in"},
![](media/image683.wmf){width="0.44166666666666665in"
height="0.2534722222222222in"}, $Q_{ACK/CG - UCI}'$,
$Q_{ACK/UTO - UCI}'\ $and
![](media/image684.wmf){width="0.15555555555555556in"
height="0.1361111111111111in"}are defined in Clause 6.3.2.4 of \[5, TS
38.212\].

Part 2 CSI is omitted level by level, beginning with the lowest priority
level until the lowest priority level is reached which causes the
![](media/image675.wmf){width="2.8506944444444446in"
height="0.4673611111111111in"} to be less than or equal to
$\left\lceil \alpha \bullet \sum_{l = 0}^{N_{\text{symb,all}}^{\text{PUSCH}} - 1}{M_{\text{sc}}^{\text{UCI}}(l)} \right\rceil - Q_{ACK/CG - UCI}' - Q_{\text{CSI-1}}'$
or
$\left\lceil \alpha \bullet \sum_{l = 0}^{N_{symb,all}^{PUSCH} - 1}{M_{sc}^{UCI}(l)} \right\rceil - Q_{ACK/UTO - UCI}' - Q_{CSI - 1}'$
when the higher layer parameter *nrofBitsInUTO-UCI* is configured.

When the UE is scheduled to transmit a transport block on PUSCH not
using repetition type B multiplexed with a CSI report(s) and if
*numberOfSlotsTBoMS* is present in the resource allocation table and the
value of *numberOfSlotsTBoMS* in the row indicated by the Time domain
resource assignment field in DCI is larger than 1, Part 2 CSI is omitted
only when
$\left\lceil \frac{\left( O_{CSI - 2} + L_{CSI - 2} \right) \bullet \beta_{offset}^{PUSCH} \bullet \sum_{l = 0}^{N_{symb,all}^{PUSCH} - 1}{M_{sc}^{UCI}(l)}}{\frac{1}{N_{s}}\sum_{r = 0}^{C_{UL - SCH} - 1}K_{r}} \right\rceil$
is larger than
$\left\lceil \alpha \bullet \sum_{l = 0}^{N_{\text{symb,all}}^{\text{PUSCH}} - 1}{M_{\text{sc}}^{\text{UCI}}(l)} \right\rceil - Q_{\frac{ACK}{CG} - UCI}' - Q_{\text{CSI-1}}'\ or\ \left\lceil \alpha \bullet \sum_{l = 0}^{N_{symb,all}^{PUSCH} - 1}{M_{sc}^{UCI}(l)} \right\rceil - Q_{ACK/UTO - UCI}' - Q_{CSI - 1}'\ $
when the higher layer parameter *nrofBitsInUTO-UCI* is configured, where
parameters ![](media/image676.wmf){width="0.38958333333333334in"
height="0.2534722222222222in"}, ![](media/image677.wmf){width="0.325in"
height="0.23402777777777778in"},
![](media/image678.wmf){width="0.49375in"
height="0.2465277777777778in"},
![](media/image679.wmf){width="0.4284722222222222in"
height="0.2534722222222222in"},
![](media/image680.wmf){width="0.50625in"
height="0.2534722222222222in"},
![](media/image681.wmf){width="0.5194444444444445in"
height="0.2534722222222222in"},
![](media/image682.wmf){width="0.22708333333333333in"
height="0.2534722222222222in"},
$N_{s}\ $,![](media/image683.wmf){width="0.44166666666666665in"
height="0.2534722222222222in"}, $Q_{ACK/CG - UCI}'$,
$Q_{ACK/UTO - UCI}'$ and
![](media/image684.wmf){width="0.15555555555555556in"
height="0.1361111111111111in"}are defined in Clause 6.3.2.4 of \[5, TS
38.212\].

Part 2 CSI is omitted level by level, beginning with the lowest priority
level until the lowest priority level is reached which causes the
$\left\lceil \frac{\left( O_{CSI - 2} + L_{CSI - 2} \right) \bullet \beta_{offset}^{PUSCH} \bullet \sum_{l = 0}^{N_{symb,all}^{PUSCH} - 1}{M_{sc}^{UCI}(l)}}{\frac{1}{N_{s}}\sum_{r = 0}^{C_{UL - SCH} - 1}K_{r}} \right\rceil\ $to
be less than or equal to
$\left\lceil \alpha \bullet \sum_{l = 0}^{N_{\text{symb,all}}^{\text{PUSCH}} - 1}{M_{\text{sc}}^{\text{UCI}}(l)} \right\rceil - Q_{ACK/CG - UCI}' - Q_{\text{CSI-1}}'$
or
$\left\lceil \alpha \bullet \sum_{l = 0}^{N_{\text{symb,all}}^{\text{PUSCH}} - 1}{M_{\text{sc}}^{\text{UCI}}(l)} \right\rceil - Q_{ACK/UTO - UCI}' - Q_{\text{CSI-1}}'$
when the higher layer parameter *nrofBitsInUTO-UCI* is configured.

When the UE is scheduled to transmit a transport block on PUSCH using
repetition type B multiplexed with a CSI report(s), Part 2 CSI is
omitted only when

$$\left\lceil \frac{\left( O_{\text{CSI-2}} + L_{\text{CSI-2}} \right) \bullet \beta_{\text{offset}}^{\text{PUSCH}} \bullet \sum_{l = 0}^{N_{\text{symb,nominal}}^{\text{PUSCH}} - 1}{M_{\text{sc,nominal}}^{\text{UCI}}(l)}}{\sum_{r = 0}^{C_{\text{UL-SCH}} - 1}K_{r}} \right\rceil$$

is larger than

$\min\left\{ \begin{array}{r}
\left\lceil \alpha \bullet \sum_{l = 0}^{N_{\text{symb,nominal}}^{\text{PUSCH}} - 1}{M_{\text{sc,nominal}}^{\text{UCI}}(l)} \right\rceil - Q_{ACK/CG - UCI}' - Q_{\text{CSI-1}}'\ ,\ \  \\
\sum_{l = 0}^{N_{\text{symb,actual}}^{\text{PUSCH}} - 1}{M_{\text{sc,actual}}^{\text{UCI}}(l)} - Q_{ACK/CG - UCI}' - Q_{\text{CSI-1}}'
\end{array} \right\}$,

or

$\min\left\{ \begin{array}{r}
\left\lceil \alpha \bullet \sum_{l = 0}^{N_{symb,nominal}^{PUSCH} - 1}{M_{sc,nominal}^{UCI}(l)} \right\rceil - Q_{ACK/UTO - UCI}' - Q_{CSI - 1}'\ ,\ \  \\
\sum_{l = 0}^{N_{symb,actual}^{PUSCH} - 1}{M_{sc,actual}^{UCI}(l)} - Q_{ACK/UTO - UCI}' - Q_{CSI - 1}'
\end{array} \right\}$,

when the higher layer parameter *nrofBitsInUTO-UCI* is configured, where
parameters ![](media/image676.wmf){width="0.38958333333333334in"
height="0.2534722222222222in"}, ![](media/image677.wmf){width="0.325in"
height="0.23402777777777778in"},
![](media/image678.wmf){width="0.49375in"
height="0.2465277777777778in"}, $N_{symb\text{,nominal}}^{PUSCH}$,
$N_{symb\text{,actual}}^{PUSCH}$, $M_{sc\text{,nominal}}^{UCI}(l)$,
$M_{sc\text{,actual}}^{UCI}(l)$,
![](media/image681.wmf){width="0.5194444444444445in"
height="0.2534722222222222in"},
![](media/image682.wmf){width="0.22708333333333333in"
height="0.2534722222222222in"}, $Q_{ACK/CG - UCI}'$,
$Q_{ACK/UTO - UCI}',\ $![](media/image683.wmf){width="0.44166666666666665in"
height="0.2534722222222222in"}, and
![](media/image684.wmf){width="0.15555555555555556in"
height="0.1361111111111111in"}are defined in Clause 6.3.2.4 of \[5, TS
38.212\].

Part 2 CSI is omitted level by level, beginning with the lowest priority
level until the lowest priority level is reached which causes

$$\left\lceil \frac{\left( O_{\text{CSI-2}} + L_{\text{CSI-2}} \right) \bullet \beta_{\text{offset}}^{\text{PUSCH}} \bullet \sum_{l = 0}^{N_{\text{symb,nominal}}^{\text{PUSCH}} - 1}{M_{\text{sc,nominal}}^{\text{UCI}}(l)}}{\sum_{r = 0}^{C_{\text{UL-SCH}} - 1}K_{r}} \right\rceil$$

to be less than or equal to

$\min\left\{ \begin{array}{r}
\left\lceil \alpha \bullet \sum_{l = 0}^{N_{\text{symb,nominal}}^{\text{PUSCH}} - 1}{M_{\text{sc,nominal}}^{\text{UCI}}(l)} \right\rceil - Q_{ACK/CG - UCI}' - Q_{\text{CSI-1}}'\ ,\ \  \\
\sum_{l = 0}^{N_{\text{symb,actual}}^{\text{PUSCH}} - 1}{M_{\text{sc,actual}}^{\text{UCI}}(l)} - Q_{ACK/CG - UCI}' - Q_{\text{CSI-1}}'
\end{array} \right\}$,

or

$\min\left\{ \begin{array}{r}
\left\lceil \alpha \bullet \sum_{l = 0}^{N_{symb,nominal}^{PUSCH} - 1}{M_{sc,nominal}^{UCI}(l)} \right\rceil - Q_{ACK/UTO - UCI}' - Q_{CSI - 1}'\ ,\ \  \\
\sum_{l = 0}^{N_{symb,actual}^{PUSCH} - 1}{M_{sc,actual}^{UCI}(l)} - Q_{ACK/UTO - UCI}' - Q_{CSI - 1}'
\end{array} \right\}$,

when the higher layer parameter *nrofBitsInUTO-UCI* is configured.

When part 2 CSI is transmitted on PUSCH with no transport block, lower
priority bits are omitted until Part 2 CSI code rate, which is given by
$\left( O_{\text{CSI-2}} + L_{\text{CSI-2}} \right)/(N_{L} \cdot Q'_{\text{CSI,2}} \cdot Q_{m})$
where $O_{\text{CSI-2}}$, $L_{\text{CSI-2}}$,
$N_{L},Q'_{\text{CSI,2}},Q_{m}$ are given in clause 6.3.2.4 of \[5,
38.212\] before HARQ-ACK puncturing part 2 CSI if any, is below a
threshold code rate ![](media/image685.wmf)lower than one, where

![](media/image686.wmf)

\- ![](media/image687.wmf)is the CSI offset value from Table 9.3-2 of
\[6, TS 38.213\]

\- *R* is signaled code rate in DCI

If the UE is in an active semi-persistent CSI reporting configuration on
PUSCH, the CSI reporting is deactivated when either the downlink BWP or
the uplink BWP is changed. Another activation command is required to
enable the semi-persistent CSI reporting.