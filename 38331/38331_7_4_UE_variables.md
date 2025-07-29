## 7.4 UE variables

NOTE: To facilitate the specification of the UE behavioural
requirements, UE variables are represented using ASN.1. Unless
explicitly specified otherwise, it is however up to UE implementation
how to store the variables. The optionality of the IEs in ASN.1 is used
only to indicate that the values may not always be available.

#### -- *NR-UE-Variables*

This ASN.1 segment is the start of the NR UE variable definitions.

\-- ASN1START

\-- NR-UE-VARIABLES-START

NR-UE-Variables DEFINITIONS AUTOMATIC TAGS ::=

BEGIN

IMPORTS

AreaConfiguration-r17,

ARFCN-ValueNR,

CellIdentity,

EUTRA-PhysCellId,

maxCEFReport-r17,

maxCellReport,

MeasId,

MeasIdToAddModList,

MeasIdleCarrierEUTRA-r16,

MeasIdleCarrierNR-r16,

MeasResultIdleEUTRA-r16,

MeasResultIdleNR-r16,

MeasReselectionCarrierNR-r18,

MeasurementValidityDuration-r18,

MeasObjectToAddModList,

MeasConfigAppLayerId-r17,

MeasConfigAppLayer-r17,

maxNrofAppLayerMeas-r17,

AppLayerIdleInactiveConfig-r18,

PhysCellId,

RNTI-Value,

ReportConfigToAddModList,

RSRP-Range,

SL-MeasId-r16,

SL-MeasIdList-r16,

SL-MeasObjectList-r16,

SL-ReportConfigList-r16,

SL-QuantityConfig-r16,

Tx-PoolMeasList-r16,

QuantityConfig,

maxNrofCellMeas,

maxNrofMeasId,

maxFreqIdle-r16,

PhysCellIdUTRA-FDD-r16,

ValidityAreaList-r16,

CondReconfigToAddModList-r16,

ConnEstFailReport-r16,

LoggingDuration-r16,

LoggingInterval-r16,

LogMeasInfoList-r16,

LogMeasInfo-r16,

RA-Report-r16,

RLF-Report-r16,

TraceReference-r16,

WLAN-Identifiers-r16,

WLAN-NameList-r16,

BT-NameList-r16,

PLMN-Identity,

maxNrofRelayMeas-r17,

maxPLMN,

RA-ReportList-r16,

VisitedCellInfoList-r16,

AbsoluteTimeInfo-r16,

LoggedEventTriggerConfig-r16,

LoggedPeriodicalReportConfig-r16,

Sensor-NameList-r16,

SL-SourceIdentity-r17,

SuccessHO-Report-r17,

PLMN-IdentityList2-r16,

AreaConfiguration-r16,

maxNrofSL-MeasId-r16,

maxNrofFreqSL-r16,

maxNrofCLI-RSSI-Resources-r16,

maxNrofCLI-SRS-Resources-r16,

RSSI-ResourceId-r16,

SRS-ResourceId,

VisitedPSCellInfoList-r17,

SuccessPSCell-Report-r18,

maxNPN-r16,

SNPN-ConfigID-List-r18,

AreaConfiguration-v1800,

NID-r16,

SK-CounterConfig-r18,

ReferenceConfiguration-r18,

maxNrofLTM-Configs-plus1-r18,

maxSecurityCellSet-r18

FROM NR-RRC-Definitions;

\-- NR-UE-VARIABLES-STOP

\-- ASN1STOP

#### -- *VarAppLayerIdleConfig*

The UE variable *VarAppLayerIdleConfig* includes the parameters of the
application layer measurements stored in the UE while in RRC_IDLE.

*VarAppLayerIdleConfig* UE variable

\-- ASN1START

\-- TAG-VARAPPLAYERIDLECONFIG-START

VarAppLayerIdleConfig-r18 ::= SEQUENCE {

appLayerIdleConfigList-r18 SEQUENCE (SIZE (1..maxNrofAppLayerMeas-r17))
OF VarAppLayerIdle-r18

}

