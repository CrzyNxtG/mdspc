### 5.7.4 Header compression using ROHC

If ROHC is configured, the ROHC protocol generates two types of output
packets:

\- ROHC compressed packets, each associated with one PDCP SDU;

\- standalone packets not associated with a PDCP SDU, i.e. interspersed
ROHC feedback.

A ROHC compressed packet is associated with the same PDCP SN and COUNT
value as the related PDCP SDU. The header compression is not applicable
to the SDAP header and the SDAP Control PDU if included in the PDCP SDU.

For DAPS bearers, the PDCP entity shall perform the header compression
for the PDCP SDU using the ROHC protocol either configured for the
source cell or configured for the target cell, based on to which cell
the PDCP SDU is transmitted.

Interspersed ROHC feedback are not associated with a PDCP SDU. They are
not associated with a PDCP SN and are not ciphered.

NOTE 1: If the MAX_CID number of ROHC contexts are already established
for the compressed flows and a new IP flow does not match any
established ROHC context, the compressor should associate the new IP
flow with one of the ROHC CIDs allocated for the existing compressed
flows or send PDCP SDUs belonging to the IP flow as uncompressed packet.

NOTE 2: For downlink, the ROHC protocol of the target cell should
maintain the IR state if operating in U-mode and O-mode during DAPS
handover before release of source cell.