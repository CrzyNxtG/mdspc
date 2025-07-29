### 4.7.2 Protocol Stacks

Fig. 4.7.2-1 shows the protocol stack for F1-U and Fig. 4.7.2-2 shows
the protocol stack for F1-C between IAB-DU and IAB-donor-CU. In these
figures, F1-U and F1-C are carried over two backhaul hops.

F1-U and F1-C use an IP transport layer between IAB-DU and IAB-donor-CU
as defined in TS 38.470 \[32\]. F1-U and F1-C need to be
security-protected as described in TS 33.501 \[5\] (the security layer
is not shown in the Figures 4.7.2-1/2).

On the wireless backhaul, the IP layer is carried over the Backhaul
Adaptation Protocol (BAP) sublayer, which enables routing over multiple
hops. The IP layer can also be used for *non*-F1 traffic, such as OAM
traffic as defined in TS 38.401 \[4\].

On each backhaul link, the BAP PDUs are carried by BH RLC channels.
Multiple BH RLC channels can be configured on each BH link to allow
traffic prioritization and QoS enforcement. The BH-RLC-channel mapping
for BAP PDUs is performed by the BAP entities on each IAB-node and the
IAB-donor-DU.

Protocol stacks for an IAB-donor with split gNB architecture are
specified in TS 38.401 \[4\].

![](media/image13.emf)

Fig. 4.7.2-1: Protocol stack for the support of F1-U protocol

![](media/image14.emf)

Fig. 4.7.2-2: Protocol stack for the support of F1-C protocol

The IAB-MT further establishes SRBs (carrying RRC and NAS) with the
IAB-donor-CU. For IAB-nodes operating in EN-DC, the IAB-MT establishes
one or more DRBs with the eNB and one or more DRBs with the
IAB-donor-CU, which can be used, e.g., to carry OAM traffic. For SA
mode, the establishment of DRBs is optional. These SRBs and DRBs are
transported between the IAB-MT and its parent node over Uu access
channel(s). The protocol stacks for the SRB is shown in Fig. 4.7.2-3.

![](media/image15.emf)

Figure 4.7.2-3: Protocol stack for the support of IAB-MT\'s RRC and NAS
connections