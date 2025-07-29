### 7.1.1 UE behaviour

If a UE transmits a PUSCH on active UL BWP $b$ of carrier $f$ of serving
cell $c$ using parameter set configuration with index $j$ and PUSCH
power control adjustment state with index $l$

\- if the UE is indicated a first *TCI-State* or *TCI-UL-State* and a
second *TCI-State* or *TCI-UL-State*, and is configured with
*multipanelSchemeSDM* or *multipanelSchemeSFN* or *sTx-2Panel*, and the
UE determines to apply both the first *TCI-State* or *TCI-UL-State* and
the second *TCI-State* or *TCI-UL-S*tate in PUSCH transmission occasion
$i$, the UE determines the PUSCH transmission power
$P_{\text{PUSCH},b,f,c,\ k}(i,j,q_{d},l)$ for the k-th indicated
*TCI-State* or *TCI-UL-State* as

$P_{\text{PUSCH},b,f,c,k}\left( i,j,q_{d},l \right) = \min\begin{Bmatrix}
P_{\text{CMAX},f,c,k}(i) \\
P_{O\_ PUSCH,b,f,c}(j) + 10\log_{10}\left( 2^{\mu} \bullet M_{RB,b,f,c}^{PUSCH}(i) \right) + \alpha_{b,f,c}(j) \bullet {PL}_{b,f,c}\left( q_{d} \right) + \mathrm{\Delta}_{TF,b,f,c}(i) + f_{b,f,c}(i,l)\ \ 
\end{Bmatrix}$ \[dBm\]

\- else, the UE determines the PUSCH transmission power
$P_{\text{PUSCH},b,f,c}(i,j,q_{d},l)$ in PUSCH transmission occasion $i$
as

$P_{\text{PUSCH},b,f,c}\left( i,j,q_{d},l \right) = \min\begin{Bmatrix}
P_{\text{CMAX},f,c}(i) \\
P_{O\_ PUSCH,b,f,c}(j) + 10\log_{10}\left( 2^{\mu} \bullet M_{RB,b,f,c}^{PUSCH}(i) \right) + \alpha_{b,f,c}(j) \bullet {PL}_{b,f,c}\left( q_{d} \right) + \mathrm{\Delta}_{TF,b,f,c}(i) + f_{b,f,c}(i,l)\ \ 
\end{Bmatrix}$ \[dBm\]

where,

\- $P_{\text{CMAX},f,c,k}(i)$ is the UE configured maximum output power
for the k-th indicated *TCI-State* or *TCI-UL-State* defined in \[8-2,
TS 38.101-2\] for carrier $f$ of serving cell $c$ in PUSCH transmission
occasion $i$ .

\- $P_{\text{CMAX},f,c}(i)$ is the UE configured maximum output power
defined in \[8-1, TS 38.101-1\], \[8-2, TS 38.101-2\], \[8-3, TS
38.101-3\] and \[8-5, TS 38.101-5\] for carrier $f$ of serving cell $c$
in PUSCH transmission occasion $i$.

\- $P_{\text{O\_PUSCH},b,f,c}(j)$ is a parameter composed of the sum of
a component $P_{\text{O\_NOMINAL,PUSCH},f,c}(j)$ and a component
$P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ where
$j \in \left\{ 0,1,\ldots,J - 1 \right\}$.

\- If a UE established dedicated RRC connection using a Type-1 random
access procedure, as described in clause 8, and is not provided
*P0-PUSCH-AlphaSet* or for a PUSCH (re)transmission corresponding to a
RAR UL grant as described in clause 8.3,

$j = 0$, $P_{\text{O\_UE\_PUSCH},b,f,c}(0) = 0$, and
$P_{\text{O\_NOMINAL,PUSCH},f,c}(0) = P_{\text{O\_PRE}} + \mathrm{\Delta}_{PREAMBLE,Msg3}$,

> where $P_{\text{O\_PRE}}$ is provided by *preambleReceivedTargetPower*
> \[11, TS 38.321\] and $\Delta_{PREAMBLE\_ Msg3}$ is provided by
> *msg3-DeltaPreamble* or *deltaPreamble*, or
> $\mathrm{\Delta}_{PREAMBLE,Msg3} = 0$ dB if *msg3-DeltaPreamble* and
> *deltaPreamble* are not provided, for carrier $f$ of serving cell $c$

\- If a UE established dedicated RRC connection using a Type-2 random
access procedure, as described in clause 8, and is not provided
*P0-PUSCH-AlphaSet*, or for a PUSCH transmission for Type-2 random
access procedure as described in clause 8.1A,

$j = 0$, $P_{\text{O\_UE\_PUSCH,}b,f,c}(0) = 0$, and
$P_{\text{O\_NOMINAL\_PUSCH,}f,c}(0) = P_{\text{O\_PRE}} + \Delta_{MsgA\_ PUSCH}$,

> where $P_{\text{O\_PRE}}$ is provided by
> *msgA-preambleReceivedTargetPower*, or by
> *preambleReceivedTargetPower* if *msgA-preambleReceivedTargetPower* is
> not provided and $\Delta_{MsgA\_ PUSCH}$ is provided by
> *msgA-DeltaPreamble* or *deltaPreamble*, or
> $\Delta_{MsgA\_ PUSCH} = \Delta_{PREAMBLE\_ Msg3}$ dB if
> *msgA-DeltaPreamble* and *deltaPreamble* are not provided, for carrier
> $f$ of serving cell $c$

\- For a PUSCH (re)transmission configured by *ConfiguredGrantConfig*,
$j = 1$, $P_{\text{O\_NOMINAL,PUSCH},f,c}(1)$ is provided by
*p0-NominalWithoutGrant*, or
$P_{\text{O\_NOMINAL,PUSCH},f,c}(1) = P_{\text{O\_NOMINAL,PUSCH},f,c}(0)$
if *p0-NominalWithoutGrant* is not provided.

\- If the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and is provided
*p0-PUSCH-Alpha2*, for a retransmission of a configured grant Type 1
PUSCH, or for activation or retransmission of a configured grant Type 2
PUSCH, scheduled by a DCI format that includes a SRS resource set
indicator field, and for active UL BWP $b$ of carrier $f$ of serving
cell

> \- If the SRS resource set indicator value is 00, first
> $P_{\text{O\_UE\_PUSCH},b,f,c}(1)$ value is provided by the value of
> *p0-PUSCH-Alpha* in *ConfiguredGrantConfig*.
>
> \- If the SRS resource set indicator value is 01, second
> $P_{\text{O\_UE\_PUSCH},b,f,c}(1)$ value is provided by the value of
> *p0-PUSCH-Alpha2* in *ConfiguredGrantConfig*.
>
> \- If the SRS resource set indicator value is 10 or 11, first and
> second $P_{\text{O\_UE\_PUSCH},b,f,c}(1)$ values that are respectively
> associated with the first and second SRS resource set are respectively
> provided by the values of *p0-PUSCH-Alpha* and by *p0-PUSCH-Alpha2* in
> *ConfiguredGrantConfig*.

\- else if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and is provided
*p0-PUSCH-Alpha2*, for a transmission of a configured grant Type 1 PUSCH
and for active UL BWP $b$ of carrier $f$ of serving cell

> \- a first $P_{\text{O\_UE\_PUSCH},b,f,c}(1)$ value is provided by the
> value of *p0-PUSCH-Alpha* in *ConfiguredGrantConfig* that is
> associated with the first *srs-ResourceIndicator* in
> *rrc-ConfiguredUplinkGrant*
>
> \- a second $P_{\text{O\_UE\_PUSCH},b,f,c}(1)$ value is provided by
> the value of *p0-PUSCH-Alpha2* in *ConfiguredGrantConfig* that is
> associated with the second *srs-ResourceIndicator* in
> *rrc-ConfiguredUplinkGrant*

