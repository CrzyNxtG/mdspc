# A.2 New QoS Flow with RQoS

The following figure shows an example message flow when RQoS is used for
a new QoS flow. In this example, the gNB receives from UPF a first
downlink packet associated with a QFI for which the QoS parameters are
known from the PDU session establishment, but for which there is no
association to any DRB yet in AS.

![](media/image114.wmf)

Figure A.2-1: DL data with new QFI sent over existing DRB

0\. PDU session and DRB(s) have been already established.

1\. gNB receives a downlink packet with a new QFI from UPF.

2\. gNB decides to send the new QoS flow over an existing DRB.

NOTE: If gNB decides to send it over a new DRB, it needs to establish
the DRB first.

3\. gNB sends the DL packet over the selected DRB with the new QFI and
RDI set in the SDAP header.

4\. UE identifies the QFI and RDI in the received DL packet and the DRB
on which the packet was received. The AS mapping rules are then updated
accordingly.

5\. User Plane Data for the new QoS flow can then be exchanged between
UE and gNB over the DRB according to the updated mapping rules and
between UPF and gNB over the tunnel for the PDU session.