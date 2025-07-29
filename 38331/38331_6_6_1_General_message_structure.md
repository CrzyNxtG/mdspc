### 6.6.1 General message structure

#### -- *PC5-RRC-Definitions*

This ASN.1 segment is the start of the PC5 RRC PDU definitions.

\-- ASN1START

\-- TAG-PC5-RRC-DEFINITIONS-START

PC5-RRC-Definitions DEFINITIONS AUTOMATIC TAGS ::=

BEGIN

IMPORTS

ARFCN-ValueNR,

CellAccessRelatedInfo,

SetupRelease,

RRC-TransactionIdentifier,

SN-FieldLengthAM,

SN-FieldLengthUM,

LogicalChannelIdentity,

maxNrofSLRB-r16,

maxNrofSL-RxInfoSet-r17,

maxNrofSL-QFIs-r16,

maxNrofSL-QFIsPerDest-r16,

PagingCycle,

PagingRecord,

RSRP-Range,

SL-MeasConfig-r16,

SL-MeasId-r16,

FreqBandList,

FreqBandIndicatorNR,

GNSS-ID-r16,

maxNrofRelayMeas-r17,

maxSimultaneousBands,

maxBandComb,

maxBands,

maxSIB,

maxSIB-MessagePlus1-r17,

maxSL-LCID-r16,

maxNrofFreqSL-1-r18,

BandParametersSidelink-r16,

PagingRecord-v1700,

RLC-ParametersSidelink-r16,

SBAS-ID-r16,

SIB1,

SL-DRX-ConfigUC-r17,

SL-DRX-ConfigUC-SemiStatic-r17,

SL-PagingIdentityRemoteUE-r17,

SL-RLC-ChannelID-r17,

SL-SourceIdentity-r17,

SystemInformation,

maxNrofSL-Dest-r16,

SL-DestinationIdentity-r16,

SL-RelayIndicationMP-r18,

SL-RSRP-Range-r16,

SL-QoS-FlowIdentity-r16,

SL-QoS-Info-r16,

maxNrofPhysicalResourceBlocks,

SubcarrierSpacing

FROM NR-RRC-Definitions;

\-- TAG-PC5-RRC-DEFINITIONS-STOP

\-- ASN1STOP

#### -- *SBCCH-SL-BCH-Message*

The *SBCCH-SL-BCH-Message* class is the set of RRC messages that may be
sent from the UE to the UE via SL-BCH on the SBCCH logical channel.

\-- ASN1START

\-- TAG-SBCCH-SL-BCH-MESSAGE-START

SBCCH-SL-BCH-Message ::= SEQUENCE {

message SBCCH-SL-BCH-MessageType

}

SBCCH-SL-BCH-MessageType::= CHOICE {

c1 CHOICE {

masterInformationBlockSidelink MasterInformationBlockSidelink,

spare1 NULL

},

messageClassExtension SEQUENCE {}

}

\-- TAG-SBCCH-SL-BCH-MESSAGE-STOP

\-- ASN1STOP

#### -- *SCCH-Message*

The *SCCH-Message* class is the set of PC5-RRC messages that may be sent
from the UE to the UE for unicast of NR sidelink communication on SCCH
logical channel.

\-- ASN1START

\-- TAG-SCCH-MESSAGE-START

SCCH-Message ::= SEQUENCE {

message SCCH-MessageType

}

SCCH-MessageType ::= CHOICE {

c1 CHOICE {

measurementReportSidelink MeasurementReportSidelink,

rrcReconfigurationSidelink RRCReconfigurationSidelink,

rrcReconfigurationCompleteSidelink RRCReconfigurationCompleteSidelink,

rrcReconfigurationFailureSidelink RRCReconfigurationFailureSidelink,

ueCapabilityEnquirySidelink UECapabilityEnquirySidelink,

ueCapabilityInformationSidelink UECapabilityInformationSidelink,

uuMessageTransferSidelink-r17 UuMessageTransferSidelink-r17,

remoteUEInformationSidelink-r17 RemoteUEInformationSidelink-r17

},

messageClassExtension CHOICE {

c2 CHOICE {

notificationMessageSidelink-r17 NotificationMessageSidelink-r17,

ueAssistanceInformationSidelink-r17 UEAssistanceInformationSidelink-r17,

ueInformationRequestSidelink-r18 UEInformationRequestSidelink-r18,

ueInformationResponseSidelink-r18 UEInformationResponseSidelink-r18,
spare4 NULL, spare3 NULL, spare2 NULL, spare1 NULL

},

messageClassExtensionFuture-r17 SEQUENCE {}

}

}

\-- TAG-SCCH-MESSAGE-STOP

\-- ASN1STOP

