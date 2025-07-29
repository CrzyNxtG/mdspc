## 7.4 Access Control

NG-RAN supports overload and access control functionality such as RACH
back off, RRC Connection Reject, RRC Connection Release and UE based
access barring mechanisms.

One unified access control framework as specified in TS 22.261 \[19\]
applies to all UE states (RRC_IDLE, RRC_INACTIVE and RRC_CONNECTED) for
NR. NG-RAN broadcasts barring control information associated with Access
Categories and Access Identities (in case of network sharing, the
barring control information can be set individually for each PLMN). The
UE determines whether an access attempt is authorized based on the
barring information broadcast for the selected PLMN, and the selected
Access Category and Access Identity(ies) for the access attempt:

\- For NAS triggered requests, NAS determines the Access Category and
Access Identity(ies);

\- For AS triggered requests, RRC determines the Access Category while
NAS determines the Access Identity(ies).

The gNB handles access attempts with establishment or resume causes
\"emergency\", \"mps-PriorityAccess\" and \"mcs-PriorityAccess\" (i.e.
Emergency calls, MPS, MCS subscribers) with high priority and responds
with RRC Reject to these access attempts only in extreme network load
conditions that may threaten the gNB stability.

Unified access control does not apply to IAB-MTs or NCR-MTs.