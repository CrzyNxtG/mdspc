## 7.6 Transport of NAS Messages

NR provides reliable in-sequence delivery of NAS messages over SRBs in
RRC, except at handover where losses or duplication can occur when PDCP
is re-established. In RRC, NAS messages are sent in transparent
containers. Piggybacking of NAS messages can occur in the following
scenarios:

\- At bearer establishment/modification/release in the DL;

\- For transferring the initial NAS message during connection setup and
connection resume in the UL.

NOTE: In addition to the integrity protection and ciphering performed by
NAS, NAS messages can also be integrity protected and ciphered by PDCP.

Multiple NAS messages can be sent in a single downlink RRC message
during PDU Session Resource establishment or modification. In this case,
the order of the NAS messages contained in the RRC message shall be in
the same order as that in the corresponding NG-AP message in order to
ensure the in-sequence delivery of NAS messages.

NG-RAN node may trigger the NAS Non Delivery Indication procedure to
report the non-delivery of the non PDU Session related NAS PDU received
from the AMF as specified in TS 38.413 \[26\].