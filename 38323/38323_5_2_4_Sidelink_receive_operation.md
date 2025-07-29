### 5.2.4 Sidelink receive operation

For sidelink reception of the SLRB, the UE shall follow the procedures
in clause 5.2.2 with following modification:

\- perform the header decompression using ROHC as specified in clause
5.7.5, if SDU Type is IP.

NOTE: For reception of sidelink SRBs except sidelink SRB3, the UE may
deliver the PDCP SDU to the upper layer along with an indication whether
it is PC5-S message or NR sidelink discovery message.