VarAppLayerIdle-r18 ::= SEQUENCE {

measConfigAppLayerId-r18 MeasConfigAppLayerId-r17,

serviceType-r18 ENUMERATED {streaming, mtsi, vr, spare5, spare4, spare3,
spare2, spare1},

appLayerIdleInactiveConfig-r18 AppLayerIdleInactiveConfig-r18,

appLayerMeasPriority-r18 INTEGER (1..16) OPTIONAL

}

\-- TAG-VARAPPLAYERIDLECONFIG-STOP

\-- ASN1STOP

#### -- *VarAppLayerPLMN-ListConfig*

The UE variable *VarAppLayerPLMN-ListConfig* includes the PLMNs to which
application layer measurement reports and application layer measurement
configurations are allowed to be sent.

*VarAppLayerPLMN-ListConfig* UE variable

\-- ASN1START

\-- TAG-VARAPPLAYERPLMN-LISTCONFIG-START

VarAppLayerPLMN-ListConfig-r18 ::= SEQUENCE {

plmnConfigList-r18 SEQUENCE (SIZE (1..maxNrofAppLayerMeas-r17)) OF
VarAppLayerPLMN-List-r18

}

VarAppLayerPLMN-List-r18 ::= SEQUENCE {

measConfigAppLayerId-r18 MeasConfigAppLayerId-r17,

plmn-IdentityList-r18 PLMN-IdentityList2-r16

}

\-- TAG-VARAPPLAYERPLMN-LISTCONFIG-STOP

\-- ASN1STOP

#### -- *VarConditionalReconfig*

The UE variable *VarConditionalReconfig* includes the accumulated
configuration of the conditional handover, conditional PSCell addition
or conditional PSCell change configurations including the pointers to
conditional handover, conditional PSCell addition, conditional PSCell
change, or subsequent CPAC execution condition (associated *measId*(s)),
the stored target candidate SpCell *RRCReconfiguration*, the stored
reference configuration, and the stored *SK-Counter* configuration.

*VarConditionalReconfig UE variable*

\-- ASN1START

\-- TAG-VARCONDITIONALRECONFIG-START

VarConditionalReconfig ::= SEQUENCE {

condReconfigList CondReconfigToAddModList-r16 OPTIONAL,

scpac-ReferenceConfiguration-r18 ReferenceConfiguration-r18 OPTIONAL,

sk-CounterConfiguration-r18 SEQUENCE (SIZE (1..maxSecurityCellSet-r18))
OF SK-CounterConfig-r18 OPTIONAL

}

\-- TAG-VARCONDITIONALRECONFIG-STOP

\-- ASN1STOP

#### -- *VarConnEstFailReport*

The UE variable *VarConnEstFailReport* includes the connection
establishment failure and/or connection resume failure information.

*VarConnEstFailReport* UE variable

\-- ASN1START

\-- TAG-VARCONNESTFAILREPORT-START

VarConnEstFailReport-r16 ::= SEQUENCE {

connEstFailReport-r16 ConnEstFailReport-r16,

networkIdentity-r18 CHOICE {

plmn-Identity-r18 PLMN-Identity,

snpn-Identity-r18 SNPN-Identity-r18

}

}

SNPN-Identity-r18 ::= SEQUENCE {

plmn-Identity-r18 PLMN-Identity,

nid-r18 NID-r16

}

\-- TAG-VARCONNESTFAILREPORT-STOP

\-- ASN1STOP

#### -- *VarConnEstFailReportList*

The UE variable *VarConnEstFailReportList* includes a list of the
connection establishment failure and/or connection resume failure
information.

*VarConnEstFailReportList* UE variable

\-- ASN1START

\-- TAG-VARCONNESTFAILREPORTLIST-START

VarConnEstFailReportList-r17 ::= SEQUENCE {

connEstFailReportList-r17 SEQUENCE (SIZE (1..maxCEFReport-r17)) OF
VarConnEstFailReport-r16

}

\-- TAG-VARCONNESTFAILREPORTLIST-STOP

\-- ASN1STOP

