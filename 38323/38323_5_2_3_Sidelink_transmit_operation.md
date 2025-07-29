### 5.2.3 Sidelink transmit operation

For NR sidelink transmission of the SLRB, the UE shall follow the
procedures in clause 5.2.1 with following modification:

\- perform the header compression using ROHC as specified in clause
5.7.4, if SDU Type is IP;

\- set the PDCP SN of the PDCP Data PDU to TX_NEXT modulo
2^\[*sl-PDCP-SN-Size*\]^;

\- if the transmitting PDCP entity is associated with two RLC entities:

\- consider PDCP duplication as activated;

\- submit the PDCP control PDU to one of the associated RLC entities.

NOTE: How to decide to which RLC entity a PDCP control PDU is submitted
is left up to UE implementation.