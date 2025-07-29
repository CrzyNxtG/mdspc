### 5.12.4 Header compression using EHC

If EHC is configured, the EHC protocol generates two types of output
packets:

\- EHC compressed packets (i.e. EHC full header packets and EHC
compressed header packets), each associated with one PDCP SDU;

\- standalone packets not associated with a PDCP SDU, i.e. EHC feedback.

An EHC compressed packet is associated with the same PDCP SN and COUNT
value as the related PDCP SDU. The header compression is not applicable
to the SDAP header and the SDAP Control PDU if included in the PDCP SDU.

EHC feedback are not associated with a PDCP SDU. They are not associated
with a PDCP SN and are not ciphered/integrity protected.