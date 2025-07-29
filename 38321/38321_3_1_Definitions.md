## 3.1 Definitions

For the purposes of the present document, the terms and definitions
given in TR 21.905 \[1\] and the following apply. A term defined in the
present document takes precedence over the definition of the same term,
if any, in TR 21.905 \[1\].

**A2X communication**: A communication to support A2X services
leveraging PC5 reference points, as defined in TS 23.256 \[31\]. A2X
services are realized by various types of A2X applications, e.g., BRID
or DAA.

**Air to Ground network:** An NG-RAN consisting of ground-based gNBs,
which provide cell towers that send signals up to an aircraft\'s
antenna(s) of onboard ATG terminal, with typical vertical altitude of
around 10,000 m and take-off/landing altitudes down to 3000 m.

**BWP for SRS for positioning Tx frequency hopping**: For SRS for
positioning Tx frequency hopping, separate BWP configuration outside BWP
configuration for data transmission.

**Dedicated SL-PRS resource pool**: A sidelink resource pool which can
be used for the transmission of SL-PRS and cannot be used for the
transmission of PSSCH.

**Dormant BWP**: The dormant BWP is one of downlink BWPs configured by
the network via dedicated RRC signaling. In the dormant BWP, the UE stop
monitoring PDCCH on/for the SCell, but continues performing CSI
measurements, Automatic Gain Control (AGC) and beam management, if
configured.

**DRX group**: A group of Serving Cells that is configured by RRC and
that have the same DRX Active Time.

**eRedCap UE**: A UE with enhanced reduced capabilities as specified in
clause 4.2.22.1 of TS 38.306 \[25\].

**HARQ information**: HARQ information for DL-SCH, for UL-SCH, or for
SL-SCH transmissions consists of New Data Indicator (NDI), Transport
Block Size (TBS), Redundancy Version (RV), and HARQ process ID.

**IAB-donor**: gNB that provides network access to UEs via a network of
backhaul and access links.

**IAB-node**: RAN node that supports NR access links to UEs and NR
backhaul links to parent nodes and child nodes.

**Listen Before Talk**: A procedure according to which transmissions are
not performed if the channel is identified as being occupied, see TS
37.213 \[18\].

**LTM candidate cell**: A candidate cell configured for LTM as defined
in TS 38.331 \[5\].

**Msg3**: Message transmitted on UL-SCH containing a C-RNTI MAC CE or
CCCH SDU, submitted from upper layer and associated with the UE
Contention Resolution Identity, as part of a Random Access procedure.

**Multi-path**: Mode of operation of a UE in RRC_CONNECTED configured
with one direct path on which the UE connects to gNB using NR Uu, and
one indirect path on which the UE connects to the same gNB via another
UE using PC5 unicast link or non-3GPP connection (N3C).

**Multi-PUSCH configured grant**: A configured grant configuration
configured with *nrOfSlotsInCG-Period* (see TS 38.331 \[5\]). It
includes multiple consecutive configured uplink grants within a single
periodicity.

**N3C indirect path:** In Multi-path, the indirect path using Non-3GPP
Connection between remote UE and relay UE.

**NCR-Fwd**: NCR-node function, which performs amplifying-and-forwarding
of UL/DL RF signals between gNB and UE. The behavior of the NCR-Fwd is
controlled according to the side control information received by the
NCR-MT from a gNB.

**NCR-MT**: NCR-node entity which communicates with a gNB via a control
link to receive side control information. The control link is based on
NR Uu interface.

**NCR-node**: RAN node comprising NCR-MT and NCR-Fwd.

**Non-terrestrial network**: An NG-RAN consisting of gNBs, which provide
non-terrestrial NR access to UEs by means of an NTN payload embarked on
an airborne or space-borne NTN vehicle and an NTN Gateway.

**NR backhaul link**: NR link used for backhauling between an IAB-node
and an IAB-donor, and between IAB-nodes in case of a multi-hop
backhauling.

**NR sidelink communication**: AS functionality enabling at least V2X
Communication as defined in TS 23.287 \[19\] and ProSe communication
(including ProSe non-Relay, UE-to-Network Relay and UE-to-UE Relay
communication (including ProSe UE-to-UE Relay communication with
integrated discovery)) as defined in TS 23.304 \[26\], between two or
more nearby UEs, using NR technology but not traversing any network
node.

**NR sidelink discovery**: AS functionality enabling ProSe non-Relay
discovery, ProSe UE-to-Network Relay discovery and ProSe UE-to-UE Relay
discovery for Proximity based Services as defined in TS 23.304 \[26\],
between two or more nearby UEs, using NR technology but not traversing
any network node.

