### 5.2.1 Channel state information framework

The procedures on aperiodic CSI reporting described in this clause
assume that the CSI reporting is triggered by DCI format 0_1, but they
equally apply to CSI reporting triggered by DCI format 0_2, by applying
the higher layer parameter *reportTriggerSizeDCI-0-2* instead of
*reportTriggerSize*. The procedures on aperiodic CSI reporting described
in this clause assume that the CSI reporting is triggered by DCI format
0_1, but they equally apply to CSI reporting triggered by DCI format
0_3.

The time and frequency resources that can be used by the UE to report
CSI are controlled by the gNB. CSI may consist of Channel Quality
Indicator (CQI), precoding matrix indicator (PMI), CSI-RS resource
indicator (CRI), SS/PBCH Block Resource indicator (SSBRI), layer
indicator (LI), rank indicator (RI), L1-RSRP, L1-SINR, CapabilityIndex
or time-domain channel properties (TDCP).

For CQI, PMI, CRI, SSBRI, LI, RI, L1-RSRP, L1-SINR, CapabilityIndex,
TDCP a UE is configured by higher layers with N≥1 *CSI-ReportConfig*
Reporting Settings and/or X≥1 *ltm-CSI-ReportConfig* Reporting Settings,
M≥1 *CSI-ResourceConfig* Resource Settings and/or Y≥1
*LTM-CSI-ResourceConfig* Resource Settings, and one or two list(s) of
trigger states (given by the higher layer parameters
*CSI-AperiodicTriggerStateList* and
*CSI-SemiPersistentOnPUSCH-TriggerStateList*). Each trigger state in
*CSI-AperiodicTriggerStateList* contains a list of associated
*CSI-ReportConfigs* or one associated *LTM-CSI-ReportConfig* indicating
the Resource Set IDs for channel and optionally for interference where a
Resource Set for interference can only be present for a Report Setting
given by a *CSI-ReportConfig* and a trigger state additionally contains
one or more *reportSubConfigId* if the associated *CSI-ReportConfig*
configured with a list of sub-configurations, as described in Clause
5.2.1.1. Each trigger state in
*CSI-SemiPersistentOnPUSCH-TriggerStateList* contains one associated
*CSI-ReportConfig* or *LTM-CSI-ReportConfig*, and a trigger state
additionally contain one or more *reportSubConfigId* if the associated
CSI-ReportConfig is configured with a list of sub-configurations, as
described in Clause 5.2.1.1.