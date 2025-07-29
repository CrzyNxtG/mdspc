## 3.2 Definitions

For the purposes of the present document, the terms and definitions
given in TR 21.905 \[1\], in TS 36.300 \[2\] and the following apply. A
term defined in the present document takes precedence over the
definition of the same term, if any, in TR 21.905 \[1\] and TS 36.300
\[2\].

**2Rx XR UE**: two antenna port XR UE as specified in TS 38.101-1
\[18\].

**A2X communication**: A communication to support A2X services
leveraging PC5 reference points. A2X services are realized by various
types of A2X applications, i.e. BRID or DAA.

**Aerial UE communication:** functionality enabling Aerial UE function,
as defined in 16.18.

**Air to Ground network:** An NG-RAN consisting of ground-based gNBs,
which provide cell towers that send signals up to an aircraft\'s
antenna(s) of onboard ATG terminal, with typical vertical altitude of
around 10,000m and take-off/landing altitudes down to 3000m.

**BH RLC channel**: an RLC channel between two nodes, which is used to
transport backhaul packets**.**

**Boundary IAB-node:** as defined in TS 38.401 \[4\].

**Broadcast MRB**: A radio bearer configured for MBS broadcast delivery.

**CAG Cell**: a PLMN cell broadcasting at least one Closed Access Group
identity.

**CAG Member Cell**: for a UE, a CAG cell broadcasting the identity of
the selected PLMN, registered PLMN or equivalent PLMN, and for that
PLMN, a CAG identifier belonging to the Allowed CAG list of the UE for
that PLMN.

**CAG-only cell**: a CAG cell that is only available for normal service
for CAG UEs.

**Cell-Defining SSB**: an SSB with an RMSI associated.

**Child node**: IAB-DU\'s and IAB-donor-DU\'s next hop neighbour node;
the child node is also an IAB-node.

**Conditional Handover (CHO**): a handover procedure that is executed
only when execution condition(s) are met.

**CORESET#0**: the control resource set for at least SIB1 scheduling,
can be configured either via MIB or via dedicated RRC signalling.

**DAPS Handover**: a handover procedure that maintains the source gNB
connection after reception of RRC message for handover and until
releasing the source cell after successful random access to the target
gNB.

**Data Burst:** A set of multiple PDUs generated and sent by the
application in a short period of time, as defined in TS 23.501 \[3\].

**Direct Path**: a type of UE-to-Network transmission path, where data
is transmitted between a UE and the network without sidelink relaying.

**Downstream**: direction toward child node or UE in IAB-topology.

**Early Data Forwarding**: data forwarding that is initiated before the
UE executes the handover.

**Earth-centered, earth-fixed**: a global geodetic reference system for
the Earth intended for practical applications of mapping, charting,
geopositioning and navigation, as specified in NIMA TR 8350.2 \[51\].

**eRedCap UE**: a UE with enhanced reduced capabilities as specified in
clause 4.2.22.1 in TS 38.306 \[11\].

**Feeder link**: wireless link between the NTN Gateway and the NTN
payload.

**Geosynchronous Orbit**: earth-centered orbit at approximately 35786
kilometres above Earth\'s surface and synchronised with Earth\'s
rotation. A geostationary orbit is a non-inclined geosynchronous orbit,
i.e. in the Earth\'s equator plane.

**Group ID for Network Selection**: an identifier used during SNPN
selection to enhance the likelihood of selecting a preferred SNPN that
supports a Default Credentials Server or a Credentials Holder, as
specified in TS 23.501 \[3\].

**gNB**: node providing NR user plane and control plane protocol
terminations towards the UE, and connected via the NG interface to the
5GC.

**High Altitude Platform Station**: airborne vehicle embarking the NTN
payload placed at an altitude between 8 and 50 km.

**IAB-donor**: gNB that provides network access to UEs via a network of
backhaul and access links.

**IAB-donor-CU**: as defined in TS 38.401 \[4\].

**IAB-donor-DU**: as defined in TS 38.401 \[4\].

**IAB-DU**: gNB-DU functionality supported by the IAB-node to terminate
the NR access interface to UEs and next-hop IAB-nodes, and to terminate
the F1 protocol to the gNB-CU functionality, as defined in TS 38.401
\[4\], on the IAB-donor.

**IAB-MT**: IAB-node function that terminates the Uu interface to the
parent node using the procedures and behaviours specified for UEs unless
stated otherwise. IAB-MT function used in 38-series of 3GPP
Specifications corresponds to IAB-UE function defined in TS 23.501
\[3\].

