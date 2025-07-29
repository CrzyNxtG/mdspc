### 7.7.1 Type 1 PH report

If a UE determines that a Type 1 power headroom report for an activated
serving cell is based on an actual PUSCH transmission then, for PUSCH
transmission occasion $i$ on active UL BWP $b$ of carrier $f$ of serving
cell $c$,

\- if for the active UL BWP $b$ of carrier $f$ of serving cell $c$, the
UE is provided

*- twoPHRMode,*

\- two SRS resource sets in *srs-ResourceSetToAddModList* or
*srs-ResourceSetToAddModListDCI-0-2* with usage set to \'codebook\' or
\'nonCodebook\',

\- *dl-OrJointTCI-StateList* or *TCI-UL-State* and is indicated a first
TCI-State or TCI-UL-State and a second TCI-State or TCI-UL-State, and

\- *multipanelSchemeSDM* or *multipanelSchemeSFN*

the UE computes the Type 1 power headroom report associated with the
k-th TCI-State or TCI-UL-State as

${PH}_{\text{type1},b,f,c,k}\left( i,j,q_{d},l \right) = \ P_{CMAX,f,c,k}(i) - \left\{ P_{\text{O\_PUSCH},b,f,c}(j) + 10\log_{10}\left( 2^{\mu}{\cdot M}_{RB,b,f,c}^{PUSCH}(i) \right) + \alpha_{b,f,c}(j) \cdot {PL}_{b,f,c}\left( q_{d} \right) + \mathrm{\Delta}_{TF,b,f,c}(i) + f_{b,f,c}(i,l) \right\}$
\[dB\]

\- else, the UE computes the Type 1 power headroom report as

${PH}_{\text{type1},b,f,c}\left( i,j,q_{d},l \right) = \ P_{\text{CMAX},f,c}(i) - \left\{ P_{\text{O\_PUSCH},b,f,c}(j) + 10\log_{10}\left( 2^{\mu}{\cdot M}_{RB,b,f,c}^{PUSCH}(i) \right) + \alpha_{b,f,c}(j) \cdot {PL}_{b,f,c}\left( q_{d} \right) + \mathrm{\Delta}_{TF,b,f,c}(i) + f_{b,f,c}(i,l) \right\}$
\[dB\]

where $P_{\text{CMAX},f,c}(i)$, $P_{CMAX,f,c,k}(i)$,
$P_{\text{O\_PUSCH},b,f,c}(j)$, $M_{RB,b,f,c}^{PUSCH}(i)$,
$\alpha_{b,f,c}(j)$, ${PL}_{b,f,c}(q_{d})$,
$\mathrm{\Delta}_{TF,b,f,c}(i)$ and $f_{b,f,c}(i,l)$ are defined in
clause 7.1.1.

If a UE is configured with multiple cells for PUSCH transmissions, where
a SCS configuration $\mu_{1}$ on active UL BWP $b_{1}$ of carrier
$f_{1}$ of serving cell $c_{1}$ is smaller than a SCS configuration
$\mu_{2}$ on active UL BWP $b_{2}$ of carrier $f_{2}$ of serving cell
$c_{2}$, and if the UE provides a Type 1 power headroom report in a
PUSCH transmission in a slot on active UL BWP $b_{1}$ that overlaps with
multiple slots on active UL BWP $b_{2}$, the UE provides a Type 1 power
headroom report for the first PUSCH, if any, on the first slot of the
multiple slots on active UL BWP $b_{2}$ that fully overlaps with the
slot on active UL BWP $b_{1}$. If a UE is configured with multiple cells
for PUSCH transmissions, where a same SCS configuration on active UL BWP
$b_{1}$ of carrier $f_{1}$ of serving cell $c_{1}$ and active UL BWP
$b_{2}$ of carrier $f_{2}$ of serving cell $c_{2}$, and if the UE
provides a Type 1 power headroom report in a PUSCH transmission in a
slot on active UL BWP $b_{1}$, the UE provides a Type 1 power headroom
report for the first PUSCH, if any, on the slot on active UL BWP $b_{2}$
that overlaps with the slot on active UL BWP $b_{1}$.

