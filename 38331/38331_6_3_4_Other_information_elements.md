### 6.3.4 Other information elements

#### -- *AbsoluteTimeInfo*

The IE *AbsoluteTimeInfo* indicates an absolute time in a format
YY-MM-DD HH:MM:SS and using BCD encoding. The first/ leftmost bit of the
bit string contains the most significant bit of the most significant
digit of the year and so on.

*AbsoluteTimeInfo* information element

\-- ASN1START

\-- TAG-ABSOLUTETIMEINFO-START

AbsoluteTimeInfo-r16 ::= BIT STRING (SIZE (48))

\-- TAG-ABSOLUTETIMEINFO-STOP

\-- ASN1STOP

#### -- *AppLayerIdleInactiveConfig*

The IE *AppLayerIdleInactiveConfig* indicates parameters specific to
application layer measurements applicable to RRC_IDLE and RRC_INACTIVE.
The configured application layer measurement is also applicable to
RRC_CONNECTED.

*AppLayerIdleInactiveConfig* information element

\-- ASN1START

\-- TAG-APPLAYERIDLEINACTIVECONFIG-START

AppLayerIdleInactiveConfig-r18 ::= SEQUENCE {

measConfigAppLayerId-r18 MeasConfigAppLayerId-r17,

serviceType-r18 ENUMERATED {streaming, mtsi, vr, spare5, spare4, spare3,
spare2, spare1} OPTIONAL, \-- Need M

appLayerMeasPriority-r18 INTEGER (1..16) OPTIONAL, \-- Need M

qoe-Reference-r18 OCTET STRING (SIZE (6)) OPTIONAL, \-- Need M

qoe-MeasurementType-r18 ENUMERATED {sbased, mbased} OPTIONAL, \-- Need M

qoe-AreaScope-r18 Qoe-AreaScope-r18 OPTIONAL, \-- Need M

mce-Id-r18 OCTET STRING (SIZE (1)) OPTIONAL, \-- Need M

availableRAN-VisibleMetrics-r18 AvailableRAN-VisibleMetrics-r18
OPTIONAL, \-- Need M

\...

}

Qoe-AreaScope-r18 ::= CHOICE {

cellGlobalIdList CellGlobalIdList-r16,

trackingAreaCodeList TrackingAreaCodeList-r16,

trackingAreaIdentityList TrackingAreaIdentityList-r16,

plmn-IdentityList PLMN-IdentityList2-r16,

\...

}

AvailableRAN-VisibleMetrics-r18 ::= SEQUENCE {

appLayerBufferLevelList-r18 ENUMERATED {true} OPTIONAL, \-- Need M

playoutDelayForMediaStartup-r18 ENUMERATED {true} OPTIONAL, \-- Need M

\...

}

\-- TAG-APPLAYERIDLEINACTIVECONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *AppLayerIdleInactiveConfig* field descriptions                       |
+=======================================================================+
| ***appLayerBufferLevelList***                                         |
|                                                                       |
| The field defines whether the buffer level for DASH streaming and VR  |
| service types can be collected as a RAN visible QoE metric from the   |
| UE.                                                                   |
+-----------------------------------------------------------------------+
| ***qoe-AreaScope***                                                   |
|                                                                       |
| The field contains the area where the application layer measurement   |
| shall start if an application layer session starts.                   |
+-----------------------------------------------------------------------+
| ***qoe-MeasurementType***                                             |
|                                                                       |
| Indicates whether the application layer measurement is signalling     |
| based or management based.                                            |
+-----------------------------------------------------------------------+
| ***qoe-Reference***                                                   |
|                                                                       |
| Indicates the QoE Reference as defined in TS 28.405 \[80\], clause    |
| 5.2.                                                                  |
+-----------------------------------------------------------------------+
| ***mce-id***                                                          |
|                                                                       |
| The field contains the Measurement Collection Entity ID.              |
+-----------------------------------------------------------------------+
| ***playoutDelayForMediaStartup***                                     |
|                                                                       |
| The field defines whether the playout delay for DASH streaming and VR |
| service types can be collected as a RAN visible QoE metric from the   |
| UE.                                                                   |
+-----------------------------------------------------------------------+

#### -- *AppLayerMeasConfig*

The IE *AppLayerMeasConfig* indicates configuration of application layer
measurements.

*AppLayerMeasConfig* information element

\-- ASN1START

\-- TAG-APPLAYERMEASCONFIG-START

AppLayerMeasConfig-r17 ::= SEQUENCE {

measConfigAppLayerToAddModList-r17 SEQUENCE (SIZE
(1..maxNrofAppLayerMeas-r17)) OF MeasConfigAppLayer-r17 OPTIONAL, \--
Need N

measConfigAppLayerToReleaseList-r17 SEQUENCE (SIZE
(1..maxNrofAppLayerMeas-r17)) OF MeasConfigAppLayerId-r17 OPTIONAL, \--
Need N

rrc-SegAllowedSRB4-r17 ENUMERATED {enabled} OPTIONAL, \-- Need R

\...,

\[\[

rrc-SegAllowedSRB5-r18 ENUMERATED {enabled} OPTIONAL, \-- Need R

idleInactiveReportAllowed-r18 ENUMERATED {enabled} OPTIONAL \-- Need R

\]\]

}

MeasConfigAppLayer-r17 ::= SEQUENCE {

measConfigAppLayerId-r17 MeasConfigAppLayerId-r17,

measConfigAppLayerContainer-r17 OCTET STRING (SIZE (1..8000)) OPTIONAL,
\-- Need N

serviceType-r17 ENUMERATED {streaming, mtsi, vr, spare5, spare4, spare3,
spare2, spare1} OPTIONAL, \-- Need M

pauseReporting-r17 BOOLEAN OPTIONAL, \-- Need M

transmissionOfSessionStartStop-r17 BOOLEAN OPTIONAL, \-- Need M

ran-VisibleParameters-r17 SetupRelease {RAN-VisibleParameters-r17}
OPTIONAL, \-- Cond ServiceType

\...,

\[\[

reportingSRB-r18 ENUMERATED {srb4, srb5} OPTIONAL, \-- Cond QoENRDC

appLayerMeasPriority-r18 INTEGER (1..16) OPTIONAL, \-- Need M

appLayerIdleInactiveConfig-r18 SetupRelease
{AppLayerIdleInactiveConfig-r18} OPTIONAL \-- Need M

\]\]

}

RAN-VisibleParameters-r17 ::= SEQUENCE {

ran-VisiblePeriodicity-r17 ENUMERATED {ms120, ms240, ms480, ms640,
ms1024} OPTIONAL, \-- Need S

numberOfBufferLevelEntries-r17 INTEGER (1..8) OPTIONAL, \-- Need R

reportPlayoutDelayForMediaStartup-r17 BOOLEAN OPTIONAL, \-- Need M

\...,

\[\[

ran-VisibleReportingSRB-r18 ENUMERATED {srb4, srb5} OPTIONAL \-- Cond
QoENRDC

\]\]

}

\-- TAG-APPLAYERMEASCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *AppLayerMeasConfig* field descriptions                               |
+=======================================================================+
| ***appLayerMeasPriority***                                            |
|                                                                       |
| The field indicates the priority of the application layer measurement |
| configuration, where a higher value indicates lower priority. If the  |
| field is not configured, the application layer measurement            |
| configuration has the lowest priority.                                |
+-----------------------------------------------------------------------+
| ***idleInactiveReportAllowed***                                       |
|                                                                       |
| The field indicates whether transmission of application layer         |
| measurement configurations and reports for application layer          |
| measurements applicable to RRC_IDLE and/or RRC_INACTIVE is allowed in |
| the cell where the field is received. If the field is not configured, |
| transmission of application layer measurement reports and             |
| configurations for RRC_IDLE/RRC_INACTIVE is not allowed.              |
+-----------------------------------------------------------------------+
| ***measConfigAppLayerContainer***                                     |
|                                                                       |
| The field contains configuration of application layer measurements,   |
| see Annex L (normative) in TS 26.247 \[68\], clause 16.5 in TS 26.114 |
| \[69\] and clause 9.4 in TS 26.118 \[70\].                            |
+-----------------------------------------------------------------------+
| ***measConfigAppLayerId***                                            |
|                                                                       |
| The field contains the identity of the application layer              |
| measurements. When application layer measurements are configured for  |
| an SCG, the *measConfigAppLayerId* is obtained according to TS 38.423 |
| \[37\], clauses 8.3.1 and 8.3.3.                                      |
+-----------------------------------------------------------------------+
| ***pauseReporting***                                                  |
|                                                                       |
| The field indicates whether the transmission of                       |
| *measReportAppLayerContainer* is paused or not. Value *true*          |
| indicates the transmission of *measReportAppLayerContainer* is        |
| paused; value *false* indicates the transmission of                   |
| *measReportAppLayerContainer* is not paused.                          |
+-----------------------------------------------------------------------+
| ***ran-VisibleParameters***                                           |
|                                                                       |
| The field indicates whether RAN visible application layer             |
| measurements shall be reported or not.                                |
+-----------------------------------------------------------------------+
| ***ran-VisibleReportingSRB***                                         |
|                                                                       |
| The field indicates the SRB to be used for transmission of RAN        |
| visible application layer measurement reports.                        |
+-----------------------------------------------------------------------+
| ***reportingSRB***                                                    |
|                                                                       |
| The field indicates the SRB to be used for transmission of            |
| encapsulated application layer measurement reports.                   |
+-----------------------------------------------------------------------+
| ***rrc-SegAllowedSRB4***                                              |
|                                                                       |
| This field indicates that RRC segmentation of                         |
| *MeasurementReportAppLayer* is enabled on SRB4. The field is only     |
| configured for an MCG. It may be present only if the UE supports RRC  |
| segmentation of the *MeasurementReportAppLayer* message***.***        |
+-----------------------------------------------------------------------+
| ***rrc-SegAllowedSRB5***                                              |
|                                                                       |
| This field indicates that RRC segmentation of                         |
| *MeasurementReportAppLayer* is enabled on SRB5. The field is only     |
| configured for an SCG. It may be present only if the UE supports RRC  |
| segmentation of the *MeasurementReportAppLayer* message***.***        |
+-----------------------------------------------------------------------+
| ***serviceType***                                                     |
|                                                                       |
| Indicates the type of application layer measurement. Value            |
| *streaming* indicates Quality of Experience Measurement Collection    |
| for streaming services (see TS 26.247 \[68\]), value *mtsi* indicates |
| Quality of Experience Measurement Collection for MTSI (see TS 26.114  |
| \[69\]) and value *vr* indicates Quality of Experience Measurement    |
| Collection for VR service (see TS 26.118 \[70\]). The network always  |
| configures *serviceType* when application layer measurements are      |
| initially configured and at *fullConfig*.                             |
+-----------------------------------------------------------------------+
| ***transmissionOfSessionStartStop***                                  |
|                                                                       |
| Value *true* indicates that the UE shall transmit indications when    |
| the measurement session in the application layer starts and stops.    |
| Value *false* indicates that the UE shall not transmit any session    |
| status indications. The UE transmits a session start indication upon  |
| configuration of this field set to value *true* if a session already  |
| has started in the application layer.                                 |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *RAN-VisibleParameters* field descriptions                            |
+=======================================================================+
| ***numberOfBufferLevelEntries***                                      |
|                                                                       |
| The field contains the maximum number of buffer level entries that    |
| can be reported for RAN visible application layer measurements. This  |
| field is also used by application layer to calculate the interval of  |
| RAN visible buffer level measurement, which is equal to the           |
| periodicity of RAN visible application layer measurements reporting   |
| divided by *numberOfBufferLevelEntries*.                              |
+-----------------------------------------------------------------------+
| ***ran-VisiblePeriodicity***                                          |
|                                                                       |
| The field indicates the periodicity of RAN visible application layer  |
| measurements reporting. Value *ms120* indicates 120 ms, value *ms240* |
| indicates 240 ms and so on. If this field is absent, the periodicity  |
| of RAN visible application layer measurements reporting is the same   |
| as the reporting periodicity indicated in                             |
| *measConfigAppLayerContainer.*                                        |
+-----------------------------------------------------------------------+
| ***reportPlayoutDelayForMediaStartup***                               |
|                                                                       |
| The field indicates whether the UE shall report Playout Delay for     |
| Media Startup for RAN visible application layer measurements.         |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional       Explanation
  Presence          
  ----------------- -----------------------------------------------------
  *QoENRDC*         This field is optionally present, Need M, when QoE
                    for an NR-DC configuration is configured, i.e. when
                    either QoE for an SCG is configured or when SRB5 is
                    configured. Otherwise, it is absent.

  *ServiceType*     This field is optionally present, Need M, when
                    *serviceType* is set to *streaming* or *vr*.
                    Otherwise, it is absent.
  -----------------------------------------------------------------------

