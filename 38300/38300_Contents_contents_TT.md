#  Contents {#contents .TT}

Foreword [13](#foreword)

1 Scope [14](#scope)

2 References [14](#references)

3 Abbreviations and Definitions [16](#abbreviations-and-definitions)

3.1 Abbreviations [16](#abbreviations)

3.2 Definitions [20](#definitions)

4 Overall Architecture and Functional Split
[24](#overall-architecture-and-functional-split)

4.1 Overall Architecture [24](#overall-architecture)

4.2 Functional Split [25](#functional-split)

4.3 Network Interfaces [27](#network-interfaces)

4.3.1 NG Interface [27](#ng-interface)

4.3.1.1 NG User Plane [27](#ng-user-plane)

4.3.1.2 NG Control Plane [28](#ng-control-plane)

4.3.2 Xn Interface [28](#xn-interface)

4.3.2.1 Xn User Plane [28](#xn-user-plane)

4.3.2.2 Xn Control Plane [29](#xn-control-plane)

4.4 Radio Protocol Architecture [30](#radio-protocol-architecture)

4.4.1 User Plane [30](#user-plane)

4.4.2 Control Plane [30](#control-plane)

4.5 Multi-Radio Dual Connectivity [30](#multi-radio-dual-connectivity)

4.6 Radio Access Network Sharing [31](#radio-access-network-sharing)

4.7 Integrated Access and Backhaul [31](#integrated-access-and-backhaul)

4.7.1 Architecture [31](#architecture)

4.7.2 Protocol Stacks [32](#protocol-stacks)

4.7.3 User-plane Aspects [33](#user-plane-aspects)

4.7.3.1 Backhaul transport [33](#backhaul-transport)

4.7.3.2 Flow and Congestion Control [34](#flow-and-congestion-control)

4.7.3.3 Uplink Scheduling Latency [34](#uplink-scheduling-latency)

4.7.4 Signalling procedures [34](#signalling-procedures)

4.7.4.1 IAB-node Integration [34](#iab-node-integration)

4.7.4.2 IAB-node Migration [35](#iab-node-migration)

4.7.4.3 Topological Redundancy [35](#topological-redundancy)

4.7.4.4 Backhaul RLF Recovery [35](#backhaul-rlf-recovery)

4.7.4.5 OTA timing synchronization [35](#ota-timing-synchronization)

4.7.4.6 Inter node discovery [36](#inter-node-discovery)

4.7.5 Mobile IAB [36](#mobile-iab)

4.7.5.1 General [36](#general)

4.7.5.2 Void [36](#void)

4.8 Non-Public Networks [36](#non-public-networks)

4.9 Network-Controlled Repeaters [37](#network-controlled-repeaters)

4.9.1 Architecture [37](#architecture-1)

4.9.2 Capabilities [37](#capabilities)

4.9.3 Signalling procedures [37](#signalling-procedures-1)

4.9.4 OAM aspects [38](#oam-aspects)

4.9.5 Network-controlled repeater management
[38](#network-controlled-repeater-management)

5 Physical Layer [39](#physical-layer)

5.1 Waveform, numerology and frame structure
[39](#waveform-numerology-and-frame-structure)

5.2 Downlink [40](#downlink)

5.2.1 Downlink transmission scheme [40](#downlink-transmission-scheme)

5.2.2 Physical-layer processing for physical downlink shared channel
[40](#physical-layer-processing-for-physical-downlink-shared-channel)

5.2.3 Physical downlink control channels
[41](#physical-downlink-control-channels)

5.2.4 Synchronization signal and PBCH block
[42](#synchronization-signal-and-pbch-block)

5.2.5 Physical layer procedures [43](#physical-layer-procedures)

5.2.5.1 Link adaptation [43](#link-adaptation)

5.2.5.2 Power Control [43](#power-control)

5.2.5.3 Cell search [43](#cell-search)

5.2.5.4 HARQ [44](#harq)

5.2.5.5 Reception of SIB1 [44](#reception-of-sib1)

5.2.6 Downlink Reference Signals and Measurements for Positioning
[44](#downlink-reference-signals-and-measurements-for-positioning)

5.3 Uplink [44](#uplink)

5.3.1 Uplink transmission scheme [44](#uplink-transmission-scheme)

5.3.2 Physical-layer processing for physical uplink shared channel
[45](#physical-layer-processing-for-physical-uplink-shared-channel)

5.3.3 Physical uplink control channel
[45](#physical-uplink-control-channel)

5.3.4 Random access [46](#random-access)

5.3.5 Physical layer procedures [47](#physical-layer-procedures-1)

5.3.5.1 Link adaptation [47](#link-adaptation-1)

5.3.5.2 Uplink Power control [47](#uplink-power-control)

5.3.5.3 Uplink timing control [47](#uplink-timing-control)

5.3.5.4 HARQ [48](#harq-1)

5.3.5.5 Prioritization of overlapping transmissions
[48](#prioritization-of-overlapping-transmissions)

5.3.6 Uplink Reference Signals and Measurements for Positioning
[48](#uplink-reference-signals-and-measurements-for-positioning)

5.4 Carrier aggregation [48](#carrier-aggregation)

5.4.1 Carrier aggregation [48](#carrier-aggregation-1)

5.4.2 Supplementary Uplink [48](#supplementary-uplink)

5.4.3 Uplink Tx switching [49](#uplink-tx-switching)

5.5 Transport Channels [49](#transport-channels)

5.6 Access to Shared Spectrum [50](#access-to-shared-spectrum)

5.6.1 Overview [50](#overview)

5.6.2 Channel Access Priority Classes
[50](#channel-access-priority-classes)

5.7 Sidelink [51](#sidelink)

5.7.1 General [51](#general-1)

5.7.2 Sidelink resource allocation modes/schemes
[51](#sidelink-resource-allocation-modesschemes)

5.7.3 Physical sidelink channels and signals
[51](#physical-sidelink-channels-and-signals)

5.7.4 Physical layer procedures for sidelink
[51](#physical-layer-procedures-for-sidelink)

5.7.4.1 HARQ feedback [51](#harq-feedback)

5.7.4.2 Power Control [52](#power-control-1)

5.7.4.3 CSI report [52](#csi-report)

5.7.5 Physical layer measurement definition
[52](#physical-layer-measurement-definition)

5.7.6 Sidelink Reference Signal and Measurements for Positioning
[52](#sidelink-reference-signal-and-measurements-for-positioning)

6 Layer 2 [52](#layer-2)

6.1 Overview [52](#overview-1)

6.2 MAC Sublayer [56](#mac-sublayer)

6.2.1 Services and Functions [56](#services-and-functions)

6.2.2 Logical Channels [57](#logical-channels)

6.2.3 Mapping to Transport Channels [57](#mapping-to-transport-channels)

6.2.4 HARQ [57](#harq-2)

6.3 RLC Sublayer [57](#rlc-sublayer)

6.3.1 Transmission Modes [57](#transmission-modes)

6.3.2 Services and Functions [58](#services-and-functions-1)

6.3.3 ARQ [58](#arq)

6.4 PDCP Sublayer [58](#pdcp-sublayer)

6.4.1 Services and Functions [58](#services-and-functions-2)

6.5 SDAP Sublayer [59](#sdap-sublayer)

6.6 L2 Data Flow [59](#l2-data-flow)

6.7 Carrier Aggregation [59](#carrier-aggregation-2)

6.8 Dual Connectivity [61](#dual-connectivity)

6.9 Supplementary Uplink [61](#supplementary-uplink-1)

6.10 Bandwidth Adaptation [61](#bandwidth-adaptation)

6.11 Backhaul Adaptation Protocol Sublayer
[62](#backhaul-adaptation-protocol-sublayer)

6.11.1 Services and Functions [62](#services-and-functions-3)

6.11.2 Traffic Mapping from Upper Layers to Layer-2
[62](#traffic-mapping-from-upper-layers-to-layer-2)

6.11.3 Routing, BAP Header Rewriting and BH-RLC-channel Mapping on BAP
sublayer
[63](#routing-bap-header-rewriting-and-bh-rlc-channel-mapping-on-bap-sublayer)

6.12 Multiple Transmit/Receive Point Operation
[65](#multiple-transmitreceive-point-operation)

7 RRC [65](#rrc)

7.1 Services and Functions [65](#services-and-functions-4)

7.2 Protocol States [66](#protocol-states)

7.3 System Information Handling [67](#system-information-handling)

7.3.1 Overview [67](#overview-2)

7.3.2 Scheduling [69](#scheduling)

7.3.3 SI Modification [69](#si-modification)

7.4 Access Control [70](#access-control)

7.5 UE Capability Retrieval framework
[70](#ue-capability-retrieval-framework)

7.6 Transport of NAS Messages [70](#transport-of-nas-messages)

7.7 Carrier Aggregation [71](#carrier-aggregation-3)

7.8 Bandwidth Adaptation [71](#bandwidth-adaptation-1)

7.9 UE Assistance Information [71](#ue-assistance-information)

7.10 Segmentation of RRC messages [72](#segmentation-of-rrc-messages)

8 NG Identities [72](#ng-identities)

8.1 UE Identities [72](#ue-identities)

8.2 Network Identities [73](#network-identities)

8.3 User Data Transport on the CN-RAN Interface
[74](#user-data-transport-on-the-cn-ran-interface)

8.4 NR sidelink communication, V2X sidelink communication and
Ranging/Sidelink positioning related identities
[74](#nr-sidelink-communication-v2x-sidelink-communication-and-rangingsidelink-positioning-related-identities)

9 Mobility and State Transitions [75](#mobility-and-state-transitions)

9.1 Overview [75](#overview-3)

9.2 Intra-NR [76](#intra-nr)

9.2.1 Mobility in RRC_IDLE [76](#mobility-in-rrc_idle)

9.2.1.1 Cell Selection [76](#cell-selection)

9.2.1.2 Cell Reselection [77](#cell-reselection)

9.2.1.3 State Transitions [77](#state-transitions)

9.2.2 Mobility in RRC_INACTIVE [79](#mobility-in-rrc_inactive)

9.2.2.1 Overview [79](#overview-4)

9.2.2.2 Cell Reselection [80](#cell-reselection-1)

9.2.2.3 RAN-Based Notification Area [80](#ran-based-notification-area)

9.2.2.4 State Transitions [81](#state-transitions-1)

9.2.2.4.1 UE triggered transition from RRC_INACTIVE to RRC_CONNECTED
[81](#ue-triggered-transition-from-rrc_inactive-to-rrc_connected)

9.2.2.4.2 Network triggered transition from RRC_INACTIVE to
RRC_CONNECTED
[83](#network-triggered-transition-from-rrc_inactive-to-rrc_connected)

9.2.2.5 RNA update [83](#rna-update)

9.2.2.6 Resume request responded with Release with Redirect, with UE
context relocation
[86](#resume-request-responded-with-release-with-redirect-with-ue-context-relocation)

9.2.3 Mobility in RRC_CONNECTED [87](#mobility-in-rrc_connected)

9.2.3.1 Overview [87](#overview-5)

9.2.3.2 Handover [89](#handover)

9.2.3.2.1 C-Plane Handling [89](#c-plane-handling)

9.2.3.2.2 U-Plane Handling [92](#u-plane-handling)

9.2.3.2.3 Data Forwarding [94](#data-forwarding)

9.2.3.3 Re-establishment procedure [96](#re-establishment-procedure)

9.2.3.4 Conditional Handover [97](#conditional-handover)

9.2.3.4.1 General [97](#general-2)

9.2.3.4.2 C-plane handling [97](#c-plane-handling-1)

9.2.3.4.3 U-plane handling [99](#u-plane-handling-1)

9.2.3.4.4 Data Forwarding [99](#data-forwarding-1)

9.2.3.5 L1/L2 Triggered Mobility [99](#l1l2-triggered-mobility)

9.2.3.5.1 General [99](#general-3)

9.2.3.5.2 C-Plane Handling [100](#c-plane-handling-2)

9.2.3.5.3 U-Plane Handling [102](#u-plane-handling-2)

9.2.3.6 RACH-less handover [102](#rach-less-handover)

9.2.4 Measurements [102](#measurements)

9.2.5 Paging [105](#paging)

9.2.6 Random Access Procedure [108](#random-access-procedure)

9.2.7 Radio Link Failure [111](#radio-link-failure)

9.2.8 Beam failure detection and recovery
[112](#beam-failure-detection-and-recovery)

9.2.9 Timing Advance [113](#timing-advance)

9.2.10 Extended DRX for RRC_IDLE and RRC_INACTIVE
[113](#extended-drx-for-rrc_idle-and-rrc_inactive)

9.3 Inter RAT [114](#inter-rat)

9.3.1 NR-E-UTRA mobility: Intra 5GC [114](#nr-e-utra-mobility-intra-5gc)

9.3.1.1 Cell Reselection [114](#cell-reselection-2)

9.3.1.2 Handover [114](#handover-1)

9.3.1.3 Measurements [115](#measurements-1)

9.3.2 NR-E-UTRA mobility: From 5GC to EPC
[115](#nr-e-utra-mobility-from-5gc-to-epc)

9.3.2.1 Cell Reselection [115](#cell-reselection-3)

9.3.2.2 Handover and redirection [115](#handover-and-redirection)

9.3.2.3 Measurements [115](#measurements-2)

9.3.2.4 Data Forwarding for the Control Plane
[116](#data-forwarding-for-the-control-plane)

9.3.2.5 Data Forwarding for the User Plane
[116](#data-forwarding-for-the-user-plane)

9.3.3 NR-E-UTRA mobility: From EPC to 5GC
[117](#nr-e-utra-mobility-from-epc-to-5gc)

9.3.3.1 Data Forwarding for the Control Plane
[117](#data-forwarding-for-the-control-plane-1)

9.3.3.2 Data Forwarding for the User Plane
[117](#data-forwarding-for-the-user-plane-1)

9.3.4 NR-UTRA mobility [118](#nr-utra-mobility)

9.3.4.1 Handover with SRVCC operation
[118](#handover-with-srvcc-operation)

9.3.4.2 Measurements [118](#measurements-3)

9.4 Roaming and Access Restrictions
[119](#roaming-and-access-restrictions)

10 Scheduling [119](#scheduling-1)

10.1 Basic Scheduler Operation [119](#basic-scheduler-operation)

10.2 Downlink Scheduling [120](#downlink-scheduling)

10.3 Uplink Scheduling [120](#uplink-scheduling)

10.4 Measurements to Support Scheduler Operation
[121](#measurements-to-support-scheduler-operation)

10.5 Rate Control [122](#rate-control)

10.5.1 Downlink [122](#downlink-1)

10.5.2 Uplink [122](#uplink-1)

10.6 Activation/Deactivation Mechanism
[122](#activationdeactivation-mechanism)

10.7 E-UTRA-NR Cell Resource Coordination
[123](#e-utra-nr-cell-resource-coordination)

10.8 Cross Carrier Scheduling [123](#cross-carrier-scheduling)

10.9 IAB Resource Configuration [124](#iab-resource-configuration)

10.10 Autonomous Denial for IDC [124](#autonomous-denial-for-idc)

10.11 Multi-cell scheduling by a single DCI
[124](#multi-cell-scheduling-by-a-single-dci)

11 UE Power Saving [125](#ue-power-saving)

12 QoS [127](#qos)

12.1 Overview [127](#overview-6)

12.2 Explicit Congestion Notification
[129](#explicit-congestion-notification)

13 Security [129](#security)

13.1 Overview and Principles [129](#overview-and-principles)

13.2 Security Termination Points [131](#security-termination-points)

13.3 State Transitions and Mobility
[132](#state-transitions-and-mobility)

14 UE Capabilities [132](#ue-capabilities)

15 Self-Configuration and Self-Optimisation
[134](#self-configuration-and-self-optimisation)

15.1 Definitions [134](#definitions-1)

15.2 Void [134](#void-1)

15.3 Self-configuration [134](#self-configuration)

15.3.1 Dynamic configuration of the NG-C interface
[134](#dynamic-configuration-of-the-ng-c-interface)

15.3.1.1 Prerequisites [134](#prerequisites)

15.3.1.2 SCTP initialization [134](#sctp-initialization)

15.3.1.3 Application layer initialization
[134](#application-layer-initialization)

15.3.2 Dynamic Configuration of the Xn interface
[134](#dynamic-configuration-of-the-xn-interface)

15.3.2.1 Prerequisites [134](#prerequisites-1)

15.3.2.2 SCTP initialization [134](#sctp-initialization-1)

15.3.2.3 Application layer initialization
[135](#application-layer-initialization-1)

15.3.3 Automatic Neighbour Cell Relation Function
[135](#automatic-neighbour-cell-relation-function)

15.3.3.1 General [135](#general-4)

15.3.3.2 Intra-system Automatic Neighbour Cell Relation Function
[136](#intra-system-automatic-neighbour-cell-relation-function)

15.3.3.3 Void [137](#void-2)

15.3.3.4 Void [137](#void-3)

15.3.3.5 Inter-system Automatic Neighbour Cell Relation Function
[137](#inter-system-automatic-neighbour-cell-relation-function)

15.3.4 Xn-C TNL address discovery [137](#xn-c-tnl-address-discovery)

15.4 Support for Energy Saving [138](#support-for-energy-saving)

15.4.1 General [138](#general-5)

15.4.2 Solution description [138](#solution-description)

15.4.2.1 Intra-system energy saving [138](#intra-system-energy-saving)

15.4.2.2 Inter-system energy saving [139](#inter-system-energy-saving)

15.4.2.3 Cell DTX/DRX [139](#cell-dtxdrx)

15.4.2.4 Conditional Handover [139](#conditional-handover-1)

15.4.2.5 Camping Restrictions [139](#camping-restrictions)

15.4.2.6 SSB-less SCell [140](#ssb-less-scell)

15.4.2.7 Spatial and power domain adaptation
[140](#spatial-and-power-domain-adaptation)

15.4.3 O&M requirements [140](#om-requirements)

15.5 Self-optimisation [140](#self-optimisation)

15.5.1 Support for Mobility Load Balancing
[140](#support-for-mobility-load-balancing)

15.5.1.1 General [140](#general-6)

15.5.1.2 Load reporting for intra-RAT and intra-system inter-RAT load
balancing
[140](#load-reporting-for-intra-rat-and-intra-system-inter-rat-load-balancing)

15.5.1.4 Adapting handover and/or reselection configuration
[141](#adapting-handover-andor-reselection-configuration)

15.5.1.5 Load reporting for inter-system load balancing
[141](#load-reporting-for-inter-system-load-balancing)

15.5.2 Support for Mobility Robustness Optimization
[142](#support-for-mobility-robustness-optimization)

15.5.2.1 General [142](#general-7)

15.5.2.2 Connection failure [142](#connection-failure)

15.5.2.2.1 General [142](#general-8)

15.5.2.2.2 Connection failure due to intra-system mobility
[142](#connection-failure-due-to-intra-system-mobility)

15.5.2.2.3 Connection failure due to inter-system mobility
[144](#connection-failure-due-to-inter-system-mobility)

15.5.2.3 Inter-system Unnecessary HO [145](#inter-system-unnecessary-ho)

15.5.2.4 Inter-system Ping-pong [145](#inter-system-ping-pong)

15.5.2.5 O&M Requirements [146](#om-requirements-1)

15.5.2.6 PSCell addition/change failure
[146](#pscell-additionchange-failure)

15.5.2.7 Successful HO [146](#successful-ho)

15.5.2.8 Successful PSCell Addition/Change Report
[147](#successful-pscell-additionchange-report)

15.5.3 Support for RACH Optimization
[147](#support-for-rach-optimization)

15.5.4 UE History Information [147](#ue-history-information)

15.5.5 Support for Coverage and Capacity Optimisation
[148](#support-for-coverage-and-capacity-optimisation)

15.5.5.1 General [148](#general-9)

15.5.5.2 OAM requirements [148](#oam-requirements)

15.5.5.3 Dynamic coverage configuration changes
[148](#dynamic-coverage-configuration-changes)

15.5.6 Support for PCI Optimisation [148](#support-for-pci-optimisation)

15.5.6.1 Centralized PCI Assignment [148](#centralized-pci-assignment)

15.5.6.2 Distributed PCI Assignment [148](#distributed-pci-assignment)

16 Verticals Support [148](#verticals-support)

16.1 URLLC [148](#urllc)

16.1.1 Overview [148](#overview-7)

16.1.2 LCP Restrictions [149](#lcp-restrictions)

16.1.3 Packet Duplication [149](#packet-duplication)

16.1.4 CQI and MCS [150](#cqi-and-mcs)

16.1.5 DCI formats [150](#dci-formats)

16.1.6 Higher layer multi-connectivity
[150](#higher-layer-multi-connectivity)

16.1.6.1 Redundant user plane paths based on dual connectivity
[150](#redundant-user-plane-paths-based-on-dual-connectivity)

16.1.6.2 Redundant data transmission via single UPF and single RAN node
[150](#redundant-data-transmission-via-single-upf-and-single-ran-node)

16.1.7 URLLC in Unlicensed Controlled Environment
[150](#urllc-in-unlicensed-controlled-environment)

16.1.8 PUCCH cell switching for TDD cells
[151](#pucch-cell-switching-for-tdd-cells)

16.2 IMS Voice [151](#ims-voice)

16.2.0 Support for IMS voice [151](#support-for-ims-voice)

16.2.1 Support for MMTEL IMS voice and video enhancements
[151](#support-for-mmtel-ims-voice-and-video-enhancements)

16.2.1.1 RAN-assisted codec adaptation
[151](#ran-assisted-codec-adaptation)

16.2.1.2 MMTEL voice quality/coverage enhancements
[152](#mmtel-voice-qualitycoverage-enhancements)

16.3 Network Slicing [152](#network-slicing)

16.3.1 General Principles and Requirements
[152](#general-principles-and-requirements)

16.3.2 AMF and NW Slice Selection [154](#amf-and-nw-slice-selection)

16.3.2.1 CN-RAN interaction and internal RAN aspects
[154](#cn-ran-interaction-and-internal-ran-aspects)

16.3.2.2 Radio Interface Aspects [154](#radio-interface-aspects)

16.3.3 Resource Isolation and Management
[155](#resource-isolation-and-management)

16.3.3.1 General [155](#general-10)

16.3.3.2 Handling of Slice Resources [155](#handling-of-slice-resources)

16.3.3a Slice-based cell reselection
[155](#a-slice-based-cell-reselection)

16.3.4 Signalling Aspects [155](#signalling-aspects)

16.3.4.1 General [155](#general-11)

16.3.4.2 AMF and NW Slice Selection [156](#amf-and-nw-slice-selection-1)

16.3.4.3 UE Context Handling [156](#ue-context-handling)

16.3.4.4 PDU Session Setup Handling [157](#pdu-session-setup-handling)

16.3.4.5 Mobility [157](#mobility)

16.4 Public Warning System [158](#public-warning-system)

16.5 Emergency Services [159](#emergency-services)

16.5.1 Overview [159](#overview-8)

16.5.2 IMS Emergency call [159](#ims-emergency-call)

16.5.3 eCall over IMS [159](#ecall-over-ims)

16.5.4 Fallback [159](#fallback)

16.5.5 Barring exemption for emergency calls
[159](#barring-exemption-for-emergency-calls)

16.6 Stand-Alone NPN [159](#stand-alone-npn)

16.6.1 General [159](#general-12)

16.6.2 Mobility [160](#mobility-1)

16.6.2.1 General [160](#general-13)

16.6.2.2 Inactive Mode [160](#inactive-mode)

16.6.2.3 Connected Mode [160](#connected-mode)

16.7 Public Network Integrated NPN [161](#public-network-integrated-npn)

16.7.1 General [161](#general-14)

16.7.2 Mobility [161](#mobility-2)

16.7.2.1 General [161](#general-15)

16.7.2.2 Inactive Mode [162](#inactive-mode-1)

16.7.2.3 Connected Mode [162](#connected-mode-1)

16.7.3 Self-Configuration for PNI-NPN
[162](#self-configuration-for-pni-npn)

16.7.4 Access Control [162](#access-control-1)

16.7.5 Paging [162](#paging-1)

16.8 Support for Time Sensitive Communications
[162](#support-for-time-sensitive-communications)

16.8.1 General [162](#general-16)

16.8.2 Network timing synchronization status monitoring
[164](#network-timing-synchronization-status-monitoring)

16.8.2.1 General [164](#general-17)

16.8.2.2 Network timing synchronization status monitoring towards CN
[164](#network-timing-synchronization-status-monitoring-towards-cn)

16.8.2.3 Network timing synchronization status monitoring towards UE
[164](#network-timing-synchronization-status-monitoring-towards-ue)

16.8.3 RAN feedback for adaptation of Burst Arrival Time and Periodicity
[165](#ran-feedback-for-adaptation-of-burst-arrival-time-and-periodicity)

16.9 Sidelink [166](#sidelink-1)

16.9.1 General [166](#general-18)

16.9.2 Radio Protocol Architecture for NR sidelink communication
[167](#radio-protocol-architecture-for-nr-sidelink-communication)

16.9.2.1 Overview [167](#overview-9)

16.9.2.2 MAC [168](#mac)

16.9.2.3 RLC [169](#rlc)

16.9.2.4 PDCP [169](#pdcp)

16.9.2.5 SDAP [169](#sdap)

16.9.2.6 RRC [169](#rrc-1)

16.9.3 Radio Resource Allocation [169](#radio-resource-allocation)

16.9.3.1 General [169](#general-19)

16.9.3.2 Scheduled Resource Allocation
[170](#scheduled-resource-allocation)

16.9.3.3 UE Autonomous Resource Selection
[170](#ue-autonomous-resource-selection)

16.9.3.4 LTE and NR Sidelink co-channel coexistence
[170](#lte-and-nr-sidelink-co-channel-coexistence)

16.9.4 Uu Control [170](#uu-control)

16.9.4.1 General [170](#general-20)

16.9.4.2 Control of connected UEs [171](#control-of-connected-ues)

16.9.4.3 Control of idle/inactive UEs
[171](#control-of-idleinactive-ues)

16.9.5 Sidelink Discovery [172](#sidelink-discovery)

16.9.6 SL DRX [172](#sl-drx)

16.9.6.1 General [172](#general-21)

16.9.6.2 Unicast [172](#unicast)

16.9.6.3 Groupcast/Broadcast [173](#groupcastbroadcast)

16.9.6.4 Alignment between Uu DRX and SL DRX
[173](#alignment-between-uu-drx-and-sl-drx)

16.9.7 Power Savings Resource Allocation
[174](#power-savings-resource-allocation)

16.9.8 Inter-UE Coordination (IUC) [174](#inter-ue-coordination-iuc)

16.9.9 Sidelink in Shared Spectrum (SL-U)
[174](#sidelink-in-shared-spectrum-sl-u)

16.9.9.1 Overview [174](#overview-10)

16.9.9.2 Channel Access Priority Classes for Sidelink (SL-CAPC)
[175](#channel-access-priority-classes-for-sidelink-sl-capc)

16.9.9.3 Sidelink Specific Consistent LBT Failure
[175](#sidelink-specific-consistent-lbt-failure)

16.9.9.4 COT Sharing [175](#cot-sharing)

16.9.9.5 Resource Allocation [176](#resource-allocation)

16.9.10 Sidelink CA [176](#sidelink-ca)

16.10 Multicast and Broadcast Services
[177](#multicast-and-broadcast-services)

16.10.1 General [177](#general-22)

16.10.2 Network Architecture [177](#network-architecture)

16.10.3 Protocol Architecture [177](#protocol-architecture)

16.10.4 Group Scheduling [179](#group-scheduling)

16.10.5 Multicast Handling [180](#multicast-handling)

16.10.5.1 Session Management [180](#session-management)

16.10.5.2 Configuration [180](#configuration)

16.10.5.3 Service Continuity [181](#service-continuity)

16.10.5.3.1 General [181](#general-23)

16.10.5.3.2 Handover between Multicast supporting cells
[182](#handover-between-multicast-supporting-cells)

16.10.5.3.3 Handover between Multicast-supporting cell and Multicast
non-supporting cell
[182](#handover-between-multicast-supporting-cell-and-multicast-non-supporting-cell)

16.10.5.3.4 MRB reconfiguration [183](#mrb-reconfiguration)

16.10.5.3.5 Service Continuity in RRC_INACTIVE
[183](#service-continuity-in-rrc_inactive)

16.10.5.4 Reception of MBS Multicast data
[183](#reception-of-mbs-multicast-data)

16.10.5.5 Support of CA [184](#support-of-ca)

16.10.5.6 DRX [184](#drx)

16.10.5.7 Physical Layer [184](#physical-layer-1)

16.10.6 Broadcast Handling [184](#broadcast-handling)

16.10.6.1 Session Management [184](#session-management-1)

16.10.6.2 Configuration [184](#configuration-1)

16.10.6.3 Support of CA [185](#support-of-ca-1)

16.10.6.4 DRX [185](#drx-1)

16.10.6.5 Service Continuity [185](#service-continuity-1)

16.10.6.5.0 General [185](#general-24)

16.10.6.5.1 Service Continuity in RRC_IDLE or RRC_INACTIVE
[185](#service-continuity-in-rrc_idle-or-rrc_inactive)

16.10.6.5.2 Service Continuity in RRC_CONNECTED
[186](#service-continuity-in-rrc_connected)

16.10.6.5A Reception of MBS Broadcast data
[186](#a-reception-of-mbs-broadcast-data)

16.10.6.6 Physical Layer [186](#physical-layer-2)

16.10.6.7 Shared processing for MBS broadcast and unicast reception
[186](#shared-processing-for-mbs-broadcast-and-unicast-reception)

16.11 Minimization of Service Interruption
[187](#minimization-of-service-interruption)

16.12 Sidelink Relay [187](#sidelink-relay)

16.12.1 General [187](#general-25)

16.12.2 Protocol Architecture [188](#protocol-architecture-1)

16.12.2.1 L2 UE-to-Network Relay [188](#l2-ue-to-network-relay)

16.12.2.2 L2 UE-to-UE Relay [190](#l2-ue-to-ue-relay)

16.12.3 Relay Discovery [191](#relay-discovery)

16.12.4 Relay Selection/Reselection [193](#relay-selectionreselection)

16.12.5 Control plane procedures for L2 U2N Relay
[194](#control-plane-procedures-for-l2-u2n-relay)

16.12.5.1 RRC Connection Management [194](#rrc-connection-management)

16.12.5.2 Radio Link Failure [196](#radio-link-failure-1)

16.12.5.3 RRC Connection Re-establishment
[196](#rrc-connection-re-establishment)

16.12.5.4 RRC Connection Resume [196](#rrc-connection-resume)

16.12.5.5 System Information [196](#system-information)

16.12.5.6 Paging [197](#paging-2)

16.12.5.7 Access Control [197](#access-control-2)

16.12.5.8 Mobility Registration Update and RAN Area Update
[197](#mobility-registration-update-and-ran-area-update)

16.12.6 Service Continuity for L2 U2N relay
[197](#service-continuity-for-l2-u2n-relay)

16.12.6.0 General [197](#general-26)

16.12.6.1 Switching from indirect to direct path
[197](#switching-from-indirect-to-direct-path)

16.12.6.2 Switching from direct to indirect path
[200](#switching-from-direct-to-indirect-path)

16.12.6.3 Switching from indirect to indirect path
[202](#switching-from-indirect-to-indirect-path)

16.12.7 Control plane procedures for L2 U2U Relay
[205](#control-plane-procedures-for-l2-u2u-relay)

16.13 Support of Reduced Capability (RedCap) and enhanced Reduced
Capability (eRedCap) NR devices
[207](#support-of-reduced-capability-redcap-and-enhanced-reduced-capability-eredcap-nr-devices)

16.13.1 Introduction [207](#introduction)

16.13.2 Capabilities [207](#capabilities-1)

16.13.3 Identification, access and camping restrictions
[207](#identification-access-and-camping-restrictions)

16.13.4 RRM measurement relaxations [208](#rrm-measurement-relaxations)

16.13.5 BWP operation [208](#bwp-operation)

16.14 Non-Terrestrial Networks [208](#non-terrestrial-networks)

16.14.1 Overview [208](#overview-11)

16.14.2 Timing and Synchronization [210](#timing-and-synchronization)

16.14.2.1 Scheduling and Timing [210](#scheduling-and-timing)

16.14.2.2 Timing Advance and Frequency Pre-compensation
[211](#timing-advance-and-frequency-pre-compensation)

16.14.3 Mobility and State transition
[212](#mobility-and-state-transition)

16.14.3.1 Mobility in RRC_IDLE and RRC_INACTIVE
[212](#mobility-in-rrc_idle-and-rrc_inactive)

16.14.3.2 Mobility in RRC_CONNECTED [212](#mobility-in-rrc_connected-1)

16.14.3.2.1 Handover [212](#handover-2)

16.14.3.2.2 Conditional Handover [212](#conditional-handover-2)

16.14.3.2.3 Satellite switch with re-synchronization
[213](#satellite-switch-with-re-synchronization)

16.14.3.3 Measurements [213](#measurements-4)

16.14.4 Switchover [214](#switchover)

16.14.4.1 Definitions [214](#definitions-2)

16.14.4.2 Assumptions [214](#assumptions)

16.14.4.3 Procedures [214](#procedures)

16.14.5 NG-RAN signalling [214](#ng-ran-signalling)

16.14.6 AMF (Re-)Selection [215](#amf-re-selection)

16.14.7 O&M Requirements [215](#om-requirements-2)

16.14.8 Coarse UE location reporting
[216](#coarse-ue-location-reporting)

16.14.9 Support for NR NTN coverage enhancements
[216](#support-for-nr-ntn-coverage-enhancements)

16.14.10 Verification of UE location [216](#verification-of-ue-location)

16.15 eXtended Reality Services [216](#extended-reality-services)

16.15.1 General [216](#general-27)

16.15.2 Awareness [216](#awareness)

16.15.3 Power Saving [217](#power-saving)

16.15.4 Capacity [218](#capacity)

16.15.4.1 Physical Layer Enhancements
[218](#physical-layer-enhancements)

16.15.4.2 Layer 2 Enhancements [218](#layer-2-enhancements)

16.15.4.2.1 Assistance Information [218](#assistance-information)

16.15.4.2.2 Discard [218](#discard)

16.15.5 Non-Homogeneous support of PDU set based handling in NG-RAN
[219](#non-homogeneous-support-of-pdu-set-based-handling-in-ng-ran)

16.16 ECN marking for L4S and congestion information exposure
[219](#ecn-marking-for-l4s-and-congestion-information-exposure)

16.17 Support for TSN enabled Transport Network
[219](#support-for-tsn-enabled-transport-network)

16.18 Support for Aerial UE Communication
[219](#support-for-aerial-ue-communication)

16.18.1 General [219](#general-28)

16.18.2 Subscription-based Identification of Aerial UE
[220](#subscription-based-identification-of-aerial-ue)

16.18.3 Altitude-based Reporting for Aerial UE Communication
[220](#altitude-based-reporting-for-aerial-ue-communication)

16.18.4 Altitude-dependent Configurations for Aerial UE Communication
[220](#altitude-dependent-configurations-for-aerial-ue-communication)

16.18.5 Interference Detection and Mitigation for Aerial UE
Communication
[220](#interference-detection-and-mitigation-for-aerial-ue-communication)

16.18.6 Flight Path Information Reporting for Aerial UE Communication
[221](#flight-path-information-reporting-for-aerial-ue-communication)

16.18.7 Location Reporting for Aerial UE Communication
[221](#location-reporting-for-aerial-ue-communication)

16.18.8 BRID and DAA Support via A2X Communication
[221](#brid-and-daa-support-via-a2x-communication)

16.19 Support for Air to Ground Networks
[221](#support-for-air-to-ground-networks)

16.19.1 Overview [221](#overview-12)

16.19.2 Timing and Synchronization [221](#timing-and-synchronization-1)

16.19.2.1 Scheduling and Timing [221](#scheduling-and-timing-1)

16.19.2.2 Timing Advance [221](#timing-advance-1)

16.19.3 Mobility [222](#mobility-3)

16.19.3.1 Mobility in RRC_IDLE and RRC_INACTIVE
[222](#mobility-in-rrc_idle-and-rrc_inactive-1)

16.19.3.2 Mobility in RRC_CONNECTED [222](#mobility-in-rrc_connected-2)

16.19.3.2.1 Handover [222](#handover-3)

16.19.3.2.2 Conditional Handover [222](#conditional-handover-3)

16.20 Support of AI/ML for NG-RAN [222](#support-of-aiml-for-ng-ran)

16.20.1 General [222](#general-29)

16.20.2 Principles [222](#principles)

16.20.3 Data Collection and Reporting
[223](#data-collection-and-reporting)

16.20.4 OAM Requirements [223](#oam-requirements-1)

16.21 Multi-path Relay [223](#multi-path-relay)

16.21.1 General [223](#general-30)

16.21.2 Protocol Architecture [224](#protocol-architecture-2)

16.21.2.1 L2 MP Relay using SL indirect path
[224](#l2-mp-relay-using-sl-indirect-path)

16.21.2.2 L2 MP Relay using N3C indirect path
[225](#l2-mp-relay-using-n3c-indirect-path)

16.21.3 Control plane procedure for multi-path relaying
[226](#control-plane-procedure-for-multi-path-relaying)

16.21.3.1 Path Management [226](#path-management)

16.21.3.2 Path Failure Report [232](#path-failure-report)

16.22 Support of 2Rx XR devices [232](#support-of-2rx-xr-devices)

16.22.1 Introduction [232](#introduction-1)

16.22.2 Identification, access and camping restrictions
[232](#identification-access-and-camping-restrictions-1)

17 Interference Management [232](#interference-management)

17.1 Remote Interference Management
[232](#remote-interference-management)

17.2 Cross-Link Interference Management
[233](#cross-link-interference-management)

18 Small Data Transmission [233](#small-data-transmission)

18.0 General [233](#general-31)

18.1 Support of SDT procedure over RACH
[235](#support-of-sdt-procedure-over-rach)

18.2 SDT with UE context relocation
[235](#sdt-with-ue-context-relocation)

18.3 SDT without UE context relocation
[237](#sdt-without-ue-context-relocation)

18.4 MT-SDT with/without UE context relocation
[238](#mt-sdt-withwithout-ue-context-relocation)

19 Support for NR coverage enhancements
[239](#support-for-nr-coverage-enhancements)

20 Support for Multi-USIM devices [240](#support-for-multi-usim-devices)

20.1 General [240](#general-32)

20.2 Paging Collision Avoidance [240](#paging-collision-avoidance)

20.3 UE notification on Network Switching
[241](#ue-notification-on-network-switching)

20.4 Temporary UE capability restriction and removal of restriction
[241](#temporary-ue-capability-restriction-and-removal-of-restriction)

21 Application Layer Measurement Collection
[242](#application-layer-measurement-collection)

21.1 Overview [242](#overview-13)

21.2 QoE Measurement Configuration [242](#qoe-measurement-configuration)

21.2.1 QoE Measurement Collection Activation and Reporting
[242](#qoe-measurement-collection-activation-and-reporting)

21.2.2 QoE Measurement Collection Deactivation
[243](#qoe-measurement-collection-deactivation)

21.2.3 Handling of QMC during RAN Overload
[243](#handling-of-qmc-during-ran-overload)

21.2.4 QoE Measurement Handling in RRC_IDLE and RRC_INACTIVE States
[243](#qoe-measurement-handling-in-rrc_idle-and-rrc_inactive-states)

21.2.5 Per-slice QoE Measurement [244](#per-slice-qoe-measurement)

21.3 QoE Measurement Continuity for Mobility
[244](#qoe-measurement-continuity-for-mobility)

21.4 RAN Visible QoE Measurements [245](#ran-visible-qoe-measurements)

21.5 Alignment of MDT and QoE Measurements
[246](#alignment-of-mdt-and-qoe-measurements)

Annex A (informative): QoS Handling in RAN
[247](#annex-a-informative-qos-handling-in-ran)

A.1 PDU Session Establishment [247](#a.1-pdu-session-establishment)

A.2 New QoS Flow with RQoS [247](#a.2-new-qos-flow-with-rqos)

A.3 New QoS Flow with Explicit RRC Signalling
[248](#a.3-new-qos-flow-with-explicit-rrc-signalling)

A.4 New QoS Flow with Explicit NAS Signalling
[249](#a.4-new-qos-flow-with-explicit-nas-signalling)

A.5 Release of QoS Flow with Explicit Signalling
[250](#a.5-release-of-qos-flow-with-explicit-signalling)

A.6 UE Initiated UL QoS Flow [250](#a.6-ue-initiated-ul-qos-flow)

Annex B (informative): Deployment Scenarios
[252](#annex-b-informative-deployment-scenarios)

B.1 Supplementary Uplink [252](#b.1-supplementary-uplink)

B.2 Multiple SSBs in a carrier [252](#b.2-multiple-ssbs-in-a-carrier)

B.3 NR Operation with Shared Spectrum
[253](#b.3-nr-operation-with-shared-spectrum)

B.4 Example implementation of Non-Terrestrial Networks
[253](#b.4-example-implementation-of-non-terrestrial-networks)

Annex C (informative): I-RNTI Reference Profiles
[256](#annex-c-informative-i-rnti-reference-profiles)

Annex D (informative): SPID ranges and mapping of SPID values to cell
reselection and inter-RAT/inter frequency handover priorities
[257](#annex-d-informative-spid-ranges-and-mapping-of-spid-values-to-cell-reselection-and-inter-ratinter-frequency-handover-priorities)

Annex E (informative): NG-RAN Architecture for Radio Access Network
Sharing with multiple cell ID broadcast
[258](#annex-e-informative-ng-ran-architecture-for-radio-access-network-sharing-with-multiple-cell-id-broadcast)

Annex F (normative): Use and structure of the I-RNTI
[259](#annex-f-normative-use-and-structure-of-the-i-rnti)

Annex G (informative): Components of Mobility Latency
[260](#annex-g-informative-components-of-mobility-latency)

Annex H (informative): Change history
[262](#annex-h-informative-change-history)