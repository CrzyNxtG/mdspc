### 5.7.5 Header decompression using ROHC

If ROHC is configured by upper layers for PDCP entities associated with
user plane data, the PDCP Data PDUs are decompressed by the ROHC
protocol after performing deciphering as explained in clause 5.8. The
header decompression is not applicable to the SDAP header and the SDAP
Control PDU if included in the PDCP Data PDU.

For DAPS bearers, the PDCP entity shall perform the header decompression
for the PDCP SDU using the ROHC protocol either configured for the
source cell or configured for the target cell, based on from which cell
the PDCP SDU is received.