\- else if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and is provided
*p0-PUSCH-Alpha2*, for a retransmission of a configured grant Type 1
PUSCH, or for activation or retransmission of a configured grant Type 2
PUSCH, scheduled by a DCI format 0_0, and for active UL BWP $b$ of
carrier $f$ of serving cell

> \- a first $P_{\text{O\_UE\_PUSCH},b,f,c}(1)$ value is provided by the
> value of *p0-PUSCH-Alpha* in *ConfiguredGrantConfig*

\- else, $P_{\text{O\_UE\_PUSCH},b,f,c}(1)$ is provided by *p0* obtained
from *p0-PUSCH-Alpha* in *ConfiguredGrantConfig* that provides an index
*P0-PUSCH-AlphaSetId* to a set of *P0-PUSCH-AlphaSet*, or by
*sdt*-*P0-PUSCH* for a PUSCH (re)transmission as described in clause
19.1, or by *rrc-P0-PUSCH* for a PUSCH (re)transmission as described in
clause 22.1, or by *p0* of *p0AlphaSetforPUSCH* associated with the
*CandidateTCI-State* or *CandidateTCI-UL-State* indicated in the LTM
Cell Switch Command MAC CE for a configured grant Type-1 PUSCH
(re)transmission as described in clause \[21.1\], for active UL BWP $b$
of carrier $f$ of serving cell $c$

\- For $j \in \left\{ 2,\ldots,J - 1 \right\} = S_{J}$, a
$P_{\text{O\_NOMINAL,PUSCH},f,c}(j)$ value, applicable for all
$j \in S_{J}$, is provided by *p0-NominalWithGrant,* or
$P_{\text{O\_NOMINAL,PUSCH},f,c}(j) = P_{\text{O\_NOMINAL,PUSCH},f,c}(0)$
if *p0-NominalWithGrant* is not provided, for each carrier $f$ of
serving cell $c$ and a set of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)\ $values
are provided by a set of *p0* in *P0-PUSCH-AlphaSet* indicated by a
respective set of *p0-PUSCH-AlphaSetId* for active UL BWP $b$ of carrier
$f$ of serving cell $c$

\- If the UE is provided by *SRI-PUSCH-PowerControl* more than one
values of *p0-PUSCH-AlphaSetId* and if a DCI format scheduling the PUSCH
transmission includes an SRI field, the UE obtains a mapping from
*sri-PUSCH-PowerControlId* in *SRI-PUSCH-PowerControl* between a set of
values for the SRI field in the DCI format \[5, TS 38.212\] and a set of
indexes provided by *p0-PUSCH-AlphaSetId* that map to a set of
*P0-PUSCH-AlphaSet* values and determines the value of
$P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ from the *p0-PUSCH-AlphaSetId* value
that is mapped to the SRI field value. If the UE is provided by
*SRI-PUSCH-PowerControl* more than one values of *p0-PUSCH-AlphaSetId*

> \- if the DCI format scheduling the PUSCH transmission includes two
> SRI fields and the UE is provided two SRS resource sets in
> *srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
> with *usage* set to \'codebook\', the UE obtains a mapping from
> *sri-PUSCH-PowerControlId* in *SRI-PUSCH-PowerControl* between a set
> of values for the two SRI fields and a set of indexes provided by
> *p0-PUSCH-AlphaSetId* that map to a set of *P0-PUSCH-AlphaSet* values,
> and determines first and second values of
> $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ from the *p0-PUSCH-AlphaSetId*
> values that are mapped to the values of the first and second SRI
> fields, respectively.
>
> \- if the DCI format scheduling the PUSCH transmission includes two
> SRI fields and the UE is provided two SRS resource sets in
> *srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
> with *usage* set to \'nonCodebook\', the UE obtains a mapping from
> *sri-PUSCH-PowerControlId* in *SRI-PUSCH-PowerControl* between

\- a set of values for the first SRI field value and a set of indexes
provided by *p0-PUSCH-AlphaSetId* that map to a set of
*P0-PUSCH-AlphaSet* values, and determines the first value of
$P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ from the *p0-PUSCH-AlphaSetId* value
that is mapped to the first SRI field value, and

\- a set of values associated with the second SRI field value for a same
number of layers as indicated by the first SRI field \[5, TS 38.212\],
and a set of indexes provided by *p0-PUSCH-AlphaSetId* that map to a set
of *P0-PUSCH-AlphaSet* values, and determines the second value of
$P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ from the *p0-PUSCH-AlphaSetId* value
that is mapped to the second SRI field value corresponding to Tables
7.3.1.1.2-28/29/30/31 of \[5, TS 38.212\].

> \- If the DCI format also includes an open-loop power control
> parameter set indication field and a value of the open-loop power
> control parameter set indication field is \'1\' and if the DCI format
> scheduling the PUSCH transmission includes an SRI field, the UE
> determines a value of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ from a first
> value in *P0-PUSCH-Set* with a *p0-PUSCH-SetId* value mapped to the
> SRI field value.
>
> \- If the UE is provided by *SRI-PUSCH-PowerControl* more than one
> values of *p0-PUSCH-AlphaSetId*

\- if a DCI format scheduling the PUSCH transmission includes two SRI
fields and an open-loop power control parameter set indication field and
the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\'

\- if a value of the open-loop power control parameter set indication
field is \'0\', the UE determines two values of
$P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ from the *p0-PUSCH-AlphaSetId* values
in *SRI-PUSCH-PowerControl* that are mapped to the two SRI values
corresponding to each SRS resource set with *usage* set to \'codebook\'.

\- if a value of the open-loop power control parameter set indication
field is \'1\', the UE determines two values of
$P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ from first values in *P0-PUSCH-Set*
in *P0-PUSCH-SetList* and *P0-PUSCH-Set* in *P0-PUSCH-SetList*2 with
*p0-PUSCH-SetId* values mapped to the two SRI values corresponding to
each SRS resource set with *usage* set to \'codebook\', respectively.

\- if a DCI format scheduling the PUSCH transmission includes two SRI
fields and an open-loop power control parameter set indication field and
the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'nonCodebook\',

\- if a value of the open-loop power control parameter set indication
field is \'0\', the UE determines two values of
$P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ from the *p0-PUSCH-AlphaSetId* values
in *SRI-PUSCH-PowerControl* that are mapped to the first SRI field value
corresponding to the first SRS resource set with *usage* set to
\'nonCodebook\' and to a second value, that is associated with the
second SRI field value corresponding to Tables 7.3.1.1.2-28/29/30/31 of
\[5, TS 38.212\] for a same number of layers as indicated by the first
SRI field value, corresponding to the second SRS resource set with
*usage* set to \'nonCodebook\'.

\- if a value of the open-loop power control parameter set indication
field is \'1\', the UE determines two values of
$P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ from first values in *P0-PUSCH-Set*
in *P0-PUSCH-SetList* and *P0-PUSCH-Set* in *P0-PUSCH-SetList*2 with
*p0-PUSCH-SetId* values mapped to the first SRI field value
corresponding to the first SRS resource set with *usage* set to
\'nonCodebook, and a second value, that is associated with the second
SRS field value corresponding to Tables 7.3.1.1.2-28/29/30/31 of \[5, TS
38.212\] for a same number of layers as indicated by the first SRI field
value, corresponding to the second SRS resource set with *usage* set to
\'nonCodebook\', respectively.