#### -- *AreaConfiguration*

The *AreaConfiguration* indicates area for which UE is requested to
perform measurement logging. If not configured, measurement logging is
not restricted to specific cells or tracking areas but applies as long
as the RPLMN is contained in *plmn-IdentityList* stored in
*VarLogMeasReport* or the registered SNPN identity is included in
*snpn-ConfigID-List* stored in *VarLogMeasReport*.

*AreaConfiguration* information element

\-- ASN1START

\-- TAG-AREACONFIGURATION-START

AreaConfiguration-r16 ::= SEQUENCE {

areaConfig-r16 AreaConfig-r16,

interFreqTargetList-r16 SEQUENCE(SIZE (1..maxFreq)) OF
InterFreqTargetInfo-r16 OPTIONAL \-- Need R

}

AreaConfiguration-r17 ::= SEQUENCE {

areaConfig-r17 AreaConfig-r16 OPTIONAL, \-- Need R

interFreqTargetList-r17 SEQUENCE(SIZE (1..maxFreq)) OF
InterFreqTargetInfo-r16 OPTIONAL \-- Need R

}

AreaConfiguration-v1800 ::= CHOICE {

cag-ConfigList-r18 CAG-ConfigList-r18,

snpn-ConfigList-r18 SNPN-ConfigList-r18

}

AreaConfig-r16 ::= CHOICE {

cellGlobalIdList-r16 CellGlobalIdList-r16,

trackingAreaCodeList-r16 TrackingAreaCodeList-r16,

trackingAreaIdentityList-r16 TrackingAreaIdentityList-r16

}

InterFreqTargetInfo-r16 ::= SEQUENCE {

dl-CarrierFreq-r16 ARFCN-ValueNR,

cellList-r16 SEQUENCE (SIZE (1..32)) OF PhysCellId OPTIONAL \-- Need R

}

CellGlobalIdList-r16 ::= SEQUENCE (SIZE (1..32)) OF CGI-Info-Logging-r16

TrackingAreaCodeList-r16 ::= SEQUENCE (SIZE (1..8)) OF TrackingAreaCode

TrackingAreaIdentityList-r16 ::= SEQUENCE (SIZE (1..8)) OF
TrackingAreaIdentity-r16

TrackingAreaIdentity-r16 ::= SEQUENCE {

plmn-Identity-r16 PLMN-Identity,

trackingAreaCode-r16 TrackingAreaCode

}

CAG-ConfigList-r18 ::= SEQUENCE (SIZE (1..maxNPN-r16)) OF CAG-Config-r18

CAG-Config-r18 ::= SEQUENCE {

plmn-Identity-r18 PLMN-Identity,

cag-IdentityList-r18 SEQUENCE (SIZE (1..maxNPN-r16)) OF BIT STRING (SIZE
(32))

}

SNPN-ConfigList-r18 ::= CHOICE {

snpn-ConfigCellIdList-r18 SNPN-ConfigCellIdList-r18,

snpn-ConfigTAI-List-r18 SNPN-ConfigTAI-List-r18,

snpn-ConfigID-List-r18 SNPN-ConfigID-List-r18

}

SNPN-ConfigCellIdList-r18 ::= SEQUENCE (SIZE
(1..maxSNPN-ConfigCellId-r18)) OF SNPN-ConfigCellId-r18

SNPN-ConfigCellId-r18 ::= SEQUENCE {

cgi-Identity-r18 CGI-Info-Logging-r16,

nid-IdentityList-r18 SEQUENCE (SIZE (1..maxNPN-r16)) OF NID-r16

}

SNPN-ConfigTAI-List-r18 ::= SEQUENCE (SIZE (1..maxSNPN-ConfigTAI-r18))
OF SNPN-ConfigTAI-r18

SNPN-ConfigTAI-r18 ::= SEQUENCE {

tai-Identity-r18 TrackingAreaIdentity-r16,

nid-IdentityList-r18 SEQUENCE (SIZE (1..maxNPN-r16)) OF NID-r16

}

SNPN-ConfigID-List-r18 ::= SEQUENCE (SIZE (1..maxSNPN-ConfigID-r18)) OF
SNPN-ConfigID-r18

SNPN-ConfigID-r18 ::= SEQUENCE {

plmn-Identity-r18 PLMN-Identity,

nid-IdentityList-r18 SEQUENCE (SIZE (1..maxNPN-r16)) OF NID-r16

}

\-- TAG-AREACONFIGURATION-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *AreaConfiguration* field descriptions                                |
+=======================================================================+
| ***cag-IdentityList***                                                |
|                                                                       |
| The *cag-IdentityList* contains one or more CAG IDs. A PLMN ID may be |
| present more than once within *CAG-ConfigList.*                       |
+-----------------------------------------------------------------------+
| ***InterFreqTargetInfo***                                             |
|                                                                       |
| If configured, it indicates the neighbouring frequency and cells for  |
| which UE is requested to perform measurement logging. It can include  |
| sync raster or non-sync raster frequencies.                           |
+-----------------------------------------------------------------------+
| ***nid-IdentityList***                                                |
|                                                                       |
| The *nid-IdentityList* contains one or more NID. All NIDs associated  |
| to the same PLMN ID are listed in the same *nid-IdentityList* entry.  |
+-----------------------------------------------------------------------+

#### -- *BT-NameList*

The IE *BT-NameList* is used to indicate the names of the Bluetooth
beacon which the UE is configured to measure.

*BT-NameList* information element

\-- ASN1START

\-- TAG-BTNAMELIST-START

BT-NameList-r16 ::= SEQUENCE (SIZE (1..maxBT-Name-r16)) OF BT-Name-r16

BT-Name-r16 ::= OCTET STRING (SIZE (1..248))

\-- TAG-BTNAMELIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *BT-NameList* field descriptions                                      |
+=======================================================================+
| ***bt-Name***                                                         |
|                                                                       |
| If configured, the UE only performs Bluetooth measurements according  |
| to the names identified. For each name, it refers to LOCAL NAME       |
| defined in Bluetooth specification \[51\].                            |
+-----------------------------------------------------------------------+

#### -- *DedicatedInfoF1c*

The IE *DedicatedInfoF1c* is used to transfer IAB-DU specific F1-C
related information between the network and the IAB node. The carried
information consists of F1AP message encapsulated in SCTP/IP or F1-C
related (SCTP)/IP packet, see TS 38.472 \[64\]. The RRC layer is
transparent for this information.

*DedicatedInfoF1c* information element

\-- ASN1START

\-- TAG-DEDICATEDINFOF1C-START

DedicatedInfoF1c-r17 ::= OCTET STRING

\-- TAG-DEDICATEDINFOF1C-STOP

\-- ASN1STOP

#### -- *EUTRA-AllowedMeasBandwidth*

The IE *EUTRA-AllowedMeasBandwidth* is used to indicate the maximum
allowed measurement bandwidth on a carrier frequency as defined by the
parameter Transmission Bandwidth Configuration \"N~RB~\" in TS 36.104
\[33\]. The values *mbw6*, *mbw15*, *mbw25*, *mbw50*, *mbw75*, *mbw100*
indicate 6, 15, 25, 50, 75 and 100 resource blocks, respectively.

*EUTRA-AllowedMeasBandwidth* information element

\-- ASN1START

\-- TAG-EUTRA-ALLOWEDMEASBANDWIDTH-START

EUTRA-AllowedMeasBandwidth ::= ENUMERATED {mbw6, mbw15, mbw25, mbw50,
mbw75, mbw100}

\-- TAG-EUTRA-ALLOWEDMEASBANDWIDTH-STOP

\-- ASN1STOP

#### -- *EUTRA-MBSFN-SubframeConfigList*

The IE *EUTRA-MBSFN-SubframeConfigList* is used to define an E-UTRA
MBSFN subframe pattern (for the purpose of NR rate matching).

*EUTRA-MBSFN-SubframeConfigList* information element

\-- ASN1START

\-- TAG-EUTRA-MBSFN-SUBFRAMECONFIGLIST-START