**IAB-node**: RAN node that supports NR access links to UEs and NR
backhaul links to parent nodes and child nodes. The IAB-node does not
support backhauling via LTE.

**IAB topology**: the unison of all IAB-nodes and IAB-donor-DUs whose F1
and/or RRC connections are terminated at the same IAB-donor-CU.

**Indirect Path**: a type of UE-to-Network transmission path, where data
is forwarded via a U2N Relay UE between a U2N Remote UE and the network.

**Inter-donor partial migration:** migration of an IAB-MT to a parent
node underneath a different IAB-donor-CU while the collocated IAB-DU and
its descendant IAB-node(s), if any, are terminated at the initial
IAB-donor-CU. The procedure renders the said IAB-node as a boundary
IAB-node.

**Intra-system Handover**: handover that does not involve a CN change
(EPC or 5GC).

**Inter-system Handover**: handover that involves a CN change (EPC or
5GC).

**Late Data Forwarding**: data forwarding that is initiated after the
source NG-RAN node knows that the UE has successfully accessed a target
NG-RAN node.

**L1/L2 Triggered Mobility**: a cell switch procedure that the network
triggers via MAC CE based on L1 or L3 measurement report.

**Mapped Cell ID**: in NTN, it corresponds to a fixed geographical area.

**MBS Radio Bearer**: A radio bearer configured for MBS delivery.

**Mobile-IAB cell**: a cell of a mobile IAB-DU.

**Mobile IAB-DU**: gNB-DU functionality supported by the mobile IAB-node
to terminate the NR access interface to UEs, and to terminate the F1
protocol to the gNB-CU functionality on the IAB-donor, as defined in TS
38.401 \[4\].

**Mobile IAB-DU migration**: procedure for a mobile IAB-node as defined
in TS 38.401 \[4\].

**Mobile IAB-MT**: mobile IAB-node function that terminates the Uu
interface to the parent node using the procedures and behaviours
specified for UEs unless stated otherwise.

**Mobile IAB-MT migration**: procedure for a mobile IAB-MT as defined in
TS 38.401 \[4\].

**Mobile IAB-node**: RAN node that supports NR access links to UEs and
an NR backhaul link to a parent node, and that can conduct physical
mobility across the RAN area. The mobile IAB-node function used in
38-series of 3GPP Specifications corresponds to the MBSR function
defined in TS 23.501 \[3\].

**MP Relay UE**: a UE that provides functionality to support
connectivity to the network for MP Remote UE(s).

**MP Remote UE**: a UE that communicates with the network via a direct
Uu link and a MP Relay UE.

**MSG1**: preamble transmission of the random access procedure for
4-step random access (RA) type.

**MSG3**: first scheduled transmission of the random access procedure.

**MSGA**: preamble and payload transmissions of the random access
procedure for 2-step RA type.

**MSGB**: response to MSGA in the 2-step random access procedure. MSGB
may consist of response(s) for contention resolution, fallback
indication(s), and backoff indication.

**Multicast/Broadcast Service**: A point-to-multipoint service as
defined in TS 23.247 \[45\].

**Multicast MRB**: A radio bearer configured for MBS multicast delivery.

**Multi-hop backhauling**: using a chain of NR backhaul links between an
IAB-node and an IAB-donor.

**NCR-Fwd**: Network-Controlled Repeater node function, which performs
amplifying-and-forwarding of UL/DL RF signals between gNB and UE. The
behaviour of the NCR-Fwd is controlled according to the side control
information received by the NCR-MT from a gNB.

**NCR-Fwd access link**: link used for transmissions between the NCR-Fwd
and UEs.

**NCR-Fwd backhaul link**: link used for backhauling between the NCR-Fwd
and gNB.

**NCR-MT**: NCR-node entity which communicates with a gNB via a control
link to receive side control information. The control link is based on
NR Uu interface.

**NCR-node**: RAN node comprising NCR-MT and NCR-Fwd.

**ng-eNB**: node providing E-UTRA user plane and control plane protocol
terminations towards the UE, and connected via the NG interface to the
5GC.

**NG-C**: control plane interface between NG-RAN and 5GC.

**NG-U**: user plane interface between NG-RAN and 5GC.

**NG-RAN node**: either a gNB or an ng-eNB.

**Non-CAG Cell**: a PLMN cell which does not broadcast any Closed Access
Group identity.

**Non-Cell Defining SSB**: an SSB without an RMSI associated.

**Non-Geosynchronous orbit**: earth-centered orbit with an orbital
period that does not match Earth\'s rotation on its axis. This includes
Low and Medium Earth Orbit (LEO and MEO). LEO operates at altitudes
between 300 km and 1500 km and MEO at altitudes between 7000 km and
25000 km, approximately.