\- if the UE is not provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and if the PUSCH
transmission, except for the PUSCH retransmission corresponding to a RAR
UL grant, is scheduled by a DCI format that does not include an SRI
field, or if *SRI-PUSCH-PowerControl* is not provided to the UE,
$j = 2$,

\- if *P0-PUSCH-Set* is provided to the UE and the DCI format includes
an open-loop power control parameter set indication field, the UE
determines a value of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ from

\- a first *P0-PUSCH-AlphaSet* in *p0-AlphaSets* if a value of the
open-loop power control parameter set indication field is \'0\' or
\'00\'

\- a first value in *P0-PUSCH-Set* with the lowest *p0-PUSCH-SetID*
value if a value of the open-loop power control parameter set indication
field is \'1\' or \'01\'

\- a second value in *P0-PUSCH-Set* with the lowest *p0-PUSCH-SetID*
value if a value of the open-loop power control parameter set indication
field is \'10\'

\- else, the UE determines $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ from the
value of the first *P0-PUSCH-AlphaSet* in *p0-AlphaSets*

\- if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and the PUSCH
transmission is scheduled by a DCI format that does not include an SRI
field and includes an SRS resource set indicator field with value 10 or
11

> \- if *P0-PUSCH-Set* is provided to the UE and the DCI format includes
> an open-loop power control parameter set indication field, the UE
> determines first and second values of
> $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ respectively associated with the
> first and second SRS resource set as
>
> \- first and second *P0-PUSCH-AlphaSet* in *p0-AlphaSets* if the
> open-loop power control parameter set indication value is \'0\' or
> \'00\'
>
> \- first value in *P0-PUSCH-Set* with the lowest *p0-PUSCH-SetID*
> value in *p0-PUSCH-SetList* and first value in *P0-PUSCH-Set* with the
> lowest *p0-PUSCH-SetID* value in *p0-PUSCH-SetList2*, respectively, if
> the open-loop power control parameter set indication value is \'1\' or
> \'01\'
>
> \- second value in *P0-PUSCH-Set* with the lowest *p0-PUSCH-SetID*
> value in *p0-PUSCH-SetList* and second value in *P0-PUSCH-Set* with
> the lowest *p0-PUSCH-SetID* in *p0-PUSCH-SetList2*, respectively, if
> the open-loop power control parameter set indication value is \'10\'
> or \'11\'

\- else, the UE determines first and second values
$P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ respectively associated with the
first and second SRS resource set from the values of the first and
second *P0-PUSCH-AlphaSet* in *p0-AlphaSets*, respectively

\- if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\', and the PUSCH
transmission is scheduled by a DCI format that does not include an SRI
field and includes an SRS resource set indicator field with value \'00\'

> \- if the UE is provided *P0-PUSCH-Set* and the DCI format includes an
> open-loop power control parameter set indication field, the UE
> determines a value of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ as
>
> \- first *P0-PUSCH-AlphaSet* in *p0-AlphaSets* if the open-loop power
> control parameter set indication value is \'0\' or \'00\'
>
> \- first value in *P0-PUSCH-Set* with the lowest *p0-PUSCH-SetID*
> value in *p0-PUSCH-SetList*, if the open-loop power control parameter
> set indication value is \'1\' or \'01\'
>
> \- second value in *P0-PUSCH-Set* with the lowest *p0-PUSCH-SetID*
> value in *p0-PUSCH-SetList*, if the open-loop power control parameter
> set indication value is \'10\' or \'11\'

\- else, the UE determines a value of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$
from the value of the first *P0-PUSCH-AlphaSet* in *p0-AlphaSets*

\- if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\', and the PUSCH
transmission is scheduled by a DCI format that does not include an SRI
field and includes an SRS resource set indicator field with value \'01\'

\- if *P0-PUSCH-Set* is provided to the UE and the DCI format includes
an open-loop power control parameter set indication field, the UE
determines a value of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ as

> \- second *P0-PUSCH-AlphaSet* in *p0-AlphaSets* if the open-loop power
> control parameter set indication value is \'0\' or \'00\'
>
> \- first value in *P0-PUSCH-Set* with the lowest *p0-PUSCH-SetID*
> value in *p0-PUSCH-SetList2*, if the open-loop power control parameter
> set indication value is \'1\' or \'01\'
>
> \- second value in *P0-PUSCH-Set* with the lowest *p0-PUSCH-SetID* in
> *p0-PUSCH-SetList2*, if the open-loop power control parameter set
> indication value is \'10\' or \'11\'

\- else, the UE determines a value of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$
from the value of the second *P0-PUSCH-AlphaSet* in *p0-AlphaSets*

\- For $\alpha_{b,f,c}(j)$

\- For $j = 0$,

\- if
$P_{\text{O\_NOMINAL\_PUSCH,}f,c}(0) = P_{\text{O\_PRE}} + \Delta_{MsgA\_ PUSCH}$
and *msgA-Alpha* is provided, $\alpha_{b,f,c}(0)$ is the value of
*msgA-Alpha*

\- elseif
$P_{\text{O\_NOMINAL\_PUSCH,}f,c}(0) = P_{\text{O\_PRE}} + \Delta_{PREAMBLE\_ Msg3}$
or *msgA-Alpha* is not provided, and *msg3-Alpha* is provided,
$\alpha_{b,f,c}(0)$ is the value of *msg3-Alpha*

\- else, $\alpha_{b,f,c}(0) = 1$

\- For $j = 1$,

\- if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and is provided
*p0-PUSCH-Alpha2*, for a retransmission of a configured grant Type 1
PUSCH, or for activation or retransmission of a configured grant Type 2
PUSCH, scheduled by a DCI format that includes an SRS resource set
indicator field, and for active UL BWP $b$ of carrier $f$ of serving
cell

> \- if the SRS resource set indicator value is \'00\', first
> $\alpha_{b,f,c}(1)$ value is provided by *p0-PUSCH-Alpha* in
> *ConfiguredGrantConfig*
>
> \- if the SRS resource set indicator value is \'01\', first
> $\alpha_{b,f,c}(1)$ value is provided by *p0-PUSCH-Alpha2* in
> *ConfiguredGrantConfig*
>
> \- if the SRS resource set indicator value is \'10\' or \'11\', first
> and second $\alpha_{b,f,c}(1)$ values associated with the first and
> second SRS resource set are respectively provided by *p0-PUSCH-Alpha*
> and *p0-PUSCH-Alpha2* in *ConfiguredGrantConfig*

\- else if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and is provided
*p0-PUSCH-Alpha2*, for a transmission of a configured grant Type 1 PUSCH
and for active UL BWP $b$ of carrier $f$ of serving cell

\- a first $\alpha_{b,f,c}(1)$ value is provided by the value of
*p0-PUSCH-Alpha* in *ConfiguredGrantConfig* that is associated with the
first *srs-ResourceIndicator* in *rrc-ConfiguredUplinkGrant*.

\- a second $\alpha_{b,f,c}(1)$ value is provided by the value of
*p0-PUSCH-Alpha2* in *ConfiguredGrantConfig* that is associated with the
second *srs-ResourceIndicator* in *rrc-ConfiguredUplinkGrant*.

\- else if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and is provided
*p0-PUSCH-Alpha2*, for a retransmission of a configured grant Type 1
PUSCH, or for activation or retransmission of a configured grant Type 2
PUSCH, scheduled by a DCI format 0_0 and for active UL BWP $b$ of
carrier $f$ of serving cell

\- a first$P_{\text{O\_UE\_PUSCH},b,f,c}(1)$ $\alpha_{b,f,c}(1)$ value
is provided by the value of *p0-PUSCH-Alpha* in *ConfiguredGrantConfig.*