EUTRA-MBSFN-SubframeConfigList ::= SEQUENCE (SIZE
(1..maxMBSFN-Allocations)) OF EUTRA-MBSFN-SubframeConfig

EUTRA-MBSFN-SubframeConfig ::= SEQUENCE {

radioframeAllocationPeriod ENUMERATED {n1, n2, n4, n8, n16, n32},

radioframeAllocationOffset INTEGER (0..7),

subframeAllocation1 CHOICE {

oneFrame BIT STRING (SIZE(6)),

fourFrames BIT STRING (SIZE(24))

},

subframeAllocation2 CHOICE {

oneFrame BIT STRING (SIZE(2)),

fourFrames BIT STRING (SIZE(8))

} OPTIONAL, \-- Need R

\...

}

\-- TAG-EUTRA-MBSFN-SUBFRAMECONFIGLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *EUTRA-MBSFN-SubframeConfig* field descriptions                       |
+=======================================================================+
| ***radioframeAllocationOffset***                                      |
|                                                                       |
| Field as defined in *MBSFN-SubframeConfig* in TS 36.331 \[10\].       |
+-----------------------------------------------------------------------+
| ***radioframeAllocationPeriod***                                      |
|                                                                       |
| Field as defined in *MBSFN-SubframeConfig* in TS 36.331 \[10\], where |
| *SFN* refers to the SFN of the NR serving cell.                       |
+-----------------------------------------------------------------------+
| ***subframeAllocation1***                                             |
|                                                                       |
| Field as defined in *MBSFN-SubframeConfig* in TS 36.331 \[10\], where |
| the UE assumes the duplex mode (FDD or TDD) of the NR cell for which  |
| the *E-UTRA-MBSFN-SubframeConfig* is provided.                        |
+-----------------------------------------------------------------------+
| ***subframeAllocation2***                                             |
|                                                                       |
| Field as defined in *MBSFN-SubframeConfig-v1430* in TS 36.331 \[10\], |
| where the UE assumes the duplex mode (FDD or TDD) of the NR cell for  |
| which the *E-UTRA-MBSFN-SubframeConfig* is provided.                  |
+-----------------------------------------------------------------------+

#### -- *EUTRA-MultiBandInfoList*

The IE *EUTRA-MultiBandInfoList* indicates the list of frequency bands
in addition to the band represented by *CarrierFreq* for which cell
reselection parameters are common, and a list of *additionalPmax* and
*additionalSpectrumEmission*.

*EUTRA-MultiBandInfoList* information element

\-- ASN1START

\-- TAG-EUTRA-MULTIBANDINFOLIST-START

EUTRA-MultiBandInfoList ::= SEQUENCE (SIZE (1..maxMultiBands)) OF
EUTRA-MultiBandInfo

EUTRA-MultiBandInfo ::= SEQUENCE {

eutra-FreqBandIndicator FreqBandIndicatorEUTRA,

eutra-NS-PmaxList EUTRA-NS-PmaxList OPTIONAL \-- Need R

}

\-- TAG-EUTRA-MULTIBANDINFOLIST-STOP

\-- ASN1STOP

#### -- *EUTRA-MultiBandInfoListAerial*

The IE *EUTRA-MultiBandInfoListAerial* indicates the list of frequency
bands for aerial UE in addition to the band represented by *CarrierFreq*
for which cell reselection parameters are common, and a list of
*additionalPmax* and *additionalSpectrumEmission*.

*EUTRA-MultiBandInfoListAerial* information element

\-- ASN1START

\-- TAG-EUTRA-MULTIBANDINFOLISTAERIAL-START

EUTRA-MultiBandInfoListAerial-r18 ::= SEQUENCE (SIZE (1..maxMultiBands))
OF EUTRA-MultiBandInfoAerial-r18

EUTRA-MultiBandInfoAerial-r18 ::= SEQUENCE {

eutra-FreqBandIndicator-r18 FreqBandIndicatorEUTRA,

eutra-NS-PmaxListAerial-r18 EUTRA-NS-PmaxList OPTIONAL \-- Need R

}

\-- TAG-EUTRA-MULTIBANDINFOLISTAERIAL-STOP

\-- ASN1STOP

#### -- *EUTRA-NS-PmaxList*

The IE *EUTRA-NS-PmaxList* concerns a list of *additionalPmax* and
*additionalSpectrumEmission*, as defined in TS 36.101 \[22\], clause 6,
for a given frequency band.

*EUTRA-NS-PmaxList* information element

\-- ASN1START

\-- TAG-EUTRA-NS-PMAXLIST-START

EUTRA-NS-PmaxList ::= SEQUENCE (SIZE (1..maxEUTRA-NS-Pmax)) OF
EUTRA-NS-PmaxValue

EUTRA-NS-PmaxValue ::= SEQUENCE {

additionalPmax INTEGER (-30..33) OPTIONAL, \-- Need R

additionalSpectrumEmission INTEGER (1..288) OPTIONAL \-- Need R

}

\-- TAG-EUTRA-NS-PMAXLIST-STOP

\-- ASN1STOP

#### -- *EUTRA-PhysCellId*

The IE *EUTRA-PhysCellId* is used to indicate the physical layer
identity of the cell, as defined in TS 36.211 \[31\].

*EUTRA-PhysCellId* information element

\-- ASN1START

\-- TAG-EUTRA-PHYSCELLID-START

EUTRA-PhysCellId ::= INTEGER (0..503)

\-- TAG-EUTRA-PHYSCELLID-STOP

\-- ASN1STOP

#### -- *EUTRA-PhysCellIdRange*

The IE *EUTRA-PhysCellIdRange* is used to encode either a single or a
range of physical cell identities. The range is encoded by using a
*start* value and by indicating the number of consecutive physical cell
identities (including *start*) in the range. For fields comprising
multiple occurrences of *EUTRA-PhysCellIdRange*, NW may configure
overlapping ranges of physical cell identities.

*EUTRA-PhysCellIdRange* information element

\-- ASN1START

\-- TAG-EUTRA-PHYSCELLIDRANGE-START

EUTRA-PhysCellIdRange ::= SEQUENCE {

start EUTRA-PhysCellId,

range ENUMERATED {n4, n8, n12, n16, n24, n32, n48, n64, n84, n96,

n128, n168, n252, n504, spare2, spare1} OPTIONAL \-- Need N

}

\-- TAG-EUTRA-PHYSCELLIDRANGE-STOP

\-- ASN1STOP

#### -- *EUTRA-PresenceAntennaPort1*

The IE *EUTRA-PresenceAntennaPort1* is used to indicate whether all the
neighbouring cells use Antenna Port 1. When set to *true*, the UE may
assume that at least two cell-specific antenna ports are used in all
neighbouring cells.

*EUTRA-PresenceAntennaPort1* information element

\-- ASN1START

\-- TAG-EUTRA-PRESENCEANTENNAPORT1-START

EUTRA-PresenceAntennaPort1 ::= BOOLEAN

\-- TAG-EUTRA-PRESENCEANTENNAPORT1-STOP

\-- ASN1STOP

#### -- *EUTRA-Q-OffsetRange*

The IE *EUTRA-Q-OffsetRange* is used to indicate a cell, or frequency
specific offset to be applied when evaluating triggering conditions for
measurement reporting. The value in dB. Value *dB-24* corresponds to -24
dB, value *dB-22* corresponds to -22 dB and so on.

*EUTRA-Q-OffsetRange* information element

\-- ASN1START

\-- TAG-EUTRA-Q-OFFSETRANGE-START

EUTRA-Q-OffsetRange ::= ENUMERATED {

dB-24, dB-22, dB-20, dB-18, dB-16, dB-14,

dB-12, dB-10, dB-8, dB-6, dB-5, dB-4, dB-3,

dB-2, dB-1, dB0, dB1, dB2, dB3, dB4, dB5,

dB6, dB8, dB10, dB12, dB14, dB16, dB18,

dB20, dB22, dB24}

\-- TAG-EUTRA-Q-OFFSETRANGE-STOP

\-- ASN1STOP

#### -- *IAB-IP-Address*

The IE *IAB-IP-Address* is used to indicate the IP address/prefix.

*IAB-IP-Address* information element

\-- ASN1START

\-- TAG-IABIPADDRESS-START

IAB-IP-Address-r16 ::= CHOICE {

iPv4-Address-r16 BIT STRING (SIZE(32)),

iPv6-Address-r16 BIT STRING (SIZE(128)),

iPv6-Prefix-r16 BIT STRING (SIZE(64)),

\...

}

\-- TAG-IABIPADDRESS-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *IAB-IP-Address* field descriptions                                   |
+=======================================================================+
| ***iPv4-Address***                                                    |
|                                                                       |
| This field is used to provide the allocated IPv4 address.             |
+-----------------------------------------------------------------------+
| ***iPv6-Address***                                                    |
|                                                                       |
| This field is used to provide the allocated IPv6 address.             |
+-----------------------------------------------------------------------+
| ***iPv6-Prefix***                                                     |
|                                                                       |
| This field is used to provide the allocated IPv6 prefix.              |
+-----------------------------------------------------------------------+

#### -- *IAB-IP-AddressIndex*

The IE *IAB-IP-AddressIndex* is used to identify a configuration of an
IP address.

*IAB-IP-AddressIndex* information element

\-- ASN1START

\-- TAG-IABIPADDRESSINDEX-START

IAB-IP-AddressIndex-r16 ::= INTEGER (1..maxIAB-IP-Address-r16)

\-- TAG-IABIPADDRESSINDEX-STOP

\-- ASN1STOP

#### -- *IAB-IP-Usage*

The IE *IAB-IP-Usage* is used to indicate the usage of the assigned IP
address/prefix.

*IAB-IP-Usage* information element

\-- ASN1START

\-- TAG-IAB-IP-USAGE-START

IAB-IP-Usage-r16 ::= ENUMERATED {f1-C, f1-U, non-F1, spare}

\-- TAG-IAB-IP-USAGE-STOP

\-- ASN1STOP

#### -- *LoggingDuration*

The *LoggingDuration* indicates the duration for which UE is requested
to perform measurement logging. Value min10 corresponds to 10 minutes,
value min20 corresponds to 20 minutes and so on.

*LoggingDuration* information element

\-- ASN1START

\-- TAG-LOGGINGDURATION-START

LoggingDuration-r16 ::= ENUMERATED {

min10, min20, min40, min60, min90, min120, spare2, spare1}

\-- TAG-LOGGINGDURATION-STOP