#### -- *VarLogMeasConfig*

The UE variable *VarLogMeasConfig* includes the configuration of the
logging of measurements to be performed by the UE while in RRC_IDLE,
RRC_INACTIVE, covering intra-frequency, inter-frequency and inter-RAT
mobility related measurements. The UE performs logging of measurements
only while in RRC_IDLE and RRC_INACTIVE.

*VarLogMeasConfig* UE variable

\-- ASN1START

\-- TAG-VARLOGMEASCONFIG-START

VarLogMeasConfig-r16 ::= SEQUENCE {

areaConfiguration-r16 AreaConfiguration-r16 OPTIONAL,

bt-NameList-r16 BT-NameList-r16 OPTIONAL,

wlan-NameList-r16 WLAN-NameList-r16 OPTIONAL,

sensor-NameList-r16 Sensor-NameList-r16 OPTIONAL,

loggingDuration-r16 LoggingDuration-r16,

reportType CHOICE {

periodical LoggedPeriodicalReportConfig-r16,

eventTriggered LoggedEventTriggerConfig-r16

},

earlyMeasIndication-r17 ENUMERATED {true} OPTIONAL,

areaConfiguration-r17 AreaConfiguration-r17 OPTIONAL,

areaConfiguration-v1800 AreaConfiguration-v1800 OPTIONAL

}

\-- TAG-VARLOGMEASCONFIG-STOP

\-- ASN1STOP

#### -- *VarLogMeasReport*

The UE variable *VarLogMeasReport* includes the logged measurements
information.

*VarLogMeasReport* UE variable

\-- ASN1START

\-- TAG-VARLOGMEASREPORT-START

VarLogMeasReport-r16 ::= SEQUENCE {

absoluteTimeInfo-r16 AbsoluteTimeInfo-r16,

traceReference-r16 TraceReference-r16,

traceRecordingSessionRef-r16 OCTET STRING (SIZE (2)),

tce-Id-r16 OCTET STRING (SIZE (1)),

logMeasInfoList-r16 LogMeasInfoList-r16,

sigLoggedMeasType-r17 ENUMERATED {true},

identityList-r18 CHOICE {

plmn-IdentityList-r18 PLMN-IdentityList2-r16,

snpn-ConfigID-List-r18 SNPN-ConfigID-List-r18

}

}

\-- TAG-VARLOGMEASREPORT-STOP

\-- ASN1STOP

#### -- *VarLTM-ServingCellNoResetID*

The IE *VarLTM-ServingCellNoResetID* is used to store the ID associated
with the serving cell based on which the UE determines whether a L2
reset is needed or not upon an LTM cell switch procedure.

*VarLTM-ServingCellNoResetID* UE variable

\-- ASN1START

\-- TAG-VARLTM-SERVINGCELLNORESETID-START

VarLTM-ServingCellNoResetID-r18 ::= SEQUENCE {

ltm-ServingCellNoResetID-r18 INTEGER (1..maxNrofLTM-Configs-plus1-r18)
OPTIONAL

}

\-- TAG-VARLTM-SERVINGCELLNORESETID-STOP

\-- ASN1STOP

#### -- *VarLTM-ServingCellUE-MeasuredTA-ID*

The IE *VarLTM-ServingCellUE-MeasuredTA-ID* is used to store the ID
associated with the serving cell based on which the UE determines
whether UE-based TA measurements are needed or not.

*VarLTM-ServingCellUE-MeasuredTA-ID* UE variable

\-- ASN1START

\-- TAG-VARLTM-SERVINGCELLUE-MEASUREDTA-ID-START

VarLTM-ServingCellUE-MeasuredTA-ID-r18 ::= SEQUENCE {

ltm-ServingCellUE-MeasuredTA-ID-r18 INTEGER
(1..maxNrofLTM-Configs-plus1-r18) OPTIONAL

}

\-- TAG-VARLTM-SERVINGCELLUE-MEASUREDTA-ID-STOP

\-- ASN1STOP

#### -- *VarMeasConfig*

