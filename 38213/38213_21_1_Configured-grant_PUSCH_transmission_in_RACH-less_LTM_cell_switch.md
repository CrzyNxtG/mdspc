## 21.1 Configured-grant PUSCH transmission in RACH-less LTM cell switch

A UE configured to perform PUSCH transmission in RACH-less LTM cell
switch can be provided one or more configurations by respective one or
more *ConfiguredGrantConfig*, for configured grant Type 1 PUSCH
transmissions on the active UL BWP \[12, TS 38.331\]. For the remaining
of this clause, PUSCH transmissions refer to configured grant Type-1
PUSCH transmissions for a configuration provided by
*ConfiguredGrantConfig*.

A UE can be provided by *rrc-SSB-Subset* in *cg-LTM-Configuration* a
number of SS/PBCH block indexes $N_{PUSCH}^{SS/PBCH}$ to map to a number
of valid PUSCH occasions for PUSCH transmissions over an association
period. If the UE is not provided *rrc-SSB-Subset* in
*cg-LTM-Configuration*, the UE determines $N_{PUSCH}^{SS/PBCH}$ from the
value of *ssb-PositionsInBurst* in *ServingCellConfigCommon*. A PUSCH
occasion for a PUSCH transmission is defined by a time resource and a
frequency resource and is associated with a DM-RS provided by
*cg-DMRS-Configuration* for the configuration of PUSCH transmissions. A
UE can be provided a number of repetitions for a PUSCH transmission by
*repK* or *numberOfRepetitions*. If the number of repetitions is
provided and larger than 1, all the PUSCH occasions of the repetitions
for the PUSCH transmission are mapped to the same SS/PBCH block
index(es). For the initial transmission or autonomous retransmission of
an initial transport block provided for PUSCH transmission, the UE
encodes the transport block using redundancy version number 0 if the UE
is not provided *repK-RV*.

An association period, starting from frame with SFN 0, for mapping
$N_{PUSCH}^{SS/PBCH}$ SS/PBCH block indexes, from the number of SS/PBCH
block indexes, to valid PUSCH occasions and associated DM-RS resources
is the smallest value in the set determined by the PUSCH configuration
period provided by *periodicity* in *ConfiguredGrantConfig* according to
Table 19.1-1 such that $N_{PUSCH}^{SS/PBCH}$ SS/PBCH block indexes are
mapped at least once to valid PUSCH occasions and associated DM-RS
resources within the association period. A UE is provided a number of
SS/PBCH block indexes associated with a PUSCH occasion and a DM-RS
resource by *rrc-SSB-PerCG-PUSCH* in *cg-LTM-Configuration*. If after an
integer number of SS/PBCH block indexes to PUSCH occasions and
associated DMRS resources mapping cycles within the association period
there is a set of PUSCH occasions and associated DMRS resources that are
not mapped to $N_{PUSCH}^{SS/PBCH}$ SS/PBCH block indexes, no SS/PBCH
block indexes are mapped to the set of PUSCH occasions and associated
DMRS resources. An association pattern period includes one or more
association periods and is determined so that a pattern between PUSCH
occasions with associated DMRS resources and SS/PBCH block indexes
repeats at most every 640 msec. PUSCH occasions and associated DMRS
resources not associated with SS/PBCH block indexes after an integer
number of association periods, if any, are not used for PUSCH
transmissions.

Each *N* of $N_{PUSCH}^{SS/PBCH}$ SS/PBCH block indexes in increasing
order are mapped to valid PUSCH occasions and associated DMRS resources
in the following order

\- first, in increasing order of DMRS resource indexes within a PUSCH
occasion, where a DMRS resource index $DMRS_{id}$ is determined first in
an ascending order of a DMRS port index and second in an ascending order
of a DMRS sequence index \[4, TS 38.211\]

\- second, in increasing order of PUSCH configuration period indexes

where *N* is provided by *rrc-SSB-PerCG-PUSCH*
in *cg-LTM-Configuration*.

A PUSCH occasion is valid if it does not overlap with a valid PRACH
occasion as described in clause 8.1.

For unpaired spectrum and for SS/PBCH blocks with indexes provided by
*rrc-SSB-Subset* in *cg-LTM-Configuration,* or *ssb-PositionsInBurst* in
*ServingCellConfigCommon* if *rrc-SSB-Subset* is not provided

\- if a UE is provided *tdd-UL-DL-ConfigurationCommon*, a PUSCH occasion
is valid if the PUSCH occasion

\- is within UL symbols

\- starts at least $N_{\text{gap}}$ symbols after a last downlink
symbol, and at least $N_{\text{gap}}$ symbols after a last SS/PBCH block
symbol, where $N_{\text{gap}}$ is provided in Table 8.1-2

If the UE is provided *cg-LTM-Configuration,* the UE performs configured
grant Type 1 PUSCH transmission on the valid PUSCH occasions associated
with the SS/PBCH block indexes same as the SS/PBCH block indexes
provided by or associated with QCL RS of the *CandidateTCI-State* or
*CandidateTCI-UL-State* indicated by the LTM Cell Switch Command MAC CE.

A UE determines a power of a PUSCH transmission as described in clause
7.1.1, where the UE obtains ${PL}_{b,f,c}(q_{d})$ using a RS resource
from *pathlossReferenceRS-Id* included in the *CandidateTCI-State* or
*CandidateTCI-UL-State* indicated by the LTM Cell Switch Command MAC CE.