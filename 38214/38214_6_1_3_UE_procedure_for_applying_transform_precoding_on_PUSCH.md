### 6.1.3 UE procedure for applying transform precoding on PUSCH

For a PUSCH scheduled by RAR UL grant, or for a PUSCH scheduled by
fallbackRAR UL grant, or for a PUSCH scheduled by DCI format 0_0 with
CRC scrambled by TC-RNTI, the UE shall consider the transform precoding
either \'enabled\' or \'disabled\' according to the higher layer
configured parameter *msg3-transformPrecoder.*

For a MsgA PUSCH, the UE shall consider the transform precoding either
\'enabled\' or \'disabled\' according to the higher layer configured
parameter *msgA-TransformPrecoder.* If higher layer parameter
*msgA-TransformPrecoder* is not configured, the UE shall consider the
transform precoding either \'enabled\' or \'disabled\' according to the
higher layer configured parameter *msg3-transformPrecoder.*

For PUSCH transmission scheduled by a PDCCH with CRC scrambled by
CS-RNTI with NDI=1, C-RNTI, or MCS-C-RNTI or SP-CSI-RNTI:

\- If the DCI with the scheduling grant was received with DCI format
0_0, the UE shall, for this PUSCH transmission, consider the transform
precoding either enabled or disabled according to the higher layer
configured parameter *msg3-transformPrecoder* from *rach-ConfigCommon*
included directly within BWP configuration.

\- If the DCI with the scheduling grant was not received with DCI format
0_0

\- If the DCI with the scheduling grant was received with DCI format 0_1
or 0_2 with CRC scrambled by C-RNTI, MCS-RNTI, or CS-RNTI with NDI=1 and
if the UE is configured with a higher layer parameter
*dynamicTransformPrecoderFieldPresenceDCI-0-1* in *pusch-Config* for DCI
format 0_1 or *dynamicTransformPrecoderFieldPresenceDCI-0-2* in
*pusch-Config* for DCI format 0_2 and the higher layer parameter is set
to \'enabled\',

\- the UE shall, for this PUSCH transmission, consider the transform
precoding either enabled or disabled according to the Transform precoder
indicator field in the DCI with the scheduling grant.

\- For *pusch-TimeDomainAllocationListForMultiPUSCH* in *pusch-Config,*
the UE shall, for all PUSCH transmissions, consider the transform
precoding either enabled or disabled according to Transform precoder
indicator field in the DCI format 0_1 with the scheduling grant.

\- If r*esourceAllocation* in *pusch-Config* for DCI format 0_1 or
*resourceAllocationDCI-0-2* in *pusch-Config* for DCI format 0_2 is set
to *resourceAllocationType0*, or if the resource allocation is set to
resource allocation type 0 according to the DCI configuration as
described in clauses 7.3.1.1.2 and 7.3.1.1.3 of \[6, TS 38.212\], or if
*dmrs-Type* in *DMRS-UplinkConfig* is set to 'type 2' for this PUSCH
transmission, the UE does not expect that the Transform precoder
indicator field in the DCI with the scheduling grant indicates that
transform precoding is enabled.

\- If the UE is configured with the higher layer parameter
*dmrs-TypeEnh* in *DMRS-UplinkConfig*, and if the scheduling grant
indicates that transform precoding is enabled for the scheduled PUSCH
transmission, the UE ignores the higher layer parameters *dmrs-TypeEnh*
in *DMRS-UplinkConfig*, if configured, for the DM-RS transmission of the
scheduled PUSCH transmission.

\- Otherwise,

\- If the UE is configured with the higher layer parameter
*transformPrecoder* in *pusch-Config*, the UE shall, for this PUSCH
transmission, consider the transform precoding either enabled or
disabled according to this parameter.

\- If the UE is not configured with the higher layer parameter
*transformPrecoder* in *pusch-Config*, the UE shall, for this PUSCH
transmission, consider the transform precoding either enabled or
disabled according to the higher layer configured parameter
*msg3-transformPrecoder*.

For PUSCH transmission with a configured grant

\- If the UE is configured with the higher layer parameter
*transformPrecoder* in *configuredGrantConfig*, the UE shall, for this
PUSCH transmission, consider the transform precoding either enabled or
disabled according to this parameter.

\- If the UE is not configured with the higher layer parameter
*transformPrecoder* in *configuredGrantConfig*, the UE shall, for this
PUSCH transmission, consider the transform precoding either enabled or
disabled according to the higher layer configured parameter
*msg3-transformPrecoder*.