The UE variable *VarMeasConfig* includes the accumulated configuration
of the measurements to be performed by the UE, covering intra-frequency,
inter-frequency and inter-RAT mobility related measurements.

*VarMeasConfig UE variable*

\-- ASN1START

\-- TAG-VARMEASCONFIG-START

VarMeasConfig ::= SEQUENCE {

\-- Measurement identities

measIdList MeasIdToAddModList OPTIONAL,

\-- Measurement objects

measObjectList MeasObjectToAddModList OPTIONAL,

\-- Reporting configurations

reportConfigList ReportConfigToAddModList OPTIONAL,

\-- Other parameters

quantityConfig QuantityConfig OPTIONAL,

s-MeasureConfig CHOICE {

ssb-RSRP RSRP-Range,

csi-RSRP RSRP-Range

} OPTIONAL

}

\-- TAG-VARMEASCONFIG-STOP

\-- ASN1STOP

#### -- *VarMeasConfigSL*

The UE variable *VarMeasConfigSL* includes the accumulated configuration
of the NR sidelink measurements to be performed by the UE of unicast
destination.

*VarMeasConfigSL UE* variable

\-- ASN1START

\-- TAG-VARMEASCONFIGSL-START

VarMeasConfigSL-r16 ::= SEQUENCE {

\-- NR sidelink measurement identities

sl-MeasIdList-r16 SL-MeasIdList-r16 OPTIONAL,

\-- NR sidelink measurement objects

sl-MeasObjectList-r16 SL-MeasObjectList-r16 OPTIONAL,

\-- NR sidelink reporting configurations

sl-ReportConfigList-r16 SL-ReportConfigList-r16 OPTIONAL,

\-- Other parameters

sl-QuantityConfig-r16 SL-QuantityConfig-r16 OPTIONAL

}

\-- TAG-VARMEASCONFIGSL-STOP

\-- ASN1STOP

#### -- *VarMeasIdleConfig*

The UE variable *VarMeasIdleConfig* includes the configuration of the
measurements to be performed by the UE while in RRC_IDLE or RRC_INACTIVE
for NR inter-frequency and inter-RAT (i.e. EUTRA) measurements.

*VarMeasIdleConfig UE* variable

\-- ASN1START

\-- TAG-VARMEASIDLECONFIG-START

VarMeasIdleConfig-r16 ::= SEQUENCE {

measIdleCarrierListNR-r16 SEQUENCE (SIZE (1..maxFreqIdle-r16)) OF
MeasIdleCarrierNR-r16 OPTIONAL,

measIdleCarrierListEUTRA-r16 SEQUENCE (SIZE (1..maxFreqIdle-r16)) OF
MeasIdleCarrierEUTRA-r16 OPTIONAL,

measIdleDuration-r16 ENUMERATED {sec10, sec30, sec60, sec120, sec180,
sec240, sec300, spare},

validityAreaList-r16 ValidityAreaList-r16 OPTIONAL

}

VarEnhMeasIdleConfig-r18 ::= SEQUENCE {

measIdleValidityDuration-r18 MeasurementValidityDuration-r18 OPTIONAL

}

\-- TAG-VARMEASIDLECONFIG-STOP

\-- ASN1STOP

#### -- *VarMeasIdleReport*

The UE variable *VarMeasIdleReport* includes the logged measurements
information.

*VarMeasIdleReport UE* variable

\-- ASN1START

\-- TAG-VARMEASIDLEREPORT-START

VarMeasIdleReport-r16 ::= SEQUENCE {

measReportIdleNR-r16 MeasResultIdleNR-r16 OPTIONAL,

measReportIdleEUTRA-r16 MeasResultIdleEUTRA-r16 OPTIONAL

}

\-- TAG-VARMEASIDLEREPORT-STOP

\-- ASN1STOP

#### -- *VarMeasReportList*

The UE variable *VarMeasReportList* includes information about the
measurements for which the triggering conditions have been met.

*VarMeasReportList UE variable*

\-- ASN1START

\-- TAG-VARMEASREPORTLIST-START

