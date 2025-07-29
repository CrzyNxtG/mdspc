## 18.2 SDT with UE context relocation

The overall procedure for SDT procedure over RACH with UE context
relocation is illustrated in the figure 18.2-1.

![](media/image110.emf)

Figure 18.2-1. RA-based SDT with UE context relocation

1\. The UE sends an *RRCResumeRequest* as well as UL SDT data and/or UL
SDT signalling to the Receiving gNB.

2\. The Receiving gNB identifies the Last Serving gNB using the I-RNTI
and retrieves the UE context by means of Xn-AP Retrieve UE Context
procedure. The Receiving gNB indicates that the UE request is for an SDT
and may also provide SDT assistance information (e.g., single packet,
multiple packets).

3\. The Last Serving gNB decides to relocate UE context and responds
with the RETRIEVE UE CONTEXT RESPONSE message. The UL SDT data, if any,
is delivered from the Receiving gNB to the UPF. In case that the Last
Serving gNB has requested the AMF for CN Buffering as part of step 0 for
the UE in RRC INACTIVE state with eDRX cycle longer than 10.24 seconds,
reachability of the UE can be indicated to the AMF by the last serving
gNB using the MT Communication Handling procedure as described in TS
23.501 \[3\] and TS 38.413 \[26\], otherwise, the AMF considers that the
UE is reachable (i.e., the MT Communicating Handing is deactivated) upon
step 5.

4-6. The Receiving gNB decides to keep UE in RRC_INACTIVE state for SDT.
If loss of DL user data buffered in the Last Serving gNB shall be
prevented, the Receiving gNB provides forwarding addresses via the Xn-U
ADDRESS INDICATION message. The Receiving gNB also initiates NGAP Path
Switch Request procedure to establish a NG UE-associated signalling
connection to the AMF. After the Path Switch Request procedure, the
buffered UL NAS PDU, if any, is delivered from the Receiving gNB to the
AMF. And then, the subsequent UL/DL SDT data and/or signalling are
transferred between UE and core network via the Receiving gNB.

NOTE 1: If the UP policy received from the Last Serving gNB is different
from that received in the PATH SWITCH REQUEST ACKNOWLEDGE message, the
Receiving gNB may either send the UE back to RRC_IDLE or move the UE to
RRC_CONNECTED to update the security configuration.

7\. After the SDT transmission is terminated, the Receiving gNB
generates and sends the *RRCRelease* message including the suspend
indication to the UE to terminate the SDT procedure and continue in
RRC_INACTIVE state.

NOTE 2: In case DL non-SDT data or DL non-SDT signalling arrives, or the
UE assistance information (i.e. UL non-SDT data arrival indication) is
received from the UE, the Receiving gNB may decide to directly send the
UE to RRC_CONNECTED state by sending the *RRCResume* message.

NOTE 3: The Receiving gNB may decide to directly send the UE to
RRC_CONNECTED state by sending the *RRCResume* message based on (e.g.
large size of) DL SDT data or DL SDT signalling.

NOTE 4: The Receiving gNB may decide to directly send the UE to
RRC_CONNECTED state by sending the *RRCResume* message based on the BSR
received from the UE in case of uplink SDT data exceeding the data size
threshold.

NOTE 5: The Receiving gNB may send the NGAP MT Communication Handling
Request message to the AMF to trigger CN buffering when the UE is put
again into RRC_INACTIVE state with eDRX cycle longer than 10.24 seconds.

8\. The Receiving gNB indicates to the Last Serving gNB to remove the UE
context by sending the XnAP UE CONTEXT RELEASE message. The XnAP UE
CONTEXT RELEASE message can be sent after step 6.