**Non-terrestrial network**: an NG-RAN consisting of gNBs, which provide
non-terrestrial NR access to UEs by means of an NTN payload embarked on
an airborne or space-borne NTN vehicle and an NTN Gateway.

**NR backhaul link**: NR link used for backhauling between an IAB-node
and an IAB-donor, and between IAB-nodes in case of a multi-hop
backhauling.

**NR sidelink communication**: AS functionality enabling at least V2X
communication as defined in TS 23.287 \[40\] and/or A2X communication as
defined in TS 23.256 \[60\] and/or the ProSe communication (including
ProSe non-Relay and UE-to-Network Relay communication) as defined in TS
23.304 \[48\], between two or more nearby UEs, using NR technology but
not traversing any network node.

**NR sidelink discovery**: AS functionality enabling ProSe non-Relay
Discovery and ProSe UE-to-Network Relay discovery for Proximity based
Services as defined in TS 23.304 \[48\] between two or more nearby UEs,
using NR technology but not traversing any network node.

**NTN Gateway**: an earth station located at the surface of the earth,
providing connectivity to the NTN payload using the feeder link. An NTN
Gateway is a TNL node.

**NTN payload**: a network node, embarked on board a satellite or high
altitude platform station, providing connectivity functions, between the
service link and the feeder link. In the current version of this
specification, the NTN payload is a TNL node.

**Numerology**: corresponds to one subcarrier spacing in the frequency
domain. By scaling a reference subcarrier spacing by an integer *N*,
different numerologies can be defined.

**Parent node**: IAB-MT\'s or mobile IAB-MT\'s next hop neighbour node;
the parent node can be an IAB-node or IAB-donor-DU

**PC5 Relay RLC channel**: an RLC channel between L2 U2N Remote UE and
L2 U2N Relay UE, or between L2 U2U Remote UE and L2 U2U Relay UE, which
is used to transport packets over PC5 for L2 UE-to-Network/UE-to-UE
Relay**.**

**PDU Set**: one or more PDUs carrying the payload of one unit of
information generated at the application level (e.g. frame(s) or video
slice(s) for XR Services), as defined in TS 23.501 \[3\].

**PLMN Cell**: a cell of the PLMN.

**RACH-less LTM**: an LTM cell switch procedure where UE skips the
random access procedure.

**RedCap UE**: a UE with reduced capabilities as specified in clause
4.2.21.1 in TS 38.306 \[11\].

**Relay discovery**: AS functionality enabling 5G ProSe UE-to-Network
Relay Discovery as defined in TS 23.304 \[48\], using NR technology but
not traversing any network node.

**Satellite**: a space-borne vehicle orbiting the Earth embarking the
NTN payload.

**Service link**: wireless link between the NTN payload and UE.

**Sidelink Discovery RSRP:** RSRP measurements on PC5 link related to NR
sidelink discovery.

**Sidelink RSRP:** RSRP measurements on PC5 link related to NR sidelink
communication.

**SNPN Access Mode**: mode of operation whereby a UE only accesses
SNPNs.

**SNPN-only cell**: a cell that is only available for normal service for
SNPN subscribers.

**SNPN Identity**: the identity of Stand-alone NPN defined by the pair
(PLMN ID, NID).

**Special Cell:** For Dual Connectivity operation the term Special Cell
refers to the PCell of the MCG or the PSCell of the SCG, otherwise, in
case of NR Standalone, the term Special Cell refers to the PCell.

**Transmit/Receive Point**: part of the gNB transmitting and receiving
radio signals to/from UE according to physical layer properties and
parameters inherent to that element.

**U2N Relay UE**: a UE that provides functionality to support
connectivity to the network for U2N Remote UE(s).

**U2N Remote UE**: a UE that communicates with the network via a U2N
Relay UE.

**U2U Relay UE**: a UE that provides functionality to support
connectivity between two U2U Remote UEs.

**U2U Remote UE**: a UE that communicates with other UE(s) via a U2U
Relay UE.

**Upstream**: direction toward parent node in IAB-topology.

**Uu Relay RLC channel**: an RLC channel between L2 U2N Relay UE or MP
Relay UE and gNB, which is used to transport packets over Uu for L2
UE-to-Network Relay or for indirect path in case of MP.

**V2X sidelink communication**: AS functionality enabling V2X
communication as defined in TS 23.285 \[41\], between nearby UEs, using
E-UTRA technology but not traversing any network node.

**Xn**: network interface between NG-RAN nodes.