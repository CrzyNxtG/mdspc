### 6.1.1 Transmission schemes

Two transmission schemes are supported for PUSCH: codebook based
transmission and non-codebook based transmission. The UE is configured
with codebook based transmission when the higher layer parameter
*txConfig* in *pusch-Config* is set to \'codebook\', the UE is
configured non-codebook based transmission when the higher layer
parameter *txConfig* is set to \'nonCodebook\'. If the higher layer
parameter *txConfig* is not configured, the UE is not expected to be
scheduled by DCI format 0_1, 0_2 or 0_3. If PUSCH is scheduled by DCI
format 0_0, the PUSCH transmission is based on a single antenna port.
Except if the higher layer parameter *enableDefaultBeamPL-ForPUSCH0-0*
is set \'enabled\', the UE shall not expect PUSCH scheduled by DCI
format 0_0 in a BWP without configured PUCCH resource with
*PUCCH-SpatialRelationInfo* in frequency range 2 in RRC connected mode.