## 18.1 Support of SDT procedure over RACH

For SDT procedure over RACH, if the UE accesses a gNB other than the
last serving gNB, the UL SDT data/signalling is buffered at the
receiving gNB, and then the receiving gNB triggers the XnAP Retrieve UE
Context procedure. The receiving gNB indicates SDT to the last serving
gNB and the last serving gNB decides whether to relocate the UE context
or not. Other SDT assistance information (e.g., single packet, multiple
packets) may also be provided by the receiving gNB to help the decision
of UE context relocation. If the UE is configured with the clock quality
control information, the last serving gNB performs full UE context
relocation to enable the receiving gNB to provide clock quality
information.

If the last serving gNB decides not to relocate the full UE context, it
transfers a partial UE context containing SDT RLC context information
necessary for the receiving gNB to handle SDT via the Partial UE Context
Transfer procedure.

Then, in case SDT is used for user data over DRBs, UL/DL tunnels are
established for DRBs configured for SDT between the receiving gNB and
the last serving gNB. The PDCP PDU of UL/DL data is transferred over the
tunnels, until the last serving gNB terminates the SDT session and
directs the UE to continue in RRC_INACTIVE by sending the *RRCRelease*
message.

Or in case SDT is used for signalling, SRB PDCP PDUs are transferred
between the receiving gNB and the last serving gNB via the XnAP RRC
Transfer procedure, until the last serving gNB terminates the SDT
session and directs the UE to continue in RRC_INACTIVE by sending the
*RRCRelease* message.

During the SDT session, in case the receiving gNB detects that no more
packets are to be transmitted, or radio link problem is detected, the
receiving gNB may also request to terminate the SDT session to the last
serving gNB via the UE Context Retrieve Confirmation procedure.