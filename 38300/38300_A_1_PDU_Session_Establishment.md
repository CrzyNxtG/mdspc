# A.1 PDU Session Establishment

The following figure shows an example message flow for a PDU session
establishment. NAS procedures details between gNB and 5GC can be found
in TS 23.501 \[3\], TS 23.502 \[22\] and TS 38.413 \[26\].

![](media/image113.wmf)

Figure A.1-1: PDU session establishment

1\. UE requests a PDU session establishment to AMF.

2\. AMF sends a PDU SESSION RESOURCE SETUP REQUEST message to gNB, which
includes the NAS message to be sent to the UE with NAS QoS related
information.

3\. gNB sends an *RRCReconfiguration* message to UE including the
configuration of at least one DRB and the NAS message received at Step
2.

4\. UE establishes the DRB(s) for the new PDU session and creates the
QFI to DRB mapping rules.

5\. UE sends an *RRCReconfiguration* *Complete* message to gNB.

6\. gNB sends a PDU SESSION RESOURCE SETUP RESPONSE message to AMF.

7\. User Plane Data can then be exchanged between UE and gNB over DRB(s)
according to the mapping rules and between UPF and gNB over the tunnel
for the PDU session. QFI marking over Uu is optional (see clause 12)
while QFI marking over NG-U is always present.