\-- ASN1STOP

#### -- *LoggingInterval*

The *LoggingInterval* indicates the periodicity for logging measurement
results. Value ms1280 corresponds to 1.28s, value ms2560 corresponds to
2.56s and so on. Value infinity means it is equal to the configured
value of the *LoggingDuration* IE.

*LoggingInterval* information element

\-- ASN1START

\-- TAG-LOGGINGINTERVAL-START

LoggingInterval-r16 ::= ENUMERATED {

ms320, ms640, ms1280, ms2560, ms5120, ms10240, ms20480,

ms30720, ms40960, ms61440 , infinity}

\-- TAG-LOGGINGINTERVAL-STOP

\-- ASN1STOP

#### -- *LogMeasResultListBT*

The IE *LogMeasResultListBT* covers measured results for Bluetooth.

*LogMeasResultListBT* information element

\-- ASN1START

\-- TAG-LOGMEASRESULTLISTBT-START

LogMeasResultListBT-r16 ::= SEQUENCE (SIZE (1..maxBT-IdReport-r16)) OF
LogMeasResultBT-r16

LogMeasResultBT-r16 ::= SEQUENCE {

bt-Addr-r16 BIT STRING (SIZE (48)),

rssi-BT-r16 INTEGER (-128..127) OPTIONAL,

\...

}

\-- TAG-LOGMEASRESULTLISTBT-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *LogMeasResultListBT* field descriptions                              |
+=======================================================================+
| ***bt-Addr***                                                         |
|                                                                       |
| This field indicates the Bluetooth public address of the Bluetooth    |
| beacon as defined in TS 37.355 \[49\].                                |
+-----------------------------------------------------------------------+
| ***rssi-BT***                                                         |
|                                                                       |
| This field provides the beacon received signal strength indicator     |
| (RSSI) in dBm as defined in TS 37.355 \[49\].                         |
+-----------------------------------------------------------------------+

#### -- *LogMeasResultListWLAN*

The IE *LogMeasResultListWLAN* covers measured results for WLAN.

*LogMeasResultListWLAN* information element

\-- ASN1START

\-- TAG-LOGMEASRESULTLISTWLAN-START

LogMeasResultListWLAN-r16 ::= SEQUENCE (SIZE (1..maxWLAN-Id-Report-r16))
OF LogMeasResultWLAN-r16

LogMeasResultWLAN-r16 ::= SEQUENCE {

wlan-Identifiers-r16 WLAN-Identifiers-r16,

rssiWLAN-r16 WLAN-RSSI-Range-r16 OPTIONAL,

rtt-WLAN-r16 WLAN-RTT-r16 OPTIONAL,

\...

}

WLAN-Identifiers-r16 ::= SEQUENCE {

ssid-r16 OCTET STRING (SIZE (1..32)) OPTIONAL,

bssid-r16 OCTET STRING (SIZE (6)) OPTIONAL,

hessid-r16 OCTET STRING (SIZE (6)) OPTIONAL,

\...

}

WLAN-RSSI-Range-r16 ::= INTEGER(0..141)

WLAN-RTT-r16 ::= SEQUENCE {

rttValue-r16 INTEGER (0..16777215),

rttUnits-r16 ENUMERATED {

microseconds,

hundredsofnanoseconds,

tensofnanoseconds,

nanoseconds,

tenthsofnanoseconds,

\...},

rttAccuracy-r16 INTEGER (0..255) OPTIONAL,

\...

}

\-- TAG-LOGMEASRESULTLISTWLAN-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *LogMeasResultListWLAN* field descriptions                            |
+=======================================================================+
| ***bssid***                                                           |
|                                                                       |
| Basic Service Set Identifier (BSSID) defined in IEEE 802.11-2012      |
| \[50\].                                                               |
+-----------------------------------------------------------------------+
| ***hessid***                                                          |
|                                                                       |
| Homogenous Extended Service Set Identifier (HESSID) defined in IEEE   |
| 802.11-2012 \[50\].                                                   |
+-----------------------------------------------------------------------+
| ***rssiWLAN***                                                        |
|                                                                       |
| Measured WLAN RSSI result in dBm. The IE WLAN-RSSI-Range specifies    |
| the value range used in WLAN RSSI measurements and thresholds.        |
| Integer value for WLAN RSSI measurements is according to mapping      |
| table in TS 36.133 \[40\]. Value 0 corresponds to --infinity, value 1 |
| to -100dBm, value 2 to -99dBm, and so on (i.e. in steps of 1dBm)      |
| until value 140, which corresponds to 39dBm, while value 141          |
| corresponds to +infinity.                                             |
+-----------------------------------------------------------------------+
| ***rtt-WLAN***                                                        |
|                                                                       |
| This field provides the measured roundtrip time between the target    |
| device and WLAN AP and optionally the accuracy expressed as the       |
| standard deviation of the delay. Units for each of these are 1000ns,  |
| 100ns, 10ns, 1ns, and 0.1ns as defined in TS 37.355 \[49\].           |
+-----------------------------------------------------------------------+
| ***rttValue***                                                        |
|                                                                       |
| This field specifies the Round Trip Time (RTT) measurement between    |
| the target device and WLAN AP in units given by the field rttUnits as |
| defined in TS 37.355 \[49\].                                          |
+-----------------------------------------------------------------------+
| ***rttUnits***                                                        |
|                                                                       |
| This field specifies the Units for the fields rttValue and            |
| rttAccuracy. The available Units are 1000ns, 100ns, 10ns, 1ns, and    |
| 0.1ns as defined in TS 37.355 \[49\].                                 |
+-----------------------------------------------------------------------+
| ***rttAccuracy***                                                     |
|                                                                       |
| This field provides the estimated accuracy of the provided rttValue   |
| expressed as the standard deviation in units given by the field       |
| rttUnits as defined in TS 37.355 \[49\].                              |
+-----------------------------------------------------------------------+
| ***ssid***                                                            |
|                                                                       |
| Service Set Identifier (SSID) defined in IEEE 802.11-2012 \[50\].     |
+-----------------------------------------------------------------------+
| ***wlan-Identifiers***                                                |
|                                                                       |
| Indicates the WLAN parameters used for identification of the WLAN for |
| which the measurement results are applicable.                         |
+-----------------------------------------------------------------------+

#### -- *MeasConfigAppLayerId*

The IE *MeasConfigAppLayerId* identifies the application layer
measurement.

*MeasConfigAppLayerId* information element

\-- ASN1START

\-- TAG-MEASCONFIGAPPLAYERID-START

MeasConfigAppLayerId-r17 ::= INTEGER (0..maxNrofAppLayerMeas-1-r17)

\-- TAG-MEASCONFIGAPPLAYERID-STOP

\-- ASN1STOP

#### -- *OtherConfig*

The IE *OtherConfig* contains configuration related to miscellaneous
other configurations.

*OtherConfig* information element

\-- ASN1START

\-- TAG-OTHERCONFIG-START

OtherConfig ::= SEQUENCE {

delayBudgetReportingConfig CHOICE{

release NULL,

setup SEQUENCE{

delayBudgetReportingProhibitTimer ENUMERATED {s0, s0dot4, s0dot8,
s1dot6, s3, s6, s12, s30}

}

} OPTIONAL \-- Need M

}

OtherConfig-v1540 ::= SEQUENCE {

overheatingAssistanceConfig SetupRelease {OverheatingAssistanceConfig}
OPTIONAL, \-- Need M

\...

}

OtherConfig-v1610 ::= SEQUENCE {

idc-AssistanceConfig-r16 SetupRelease {IDC-AssistanceConfig-r16}
OPTIONAL, \-- Need M

drx-PreferenceConfig-r16 SetupRelease {DRX-PreferenceConfig-r16}
OPTIONAL, \-- Need M

maxBW-PreferenceConfig-r16 SetupRelease {MaxBW-PreferenceConfig-r16}
OPTIONAL, \-- Need M

maxCC-PreferenceConfig-r16 SetupRelease {MaxCC-PreferenceConfig-r16}
OPTIONAL, \-- Need M

maxMIMO-LayerPreferenceConfig-r16 SetupRelease
{MaxMIMO-LayerPreferenceConfig-r16} OPTIONAL, \-- Need M

minSchedulingOffsetPreferenceConfig-r16 SetupRelease
{MinSchedulingOffsetPreferenceConfig-r16} OPTIONAL, \-- Need M

releasePreferenceConfig-r16 SetupRelease {ReleasePreferenceConfig-r16}
OPTIONAL, \-- Need M

referenceTimePreferenceReporting-r16 ENUMERATED {true} OPTIONAL, \--
Need R

btNameList-r16 SetupRelease {BT-NameList-r16} OPTIONAL, \-- Need M

wlanNameList-r16 SetupRelease {WLAN-NameList-r16} OPTIONAL, \-- Need M

sensorNameList-r16 SetupRelease {Sensor-NameList-r16} OPTIONAL, \-- Need
M

obtainCommonLocation-r16 ENUMERATED {true} OPTIONAL, \-- Need R

sl-AssistanceConfigNR-r16 ENUMERATED{true} OPTIONAL \-- Need R

}

OtherConfig-v1700 ::= SEQUENCE {

ul-GapFR2-PreferenceConfig-r17 ENUMERATED {true} OPTIONAL, \-- Need R

musim-GapAssistanceConfig-r17 SetupRelease
{MUSIM-GapAssistanceConfig-r17} OPTIONAL, \-- Need M

musim-LeaveAssistanceConfig-r17 SetupRelease
{MUSIM-LeaveAssistanceConfig-r17} OPTIONAL, \-- Need M

successHO-Config-r17 SetupRelease {SuccessHO-Config-r17} OPTIONAL, \--
Need M

maxBW-PreferenceConfigFR2-2-r17 ENUMERATED {true} OPTIONAL, \-- Cond
maxBW

maxMIMO-LayerPreferenceConfigFR2-2-r17 ENUMERATED {true} OPTIONAL, \--
Cond maxMIMO

minSchedulingOffsetPreferenceConfigExt-r17 ENUMERATED {true} OPTIONAL,
\-- Cond minOffset

rlm-RelaxationReportingConfig-r17 SetupRelease
{RLM-RelaxationReportingConfig-r17} OPTIONAL, \-- Need M

bfd-RelaxationReportingConfig-r17 SetupRelease
{BFD-RelaxationReportingConfig-r17} OPTIONAL, \-- Need M

scg-DeactivationPreferenceConfig-r17 SetupRelease
{SCG-DeactivationPreferenceConfig-r17} OPTIONAL, \-- Cond SCG

rrm-MeasRelaxationReportingConfig-r17 SetupRelease
{RRM-MeasRelaxationReportingConfig-r17} OPTIONAL, \-- Need M

propDelayDiffReportConfig-r17 SetupRelease
{PropDelayDiffReportConfig-r17} OPTIONAL \-- Need M

}