If a UE is configured with multiple cells for PUSCH transmissions and
provides a Type 1 power headroom report in a PUSCH transmission with
PUSCH repetition Type B having a nominal repetition that spans multiple
slots on active UL BWP $b_{1}$ and overlaps with one or more slots on
active UL BWP $b_{2}$, the UE provides a Type 1 power headroom report
for the first PUSCH, if any, on the first slot of the one or more slots
on active UL BWP $b_{2}$ that overlaps with the multiple slots of the
nominal repetition on active UL BWP $b_{1}$.

For a UE configured with EN-DC/NE-DC and capable of dynamic power
sharing, if E-UTRA Dual Connectivity PHR \[14, TS 36.321\] is triggered,
the UE provides power headroom of the first PUSCH, if any, on the
determined NR slot as described in clause 7.7.

If a UE is configured with multiple cells for PUSCH transmissions, the
UE does not consider for computation of a Type 1 power headroom report
in a first PUSCH transmission that includes an initial transmission of
transport block on active UL BWP $b_{1}$ of carrier $f_{1}$ of serving
cell $c_{1}$, a second PUSCH transmission on active UL BWP $b_{2}$ of
carrier $f_{2}$ of serving cell $c_{2}$ that overlaps with the first
PUSCH transmission if

\- the second PUSCH transmission is scheduled by a DCI format in a PDCCH
received in a second PDCCH monitoring occasion, and

\- the second PDCCH monitoring occasion is after a first PDCCH
monitoring occasion where the UE detects the earliest DCI format
scheduling an initial transmission of a transport block after a power
headroom report was triggered

or

