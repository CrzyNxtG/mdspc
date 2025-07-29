# A.3 New QoS Flow with Explicit RRC Signalling

The following figure shows an example message flow when explicit RRC
signalling is used for a new QoS flow. In this example, the gNB receives
from UPF a first downlink packet associated with a QFI, for which the
QoS parameters are already known from the PDU session establishment, but
for which there is no association to any DRB yet in AS.

![](media/image115.wmf)

Figure A.3-1: DL data with new QFI sent over existing DRB

0\. PDU session and DRB(s) have been already established.

1\. gNB receives a downlink packet with a new QFI from UPF.

2\. gNB decides to send the new QoS flow over an existing DRB using
explicit RRC signalling for updating the AS mapping rules.

3\. gNB sends an *RRCReconfiguration* message to UE with the new QFI to
DRB mapping rule. gNB may also decide to update the DRB configuration if
required to meet the QoS requirements for the new QoS Flow.

4\. UE updates the QFI to DRB mapping rules and configuration (if
received).

5\. UE sends an *RRCReconfigurationComplete* message to gNB.

6\. User Plane Data for the new QoS flow can then be exchanged between
UE and gNB over the DRB according to the updated mapping rules and
between UPF and gNB over the tunnel for the PDU session.