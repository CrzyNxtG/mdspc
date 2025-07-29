#  Contents {#contents .TT}

Foreword [5](#foreword)

1 Scope [6](#scope)

2 References [6](#references)

3 Definitions, symbols and abbreviations
[7](#definitions-symbols-and-abbreviations)

3.1 Definitions [7](#definitions)

3.2 Abbreviations [9](#abbreviations)

4 General description of RRC_IDLE state and RRC_INACTIVE state
[10](#general-description-of-rrc_idle-state-and-rrc_inactive-state)

4.1 Overview [10](#overview)

4.2 Functional division between AS and NAS in RRC_IDLE state and
RRC_INACTIVE state
[12](#functional-division-between-as-and-nas-in-rrc_idle-state-and-rrc_inactive-state)

4.3 Service types in RRC_IDLE state
[15](#service-types-in-rrc_idle-state)

4.4 Service types in RRC_INACTIVE state
[15](#service-types-in-rrc_inactive-state)

4.5 Cell Categories [15](#cell-categories)

5 Process and procedure descriptions
[16](#process-and-procedure-descriptions)

5.1 PLMN selection and SNPN selection
[16](#plmn-selection-and-snpn-selection)

5.1.1 Support for PLMN selection [17](#support-for-plmn-selection)

5.1.1.1 General [17](#general)

5.1.1.2 NR case [17](#nr-case)

5.1.1.3 E-UTRA case [17](#e-utra-case)

5.1.2 Support for SNPN selection [17](#support-for-snpn-selection)

5.1.2.1 General [17](#general-1)

5.1.2.2 NR case [17](#nr-case-1)

5.2 Cell selection and reselection [18](#cell-selection-and-reselection)

5.2.1 Introduction [18](#introduction)

5.2.2 States and state transitions in RRC_IDLE state and RRC_INACTIVE
state
[19](#states-and-state-transitions-in-rrc_idle-state-and-rrc_inactive-state)

5.2.3 Cell Selection process [20](#cell-selection-process)

5.2.3.1 Description [20](#description)

5.2.3.2 Cell Selection Criterion [21](#cell-selection-criterion)

5.2.3.3 E-UTRAN case in Cell Selection
[22](#e-utran-case-in-cell-selection)

5.2.4 Cell Reselection evaluation process
[22](#cell-reselection-evaluation-process)

5.2.4.1 Reselection priorities handling
[22](#reselection-priorities-handling)

5.2.4.2 Measurement rules for cell re-selection
[25](#measurement-rules-for-cell-re-selection)

5.2.4.3 Mobility states of a UE [26](#mobility-states-of-a-ue)

5.2.4.3.0 Introduction [26](#introduction-1)

5.2.4.3.1 Scaling rules [27](#scaling-rules)

5.2.4.4 Cells with cell reservations, access restrictions or unsuitable
for normal camping
[27](#cells-with-cell-reservations-access-restrictions-or-unsuitable-for-normal-camping)

5.2.4.5 NR Inter-frequency and inter-RAT Cell Reselection criteria
[28](#nr-inter-frequency-and-inter-rat-cell-reselection-criteria)

5.2.4.6 Intra-frequency and equal priority inter-frequency Cell
Reselection criteria
[28](#intra-frequency-and-equal-priority-inter-frequency-cell-reselection-criteria)

5.2.4.7 Cell reselection parameters in system information broadcasts
[29](#cell-reselection-parameters-in-system-information-broadcasts)

5.2.4.7.0 General reselection parameters
[29](#general-reselection-parameters)

5.2.4.7.1 Speed dependent reselection parameters
[32](#speed-dependent-reselection-parameters)

5.2.4.7.2 Slice-based cell reselection parameters
[33](#slice-based-cell-reselection-parameters)

5.2.4.8 Inter-RAT Cell reselection in RRC_INACTIVE state
[33](#inter-rat-cell-reselection-in-rrc_inactive-state)

5.2.4.9 Relaxed measurement [33](#relaxed-measurement)

5.2.4.9.0 Relaxed measurement rules [33](#relaxed-measurement-rules)

5.2.4.9.1 Relaxed measurement criterion for UE with low mobility
[35](#relaxed-measurement-criterion-for-ue-with-low-mobility)

5.2.4.9.2 Relaxed measurement criterion for UE not at cell edge
[35](#relaxed-measurement-criterion-for-ue-not-at-cell-edge)

5.2.4.9.3 Relaxed measurement criterion for a stationary (e)RedCap UE
[35](#relaxed-measurement-criterion-for-a-stationary-eredcap-ue)

5.2.4.9.4 Relaxed measurement criterion for a stationary (e)RedCap UE
not at cell edge
[35](#relaxed-measurement-criterion-for-a-stationary-eredcap-ue-not-at-cell-edge)

5.2.4.10 Cell reselection with CAG cells
[36](#cell-reselection-with-cag-cells)

5.2.4.11 Reselection priorities for slice-based cell reselection
[36](#reselection-priorities-for-slice-based-cell-reselection)

5.2.5 Camped Normally state [37](#camped-normally-state)

5.2.6 Selection of cell at transition to RRC_IDLE or RRC_INACTIVE state
[37](#selection-of-cell-at-transition-to-rrc_idle-or-rrc_inactive-state)

5.2.7 Any Cell Selection state [37](#any-cell-selection-state)

5.2.8 Camped on Any Cell state [38](#camped-on-any-cell-state)

5.3 Cell Reservations and Access Restrictions
[38](#cell-reservations-and-access-restrictions)

5.3.0 Introduction [38](#introduction-2)

5.3.1 Cell status and cell reservations
[38](#cell-status-and-cell-reservations)

5.3.2 Unified access control [43](#unified-access-control)

5.4 Tracking Area registration [43](#tracking-area-registration)

5.5 RAN Area registration [43](#ran-area-registration)

6 Reception of broadcast information
[43](#reception-of-broadcast-information)

6.1 Reception of system information
[43](#reception-of-system-information)

6.2 Reception of MBS [44](#reception-of-mbs)

7 Paging [44](#paging)

7.1 Discontinuous Reception for paging
[44](#discontinuous-reception-for-paging)

7.2 Paging Early Indication [47](#paging-early-indication)

7.2.1 Paging Early Indication reception
[47](#paging-early-indication-reception)

7.3 Subgrouping [48](#subgrouping)

7.3.0 General [48](#general-2)

7.3.1 CN assigned subgrouping [48](#cn-assigned-subgrouping)

7.3.2 UE_ID based subgrouping [49](#ue_id-based-subgrouping)

7.4 Paging in extended DRX [49](#paging-in-extended-drx)

8 Sidelink Operation [51](#sidelink-operation)

8.1 NR sidelink communication, and V2X sidelink communication, NR
sidelink discovery, and ranging/ sidelink positioning
[51](#nr-sidelink-communication-and-v2x-sidelink-communication-nr-sidelink-discovery-and-ranging-sidelink-positioning)

8.2 Cell selection and reselection for Sidelink
[51](#cell-selection-and-reselection-for-sidelink)

8.2.1 Parameters used for cell selection and reselection triggered for
sidelink
[52](#parameters-used-for-cell-selection-and-reselection-triggered-for-sidelink)

9 Tracking Reference Signal [52](#tracking-reference-signal)

Annex A (informative): Example of Hashed ID Calculation using 32-bit FCS
[53](#annex-a-informative-example-of-hashed-id-calculation-using-32-bit-fcs)

Annex B (informative): Change history
[54](#annex-b-informative-change-history)