VarMeasReportList ::= SEQUENCE (SIZE (1..maxNrofMeasId)) OF
VarMeasReport

VarMeasReport ::= SEQUENCE {

\-- List of measurement that have been triggered

measId MeasId,

cellsTriggeredList CellsTriggeredList OPTIONAL,

numberOfReportsSent INTEGER,

cli-TriggeredList-r16 CLI-TriggeredList-r16 OPTIONAL,

tx-PoolMeasToAddModListNR-r16 Tx-PoolMeasList-r16 OPTIONAL,

relaysTriggeredList-r17 RelaysTriggeredList-r17 OPTIONAL,

cellsMetLeavingCond-r18 SEQUENCE (SIZE (1..maxCellReport)) OF PhysCellId
OPTIONAL,

reportedBestNeighbourCell-r18 SEQUENCE (SIZE (1..2)) OF PhysCellId
OPTIONAL

}

CellsTriggeredList ::= SEQUENCE (SIZE (1..maxNrofCellMeas)) OF CHOICE {

physCellId PhysCellId,

physCellIdEUTRA EUTRA-PhysCellId,

physCellIdUTRA-FDD-r16 PhysCellIdUTRA-FDD-r16

}

CLI-TriggeredList-r16 ::= CHOICE {

srs-RSRP-TriggeredList-r16 SRS-RSRP-TriggeredList-r16,

cli-RSSI-TriggeredList-r16 CLI-RSSI-TriggeredList-r16

}

SRS-RSRP-TriggeredList-r16 ::= SEQUENCE (SIZE (1..
maxNrofCLI-SRS-Resources-r16)) OF SRS-ResourceId

CLI-RSSI-TriggeredList-r16 ::= SEQUENCE (SIZE (1..
maxNrofCLI-RSSI-Resources-r16)) OF RSSI-ResourceId-r16

RelaysTriggeredList-r17 ::= SEQUENCE (SIZE (1.. maxNrofRelayMeas-r17))
OF SL-SourceIdentity-r17

\-- TAG-VARMEASREPORTLIST-STOP

\-- ASN1STOP

#### -- *VarMeasReportListSL*

The UE variable *VarMeasReportListSL* includes information about the NR
sidelink measurements for which the triggering conditions have been met.

*VarMeasReportListSL UE* variable

\-- ASN1START

\-- TAG-VARMEASREPORTLISTSL-START

VarMeasReportListSL-r16 ::= SEQUENCE (SIZE (1..maxNrofSL-MeasId-r16)) OF
VarMeasReportSL-r16

VarMeasReportSL-r16 ::= SEQUENCE {

\-- List of NR sidelink measurement that have been triggered

sl-MeasId-r16 SL-MeasId-r16,

sl-FrequencyTriggeredList-r16 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
ARFCN-ValueNR OPTIONAL,

sl-NumberOfReportsSent-r16 INTEGER

}

\-- TAG-VARMEASREPORTLISTSL-STOP

\-- ASN1STOP

#### -- *VarMeasReselectionConfig*

The UE variable *VarMeasReselectionConfig* includes the configuration
for reporting the NR inter-frequency and inter-RAT (i.e. EUTRA)
reselection measurements while in RRC_IDLE or RRC_INACTIVE for.

*VarMeasReselectionConfig UE* variable

\-- ASN1START

\-- TAG-VARMEASRESELECTIONCONFIG-START

VarMeasReselectionConfig-r18 ::= SEQUENCE {

measReselectionCarrierListNR-r18 SEQUENCE (SIZE (1..maxFreqIdle-r16)) OF
MeasReselectionCarrierNR-r18 OPTIONAL,

measReselectionValidityDuration-r18 MeasurementValidityDuration-r18
OPTIONAL

}

\-- TAG-VARMEASRESELECTIONCONFIG-STOP

\-- ASN1STOP

#### -- *VarMobilityHistoryReport*

The UE variable *VarMobilityHistoryReport* includes the mobility history
information.

*VarMobilityHistoryReport* UE variable

\-- ASN1START

\-- TAG-VARMOBILITYHISTORYREPORT-START