[]{#_Toc193463744 .anchor}6.6.2 Message definitions

#### -- *MasterInformationBlockSidelink*

The *MasterInformationBlockSidelink* includes the system information
transmitted by a UE via SL-BCH.

Signalling radio bearer: N/A

RLC-SAP: TM

Logical channel: SBCCH

Direction: UE to UE

*MasterInformationBlockSidelink*

\-- ASN1START

\-- TAG-MASTERINFORMATIONBLOCKSIDELINK-START

MasterInformationBlockSidelink ::= SEQUENCE {

sl-TDD-Config-r16 BIT STRING (SIZE (12)),

inCoverage-r16 BOOLEAN,

directFrameNumber-r16 BIT STRING (SIZE (10)),

slotIndex-r16 BIT STRING (SIZE (7)),

reservedBits-r16 BIT STRING (SIZE (2))

}

\-- TAG-MASTERINFORMATIONBLOCKSIDELINK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MasterInformationBlockSidelink* field descriptions                   |
+=======================================================================+
| ***directFrameNumber***                                               |
|                                                                       |
| Indicates the frame number in which S-SSB transmitted.                |
+-----------------------------------------------------------------------+
| ***inCoverage***                                                      |
|                                                                       |
| Value true indicates that the UE transmitting the                     |
| *MasterInformationBlockSidelink* is in network coverage, or UE        |
| selects GNSS timing as the synchronization reference source.          |
+-----------------------------------------------------------------------+
| ***slotIndex***                                                       |
|                                                                       |
| Indicates the slot index in which S-SSB transmitted.                  |
+-----------------------------------------------------------------------+

#### -- *MeasurementReportSidelink*

The *MeasurementReportSidelink* message is used for the indication of
measurement results of NR sidelink.

Signalling radio bearer: SL-SRB3

RLC-SAP: AM

Logical channel: SCCH

Direction: UE to UE

*MeasurementReportSidelink* message

\-- ASN1START

\-- TAG-MEASUREMENTREPORTSIDELINK-START

MeasurementReportSidelink ::= SEQUENCE {

criticalExtensions CHOICE {

measurementReportSidelink-r16 MeasurementReportSidelink-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

MeasurementReportSidelink-r16-IEs ::= SEQUENCE {

sl-MeasResults-r16 SL-MeasResults-r16,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

SL-MeasResults-r16 ::= SEQUENCE {

sl-MeasId-r16 SL-MeasId-r16,

sl-MeasResult-r16 SL-MeasResult-r16,

\...

}

SL-MeasResult-r16 ::= SEQUENCE {

sl-ResultDMRS-r16 SL-MeasQuantityResult-r16 OPTIONAL,

\...,

\[\[

sl-Result-SL-PRS-r18 SL-MeasQuantityResult-r16 OPTIONAL

\]\]

}

SL-MeasQuantityResult-r16 ::= SEQUENCE {

sl-RSRP-r16 RSRP-Range OPTIONAL,

\...,

\[\[

sl-RSRP-DedicatedSL-PRS-RP-r18 SL-RSRP-Range-r16 OPTIONAL

\]\]

}

SL-MeasResultListRelay-r17 ::= SEQUENCE (SIZE (1..maxNrofRelayMeas-r17))
OF SL-MeasResultRelay-r17

SL-MeasResultRelay-r17 ::= SEQUENCE {

cellIdentity-r17 CellAccessRelatedInfo,

sl-RelayUE-Identity-r17 SL-SourceIdentity-r17,

sl-MeasResult-r17 SL-MeasResult-r16,

\...,

\[\[

sl-MeasQuantity-r18 ENUMERATED { sl-rsrp, sd-rsrp } OPTIONAL,

sl-RelayIndicationMP-r18 SL-RelayIndicationMP-r18 OPTIONAL

\]\]

}

\-- TAG-MEASUREMENTREPORTSIDELINK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MeasurementReportSidelink* field descriptions                        |
+=======================================================================+
| ***sl-MeasId***                                                       |
|                                                                       |
| Identifies the sidelink measurement identity for which the reporting  |
| is being performed.                                                   |
+-----------------------------------------------------------------------+
| ***sl-MeasResult***                                                   |
|                                                                       |
| Measured RSRP results of a unicast destination.                       |
+-----------------------------------------------------------------------+
| ***sl-RSRP-DedicatedSL-PRS-RP***                                      |
|                                                                       |
| Measured SL PRS-based filtered RSRP.                                  |
+-----------------------------------------------------------------------+
| ***sl-RelayIndicationMP***                                            |
|                                                                       |
| Indicate the reported L2 U2N Relay UE supports RRC connection         |
| establishment/resume for MP operation triggered by receiving          |
| *RemoteUEInformationSidelink* containing the *connectionForMP* as     |
| specified in 5.3.3.1a and 5.3.13.1a in Rel-18.                        |
+-----------------------------------------------------------------------+

#### -- *NotificationMessageSidelink*

The *NotificationMessageSidelink* message is used to send notification
message from U2N Relay UE to the connected U2N Remote UE or from U2U
Relay UE to the connected U2U Remote UE.

Signalling radio bearer: SL-SRB3

RLC-SAP: AM

Logical channel: SCCH

Direction: U2N Relay UE to U2N Remote UE or U2U Relay UE to U2U Remote
UE

*NotificationMessageSidelink* message

\-- ASN1START

\-- TAG-NOTIFICATIONMESSAGESIDELINK-START

NotificationMessageSidelink-r17 ::= SEQUENCE {

criticalExtensions CHOICE {

notificationMessageSidelink-r17 NotificationMessageSidelink-r17-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

NotificationMessageSidelink-r17-IEs ::= SEQUENCE {

indicationType-r17 ENUMERATED {

relayUE-Uu-RLF, relayUE-HO, relayUE-CellReselection,

relayUE-Uu-RRC-Failure

} OPTIONAL, \-- Need N

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension NotificationMessageSidelink-v1800-IEs OPTIONAL

}

NotificationMessageSidelink-v1800-IEs ::= SEQUENCE {

sl-IndicationType-r18 ENUMERATED {relayUE-PC5-RLF, spare1} OPTIONAL, \--
Need N

sl-DestinationIdentityRemoteUE-r18 SL-DestinationIdentity-r16 OPTIONAL,
\-- Need N

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-NOTIFICATIONMESSAGESIDELINK -STOP

\-- ASN1STOP

#### -- *RemoteUEInformationSidelink*

The *RemoteUEInformationSidelink* message is used to request SIB(s) or
provide paging related information, or provide other remote UE
information, as specified in clause 5.8.9.8.1.

Signalling radio bearer: SL-SRB3

RLC-SAP: AM

Logical channel: SCCH

Direction: L2 U2N Remote UE to L2 U2N Relay UE, or L2 U2U Remote UE to
L2 U2U Relay UE

*RemoteUEInformationSidelink* message

\-- ASN1START

\-- TAG-REMOTEUEINFORMATIONSIDELINK-START

RemoteUEInformationSidelink-r17 ::= SEQUENCE {

criticalExtensions CHOICE {

remoteUEInformationSidelink-r17 RemoteUEInformationSidelink-r17-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RemoteUEInformationSidelink-r17-IEs ::= SEQUENCE {

sl-RequestedSIB-List-r17 SetupRelease { SL-RequestedSIB-List-r17}
OPTIONAL, \-- Need M

sl-PagingInfo-RemoteUE-r17 SetupRelease { SL-PagingInfo-RemoteUE-r17}
OPTIONAL, \-- Need M

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RemoteUEInformationSidelink-v1800-IEs OPTIONAL

}

RemoteUEInformationSidelink-v1800-IEs ::= SEQUENCE {

sl-RequestedPosSIB-List-r18 SetupRelease { SL-RequestedPosSIB-List-r18 }
OPTIONAL, \-- Need M

sl-SFN-DFN-OffsetRequested-r18 ENUMERATED { true } OPTIONAL, \-- Need R

connectionForMP-r18 ENUMERATED {true} OPTIONAL, \-- Need N

sl-DestinationIdentityRemoteUE-r18 SL-DestinationIdentity-r16 OPTIONAL,
\-- Need N

nonCriticalExtension SEQUENCE {} OPTIONAL

}

SL-RequestedSIB-List-r17 ::= SEQUENCE (SIZE (maxSIB-MessagePlus1-r17))
OF SL-SIB-ReqInfo-r17

SL-PagingInfo-RemoteUE-r17 ::= SEQUENCE {

sl-PagingIdentityRemoteUE-r17 SL-PagingIdentityRemoteUE-r17,

sl-PagingCycleRemoteUE-r17 PagingCycle OPTIONAL \-- Need M

}

SL-SIB-ReqInfo-r17 ::= ENUMERATED { sib1, sib2, sib3, sib4, sib5, sib6,
sib7, sib8, sib9, sib10, sib11, sib12, sib13,

sib14, sib15, sib16, sib17, sib18, sib19, sib20, sib21, sibNotReq11,
sibNotReq10,

sibNotReq9, sibNotReq8, sibNotReq7, sibNotReq6, sibNotReq5, sibNotReq4,

sibNotReq3, sibNotReq2, sibNotReq1, \..., sib17bis-v1820 }

SL-RequestedPosSIB-List-r18 ::= SEQUENCE (SIZE (1..maxSIB)) OF
SL-PosSIB-ReqInfo-r18

SL-PosSIB-ReqInfo-r18 ::= SEQUENCE {

gnss-id-r18 GNSS-ID-r16 OPTIONAL, \-- Need R

sbas-id-r18 SBAS-ID-r16 OPTIONAL, \-- Cond GNSS-ID-SBAS

posSibType-r18 ENUMERATED { posSibType1-1, posSibType1-2, posSibType1-3,
posSibType1-4, posSibType1-5, posSibType1-6,

posSibType1-7, posSibType1-8, posSibType1-9, posSibType1-10,
posSibType1-11,

posSibType1-12, posSibType2-1, posSibType2-2, posSibType2-3,
posSibType2-4, posSibType2-5,

posSibType2-6, posSibType2-7, posSibType2-8, posSibType2-9,
posSibType2-10, posSibType2-11,

posSibType2-12, posSibType2-13, posSibType2-14, posSibType2-15,
posSibType2-16,

posSibType2-17, posSibType2-17a, posSibType2-18, posSibType2-18a,
posSibType2-19,

posSibType2-20, posSibType2-20a, posSibType2-21, posSibType2-22,
posSibType2-23,

posSibType2-24, posSibType2-25, posSibType2-26, posSibType2-27,
posSibType3-1,

posSibType4-1, posSibType5-1, posSibType6-1, posSibType6-2,
posSibType6-3, posSibType6-4,

posSibType6-5, posSibType6-6, posSibType6-7, posSibType7-1,
posSibType7-2, posSibType7-3,

posSibType7-4, spare9, spare8, spare7, spare6, spare5, spare4, spare3,
spare2, spare1,

\... }

}

\-- TAG-REMOTEUEINFORMATIONSIDELINK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RemoteUEInformationSidelink-IEs* field descriptions                  |
+=======================================================================+
| ***connectionForMP***                                                 |
|                                                                       |
| Indicates the connected L2 U2N Relay UE by the L2 U2N Remote UE that  |
| the access is for MP.                                                 |
+-----------------------------------------------------------------------+
| ***sl-DestinationIdentityRemoteUE***                                  |
|                                                                       |
| Indicates the peer L2 U2U Remote UE upon end-to-end PC5 connection    |
| failure or release.                                                   |
+-----------------------------------------------------------------------+
| ***sl-PagingCycleRemoteUE***                                          |
|                                                                       |
| Indicates the L2 U2N Remote UE\'s UE specific DRX cycle as the        |
| minimum value of the one provided by upper layers (if configured) and |
| the one provided by RRC layer (if configured). Value rf32 corresponds |
| to 32 radio frames, value rf64 corresponds to 64 radio frames and so  |
| on.                                                                   |
+-----------------------------------------------------------------------+
| ***sl-PagingIdentityRemoteUE***                                       |
|                                                                       |
| Indicates the L2 U2N Remote UE\'s paging UE ID.                       |
+-----------------------------------------------------------------------+
| ***sl-PagingInfo-RemoteUE***                                          |
|                                                                       |
| Indicates the paging information used by L2 U2N Relay UE to perform   |
| the connected L2 U2N Remote UE\'s paging monitoring.                  |
+-----------------------------------------------------------------------+
| ***sl-RequestedPosSIB-List***                                         |
|                                                                       |
| Contains a list of requested PosSIBs.                                 |
+-----------------------------------------------------------------------+
| ***sl-RequestedSIB-List***                                            |
|                                                                       |
| Contains a list of requested SIBs.                                    |
+-----------------------------------------------------------------------+
| ***sl-SFN-DFN-OffsetRequested***                                      |
|                                                                       |
| If present, this field indicates that the L2 U2N Remote UE requests   |
| the L2 U2N Relay UE to provide the SFN-DFN offset in a subsequent     |
| *RRCReconfigurationSidelink* message.                                 |
+-----------------------------------------------------------------------+
| ***SL-SIB-ReqInfo***                                                  |
|                                                                       |
| Indicates the requested SIB type. Values sibNotReq11, sibNotReq10,    |
| ..., sibNotReq1 shall be ignored by L2 U2N relay UE (i.e., no SIB     |
| requested).                                                           |
+-----------------------------------------------------------------------+

  ----------------------------------------------------------------------------
  Conditional      Explanation
  presence         
  ---------------- -----------------------------------------------------------
  *GNSS-ID-SBAS*   The field is mandatory present if *gnss-id* is set to
                   *sbas*. It is absent otherwise.

  ----------------------------------------------------------------------------

#### -- *RRCReconfigurationSidelink*

The *RRCReconfigurationSidelink* message is the command to AS
configuration of the PC5 RRC connection. It is only applied to unicast
of NR sidelink communication.

Signalling radio bearer: SL-SRB3

RLC-SAP: AM

Logical channel: SCCH

Direction: UE to UE

*RRCReconfigurationSidelink* message

\-- ASN1START

\-- TAG-RRCRECONFIGURATIONSIDELINK-START

RRCReconfigurationSidelink ::= SEQUENCE {

rrc-TransactionIdentifier-r16 RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcReconfigurationSidelink-r16 RRCReconfigurationSidelink-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCReconfigurationSidelink-r16-IEs ::= SEQUENCE {

slrb-ConfigToAddModList-r16 SEQUENCE (SIZE (1..maxNrofSLRB-r16)) OF
SLRB-Config-r16 OPTIONAL, \-- Need N

slrb-ConfigToReleaseList-r16 SEQUENCE (SIZE (1..maxNrofSLRB-r16)) OF
SLRB-PC5-ConfigIndex-r16 OPTIONAL, \-- Need N

sl-MeasConfig-r16 SetupRelease {SL-MeasConfig-r16} OPTIONAL, \-- Need M

sl-CSI-RS-Config-r16 SetupRelease {SL-CSI-RS-Config-r16} OPTIONAL, \--
Need M

sl-ResetConfig-r16 ENUMERATED {true} OPTIONAL, \-- Need N

sl-LatencyBoundCSI-Report-r16 INTEGER (3..160) OPTIONAL, \-- Need M

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RRCReconfigurationSidelink-v1700-IEs OPTIONAL

}

RRCReconfigurationSidelink-v1700-IEs ::= SEQUENCE {

sl-DRX-ConfigUC-PC5-r17 SetupRelease { SL-DRX-ConfigUC-r17 } OPTIONAL,
\-- Need M

sl-LatencyBoundIUC-Report-r17 SetupRelease {
SL-LatencyBoundIUC-Report-r17 } OPTIONAL, \-- Need M

sl-RLC-ChannelToReleaseListPC5-r17 SEQUENCE (SIZE (1..maxSL-LCID-r16))
OF SL-RLC-ChannelID-r17 OPTIONAL, \-- Need N

sl-RLC-ChannelToAddModListPC5-r17 SEQUENCE (SIZE (1..maxSL-LCID-r16)) OF
SL-RLC-ChannelConfigPC5-r17 OPTIONAL, \-- Need N

nonCriticalExtension RRCReconfigurationSidelink-v1800-IEs OPTIONAL

}

RRCReconfigurationSidelink-v1800-IEs ::= SEQUENCE {

sl-SFN-DFN-Offset-r18 SetupRelease { SL-SFN-DFN-Offset-r18 } OPTIONAL,
\-- Need M

sl-CarrierToAddModList-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-1-r18)) OF
SL-CarrierConfig-r18 OPTIONAL, \-- Need N

sl-CarrierToReleaseList-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-1-r18)) OF
SL-CarrierId-r18 OPTIONAL, \-- Need N

sl-RLC-BearerToAddModList-r18 SEQUENCE (SIZE(1..maxNrofSLRB-r16)) OF
SL-RLC-BearerConfig-r18 OPTIONAL, \-- Need N

sl-RLC-BearerToReleaseList-r18 SEQUENCE (SIZE(1..maxNrofSLRB-r16)) OF
SL-RLC-BearerConfigIndex-r18 OPTIONAL, \-- Need N

sl-LocalID-PairList-r18 SEQUENCE (SIZE (1..maxNrofSL-Dest-r16)) OF
SL-SRAP-ConfigPC5-r18 OPTIONAL, \-- Need N

nonCriticalExtension SEQUENCE {} OPTIONAL

}

SL-CarrierConfig-r18 ::= SEQUENCE {

sl-CarrierId-r18 SL-CarrierId-r18,

sl-OffsetToCarrier-r18 INTEGER (0..2199),

subcarrierSpacing-r18 SubcarrierSpacing,

carrierBandwidth-r18 INTEGER (1..maxNrofPhysicalResourceBlocks),

sl-AbsoluteFrequencyPointA-r18 ARFCN-ValueNR

}

SL-CarrierId-r18 ::= INTEGER (1..maxNrofFreqSL-1-r18)

SL-RLC-BearerConfig-r18 ::= CHOICE {

srb SEQUENCE {

sl-SRB-IdentityWithDuplication INTEGER (1..3),

sL-RLC-BearerConfigIndex-r18 SL-RLC-BearerConfigIndex-r18,

\...

},

drb SEQUENCE {

slrb-PC5-ConfigIndex-r18 SLRB-PC5-ConfigIndex-r16,

sL-RLC-BearerConfigIndex-r18 SL-RLC-BearerConfigIndex-r18,

sl-RLC-ConfigPC5-r18 SL-RLC-ConfigPC5-r16 OPTIONAL, \-- Need M

sl-MAC-LogicalChannelConfigPC5-r18 SL-LogicalChannelConfigPC5-r16
OPTIONAL, \-- Need M

\...

}

}

SL-RLC-BearerConfigIndex-r18 ::= INTEGER (1..maxSL-LCID-r16)

SL-LatencyBoundIUC-Report-r17::= INTEGER (3..160)

SLRB-Config-r16::= SEQUENCE {

slrb-PC5-ConfigIndex-r16 SLRB-PC5-ConfigIndex-r16,

sl-SDAP-ConfigPC5-r16 SL-SDAP-ConfigPC5-r16 OPTIONAL, \-- Need M

sl-PDCP-ConfigPC5-r16 SL-PDCP-ConfigPC5-r16 OPTIONAL, \-- Need M

sl-RLC-ConfigPC5-r16 SL-RLC-ConfigPC5-r16 OPTIONAL, \-- Need M

sl-MAC-LogicalChannelConfigPC5-r16 SL-LogicalChannelConfigPC5-r16
OPTIONAL, \-- Need M

\...

}

SLRB-PC5-ConfigIndex-r16 ::= INTEGER (1..maxNrofSLRB-r16)

SL-SDAP-ConfigPC5-r16 ::= SEQUENCE {

sl-MappedQoS-FlowsToAddList-r16 SEQUENCE (SIZE (1..
maxNrofSL-QFIsPerDest-r16)) OF SL-PQFI-r16 OPTIONAL, \-- Need N

sl-MappedQoS-FlowsToReleaseList-r16 SEQUENCE (SIZE (1..
maxNrofSL-QFIsPerDest-r16)) OF SL-PQFI-r16 OPTIONAL, \-- Need N

sl-SDAP-Header-r16 ENUMERATED {present, absent},

\...

}

SL-PDCP-ConfigPC5-r16 ::= SEQUENCE {

sl-PDCP-SN-Size-r16 ENUMERATED {len12bits, len18bits} OPTIONAL, \-- Need
M

sl-OutOfOrderDelivery-r16 ENUMERATED { true } OPTIONAL, \-- Need R

\...

}

SL-RLC-ConfigPC5-r16 ::= CHOICE {

sl-AM-RLC-r16 SEQUENCE {

sl-SN-FieldLengthAM-r16 SN-FieldLengthAM OPTIONAL, \-- Need M

\...

},

sl-UM-Bi-Directional-RLC-r16 SEQUENCE {

sl-SN-FieldLengthUM-r16 SN-FieldLengthUM OPTIONAL, \-- Need M

\...

},

sl-UM-Uni-Directional-RLC-r16 SEQUENCE {

sl-SN-FieldLengthUM-r16 SN-FieldLengthUM OPTIONAL, \-- Need M

\...

}

}

SL-LogicalChannelConfigPC5-r16 ::= SEQUENCE {

sl-LogicalChannelIdentity-r16 LogicalChannelIdentity,

\...,

\[\[

sl-LogicalChannelIdentity-v1800 INTEGER (33..38) OPTIONAL \-- Need M

\]\]

}

SL-PQFI-r16 ::= INTEGER (1..64)

SL-CSI-RS-Config-r16 ::= SEQUENCE {

sl-CSI-RS-FreqAllocation-r16 CHOICE {

sl-OneAntennaPort-r16 BIT STRING (SIZE (12)),

sl-TwoAntennaPort-r16 BIT STRING (SIZE (6))

} OPTIONAL, \-- Need M

sl-CSI-RS-FirstSymbol-r16 INTEGER (3..12) OPTIONAL, \-- Need M

\...

}

SL-RLC-ChannelConfigPC5-r17::= SEQUENCE {

sl-RLC-ChannelID-PC5-r17 SL-RLC-ChannelID-r17,

sl-RLC-ConfigPC5-r17 SL-RLC-ConfigPC5-r16 OPTIONAL, \-- Need M

sl-MAC-LogicalChannelConfigPC5-r17 SL-LogicalChannelConfigPC5-r16
OPTIONAL, \-- Need M

\...

}

SL-SFN-DFN-Offset-r18 ::= SEQUENCE {

sl-FrameOffset-r18 INTEGER (0..1023),

sl-SubframeOffset-r18 INTEGER (0..9),

sl-SlotOffset-r18 INTEGER (0..31)

}

SL-SRAP-ConfigPC5-r18 ::= SEQUENCE {

sl-PeerRemoteUE-L2Identity-r18 SL-DestinationIdentity-r16 OPTIONAL, \--
Need M

sl-PeerRemoteUE-LocalIdentity-r18 INTEGER (0..255) OPTIONAL, \-- Need M

sl-RemoteUE-L2Identity-r18 SL-SourceIdentity-r17 OPTIONAL, \-- Need M

sl-RemoteUE-LocalIdentity-r18 INTEGER (0..255) OPTIONAL, \-- Need M

\...

}

\-- TAG-RRCRECONFIGURATIONSIDELINK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCReconfigurationSidelink* field descriptions                       |
+=======================================================================+
| ***sl-AbsoluteFrequencyPointA***                                      |
|                                                                       |
| Absolute frequency of the reference resource block (Common RB 0). Its |
| lowest subcarrier is also known as Point A.                           |
+-----------------------------------------------------------------------+
| ***sl-CarrierToAddModList***                                          |
|                                                                       |
| Indicate the carrier(s) to be added/modified for transmission by UE   |
| transmitting *RRCReconfigurationSidelink* message, corresponding to   |
| the frequency in *sl-FreqInfoListSizeExt* broadcast in *SIB12* or     |
| corresponding to the frequency in *sl-PreconfigFreqInfoListSizeExt*   |
| in *SL-PreconfigurationNR*.                                           |
+-----------------------------------------------------------------------+
| ***sl-CarrierToReleaseList***                                         |
|                                                                       |
| Indicate the carrier(s) to be released for the transmission by UE     |
| transmitting *RRCReconfigurationSidelink* message.                    |
+-----------------------------------------------------------------------+
| ***sl-CSI-RS-FreqAllocation***                                        |
|                                                                       |
| Indicates the frequency domain position for sidelink CSI-RS.          |
+-----------------------------------------------------------------------+
| ***sl-CSI-RS-FirstSymbol***                                           |
|                                                                       |
| Indicates the position of first symbol of sidelink CSI-RS.            |
+-----------------------------------------------------------------------+
| ***sl-DRX-ConfigUC-PC5***                                             |
|                                                                       |
| Indicates the NR sidelink DRX configuration for unicast               |
| communication, as specified in TS 38.321 \[3\]                        |
+-----------------------------------------------------------------------+
| ***sl-LatencyBoundCSI-Report***                                       |
|                                                                       |
| Indicates the latency bound of SL CSI report from the associated SL   |
| CSI triggering in terms of number of slots.                           |
+-----------------------------------------------------------------------+
| ***sl-LatencyBoundIUC-Report***                                       |
|                                                                       |
| Indicates the latency bound of SL Inter-UE coordination report from   |
| the associated SL Inter-UE coordination explicit request triggering   |
| in terms of number of slots.                                          |
+-----------------------------------------------------------------------+
| ***sl-LocalID-PairList***                                             |
|                                                                       |
| Indicate a list of local ID pair which is assigned for one end-to-end |
| PC5 connection by the L2 U2U Relay UE.                                |
+-----------------------------------------------------------------------+
| ***sl-LogicalChannelIdentity***                                       |
|                                                                       |
| Indicates the identity of the sidelink logical channel, as specified  |
| in TS 38.321 \[3\], clause 6.2.4. If the                              |
| *sl-LogicalChannelIdentity-v1800* is present, the UE shall ignore the |
| *sl-LogicalChannelIndentity-r16* field.                               |
+-----------------------------------------------------------------------+
| ***sl-MappedQoS-FlowsToAddList***                                     |
|                                                                       |
| Indicate the QoS flows to be mapped to the configured sidelink DRB.   |
| Each entry is indicated by the *SL-PQFI*, which is used between UEs,  |
| as defined in TS 23.287 \[55\].                                       |
+-----------------------------------------------------------------------+
| ***sl-MappedQoS-FlowsToReleaseList***                                 |
|                                                                       |
| Indicate the QoS flows to be released from the configured sidelink    |
| DRB. Each entry is indicated by the *SL-PQFI*, which is used between  |
| UEs, as defined in TS 23.287 \[55\].                                  |
+-----------------------------------------------------------------------+
| ***sl-MeasConfig***                                                   |
|                                                                       |
| Indicates the sidelink measurement configuration for the unicast      |
| destination.                                                          |
+-----------------------------------------------------------------------+
| ***sl-OffsetToCarrier***                                              |
|                                                                       |
| Offset in frequency domain between Point A (lowest subcarrier of      |
| common RB 0) and the lowest usable subcarrier on this carrier in      |
| number of PRBs (using the subcarrierSpacing defined for this          |
| carrier). The maximum value corresponds to 275\*8-1. See TS 38.211    |
| \[16\], clause 4.4.2.                                                 |
+-----------------------------------------------------------------------+
| ***sl-OutOfOrderDelivery***                                           |
|                                                                       |
| Indicates whether or not outOfOrderDelivery specified in TS 38.323    |
| \[5\] is configured. This field should be either always present or    |
| always absent, after the sidelink radio bearer is established.        |
+-----------------------------------------------------------------------+
| ***sl-PDCP-SN-Size***                                                 |
|                                                                       |
| Indicates the PDCP SN size of the configured sidelink DRB.            |
+-----------------------------------------------------------------------+
| ***sl-Resetconfig***                                                  |
|                                                                       |
| Indicates that the full configuration should be applicable for the    |
| *RRCReconfigurationSidelink* message.                                 |
+-----------------------------------------------------------------------+
| ***sl-RLC-BearerToAddModList***                                       |
|                                                                       |
| Indicate the additional Sidelink RLC bearer to be added / modified    |
| for the configured sidelink SRB/DRB.                                  |
+-----------------------------------------------------------------------+
| ***sl-RLC-BearerToReleaseList***                                      |
|                                                                       |
| Indicate the additional Sidelink RLC bearer to be released for the    |
| configured sidelink SRB/DRB.                                          |
+-----------------------------------------------------------------------+
| ***sl-SDAP-Header***                                                  |
|                                                                       |
| Indicates whether or not a SDAP header is present on this sidelink    |
| DRB.                                                                  |
+-----------------------------------------------------------------------+
| ***sl-SFN-DFN-Offset***                                               |
|                                                                       |
| Indicates the SFN-DFN offset to be used for determining the SFN       |
| timeline based on the DFN timeline.                                   |
+-----------------------------------------------------------------------+
| ***sl-SRB-IdentityWithDuplication***                                  |
|                                                                       |
| Indicate the sidelink SRB for which duplication is configured.        |
+-----------------------------------------------------------------------+
| ***slrb-PC5-ConfigIndex***                                            |
|                                                                       |
| Indicates the identity of the configuration of a sidelink DRB. In     |
| case of L2 U2U relay, only value 4-31 can be signaled for an          |
| end-to-end sidelink DRB, and all other values are reserved.           |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SL-SRAP-ConfigPC5* field descriptions                                |
+=======================================================================+
| ***sl-RemoteUE-LocalIdentity***                                       |
|                                                                       |
| Indicates the local UE ID of the L2 U2U Remote UE used in SRAP as     |
| specified in TS 38.351 \[66\].                                        |
+-----------------------------------------------------------------------+
| ***sl-RemoteUE-L2Identity***                                          |
|                                                                       |
| Indicates the Source L2 ID of the L2 U2U Remote UE as specified in TS |
| 23.304 \[65\].                                                        |
+-----------------------------------------------------------------------+
| ***sl-PeerRemoteUE-LocalIdentity***                                   |
|                                                                       |
| Indicates the local UE ID of the peer L2 U2U Remote UE used in SRAP   |
| as specified in TS 38.351 \[66\].                                     |
+-----------------------------------------------------------------------+
| ***sl-PeerRemoteUE-L2Identity***                                      |
|                                                                       |
| Indicates the destination L2 ID identifying the peer L2 U2U Remote UE |
| as specified in TS 23.304 \[65\].                                     |
+-----------------------------------------------------------------------+

#### -- *RRCReconfigurationCompleteSidelink*

The *RRCReconfigurationCompleteSidelink* message is used to confirm the
successful completion of a PC5 RRC AS reconfiguration. It is only
applied to unicast of NR sidelink communication.

Signalling radio bearer: SL-SRB3

RLC-SAP: AM

Logical channel: SCCH

Direction: UE to UE

*RRCReconfigurationCompleteSidelink* message

\-- ASN1START

\-- TAG-RRCRECONFIGURATIONCOMPLETESIDELINK-START

RRCReconfigurationCompleteSidelink ::= SEQUENCE {

rrc-TransactionIdentifier-r16 RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcReconfigurationCompleteSidelink-r16
RRCReconfigurationCompleteSidelink-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCReconfigurationCompleteSidelink-r16-IEs ::= SEQUENCE {

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RRCReconfigurationCompleteSidelink-v1710-IEs
OPTIONAL

}

RRCReconfigurationCompleteSidelink-v1710-IEs ::= SEQUENCE {

dummy ENUMERATED {true},

nonCriticalExtension RRCReconfigurationCompleteSidelink-v1720-IEs
OPTIONAL

}

RRCReconfigurationCompleteSidelink-v1720-IEs ::= SEQUENCE {

sl-DRX-ConfigReject-v1720 ENUMERATED {true} OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-RRCRECONFIGURATIONCOMPLETESIDELINK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCReconfigurationCompleteSidelink* field descriptions               |
+=======================================================================+
| ***dummy***                                                           |
|                                                                       |
| This field is not used in the specification. The UE shall not include |
| this field. If received it shall be ignored by the peer UE.           |
+-----------------------------------------------------------------------+
| ***sl-DRX-ConfigReject***                                             |
|                                                                       |
| Indicates the rejection of sidelink DRX configuration received from   |
| the peer UE for the corresponding NR sidelink unicast communication.  |
+-----------------------------------------------------------------------+

#### -- *RRCReconfigurationFailureSidelink*

The *RRCReconfigurationFailureSidelink* message is used to indicate the
failure of a PC5 RRC AS reconfiguration. It is only applied to unicast
of NR sidelink communication.

Signalling radio bearer: SL-SRB3

RLC-SAP: AM

Logical channel: SCCH

Direction: UE to UE

*RRCReconfigurationFailureSidelink* message

\-- ASN1START

\-- TAG-RRCRECONFIGURATIONFAILURESIDELINK-START

RRCReconfigurationFailureSidelink ::= SEQUENCE {

rrc-TransactionIdentifier-r16 RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcReconfigurationFailureSidelink-r16
RRCReconfigurationFailureSidelink-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCReconfigurationFailureSidelink-r16-IEs ::= SEQUENCE {

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-RRCRECONFIGURATIONFAILURESIDELINK-STOP

\-- ASN1STOP

#### -- *UEAssistanceInformationSidelink*

The *UEAssistanceInformationSidelink* message may include sidelink DRX
assistance information used to determine the sidelink DRX configuration.

Signalling radio bearer: SL-SRB3

RLC-SAP: AM

Logical channel: SCCH

Direction: UE to UE

*UEAssistanceInformationSidelink* message

\-- ASN1START

\-- TAG-UEASSISTANCEINFORMATIONSIDELINK-START

UEAssistanceInformationSidelink-r17 ::= SEQUENCE {

criticalExtensions CHOICE {

ueAssistanceInformationSidelink-r17
UEAssistanceInformationSidelink-r17-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

UEAssistanceInformationSidelink-r17-IEs ::= SEQUENCE {

sl-PreferredDRX-ConfigList-r17 SEQUENCE (SIZE
(1..maxNrofSL-RxInfoSet-r17)) OF SL-DRX-ConfigUC-SemiStatic-r17

OPTIONAL, \-- Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-UEASSISTANCEINFORMATIONSIDELINK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UEAssistanceInformationSidelink* field descriptions                  |
+=======================================================================+
| ***sl-PreferredDRX-ConfigList***                                      |
|                                                                       |
| Indicates a list of the reference sidelink DRX configurations         |
| provided by a UE to a peer UE for determining the sidelink DRX        |
| configuration.                                                        |
+-----------------------------------------------------------------------+

#### -- *UECapabilityEnquirySidelink*

The *UECapabilityEnquirySidelink* message is used to request UE sidelink
capabilities. It is only applied to unicast of NR sidelink
communication.

Signalling radio bearer: SL-SRB3

RLC-SAP: AM

Logical channel: SCCH

Direction: UE to UE

*UECapabilityEnquirySidelink* message

\-- ASN1START

\-- TAG-UECAPABILITYENQUIRYSIDELINK-START

UECapabilityEnquirySidelink ::= SEQUENCE {

rrc-TransactionIdentifier-r16 RRC-TransactionIdentifier,

criticalExtensions CHOICE {

ueCapabilityEnquirySidelink-r16 UECapabilityEnquirySidelink-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

UECapabilityEnquirySidelink-r16-IEs ::= SEQUENCE {

frequencyBandListFilterSidelink-r16 FreqBandList OPTIONAL, \-- Need N

ue-CapabilityInformationSidelink-r16 OCTET STRING OPTIONAL, \-- Need N

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

\-- TAG-UECAPABILITYENQUIRYSIDELINK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UECapabilityEnquirySidelink-IEs* field descriptions                  |
+=======================================================================+
| ***frequencyBandListFilterSidelink***                                 |
|                                                                       |
| This field is used to indicate frequency bands for which the peer UE  |
| is requested to provide supported bands and band combinations for NR  |
| sidelink communications. The UE always provides this field.           |
+-----------------------------------------------------------------------+
| ***ue-CapabilityInformationSidelink***                                |
|                                                                       |
| This field indicates the *UECapabilityInformationSidelink* message to |
| provide the UE sidelink capability, which can be optionally sent      |
| together with *UECapabilityEnquirySidelink*.                          |
+-----------------------------------------------------------------------+

#### -- *UECapabilityInformationSidelink*

The *UECapabilityInformationSidelink* message is used to transfer UE
radio access capabilities. It is only applied to unicast of NR sidelink
communication.

Signalling radio bearer: SL-SRB3

RLC-SAP: AM

Logical channel: SCCH

Direction: UE to UE

*UECapabilityInformationSidelink* message

\-- ASN1START

\-- TAG-UECAPABILITYINFORMATIONSIDELINK-START

UECapabilityInformationSidelink ::= SEQUENCE {

rrc-TransactionIdentifier-r16 RRC-TransactionIdentifier,

criticalExtensions CHOICE {

ueCapabilityInformationSidelink-r16
UECapabilityInformationSidelink-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

UECapabilityInformationSidelink-r16-IEs ::= SEQUENCE {

accessStratumReleaseSidelink-r16 AccessStratumReleaseSidelink-r16,

pdcp-ParametersSidelink-r16 PDCP-ParametersSidelink-r16 OPTIONAL,

rlc-ParametersSidelink-r16 RLC-ParametersSidelink-r16 OPTIONAL,

supportedBandCombinationListSidelinkNR-r16
BandCombinationListSidelinkNR-r16 OPTIONAL,

supportedBandListSidelink-r16 SEQUENCE (SIZE (1..maxBands)) OF
BandSidelinkPC5-r16 OPTIONAL,

appliedFreqBandListFilter-r16 FreqBandList OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension UECapabilityInformationSidelink-v1700-IEs OPTIONAL

}

UECapabilityInformationSidelink-v1700-IEs ::= SEQUENCE {

mac-ParametersSidelink-r17 MAC-ParametersSidelink-r17 OPTIONAL,

supportedBandCombinationListSidelinkNR-v1710
BandCombinationListSidelinkNR-v1710 OPTIONAL,

nonCriticalExtension UECapabilityInformationSidelink-v1800-IEs OPTIONAL

}

UECapabilityInformationSidelink-v1800-IEs ::= SEQUENCE {

sfn-DFN-OffsetSupported-r18 ENUMERATED { supported } OPTIONAL,

posSIB-ForwardingSupported-r18 ENUMERATED { supported } OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

MAC-ParametersSidelink-r17 ::= SEQUENCE {

drx-OnSidelink-r17 ENUMERATED {supported} OPTIONAL,

\...

}

AccessStratumReleaseSidelink-r16 ::= ENUMERATED { rel16, rel17, rel18,
spare5, spare4, spare3, spare2, spare1, \... }

PDCP-ParametersSidelink-r16 ::= SEQUENCE {

outOfOrderDeliverySidelink-r16 ENUMERATED {supported} OPTIONAL,

\...,

\[\[

pdcp-DuplicationSRB-sidelink-r18 ENUMERATED {supported} OPTIONAL,

pdcp-DuplicationDRB-sidelink-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

BandCombinationListSidelinkNR-r16 ::= SEQUENCE (SIZE (1..maxBandComb))
OF BandCombinationParametersSidelinkNR-r16

BandCombinationListSidelinkNR-v1710 ::= SEQUENCE (SIZE (1..maxBandComb))
OF BandCombinationParametersSidelinkNR-v1710

BandCombinationParametersSidelinkNR-r16 ::= SEQUENCE (SIZE
(1..maxSimultaneousBands)) OF BandParametersSidelink-r16

BandCombinationParametersSidelinkNR-v1710 ::= SEQUENCE (SIZE
(1..maxSimultaneousBands)) OF BandParametersSidelink-v1710

BandParametersSidelink-v1710 ::= SEQUENCE {

\--32-5a-1

tx-IUC-Scheme1-Mode2Sidelink-r17 ENUMERATED {supported} OPTIONAL,

\--32-5b-1

tx-IUC-Scheme2-Mode2Sidelink-r17 ENUMERATED {n4, n8, n16} OPTIONAL

}

BandSidelinkPC5-r16 ::= SEQUENCE {

freqBandSidelink-r16 FreqBandIndicatorNR,

\--15-1

sl-Reception-r16 SEQUENCE {

harq-RxProcessSidelink-r16 ENUMERATED {n16, n24, n32, n64},

pscch-RxSidelink-r16 ENUMERATED {value1, value2},

scs-CP-PatternRxSidelink-r16 CHOICE {

fr1-r16 SEQUENCE {

scs-15kHz-r16 BIT STRING (SIZE (16)) OPTIONAL,

scs-30kHz-r16 BIT STRING (SIZE (16)) OPTIONAL,

scs-60kHz-r16 BIT STRING (SIZE (16)) OPTIONAL

},

fr2-r16 SEQUENCE {

scs-60kHz-r16 BIT STRING (SIZE (16)) OPTIONAL,

scs-120kHz-r16 BIT STRING (SIZE (16)) OPTIONAL

}

} OPTIONAL,

extendedCP-RxSidelink-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\--15-10

sl-Tx-256QAM-r16 ENUMERATED {supported} OPTIONAL,

\--15-12

lowSE-64QAM-MCS-TableSidelink-r16 ENUMERATED {supported} OPTIONAL,

\...,

\[\[

\--15-14

csi-ReportSidelink-r16 SEQUENCE {

csi-RS-PortsSidelink-r16 ENUMERATED {p1, p2}

} OPTIONAL,

\--15-19

rankTwoReception-r16 ENUMERATED {supported} OPTIONAL,

\--15-23

sl-openLoopPC-RSRP-ReportSidelink-r16 ENUMERATED {supported} OPTIONAL,

\--13-1

sl-Rx-256QAM-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\--32-5a-2

rx-IUC-Scheme1-PreferredMode2Sidelink-r17 ENUMERATED {supported}
OPTIONAL,

\--32-5a-3

rx-IUC-Scheme1-NonPreferredMode2Sidelink-r17 ENUMERATED {supported}
OPTIONAL,

\--32-5b-2

rx-IUC-Scheme2-Mode2Sidelink-r17 ENUMERATED {n5, n15, n25, n32, n35,
n45, n50, n64} OPTIONAL,

\--32-6-1

rx-IUC-Scheme1-SCI-r17 ENUMERATED {supported} OPTIONAL,

\--32-6-2

rx-IUC-Scheme1-SCI-ExplicitReq-r17 ENUMERATED {supported} OPTIONAL,

\--32-7

scheme2-ConflictDeterminationRSRP-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 41-1-17: Open loop SL pathloss based power control for SL-PRS and
associated PSCCH and SL RSRP report for dedicated resource

\-- pool

sl-PathlossBasedOLPC-SL-RSRP-Report-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-k4: Transmitting UE to UE COT sharing information

sl-UE-COT-Sharing-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-m11: PSFCH transmissions in multiple contiguous RB sets

sl-PSFCH-MultiContiguousRB-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-m11a: PSFCH transmissions in multiple non-contiguous RB sets

sl-PSFCH-MultiNonContiguousRB-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-v1: NR SL communication with SL CA

sl-CA-Communication-r18 SEQUENCE {

numberOfCarriers-r18 INTEGER (2..8),

numberOfPSCCH-DecodeValueZ-r18 INTEGER (1..2),

totalBandwidth-r18 ENUMERATED {mhz20,mhz30,mhz40,mhz50,mhz60,mhz70}

} OPTIONAL,

\-- R4 45-2: SL reception in intra-carrier guard band

sl-ReceptionIntraCarrierGuardBand-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 45-3: Power class for sidelink unlicensed

sl-PowerClassUnlicensed-r18 ENUMERATED {pc5, spare7, spare6, spare5,
spare4, spare3, spare2, spare1} OPTIONAL

\]\]

}

\-- TAG-UECAPABILITYINFORMATIONSIDELINK-STOP

\-- ASN1STOP

#### *-- UEInformationRequestSidelink*

The *UEInformationRequestSidelink* message is used to transfer UE
information in sidelink, e.g. the end-to-end QoS information for L2 U2U
Relay operation.

> Signalling radio bearer: SL-SRB3
>
> RLC-SAP: AM
>
> Logical channel: SCCH
>
> Direction: L2 U2U Remote UE to L2 U2U Relay UE

*UEInformationRequestSidelink* message

\-- ASN1START

\-- TAG-UEINFORMATIONREQUESTSIDELINK-START

UEInformationRequestSidelink-r18 ::= SEQUENCE {

rrc-TransactionIdentifier-r18 RRC-TransactionIdentifier,

criticalExtensions CHOICE {

ueInformationRequestSidelink-r18 UEInformationRequestSidelink-r18-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

UEInformationRequestSidelink-r18-IEs ::= SEQUENCE {

sl-E2E-QoS-InfoListPC5-r18 SEQUENCE (SIZE (1..maxNrofSLRB-r16)) OF
SL-E2E-QoS-InfoPC5-r18 OPTIONAL, \-- Need N

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

SL-E2E-QoS-InfoPC5-r18 ::= SEQUENCE {

sl-DestinationIdentityRemoteUE-r18 SL-DestinationIdentity-r16,

sl-E2E-SLRB-Index-r18 SLRB-PC5-ConfigIndex-r16,

sl-QoS-InfoList-r18 SEQUENCE (SIZE (1..maxNrofSL-QFIsPerDest-r16)) OF
SL-QoS-Info-r16

}

\-- TAG-UEINFORMATIONREQUESTSIDELINK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UEInformationRequestSidelink* field descriptions                     |
+=======================================================================+
| ***sl-E2E-QoS-InfoListPC5***                                          |
|                                                                       |
| Indicates the per-QoS flow QoS info for a list of end-to-end PC5      |
| connections with each connection indicated by the destination L2 ID   |
| of the peer L2 U2U Remote UE. In addition, the end-to-end SLRB index  |
| is included to indicate the mapping from the QoS flow to the SLRB.    |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SL-E2E-QoS-InfoPC5* field descriptions                               |
+=======================================================================+
| ***sl-DestinationIdentityRemoteUE***                                  |
|                                                                       |
| Indicates the destination L2 ID of the peer L2 U2U Remote UE for an   |
| end-to-end PC5 connection.                                            |
+-----------------------------------------------------------------------+
| ***sl-E2E-SLRB-Index***                                               |
|                                                                       |
| Indicates the index of an end-to-end SLRB.                            |
+-----------------------------------------------------------------------+
| ***sl-QoS-InfoList***                                                 |
|                                                                       |
| List of QoS profile of the sidelink QoS flow for an end-to-end PC5    |
| connection, with each QoS flow indicated by *sl-QoS-FlowIdentity*     |
| which is unique for different end-to-end PC5 connection in the scope  |
| of UE, and uniquely identifies one sidelink QoS flow between the L2   |
| U2U Remote UE and the L2 U2U Relay UE.                                |
+-----------------------------------------------------------------------+

#### -- *UEInformationResponseSidelink*

The *UEInformationResponseSidelink* message is used to deliver UE
information in sidelink, e.g. the split QoS information for L2 U2U Relay
operation.

> Signalling radio bearer: SL-SRB3
>
> RLC-SAP: AM
>
> Logical channel: SCCH
>
> Direction: L2 U2U Relay UE to L2 U2U Remote UE

*UEInformationResponseSidelink* message

\-- ASN1START

\-- TAG-UEINFORMATIONRESPONSESIDELINK-START

UEInformationResponseSidelink-r18 ::= SEQUENCE {

rrc-TransactionIdentifier-r18 RRC-TransactionIdentifier,

criticalExtensions CHOICE {

ueInformationResponseSidelink-r18 UEInformationResponseSidelink-r18-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

UEInformationResponseSidelink-r18-IEs ::= SEQUENCE {

sl-SplitQoS-InfoListPC5-r18 SEQUENCE (SIZE (1.. maxNrofSL-QFIs-r16)) OF
SL-SplitQoS-InfoPC5-r18 OPTIONAL, \-- Need N

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

SL-SplitQoS-InfoPC5-r18 ::= SEQUENCE {

sl-QoS-FlowIdentity-r18 SL-QoS-FlowIdentity-r16,

sl-SplitPacketDelayBudget-r18 INTEGER (0..1023)

}

\-- TAG-UEINFORMATIONRESPONSESIDELINK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UEInformationResponseSidelink* field descriptions                    |
+=======================================================================+
| ***sl-SplitQoS-InfoListPC5***                                         |
|                                                                       |
| Indicates the split PDB on the first PC5 hop between L2 U2U Relay UE  |
| and the L2 U2U Remote UE for a list of QoS flow indicated by          |
| *sl-QoS-FlowIdentity* for one or more end-to-end PC5 connections.     |
| *sl-SplitPacketDelayBudget* indicates upper bound value for the delay |
| that a packet may experience expressed in unit of 0.5ms.              |
+-----------------------------------------------------------------------+

#### -- *UuMessageTransferSidelink*

The *UuMessageTransferSidelink* message is used for the sidelink
transfer of Paging message and System Information messages.

Signalling radio bearer: SL-SRB3

RLC-SAP: AM

Logical channel: SCCH

Direction: L2 U2N Relay UE to L2 U2N Remote UE

*UuMessageTransferSidelink* message

\-- ASN1START

\-- TAG-UUMESSAGETRANSFERSIDELINK-START

UuMessageTransferSidelink-r17 ::= SEQUENCE {

criticalExtensions CHOICE {

uuMessageTransferSidelink-r17 UuMessageTransferSidelink-r17-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

UuMessageTransferSidelink-r17-IEs ::= SEQUENCE {

sl-PagingDelivery-r17 OCTET STRING (CONTAINING PagingRecord) OPTIONAL,
\-- Need N

sl-SIB1-Delivery-r17 OCTET STRING (CONTAINING SIB1) OPTIONAL, \-- Need N

sl-SystemInformationDelivery-r17 OCTET STRING (CONTAINING
SystemInformation) OPTIONAL, \-- Need N

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension UuMessageTransferSidelink-v1800-IEs OPTIONAL

}

UuMessageTransferSidelink-v1800-IEs ::= SEQUENCE {

sl-PagingDelivery-r18 OCTET STRING (CONTAINING PagingRecord-v1700)
OPTIONAL, \-- Need N

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-UUMESSAGETRANSFERSIDELINK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UuMessageTransferSidelink-IEs* field descriptions                    |
+=======================================================================+
| ***sl-PagingDelivery***                                               |
|                                                                       |
| This field is used to transfer PagingRecord and *PagingRecord-v1700*  |
| relevant to the L2 U2N Remote UE in RRC_IDLE or RRC_INACTIVE.         |
+-----------------------------------------------------------------------+
| ***sl-SIB1-Delivery***                                                |
|                                                                       |
| This field is used to transfer SIB1 to the L2 U2N Remote UE in        |
| RRC_IDLE or RRC_INACTIVE.                                             |
+-----------------------------------------------------------------------+
| ***sl-SystemInformationDelivery***                                    |
|                                                                       |
| This field is used to transfer SIBs and posSIBs to the L2 U2N Remote  |
| UE in RRC_IDLE or RRC_INACTIVE.                                       |
+-----------------------------------------------------------------------+

#### -- *End of PC5-RRC-Definitions*

\-- ASN1START

END

\-- ASN1STOP