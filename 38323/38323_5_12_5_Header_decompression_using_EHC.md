### 5.12.5 Header decompression using EHC

If EHC is configured by upper layers for PDCP entities associated with
user plane data, the PDCP Data PDUs are decompressed by the EHC protocol
after performing deciphering and integrity verification as explained in
clause 5.8 and 5.9, respectively. The header decompression is not
applicable to the SDAP header and the SDAP Control PDU if included in
the PDCP Data PDU.