\- else $\alpha_{b,f,c}(1)$ is provided by *alpha* obtained from
*p0-PUSCH-Alpha* in *ConfiguredGrantConfig* providing an index
*P0-PUSCH-AlphaSetId* to a set of *P0-PUSCH-AlphaSet*, or by
*sdt*-*Alpha* for a PUSCH (re)transmission as described in clause 19.1,
or by *rrc-Alpha* for a PUSCH (re)transmission as described in clause
22.1, or by *alpha* of *p0AlphaSetforPUSCH* associated with the
*CandidateTCI-State* or *CandidateTCI-UL-State* indicated in the LTM
Cell Switch Command MAC CE for a configured grant Type-1 PUSCH
(re)transmission as described in clause \[21.1\], for active UL BWP $b$
of carrier $f$ of serving cell $c$

\- For $j \in S_{J}$, a set of $\alpha_{b,f,c}(j)$ values are provided
by a set of *alpha* in *P0-PUSCH-AlphaSet* indicated by a respective set
of *p0-PUSCH-AlphaSetId* for active UL BWP $b$ of carrier $f$ of serving
cell $c$

\- If the UE is provided *SRI-PUSCH-PowerControl* and more than one
values of *p0-PUSCH-AlphaSetId* in *p0-AlphaSets*,

\- if a DCI format scheduling the PUSCH transmission includes two SRI
fields and the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\', the UE obtains a mapping from
*sri-PUSCH-PowerControlId* in *SRI-PUSCH-PowerControl* between a set of
values for

\- the two SRI fields and a set of indexes provided by
*P0-PUSCH-AlphaSetId* that map to *P0-PUSCH-AlphaSet* values, and
determines first and second values of $\alpha_{b,f,c}(j)$ from the
*P0-PUSCH-AlphaSetID* values that are mapped to the values of the first
and second SRI field values, respectively.

\- if a DCI format scheduling the PUSCH transmission includes two SRI
fields and the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'nonCodebook\', the UE obtains a mapping from
*sri-PUSCH-PowerControlId* in *SRI-PUSCH-PowerControl* between a set of
values for

\- the first SRI field and a set of indexes provided by
*P0-PUSCH-AlphaSetId* that map to *P0-PUSCH-AlphaSet* values, and
determines first value of $\alpha_{b,f,c}(j)$ from the
*P0-PUSCH-AlphaSetID* value that is mapped to the first SRI field value,
and

\- the second value, associated with the second SRI field value
corresponding to Tables 7.3.1.1.2-28/29/30/31 of \[5, TS 38.212\] for a
same number of layers as indicated by the first SRI field value, and a
set of indexes provided by *p0-PUSCH-AlphaSetId* that map to a set of
*P0-PUSCH-AlphaSet* values, and determines the second value of
$\alpha_{b,f,c}(j)$ from the *p0-PUSCH-AlphaSetId* value that is mapped
to the second SRI field value

\- if a DCI format scheduling the PUSCH transmission includes one SRI
field, the UE obtains a mapping from *sri-PUSCH-PowerControlId* in
*SRI-PUSCH-PowerControl* between a set of values for the SRI field in
the DCI format \[5, TS 38.212\] and a set of indexes provided by
*p0-PUSCH-AlphaSetId* that map to a set of *P0-PUSCH-AlphaSet* values
and determines the values of $\alpha_{b,f,c}(j)$ from the
*p0-PUSCH-AlphaSetId* value that is mapped to the SRI field value

\- If the UE is not provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and if the PUSCH
transmission except for the PUSCH retransmission corresponding to a RAR
UL grant is scheduled by a DCI format that does not include an SRI
field, or if *SRI-PUSCH-PowerControl* is not provided to the UE,
$j = 2$, and the UE determines $\alpha_{b,f,c}(j)$ from the value of the
first *P0-PUSCH-AlphaSet* in *p0-AlphaSets*

\- If the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and the PUSCH
transmission is scheduled by a DCI format that does not include an SRI
field and includes an SRS resource set indicator field with value \'10\'
or \'11\', the UE determines $\alpha_{b,f,c}(j)$ respectively associated
with the first and second SRS resource set from first and second
*P0-PUSCH-AlphaSet* in *p0-AlphaSets*

\- If the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\', and the PUSCH
transmission is scheduled by a DCI format that does not include an SRI
field and includes an SRS resource set indicator field with value \'00\'
or \'01\', the UE determines $\alpha_{b,f,c}(j)$ from first
*P0-PUSCH-AlphaSet* or second *P0-PUSCH-AlphaSet* in *p0-AlphaSets*,
respectively.

\- $M_{RB,b,f,c}^{PUSCH}(i)$ is the bandwidth of the PUSCH resource
assignment expressed in number of resource blocks for PUSCH transmission
occasion $i$ on active UL BWP $b$ of carrier $f$ of serving cell $c$ and
$\mu$ is a SCS configuration defined in \[4, TS 38.211\]

\- ${PL}_{b,f,c}(q_{d})$ is a downlink pathloss estimate in dB
calculated by the UE using reference signal (RS) index $q_{d}$ for the
active DL BWP, as described in clause 12, of carrier $f$ of serving cell
$c$

\- If the UE is not provided *PUSCH-PathlossReferenceRS* and
*enableDefaultBeamPL-ForSRS*, or before the UE is provided dedicated
higher layer parameters, the UE calculates ${PL}_{b,f,c}(q_{d})$

\- using a RS resource from an SS/PBCH block with same SS/PBCH block
index as the one the UE uses to obtain *MIB*, or using the SS/PBCH block
the UE acquired the time and frequency synchronization for a secondary
cell.

\- if the UE is provided *RACH-LessHO* in *ReconfigurationWithSync*
\[12. TS 38.331\], using a RS resource from an SS/PBCH block with same
SS/PBCH block index as the one with same quasi co-location properties as
for PDCCH receptions for scheduling an initial PUSCH transmission, as
described in Clause 10.1, in *controlResourceSetZero* provided in
*ServingCellConfigCommon* of *ReconfigurationWithSync*

\- If the UE is configured with a number of RS resource indexes, up to
the value of *maxNrofPUSCH-PathlossReferenceRSs*, and a respective set
of RS configurations for the number of RS resource indexes by
*PUSCH-PathlossReferenceRS*, the set of RS resource indexes can include
one or both of a set of SS/PBCH block indexes, each provided by
*ssb-Index* when a value of a corresponding
*pusch-PathlossReferenceRS-Id* maps to a SS/PBCH block index, and a set
of CSI-RS resource indexes, each provided by *csi-RS-Index* when a value
of a corresponding *pusch-PathlossReferenceRS-Id* maps to a CSI-RS
resource index. The UE identifies a RS resource index $q_{d}$ in the set
of RS resource indexes to correspond either to a SS/PBCH block index or
to a CSI-RS resource index as provided by *pusch-PathlossReferenceRS-Id*
in *PUSCH-PathlossReferenceRS*

\- If the PUSCH transmission is scheduled by a RAR UL grant as described
in clause 8.3, or for a PUSCH transmission for Type-2 random access
procedure as described in clause 8.1A, the UE uses the same RS resource
index $q_{d}$ as for a corresponding PRACH transmission

