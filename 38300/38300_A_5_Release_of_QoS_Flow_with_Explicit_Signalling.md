# A.5 Release of QoS Flow with Explicit Signalling

The following figure shows an example message flow when the gNB receives
a request to release a QoS flow from CN that involves explicit NAS
signalling. NAS procedures details between gNB and 5GC can be found in
TS 23.501 \[3\], TS 23.502 \[22\] and TS 38.413 \[26\].

![](media/image117.wmf)

Figure A.5-1: Release of QoS Flow with Explicit Signalling

0\. PDU session and DRB(s) have been already established.

1\. gNB receives a PDU SESSION RESOURCE MODIFY REQUEST message from AMF
to release a QoS flow.

2\. The gNB decides to release corresponding the QFI to DRB mapping
rule. Since the DRB also carries other QoS flows, the DRB is not
released.

3\. gNB sends an *RRCReconfiguration* message to UE to release the QFI
to DRB mapping rule.

4\. UE updates the AS QFI to DRB mapping rules to release this QFI to
DRB mapping rule.

5\. UE sends an *RRCReconfigurationC*omplete message to gNB.

6\. gNB sends a PDU SESSION RESOURCE MODIFY RESPONSE message to AMF.