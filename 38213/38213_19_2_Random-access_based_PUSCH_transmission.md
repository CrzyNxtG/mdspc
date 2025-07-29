## 19.2 Random-access based PUSCH transmission

A UE indicated to release a dedicated RRC connection can be provided a
configuration for a Type-1 and/or a Type-2 random access procedure on
the initial UL BWP \[12, TS 38.331\]. PRACH occasions can have either a
common configuration as, or a separate configuration from, PRACH
occasions for Type-1 or Type-2 random access procedure as described in
clause 8.1. The UE procedure is as described in clause 8, including
clauses 8.1 through 8.4. The UE transmits a PRACH preamble with a power
determined as described in clause 7.4.

For a common configuration of PRACH occasions and a Type-1 or a Type-2
random access procedure, a UE can be provided a number of contention
based preambles per SS/PBCH block index per valid PRACH occasion by
*startPreambleForThisPartition* and
*numberOfPreamblesPerSSB-ForThisPartition* when *smallData* is present
in corresponding *FeatureCombination*. A PRACH transmission can be on a
subset of PRACH occasions associated with a same SS/PBCH block index
within an SSB-RO mapping cycle as determined by a PRACH mask index
provided by *ssb-SharedRO-MaskIndex* according to \[11, TS 38.321\].

A UE can be provided by *sdt-SearchSpace* a CSS set to monitor, after
contention resolution according to \[11, TS 38.321\], PDCCH for
detection of a DCI format 0_0 or DCI format 1_0 with CRC scrambled by
C-RNTI for scheduling respective PUSCH transmissions or PDSCH
receptions; otherwise, if the UE is not provided *sdt-SearchSpace*, the
UE monitors PDCCH according to a Type1-PDCCH CSS set as described in
clause 10.1. The UE may assume that the DM-RS antenna port associated
with the PDCCH receptions, the DM-RS antenna port associated with the
PDSCH receptions, and the SS/PBCH block associated with the PRACH
transmission are quasi co-located with respect to average gain and quasi
co-location \'typeA\' or \'typeD\' properties.