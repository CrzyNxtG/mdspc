# A.4 New QoS Flow with Explicit NAS Signalling

The following figure shows an example message flow when the gNB receives
a new QoS flow establishment request from CN that involves NAS explicit
signalling. The QoS flow establishment request provides the gNB and UE
with the QoS parameters for the QFI. In this example, the gNB decides to
establish a new DRB (rather than re-use an existing one) for this QoS
flow and provides the mapping rule over RRC signalling. NAS procedures
details between gNB and 5GC can be found in TS 23.501 \[3\], TS 23.502
\[22\] and TS 38.413 \[26\].

![](media/image116.wmf)

Figure A.4-1: DL data with new QoS Flow ID sent over new DRB with
explicit signalling

0\. PDU session DRB(s) have been already established.

1\. gNB receives a PDU SESSION RESOURCE MODIFY REQUEST message from AMF
for a new QoS flow.

2\. If gNB cannot find an existing DRB to map this new QoS flow, it
decides to establish a new DRB.

3\. gNB sends an *RRCReconfiguration* message to UE including the DRB
configuration with the new QFI to DRB mapping rule and the NAS message
received at step 1.

4\. UE establishes the DRB for the new QoS flow associated with this PDU
session and updates the mapping rules.

5\. UE sends an *RRCReconfigurationComplete* message to gNB.

6\. gNB sends a PDU SESSION RESOURCE MODIFY RESPONSE message to AMF.

7\. User Plane Data can then be exchanged between UE and gNB over DRB(s)
according to the mapping rules and between UPF and gNB over the tunnel
for the PDU session.