OtherConfig-v1800 ::= SEQUENCE {

idc-AssistanceConfig-v1800 SetupRelease {IDC-AssistanceConfig-v1800}
OPTIONAL, \-- Need M

multiRx-PreferenceReportingConfigFR2-r18 SetupRelease
{MultiRx-PreferenceReportingConfigFR2-r18} OPTIONAL, \-- Need M

aerial-FlightPathAvailabilityConfig-r18 ENUMERATED {true} OPTIONAL, \--
Need R

ul-TrafficInfoReportingConfig-r18 SetupRelease
{UL-TrafficInfoReportingConfig-r18} OPTIONAL, \-- Need M

n3c-RelayUE-InfoReportConfig-r18 ENUMERATED {true} OPTIONAL, \-- Need R

successPSCell-Config-r18 SetupRelease {SuccessPSCell-Config-r18}
OPTIONAL, \-- Need M

sn-InitiatedPSCellChange-r18 ENUMERATED {true} OPTIONAL, \-- Need R

musim-GapPriorityAssistanceConfig-r18 ENUMERATED {true} OPTIONAL, \--
Cond musimGapConfig

musim-CapabilityRestrictionConfig-r18 SetupRelease
{MUSIM-CapabilityRestrictionConfig-r18} OPTIONAL \-- Need M

}

OtherConfig-v1830 ::= SEQUENCE {

sl-PRS-AssistanceConfigNR-r18 ENUMERATED{true} OPTIONAL \-- Need R

}

IDC-AssistanceConfig-v1800 ::= SEQUENCE {

idc-FDM-AssistanceConfig-r18 SetupRelease {IDC-FDM-AssistanceConfig-r18}
OPTIONAL, \-- Need M

idc-TDM-AssistanceConfig-r18 ENUMERATED {setup} OPTIONAL \-- Cond FDM

}

MultiRx-PreferenceReportingConfigFR2-r18 ::= SEQUENCE {

multiRx-PreferenceReportingConfigFR2ProhibitTimer-r18 ENUMERATED {

s0, s0dot5, s1, s2, s3, s4, s5, s6, s7,

s8, s9, s10, s20, s30, spare2, spare1}

}

CandidateServingFreqListNR-r16 ::= SEQUENCE (SIZE (1..maxFreqIDC-r16))
OF ARFCN-ValueNR

MUSIM-GapAssistanceConfig-r17 ::= SEQUENCE {

musim-GapProhibitTimer-r17 ENUMERATED {s0, s0dot1, s0dot2, s0dot3,
s0dot4, s0dot5, s1, s2, s3, s4, s5, s6, s7, s8, s9, s10}

}

MUSIM-LeaveAssistanceConfig-r17 ::= SEQUENCE {

musim-LeaveWithoutResponseTimer-r17 ENUMERATED {ms10, ms20, ms40, ms60,
ms80, ms100, spare2, spare1}

}

MUSIM-CapabilityRestrictionConfig-r18 ::= SEQUENCE {

musim-CandidateBandList-r18 MUSIM-CandidateBandList-r18 OPTIONAL, \--
Need R

musim-WaitTimer-r18 ENUMERATED {ms10, ms20, ms40, ms60, ms80, ms100,
spare2, spare1},

musim-ProhibitTimer-r18 ENUMERATED {s0, s0dot1, s0dot2, s0dot3, s0dot4,
s0dot5, s1, s2, s3, s4, s5, s6, s7, s8,

s9, s10}

}

MUSIM-CandidateBandList-r18::= SEQUENCE (SIZE
(1..maxCandidateBandIndex-r18)) OF FreqBandIndicatorNR

SuccessHO-Config-r17 ::= SEQUENCE {

thresholdPercentageT304-r17 ENUMERATED {p40, p60, p80, spare5, spare4,
spare3, spare2, spare1} OPTIONAL, \--Need R

thresholdPercentageT310-r17 ENUMERATED {p40, p60, p80, spare5, spare4,
spare3, spare2, spare1} OPTIONAL, \--Need R

thresholdPercentageT312-r17 ENUMERATED {p20, p40, p60, p80, spare4,
spare3, spare2, spare1} OPTIONAL, \--Need R

sourceDAPS-FailureReporting-r17 ENUMERATED {true} OPTIONAL, \--Need R

\...

}

SuccessPSCell-Config-r18 ::= SEQUENCE {

thresholdPercentageT304-SCG-r18 ENUMERATED {p40, p60, p80, spare5,
spare4, spare3, spare2, spare1} OPTIONAL, \--Need R

thresholdPercentageT310-SCG-r18 ENUMERATED {p40, p60, p80, spare5,
spare4, spare3, spare2, spare1} OPTIONAL, \--Need R

thresholdPercentageT312-SCG-r18 ENUMERATED {p20, p40, p60, p80, spare4,
spare3, spare2, spare1} OPTIONAL, \--Need R

\...

}

OverheatingAssistanceConfig ::= SEQUENCE {

overheatingIndicationProhibitTimer ENUMERATED {s0, s0dot5, s1, s2, s5,
s10, s20, s30,

s60, s90, s120, s300, s600, spare3, spare2, spare1}

}

IDC-AssistanceConfig-r16 ::= SEQUENCE {

candidateServingFreqListNR-r16 CandidateServingFreqListNR-r16 OPTIONAL,
\-- Need R

\...

}

DRX-PreferenceConfig-r16 ::= SEQUENCE {

drx-PreferenceProhibitTimer-r16 ENUMERATED {

s0, s0dot5, s1, s2, s3, s4, s5, s6, s7,

s8, s9, s10, s20, s30, spare2, spare1}

}

MaxBW-PreferenceConfig-r16 ::= SEQUENCE {

maxBW-PreferenceProhibitTimer-r16 ENUMERATED {

s0, s0dot5, s1, s2, s3, s4, s5, s6, s7,

s8, s9, s10, s20, s30, spare2, spare1}

}

MaxCC-PreferenceConfig-r16 ::= SEQUENCE {

maxCC-PreferenceProhibitTimer-r16 ENUMERATED {

s0, s0dot5, s1, s2, s3, s4, s5, s6, s7,

s8, s9, s10, s20, s30, spare2, spare1}

}

MaxMIMO-LayerPreferenceConfig-r16 ::= SEQUENCE {

maxMIMO-LayerPreferenceProhibitTimer-r16 ENUMERATED {

s0, s0dot5, s1, s2, s3, s4, s5, s6, s7,

s8, s9, s10, s20, s30, spare2, spare1}

}

MinSchedulingOffsetPreferenceConfig-r16 ::= SEQUENCE {

minSchedulingOffsetPreferenceProhibitTimer-r16 ENUMERATED {

s0, s0dot5, s1, s2, s3, s4, s5, s6, s7,

s8, s9, s10, s20, s30, spare2, spare1}

}

ReleasePreferenceConfig-r16 ::= SEQUENCE {

releasePreferenceProhibitTimer-r16 ENUMERATED {

s0, s0dot5, s1, s2, s3, s4, s5, s6, s7,

s8, s9, s10, s20, s30, infinity, spare1},

connectedReporting ENUMERATED {true} OPTIONAL \-- Need R

}

RLM-RelaxationReportingConfig-r17 ::= SEQUENCE {

rlm-RelaxtionReportingProhibitTimer ENUMERATED {s0, s0dot5, s1, s2, s5,
s10, s20, s30,

s60, s90, s120, s300, s600, infinity, spare2, spare1}

}

BFD-RelaxationReportingConfig-r17 ::= SEQUENCE {

bfd-RelaxtionReportingProhibitTimer ENUMERATED {s0, s0dot5, s1, s2, s5,
s10, s20, s30,

s60, s90, s120, s300, s600, infinity, spare2, spare1}

}

SCG-DeactivationPreferenceConfig-r17 ::= SEQUENCE {

scg-DeactivationPreferenceProhibitTimer-r17 ENUMERATED {

s0, s1, s2, s4, s8, s10, s15, s30,

s60, s120, s180, s240, s300, s600, s900, s1800}

}

RRM-MeasRelaxationReportingConfig-r17 ::= SEQUENCE {

s-SearchDeltaP-Stationary-r17 ENUMERATED {dB2, dB3, dB6, dB9, dB12,
dB15, spare2, spare1},

t-SearchDeltaP-Stationary-r17 ENUMERATED {s5, s10, s20, s30, s60, s120,
s180, s240, s300, spare7, spare6, spare5,

spare4, spare3, spare2, spare1}

}

PropDelayDiffReportConfig-r17 ::= SEQUENCE {

threshPropDelayDiff-r17 ENUMERATED {ms0dot5, ms1, ms2, ms3, ms4, ms5,
ms6 ,ms7, ms8, ms9, ms10, spare5,

spare4, spare3, spare2, spare1} OPTIONAL, \-- Need M

neighCellInfoList-r17 SEQUENCE (SIZE (1..maxCellNTN-r17)) OF
NeighbourCellInfo-r17 OPTIONAL \-- Need M

}

NeighbourCellInfo-r17 ::= SEQUENCE {

epochTime-r17 EpochTime-r17,

ephemerisInfo-r17 EphemerisInfo-r17

}

IDC-FDM-AssistanceConfig-r18 ::= SEQUENCE {

candidateServingFreqRangeListNR-r18 CandidateServingFreqRangeListNR-r18
OPTIONAL, \-- Need R

\...

}

CandidateServingFreqRangeListNR-r18 ::= SEQUENCE (SIZE
(1..maxFreqIDC-r16)) OF CandidateServingFreqRangeNR-r18

CandidateServingFreqRangeNR-r18 ::= SEQUENCE {

candidateCenterFreq-r18 ARFCN-ValueNR,

candidateBandwidth-r18 ENUMERATED {khz200, khz400, khz600, khz800, mhz1,
mhz2, mhz3, mhz4, mhz5,

mhz6, mhz8, mhz10, mhz20, mhz30, mhz40, mhz50, mhz60, mhz80, mhz100,

mhz200, mhz300, mhz400} OPTIONAL \-- Need R

}

