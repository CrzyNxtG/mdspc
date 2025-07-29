## 18.4 MT-SDT with/without UE context relocation

The overall procedure for MT-SDT procedure with/without UE context
relocation is illustrated in the figure 18.4-1.

![](media/image112.emf)

Figure 18.4-1: MT-SDT with/without UE context relocation

1\. DL user data and/or DL NAS signalling are received at the Last
Serving gNB for the UE in RRC_INACTIVE state, or RAN Paging request
message is received at the Last Serving gNB for the UE in RRC_INACTIVE
state with long eDRX(cycle) beyond 10.24 seconds.

2\. The Last Serving gNB may send MT-SDT information to the neighbour
gNBs within the RNA, via XnAP RAN PAGING message.

3\. The gNB that receives MT-SDT information within the RNA, takes into
account the MT-SDT information received in the XnAP RAN PAGING message
to decide whether to trigger MT-SDT Paging. The gNB which ultimately
reaches the UE via the Uu Paging becomes the Receiving gNB.

NOTE 1: In case that the Receiving gNB decides not to trigger MT-SDT
paging, the above step 3 and subsequent steps are the same as Figure
9.2.2.4.2 from step 3.

4/5. The UE may decide to initiate MT-SDT procedure and in this case
sends an RRCResumeRequest message with an MT-SDT resume cause to the
Receiving gNB.

6\. The following steps are the same as Figure 18.2-1/18.3-1 from step
2, except that the first SDT user data and/or NAS signalling is DL SDT
data and/or DL SDT NAS signalling.

NOTE 2: In case DL non-SDT data or DL non-SDT signalling has arrived
between step 2 and step 6, the Last Serving gNB should relocate the UE
context to the Receiving gNB and forward the received data to the
Receiving gNB.