\- the second PUSCH transmission is after the first uplink symbol of the
first PUSCH transmission minus ${T'}_{proc,2} = T_{proc,2}$ where
$T_{proc,2}$ is determined according to \[6, TS 38.214\] assuming
$d_{2,1} = 1$, $d_{2,2} = 0$, and with $\mu_{DL}$ corresponding to the
subcarrier spacing of the active downlink BWP of the scheduling cell for
a configured grant if the first PUSCH transmission is on a configured
grant after a power headroom report was triggered.

If the UE determines that a Type 1 power headroom report for an
activated serving cell is based on a reference PUSCH transmission then,
for PUSCH transmission occasion $i$ on active UL BWP $b$ of carrier $f$
of serving cell $c$,

\- if for the active UL BWP $b$ of carrier $f$ of serving cell $c$, the
UE is provided

*- twoPHRMode,*

\- two SRS resource sets in *srs-ResourceSetToAddModList* or
*srs-ResourceSetToAddModListDCI-0-2* with usage set to \'codebook\' or
\'nonCodebook\',

\- *dl-OrJointTCI-StateList* or *TCI-UL-State* and is indicated a first
TCI-State or TCI-UL-State and a second TCI-State or TCI-UL-State, and

\- *multipanelSchemeSDM* or *multipanelSchemeSFN*

the UE computes the Type 1 power headroom report associated with the
k-th TCI-State or TCI-UL-State as

${PH}_{\text{type1},b,f,c,k}\left( i,j,q_{d},l \right) = \ {\widetilde{P}}_{CMAX,f,c,k}(i) - \left\{ P_{\text{O\_PUSCH},b,f,c}(j) + \alpha_{b,f,c}(j) \cdot {PL}_{b,f,c}\left( q_{d} \right) + f_{b,f,c}(i,l) \right\}$
\[dB\]

\- else, the UE computes the Type 1 power headroom report as

${PH}_{\text{type1},b,f,c}\left( i,j,q_{d},l \right) = \ {\widetilde{P}}_{CMAX,f,c}(i) - \left\{ P_{\text{O\_PUSCH},b,f,c}(j) + \alpha_{b,f,c}(j) \cdot {PL}_{b,f,c}\left( q_{d} \right) + f_{b,f,c}(i,l) \right\}$
\[dB\]

where ${\widetilde{P}}_{\text{CMAX},f,c}(i)$ and
${\widetilde{P}}_{CMAX,f,c,k}(i)$ are computed assuming MPR=0 dB,
A-MPR=0 dB, P-MPR=0 dB. ∆T~C~ = 0 dB. MPR, A-MPR, P-MPR and ∆T~C~ are
defined in \[8-1, TS 38.101-1\], \[8-2, TS 38.101-2\], \[8-3, TS
38.101-3\] and \[8-5, TS 38.101-5\]. The remaining parameters are
defined in clause 7.1.1 and, if *ul-powerControl* is not provided,
$P_{\text{O\_PUSCH},b,f,c}(j)$ and $\alpha_{b,f,c}(j)$ are obtained
using $P_{\text{O\_NOMINAL,PUSCH},f,c}(0)$ and *p0-PUSCH-AlphaSetId* *=*
0, ${PL}_{b,f,c}(q_{d})$ is obtained using *pusch-PathlossReferenceRS-Id
=* 0, and $l = 0$. If *ul-powerControl* is provided and the UE is
indicated one TCI-State or TCI-UL-State, $P_{\text{O\_PUSCH},b,f,c}(j),$
$\alpha_{b,f,c}(j)$ and $l$ are obtained by *p0AlphaSetforPUSCH*
associated with the indicated *TCI-State* or *TCI-UL-State*,
${PL}_{b,f,c}(q_{d})$ is obtained by PL-RS associated with the indicated
*TCI-State* or *TCI-UL-State*. If *ul-powerControl* is provided and the
UE is indicated a first TCI-State or TCI-UL-State and a second TCI-State
or TCI-UL-State, $P_{\text{O\_PUSCH},b,f,c}(j),$ $\alpha_{b,f,c}(j)$ and
$l$ for ${PH}_{\text{type1},b,f,c,k}\left( i,j,q_{d},l \right)$ are
obtained by *p0AlphaSetforPUSCH* associated with the *k*-th indicated
*TCI-State* or *TCI-UL-State*, ${PL}_{b,f,c}(q_{d})$ is obtained by
PL-RS associated with the *k*-th indicated *TCI-State* or
*TCI-UL-State*. If *ul-powerControl* is provided, and if UE is indicated
a first *TCI-State* or *TCI-UL-State* and a second *TCI-State* or
*TCI-UL-State*, and if UE is not provided *twoPHRmode*,
$P_{\text{O\_PUSCH},b,f,c}(j),$ $\alpha_{b,f,c}(j)$ and $l$ for
${PH}_{\text{type1},b,f,c}\left( i,j,q_{d},l \right)$ are obtained by
*p0AlphaSetforPUSCH* associated with the first indicated *TCI-State* or
*TCI-UL-State*, ${PL}_{b,f,c}(q_{d})$ is obtained by PL-RS associated
with the first indicated *TCI-State* or *TCI-UL-State*. If the activated
serving cell is an SCell and parameter *preambleReceivedTargetPower* is
not configured for the cell, then the parameter
*preambleReceivedTargetPower* configured for the primary cell is
applied, where the parameter refers to the one configured for the
non-supplementary uplink carrier if the primary cell is configured with
two uplink carriers.

If a UE is configured with two UL carriers for a serving cell and the UE
determines a Type 1 power headroom report for the serving cell based on
a reference PUSCH transmission, the UE computes a Type 1 power headroom
report for the serving cell assuming a reference PUSCH transmission on
the UL carrier provided by *pusch-Config*. If the UE is provided
*pusch-Config* for both UL carriers, the UE computes a Type 1 power
headroom report for the serving cell assuming a reference PUSCH
transmission on the UL carrier provided by *pucch-Config*. If
*pucch-Config* is not provided to the UE for any of the two UL carriers,
the UE computes a Type 1 power headroom report for the serving cell
assuming a reference PUSCH transmission on the non-supplementary UL
carrier.

If a UE is not provided *twoPHRMode,* and is provided two SRS resource
sets in *srs-ResourceSetToAddModList* or
*srs-ResourceSetToAddModListDCI-0-2* with *usage* set to \'codebook\' or
\'nonCodebook\' on active UL BWP $b$ of carrier $f$ of serving cell $c$,
the UE provides one Type 1 power headroom report in a slot $n$. If the
Type 1 power headroom report is for an actual PUSCH repetition, the Type
1 power headroom report is for the first PUSCH repetition associated
with the first SRS resource set or the second SRS resource set that
overlaps with slot $n$.

If a UE is provided *twoPHRMode*, and is provided two SRS resource sets
in *srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' on active UL BWP $b$
of carrier $f$ of serving cell $c$, the UE provides two Type 1 power
headroom reports in a slot $n$, where

\- if the UE provides a first Type 1 power headroom report for an actual
PUSCH repetition of a PUSCH transmission starting earliest in slot $n$
that is associated with one SRS resource set,

\- if the UE transmits PUSCH repetitions associated with the other SRS
resource set in slot $n$, the UE provides a second Type 1 power headroom
report for a first actual PUSCH repetition associated with the other SRS
resource set that overlaps with slot $n$

\- else, the UE provides a second Type 1 power headroom report for a
reference PUSCH transmission associated with the other SRS resource set,
where

\- if the other SRS resource set is the first SRS resource set,
$P_{\text{O\_PUSCH},b,f,c}(j)$ and $\alpha_{b,f,c}(j)$ are obtained
using $P_{\text{O\_NOMINAL,PUSCH},f,c}(0)$ and *p0-PUSCH-AlphaSetId* *=*
0, ${PL}_{b,f,c}(q_{d})$ is obtained using *pusch-PathlossReferenceRS-Id
=* 0 if the UE is not provided *enablePL-RS-UpdateForPUSCH-SRS* or is
obtained from *PUSCH-PathlossReferenceRS-Id* mapped to
*sri-PUSCH-PowerControlId* = 0 of *sri-PUSCH-MappingToAddModList* if the
UE is provided *enablePL-RS-UpdateForPUSCH-SRS*, and $l = 0$. If the UE
is provided *dl-OrJointTCI-StateList* or *TCI-UL-State* that indicate a
first *TCI-State* or *TCI-UL-State* and a second *TCI-State* or
*TCI-UL-State*, the UE provides the second Type 1 power headroom report
using the *p0AlphaSetforPUSCH* and *pathlossReferenceRS-Id-r17* values
associated with the first *TCI-State* or *TCI-UL-State.*

\- else, $P_{\text{O\_PUSCH},b,f,c}(j)$ and $\alpha_{b,f,c}(j)$ are
obtained using $P_{\text{O\_NOMINAL,PUSCH},f,c}(0)$ and
*p0-PUSCH-AlphaSetId* *= 1*, ${PL}_{b,f,c}(q_{d})$ is obtained using
*pusch-PathlossReferenceRS-Id* = 1 if the UE is not provided
*enablePL-RS-UpdateForPUSCH-SRS* or is obtained from
*PUSCH-PathlossReferenceRS-Id* mapped to *sri-PUSCH-PowerControlId* = 0
of *sri-PUSCH-MappingToAddModList2* if the UE is provided
*enablePL-RS-UpdateForPUSCH-SRS*, and $l = 1$ if the UE is provided
*twoPUSCH-PC-AdjustmentStates*, or $l = 0$ if the UE is not provided
*twoPUSCH-PC-AdjustmentStates*. If the UE is provided
*dl-OrJointTCI-StateList* or *TCI-UL-State* that indicate a first
*TCI-State* or *TCI-UL-State* and a second *TCI-State* or
*TCI-UL-State*, the UE provides the second Type 1 power headroom report
using the *p0AlphaSetforPUSCH* and *pathlossReferenceRS-Id-r17* values
associated with the second *TCI-State* or *TCI-UL-State.*

\- else, if the UE provides a Type 1 power headroom report for a
reference PUSCH transmission associated with the first SRS resource set,
the UE provides a Type 1 power headroom report for a reference PUSCH
transmission associated with the second SRS resource set, where

\- for the first Type 1 power headroom report,
$P_{\text{O\_PUSCH},b,f,c}(j)$ and $\alpha_{b,f,c}(j)$ are obtained
using $P_{\text{O\_NOMINAL,PUSCH},f,c}(0)$ and *p0-PUSCH-AlphaSetId* *=*
0, ${PL}_{b,f,c}(q_{d})$ is obtained using *pusch-PathlossReferenceRS-Id
=* 0 if the UE is not provided *enablePL-RS-UpdateForPUSCH-SRS*, or is
obtained from the *PUSCH-PathlossReferenceRS-Id* mapped to
*sri-PUSCH-PowerControlId* = 0 of *sri-PUSCH-MappingToAddModList* if the
UE is provided *enablePL-RS-UpdateForPUSCH-SRS*, and $l = 0$.

\- for the second Type 1 power headroom report,
$P_{\text{O\_PUSCH},b,f,c}(j)$ and $\alpha_{b,f,c}(j)$ are obtained
using $P_{\text{O\_NOMINAL,PUSCH},f,c}(0)$ and *p0-PUSCH-AlphaSetId* *=
1*, ${PL}_{b,f,c}(q_{d})$ is obtained using
*pusch-PathlossReferenceRS-Id = 1* if the UE is not provided
*enablePL-RS-UpdateForPUSCH-SRS*, or is obtained from the
*PUSCH-PathlossReferenceRS-Id* mapped to *sri-PUSCH-PowerControlId* = 0
of *sri-PUSCH-MappingToAddModList2* if the UE is provided
*enablePL-RS-UpdateForPUSCH-SRS*, and $l = 1$ if the UE is provided
*twoPUSCH-PC-AdjustmentStates* or $l = 0$ if the UE is not provided
*twoPUSCH-PC-AdjustmentStates*

\- if a UE is provided *dl-OrJointTCI-StateList* or *TCI-UL-State* and
is indicated a first *TCI-State* or *TCI-UL-State* and a second
*TCI-State* or *TCI-UL-State*, the UE provides the first or the second
Type 1 power headroom reports using the *p0AlphaSetforPUSCH* and
*pathlossReferenceRS-Id-r17* values associated with the first
*TCI-State* or *TCI-UL-State* or with the second *TCI-State* or
*TCI-UL-State*, respectively, if the reference PUSCH transmission is
associated with the first *TCI-State* or *TCI-UL-State* or with the
second *TCI-State* or *TCI-UL-State*, respectively

If a UE is provided, for active UL BWP $b$ of carrier $f$ of serving
cell $c$,

\- *twoPHRMode*,

\- two SRS resource sets in *srs-ResourceSetToAddModList* or
*srs-ResourceSetToAddModListDCI-0-2* with usage set to \'codebook\' or
\'nonCodebook\',

\- *dl-OrJointTCI-StateList* or *TCI-UL-State* and is indicated a first
TCI-State or TCI-UL-State and a second TCI-State or TCI-UL-State, and

\- *multipanelSchemeSDM* or *multipanelSchemeSFN*

the UE provides

\- a first Type 1 power headroom report and a first configured maximum
output power associated with the first *TCI-State* or *TCI-UL-State* for
an actual PUSCH transmission using a spatial domain filter corresponding
only to the first *TCI-State* or *TCI-UL-State*, and a second Type 1
power headroom report and a second configured maximum output power
associated with the second *TCI-State* or *TCI-UL-State* for a reference
PUSCH transmission using the *p0AlphaSetforPUSCH* and
*pathlossReferenceRS-Id-r17* values associated with the second
*TCI-State* or *TCI-UL-State*

\- a second Type 1 power headroom report and a second configured maximum
output power associated with the second *TCI-State* or *TCI-UL-State*
for an actual PUSCH transmission using a spatial domain filter
corresponding only to the second *TCI-State* or *TCI-UL-State*, and a
first Type 1 power headroom report and a first configured maximum output
power associated with the first *TCI-State* or *TCI-UL-State* for a
reference PUSCH transmission using the *p0AlphaSetforPUSCH* and
*pathlossReferenceRS-Id-r17* values associated with the first
*TCI-State* or *TCI-UL-State*

\- a first Type 1 power headroom report and a first configured maximum
output power associated with the first *TCI-State* or *TCI-UL-State*,
and a second Type 1 power headroom report and a second configured
maximum output power associated with the second *TCI-State* or
*TCI-UL-State*, for an actual PUSCH transmission using a spatial domain
filter corresponding to the first *TCI-State* or *TCI-UL-State* and
using a spatial domain filter corresponding to the second *TCI-State* or
*TCI-UL-State*.

\- a first Type 1 power headroom report and a first configured maximum
output power associated with the first *TCI-State* or *TCI-UL-State* for
a reference PUSCH transmission using the *p0AlphaSetforPUSCH* and
*pathlossReferenceRS-Id-r17* values associated with the first
*TCI-State* or *TCI-UL-State*, and a second Type 1 power headroom report
and a second configured maximum output power associated with the second
*TCI-State* or *TCI-UL-State* for another reference PUSCH transmission
using the *p0AlphaSetforPUSCH* and *pathlossReferenceRS-Id-r17* values
associated with the second *TCI-State* or *TCI-UL-State*

For active UL BWP $b$ of carrier $f$ of serving cell $c,\ $if a UE is
not provided *twoPHRMode*, and

\- is provided two SRS resource sets in *srs-ResourceSetToAddModList* or
*srs-ResourceSetToAddModListDCI-0-2* with usage set to \'codebook\' or
\'nonCodebook\',

\- is provided *dl-OrJointTCI-StateList* or *TCI-UL-State* and is
indicated a first *TCI-State* or *TCI-UL-State* and a second *TCI-State*
or *TCI-UL-State*,

\- is not provided *coresetPoolIndex* or is provided *coresetPoolIndex*
with a value of 0 for first CORESETs on active DL BWPs of serving cells,

\- is provided *coresetPoolIndex* with a value of 1 for second CORESETs
on active DL BWPs of the serving cells, and

\- is provided *sTx-2Panel*,

the UE provides one Type 1 power headroom report for the actual PUSCH
transmission associated with *coresetPoolIndex* value 0 when there are
two actual PUSCH transmissions associated with different
*coresetPoolIndex* values overlap in time.

For active UL BWP $b$ of carrier $f$ of serving cell $c,\ i$f a UE is
not provided *twoPHRMode*, and is provided

\- two SRS resource sets in *srs-ResourceSetToAddModList* or
*srs-ResourceSetToAddModListDCI-0-2* with usage set to \'codebook\' or
\'nonCodebook\',

\- *dl-OrJointTCI-StateList* or *TCI-UL-State* and is indicated a first
*TCI-State* or *TCI-UL-State* and a second *TCI-State* or
*TCI-UL-State*, and

\- *multipanelSchemeSDM* or *multipanelSchemeSFN*

the UE provides one Type 1 power headroom report and one configured
maximum output power associated with the first *TCI-State* or
*TCI-UL-State* for an actual PUSCH transmission using a spatial domain
filter corresponding to the first *TCI-State* or *TCI-UL-State* and
using a spatial domain filter corresponding to the second *TCI-State* or
*TCI-UL-State.*

If a UE provides a Type 1 power headroom report for an activated serving
cell based on an actual PUSCH transmission, is provided
*phr-AssumedPUSCH-Reporting*, and
*dynamicTransformPrecoderFieldPresenceDCI-0-1* or
*dynamicTransformPrecoderFieldPresenceDCI-0-2* is set to enabled for the
active UL BWP of the serving cell, the UE provides

\- $P_{\text{CMAX},f,c}(i)$ based on any applicable maximum output power
reduction for an assumed PUSCH transmission with transform precoder
enabled, if supported, if transform precoder is disabled for the actual
PUSCH transmission, or

\- $P_{\text{CMAX},f,c}(i)$ based on any applicable maximum output power
reduction for an assumed PUSCH transmission with transform precoder
disabled, if supported, if the transform precoder is enabled for the
actual PUSCH transmission,

where all other parameters used for the calculation of
$P_{\text{CMAX},f,c}(i)$ of the assumed PUSCH transmission are same as
for the actual PUSCH transmission.