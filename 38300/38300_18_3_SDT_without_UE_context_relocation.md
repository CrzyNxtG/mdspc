## 18.3 SDT without UE context relocation

The overall procedure for SDT procedure over RACH without UE context
relocation is illustrated in the figure 18.3-1.

![](media/image111.emf)

Figure 18.3-1. RA-based SDT without UE context relocation

1/2. The steps 1/2 are as defined in steps 1/2 in Figure 18.2-1.

3\. The last serving gNB decides not to relocate the full UE context for
SDT. In case that the Last Serving gNB has requested AMF for CN
Buffering as part of step 0 for the UE in RRC INACTIVE state with eDRX
cycle longer than 10.24 seconds, reachability of the UE is indicated to
the AMF by the last serving gNB using the MT Communication Handling
procedure as described in TS 23.501 \[3\] and TS 38.413 \[26\].

4\. The last serving gNB transfers a partial UE context including the
SDT related RLC context.

5\. The receiving gNB acknowledges receiving the partial UE context and
provides associated DL TNL address. The UE context is kept at the last
serving gNB and the SDT related RLC context is established at the
receiving gNB. Then UL/DL GTP-U tunnels are established for DRBs
configured for SDT, if any, and the UL SDT data and/or signalling, if
any, are forwarded to the last serving gNB, and then delivered to the
core network.

NOTE 1: The DL signalling from the last serving gNB, if any, is
forwarded to the receiving gNB via the RRC TRANSFER message, for which
the receiving gNB delivers it to the UE.

NOTE 1a: In case DL non-SDT data or DL non-SDT signalling arrives, or UE
assistance information (i.e. UL non-SDT data arrival indication) is
received from the UE, the last serving gNB terminates the SDT procedure
by sending the *RRCRelease* message.

NOTE 1b: The last serving gNB may terminate the SDT procedure by sending
the *RRCRelease* message based on (e.g. large size of) DL SDT data or DL
SDT signalling.

6\. The receiving gNB detects the end of SDT session and sends the
RETRIEVE UE CONTEXT CONFIRM message including whether this is a
\"normal\" end of SDT transaction or a radio link problem, or large SDT
volume from BSR.

7\. Upon receiving the RETRIEVE UE CONTEXT CONFIRM message and deciding
to terminate the SDT, the last serving gNB responds to the receiving gNB
with the RETRIEVE UE CONTEXT FAILURE message including an encapsulated
*RRCRelease* message. The receiving gNB shall release the established
partial UE context.

NOTE 2: Void.

NOTE 3: Void.

8\. The receiving gNB sends the *RRCRelease* message to the UE.

NOTE 4: Void.

NOTE 5: The last serving gNB may terminate the SDT procedure by sending
the *RRCRelease* message upon receiving the indication about large
uplink SDT data from the BSR from the receiving gNB in step 6.

NOTE 6: The Last Serving gNB may send the NGAP MT Communication Handling
Request message to the AMF to trigger CN buffering when the UE is put
again into RRC_INACTIVE state with eDRX cycle longer than 10.24 seconds.

9\. The UE moves to RRC_INACTIVE state if the suspend indication is
included in the *RRCRelease* message, or the UE may initiate RRC resume
procedure to transition to RRC_CONNECTED state if the resume indication
is included in the *RRCRelease* message. Or else, the UE moves to
RRC_IDLE state.