**NR sidelink transmission**: Any NR Sidelink-based transmission,
including transmission for NR sidelink discovery, transmission for NR
sidelink communication, transmission for Ranging/Sidelink Positioning,
and transmission for A2X communication.

**PDCCH occasion**: A time duration (i.e. one or a consecutive number of
symbols) during which the MAC entity is configured to monitor the PDCCH.

**Positioning SRS Bandwidth Aggregation**: Transmission of positioning
SRS on multiple carriers in RRC_CONNECTED and RRC_INACTIVE where the
positioning SRS resources are linked in RRC configuration as defined in
TS 38.331 \[5\].

**PRS Processing Window**: A time window during which UE may perform PRS
measurement inside the active DL BWP with the same numerology as the
active DL BWP without measurement gap.

**Ranging/Sidelink Positioning**: AS functionality enabling
ranging-based services and sidelink positioning as specified in TS
23.586 \[30\].

**RB set**: A RB set refers to a contiguous set of resource blocks (RBs)
on which a channel access procedure is performed in shared spectrum as
defined in TS 37.213 \[18\].

**RedCap UE**: A UE with reduced capabilities as specified in clause
4.2.21.1 in TS 38.306 \[25\].

**Serving Cell**: A PCell, a PSCell, or an SCell in TS 38.331 \[5\].

**Shared SL-PRS resource pool**: A sidelink resource pool which can be
used for the transmission of both SL-PRS and PSSCH.

**Sidelink transmission information**: Sidelink transmission information
included in an SCI for an SL-SCH transmission or SL-PRS transmission
with or without SL-SCH transmission on Shared SL-PRS resource pool as
specified in clause 8.3 and 8.4 of TS 38.212 \[9\] consists of Sidelink
HARQ information including NDI, RV, Sidelink process ID, HARQ feedback
enabled/disabled indicator, Sidelink identification information
including cast type indicator, Source Layer-1 ID and Destination Layer-1
ID, and Sidelink other information including CSI request, SL-PRS
request, SL-PRS resource ID, a priority, a communication range
requirement and Zone ID and COT sharing information.

**SL-PRS delay budget**: Delay budget before which the SL-PRS is
expected to be transmitted by the Tx UE.

**SL-PRS transmission information on Dedicated SL-PRS resource pool**:
SL-PRS transmission information on Dedicated SL-PRS resource pool is
included in an SCI for an SL-PRS transmission on Dedicated SL-PRS
resource pool, as specified in TS 38.212 \[9\], consisting of

\- SL-PRS identification information, including cast type indicator,
source ID and destination ID;

\- SL-PRS transmission other information, including SL-PRS priority,
SL-PRS request, SL-PRS resource ID and resource reservation period.

**SRS positioning validity area**: An area consisting of a list of cells
within which the corresponding positioning SRS configuration is
considered as valid.

**Special Cell**: For Dual Connectivity operation the term Special Cell
refers to the PCell of the MCG or the PSCell of the SCG depending on if
the MAC entity is associated to the MCG or the SCG, respectively.
Otherwise the term Special Cell refers to the PCell. A Special Cell
supports PUCCH transmission and contention-based Random Access, and is
always activated.

**Timing Advance Group**: A group of Serving Cells that is configured by
RRC and that, for the cells with a UL configured, using the same timing
reference cell and the same Timing Advance value. A Timing Advance Group
containing the SpCell of a MAC entity is referred to as Primary Timing
Advance Group (PTAG), whereas the term Secondary Timing Advance Group
(STAG) refers to other TAGs.

**UE-gNB RTT**: For non-terrestrial networks, the sum of the UE\'s
Timing Advance value (see TS 38.211 \[8\] clause 4.3.1) and *kmac*.

**V2X sidelink communication**: AS functionality enabling V2X
Communication as defined in TS 23.285 \[20\], between nearby UEs, using
E-UTRA technology but not traversing any network node.

NOTE 1: A timer is running once it is started, until it is stopped or
until it expires; otherwise it is not running. A timer can be started if
it is not running or restarted if it is running. A Timer is always
started or restarted from its initial value. The duration of a timer is
not updated until it is stopped or expires (e.g. due to BWP switching).
When the MAC entity applies zero value for a timer, the timer shall be
started and immediately expire unless explicitly stated otherwise.

NOTE 2: In this version of the specification, the SRS in the procedural
description includes Positioning SRS except for the Positioning SRS for
transmission in RRC_INACTIVE as in clause 5.26. Positioning SRS except
for the Positioning SRS for transmission in RRC_INACTIVE is treated the
same as SRS by the UE unless explicitly stated otherwise.