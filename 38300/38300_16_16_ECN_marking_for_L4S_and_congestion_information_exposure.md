## 16.16 ECN marking for L4S and congestion information exposure

In order to support ECN marking for L4S at gNB as specified in TS
23.501\[3\], SMF provides ECN marking request per QoS flow level to the
gNB as part of PDU Session Resource Management procedure. If the gNB
supports ECN marking, it provides the status indication back to the SMF
which is used by the SMF as specified in TS 23.501\[3\]. During Xn
Handover Preparation procedure, source gNB provides the ECN marking
request to target gNB.

When ECN marking for L4S at gNB is enabled for downlink or uplink, the
gNB should set the Congestion Experienced (CE) codepoint in downlink or
uplink SDAP SDU(s) as per the recommendations in IETF RFC 9330 \[61\],
IETF RFC 9331 \[62\] and IETF RFC 9332 \[63\].

For ECN marking for L4S at UPF, SMF requests the gNB to report
congestion information per QoS flow level as part of PDU Session
Resource Management procedure. If the gNB supports ECN marking for L4S
at UPF, it provides the status indication back to the SMF which is used
by SMF as specified in TS 23.501\[3\]. During Xn Handover Preparation
procedure, source gNB provides the ECN marking UPF request to target
gNB.

For congestion reporting from gNB to UPF, SMF requests the gNB to report
congestion information per QoS flow level as part of PDU Session
Resource Management procedure. If the NG-RAN supports congestion
information reporting, it provides the status indication back to the SMF
which is used by the SMF as specified in TS 23.501\[3\]. During Xn
Handover Preparation procedure, source gNB provides the congestion
information request to target gNB.