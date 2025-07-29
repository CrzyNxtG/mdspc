### 6.2.3 UE PT-RS transmission procedure

The procedures on PT-RS transmission described in this clause as well as
clauses 6.2.3.1 and 6.2.3.2 apply to a UE PUSCH transmission scheduled
by DCI format 0_2 if the higher layer parameter *phaseTrackingRS* in
*dmrs-UplinkForPUSCH-MappingTypeA-DCI-0-2* or
*dmrs-UplinkForPUSCH-MappingTypeB-DCI-0-2* is configured, to PUSCH
transmissions scheduled by DCI format 0_0, 0_1 or 0_3 if the higher
layer parameter *phaseTrackingRS* in *dmrs-UplinkForPUSCH-MappingTypeA*
or *dmrs-UplinkForPUSCH-MappingTypeB* is configured and PUSCH
transmissions corresponding to a configured grant if the higher layer
parameter *phaseTrackingRS* in *cg-DMRS-Configuration* is configured. If
a UE is not configured with the higher layer parameter *phaseTrackingRS*
in the respective *DMRS-UplinkConfig*, the UE shall not transmit PT-RS.
The PT-RS is only present on PUSCH scheduled by PDCCH with CRC scrambled
by MCS-C-RNTI, C-RNTI, CS-RNTI, SP-CSI-RNTI and on PUSCH corresponding
to a configured grant. For PUSCH repetition Type B, the PT-RS
transmission procedure is applied for each actual repetition separately
based on the allocation duration of the actual repetition.