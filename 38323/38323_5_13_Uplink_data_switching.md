## 5.13 Uplink data switching

For DAPS bearers, when upper layers request uplink data switching, the
transmitting PDCP entity shall:

\- for AM DRBs, from the first PDCP SDU for which the successful
delivery of the corresponding PDCP Data PDU has not been confirmed by
the RLC entity associated with the source cell, perform retransmission
or transmission of all the PDCP SDUs already associated with PDCP SNs in
ascending order of the COUNT values associated to the PDCP SDU prior to
uplink data switching to the RLC entity associated with the target cell
as specified below:

\- perform header compression of the PDCP SDU using ROHC as specified in
the clause 5.7.4;

\- perform integrity protection and ciphering of the PDCP SDU using the
COUNT value associated with this PDCP SDU as specified in the clause 5.9
and 5.8, respectively;

\- submit the resulting PDCP Data PDU to lower layer, as specified in
clause 5.2.1.

\- for UM DRBs, for all PDCP SDUs which have been processed by PDCP but
which have not yet been submitted to lower layers, perform transmission
of the PDCP SDUs in ascending order of the COUNT values to the RLC
entity associated with the target cell as specified below:

\- perform header compression of the PDCP SDU using ROHC as specified in
the clause 5.7.4;

\- perform integrity protection and ciphering of the PDCP SDU using the
COUNT value associated with this PDCP SDU as specified in the clause 5.9
and 5.8, respectively;

\- submit the resulting PDCP Data PDU to lower layer, as specified in
clause 5.2.1.