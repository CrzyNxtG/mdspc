## 3.1 Definitions

For the purposes of the present document, the following terms and
definitions apply:

**2Rx XR UE**: two antenna port XR UE as specified in TS 38.101-1
\[15\].

**Acceptable Cell**: A cell that satisfies certain conditions as
specified in 4.5.

**Allowed CAG list**: A per-PLMN list of CAG Identifiers the UE is
allowed to access (see TS 23.501 \[10\])**.**

**Available PLMN(s)**: One or more PLMN(s) for which the UE has found at
least one cell and read its PLMN identity(ies).

**Available SNPN(s)**: One or more SNPN(s) for which the UE has found at
least one cell and read its SNPN identity(ies).

**Barred Cell**: A cell a UE is not allowed to camp on.

**CAG cell**: A cell broadcasting at least one Closed Access Group
Identifier.

**Camped on a cell**: UE has completed the cell selection/reselection
process and has chosen a cell. The UE monitors system information and
(in most cases) paging information.

**Camped on any cell**: UE is in idle mode and has completed the cell
selection/reselection process and has chosen a cell irrespective of PLMN
identity.

**Closed Access Group Identifier**: Identifier of a CAG within a PLMN.

**Commercial Mobile Alert System**: Public Warning System that delivers
*Warning Notifications* provided by *Warning Notification Providers* to
CMAS capable UEs.

**Earth-fixed cell:** An NTN cell fixed with respect to a certain
geographic area on the earth all the time. It can be provisioned by
beam(s) continuously covering the same geographical areas all the time
(e.g., the case of GSO satellites).

**Earth-moving cell**: An NTN cell moving on the ground. It can be
provisioned by beam(s) whose coverage area slides over the Earth surface
(e.g., the case of NGSO satellites generating fixed or non-steerable
beams).

**eCall Only Mode**: A UE configuration option that allows the UE to
register at 5GC and register in IMS to perform only eCall Over IMS, and
a non-emergency IMS call for test and/or terminal reconfiguration
services.

**EHPLMN**: Any of the PLMN entries contained in the Equivalent HPLMN
list TS 23.122 \[9\].

**Equivalent PLMN list**: List of PLMNs considered as equivalent by the
UE for cell selection, cell reselection, and handover according to the
information provided by the NAS.

**Equivalent SNPN list**: List of SNPNs considered as equivalent by the
UE for cell selection, cell reselection, and handover according to the
information provided by the NAS.

**eRedCap UE**: A UE with enhanced reduced capabilities as specified in
clause 4.2.22 in TS 38.306 \[24\].

**Home PLMN**: A PLMN where the Mobile Country Code (MCC) and Mobile
Network Code (MNC) of the PLMN identity are the same as the MCC and MNC
of the IMSI.

**HSDN cell**: A cell that has higher priority than other cells for cell
reselection for HSDN capable UE in a High-mobility state.

**Mobile-IAB cell**: As defined in TS 38.300 \[2\].

**Network Identifier**: Identifier of an SNPN in combination with a PLMN
ID (TS 23.501 \[10\]).

**Non-Public Network**: A network deployed for non-public use, as
defined in TS 22.261 \[12\].

**Non-terrestrial network**: An NG-RAN consisting of gNBs, which
provides non-terrestrial NR access to UEs by means of an NTN payload
embarked on an airborne or space-borne NTN vehicle and an NTN Gateway.

**NR sidelink communication**: AS functionality enabling at least V2X
Communication as defined in TS 23.287 \[16\] and/or A2X Communication as
defined in TS 23.256 \[26\], and ProSe communication (including ProSe
non-Relay, UE-to-Network Relay communication and, UE-to-UE Relay
communication including UE-to-UE Relay communication with integrated
discovery) as defined in TS 23.304 \[22\], between two or more nearby
UEs, using NR technology but not traversing any network node.

**NR sidelink discovery**: AS functionality enabling ProSe non-Relay
Discovery, ProSe UE-to-Network Relay discovery and ProSe UE-to-UE Relay
discovery for Proximity based Services as defined in TS 23.304 \[22\]
between two or more nearby UEs, using NR technology but not traversing
any network node.

**Process**: A local action in the UE invoked by an RRC procedure or an
RRC_IDLE or RRC_INACTIVE state procedure.

**Quasi-Earth fixed cell**: An NTN cell fixed with respect to a certain
geographic area on the earth during a certain time duration. It can be
provisioned by beam(s) covering one geographic area for a limited period
and a different geographic area during another period (e.g., the case of
NGSO satellites generating steerable beams).

**Radio Access Technology**: Type of technology used for radio access,
for instance NR or E-UTRA.

**Ranging/Sidelink Positioning**: AS functionality enabling
ranging-based services and sidelink positioning as defined in TS 23.586
\[25\].

**RedCap UE:** A UE with reduced capabilities as specified in clause
4.2.21 in TS 38.306 \[24\].

**Registration Area**: (NAS) registration area is an area in which the
UE may roam without a need to perform location registration, which is a
NAS procedure.

**Registered PLMN**: This is the PLMN on which certain Location
Registration outcomes have occurred, as specified in TS 23.122 \[9\].

**Registered SNPN**: This is the SNPN on which certain Location
Registration outcomes have occurred, as specified in TS 23.122 \[9\].

**Reserved Cell**: A cell on which camping is not allowed, except for
particular UEs, if so indicated in the system information.

**Selected PLMN**: This is the PLMN that has been selected by the NAS,
either manually or automatically.

**Selected SNPN**: This is the SNPN that has been selected by the NAS,
either manually or automatically.

**Serving cell**: The cell on which the UE is camped.

**Sidelink**: UE to UE interface for V2X sidelink communication defined
in TS 23.287\[16\].

**SNPN Access Mode**: Mode of operation wherein UE only selects SNPNs
(as defined in TS 23.501 \[10\]).

**SNPN identity**: An identifier of an SNPN comprising of a PLMN ID and
an NID combination.

**Strongest cell**: The cell on a particular frequency that is
considered strongest according to the layer 1 cell search procedure (TS
38.213 \[4\], TS 38.215 \[11\]).

**Suitable Cell**: This is a cell on which a UE may camp. For NR cell,
the criteria are defined in clause 4.5, for E-UTRA cell in TS 36.304
\[7\].

**U2N Relay UE**: a UE that provides functionality to support
connectivity to the network for U2N Remote UE(s).

**U2N Remote UE**: a UE that communicates with the network via a U2N
Relay UE.

**U2U Relay UE**: a UE that provides functionality to support
connectivity for U2U Remote UE(s).

**U2U Remote UE**: a UE that communicates with other UE(s) via a U2U
Relay UE.

**V2X sidelink communication**: AS functionality enabling V2X
Communication as defined in TS 23.285 \[17\], between nearby UEs, using
E-UTRA technology but not traversing any network node.