\- If the UE is provided *SRI-PUSCH-PowerControl* and more than one
values of *PUSCH-PathlossReferenceRS-Id*, the UE obtains a mapping from
*sri-PUSCH-PowerControlId* in *SRI-PUSCH-PowerControl* between a set of
values for the SRI field, or for first and second SRI fields if the UE
is provided two SRS resource sets in *srs-ResourceSetToAddModList* or
*srs-ResourceSetToAddModListDCI-0-2* with *usage* set to \'codebook\',
or values for a first SRI field and values associated with a second SRI
field value corresponding to Tables 7.3.1.1.2-28/29/30/31 of \[5, TS
38.212\] for a same number of layers as indicated by the first SRI field
value if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'nonCodebook\', in a DCI format scheduling the
PUSCH transmission and a set of *PUSCH-PathlossReferenceRS-Id* values
and determines the RS resource index $q_{d}$, or respective first and
second RS resource indexes $q_{d}$, from the value of
*PUSCH-PathlossReferenceRS-Id* that is mapped to the SRI field value, or
from the values of *PUSCH-PathlossReferenceRS-Id* that are mapped to
respective first and second SRI field values if the UE is provided two
SRS resource sets in *srs-ResourceSetToAddModList* or
*srs-ResourceSetToAddModListDCI-0-2* with *usage* set to \'codebook\',
or from the values of *PUSCH-PathlossReferenceRS-Id* that are mapped to
respective first SRI field value and a value associated with the second
SRI field value corresponding to Tables 7.3.1.1.2-28/29/30/31 of \[5, TS
38.212\] for a same number of layers as indicated by the first SRI field
value if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'nonCodebook\',

where the RS resource is either on serving cell $c$ or, if provided, on
a serving cell indicated by a value of *pathlossReferenceLinking*

\- If the PUSCH transmission is scheduled by DCI format 0_0, and

\- if two spatial settings from *PUCCH-SpatialRelationInfo* are
activated for a PUCCH resource with a lowest index for active UL BWP $b$
of each carrier $f$ and serving cell $c$, the UE uses the same RS
resource index $q_{d}$ as for a PUCCH transmission with a spatial
setting from the two spatial settings with lowest index in the PUCCH
resource with the lowest index for active UL BWP $b$ of each carrier $f$
and serving cell $c$

\- else, if the UE is provided a spatial setting by
*PUCCH-SpatialRelationInfo* for a PUCCH resource with a lowest index for
active UL BWP $b$ of each carrier $f$ and serving cell $c$, as described
in clause 9.2.2, the UE uses the same RS resource index $q_{d}$ as for a
PUCCH transmission in the PUCCH resource with the lowest index

\- If the PUSCH transmission is not scheduled by DCI format 0_0, and if
the UE is provided *enableDefaultBeamPL-ForSRS* and is not provided
*PUSCH-PathlossReferenceRS* and *PUSCH-PathlossReferenceRS-r16,* the UE
uses the same RS resource index $q_{d}$ as for an SRS resource set with
an SRS resource associated with the PUSCH transmission

\- If

\- the UE is not provided *enableDefaultBeamPL-ForPUSCH0-0* and the
PUSCH transmission is scheduled by DCI format 0_0 and the UE is not
provided a spatial setting for a PUCCH transmission, or

\- the PUSCH transmission is scheduled by DCI format 0_1 or DCI format
0_2 that does not include an SRI field, or

\- *SRI-PUSCH-PowerControl* is not provided to the UE,

the UE determines a RS resource index $q_{d}$ with a respective
*PUSCH-PathlossReferenceRS-Id* value being equal to zero where the RS
resource is either on serving cell $c$ or, if provided, on a serving
cell indicated by a value of *pathlossReferenceLinking*

\- If

\- the PUSCH transmission is scheduled by DCI format 0_0 on serving cell
$c$,

\- the UE is not provided PUCCH resources for the active UL BWP of
serving cell $c$, and

\- the UE is provided *enableDefaultBeamPL-ForPUSCH0-0*

the UE determines a RS resource index $q_{d}$ providing a periodic RS
resource configured with *qcl-Type* set to \'typeD\' in the TCI state or
the QCL assumption of a CORESET with the lowest index in the active DL
BWP of the serving cell $c$. If the CORESET has two activated TCI
states, as described in clause 10.1, the UE determines the RS resource
index $q_{d}$ based on the first TCI state.

\- If

\- the PUSCH transmission is scheduled by DCI format 0_0 on serving cell
$c$,

\- the UE is not provided a spatial setting for PUCCH resources on the
active UL BWP of the primary cell \[11, TS 38.321\], and

\- the UE is provided *enableDefaultBeamPL-ForPUSCH0-0*

the UE determines a RS resource index $q_{d}$ providing a periodic RS
resource configured with *qcl-Type* set to \'typeD\' in the TCI state or
the QCL assumption of a CORESET with the lowest index in the active DL
BWP of the serving cell $c$. If the CORESET has two activated TCI
states, as described in clause 10.1, the UE determines the RS resource
index $q_{d}$ based on the first TCI state.

\- For a PUSCH transmission configured by *ConfiguredGrantConfig,* if
*rrc-ConfiguredUplinkGrant* is included in *ConfiguredGrantConfig*,

\- if the UE is provided *enablePL-RS-UpdateForType1CG-PUSCH*, the UE
determines a RS resource index $q_{d}$ from the value of
*PUSCH-PathlossReferenceRS-Id* that is mapped to the
*sri-PUSCH-PowerControlId* indicated by the *srs-ResourceIndicator*
value included in *rrc-ConfiguredUplinkGrant*

\- if the UE is not provided *enablePL-RS-UpdateForType1CG-PUSCH*, a RS
resource index $q_{d}$ is provided by a value of
*pathlossReferenceIndex* included in *rrc-ConfiguredUplinkGrant* where
the RS resource is either on serving cell $c$ or, if provided, on a
serving cell indicated by a value of *pathlossReferenceLinking*. If the
UE is provided two SRS resource sets in *srs-ResourceSetToAddModList* or
*srs-ResourceSetToAddModListDCI-0-2* with *usage* set to \'codebook\' or
\'nonCodebook\' and for configured grant Type 1 PUSCH, first and second
RS resource indexes $q_{d}$ that are respectively associated with the
first and second *srs-ResourceIndicator* in *rrc-ConfiguredUplinkGrant*
are provided by respective values of *pathlossReferenceIndex* and
*pathlossReferenceIndex2* in *rrc-ConfiguredUplinkGrant*.

\- For a PUSCH transmission configured by *ConfiguredGrantConfig* that
does not include *rrc-ConfiguredUplinkGrant*, the UE determines a RS
resource index $q_{d}$ from a value of *PUSCH-PathlossReferenceRS-Id*
that is mapped to a SRI field value in a DCI format activating the PUSCH
transmission.

\- If the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' and the DCI format activating the PUSCH
transmission includes two SRI fields, the UE determines first and second
RS resource indexes $q_{d}$ from respective first and second values of
*PUSCH-PathlossReferenceRS-Id* that are mapped to the first and second
SRI values corresponding to each SRS resource set with *usage* set to
\'codebook\', respectively.

\- If the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'nonCodebook\' and the DCI format activating the
PUSCH transmission includes two SRI fields, the UE determines first and
second RS resource indexes $q_{d}$ from respective first and second
values of *PUSCH-PathlossReferenceRS-Id* that are mapped to the first
SRI value corresponding to the first SRS resource set with *usage* set
to \'nonCodebook\', and the value, associated with the second SRI field
value corresponding to Tables 7.3.1.1.2-28/29/30/31 of \[5, TS 38.212\]
for a same number of layers as indicated by the first SRI field value,
corresponding to the second SRS resource set with *usage* set to
\'nonCodebook\'.

\- If the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and the DCI format
activating the PUSCH transmission does not include an SRI field, the UE
determines first and second RS resource indexes $q_{d}$ respectively
associated with the first and second SRS resource set with respective
first and second *PUSCH-PathlossReferenceRS-Id* value being equal to
zero and one.

\- If the DCI format activating the PUSCH transmission does not include
an SRI field, the UE determines a RS resource index $q_{d}$ with a
respective *PUSCH-PathlossReferenceRS-Id* value being equal to zero

