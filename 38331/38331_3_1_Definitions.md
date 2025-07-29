## 3.1 Definitions

For the purposes of the present document, the terms and definitions
given in TR 21.905 \[1\] and the following apply. A term defined in the
present document takes precedence over the definition of the same term,
if any, in TR 21.905 \[1\].

**2Rx XR UE:** Two antenna port XR UE as specified in TS 38.101-1
\[15\].

**A2X communication:** A communication to support A2X services
leveraging PC5 reference points, as defined in TS 23.256 \[76\]. A2X
services are realized by various types of A2X applications, e.g., BRID
or DAA.

**Additional sidelink RLC bearer:** If the sidelink PDCP entity is
associated with two sidelink RLC entities, the additional sidelink RLC
bearer is the RLC bearer configured by
*sl-RLC-BearerToAddModListSizeExt* in *sl-ConfigDedicatedNR*, or
*sl-RLC-BearerConfigListSizeExt* in *SIB12* or in *SidelinkPreconfigNR*.

**Aerial UE:** UE performing Aerial UE communication, as defined in TS
38.300 \[2\], clause 16.18 and TS 23.256 \[76\].

**AM MRB:** An MRB associated with at least an AM RLC bearer for PTP
transmission.

**BH RLC channel:** An RLC channel between two nodes, which is used to
transport backhaul packets.

**Broadcast MRB:** A radio bearer configured for MBS broadcast delivery.

**CEIL:** Mathematical function used to \'round up\' i.e. to the nearest
integer having a higher or equal value.

**DAPS bearer:** a bearer whose radio protocols are located in both the
source gNB and the target gNB during DAPS handover to use both source
gNB and target gNB resources.

**Data Burst:** A set of multiple PDUs generated and sent by the
application in a short period of time, as defined in TS 23.501 \[32\].

**Dedicated signalling:** Signalling sent on DCCH logical channel
between the network and a single UE.

**Dormant BWP:** The dormant BWP is one of downlink BWPs configured by
the network via dedicated RRC signalling. In the dormant BWP, the UE
stops monitoring PDCCH on/for the SCell, but continues performing CSI
measurements, Automatic Gain Control (AGC) and beam management, if
configured. For each serving cell other than the SpCell or PUCCH SCell,
the network may configure one BWP as a dormant BWP.

**Earth-fixed cell:** An NTN cell fixed with respect to a certain
geographic area on Earth. It can be provisioned by beam(s) continuously
covering the same geographical area (e.g., the case of GSO satellites).

**Earth-moving cell:** An NTN cell moving on the ground. It can be
provisioned by beam(s) whose coverage area slides over the Earth\'s
surface (e.g., the case of NGSO satellites generating fixed or
non-steerable beams).

**eRedCap UE:** A UE with enhanced reduced capabilities as specified in
clause 4.2.22.1 in TS 38.306 \[26\].

**Field:** The individual contents of an information element are
referred to as fields.

**FLOOR:** Mathematical function used to \'round down\' i.e. to the
nearest integer having a lower or equal value.

**Frequency Selection Area ID:** An identity used for broadcast MBS
session to guide the frequency selection of the UE as defined in TS
23.247 \[67\].

**Global cell identity:** An identity to uniquely identifying an NR
cell. It is consisted of *cellIdentity* and *plmn-Identity* of the first
*PLMN-Identity* in *plmn-IdentityList* in SIB1.

**Information element:** A structural element containing single or
multiple fields is referred as information element.

**Candidate configuration:** A configuration part of an
*RRCReconfiguration* message associated with a candidate cell, e.g., for
LTM or subsequent CPAC. A candidate configuration can be a complete
candidate configuration or a delta configuration relatively to a
reference configuration.

**Reference configuration:** A configuration provided by the network to
the UE that is common, within the same cell group, to a group of
configured non-complete candidate configurations.

**MBS Radio Bearer:** A radio bearer that is configured for MBS
delivery.

