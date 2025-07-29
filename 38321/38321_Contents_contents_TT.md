#  Contents {#contents .TT}

Foreword [9](#foreword)

1 Scope [10](#scope)

2 References [10](#references)

3 Definitions, symbols and abbreviations
[11](#definitions-symbols-and-abbreviations)

3.1 Definitions [11](#definitions)

3.2 Abbreviations [13](#abbreviations)

4 General [15](#general)

4.1 Introduction [15](#introduction)

4.2 MAC architecture [15](#mac-architecture)

4.2.1 General [15](#general-1)

4.2.2 MAC Entities [15](#mac-entities)

4.3 Services [17](#services)

4.3.1 Services provided to upper layers
[17](#services-provided-to-upper-layers)

4.3.2 Services expected from physical layer
[17](#services-expected-from-physical-layer)

4.4 Functions [17](#functions)

4.5 Channel structure [18](#channel-structure)

4.5.1 General [18](#general-2)

4.5.2 Transport Channels [18](#transport-channels)

4.5.3 Logical Channels [18](#logical-channels)

4.5.4 Mapping of Transport Channels to Logical Channels
[19](#mapping-of-transport-channels-to-logical-channels)

4.5.4.1 General [19](#general-3)

4.5.4.2 Uplink mapping [19](#uplink-mapping)

4.5.4.3 Downlink mapping [19](#downlink-mapping)

4.5.4.4 Sidelink mapping [19](#sidelink-mapping)

5 MAC procedures [20](#mac-procedures)

5.1 Random Access procedure [20](#random-access-procedure)

5.1.1 Random Access procedure initialization
[20](#random-access-procedure-initialization)

5.1.1a Initialization of variables specific to Random Access type
[25](#a-initialization-of-variables-specific-to-random-access-type)

5.1.1b Selection of the set of Random Access resources for the Random
Access procedure
[28](#b-selection-of-the-set-of-random-access-resources-for-the-random-access-procedure)

5.1.1c Availability of the set of Random Access resources
[34](#c-availability-of-the-set-of-random-access-resources)

5.1.1d Selection of the set of Random Access resources based on feature
prioritization
[34](#d-selection-of-the-set-of-random-access-resources-based-on-feature-prioritization)

5.1.1e Selection of Msg1 repetition for SI request
[35](#e-selection-of-msg1-repetition-for-si-request)

5.1.2 Random Access Resource selection
[35](#random-access-resource-selection)

5.1.2a Random Access Resource selection for 2-step RA type
[38](#a-random-access-resource-selection-for-2-step-ra-type)

5.1.3 Random Access Preamble transmission
[40](#random-access-preamble-transmission)

5.1.3a MSGA transmission [41](#a-msga-transmission)

5.1.4 Random Access Response reception
[43](#random-access-response-reception)

5.1.4a MSGB reception and contention resolution for 2-step RA type
[47](#a-msgb-reception-and-contention-resolution-for-2-step-ra-type)

5.1.5 Contention Resolution [50](#contention-resolution)

5.1.6 Completion of the Random Access procedure
[52](#completion-of-the-random-access-procedure)

5.2 Maintenance of Uplink Time Alignment
[53](#maintenance-of-uplink-time-alignment)

5.2a Maintenance of UL Synchronization
[57](#a-maintenance-of-ul-synchronization)

5.3 DL-SCH data transfer [58](#dl-sch-data-transfer)

5.3.1 DL Assignment reception [58](#dl-assignment-reception)

5.3.2 HARQ operation [60](#harq-operation)

5.3.2.1 HARQ Entity [60](#harq-entity)

5.3.2.2 HARQ process [61](#harq-process)

5.3.3 Disassembly and demultiplexing
[62](#disassembly-and-demultiplexing)

5.4 UL-SCH data transfer [63](#ul-sch-data-transfer)

5.4.1 UL Grant reception [63](#ul-grant-reception)

5.4.2 HARQ operation [68](#harq-operation-1)

5.4.2.1 HARQ Entity [68](#harq-entity-1)

5.4.2.2 HARQ process [72](#harq-process-1)

5.4.3 Multiplexing and assembly [74](#multiplexing-and-assembly)

5.4.3.1 Logical Channel Prioritization
[74](#logical-channel-prioritization)

5.4.3.1.1 General [74](#general-4)

5.4.3.1.2 Selection of logical channels
[75](#selection-of-logical-channels)

5.4.3.1.3 Allocation of resources [75](#allocation-of-resources)

5.4.3.2 Multiplexing of MAC Control Elements and MAC SDUs
[77](#multiplexing-of-mac-control-elements-and-mac-sdus)

5.4.4 Scheduling Request [77](#scheduling-request)

5.4.5 Buffer Status Reporting [83](#buffer-status-reporting)

5.4.6 Power Headroom Reporting [86](#power-headroom-reporting)

5.4.7 Pre-emptive Buffer Status Reporting
[93](#pre-emptive-buffer-status-reporting)

5.4.8 Timing Advance Reporting [94](#timing-advance-reporting)

5.4.9 Delay status reporting [94](#delay-status-reporting)

5.5 PCH reception [95](#pch-reception)

5.6 BCH reception [96](#bch-reception)

5.7 Discontinuous Reception (DRX) [96](#discontinuous-reception-drx)

5.7a Discontinuous Reception (DRX) for MBS Broadcast
[104](#a-discontinuous-reception-drx-for-mbs-broadcast)

5.7b Discontinuous Reception (DRX) for MBS Multicast
[105](#b-discontinuous-reception-drx-for-mbs-multicast)

5.8 Transmission and reception without dynamic scheduling
[109](#transmission-and-reception-without-dynamic-scheduling)

5.8.1 Downlink [109](#downlink)

5.8.1a Downlink for Multicast [109](#a-downlink-for-multicast)

5.8.2 Uplink [110](#uplink)

5.8.3 Sidelink [115](#sidelink)

5.9 Activation/Deactivation of SCells
[116](#activationdeactivation-of-scells)

5.10 Activation/Deactivation of PDCP duplication
[118](#activationdeactivation-of-pdcp-duplication)

5.11 MAC reconfiguration [119](#mac-reconfiguration)

5.12 MAC Reset [120](#mac-reset)

5.12a Void [122](#a-void)

5.13 Handling of unknown, unforeseen and erroneous protocol data
[122](#handling-of-unknown-unforeseen-and-erroneous-protocol-data)

5.14 Handling of measurement gaps [122](#handling-of-measurement-gaps)

5.15 Bandwidth Part (BWP) operation [122](#bandwidth-part-bwp-operation)

5.15.1 Downlink and Uplink [122](#downlink-and-uplink)

5.15.2 Sidelink [127](#sidelink-1)

5.16 SUL operation [128](#sul-operation)

5.17 Beam Failure Detection and Recovery procedure
[128](#beam-failure-detection-and-recovery-procedure)

5.18 Handling of MAC CEs [132](#handling-of-mac-ces)

5.18.1 General [132](#general-5)

5.18.2 Activation/Deactivation of Semi-persistent CSI-RS/CSI-IM resource
set
[133](#activationdeactivation-of-semi-persistent-csi-rscsi-im-resource-set)

5.18.3 Aperiodic CSI Trigger State Subselection
[134](#aperiodic-csi-trigger-state-subselection)

5.18.4 Activation/Deactivation of UE-specific PDSCH TCI state
[134](#activationdeactivation-of-ue-specific-pdsch-tci-state)

5.18.5 Indication of TCI state for UE-specific PDCCH
[134](#indication-of-tci-state-for-ue-specific-pdcch)

5.18.6 Activation/Deactivation of Semi-persistent CSI reporting on PUCCH
[135](#activationdeactivation-of-semi-persistent-csi-reporting-on-pucch)

5.18.7 Activation/Deactivation of Semi-persistent SRS and Indication of
spatial relation of SP/AP SRS
[135](#activationdeactivation-of-semi-persistent-srs-and-indication-of-spatial-relation-of-spap-srs)

5.18.8 Activation/Deactivation of spatial relation of PUCCH resource
[135](#activationdeactivation-of-spatial-relation-of-pucch-resource)

5.18.9 Activation/Deactivation of semi-persistent ZP CSI-RS resource set
[136](#activationdeactivation-of-semi-persistent-zp-csi-rs-resource-set)

5.18.10 Recommended Bit Rate [136](#recommended-bit-rate)

5.18.11 Void [137](#void)

5.18.12 Void [137](#void-1)

5.18.13 Void [137](#void-2)

5.18.14 Update of Pathloss Reference RS of SRS
[137](#update-of-pathloss-reference-rs-of-srs)

5.18.15 Update of Pathloss Reference RS of PUSCH
[137](#update-of-pathloss-reference-rs-of-pusch)

5.18.16 Indication of spatial relation of SRS resource for a Serving
Cell set
[137](#indication-of-spatial-relation-of-srs-resource-for-a-serving-cell-set)

5.18.17 Activation/Deactivation of Semi-Persistent Positioning SRS
[138](#activationdeactivation-of-semi-persistent-positioning-srs)

5.18.18 Timing offset adjustments for IAB
[138](#timing-offset-adjustments-for-iab)

5.18.19 Guard symbols for IAB [138](#guard-symbols-for-iab)

5.18.20 Positioning Measurement Gap Activation/Deactivation Command
[139](#positioning-measurement-gap-activationdeactivation-command)

5.18.21 PPW Activation/Deactivation Command
[139](#ppw-activationdeactivation-command)

5.18.22 Update of PUCCH Power Control Set for multiple TRP PUCCH
repetition
[140](#update-of-pucch-power-control-set-for-multiple-trp-pucch-repetition)

5.18.23 Unified TCI States Activation/Deactivation MAC CE
[140](#unified-tci-states-activationdeactivation-mac-ce)

5.18.24 Update of Differential Koffset
[140](#update-of-differential-koffset)

5.18.25 BFD-RS Indication MAC CE [140](#bfd-rs-indication-mac-ce)

5.18.26 Restricted and recommended beam indication for IAB
[140](#restricted-and-recommended-beam-indication-for-iab)

5.18.27 DL TX power adjustment for IAB
[141](#dl-tx-power-adjustment-for-iab)

5.18.28 UL PSD range adjustment for IAB
[142](#ul-psd-range-adjustment-for-iab)

5.18.29 Timing case indication for IAB
[142](#timing-case-indication-for-iab)

5.18.30 Case-6 Timing Request [142](#case-6-timing-request)

5.18.31 Backhaul Link Beam Indication for NCR
[142](#backhaul-link-beam-indication-for-ncr)

5.18.32 Access Link Beam Indication for NCR
[143](#access-link-beam-indication-for-ncr)

5.18.33 Enhanced Unified TCI States Activation/Deactivation MAC CE
[143](#enhanced-unified-tci-states-activationdeactivation-mac-ce)

5.18.34 Activation/deactivation of PSI-based SDU discard
[143](#activationdeactivation-of-psi-based-sdu-discard)

5.18.35 LTM Cell Switch Command [143](#ltm-cell-switch-command)

5.18.36 Candidate Cell TCI States Activation/Deactivation
[144](#candidate-cell-tci-states-activationdeactivation)

5.18.37 Activation/Deactivation of Aggregated Semi-Persistent
Positioning SRS
[144](#activationdeactivation-of-aggregated-semi-persistent-positioning-srs)

5.19 Data inactivity monitoring [145](#data-inactivity-monitoring)

5.20 Void [145](#void-3)

5.21 LBT operation [145](#lbt-operation)

5.21.1 General [145](#general-6)

5.21.2 LBT failure detection and recovery procedure
[145](#lbt-failure-detection-and-recovery-procedure)

5.22 SL-SCH Data transfer and SL-PRS transmission
[147](#sl-sch-data-transfer-and-sl-prs-transmission)

5.22.1 SL-SCH Data and SL-PRS transmission
[147](#sl-sch-data-and-sl-prs-transmission)

5.22.1.1 SL Grant reception and SCI transmission
[147](#sl-grant-reception-and-sci-transmission)

5.22.1.2 TX resource (re-)selection check
[169](#tx-resource-re-selection-check)

5.22.1.2a Re-evaluation and Pre-emption
[170](#a-re-evaluation-and-pre-emption)

5.22.1.2b Re-selection for using a received resource conflict indication
[172](#b-re-selection-for-using-a-received-resource-conflict-indication)

5.22.1.2c Resource re-selection from SL LBT Failure indication
[173](#c-resource-re-selection-from-sl-lbt-failure-indication)

5.22.1.3 Sidelink HARQ operation and SL-PRS transmission
[173](#sidelink-harq-operation-and-sl-prs-transmission)

5.22.1.3.1 Sidelink HARQ Entity [173](#sidelink-harq-entity)

5.22.1.3.1a Sidelink process not associated with Dedicated SL-PRS
resource pool
[176](#a-sidelink-process-not-associated-with-dedicated-sl-prs-resource-pool)

5.22.1.3.2 PSFCH reception [178](#psfch-reception)

5.22.1.3.3 HARQ-based Sidelink RLF detection
[179](#harq-based-sidelink-rlf-detection)

5.22.1.3.4 Processing of sidelink grant on Dedicated SL-PRS resource
pool
[180](#processing-of-sidelink-grant-on-dedicated-sl-prs-resource-pool)

5.22.1.3.5 Sidelink process associated with Dedicated SL-PRS resource
pool
[181](#sidelink-process-associated-with-dedicated-sl-prs-resource-pool)

5.22.1.4 Multiplexing and assembly [181](#multiplexing-and-assembly-1)

5.22.1.4.0 General [181](#general-7)

5.22.1.4.1 Logical channel prioritization
[181](#logical-channel-prioritization-1)

5.22.1.4.1.1 General [181](#general-8)

5.22.1.4.1.2 Selection of logical channels and SL-PRS
[182](#selection-of-logical-channels-and-sl-prs)

5.22.1.4.1.3 Allocation of sidelink resources
[185](#allocation-of-sidelink-resources)

5.22.1.4.2 Multiplexing of MAC Control Elements and MAC SDUs
[186](#multiplexing-of-mac-control-elements-and-mac-sdus-1)

5.22.1.5 Scheduling Request [186](#scheduling-request-1)

5.22.1.6 Buffer Status Reporting [187](#buffer-status-reporting-1)

5.22.1.7 CSI Reporting [190](#csi-reporting)

5.22.1.8 Void [190](#void-4)

5.22.1.9 IUC-Request transmission [190](#iuc-request-transmission)

5.22.1.10 IUC-Information Reporting [191](#iuc-information-reporting)

5.22.1.10.1 General [191](#general-9)

5.22.1.10.2 Reception of IUC-Information Reporting
[192](#reception-of-iuc-information-reporting)

5.22.1.11 TX carrier (re-)selection [192](#tx-carrier-re-selection)

5.22.1.12 SL-PRS Resource Request [194](#sl-prs-resource-request)

5.22.2 SL-SCH Data and SL-PRS reception
[194](#sl-sch-data-and-sl-prs-reception)

5.22.2.1 SCI reception [194](#sci-reception)

5.22.2.2 Sidelink HARQ operation and SL-PRS reception on Shared SL-PRS
resource pool
[195](#sidelink-harq-operation-and-sl-prs-reception-on-shared-sl-prs-resource-pool)

5.22.2.2.1 Sidelink HARQ Entity [195](#sidelink-harq-entity-1)

5.22.2.2.2 Sidelink process [196](#sidelink-process)

5.22.2.3 Disassembly and demultiplexing
[197](#disassembly-and-demultiplexing-1)

5.22.2.4 SL-PRS reception on Dedicated SL-PRS resource pool
[198](#sl-prs-reception-on-dedicated-sl-prs-resource-pool)

5.23 SL-BCH data transfer [198](#sl-bch-data-transfer)

5.23.1 SL-BCH data transmission [198](#sl-bch-data-transmission)

5.23.2 SL-BCH data reception [198](#sl-bch-data-reception)

5.24 Handling of PRS Processing Window
[198](#handling-of-prs-processing-window)

5.25 Positioning Measurement Gap Activation/Deactivation Request
[199](#positioning-measurement-gap-activationdeactivation-request)

5.26 Positioning SRS transmission in RRC_INACTIVE
[199](#positioning-srs-transmission-in-rrc_inactive)

5.26.1 General [199](#general-10)

5.26.2 TA validation for SRS transmission in RRC_INACTIVE
[199](#ta-validation-for-srs-transmission-in-rrc_inactive)

5.27 Small Data Transmission [200](#small-data-transmission)

5.27.1 General [200](#general-11)

5.27.2 TA Validation for CG-SDT [202](#ta-validation-for-cg-sdt)

5.28 Sidelink Discontinuous Reception (DRX)
[203](#sidelink-discontinuous-reception-drx)

5.28.1 General [203](#general-12)

5.28.2 Behaviour of UE receiving SL-SCH Data
[203](#behaviour-of-ue-receiving-sl-sch-data)

5.28.3 Behaviour of UE transmitting SL-SCH Data
[207](#behaviour-of-ue-transmitting-sl-sch-data)

5.29 Activation/Deactivation of SCG
[208](#activationdeactivation-of-scg)

5.30 Handling of FR2 UL gap [209](#handling-of-fr2-ul-gap)

5.31 Sidelink LBT operation [209](#sidelink-lbt-operation)

5.31.1 General [209](#general-13)

5.31.2 Sidelink LBT failure detection and recovery procedure
[209](#sidelink-lbt-failure-detection-and-recovery-procedure)

5.32 Void [210](#void-5)

5.33 First PUSCH transmission of RACH-less handover
[210](#first-pusch-transmission-of-rach-less-handover)

5.34 Cell-Level Energy Saving [211](#cell-level-energy-saving)

5.34.1 General [211](#general-14)

5.34.2 Cell Discontinuous Transmission
[211](#cell-discontinuous-transmission)

5.34.3 Cell Discontinuous Reception [213](#cell-discontinuous-reception)

6 Protocol Data Units, formats and parameters
[214](#protocol-data-units-formats-and-parameters)

6.1 Protocol Data Units [214](#protocol-data-units)

6.1.1 General [214](#general-15)

6.1.2 MAC PDU (DL-SCH and UL-SCH except transparent MAC and Random
Access Response)
[214](#mac-pdu-dl-sch-and-ul-sch-except-transparent-mac-and-random-access-response)

6.1.3 MAC Control Elements (CEs) [217](#mac-control-elements-ces)

6.1.3.1 Buffer Status Report MAC CEs
[217](#buffer-status-report-mac-ces)

6.1.3.2 C-RNTI MAC CE [226](#c-rnti-mac-ce)

6.1.3.3 UE Contention Resolution Identity MAC CE
[226](#ue-contention-resolution-identity-mac-ce)

6.1.3.4 Timing Advance Command MAC CE
[226](#timing-advance-command-mac-ce)

6.1.3.4a Absolute Timing Advance Command MAC CE
[227](#a-absolute-timing-advance-command-mac-ce)

6.1.3.5 DRX Command MAC CE [227](#drx-command-mac-ce)

6.1.3.6 Long DRX Command MAC CE [227](#long-drx-command-mac-ce)

6.1.3.7 Configured Grant Confirmation MAC CE
[227](#configured-grant-confirmation-mac-ce)

6.1.3.8 Single Entry PHR MAC CE [227](#single-entry-phr-mac-ce)

6.1.3.9 Multiple Entry PHR MAC CE [229](#multiple-entry-phr-mac-ce)

6.1.3.10 SCell Activation/Deactivation MAC CEs
[232](#scell-activationdeactivation-mac-ces)

6.1.3.11 Duplication Activation/Deactivation MAC CE
[233](#duplication-activationdeactivation-mac-ce)

6.1.3.12 SP CSI-RS/CSI-IM Resource Set Activation/Deactivation MAC CE
[233](#sp-csi-rscsi-im-resource-set-activationdeactivation-mac-ce)

6.1.3.13 Aperiodic CSI Trigger State Subselection MAC CE
[234](#aperiodic-csi-trigger-state-subselection-mac-ce)

6.1.3.14 TCI States Activation/Deactivation for UE-specific PDSCH MAC CE
[235](#tci-states-activationdeactivation-for-ue-specific-pdsch-mac-ce)

6.1.3.15 TCI State Indication for UE-specific PDCCH MAC CE
[236](#tci-state-indication-for-ue-specific-pdcch-mac-ce)

6.1.3.16 SP CSI reporting on PUCCH Activation/Deactivation MAC CE
[236](#sp-csi-reporting-on-pucch-activationdeactivation-mac-ce)

6.1.3.17 SP SRS Activation/Deactivation MAC CE
[237](#sp-srs-activationdeactivation-mac-ce)

6.1.3.18 PUCCH spatial relation Activation/Deactivation MAC CE
[238](#pucch-spatial-relation-activationdeactivation-mac-ce)

6.1.3.19 SP ZP CSI-RS Resource Set Activation/Deactivation MAC CE
[239](#sp-zp-csi-rs-resource-set-activationdeactivation-mac-ce)

6.1.3.20 Recommended bit rate MAC CE [239](#recommended-bit-rate-mac-ce)

6.1.3.21 Timing Delta MAC CE [240](#timing-delta-mac-ce)

6.1.3.22 Guard Symbols MAC CEs [241](#guard-symbols-mac-ces)

6.1.3.23 BFR MAC CEs [242](#bfr-mac-ces)

6.1.3.24 Enhanced TCI States Activation/Deactivation for UE-specific
PDSCH MAC CE
[243](#enhanced-tci-states-activationdeactivation-for-ue-specific-pdsch-mac-ce)

6.1.3.25 Enhanced PUCCH Spatial Relation Activation/Deactivation MAC CE
[244](#enhanced-pucch-spatial-relation-activationdeactivation-mac-ce)

6.1.3.26 Enhanced SP/AP SRS Spatial Relation Indication MAC CE
[245](#enhanced-spap-srs-spatial-relation-indication-mac-ce)

6.1.3.27 SRS Pathloss Reference RS Update MAC CE
[246](#srs-pathloss-reference-rs-update-mac-ce)

6.1.3.28 PUSCH Pathloss Reference RS Update MAC CE
[247](#pusch-pathloss-reference-rs-update-mac-ce)

6.1.3.29 Serving Cell Set based SRS Spatial Relation Indication MAC CE
[247](#serving-cell-set-based-srs-spatial-relation-indication-mac-ce)

6.1.3.30 LBT failure MAC CEs [249](#lbt-failure-mac-ces)

6.1.3.31 Multiple Entry Configured Grant Confirmation MAC CE
[250](#multiple-entry-configured-grant-confirmation-mac-ce)

6.1.3.32 Duplication RLC Activation/Deactivation MAC CE
[250](#duplication-rlc-activationdeactivation-mac-ce)

6.1.3.33 Sidelink Buffer Status Report MAC CEs
[250](#sidelink-buffer-status-report-mac-ces)

6.1.3.34 Sidelink Configured Grant Confirmation MAC CE
[251](#sidelink-configured-grant-confirmation-mac-ce)

6.1.3.35 Sidelink CSI Reporting MAC CE
[252](#sidelink-csi-reporting-mac-ce)

6.1.3.36 SP Positioning SRS Activation/Deactivation MAC CE
[252](#sp-positioning-srs-activationdeactivation-mac-ce)

6.1.3.37 Guard Symbols MAC CEs for Case-6 and Case-7 timing modes
[255](#guard-symbols-mac-ces-for-case-6-and-case-7-timing-modes)

6.1.3.38 Case-7 Timing advance offset MAC CE
[256](#case-7-timing-advance-offset-mac-ce)

6.1.3.39 Case-6 Timing Request MAC CE
[256](#case-6-timing-request-mac-ce)

6.1.3.40 Positioning Measurement Gap Activation/Deactivation Request MAC
CE
[256](#positioning-measurement-gap-activationdeactivation-request-mac-ce)

6.1.3.41 Positioning Measurement Gap Activation/Deactivation Command MAC
CE
[257](#positioning-measurement-gap-activationdeactivation-command-mac-ce)

6.1.3.42 PPW Activation/Deactivation Command MAC CE
[257](#ppw-activationdeactivation-command-mac-ce)

6.1.3.43 Enhanced BFR MAC CEs [258](#enhanced-bfr-mac-ces)

6.1.3.44 Enhanced TCI States Indication for UE-specific PDCCH MAC CE
[261](#enhanced-tci-states-indication-for-ue-specific-pdcch-mac-ce)

6.1.3.45 PUCCH spatial relation Activation/Deactivation for multiple TRP
PUCCH repetition MAC CE
[262](#pucch-spatial-relation-activationdeactivation-for-multiple-trp-pucch-repetition-mac-ce)

6.1.3.46 PUCCH Power Control Set Update for multiple TRP PUCCH
repetition MAC CE
[263](#pucch-power-control-set-update-for-multiple-trp-pucch-repetition-mac-ce)

6.1.3.47 Unified TCI States Activation/Deactivation MAC CE
[264](#unified-tci-states-activationdeactivation-mac-ce-1)

6.1.3.48 Enhanced Single Entry PHR MAC CE
[265](#enhanced-single-entry-phr-mac-ce)

6.1.3.49 Enhanced Multiple Entry PHR MAC CE
[266](#enhanced-multiple-entry-phr-mac-ce)

6.1.3.50 Enhanced Single Entry PHR for multiple TRP MAC CE
[271](#enhanced-single-entry-phr-for-multiple-trp-mac-ce)

6.1.3.51 Enhanced Multiple Entry PHR for multiple TRP MAC CE
[271](#enhanced-multiple-entry-phr-for-multiple-trp-mac-ce)

6.1.3.52 Sidelink DRX Command MAC CE [274](#sidelink-drx-command-mac-ce)

6.1.3.53 Sidelink Inter-UE Coordination Information MAC CE
[274](#sidelink-inter-ue-coordination-information-mac-ce)

6.1.3.54 Sidelink Inter-UE Coordination Request MAC CE
[277](#sidelink-inter-ue-coordination-request-mac-ce)

6.1.3.55 Enhanced SCell Activation/Deactivation MAC CEs
[279](#enhanced-scell-activationdeactivation-mac-ces)

6.1.3.56 Timing Advance Report MAC CE
[280](#timing-advance-report-mac-ce)

6.1.3.57 Differential Koffset MAC CE [280](#differential-koffset-mac-ce)

6.1.3.58 BFD-RS Indication MAC CE [280](#bfd-rs-indication-mac-ce-1)

6.1.3.59 SP/AP SRS TCI State Indication MAC CE
[281](#spap-srs-tci-state-indication-mac-ce)

6.1.3.60 Serving Cell Set based SRS TCI State Indication MAC CE
[282](#serving-cell-set-based-srs-tci-state-indication-mac-ce)

6.1.3.61 Child IAB-DU Restricted Beam Indication MAC CE
[283](#child-iab-du-restricted-beam-indication-mac-ce)

6.1.3.62 IAB-MT Recommended Beam Indication MAC CE
[287](#iab-mt-recommended-beam-indication-mac-ce)

6.1.3.63 DL TX Power Adjustment and Desired DL TX Power Adjustment MAC
CEs
[290](#dl-tx-power-adjustment-and-desired-dl-tx-power-adjustment-mac-ces)

6.1.3.64 Desired IAB-MT PSD range MAC CE
[291](#desired-iab-mt-psd-range-mac-ce)

6.1.3.65 Timing Case Indication MAC CE
[293](#timing-case-indication-mac-ce)

6.1.3.66 NCR Downlink Backhaul Link Beam Indication MAC CE
[294](#ncr-downlink-backhaul-link-beam-indication-mac-ce)

6.1.3.67 NCR Uplink Backhaul Link Beam Indication MAC CE
[294](#ncr-uplink-backhaul-link-beam-indication-mac-ce)

6.1.3.68 NCR Access Link Beam Indication MAC CE
[295](#ncr-access-link-beam-indication-mac-ce)

6.1.3.69 SL LBT failure MAC CE [295](#sl-lbt-failure-mac-ce)

6.1.3.70 Enhanced Unified TCI States Activation/Deactivation MAC CE for
Joint TCI States
[295](#enhanced-unified-tci-states-activationdeactivation-mac-ce-for-joint-tci-states)

6.1.3.71 Enhanced Unified TCI States Activation/Deactivation MAC CE for
Separate TCI States
[296](#enhanced-unified-tci-states-activationdeactivation-mac-ce-for-separate-tci-states)

6.1.3.72 Delay Status Report MAC CE [297](#delay-status-report-mac-ce)

6.1.3.73 PSI-Based SDU Discard Activation/Deactivation MAC CE
[298](#psi-based-sdu-discard-activationdeactivation-mac-ce)

6.1.3.74 SL-PRS Resource Request MAC CE
[299](#sl-prs-resource-request-mac-ce)

6.1.3.75 LTM Cell Switch Command MAC CE
[299](#ltm-cell-switch-command-mac-ce)

6.1.3.76 Candidate Cell TCI States Activation/Deactivation MAC CE
[301](#candidate-cell-tci-states-activationdeactivation-mac-ce)

6.1.3.77 Cross-RRH TCI State Indication for UE-specific PDCCH MAC CE
[302](#cross-rrh-tci-state-indication-for-ue-specific-pdcch-mac-ce)

6.1.3.78 Single Entry PHR with assumed PUSCH MAC CE
[303](#single-entry-phr-with-assumed-pusch-mac-ce)

6.1.3.79 Multiple Entry PHR with assumed PUSCH MAC CE
[304](#multiple-entry-phr-with-assumed-pusch-mac-ce)

6.1.3.80 Enhanced SP CSI reporting on PUCCH Activation/Deactivation MAC
CE
[307](#enhanced-sp-csi-reporting-on-pucch-activationdeactivation-mac-ce)

6.1.3.81 Enhanced Single Entry PHR for multiple TRP STx2P MAC CE
[308](#enhanced-single-entry-phr-for-multiple-trp-stx2p-mac-ce)

6.1.3.82 Enhanced Multiple Entry PHR for multiple TRP STx2P MAC CE
[309](#enhanced-multiple-entry-phr-for-multiple-trp-stx2p-mac-ce)

6.1.3.83 Aggregated SP Positioning SRS Activation/Deactivation MAC CE
[312](#aggregated-sp-positioning-srs-activationdeactivation-mac-ce)

6.1.4 MAC PDU (transparent MAC) [314](#mac-pdu-transparent-mac)

6.1.5 MAC PDU (Random Access Response)
[314](#mac-pdu-random-access-response)

6.1.5a MAC PDU (MSGB) [315](#a-mac-pdu-msgb)

6.1.6 MAC PDU (SL-SCH) [316](#mac-pdu-sl-sch)

6.2 Formats and parameters [317](#formats-and-parameters)

6.2.1 MAC subheader for DL-SCH and UL-SCH
[317](#mac-subheader-for-dl-sch-and-ul-sch)

6.2.2 MAC subheader for Random Access Response
[322](#mac-subheader-for-random-access-response)

6.2.2a MAC subheader for MSGB [322](#a-mac-subheader-for-msgb)

6.2.3 MAC payload for Random Access Response
[323](#mac-payload-for-random-access-response)

6.2.3a MAC payload for MSGB [324](#a-mac-payload-for-msgb)

6.2.4 MAC subheader for SL-SCH [326](#mac-subheader-for-sl-sch)

7 Variables and constants [327](#variables-and-constants)

7.1 RNTI values [327](#rnti-values)

7.2 Backoff Parameter values [330](#backoff-parameter-values)

7.3 DELTA_PREAMBLE values [330](#delta_preamble-values)

7.4 PRACH Mask Index values [331](#prach-mask-index-values)

Annex A (informative): Change history
[332](#annex-a-informative-change-history)