VarMobilityHistoryReport-r16 ::= VisitedCellInfoList-r16

VarMobilityHistoryReport-r17 ::= SEQUENCE {

visitedCellInfoList-r16 VisitedCellInfoList-r16,

visitedPSCellInfoList-r17 VisitedPSCellInfoList-r17 OPTIONAL

}

\-- TAG-VARMOBILITYHISTORYREPORT-STOP

\-- ASN1STOP

#### -- *VarPendingRNA-Update*

The UE variable *VarPendingRNA-Update* indicates whether there is a
pending RNA update procedure or not. The setting of this BOOLEAN
variable to *true* means that there is a pending RNA Update procedure.

*VarPendingRNA-Update UE variable*

\-- ASN1START

\-- TAG-VARPENDINGRNA-UPDATE-START

VarPendingRNA-Update ::= SEQUENCE {

pendingRNA-Update BOOLEAN OPTIONAL

}

\-- TAG-VARPENDINGRNA-UPDATE-STOP

\-- ASN1STOP

#### -- *VarRA-Report*

The UE variable *VarRA-Report* includes the random-access related
information.

*VarRA-Report* UE variable

\-- ASN1START

\-- TAG-VARRA-REPORT-START

VarRA-Report-r16 ::= SEQUENCE {

ra-ReportList-r16 RA-ReportList-r16,

identityList-r18 CHOICE {

plmn-IdentityList-r18 PLMN-IdentityList2-r16,

snpn-IdentityList-r18 SEQUENCE (SIZE (1..maxNPN-r16)) OF
SNPN-Identity-r18

}

}

\-- TAG-VARRA-REPORT-STOP

\-- ASN1STOP

#### -- *VarResumeMAC-Input*

The UE variable *VarResumeMAC-Input* specifies the input used to
generate the *resumeMAC-I* during RRC Connection Resume procedure.

*VarResumeMAC-Input* UE variable

\-- ASN1START

\-- TAG-VARRESUMEMAC-INPUT-START

VarResumeMAC-Input ::= SEQUENCE {

sourcePhysCellId PhysCellId,

targetCellIdentity CellIdentity,

source-c-RNTI RNTI-Value

}

\-- TAG-VARRESUMEMAC-INPUT-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *VarResumeMAC-Input* field descriptions                               |
+=======================================================================+
| ***targetCellIdentity***                                              |
|                                                                       |
| An input variable used to calculate the *resumeMAC-I*. Set to the     |
| *cellIdentity* of the first *PLMN-Identity* included in the           |
| *PLMN-IdentityInfoList* broadcasted in *SIB1* of the target cell i.e. |
| the cell the UE is trying to resume.                                  |
+-----------------------------------------------------------------------+
| ***source-c-RNTI***                                                   |
|                                                                       |
| Set to C-RNTI that the UE had in the PCell it was connected to prior  |
| to suspension of the RRC connection.                                  |
+-----------------------------------------------------------------------+
| ***sourcePhysCellId***                                                |
|                                                                       |
| Set to the physical cell identity of the PCell the UE was connected   |
| to prior to suspension of the RRC connection.                         |
+-----------------------------------------------------------------------+

#### -- *VarRLF-Report*

The UE variable *VarRLF-Report* includes the radio link failure
information or handover failure information.

*VarRLF-Report* UE variable

\-- ASN1START

\-- TAG-VARRLF-REPORT-START

VarRLF-Report-r16 ::= SEQUENCE {

rlf-Report-r16 RLF-Report-r16,

identityList-r18 CHOICE {

plmn-IdentityList-r18 PLMN-IdentityList2-r16,

snpn-IdentityList-r18 SEQUENCE (SIZE (1..maxNPN-r16)) OF
SNPN-Identity-r18

}

}

\-- TAG-VARRLF-REPORT-STOP

\-- ASN1STOP

#### -- *VarServingSecurityCellSetID*

The UE variable *VarServingSecurityCellSetID* includes the security cell
set ID of serving PSCell.

*VarServingSecurityCellSetID* UE variable

\-- ASN1START