**Mobile IAB-MT**: mobile IAB-node function that terminates the Uu
interface to the parent node using the procedures and behaviours
specified for UEs unless stated otherwise. The mobile IAB-MT uses the
same procedures and behaviours specified for the IAB-MT, unless
explicitly stated otherwise.

**Mobile IAB-node**: RAN node that supports NR access links to UEs and
an NR backhaul link to a parent node, and that can conduct physical
mobility across the RAN area. The mobile IAB-node function used in
38-series of 3GPP Specifications corresponds to the MBSR function
defined in TS 23.501 \[32\]. The mobile IAB-node uses the same
procedures and behaviours specified for the IAB-node, unless explicitly
stated otherwise.

**Multicast/Broadcast Service:** A point-to-multipoint service as
defined in TS 23.247 \[67\].

**Multicast MRB:** A radio bearer configured for MBS multicast delivery.

**MUSIM gap:** Period that the UE may use to perform MUSIM operations.

**Multi-path:** Mode of operation of a UE in RRC_CONNECTED configured
with one direct path on which the UE connects to gNB using NR Uu, and
one indirect path on which the UE connects to the same gNB via another
UE using PC5 unicast link or Non-3GPP Connection.

**MP remote UE:** A UE configured with Multi-path. When the connectivity
of indirect path is PC5 unicast link, the MP remote UE is acting as a L2
U2N Remote UE. When the connectivity of indirect path is Non-3GPP
Connection, the MP remote UE is acting as a N3C remote UE.

**MP relay UE:** A UE that provides connectivity of indirect path to a
MP remote UE. When the connectivity is PC5 unicast link, the MP relay UE
is acting as a L2 U2N Relay UE. When the connectivity is Non-3GPP
Connection, the MP relay UE is acting as a N3C relay UE.

**NCSG:** Network controlled small gap as defined in TS 38.133 \[14\].

**NPN-only Cell**: A cell that is only available for normal service for
NPNs\' subscriber. An NPN-capable UE determines that a cell is NPN-only
Cell by detecting that the *cellReservedForOtherUse* IE is set to true
while the *npn-IdentityInfoList* IE is present in
*CellAccessRelatedInfo*.

**N3C indirect path:** In Multi-path, the indirect path using Non-3GPP
Connection between remote UE and relay UE.

**NR sidelink communication**: AS functionality enabling at least V2X
Communication as defined in TS 23.287 \[55\] and/or A2X Communication as
defined in TS 23.256 \[76\] and/or ProSe Communication (including ProSe
UE-to-Network Relay, non-Relay communication, and ProSe UE-to-UE Relay
Communication including UE-to-UE Relay communication with integrated
discovery) as defined in TS 23.304 \[65\] between two or more nearby
UEs, using NR technology but not traversing any network node.

**NR sidelink discovery**: AS functionality enabling ProSe non-Relay
Discovery, ProSe UE-to-Network Relay discovery and ProSe UE-to-UE Relay
discovery for Proximity based Services as defined in TS 23.304 \[65\]
between two or more nearby UEs, using NR technology but not traversing
any network node.

**NR sidelink positioning:** AS functionality which determines
geographical or relative location and possibly velocity of a target UE
or ranging via PC5 interface using SL-PRS transmission and reception as
defined in TS 38.305 \[73\] and TS 38.355 \[77\].

**PNI-NPN identity:** an identifier of a PNI-NPN comprising of a PLMN ID
and a CAG-ID combination.

**Primary Cell**: The MCG cell, operating on the primary frequency, in
which the UE either performs the initial connection establishment
procedure or initiates the connection re-establishment procedure.

**PC5 Relay RLC channel**: An RLC channel between L2 U2N Remote UE and
L2 U2N Relay UE, or between L2 U2U Remote UE and L2 U2U Relay UE, which
is used to transport packets over PC5 for L2 UE-to-Network relay or L2
UE-to-UE relay.

**PDU Set**: one or more PDUs carrying the payload of one unit of
information generated at the application level (e.g. frame(s) or video
slice(s) for XR Services), as defined in TS 23.501 \[32\].

