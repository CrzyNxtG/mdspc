## 4.2 Functional Split

The **gNB** and **ng-eNB** host the following functions:

\- Functions for Radio Resource Management: Radio Bearer Control, Radio
Admission Control, Connection Mobility Control, Dynamic allocation of
resources to UEs in uplink, downlink and sidelink (scheduling);

\- IP and Ethernet header compression, uplink data decompression,
encryption and integrity protection of data;

\- Selection of an AMF at UE attachment when no routing to an AMF can be
determined from the information provided by the UE;

\- Routing of User Plane data towards UPF(s);

\- Routing of Control Plane information towards AMF;

\- Connection setup and release;

\- Scheduling and transmission of paging messages;

\- Scheduling and transmission of system broadcast information
(originated from the AMF or OAM);

\- Measurement and measurement reporting configuration for mobility and
scheduling;

\- Transport level packet marking in the uplink;

\- Session Management;

\- Support of Network Slicing;

\- QoS Flow management and mapping to data radio bearers;

\- Support of UEs in RRC_INACTIVE state;

\- Distribution function for NAS messages;

\- Radio access network sharing;

\- Dual Connectivity;

\- Tight interworking between NR and E-UTRA;

\- Maintain security and radio configuration for User Plane CIoT 5GS
Optimisation, as defined in TS 23.501 \[3\] (ng-eNB only).

NOTE 1: BL UE or UE in enhanced coverage is only supported by ng-eNB,
see TS 36.300 \[2\].

NOTE 2: NB-IoT UE is only supported by ng-eNB, see TS 36.300 \[2\].

The **AMF** hosts the following main functions (see TS 23.501 \[3\]):

\- NAS signalling termination;

\- NAS signalling security;

\- AS Security control;

\- Inter CN node signalling for mobility between 3GPP access networks;

\- Idle mode UE Reachability (including control and execution of paging
retransmission);

\- Registration Area management;

\- Support of intra-system and inter-system mobility;

\- Access Authentication;

\- Access Authorization including check of roaming rights;

\- Mobility management control (subscription and policies);

\- Support of Network Slicing;

\- SMF selection.

\- Selection of CIoT 5GS optimisations;

The **UPF** hosts the following main functions (see TS 23.501 \[3\]):

\- Anchor point for Intra-/Inter-RAT mobility (when applicable);

\- External PDU session point of interconnect to Data Network;

\- Packet routing & forwarding;

\- Packet inspection and User plane part of Policy rule enforcement;

\- Traffic usage reporting;

\- Uplink classifier to support routing traffic flows to a data network;

\- Branching point to support multi-homed PDU session;

\- QoS handling for user plane, e.g. packet filtering, gating, UL/DL
rate enforcement;

\- Uplink Traffic verification (SDF to QoS flow mapping);

\- Downlink packet buffering and downlink data notification triggering.

The Session Management function (**SMF**) hosts the following main
functions (see TS 23.501 \[3\]):

\- Session Management;

\- UE IP address allocation and management;

\- Selection and control of UP function;

\- Configures traffic steering at UPF to route traffic to proper
destination;

\- Control part of policy enforcement and QoS;

\- Downlink Data Notification.

This is summarized on the figure below where yellow boxes depict the
logical nodes and white boxes depict the main functions.

![](media/image4.emf)

Figure 4.2-1: Functional Split between NG-RAN and 5GC