\-- TAG-VARSERVINGSECURITYCELLSETID-START

VarServingSecurityCellSetID ::= SEQUENCE {

servingSecurityCellSetId-r18 INTEGER (1.. maxSecurityCellSet-r18)

}

\-- TAG-VARSERVINGSECURITYCELLSETID-STOP

\-- ASN1STOP

#### -- *VarShortMAC-Input*

The UE variable *VarShortMAC-Input* specifies the input used to generate
the *shortMAC-I* during RRC Connection Reestablishment procedure.

*VarShortMAC-Input* UE variable

\-- ASN1START

\-- TAG-VARSHORTMAC-INPUT-START

VarShortMAC-Input ::= SEQUENCE {

sourcePhysCellId PhysCellId,

targetCellIdentity CellIdentity,

source-c-RNTI RNTI-Value

}

\-- TAG-VARSHORTMAC-INPUT-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *VarShortMAC-Input* field descriptions                                |
+=======================================================================+
| ***targetCellIdentity***                                              |
|                                                                       |
| An input variable used to calculate the *shortMAC-I*. Set to the      |
| *cellIdentity* of the first *PLMN-Identity* in the                    |
| *PLMN-IdentityInfoList* broadcasted in *SIB1* of the target cell i.e. |
| the cell the UE is trying to reestablish the connection.              |
+-----------------------------------------------------------------------+
| ***source-c-RNTI***                                                   |
|                                                                       |
| Set to C-RNTI that the UE had in the PCell it was connected to prior  |
| to the reestablishment.                                               |
+-----------------------------------------------------------------------+
| ***sourcePhysCellId***                                                |
|                                                                       |
| Set to the physical cell identity of the PCell the UE was connected   |
| to prior to the reestablishment.                                      |
+-----------------------------------------------------------------------+

#### -- *VarSuccessHO-Report*

The UE variable *VarSuccessHO-Report* includes the successful handover
information.

*VarSuccessHO-Report* UE variable

\-- ASN1START

\-- TAG-VARSUCCESSHO-Report-START

VarSuccessHO-Report-r17 ::= SEQUENCE {

successHO-Report-r17 SuccessHO-Report-r17,

identityList-r18 CHOICE {

plmn-IdentityList-r18 PLMN-IdentityList2-r16,

snpn-IdentityList-r18 SEQUENCE (SIZE (1..maxNPN-r16)) OF
SNPN-Identity-r18

}

}

\-- TAG-VARSUCCESSHO-Report-STOP

\-- ASN1STOP

#### -- *VarSuccessPSCell-Report*

The UE variable *VarSuccessPSCell-Report* includes the successful PSCell
change or addition information.

*VarSuccessPSCell-Report* UE variable

\-- ASN1START

\-- TAG-VARSUCCESSPSCELL-Report-START

VarSuccessPSCell-Report-r18 ::= SEQUENCE {

successPSCell-Report-r18 SuccessPSCell-Report-r18,

identityList-r18 CHOICE {

plmn-IdentityList-r18 PLMN-IdentityList2-r16,

snpn-IdentityList-r18 SEQUENCE (SIZE (1..maxNPN-r16)) OF
SNPN-Identity-r18

}

}

\-- TAG-VARSUCCESSPSCELL-Report-STOP

\-- ASN1STOP

#### -- *VarTSS-Info*

The UE variable *VarTSS-Info* includes information about the current
value of *eventID-TSS* and the current value of the global gNB Identity.

*VarTSS-Info* UE variable

\-- ASN1START

\-- TAG-VARTSS-INFO-START

VarTSS-Info-r18 ::= SEQUENCE {

storedEventID-r18 INTEGER (0..63),

storedGlobalGnbID-r18 SEQUENCE {

plmn-Identity-r18 PLMN-Identity,

gnb-ID-r18 BIT STRING (SIZE (22..32))

}

}

\-- TAG-VARTSS-INFO-STOP

\-- ASN1STOP

#### -- End of *NR-UE-Variables*

\-- ASN1START

END

\-- ASN1STOP