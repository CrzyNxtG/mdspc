## 3.1 Definitions

For the purposes of the present document, the terms and definitions
given in TR 21.905 \[1\] and the following apply. A term defined in the
present document takes precedence over the definition of the same term,
if any, in TR 21.905 \[1\].

**AM DRB**: a data radio bearer which utilizes RLC AM.

**AM MRB:** an MRB associated with at least one AM RLC bearer for PTP
transmission.

**Broadcast MRB**: a radio bearer configured for MBS broadcast delivery.

**DAPS bearer**: a bearer whose radio protocols are located in both the
source gNB and the target gNB during DAPS handover to use both source
gNB and target gNB resources.

**Delay-critical PDCP SDU**: if *pdu-SetDiscard* is not configured, a
PDCP SDU for which the remaining time till *discardTimer* expiry is less
than the *remainingTimeThreshold*. If *pdu-SetDiscard* is configured, a
PDCP SDU belonging to a PDU Set of which at least one PDCP SDU has the
remaining time till *discardTimer* expiry less than the
*remainingTimeThreshold*.

**MBS Radio Bearer:** a radio bearer that is configured for MBS
delivery.

**Multicast MRB:** a radio bearer configured for MBS multicast delivery.

**Multi-path:** Mode of operation of a remote UE in RRC_CONNECTED
configured with one direct path on which the UE connects to the gNB
using NR Uu and one indirect path on which the UE connects to the same
gNB via another UE using PC5 unicast link or Non-3GPP Connection.

**Multi-path Primary Path**: In multi-path for a split DRB, the primary
path is configured by RRC to be either the direct path or the indirect
path. In multi-path for a split SRB, the primary path is always the
direct path.

**Multi-path Secondary Path**: In multi-path for a split DRB, the path
(either direct or indirect) which is not configured by RRC as the
primary path. In multi-path for a split SRB, the secondary path is
always the indirect path (SL or N3C).

**Multi-path split bearer:** In multi-path, a bearer in which one PDCP
entity is mapped to one or more (direct) Uu RLC entities and either one
SRAP entity of a SL indirect path or a non-3GPP connection.

**N3C indirect path:** In multi-path, the indirect path using Non-3GPP
Connection between remote UE and relay UE.

**Non-split bearer**: a bearer whose radio protocols are located in
either the MgNB or the SgNB to use MgNB or SgNB resource, respectively.

**NR sidelink communication**: AS functionality enabling at least V2X
communication as defined in TS 23.287 \[13\] and ProSe communication
(including ProSe non-Relay, UE-to-Network Relay, and UE-to-UE Relay
communication) as defined in TS 23.304 \[18\], between two or more
nearby UEs, using NR technology but not traversing any network node.

**NR sidelink discovery**: AS functionality enabling ProSe non-Relay
Discovery, ProSe UE-to-Network Relay discovery, and ProSe UE-to-UE Relay
discovery for Proximity based Services as defined in TS 23.304 \[18\]
between two or more nearby UEs, using NR technology but not traversing
any network node.

**NR sidelink transmission**: any NR Sidelink-based transmission,
including both transmission for NR sidelink discovery and transmission
for NR sidelink communication.

**PDCP data volume**: the amount of data available for transmission in a
PDCP entity.

**PDU Set**: one or more PDUs carrying the payload of one unit of
information generated at the application level (e.g. frame(s) or video
slice(s) etc. for XR services), as defined in TS 23.501 \[23\]. A PDU in
the PDU Set corresponds to a PDCP SDU.

**SL indirect path**: In multi-path, the indirect path on which the L2
U2N Remote UE connects to the network via a L2 U2N Relay UE.

**Split bearer**: in dual connectivity, a bearer whose radio protocols
are located in both the MgNB and the SgNB to use both MgNB and SgNB
resources.

**Split secondary RLC entity**: in dual connectivity, the RLC entity
other than the primary RLC entity which is responsible for split bearer
operation. If the PDCP entity is associated with two RLC entities, the
split secondary RLC entity is the RLC entity other than the primary RLC
entity. If the PDCP entity is associated with more than two RLC
entities, the split secondary RLC entity is configured by upper layers.
In multi-path, the split secondary RLC entity is the RLC entity on the
direct path which is responsible for split bearer operation when the MP
primary path is the indirect path. When the PDCP entity on the direct
path is associated with one RLC entity, the split secondary RLC entity
is that RLC entity. When the PDCP entity is associated with more than
one RLC entity, the split secondary RLC entity is configured by upper
layers.

**UM DRB**: a data radio bearer which utilizes RLC UM.

**UM MRB:** an MRB associated with only RLC UM.

**U2N Relay UE**: A UE that provides functionality to support
connectivity to the network for U2N Remote UE(s).

**U2N Remote UE**: A UE that communicates with the network via a U2N
Relay UE.

**U2U Relay UE**: A UE that provides functionality to support
connectivity between two U2U Remote UEs

**U2U Remote UE**: A UE that communicates with another UE via a U2U
Relay UE