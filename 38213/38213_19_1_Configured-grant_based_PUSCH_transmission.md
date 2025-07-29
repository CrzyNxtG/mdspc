## 19.1 Configured-grant based PUSCH transmission

A UE indicated to release a dedicated RRC connection can be provided one
or more configurations by respective one or more
*ConfiguredGrantConfig*, for configured grant Type 1 PUSCH transmissions
on the initial UL BWP \[12, TS 38.331\]. For the remaining of this
clause, PUSCH transmissions refer to configured grant Type-1 PUSCH
transmissions for a configuration provided by *ConfiguredGrantConfig*.

A UE can be provided by *sdt-SSB-Subset* a number of SS/PBCH block
indexes $N_{PUSCH}^{SS/PBCH}$ to map to a number of valid PUSCH
occasions for PUSCH transmissions over an association period. If the UE
is not provided *sdt-SSB-Subset*, the UE determines
$N_{PUSCH}^{SS/PBCH}$ from the value of *ssb-PositionsInBurst* in
*SIB1*. A PUSCH occasion for a PUSCH transmission is defined by a time
resource and a frequency resource and is associated with a DM-RS
provided by *cg-DMRS-Configuration* for the configuration of PUSCH
transmissions. A UE can be provided a number of repetitions for a PUSCH
transmission by *repK* or *numberOfRepetitions*. If the number of
repetitions is provided and larger than 1, all the PUSCH occasions of
the repetitions for the PUSCH transmission are mapped to the same
SS/PBCH block index(es). All the PUSCH occasions of the repetitions are
not valid if any PUSCH occasion of the repetitions is not valid.

An association period, starting from frame with SFN 0 and hyper frame
with hyper SFN 0, for mapping $N_{PUSCH}^{SS/PBCH}$ SS/PBCH block
indexes, from the number of SS/PBCH block indexes, to valid PUSCH
occasions and associated DM-RS resources is the smallest value in the
set determined by the PUSCH configuration period provided by
*periodicity* in *ConfiguredGrantConfig* according to Table 19.1-1 such
that $N_{PUSCH}^{SS/PBCH}$ SS/PBCH block indexes are mapped at least
once to valid PUSCH occasions and associated DM-RS resources within the
association period. A UE is provided a number of SS/PBCH block indexes
associated with a PUSCH occasion and a DM-RS resource by
*sdt-SSB-PerCG-PUSCH*. If after an integer number of SS/PBCH block
indexes to PUSCH occasions and associated DMRS resources mapping cycles
within the association period there is a set of PUSCH occasions and
associated DMRS resources that are not mapped to $N_{PUSCH}^{SS/PBCH}$
SS/PBCH block indexes, no SS/PBCH block indexes are mapped to the set of
PUSCH occasions and associated DMRS resources. An association pattern
period, when PUSCH configuration period is no longer than 640 msec,
includes one or more association periods and is determined so that a
pattern between PUSCH occasions with associated DMRS resources and
SS/PBCH block indexes repeats at most every 640 msec. PUSCH occasions
and associated DMRS resources not associated with SS/PBCH block indexes
after an integer number of association periods, if any, are not used for
PUSCH transmissions.

Table 19.1-1: Mapping between PUSCH configuration period and SS/PBCH
block to configured PUSCH resource association period

  -----------------------------------------------------------------------
  PUSCH configuration period     Association period (number of PUSCH
  $\mathbf{T}_{\mathbf{cg}}$     configuration periods)
  (msec)                         
  ------------------------------ ----------------------------------------
  5                              {1, 2, 4, 8,16, 32, 64, 128}

  8                              {1, 2, 4, 5, 8, 10, 16, 20, 40, 80}

  10                             {1, 2, 4, 8,16, 32, 64}

  16                             {1, 2, 4, 5, 8,10,20,40}

  20                             {1, 2, 4, 8,16, 32}

  32                             {1, 2, 4, 5, 10, 20}

  40                             {1, 2, 4, 8, 16}

  64                             {1, 2, 5, 10}

  80                             {1, 2, 4, 8}

  128                            {1, 5}

  160                            {1, 2, 4}

  320                            {1, 2}

  640                            {1}

  1280                           {1}

  2560                           {1}

  5120                           {1}

  10240                          {1}

  61440                          {1}

  122880                         {1}

  307200                         {1}

  604160                         {1}

  1208320                        {1}

  1802240                        {1}

  3604480                        {1}
  -----------------------------------------------------------------------

Each *N* of $N_{PUSCH}^{SS/PBCH}$ SS/PBCH block indexes in increasing
order are mapped to a valid PUSCH occasion and the associated DMRS
resource

> \- first, in increasing order of DMRS resource indexes within a PUSCH
> occasion, where a DMRS resource index $DMRS_{id}$ is determined first
> in an ascending order of a DMRS port index and second in an ascending
> order of a DMRS sequence index \[4, TS 38.211\]
>
> \- second, in increasing order of PUSCH configuration period indexes

where *N* is provided by *sdt-SSB-PerCG-PUSCH.*

A PUSCH occasion is valid if it does not overlap with a valid PRACH
occasion as described in clause 8.1.

For unpaired spectrum and for SS/PBCH blocks with indexes provided by
*ssb-PositionsInBurst* in *SIB1*

\- if a UE is not provided *tdd-UL-DL-ConfigurationCommon*, a PUSCH
occasion is valid if the PUSCH occasion

\- does not precede a SS/PBCH block in the PUSCH slot, and

\- starts at least $N_{\text{gap}}$ symbols after a last SS/PBCH block
symbol, where $N_{\text{gap}}$ is provided in Table 8.1-2

\- if a UE is provided *tdd-UL-DL-ConfigurationCommon*, a PUSCH occasion
is valid if the PUSCH occasion

\- is within UL symbols

\- starts at least $N_{\text{gap}}$ symbols after a last downlink
symbol, and at least $N_{\text{gap}}$ symbols after a last SS/PBCH block
symbol, where $N_{\text{gap}}$ is provided in Table 8.1-2

A UE determines a power of a PUSCH transmission as described in clause
7.1.1, where the UE obtains ${PL}_{b,f,c}(q_{d})$ using a RS resource
from an SS/PBCH block with index associated with the PUSCH transmission.

A UE can be provided a USS set by *SearchSpace*, or a CSS set by
*sdt-SearchSpace*, to monitor PDCCH for detection of DCI format 0_0 with
CRC scrambled by C-RNTI or CS-RNTI for scheduling PUSCH transmission or
of DCI format 1_0 with CRC scrambled by C-RNTI for scheduling PDSCH
receptions \[12, TS 38.331\]. The UE may assume that the DM-RS antenna
port associated with the PDCCH receptions, the DM-RS antenna port
associated with the PDSCH receptions, and the SS/PBCH block associated
with the PUSCH transmission are quasi co-located with respect to average
gain and quasi co-location \'typeA\' or \'typeD\' properties. The UE
transmits a PUCCH with HARQ-ACK information associated with the PDSCH
receptions as described in clause 9.2.1 using a same spatial domain
transmission filter as for the last PUSCH transmission.

For initial transmission or autonomous retransmission of an initial
transport block provided for the PUSCH transmission as described in
clause 18.0 in \[19, TS 38.300\], the UE encodes the transport block
using redundancy version number 0 if the UE is not provided *repK-RV*.