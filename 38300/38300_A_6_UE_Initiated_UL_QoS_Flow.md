# A.6 UE Initiated UL QoS Flow

The following figure shows an example message flow when the UE AS
receives an UL packet for a new QoS flow for which a QFI to DRB mapping
rule does not exist.

![](media/image118.wmf)

Figure A.6-1: UL packet with a new QoS flow for which a mapping does not
exist in UE

0\. PDU session and DRBs (including a default DRB) have been already
established.

1\. UE AS receives a packet with a new QFI from UE NAS.

2\. UE uses the QFI of the packet to map it to a DRB. If there is no
mapping of the QFI to a DRB in the AS mapping rules for this PDU
session, then the packet is assigned to the default DRB.

3\. UE sends the UL packet on the default DRB. The UE includes the QFI
in the SDAP header.

4\. gNB sends UL packets to UPF and includes the corresponding QFI.

5\. If gNB wants to use a new DRB for this QoS flow, it sets up one. It
can also choose to move the QoS flow to an existing DRB using RQoS or
RRC signalling (see clauses A.2 and A.3).

6\. User Plane Data for the new QoS flow can then be exchanged between
UE and gNB over the DRB according to the updated mapping rules and
between UPF and gNB over the tunnel for the PDU session.