**Primary SCG Cell**: For dual connectivity operation, the SCG cell in
which the UE performs random access when performing the Reconfiguration
with Sync procedure.

**Primary Timing Advance Group**: Timing Advance Group containing the
SpCell.

**PUCCH SCell:** An SCell configured with PUCCH by *PUCCH-Config*.

**PUSCH-Less SCell:** An SCell configured without PUSCH.

**Quasi-Earth-fixed cell**: An NTN cell fixed with respect to a certain
geographic area on Earth during a certain time duration. It can be
provisioned by beam(s) covering one geographic area for a limited period
and a different geographic area during another period (e.g., the case of
NGSO satellites generating steerable beams).

**RedCap UE:** A UE with reduced capabilities as specified in clause
4.2.21.1 in TS 38.306 \[26\].

**RLC bearer configuration:** The lower layer part of the radio bearer
configuration comprising the RLC and logical channel configurations.

**Secondary Cell**: For a UE configured with CA, a cell providing
additional radio resources on top of Special Cell.

**Secondary Cell Group**: For a UE configured with dual connectivity,
the subset of serving cells comprising of the PSCell and zero or more
secondary cells.

**Serving Cell**: For a UE in RRC_CONNECTED not configured with CA/DC
there is only one serving cell comprising of the primary cell. For a UE
in RRC_CONNECTED configured with CA/ DC the term \'serving cells\' is
used to denote the set of cells comprising of the Special Cell(s) and
all secondary cells.

**Small Data Transmission**: A procedure used for transmission of data
and/or signalling over allowed radio bearers in RRC_INACTIVE state (i.e.
without the UE transitioning to RRC_CONNECTED state). The SDT procedure
is considered to be ongoing once the conditions for initating SDT as
specified in clause 5.3.13.1b are fulfilled until the SDT procedure is
completed either successfully or unsuccessfully as specified in clause
18.0 in TS 38.300 \[2\].

**SNPN identity:** an identifier of an SNPN comprising of a PLMN ID and
an NID combination.

**SL indirect path:** In Multi-path, the indirect path using PC5 unicast
link between remote UE and relay UE.

**Special Cell:** For Dual Connectivity operation the term Special Cell
refers to the PCell of the MCG or the PSCell of the SCG, otherwise the
term Special Cell refers to the PCell.

**Split DRB:** In MR-DC, a DRB that supports transmission via MCG and
SCG, as well as duplication of PDCP PDUs as defined in TS 37.340 \[41\];
or in MP, a DRB that supports transmission via direct path and indirect
path, as well as duplication of PDCP PDUs.

**Split SRB**: In MR-DC, an SRB that supports transmission via MCG and
SCG as well as duplication of RRC PDUs as defined in TS 37.340 \[41\];
or in MP, a SRB that supports transmission via direct path and indirect
path, as well as duplication of PDCP PDUs.

**SSB Frequency**: Frequency referring to the position of resource
element RE=#0 (subcarrier #0) of resource block RB#10 of the SS block.

**U2N Relay UE**: A UE that provides functionality to support
connectivity to the network for U2N Remote UE(s).

**U2N Remote UE**: A UE that communicates with the network via a U2N
Relay UE.

**U2U Relay UE:** A UE that provides functionality to support
connectivity between two U2U Remote UEs.

**U2U Remote UE:** A UE that communicates with other UEs via a U2U Relay
UE.

**Uu Relay RLC channel**: An RLC channel between L2 U2N Relay UE and
gNB, which is used to transport packets over Uu for L2 UE-to-Network
relay or for indirect path in case of MP**.**

**UE Inactive AS Context**: UE Inactive AS Context is stored when the
connection is suspended and restored when the connection is resumed. It
includes information as defined in clause 5.3.8.3.

**V2X sidelink communication**: AS functionality enabling V2X
Communication as defined in TS 23.285 \[56\], between nearby UEs, using
E-UTRA technology but not traversing any network node.