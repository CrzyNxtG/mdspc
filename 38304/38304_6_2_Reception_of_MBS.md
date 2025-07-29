## 6.2 Reception of MBS

A UE receiving or interested to receive MBS broadcast services shall
apply the MCCH information acquisition procedure as specified in TS
38.331 \[3\] to receive the MCCH information. A UE interested to receive
MBS broadcast services identifies if a service that it is interested to
receive is started or ongoing by receiving the MCCH information, and
then receives a MTCH(s) configured using the Broadcast MRB establishment
procedure as specified in TS 38.331 \[3\] and using the DL-SCH reception
and MBS broadcast DRX procedure as specified in TS 38.321 \[19\].

A UE which has joined multicast session(s) and configured to receive MBS
multicast services in RRC_INACTIVE state shall apply the multicast MCCH
information acquisition procedure as specified in TS 38.331 \[3\] to
receive the multicast MCCH information when UE is in RRC_INACTIVE state
and the multicast MCCH is configured in the cell. The UE identifies
whether a session is active or not by receiving the indication in
*RRCRelease*, multicast MCCH information, or group notification in
paging message, and receives the multicast MTCH(s) in RRC_INACTIVE state
using the multicast MRB configuration procedure as specified in TS
38.331 \[3\] and using the DL-SCH reception and MBS multicast DRX
procedure as specified in TS 38.321 \[19\].

UEs which have joined a multicast session(s) and are in
RRC_IDLE/RRC_INACTIVE state shall apply the reception of the paging
message procedure as specified in TS 38.331 \[3\] when the UE expects
MBS group notification as specified in clause 16.10.5.2 in TS 38.300
\[2\].

When upper layers provide MBS start time and/or scheduled activation
time(s) (as specified in TS23.247 \[21\]) and the UE has joined an MBS
session indicated by TMGI while the UE is in RRC_IDLE or RRC_INACTIVE
state, the UE monitors paging as defined in clause 7.1 using the TMGI
(as defined in TS 38.331 \[3\]) during those MBS start time and/or
scheduled activation time(s).

NOTE: When the UE is interested to receive MBS broadcast the UE may
perform procedures to receive MBS broadcast session(s) as defined in TS
38.331 \[3\] if upper layer is configured with the MBS start time and/or
scheduled activation time(s) (as specified in TS23.247 \[21\]).