where the RS resources are either on serving cell $c$ or, if provided,
on a serving cell indicated by a value of *pathlossReferenceLinking*

\- If the UE is provided *enablePL-RS-UpdateForPUSCH-SRS*, a mapping
between *sri-PUSCH-PowerControlId* and *PUSCH-PathlossReferenceRS-Id*
values can be updated by a MAC CE as described in \[11, TS 38.321\]

\- For a PUSCH transmission scheduled by a DCI format that does not
include an SRI field, or for a PUSCH transmission configured by
*ConfiguredGrantConfig* and activated, as described in clause 10.2, by a
DCI format that does not include an SRI field, the UE determines a RS
resource index $q_{d}$ from the *PUSCH-PathlossReferenceRS-Id* mapped to
*sri-PUSCH-PowerControlId* = 0. If the UE is provided two SRS resource
sets in *srs-ResourceSetToAddModList* or
*srs-ResourceSetToAddModListDCI-0-2* with *usage* set to \'codebook\' or
\'nonCodebook\', the UE determines first and second RS resource indexes
$q_{d}$ from respective *PUSCH-PathlossReferenceRS-Id* mapped to
*sri-PUSCH-PowerControlId* = 0 of *sri-PUSCH-MappingToAddModList* and
*sri-PUSCH-PowerControlId* = 0 of *sri-PUSCH-MappingToAddModList2*,
respectively.

\- If the UE is not provided *enablePL-RS-UpdateForPUSCH-SRS*

\- For a PUSCH transmission scheduled by a DCI format that does not
include an SRI field, if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\', the UE determines
first and second RS resource indexes $q_{d}$ respectively associated
with the first and second SRS resource set with respective first and
second *PUSCH-PathlossReferenceRS-Id* values being equal to 0 and 1.

${PL}_{b,f,c}(q_{d})$ = *referenceSignalPower* -- higher layer filtered
RSRP, where *referenceSignalPower* is provided by higher layers and RSRP
is defined in \[7, TS 38.215\] for the reference serving cell and the
higher layer filter configuration provided by *QuantityConfig* is
defined in \[12, TS 38.331\] for the reference serving cell

If the UE is not configured periodic CSI-RS reception,
*referenceSignalPower* is provided by *ss-PBCH-BlockPower*. If the UE is
configured periodic CSI-RS reception, *referenceSignalPower* is provided
either by *ss-PBCH-BlockPower* or by *powerControlOffsetSS* providing an
offset of the CSI-RS transmission power relative to the SS/PBCH block
transmission power \[6, TS 38.214\]. If *powerControlOffsetSS* is not
provided to the UE, the UE assumes an offset of 0 dB.

\-
$\mathrm{\Delta}_{TF,b,f,c}(i) = 10\log_{10}\left( \left( 2^{BPRE \cdot K_{s}} - 1 \right) \cdot \beta_{offset}^{PUSCH} \right)$
for $K_{s} = 1.25$ and $\mathrm{\Delta}_{TF,b,f,c}(i) = 0$ for
$K_{s} = 0$ where $K_{s}$ is provided by *deltaMCS* for each UL BWP $b$
of each carrier $f$ and serving cell $c$. If the PUSCH transmission is
over more than one layer \[6, TS 38.214\],
$\mathrm{\Delta}_{TF,b,f,c}(i) = 0$. $BPRE$ and
$\beta_{offset}^{PUSCH}$, for active UL BWP $b$ of each carrier $f$ and
each serving cell $c$, are computed as below

\- $BPRE = \sum_{r = 0}^{C - 1}\frac{K_{r}}{N_{RE}}$ for PUSCH with
UL-SCH data and $BPRE = \frac{Q_{m} \cdot R}{\beta_{offset}^{PUSCH}}$
for CSI transmission in a PUSCH without UL-SCH data, where

\- $C$ is a number of transmitted code blocks, $K_{r}$ is a size for
code block $r$, and $N_{RE}$ is a number of resource elements determined
as
$N_{RE} = N \cdot M_{RB,b,f,c}^{PUSCH}(i) \cdot \sum_{j = 0}^{N_{symb,b,f,c}^{PUSCH}(i) - 1}{N_{sc,data}^{RB}(i,j)}$,
where $N \geq 1$ is provided by *numberOfSlotsTBoMS* as described in
\[6, TS 38.214\] and $N = 1$ if *numberOfSlotsTBoMS* is not provided,
$N_{symb,b,f,c}^{PUSCH}(i)$ is a number of symbols for PUSCH
transmission occasion $i$ on active UL BWP $b$ of carrier $f$ of serving
cell $c$, $N_{sc,data}^{RB}(i,j)$ is a number of subcarriers excluding
DM-RS subcarriers and phase-tracking RS samples \[4, TS 38.211\] in
PUSCH symbol $j$ and assuming no segmentation for a nominal repetition
in case the PUSCH transmission is with repetition Type B,
$0 \leq j < N_{symb,b,f,c}^{PUSCH}(i)$, and $c$, $K_{r}$ are defined in
\[5, TS 38.212\]

\- $\beta_{offset}^{PUSCH} = 1$ when the PUSCH includes UL-SCH data and
$\beta_{offset}^{PUSCH} = \beta_{offset}^{CSI,1}$, as described in
clause 9.3, when the PUSCH includes CSI and does not include UL-SCH data

\- $Q_{m}$ is the modulation order and $R$ is the target code rate, as
described in \[6, TS 38.214\], provided by the DCI format scheduling the
PUSCH transmission that includes CSI and does not include UL-SCH data

\- For the PUSCH power control adjustment state $f_{b,f,c}(i,l)$ for
active UL BWP $b$ of carrier $f$ of serving cell $c$ in PUSCH
transmission occasion $i$

\- $\delta_{PUSCH,b,f,c}(i,l)$ is a TPC command value included in a DCI
format that schedules the PUSCH transmission occasion $i$ on active UL
BWP $b$ of carrier $f$ of serving cell $c$ or jointly coded with other
TPC commands in a DCI format 2_2 with CRC scrambled by TPC-PUSCH-RNTI,
as described in clause 11.3

\- $l \in \left\{ 0,1 \right\}$ if the UE is configured with
*twoPUSCH-PC-AdjustmentStates* and $l = 0$ if the UE is not configured
with *twoPUSCH-PC-AdjustmentStates* or if the PUSCH transmission is
scheduled by a RAR UL grant as described in clause 8.3

\- if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\', and is provided
*p0-PUSCH-Alpha2*, for a retransmission of a configured grant Type 1
PUSCH, or for activation or retransmission of a configured grant Type 2
PUSCH, scheduled by a DCI format that includes a SRS resource set
indicator field, and for active UL BWP $b$ of carrier $f$ of serving
cell

\- if the SRS resource set indicator value is 00, $l$ is equal to the
value of *powerControlLoopToUse* in *ConfiguredGrantConfig*

\- if the SRS resource set indicator value is 01, $l$ is equal to the
value of *powerControlLoopToUse2* in *ConfiguredGrantConfig*

\- if the SRS resource set indicator value is 10 or 11, a first $l$ and
a second $l$ respectively associated with the first and second SRS
resource set are respectively equal to *powerControlLoopToUse* and
*powerControlLoopToUse2* in *ConfiguredGrantConfig*

\- else if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and is provided
*p0-PUSCH-Alpha2*, for a transmission of a configured grant Type 1 PUSCH
and for active UL BWP $b$ of carrier $f$ of serving cell

\- a first $l$ is equal to the value of *powerControlLoopToUse* in
*ConfiguredGrantConfig* that is associated with the first
*srs-ResourceIndicator* in *rrc-ConfiguredUplinkGrant*