UL-TrafficInfoReportingConfig-r18 ::= SEQUENCE {

pdu-SessionsToReportUL-TrafficInfoList-r18 SEQUENCE (SIZE (1..
maxNrofPDU-Sessions-r17)) OF PDU-SessionToReportUL-TrafficInfo-r18,

ul-TrafficInfoProhibitTimer-r18 ENUMERATED {s0, s0dot5, s1, s2, s5, s10,
s20, s30,

s60, s90, s120, s300, s600, spare3, spare2, spare1}

}

PDU-SessionToReportUL-TrafficInfo-r18 ::= SEQUENCE {

pdu-SessionID-r18 PDU-SessionID,

qfi-ToReportUL-TrafficInfoList-r18 SEQUENCE (SIZE (1..maxNrofQFIs)) OF
QFI

}

\-- TAG-OTHERCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *OtherConfig* field descriptions                                      |
+-----------------------------------------------------------------------+
| ***aerial-FlightPathAvailabilityConfig***                             |
|                                                                       |
| Configuration for the UE to indicate the availability of flight path  |
| information for Aerial UE operation.                                  |
+-----------------------------------------------------------------------+
| ***bfd-RelaxationReportingConfig***                                   |
|                                                                       |
| Configuration for the UE to report the relaxation state of BFD        |
| measurements.                                                         |
+-----------------------------------------------------------------------+
| ***btNameList***                                                      |
|                                                                       |
| Configuration for the UE to report measurements from specific         |
| Bluetooth beacons. NG-RAN configures the field if *includeBT-Meas* is |
| configured for one or more measurements.                              |
+-----------------------------------------------------------------------+
| ***candidateBandwidth***                                              |
|                                                                       |
| Indicates the bandwidth of the candidate frequency range around the   |
| center frequency.                                                     |
+-----------------------------------------------------------------------+
| ***candidateCenterFreq***                                             |
|                                                                       |
| Indicates the center frequency of the candidate frequency range.      |
+-----------------------------------------------------------------------+
| ***candidateServingFreqListNR***                                      |
|                                                                       |
| Indicates for each candidate NR serving cells, the center frequency   |
| around which UE is requested to report IDC issues.                    |
+-----------------------------------------------------------------------+
| ***candidateServingFreqRangeListNR***                                 |
|                                                                       |
| Indicates the candidate frequency range with the combination of the   |
| center frequency and the candidate bandwidth, around which the UE is  |
| requested to report IDC issues.                                       |
+-----------------------------------------------------------------------+
| ***connectedReporting***                                              |
|                                                                       |
| Indicates that the UE can report a preference to remain in            |
| RRC_CONNECTED state following a report to leave RRC_CONNECTED state.  |
| If absent, the UE cannot report a preference to stay in RRC_CONNECTED |
| state.                                                                |
+-----------------------------------------------------------------------+
| ***delayBudgetReportingProhibitTimer***                               |
|                                                                       |
| Prohibit timer for delay budget reporting. Value in seconds. Value    |
| *s0* means prohibit timer is set to 0 seconds, value *s0dot4* means   |
| prohibit timer is set to 0.4 seconds, and so on.                      |
+-----------------------------------------------------------------------+
| ***drx-PreferenceConfig***                                            |
|                                                                       |
| Configuration for the UE to report assistance information to inform   |
| the gNB about the UE\'s DRX preferences for power saving.             |
+-----------------------------------------------------------------------+
| ***drx-PreferenceProhibitTimer***                                     |
|                                                                       |
| Prohibit timer for DRX preferences assistance information reporting.  |
| Value in seconds. Value *s0* means prohibit timer is set to 0         |
| seconds, value *s0dot5* means prohibit timer is set to 0.5 seconds,   |
| value *s1* means prohibit timer is set to 1 second and so on.         |
+-----------------------------------------------------------------------+
| ***idc-AssistanceConfig***                                            |
|                                                                       |
| Configuration for the UE to report assistance information to inform   |
| the gNB about UE detected IDC problem.                                |
+-----------------------------------------------------------------------+
| ***maxBW-PreferenceConfig***                                          |
|                                                                       |
| Configuration for the UE to report assistance information to inform   |
| the gNB about the UE\'s preferred bandwidth for power saving.         |
+-----------------------------------------------------------------------+
| ***maxBW-PreferenceProhibitTimer***                                   |
|                                                                       |
| Prohibit timer for preferred bandwidth assistance information         |
| reporting. Value in seconds. Value *s0* means prohibit timer is set   |
| to 0 seconds, value *s0dot5* means prohibit timer is set to 0.5       |
| seconds, value *s1* means prohibit timer is set to 1 second and so    |
| on.                                                                   |
+-----------------------------------------------------------------------+
| ***maxCC-PreferenceConfig***                                          |
|                                                                       |
| Configuration for the UE to report assistance information to inform   |
| the gNB about the UE\'s preferred number of carriers for power        |
| saving.                                                               |
+-----------------------------------------------------------------------+
| ***maxBW-PreferenceConfigFR2-2***                                     |
|                                                                       |
| Configuration for the UE to report assistance information to inform   |
| the gNB about the UE\'s preferred bandwidth for power saving for      |
| FR2-2.                                                                |
+-----------------------------------------------------------------------+
| ***maxCC-PreferenceProhibitTimer***                                   |
|                                                                       |
| Prohibit timer for preferred number of carriers assistance            |
| information reporting. Value in seconds. Value *s0* means prohibit    |
| timer is set to 0 seconds, value *s0dot5* means prohibit timer is set |
| to 0.5 seconds, value *s1* means prohibit timer is set to 1 second    |
| and so on.                                                            |
+-----------------------------------------------------------------------+
| ***maxMIMO-LayerPreferenceConfig***                                   |
|                                                                       |
| Configuration for the UE to report assistance information to inform   |
| the gNB about the UE\'s preferred number of MIMO layers for power     |
| saving.                                                               |
+-----------------------------------------------------------------------+
| ***maxMIMO-LayerPreferenceConfigFR2-2***                              |
|                                                                       |
| Configuration for the UE to report assistance information to inform   |
| the gNB about the UE\'s preferred number of MIMO layers for power     |
| saving for FR2-2.                                                     |
+-----------------------------------------------------------------------+
| ***maxMIMO-LayerPreferenceProhibitTimer***                            |
|                                                                       |
| Prohibit timer for preferred number of number of MIMO layers          |
| assistance information reporting. Value in seconds. Value *s0* means  |
| prohibit timer is set to 0 seconds, value *s0dot5* means prohibit     |
| timer is set to 0.5 seconds, value *s1* means prohibit timer is set   |
| to 1 second and so on.                                                |
+-----------------------------------------------------------------------+
| ***minSchedulingOffsetPreferenceConfig***                             |
|                                                                       |
| Configuration for the UE to report assistance information to inform   |
| the gNB about the UE\'s preferred *minimumSchedulingOffset* value for |
| cross-slot scheduling for power saving.                               |
+-----------------------------------------------------------------------+
| ***minSchedulingOffsetPreferenceConfigExt***                          |
|                                                                       |
| Configuration for the UE to report assistance information to inform   |
| the gNB about the UE\'s preferred *minimumSchedulingOffset* value for |
| cross-slot scheduling for power saving for SCS 480 kHz and/or 960     |
| kHz.                                                                  |
+-----------------------------------------------------------------------+
| ***minSchedulingOffsetPreferenceProhibitTimer***                      |
|                                                                       |
| Prohibit timer for preferred *minimumSchedulingOffset* assistance     |
| information reporting. Value in seconds. Value *s0* means prohibit    |
| timer is set to 0 seconds, value *s0dot5* means prohibit timer is set |
| to 0.5 seconds, value *s1* means prohibit timer is set to 1 second    |
| and so on.                                                            |
+-----------------------------------------------------------------------+
| ***multiRx-PreferenceReportingConfigFR2***                            |
|                                                                       |
| Configuration for the UE to report assistance information to inform   |
| gNB about the UE\'s preference on multi-Rx operation for FR2.         |
+-----------------------------------------------------------------------+
| ***multiRx-PreferenceReportingConfigFR2ProhibitTimer***               |
|                                                                       |
| Prohibit timer for multi-Rx operation preference reporting for FR2.   |
| Value in seconds. Value *s0* means prohibit timer is set to 0         |
| seconds, value *s0dot5* means prohibit timer is set to 0.5 seconds,   |
| value *s1* means prohibit timer is set to 1 second and so on.         |
+-----------------------------------------------------------------------+
| ***musim-CandidateBandList***                                         |
|                                                                       |
| A list of candidate bands that the network intends to use, e.g., for  |
| serving cells and for which the UE is requested to provide            |
| information on temporary restricted capabilities for MUSIM operation  |
| as specified in clause 5.7.4.3.                                       |
+-----------------------------------------------------------------------+
| ***musim-GapAssistanceConfig***                                       |
|                                                                       |
| Configuration for the UE to report assistance information for gap     |
| preference.                                                           |
+-----------------------------------------------------------------------+
| ***musim-GapPriorityAssistanceConfig***                               |
|                                                                       |
| Indicates the UE is allowed to provide MUSIM assistance information   |
| for gap(s) priority and/or MUSIM gaps keep preference.                |
+-----------------------------------------------------------------------+
| ***musim-GapProhibitTimer***                                          |
|                                                                       |
| Prohibit timer for MUSIM assistance information reporting for gap     |
| preference.                                                           |
+-----------------------------------------------------------------------+
| ***musim-LeaveAssistanceConfig***                                     |
|                                                                       |
| Configuration for the UE to report assistance information for leaving |
| RRC_CONNECTED for MUSIM purpose.                                      |
+-----------------------------------------------------------------------+
| ***musim-LeaveWithoutResponseTimer***                                 |
|                                                                       |
| Indicates the timer for the UE to enter RRC_IDLE for MUSIM purpose as |
| defined in clause 5.3.8.6.                                            |
+-----------------------------------------------------------------------+
| ***musim-ProhibitTimer***                                             |
|                                                                       |
| Indicates the prohibit timer for UE temporary restricted capabilities |
| for MUSIM operation. Value in milliseconds. Value *ms0* means         |
| prohibit timer is set to 0 milliseconds, value *ms10* means prohibit  |
| timer is set to 10 milliseconds and so on.                            |
+-----------------------------------------------------------------------+
| ***musim-WaitTimer***                                                 |
|                                                                       |
| Indicates the wait timer for UE temporary restricted capabilities for |
| MUSIM operation. Value in milliseconds. Value *ms10* means wait timer |
| is set to 10 milliseconds, value *ms20* means wait timer is set to 20 |
| milliseconds and so on.                                               |
+-----------------------------------------------------------------------+
| ***obtainCommonLocation***                                            |
|                                                                       |
| Requests the UE to attempt to have detailed location information      |
| available using GNSS. NR configures the field if                      |
| *includeCommonLocationInfo* is configured for one or more             |
| measurements.                                                         |
+-----------------------------------------------------------------------+
| ***overheatingAssistanceConfig***                                     |
|                                                                       |
| Configuration for the UE to report assistance information to inform   |
| the gNB about UE detected internal overheating.                       |
+-----------------------------------------------------------------------+
| ***overheatingIndicationProhibitTimer***                              |
|                                                                       |
| Prohibit timer for overheating assistance information reporting.      |
| Value in seconds. Value *s0* means prohibit timer is set to 0         |
| seconds, value *s0dot5* means prohibit timer is set to 0.5 seconds,   |
| value *s1* means prohibit timer is set to 1 second and so on.         |
+-----------------------------------------------------------------------+
| ***pdu-SessionsToReportUL-TrafficInfoList***                          |
|                                                                       |
| A list of PDU sessions for which the UE shall report UL traffic       |
| information.                                                          |
+-----------------------------------------------------------------------+
| ***propDelayDiffReportConfig***                                       |
|                                                                       |
| Configuration for the UE to report service link propagation delay     |
| difference between serving cell and neighbour cell(s).                |
+-----------------------------------------------------------------------+
| ***qfi-ToReportUL-TrafficInfoList***                                  |
|                                                                       |
| A list of QFIs of a PDU session for which the UE shall report UL      |
| traffic information.                                                  |
+-----------------------------------------------------------------------+
| ***referenceTimePreferenceReporting***                                |
|                                                                       |
| If present, the field indicates the UE is configured to provide       |
| reference time assistance information.                                |
+-----------------------------------------------------------------------+
| ***releasePreferenceConfig***                                         |
|                                                                       |
| Configuration for the UE to report assistance information to inform   |
| the gNB about the UE\'s preference to leave RRC_CONNECTED state.      |
+-----------------------------------------------------------------------+
| ***rlm-RelaxationReportingConfig***                                   |
|                                                                       |
| Configuration for the UE to report the relaxation state of RLM        |
| measurements.                                                         |
+-----------------------------------------------------------------------+
| ***releasePreferenceProhibitTimer***                                  |
|                                                                       |
| Prohibit timer for release preference assistance information          |
| reporting. Value in seconds. Value *s0* means prohibit timer is set   |
| to 0 seconds, value *s0dot5* means prohibit timer is set to 0.5       |
| seconds, value *s1* means prohibit timer is set to 1 second and so    |
| on. Value *infinity* means that once a UE has reported a release      |
| preference, the UE cannot report a release preference again during    |
| the RRC connection.                                                   |
+-----------------------------------------------------------------------+
| ***s-SearchDeltaP-Stationary***                                       |
|                                                                       |
| Parameter \"S~SearchDeltaP-StationaryConnected~\" in 5.7.4.4. Value   |
| dB2 corresponds to 2 dB, dB3 corresponds to 3 dB and so on.           |
+-----------------------------------------------------------------------+
| ***scg-DeactivationPreferenceConfig***                                |
|                                                                       |
| Configuration of the UE to indicate its preference for SCG            |
| deactivation.                                                         |
+-----------------------------------------------------------------------+
| ***scg -StatePreferenceProhibitTimer***                               |
|                                                                       |
| Prohibit timer for UE indication of its preference for SCG            |
| deactivation. Value in seconds. Value *s0* means prohibit timer is    |
| set to 0 seconds, value *s1* means prohibit timer is set to 1 second  |
| and so on.                                                            |
+-----------------------------------------------------------------------+
| ***sensorNameList***                                                  |
|                                                                       |
| Configuration for the UE to report measurements from specific         |
| sensors. NG-RAN configures the field if *includeSensor-Meas* is       |
| configured for one or more measurements.                              |
+-----------------------------------------------------------------------+
| ***sl-AssistanceConfigNR***                                           |
|                                                                       |
| Indicate whether UE is configured to provide configured grant         |
| assistance information for NR sidelink communication.                 |
+-----------------------------------------------------------------------+
| ***sl-PRS-AssistanceConfigNR***                                       |
|                                                                       |
| Indicate whether UE is configured to provide configured grant         |
| assistance information for NR sidelink positioning.                   |
+-----------------------------------------------------------------------+
| ***sn-InitiatedPSCellChange***                                        |
|                                                                       |
| This field indicates whether the PSCell change procedure or the CPC   |
| included in the *RRCReconfiguration* message is SN initiated or not.  |
| In case of SN initiated inter-SN PSCell change procedure or SN        |
| configured inter-SN CPC, MN includes this field in the MCG RRC        |
| Reconfiguration message. In case of intra-SN PSCell change, or        |
| intra-SN CPC, source SN includes the field in the SCG RRC             |
| Reconfiguration.                                                      |
+-----------------------------------------------------------------------+
| ***sourceDAPS-FailureReporting***                                     |
|                                                                       |
| This field indicates whether the UE shall generate the SHR upon       |
| successfully completing the DAPS handover to the target cell and if a |
| radio link failure was experienced in the source PCell while          |
| executing the DAPS handover. This field is set in the *otherConfig*   |
| configured by the source cell of the DAPS handover.                   |
+-----------------------------------------------------------------------+
| ***successHO-Config***                                                |
|                                                                       |
| Configuration for the UE to report the successful handover            |
| information to the network.                                           |
+-----------------------------------------------------------------------+
| ***successPSCell-Config***                                            |
|                                                                       |
| Configuration for the UE to report the successful PSCell change or    |
| addition information to the network. When this field is configured in |
| CG-Config, the *thresholdPercentageT304-SCG* is absent.               |
+-----------------------------------------------------------------------+
| ***t-SearchDeltaP-Stationary***                                       |
|                                                                       |
| Parameter \"T~SearchDeltaP-StationaryConnected~\" in 5.7.4.4. Value   |
| in seconds. Value s5 means 5 seconds, value s10 means 10 seconds and  |
| so on.                                                                |
+-----------------------------------------------------------------------+
| ***thresholdPercentageT304***                                         |
|                                                                       |
| This field indicates the threshold for the ratio in percentage        |
| between the elapsed T304 timer and the configured value of the T304   |
| timer. Value *p40* corresponds to 40%, value *p60* corresponds to 60% |
| and so on. This field is set in the *otherConfig* configured by the   |
| target cell of the handover.                                          |
+-----------------------------------------------------------------------+
| ***thresholdPercentageT310***                                         |
|                                                                       |
| This field indicates the threshold for the ratio in percentage        |
| between the elapsed T310 timer and the configured value of the T310   |
| timer. Value *p40* corresponds to 40%, value *p60* corresponds to 60% |
| and so on. This field is set in the *otherConfig* configured by the   |
| source cell of the handover.                                          |
+-----------------------------------------------------------------------+
| ***thresholdPercentageT312***                                         |
|                                                                       |
| This field indicates the threshold for the ratio in percentage        |
| between the elapsed T312 timer and the configured value(s) of the     |
| T312 timer. Value *p20* corresponds to 20%, value *p40* corresponds   |
| to 40% and so on. This field is set in the *otherConfig* configured   |
| by the source cell of the handover.                                   |
+-----------------------------------------------------------------------+
| ***thresholdPercentageT304-SCG***                                     |
|                                                                       |
| This field indicates the threshold for the ratio in percentage        |
| between the elapsed T304 timer associated to the target PSCell and    |
| the configured value of the T304 timer. Value *p40* corresponds to    |
| 40%, value *p60* corresponds to 60% and so on. This field is set in   |
| the *otherConfig* configured by the target PSCell of the PSCell       |
| change or addition.                                                   |
+-----------------------------------------------------------------------+
| ***thresholdPercentageT310-SCG***                                     |
|                                                                       |
| This field indicates the threshold for the ratio in percentage        |
| between the elapsed T310 timer associated to the source PSCell and    |
| the configured value of the T310 timer. Value *p40* corresponds to    |
| 40%, value *p60* corresponds to 60% and so on. This field is set in   |
| the *otherConfig* configured by the source PSCell of the PSCell       |
| change or CPC, or in the *otherConfig* configured by the PCell for    |
| the PSCell change or CPC. This field is not configured at the time of |
| PSCell change via SRB3.                                               |
+-----------------------------------------------------------------------+
| ***thresholdPercentageT312-SCG***                                     |
|                                                                       |
| This field indicates the threshold for the ratio in percentage        |
| between the elapsed T312 timer associated to the measurement identity |
| of the target PSCell and the configured value of the T312 timer.      |
| Value *p20* corresponds to 20%, value *p40* corresponds to 40% and so |
| on. This field is set in the *otherConfig* configured by the source   |
| PSCell of the PSCell change or CPC, or in the *otherConfig*           |
| configured by the PCell for the PSCell change or CPC. This field is   |
| not configured at the time of PSCell change via SRB3.                 |
+-----------------------------------------------------------------------+
| ***threshPropDelayDiff***                                             |
|                                                                       |
| Threshold for one-way service link propagation delay difference       |
| report as specified in 5.7.4.2.                                       |
+-----------------------------------------------------------------------+
| ***ul-GapFR2-PreferenceConfig***                                      |
|                                                                       |
| Indicates whether UE is configured to request for FR2 UL gap          |
| activation/deactivation and preferred FR2 UL gap pattern.             |
+-----------------------------------------------------------------------+
| ***wlanNameList***                                                    |
|                                                                       |
| Configuration for the UE to report measurements from specific WLAN    |
| APs. NG-RAN configures the field if *includeWLAN-Meas* is configured  |
| for one or more measurements.                                         |
+-----------------------------------------------------------------------+
| ***ul-TrafficInfoProhibitTimer***                                     |
|                                                                       |
| Prohibit timer for UL traffic information reporting. Value in         |
| seconds. Value *s0* means prohibit timer is set to 0 seconds, value   |
| *s0dot5* means prohibit timer is set to 0.5 seconds, value *s1* means |
| prohibit timer is set to 1 second and so on.                          |
+-----------------------------------------------------------------------+
| ***ul-TrafficInfoReportingConfig***                                   |
|                                                                       |
| Configuration for the UE to report UL traffic information.            |
+=======================================================================+

  ------------------------------------------------------------------------
  Conditional        Explanation
  Presence           
  ------------------ -----------------------------------------------------
  *FDM*              This field is optionally present, need R, if
                     *idc-AssistanceConfig-r16* or
                     *idc-FDM-AssistanceConfig* is setup. Otherwise, it is
                     absent, need R.

  *maxBW*            This field is optionally present, need R, if
                     *maxBW-PreferenceConfig-r16* is setup; otherwise it
                     is absent, need R.

  *maxMIMO*          This field is optionally present, need R, if
                     *maxMIMO-LayerPreferenceConfig-r16* is setup;
                     otherwise it is absent, need R.

  *minOffset*        This field is optionally present, need R, if
                     *minSchedulingOffsetPreferenceConfig-r16* is setup;
                     otherwise it is absent, need R.

  *musimGapConfig*   This field is optionally present, need R, if
                     *musim-GapAssistanceConfig-r17* is setup; otherwise
                     it is absent, need R.

  *SCG*              This field is optionally present, need M, in an
                     *RRCReconfiguration* message not within
                     *mrdc-SecondaryCellGroup* and received, either via
                     SRB3 within *DLInformationTransferMRDC* or via SRB1.
                     Otherwise, it is absent.
  ------------------------------------------------------------------------

#### -- *PhysCellIdUTRA-FDD*

The IE *PhysCellIdUTRA-FDD* is used to indicate the physical layer
identity of the cell, i.e. the primary scrambling code, as defined in TS
25.331 \[45\].

*PhysCellIdUTRA-FDD* information element

\-- ASN1START

\-- TAG-PHYSCELLIDUTRA-FDD-START

PhysCellIdUTRA-FDD-r16 ::= INTEGER (0..511)

\-- TAG-PHYSCELLIDUTRA-FDD-STOP

\-- ASN1STOP

#### -- *RRC-TransactionIdentifier*

The IE *RRC-TransactionIdentifier* is used, together with the message
type, for the identification of an RRC procedure (transaction).

*RRC-TransactionIdentifier* information element

\-- ASN1START

\-- TAG-RRC-TRANSACTIONIDENTIFIER-START

RRC-TransactionIdentifier ::= INTEGER (0..3)

\-- TAG-RRC-TRANSACTIONIDENTIFIER-STOP

\-- ASN1STOP

#### -- *Sensor-NameList*

The IE *Sensor-NameList* is used to indicate the names of the sensors
which the UE is configured to measure.

*Sensor-NameList* information element

\-- ASN1START

\-- TAG-SENSORNAMELIST-START

Sensor-NameList-r16 ::= SEQUENCE {

measUncomBarPre-r16 ENUMERATED {true} OPTIONAL, \-- Need R

measUeSpeed ENUMERATED {true} OPTIONAL, \-- Need R

measUeOrientation ENUMERATED {true} OPTIONAL \-- Need R

}