\- a second $l$ is equal to the value of *powerControlLoopToUse2* in
*ConfiguredGrantConfig* that is associated with the second
*srs-ResourceIndicator* in *rrc-ConfiguredUplinkGrant*

\- else if the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\' and is provided
*p0-PUSCH-Alpha2*, for a retransmission of a configured grant Type 1
PUSCH, or for activation or retransmission of a configured grant Type 2
PUSCH, scheduled by a DCI format 0_0 and for active UL BWP $b$ of
carrier $f$ of serving cell

\- $l$ is equal to the value of *powerControlLoopToUse* in
*ConfiguredGrantConfig*

\- else, for a PUSCH (re)transmission configured by
*ConfiguredGrantConfig*, the value of $l \in \left\{ 0,1 \right\}$ is
provided to the UE by *powerControlLoopToUse* in
*ConfiguredGrantConfig*.

\- If the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\', is provided *SRI-PUSCH-PowerControl*,
and a DCI format scheduling the PUSCH transmission includes two SRI
fields, the UE obtains a mapping from *sri-PUSCH-PowerControlId* in
*SRI-PUSCH-PowerControl* between a set of values for the first and
second SRI fields and the $l$ values provided by
*sri-PUSCH-ClosedLoopIndex*, and determines the $l$ values mapped to the
values of the first and second SRI fields corresponding to each SRS
resource set with *usage* set to \'codebook\', respectively

\- If the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'nonCodebook\', is provided
*SRI-PUSCH-PowerControl*, and a DCI format scheduling the PUSCH
transmission includes two SRI fields, the UE obtains a mapping from
*sri-PUSCH-PowerControlId* in *SRI-PUSCH-PowerControl* between a set of
values for

\- the first SRI field value and the $l$ values provided by
*sri-PUSCH-ClosedLoopIndex*, and determines the $l$ value that is mapped
to the first SRI field value corresponding to the first SRS resource set
with *usage* set to \'nonCodebook\', and

\- the value, associated with the second SRI field value corresponding
to Tables 7.3.1.1.2-28/29/30/31 of \[5, TS 38.212\] for a same number of
layers as indicated by the first SRI field value, and the $l$ value(s)
provided by *sri-PUSCH-ClosedLoopIndex*, and determines the $l$ value
that is mapped to the value corresponding to the second SRS resource set
with *usage* set to \'nonCodebook\'

\- If the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\', is provided
*SRI-PUSCH-PowerControl*, and a DCI format scheduling the PUSCH
transmission does not include an SRI field

\- If the UE is provided *twoPUSCH-PC-AdjustmentStates*

> \- the UE determines $l = 0$ for the PUSCH transmission corresponding
> to the first SRS resource set with usage set to \'codebook\' or
> \'nonCodebook\', and $l = 1$ for the PUSCH transmission corresponding
> to the second SRS resource set with usage set to \'codebook\' or
> \'nonCodebook\'

\- else

> \- the UE determines $l = 0$ for the PUSCH transmission

\- If the UE is provided two SRS resource sets in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with *usage* set to \'codebook\' or \'nonCodebook\', and is provided
*twoPUSCH-PC-AdjustmentStates*

\- If the DCI format includes two TPC command values and the PUSCH
transmissions are associated with $l = 0$ and $l = 1$, the UE applies
the first TPC command value for $l = 0$ and applies the second TPC
command value for $l = 1$

\- If the DCI format includes two TPC command values and the PUSCH
transmissions are associated with $l = 0$, the UE applies the first TPC
command value for $l = 0$ and ignores the second TPC command value

\- If the DCI format includes two TPC command values and the PUSCH
transmissions are associated with $l = 1$, the UE applies the second TPC
command value for $l = 1$ and ignores the first TPC command value

\- If the DCI format includes one TPC command value, the UE applies the
TPC command value for all $l$ associated with the PUSCH transmission

\- If the UE is provided *SRI-PUSCH-PowerControl*, the UE obtains a
mapping between a set of values for the SRI field in a DCI format
scheduling the PUSCH transmission and the $l$ value(s) provided by
*sri-PUSCH-ClosedLoopIndex* and determines the $l$ value that is mapped
to the SRI field value

\- If the PUSCH transmission is scheduled by a DCI format that does not
include an SRI field, or if an *SRI-PUSCH-PowerControl* is not provided
to the UE, $l = 0$

\- If the UE obtains one TPC command from a DCI format 2_2 with CRC
scrambled by a TPC-PUSCH-RNTI, the $l$ value is provided by the closed
loop indicator field in DCI format 2_2

\-
$f_{b,f,c}(i,l) = f_{b,f,c}\left( i - i_{0},l \right) + \sum_{m = 0}^{\text{C}\left( D_{i} \right) - 1}{\delta_{PUSCH,b,f,c}(m,l)}$
is the PUSCH power control adjustment state $l$ for active UL BWP $b$ of
carrier $f$ of serving cell $c$ and PUSCH transmission occasion $i$ if
the UE is not provided *tpc-Accumulation*, where

\- The $\delta_{PUSCH,b,f,c}$ values are given in Table 7.1.1-1

\-
$\sum_{m = 0}^{\text{C}\left( D_{i} \right) - 1}{\delta_{PUSCH,b,f,c}(m,l)}$
is a sum of TPC command values in a set $D_{i}$ of TPC command values
with cardinality $\text{C}\left( D_{i} \right)$ that the UE receives
between $K_{PUSCH}\left( i - i_{0} \right) - 1$ symbols before PUSCH
transmission occasion $i - i_{0}$ and $K_{PUSCH}(i)$ symbols before
PUSCH transmission occasion $i$ on active UL BWP $b$ of carrier $f$ of
serving cell $c$ for PUSCH power control adjustment state $l$, where
$i_{0} > 0$ is the smallest integer for which $K_{PUSCH}(i - i_{0})$
symbols before PUSCH transmission occasion $i - i_{0}$ is earlier than
$K_{PUSCH}(i)$ symbols before PUSCH transmission occasion $i$

\- If a PUSCH transmission is scheduled by a DCI format, $K_{PUSCH}(i)$
is a number of symbols for active UL BWP $b$ of carrier $f$ of serving
cell $c$ after a last symbol of a corresponding PDCCH reception and
before a first symbol of the PUSCH transmission

\- If a PUSCH transmission is configured by *ConfiguredGrantConfig*,
$K_{PUSCH}(i)$ is a number of $K_{PUSCH,min}$ symbols equal to the
product of a number of symbols per slot, $N_{symb}^{slot}$, and the
minimum of the values provided by *k2* in *PUSCH-ConfigCommon* for
active UL BWP $b$ of carrier $f$ of serving cell $c$

\- If the first symbol of the PUSCH transmission occasion occurs within
$T_{proc,2}$ after a last symbol of a PDCCH reception where the UE
detects the DCI format providing the TPC command, the UE may postpone
the application of the TPC command until the above condition is not
valid. $T_{proc,2}$ is the PUSCH preparation time for the corresponding
UE processing capability \[6, TS 38.214\] assuming $d_{2,1} = 0$, and
$\mu$ corresponds to the smallest SCS configuration between the SCS
configuration of the PDCCH carrying the DCI format and the SCS
configuration of the PUSCH.

\- If the UE has reached maximum power for active UL BWP $b$ of carrier
$f$ of serving cell $c$ at PUSCH transmission occasion $i - i_{0}$ and
$\sum_{m = 0}^{\text{C}\left( D_{i} \right) - 1}{\delta_{PUSCH,b,f,c}(m,l) \geq 0}$,
then $f_{b,f,c}(i,l) = f_{b,f,c}\left( i - i_{0},l \right)$

\- If UE has reached minimum power for active UL BWP $b$ of carrier $f$
of serving cell $c$ at PUSCH transmission occasion $i - i_{0}$ and
$\sum_{m = 0}^{\text{C}\left( D_{i} \right) - 1}{\delta_{PUSCH,b,f,c}(m,l) \leq 0}$,
then $f_{b,f,c}(i,l) = f_{b,f,c}\left( i - i_{0},l \right)$

\- A UE resets accumulation of a PUSCH power control adjustment state
$l$ for active UL BWP $b$ of carrier $f$ of serving cell $c$ to
$f_{b,f,c}(k,l) = 0,\ \ k = 0,1,\ldots,i$

\- If a configuration for a corresponding $P_{O\_ UE\_ PUSCH,b,f,c}(j)$
value is provided by higher layers

\- If a configuration for a corresponding $\alpha_{b,f,c}(j)$ value is
provided by higher layers

where $l$ is determined from the value of $j$ as

\- If $j > 1$ and the UE is provided higher *SRI-PUSCH-PowerControl*,
$l$ is the *sri-PUSCH-ClosedLoopIndex* value(s) configured in any
*SRI-PUSCH-PowerControl* with the *sri-P0-PUSCH-AlphaSetId* value
corresponding to $j$

\- If $j > 1$ and the UE is not provided *SRI-PUSCH-PowerControl* or
$j = 0$, $l = 1$ if $P_{O\_ UE\_ PUSCH,b,f,c}(j)$ and
$\ \alpha_{b,f,c}(j)\ $ are provided by the second
$P0 - PUSCH - AlphaSet\ in\ p0 - AlphaSets$; otherwise, $l = 0$

\- If $j = 1$,

> \- $l$ is provided by the value of *powerControlLoopToUse* if
> $P_{O\_ UE\_ PUSCH,b,f,c}(1)$ and $\alpha_{b,f,c}(1)$ are provided by
> *p0-PUSCH-Alpha* in *ConfiguredGrantConfig*
>
> \- $l$ is provided by the value of *powerControlLoopToUse2* if
> $P_{O\_ UE\_ PUSCH,b,f,c}(1)$ and $\alpha_{b,f,c}(1)$ are provided by
> *p0-PUSCH-Alpha2* in *ConfiguredGrantConfig*

\- $f_{b,f,c}(i,l) = \delta_{PUSCH,b,f,c}(i,l)$ is the PUSCH power
control adjustment state for active UL BWP $b$ of carrier $f$ of serving
cell $c$ and PUSCH transmission occasion
![](media/image13.wmf){width="0.10416666666666667in"
height="0.19791666666666666in"} if the UE is provided
*tpc-Accumulation*, where

\- $\delta_{PUSCH,b,f,c}$ absolute values are given in Table 7.1.1-1

\- If the UE transmits a PUSCH associated with the first RS resource
index $q_{d}$, the UE applies the first
$P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ value, the first $\alpha_{b,f,c}(j)$
value, and $f_{b,f,c}(i,l)$ for determining
$P_{\text{PUSCH},b,f,c}(i,j,q_{d},l)$. If the UE transmits a PUSCH
associated with the second RS resource index $q_{d}$, the UE applies the
second $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$ value, the second
$\alpha_{b,f,c}(j)$ value, and $f_{b,f,c}(i,l)$ or $f_{b,f,c}(i,0)$
if *twoPUSCH-PC-AdjustmentStates* is provided or not provided,
respectively, for determining $P_{\text{PUSCH},b,f,c}(i,j,q_{d},l)$.

\- If the UE receives a random access response message in response to a
PRACH transmission or a MsgA transmission on active UL BWP $b$ of
carrier $f$ of serving cell $c$ as described in clause 8

\-
$f_{b,f,c}(0,l) = {\mathrm{\Delta}P_{rampup,b,f,c} + \delta}_{msg2,b,f,c}$,
where $l = 0$ and

\- $\delta_{msg2,b,f,c}$ is a TPC command value indicated in a random
access response grant of the random access response message
corresponding to a PRACH transmission according to Type-1 random access
procedure, or in a random access response grant of the random access
response message corresponding to a MsgA transmission according to
Type-2 random access procedure with RAR message(s) for fallbackRAR, on
active UL BWP $b$ of carrier $f$ of serving cell $c$, and

\- ![](media/image14.wmf){width="5.614583333333333in"
height="0.6979166666666666in"} and
$\mathrm{\Delta}P_{rampup\_ requested,b,f,c}$ is provided by higher
layers and corresponds to the total power ramp-up requested by higher
layers \[11, TS 38.321\] for carrier $f$ in the serving cell $c$,
$M_{RB,b,f,c}^{PUSCH}(0)$ is the bandwidth of the PUSCH resource
assignment expressed in number of resource blocks for the first PUSCH
transmission on active UL BWP$\ b$ of carrier $f$ of serving cell $c$,
and $\mathrm{\Delta}_{TF,b,f,c}(0)$ is the power adjustment of first
PUSCH transmission on active UL BWP $b$ of carrier $f$ of serving cell
$c$.

\- If the UE transmits the PUSCH in PUSCH transmission occasion $i$ on
active UL BWP $b$ of carrier $f$ of serving cell $c$ as described in
clause 8.1A, $f_{b,f,c}(0,l) = \Delta P_{rampup,b,f,c}$, where

\- $l = 0$, and

\- ![](media/image15.wmf){width="5.71875in"
height="0.6979166666666666in"} and $\Delta P_{rampup\_ requested,b,f,c}$
is provided by higher layers and corresponds to the total power ramp-up
requested by higher layers, $M_{\text{RB,}b,f,c}^{\text{PUSCH}}(i)$ is
the bandwidth of the PUSCH resource assignment expressed in number of
resource blocks, and $\Delta_{\text{TF},b,f,c}(i)$ is the power
adjustment of the PUSCH transmission in PUSCH transmission occasion $i$.

Table 7.1.1-1: Mapping of TPC Command Field in a DCI format scheduling a
PUSCH transmission, or in DCI format 2_2 with CRC scrambled by
TPC-PUSCH-RNTI, or in DCI format 2_3, to absolute and accumulated
$\mathbf{\delta}_{\mathbf{PUSCH}\mathbf{,b}\mathbf{,}\mathbf{f}\mathbf{,}\mathbf{c}}$
values or
$\mathbf{\delta}_{\mathbf{SRS}\mathbf{,b}\mathbf{,}\mathbf{f}\mathbf{,}\mathbf{c}}$
values

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  TPC Command      Accumulated                                                                             Absolute
  Field            $\mathbf{\delta}_{\mathbf{PUSCH}\mathbf{,b}\mathbf{,}\mathbf{f}\mathbf{,}\mathbf{c}}$   $\mathbf{\delta}_{\mathbf{PUSCH}\mathbf{,b}\mathbf{,}\mathbf{f}\mathbf{,}\mathbf{c}}$
                   or $\mathbf{\delta}_{\mathbf{SRS}\mathbf{,b}\mathbf{,}\mathbf{f}\mathbf{,}\mathbf{c}}$  or $\mathbf{\delta}_{\mathbf{SRS}\mathbf{,b}\mathbf{,}\mathbf{f}\mathbf{,}\mathbf{c}}$
                   \[dB\]                                                                                  \[dB\]
  ---------------- --------------------------------------------------------------------------------------- ---------------------------------------------------------------------------------------
  0                -1                                                                                      -4

  1                0                                                                                       -1

  2                1                                                                                       1

  3                3                                                                                       4
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------