\-- TAG-SENSORNAMELIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *Sensor-NameList* field descriptions                                  |
+=======================================================================+
| ***measUncomBarPre***                                                 |
|                                                                       |
| If configured, the UE reports the uncompensated Barometric pressure   |
| measurement as defined in TS 37.355 \[49\].                           |
+-----------------------------------------------------------------------+
| ***measUeSpeed***                                                     |
|                                                                       |
| If configured, the UE reports the UE speed measurement as defined in  |
| TS 37.355 \[49\].                                                     |
+-----------------------------------------------------------------------+
| ***measUeOrientation***                                               |
|                                                                       |
| If configured, the UE reports the UE orientation information as       |
| defined in TS 37.355 \[49\].                                          |
+-----------------------------------------------------------------------+

#### -- *TraceReference*

The *TraceReference* contains parameter Trace Reference as defined in TS
32.422 \[52\].

*TraceReference* information element

\-- ASN1START

\-- TAG-TRACEREFERENCE-START

TraceReference-r16 ::= SEQUENCE {

plmn-Identity-r16 PLMN-Identity,

traceId-r16 OCTET STRING (SIZE (3))

}

\-- TAG-TRACEREFERENCE-STOP

\-- ASN1STOP

#### -- *UE-MeasurementsAvailable*

The IE *UE-MeasurementsAvailable* is used to indicate all relevant
available indicators for UE measurements.

*UE-MeasurementsAvailable* information element

\-- ASN1START

\-- TAG-UE-MeasurementsAvailable-START

UE-MeasurementsAvailable-r16 ::= SEQUENCE {

logMeasAvailable-r16 ENUMERATED {true} OPTIONAL,

logMeasAvailableBT-r16 ENUMERATED {true} OPTIONAL,

logMeasAvailableWLAN-r16 ENUMERATED {true} OPTIONAL,

connEstFailInfoAvailable-r16 ENUMERATED {true} OPTIONAL,

rlf-InfoAvailable-r16 ENUMERATED {true} OPTIONAL,

\...,

\[\[

successHO-InfoAvailable-r17 ENUMERATED {true} OPTIONAL,

sigLogMeasConfigAvailable-r17 BOOLEAN OPTIONAL

\]\],

\[\[

successPSCell-InfoAvailable-r18 ENUMERATED {true} OPTIONAL

\]\]

}

\-- TAG-UE-MeasurementsAvailable-STOP

\-- ASN1STOP

#### -- *UTRA-FDD-Q-OffsetRange*

The IE *UTRA-FDD-Q-OffsetRange* is used to indicate a frequency specific
offset to be applied when evaluating triggering conditions for
measurement reporting. The value is in dB. Value *dB-24* corresponds to
-24 dB, value *dB-22* corresponds to -22 dB and so on.

*UTRA-FDD-Q-OffsetRange* information element

\-- ASN1START

\-- TAG-UTRA-FDD-Q-OFFSETRANGE-START

UTRA-FDD-Q-OffsetRange-r16 ::= ENUMERATED {

dB-24, dB-22, dB-20, dB-18, dB-16, dB-14,

dB-12, dB-10, dB-8, dB-6, dB-5, dB-4, dB-3,

dB-2, dB-1, dB0, dB1, dB2, dB3, dB4, dB5,

dB6, dB8, dB10, dB12, dB14, dB16, dB18,

dB20, dB22, dB24}

\-- TAG-UTRA-FDD-Q-OFFSETRANGE-STOP

\-- ASN1STOP

#### -- *VisitedCellInfoList*

The IE *VisitedCellInfoList* includes the mobility history information
of maximum of 16 most recently visited primary cells or time spent in
any cell selection state and/or camped on any cell state in NR or E-UTRA
and, in case of Dual Connectivity, the mobility history information of
*maxPSCellHistory* most recently visited primary secondary cell group
cells across all the primary cells included in the
*VisitedCellInfoList*. The most recently visited cell is stored first in
the list. The list includes cells visited in RRC_IDLE, RRC_INACTIVE and
RRC_CONNECTED states for NR and RRC_IDLE and RRC_CONNECTED for E-UTRA.

*VisitedCellInfoList* information element

\-- ASN1START

\-- TAG-VISITEDCELLINFOLIST-START

VisitedCellInfoList-r16 ::= SEQUENCE (SIZE (1..maxCellHistory-r16)) OF
VisitedCellInfo-r16

VisitedCellInfo-r16 ::= SEQUENCE {

visitedCellId-r16 CHOICE {

nr-CellId-r16 CHOICE {

cgi-Info CGI-Info-Logging-r16,

pci-arfcn-r16 PCI-ARFCN-NR-r16

},

eutra-CellId-r16 CHOICE {

cellGlobalId-r16 CGI-InfoEUTRA,

pci-arfcn-r16 PCI-ARFCN-EUTRA-r16

}

} OPTIONAL,

timeSpent-r16 INTEGER (0..4095),

\...,

\[\[

visitedPSCellInfoListReport-r17 VisitedPSCellInfoList-r17 OPTIONAL

\]\]

}

VisitedPSCellInfoList-r17 ::= SEQUENCE (SIZE (1..maxPSCellHistory-r17))
OF VisitedPSCellInfo-r17

VisitedPSCellInfo-r17 ::= SEQUENCE {

visitedCellId-r17 CHOICE {

nr-CellId-r17 CHOICE {

cgi-Info-r17 CGI-Info-Logging-r16,

pci-arfcn-r17 PCI-ARFCN-NR-r16

},

eutra-CellId-r17 CHOICE {

cellGlobalId-r17 CGI-InfoEUTRALogging,

pci-arfcn-r17 PCI-ARFCN-EUTRA-r16

}

} OPTIONAL,

timeSpent-r17 INTEGER (0..4095),

\...

}

\-- TAG-VISITEDCELLINFOLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *VisitedCellInfoList* field descriptions                              |
+=======================================================================+
| ***timeSpent***                                                       |
|                                                                       |
| This field indicates the duration of stay in the cell or in any cell  |
| selection state and/or camped on any cell state in NR or E-UTRA       |
| approximated to the closest second. If included in                    |
| *VisitedPSCellInfo*, it indicates the duration of stay in the PSCell  |
| or without any PSCell. If the duration of stay exceeds 4095s, the UE  |
| shall set it to 4095s.                                                |
+-----------------------------------------------------------------------+
| ***visitedCellId***                                                   |
|                                                                       |
| This field indicates the visited cell id including NR and E-UTRA      |
| cells.                                                                |
+-----------------------------------------------------------------------+

#### -- *WLAN-NameList*

The IE *WLAN-NameList* is used to indicate the names of the WLAN AP for
which the UE is configured to measure.

*WLAN-NameList* information element

\-- ASN1START

\-- TAG-WLANNAMELIST-START

WLAN-NameList-r16 ::= SEQUENCE (SIZE (1..maxWLAN-Name-r16)) OF
WLAN-Name-r16

WLAN-Name-r16 ::= OCTET STRING (SIZE (1..32))

\-- ASN1STOP

\-- TAG-WLANNAMELIST-STOP

+-----------------------------------------------------------------------+
| *WLAN-NameList* field descriptions                                    |
+=======================================================================+
| ***WLAN-Name***                                                       |
|                                                                       |
| If configured, the UE only performs WLAN measurements according to    |
| the names identified. For each name, it refers to Service Set         |
| Identifier (SSID) defined in IEEE 802.11-2012 \[50\].                 |
+-----------------------------------------------------------------------+