### 6.2.2 Message definitions

#### -- *CounterCheck*

The *CounterCheck* message is used by the network to indicate the
current COUNT MSB values associated to each DRB and to request the UE to
compare these to its COUNT MSB values and to report the comparison
results to the network.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*CounterCheck message*

\-- ASN1START

\-- TAG-COUNTERCHECK-START

CounterCheck ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

counterCheck CounterCheck-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

CounterCheck-IEs ::= SEQUENCE {

drb-CountMSB-InfoList DRB-CountMSB-InfoList,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

DRB-CountMSB-InfoList ::= SEQUENCE (SIZE (1..maxDRB)) OF
DRB-CountMSB-Info

DRB-CountMSB-Info ::= SEQUENCE {

drb-Identity DRB-Identity,

countMSB-Uplink INTEGER(0..33554431),

countMSB-Downlink INTEGER(0..33554431)

}

\-- TAG-COUNTERCHECK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *CounterCheck-IEs* field descriptions                                 |
+=======================================================================+
| ***drb-CountMSB-InfoList***                                           |
|                                                                       |
| Indicates the MSBs of the COUNT values of the DRBs.                   |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *DRB-CountMSB-Info* field descriptions                                |
+=======================================================================+
| ***countMSB-Downlink***                                               |
|                                                                       |
| Indicates the value of 25 MSBs from RX_NEXT -- 1 (specified in TS     |
| 38.323 \[5\]) associated to this DRB.                                 |
+-----------------------------------------------------------------------+
| ***countMSB-Uplink***                                                 |
|                                                                       |
| Indicates the value of 25 MSBs from TX_NEXT -- 1 (specified in TS     |
| 38.323 \[5\]) associated to this DRB.                                 |
+-----------------------------------------------------------------------+

#### -- *CounterCheckResponse*

The *CounterCheckResponse* message is used by the UE to respond to a
*CounterCheck* message.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*CounterCheckResponse message*

\-- ASN1START

\-- TAG-COUNTERCHECKRESPONSE-START

CounterCheckResponse ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

counterCheckResponse CounterCheckResponse-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

CounterCheckResponse-IEs ::= SEQUENCE {

drb-CountInfoList DRB-CountInfoList,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

DRB-CountInfoList ::= SEQUENCE (SIZE (0..maxDRB)) OF DRB-CountInfo

DRB-CountInfo ::= SEQUENCE {

drb-Identity DRB-Identity,

count-Uplink INTEGER(0..4294967295),

count-Downlink INTEGER(0..4294967295)

}

\-- TAG-COUNTERCHECKRESPONSE-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *CounterCheckResponse-IEs* field descriptions                         |
+=======================================================================+
| ***drb-CountInfoList***                                               |
|                                                                       |
| Indicates the COUNT values of the DRBs.                               |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *DRB-CountInfo* field descriptions                                    |
+=======================================================================+
| ***count-Downlink***                                                  |
|                                                                       |
| Indicates the value of RX_NEXT -- 1 (specified in TS 38.323 \[5\])    |
| associated to this DRB.                                               |
+-----------------------------------------------------------------------+
| ***count-Uplink***                                                    |
|                                                                       |
| Indicates the value of TX_NEXT -- 1 (specified in TS 38.323 \[5\])    |
| associated to this DRB.                                               |
+-----------------------------------------------------------------------+

#### -- *DedicatedSIBRequest*

The *DedicatedSIBRequest* message is used to request SIB(s) required by
the UE in RRC_CONNECTED as specified in clause 5.2.2.3.5.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*DedicatedSIBRequest message*

\-- ASN1START

\-- TAG-DEDICATEDSIBREQUEST-START

DedicatedSIBRequest-r16 ::= SEQUENCE {

criticalExtensions CHOICE {

dedicatedSIBRequest-r16 DedicatedSIBRequest-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

DedicatedSIBRequest-r16-IEs ::= SEQUENCE {

onDemandSIB-RequestList-r16 SEQUENCE {

requestedSIB-List-r16 SEQUENCE (SIZE (1..maxOnDemandSIB-r16)) OF
SIB-ReqInfo-r16 OPTIONAL,

requestedPosSIB-List-r16 SEQUENCE (SIZE (1..maxOnDemandPosSIB-r16)) OF
PosSIB-ReqInfo-r16 OPTIONAL

} OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

SIB-ReqInfo-r16 ::= ENUMERATED { sib12, sib13, sib14, sib20-v1700,
sib21-v1700, sib23-v1810, spare2, spare1 }

PosSIB-ReqInfo-r16 ::= SEQUENCE {

gnss-id-r16 GNSS-ID-r16 OPTIONAL,

sbas-id-r16 SBAS-ID-r16 OPTIONAL,

posSibType-r16 ENUMERATED { posSibType1-1, posSibType1-2, posSibType1-3,
posSibType1-4, posSibType1-5, posSibType1-6,

posSibType1-7, posSibType1-8, posSibType2-1, posSibType2-2,
posSibType2-3, posSibType2-4,

posSibType2-5, posSibType2-6, posSibType2-7, posSibType2-8,
posSibType2-9, posSibType2-10,

posSibType2-11, posSibType2-12, posSibType2-13, posSibType2-14,
posSibType2-15,

posSibType2-16, posSibType2-17, posSibType2-18, posSibType2-19,
posSibType2-20,

posSibType2-21, posSibType2-22, posSibType2-23, posSibType3-1,
posSibType4-1,

posSibType5-1, posSibType6-1, posSibType6-2, posSibType6-3,\...,
posSibType1-9-v1710,

posSibType1-10-v1710, posSibType2-24-v1710, posSibType2-25-v1710,

posSibType6-4-v1710, posSibType6-5-v1710, posSibType6-6-v1710,
posSibType2-17a-v1770,

posSibType2-18a-v1770, posSibType2-20a-v1770, posSibType1-11-v1800,
posSibType1-12-v1800,

posSibType2-26-v1800, posSibType2-27-v1800, posSibType6-7-v1800,
posSibType7-1-v1800,

posSibType7-2-v1800, posSibType7-3-v1800, posSibType7-4-v1800 }

}

\-- TAG-DEDICATEDSIBREQUEST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *DedicatedSIBRequest field descriptions*                              |
+=======================================================================+
| ***requestedSIB-List***                                               |
|                                                                       |
| Contains a list of SIB(s) the UE requests while in RRC_CONNECTED.     |
+-----------------------------------------------------------------------+
| ***requestedPosSIB-List***                                            |
|                                                                       |
| Contains a list of posSIB(s) the UE requests while in RRC_CONNECTED.  |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *PosSIB-ReqInfo* field descriptions                                   |
+=======================================================================+
| ***gnss-id***                                                         |
|                                                                       |
| The presence of this field indicates that the request positioning SIB |
| type is for a specific GNSS. Indicates a specific GNSS (see also TS   |
| 37.355 \[49\])                                                        |
+-----------------------------------------------------------------------+
| ***sbas-id***                                                         |
|                                                                       |
| The presence of this field indicates that the request positioning SIB |
| type is for a specific SBAS. Indicates a specific SBAS (see also TS   |
| 37.355 \[49\]). If the UE includes this field it shall set *gnss-id*  |
| to *sbas*.                                                            |
+-----------------------------------------------------------------------+

#### -- *DLDedicatedMessageSegment*

The *DLDedicatedMessageSegment* message is used to transfer one segment
of the *RRCResume* or *RRCReconfiguration* messages.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*DLDedicatedMessageSegment message*

\-- ASN1START

\-- TAG-DLDEDICATEDMESSAGESEGMENT-START

DLDedicatedMessageSegment-r16 ::= SEQUENCE {

criticalExtensions CHOICE {

dlDedicatedMessageSegment-r16 DLDedicatedMessageSegment-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

DLDedicatedMessageSegment-r16-IEs ::= SEQUENCE {

segmentNumber-r16 INTEGER(0..4),

rrc-MessageSegmentContainer-r16 OCTET STRING,

rrc-MessageSegmentType-r16 ENUMERATED {notLastSegment, lastSegment},

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-DLDEDICATEDMESSAGESEGMENT-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *DLDedicatedMessageSegment* field descriptions                        |
+=======================================================================+
| ***segmentNumber***                                                   |
|                                                                       |
| Identifies the sequence number of a segment within the encoded DL     |
| DCCH message. The network transmits the segments with continuously    |
| increasing *segmentNumber* order so that the UE\'s RRC layer may      |
| expect to obtain them from lower layers in the correct order. Hence,  |
| the UE is not required to perform segment re-ordering on RRC level.   |
+-----------------------------------------------------------------------+
| ***rrc-MessageSegmentContainer***                                     |
|                                                                       |
| Includes a segment of the encoded DL DCCH message. The size of the    |
| included segment in this container should be small enough so the      |
| resulting encoded RRC message PDU is less than or equal to the PDCP   |
| SDU size limit.                                                       |
+-----------------------------------------------------------------------+
| ***rrc-MessageSegmentType***                                          |
|                                                                       |
| Indicates whether the included DL DCCH message segment is the last    |
| segment of the message or not.                                        |
+-----------------------------------------------------------------------+

#### -- *DLInformationTransfer*

The *DLInformationTransfer* message is used for the downlink transfer of
NAS dedicated information, timing information for the 5G internal system
clock, or IAB-DU specific F1-C related information.

Signalling radio bearer: SRB2 or SRB1 (only if SRB2 not established
yet). If SRB2 is suspended, the network does not send this message until
SRB2 is resumed. If only *dedicatedInfoF1c* is included, SRB2 is used.

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*DLInformationTransfer* message

\-- ASN1START

\-- TAG-DLINFORMATIONTRANSFER-START

DLInformationTransfer ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

dlInformationTransfer DLInformationTransfer-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

DLInformationTransfer-IEs ::= SEQUENCE {

dedicatedNAS-Message DedicatedNAS-Message OPTIONAL, \-- Need N

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension DLInformationTransfer-v1610-IEs OPTIONAL

}

DLInformationTransfer-v1610-IEs ::= SEQUENCE {

referenceTimeInfo-r16 ReferenceTimeInfo-r16 OPTIONAL, \-- Need N

nonCriticalExtension DLInformationTransfer-v1700-IEs OPTIONAL

}

DLInformationTransfer-v1700-IEs ::= SEQUENCE {

dedicatedInfoF1c-r17 DedicatedInfoF1c-r17 OPTIONAL, \-- Need N

rxTxTimeDiff-gNB-r17 RxTxTimeDiff-r17 OPTIONAL, \-- Need N

ta-PDC-r17 ENUMERATED {activate,deactivate} OPTIONAL, \-- Need N

sib9Fallback-r17 ENUMERATED {true} OPTIONAL, \-- Need N

nonCriticalExtension DLInformationTransfer-v1800-IEs OPTIONAL

}

DLInformationTransfer-v1800-IEs ::= SEQUENCE {

eventID-TSS-r18 INTEGER(0..63) OPTIONAL, \-- Cond
ClockQualityDetailsLevel

clockQualityDetailsLevel-r18 CHOICE {

clockQualityMetrics-r18 ClockQualityMetrics-r18,

clockQualityAcceptanceStatus-r18 ENUMERATED {acceptable, notAcceptable}

} OPTIONAL, \-- Need N

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-DLINFORMATIONTRANSFER-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *DLInformationTransfer* field descriptions                            |
+=======================================================================+
| ***clockQualityDetailsLevel***                                        |
|                                                                       |
| This field indicates the clock quality reporting control information  |
| as defined in TS 23.501 \[32\].                                       |
+-----------------------------------------------------------------------+
| ***eventID-TSS***                                                     |
|                                                                       |
| This field indicates the status of the 5G access stratum time         |
| distribution parameter Clock Quality Reporting Control Information as |
| defined in TS 23.501 \[32\].                                          |
+-----------------------------------------------------------------------+
| ***rxTxTimeDiff-gNB***                                                |
|                                                                       |
| Indicates the Rx-Tx time difference measurement at the gNB (see       |
| clause 5.2.3, TS 38.215 \[9\]). Upon receiving this field, the UE     |
| calculates the propagation delay based on the RTT-based PDC mechanism |
| method as described in TS 38.300 \[2\]. The network does not          |
| configure this field, if the UE is configured with *ta-PDC* with      |
| value *activate*.                                                     |
+-----------------------------------------------------------------------+
| ***sib9Fallback***                                                    |
|                                                                       |
| Indicates that the UE fallbacks to receive *referenceTimeInfo* in     |
| SIB9.                                                                 |
+-----------------------------------------------------------------------+
| ***ta-PDC***                                                          |
|                                                                       |
| Indicates whether the UE-side TA-based propagation delay compensation |
| (PDC) is activated or de-activated. The network does not configure    |
| this field with *activate,* if the field *rxTxTimeDiff-gNB* is        |
| configured.                                                           |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------------------
  Conditional Presence             Explanation
  -------------------------------- --------------------------------------------------
  ***ClockQualityDetailsLevel***   Field *eventID-TSS* is mandatory present if
                                   *clockQualityDetailsLevel* is present. Otherwise,
                                   the field is optionally present, Need M.

  -----------------------------------------------------------------------------------

#### *-- DLInformationTransferMRDC*

The *DLInformationTransferMRDC* message is used for the downlink
transfer of RRC messages during fast MCG link recovery.

Signalling radio bearer: SRB3

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*DLInformationTransferMRDC message*

\-- ASN1START

\-- TAG-DLINFORMATIONTRANSFERMRDC-START

DLInformationTransferMRDC-r16 ::= SEQUENCE {

criticalExtensions CHOICE {

c1 CHOICE {

dlInformationTransferMRDC-r16 DLInformationTransferMRDC-r16-IEs,

spare3 NULL, spare2 NULL, spare1 NULL

},

criticalExtensionsFuture SEQUENCE {}

}

}

DLInformationTransferMRDC-r16-IEs::= SEQUENCE {

dl-DCCH-MessageNR-r16 OCTET STRING OPTIONAL, \-- Need N

dl-DCCH-MessageEUTRA-r16 OCTET STRING OPTIONAL, \-- Need N

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-DLINFORMATIONTRANSFERMRDC-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *DLInformationTransferMRDC* field descriptions                        |
+=======================================================================+
| ***dl-DCCH-MessageNR***                                               |
|                                                                       |
| Includes the *DL-DCCH-Message*. In this version of the specification, |
| the field is only used to transfer the NR *RRCReconfiguration,*       |
| *RRCRelease,* and *MobilityFromNRCommand* messages.                   |
+-----------------------------------------------------------------------+
| ***dl-DCCH-MessageEUTRA***                                            |
|                                                                       |
| Includes the *DL-DCCH-Message*. In this version of the specification, |
| the field is only used to transfer the E-UTRA                         |
| *RRCConnectionReconfiguration,* *RRCConnectionRelease*, and           |
| *MobilityFromEUTRACommand* messages as specified in TS 36.331 \[10\]. |
+-----------------------------------------------------------------------+

#### -- *FailureInformation*

The *FailureInformation* message is used to inform the network about a
failure detected by the UE.

Signalling radio bearer: SRB1 or SRB3

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to network

*FailureInformation message*

\-- ASN1START

\-- TAG-FAILUREINFORMATION-START

FailureInformation ::= SEQUENCE {

criticalExtensions CHOICE {

failureInformation FailureInformation-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

FailureInformation-IEs ::= SEQUENCE {

failureInfoRLC-Bearer FailureInfoRLC-Bearer OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension FailureInformation-v1610-IEs OPTIONAL

}

FailureInfoRLC-Bearer ::= SEQUENCE {

cellGroupId CellGroupId,

logicalChannelIdentity LogicalChannelIdentity,

failureType ENUMERATED {rlc-failure, spare3, spare2, spare1}

}

FailureInformation-v1610-IEs ::= SEQUENCE {

failureInfoDAPS-r16 FailureInfoDAPS-r16 OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

FailureInfoDAPS-r16 ::= SEQUENCE {

failureType-r16 ENUMERATED {daps-failure, spare3, spare2, spare1}

}

\-- TAG-FAILUREINFORMATION-STOP

\-- ASN1STOP

#### -- *IABOtherInformation*

The *IABOtherInformation* message is used by IAB-MT to request the
network to allocate IP addresses for the collocated IAB-DU or inform the
network about IP addresses allocated to the collocated IAB-DU.

Signalling radio bearer: SRB1 or SRB3

RLC-SAP: AM

Logical channel: DCCH

Direction: IAB-MT to Network

*IABOtherInformation* message

\-- ASN1START

\-- TAG-IABOTHERINFORMATION-START

IABOtherInformation-r16 ::= SEQUENCE {

dummy RRC-TransactionIdentifier,

criticalExtensions CHOICE {

iabOtherInformation-r16 IABOtherInformation-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

IABOtherInformation-r16-IEs ::= SEQUENCE {

ip-InfoType-r16 CHOICE {

iab-IP-Request-r16 SEQUENCE {

iab-IPv4-AddressNumReq-r16 IAB-IP-AddressNumReq-r16 OPTIONAL,

iab-IPv6-AddressReq-r16 CHOICE {

iab-IPv6-AddressNumReq-r16 IAB-IP-AddressNumReq-r16,

iab-IPv6-AddressPrefixReq-r16 IAB-IP-AddressPrefixReq-r16,

\...

} OPTIONAL

},

iab-IP-Report-r16 SEQUENCE {

iab-IPv4-AddressReport-r16 IAB-IP-AddressAndTraffic-r16 OPTIONAL,

iab-IPv6-Report-r16 CHOICE {

iab-IPv6-AddressReport-r16 IAB-IP-AddressAndTraffic-r16,

iab-IPv6-PrefixReport-r16 IAB-IP-PrefixAndTraffic-r16,

\...

} OPTIONAL

},

\...

},

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

IAB-IP-AddressNumReq-r16 ::= SEQUENCE {

all-Traffic-NumReq-r16 INTEGER (1..8) OPTIONAL,

f1-C-Traffic-NumReq-r16 INTEGER (1..8) OPTIONAL,

f1-U-Traffic-NumReq-r16 INTEGER (1..8) OPTIONAL,

non-F1-Traffic-NumReq-r16 INTEGER (1..8) OPTIONAL,

\...

}

IAB-IP-AddressPrefixReq-r16 ::= SEQUENCE {

all-Traffic-PrefixReq-r16 ENUMERATED {true} OPTIONAL,

f1-C-Traffic-PrefixReq-r16 ENUMERATED {true} OPTIONAL,

f1-U-Traffic-PrefixReq-r16 ENUMERATED {true} OPTIONAL,

non-F1-Traffic-PrefixReq-r16 ENUMERATED {true} OPTIONAL,

\...

}

IAB-IP-AddressAndTraffic-r16 ::= SEQUENCE {

all-Traffic-IAB-IP-Address-r16 SEQUENCE (SIZE(1..8)) OF
IAB-IP-Address-r16 OPTIONAL,

f1-C-Traffic-IP-Address-r16 SEQUENCE (SIZE(1..8)) OF IAB-IP-Address-r16
OPTIONAL,

f1-U-Traffic-IP-Address-r16 SEQUENCE (SIZE(1..8)) OF IAB-IP-Address-r16
OPTIONAL,

non-F1-Traffic-IP-Address-r16 SEQUENCE (SIZE(1..8)) OF
IAB-IP-Address-r16 OPTIONAL

}

IAB-IP-PrefixAndTraffic-r16 ::= SEQUENCE {

all-Traffic-IAB-IP-Address-r16 IAB-IP-Address-r16 OPTIONAL,

f1-C-Traffic-IP-Address-r16 IAB-IP-Address-r16 OPTIONAL,

f1-U-Traffic-IP-Address-r16 IAB-IP-Address-r16 OPTIONAL,

non-F1-Traffic-IP-Address-r16 IAB-IP-Address-r16 OPTIONAL

}

\-- TAG-IABOTHERINFORMATION-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *IABOtherInformation-IEs* field descriptions                          |
+=======================================================================+
| ***dummy***                                                           |
|                                                                       |
| This field is not used in the specification and network ignores the   |
| received value.                                                       |
+-----------------------------------------------------------------------+
| ***iab-IPv4-AddressNumReq***                                          |
|                                                                       |
| This field is used to request the numbers of IPv4 address per         |
| specific usage. The specific usages include F1-C traffic, F1-U        |
| traffic, non-F1 traffic and all traffic.                              |
+-----------------------------------------------------------------------+
| ***iab-IPv4-AddressReport***                                          |
|                                                                       |
| This field is used to report the IPv4 address per specific usage      |
| assigned by OAM for IAB-DU. The specific usages include F1-C traffic, |
| F1-U traffic, non-F1 traffic and all traffic.                         |
+-----------------------------------------------------------------------+
| ***iab-IPv6-AddressNumReq***                                          |
|                                                                       |
| This field is used to request the numbers of IPv6 address per         |
| specific usage. The specific usages include F1-C traffic, F1-U        |
| traffic, non-F1 traffic and all traffic.                              |
+-----------------------------------------------------------------------+
| ***iab-IPv6-AddressPrefixReq***                                       |
|                                                                       |
| This field is used to request the prefix of IPv6 address per specific |
| usage. The specific usages include F1-C traffic, F1-U traffic, non-F1 |
| traffic and all traffic.                                              |
+-----------------------------------------------------------------------+
| ***iab-IPv6-AddressReport***                                          |
|                                                                       |
| This field is used to report the IPv6 address per specific usage      |
| assigned by OAM for IAB-DU. The specific usages include F1-C traffic, |
| F1-U traffic, non-F1 traffic and all traffic.                         |
+-----------------------------------------------------------------------+
| ***iab-IPv6-PrefixReport***                                           |
|                                                                       |
| This field is used to report the prefix of IPv6 address per specific  |
| usage assigned by OAM for IAB-DU. The specific usages include F1-C    |
| traffic, F1-U traffic, non-F1 traffic and all traffic.                |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *IAB-IP-AddressNumReq-IEs field descriptions*                         |
+=======================================================================+
| ***all-Traffic-NumReq***                                              |
|                                                                       |
| This field is used to request the numbers of IP address for all       |
| traffic.                                                              |
+-----------------------------------------------------------------------+
| ***f1-C-Traffic-NumReq***                                             |
|                                                                       |
| This field is used to request the numbers of IP address for F1-C      |
| traffic.                                                              |
+-----------------------------------------------------------------------+
| ***f1-U-Traffic-NumReq***                                             |
|                                                                       |
| This field is used to request the numbers of IP address for F1-U      |
| traffic.                                                              |
+-----------------------------------------------------------------------+
| ***non-F1-Traffic-NumReq***                                           |
|                                                                       |
| This field is used to request the numbers of IP address for non-F1    |
| traffic.                                                              |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *IAB-IP-AddressPrefixReq-IEs field descriptions*                      |
+=======================================================================+
| ***all-Traffic-PrefixReq***                                           |
|                                                                       |
| This field is used to request the IPv6 address prefix for all         |
| traffic. The length of allocated IPv6 prefix is fixed to 64.          |
+-----------------------------------------------------------------------+
| ***f1-C-Traffic-PrefixReq***                                          |
|                                                                       |
| This field is used to request the IPv6 address prefix for F1-C        |
| traffic. The length of allocated IPv6 prefix is fixed to 64.          |
+-----------------------------------------------------------------------+
| ***f1-U-Traffic-PrefixReq***                                          |
|                                                                       |
| This field is used to request the IPv6 address prefix for F1-U        |
| traffic. The length of allocated IPv6 prefix is fixed to 64.          |
+-----------------------------------------------------------------------+
| ***non-F1-Traffic-PrefixReq***                                        |
|                                                                       |
| This field is used to request the IPv6 address prefix for non-F1      |
| traffic. The length of allocated IPv6 prefix is fixed to 64.          |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *IAB-IP-AddressAndTraffic-IEs field descriptions*                     |
+=======================================================================+
| ***all-Traffic-IAB-IP-Address***                                      |
|                                                                       |
| This field is used to report to IAB-donor-CU the IP address(es) or    |
| IPv6 address prefix for all traffic.                                  |
+-----------------------------------------------------------------------+
| ***f1-C-Traffic-IP-Address***                                         |
|                                                                       |
| This field is used to report to IAB-donor-CU the IP address(es) or    |
| IPv6 address prefix for F1-C traffic.                                 |
+-----------------------------------------------------------------------+
| ***f1-U-Traffic-IP-Address***                                         |
|                                                                       |
| This field is used to report to IAB-donor-CU the IP address(es) or    |
| IPv6 address prefix for F1-U traffic.                                 |
+-----------------------------------------------------------------------+
| ***non-F1-Traffic-IP-Address***                                       |
|                                                                       |
| This field is used to report to IAB-donor-CU the IP address(es) or    |
| IPv6 address prefix for non-F1 traffic.                               |
+-----------------------------------------------------------------------+

#### *-- IndirectPathFailureInformation*

The *IndirectPathFailureInformation* message is used to provide
information regarding indirect path failure detected by the MP remote
UE.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*IndirectPathFailureInformation* message

\-- ASN1START

\-- TAG-INDIRECTPATHFAILUREINFORMATION-START

IndirectPathFailureInformation-r18 ::= SEQUENCE {

criticalExtensions CHOICE {

indirectPathFailureInformation-r18
IndirectPathFailureInformation-r18-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

IndirectPathFailureInformation-r18-IEs ::= SEQUENCE {

failureReportIndirectPath-r18 FailureReportIndirectPath-r18 OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

FailureReportIndirectPath-r18 ::= SEQUENCE {

failureTypeIndirectPath-r18 ENUMERATED
{t421-Expiry,sl-Failure,n3c-Failure, relayUE-Uu-RLF,

relayUE-Uu-RRC-Failure,

indirectPathAddChangeFailure, sl-PC5-Release, spare1} OPTIONAL,

sl-MeasResultServingRelay-r18 OCTET STRING OPTIONAL,

\-- Contains PC5 SL-MeasResultRelay-r17

sl-MeasResultsCandRelay-r18 OCTET STRING OPTIONAL,

n3c-RelayUE-InfoList-r18 SEQUENCE (SIZE (0..8)) OF N3C-RelayUE-Info-r18
OPTIONAL,

\...

}

\-- TAG-INDIRECTPATHFAILUREINFORMATION-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *IndirectPathFailureInformation* field descriptions                   |
+-----------------------------------------------------------------------+
| ***failureTypeIndirectPath***                                         |
|                                                                       |
| The field indicates the failure type of the indirect path failure.    |
+-----------------------------------------------------------------------+
| ***n3c-RelayUE-InfoList***                                            |
|                                                                       |
| Information of available N3C relay UE(s).                             |
+-----------------------------------------------------------------------+
| ***sl-MeasResultsCandRelay***                                         |
|                                                                       |
| Measurement result(s) of candiate L2 U2N relay UE(s).                 |
+-----------------------------------------------------------------------+
| ***sl-MeasResultServingRelay***                                       |
|                                                                       |
| Measurement result of serving L2 U2N relay UE.                        |
+=======================================================================+

#### -- *LocationMeasurementIndication*

The *LocationMeasurementIndication* message is used to indicate that the
UE is going to either start or stop location related measurement which
requires measurement gaps.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*LocationMeasurementIndication message*

\-- ASN1START

\-- TAG-LOCATIONMEASUREMENTINDICATION-START

LocationMeasurementIndication ::= SEQUENCE {

criticalExtensions CHOICE {

locationMeasurementIndication LocationMeasurementIndication-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

LocationMeasurementIndication-IEs ::= SEQUENCE {

measurementIndication SetupRelease {LocationMeasurementInfo},

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

\-- TAG-LOCATIONMEASUREMENTINDICATION-STOP

\-- ASN1STOP

#### -- *LoggedMeasurementConfiguration*

The *LoggedMeasurementConfiguration* message is used to perform logging
of measurement results while in RRC_IDLE or RRC_INACTIVE. It is used to
transfer the logged measurement configuration for network performance
optimisation.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*LoggedMeasurementConfiguration message*

\-- ASN1START

\-- TAG-LOGGEDMEASUREMENTCONFIGURATION-START

LoggedMeasurementConfiguration-r16 ::= SEQUENCE {

criticalExtensions CHOICE {

loggedMeasurementConfiguration-r16
LoggedMeasurementConfiguration-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

LoggedMeasurementConfiguration-r16-IEs ::= SEQUENCE {

traceReference-r16 TraceReference-r16,

traceRecordingSessionRef-r16 OCTET STRING (SIZE (2)),

tce-Id-r16 OCTET STRING (SIZE (1)),

absoluteTimeInfo-r16 AbsoluteTimeInfo-r16,

areaConfiguration-r16 AreaConfiguration-r16 OPTIONAL, \--Need R

plmn-IdentityList-r16 PLMN-IdentityList2-r16 OPTIONAL, \--Need R

bt-NameList-r16 SetupRelease {BT-NameList-r16} OPTIONAL, \--Need M

wlan-NameList-r16 SetupRelease {WLAN-NameList-r16} OPTIONAL, \--Need M

sensor-NameList-r16 SetupRelease {Sensor-NameList-r16} OPTIONAL, \--Need
M

loggingDuration-r16 LoggingDuration-r16,

reportType CHOICE {

periodical LoggedPeriodicalReportConfig-r16,

eventTriggered LoggedEventTriggerConfig-r16,

\...

},

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension LoggedMeasurementConfiguration-v1700-IEs OPTIONAL

}

LoggedMeasurementConfiguration-v1700-IEs ::= SEQUENCE {

sigLoggedMeasType-r17 ENUMERATED {true} OPTIONAL, \-- Need R

earlyMeasIndication-r17 ENUMERATED {true} OPTIONAL, \-- Need R

areaConfiguration-r17 AreaConfiguration-r17 OPTIONAL, \--Need R

nonCriticalExtension LoggedMeasurementConfiguration-v1800-IEs OPTIONAL

}

LoggedMeasurementConfiguration-v1800-IEs ::= SEQUENCE {

areaConfiguration-v1800 AreaConfiguration-v1800 OPTIONAL, \--Need R

nonCriticalExtension SEQUENCE {} OPTIONAL

}

LoggedPeriodicalReportConfig-r16 ::= SEQUENCE {

loggingInterval-r16 LoggingInterval-r16,

\...

}

LoggedEventTriggerConfig-r16 ::= SEQUENCE {

eventType-r16 EventType-r16,

loggingInterval-r16 LoggingInterval-r16,

\...

}

EventType-r16 ::= CHOICE {

outOfCoverage NULL,

eventL1 SEQUENCE {

l1-Threshold MeasTriggerQuantity,

hysteresis Hysteresis,

timeToTrigger TimeToTrigger

},

\...

}

\-- TAG-LOGGEDMEASUREMENTCONFIGURATION-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *LoggedMeasurementConfiguration* field descriptions                   |
+-----------------------------------------------------------------------+
| ***absoluteTimeInfo***                                                |
|                                                                       |
| Indicates the absolute time in the current cell.                      |
+-----------------------------------------------------------------------+
| ***areaConfiguration***                                               |
|                                                                       |
| Used to restrict the area in which the UE performs measurement        |
| logging to cells broadcasting any of the included cell identities,    |
| the included tracking area codes/ frequencies, the included PNI-NPN   |
| identities or the SNPN identities. If *areaConfiguration-r17* is      |
| present, the UE shall ignore *areaConfiguration-r16*. The             |
| *areaConfiguration-v180*0 is a non-critical extension of              |
| *areaConfiguration-r17*. See NOTE 1.                                  |
+-----------------------------------------------------------------------+
| ***earlyMeasIndication***                                             |
|                                                                       |
| If included, the field indicates the UE is allowed to log             |
| measurements on early measurement related frequencies in logged       |
| measurements.                                                         |
+-----------------------------------------------------------------------+
| ***eventType***                                                       |
|                                                                       |
| The value outOfCoverage indicates the UE to perform logging of        |
| measurements when the UE enters any cell selection state, and the     |
| value eventL1 indicates the UE to perform logging of measurements     |
| when the triggering condition (similar as event A2 as specified in    |
| 5.5.4.3) as configured in the event is met for the camping cell in    |
| camped normally state.                                                |
+-----------------------------------------------------------------------+
| ***plmn-IdentityList***                                               |
|                                                                       |
| Indicates a set of PLMNs defining when the UE performs measurement    |
| logging as well as the associated status indication and information   |
| retrieval i.e. the UE performs these actions when the RPLMN is part   |
| of this set of PLMNs. The network does not include this field when    |
| the UE is configured with MDT configuration in SNPN access mode.      |
+-----------------------------------------------------------------------+
| ***sigLoggedMeasType***                                               |
|                                                                       |
| If included, the field indicates a signalling based logged            |
| measurement configuration (See TS 37.320 \[61\]).                     |
+-----------------------------------------------------------------------+
| ***tce-Id***                                                          |
|                                                                       |
| Parameter Trace Collection Entity Id: See TS 32.422 \[52\].           |
+-----------------------------------------------------------------------+
| ***traceRecordingSessionRef***                                        |
|                                                                       |
| Parameter Trace Recording Session Reference: See TS 32.422 \[52\].    |
+-----------------------------------------------------------------------+
| ***reportType***                                                      |
|                                                                       |
| Parameter configures the type of MDT configuration, specifically      |
| Periodic MDT configuration or Event Triggerd MDT configuration.       |
+=======================================================================+

NOTE 1: The UE should perform measurement logging based on the following
area configuration limitations:

\- If the *areaConfiguration-r16/areaConfiguration-r17* is present, and
the *cag-ConfigList* is absent, the UE should perform logging in both PN
and PNI-NPN based on *areaConfiguration-r16/areaConfiguration-r17*, if
any;

\- If the *areaConfiguration-r17* and the *cag-ConfigList* are present
simultaneously, the UE should perform logging in PN within the
*areaConfig-r16/areaConfig-r17* and perform logging in PNI-NPN within
*cag-ConfigList*;

\- If the *snpn-ConfigList* is present, the UE should perform logging
only in SNPN based on *snpn-ConfigList*. The *snpn-ConfigList* should
not be configured together with PN or PNI-NPN area configurations.

#### *-- MBSBroadcastConfiguration*

The *MBSBroadcastConfiguration* message contains the control information
applicable for MBS broadcast services transmitted via broadcast MRB.

Signalling radio bearer: N/A

RLC-SAP: UM

Logical channel: MCCH

Direction: Network to UE

*MBSBroadcastConfiguration message*

\-- ASN1START

\-- TAG-MBSBROADCASTCONFIGURATION-START

MBSBroadcastConfiguration-r17 ::= SEQUENCE {

criticalExtensions CHOICE {

mbsBroadcastConfiguration-r17 MBSBroadcastConfiguration-r17-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

MBSBroadcastConfiguration-r17-IEs ::= SEQUENCE {

mbs-SessionInfoList-r17 MBS-SessionInfoList-r17 OPTIONAL, \-- Need R

mbs-NeighbourCellList-r17 MBS-NeighbourCellList-r17 OPTIONAL, \-- Need S

drx-ConfigPTM-List-r17 SEQUENCE (SIZE (1..maxNrofDRX-ConfigPTM-r17)) OF
DRX-ConfigPTM-r17 OPTIONAL, \-- Need R

pdsch-ConfigMTCH-r17 PDSCH-ConfigBroadcast-r17 OPTIONAL, \-- Need S

mtch-SSB-MappingWindowList-r17 MTCH-SSB-MappingWindowList-r17 OPTIONAL,
\-- Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-MBSBROADCASTCONFIGURATION-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MBSBroadcastConfiguration* field descriptions                        |
+=======================================================================+
| ***pdsch-ConfigMTCH***                                                |
|                                                                       |
| Provides parameters for acquiring the PDSCH for MTCH. When this field |
| is absent, the UE shall use parameters in *pdsch-ConfigMCCH* to       |
| acquire the PDSCH for MTCH.                                           |
+-----------------------------------------------------------------------+
| ***mbs-SessionInfoList***                                             |
|                                                                       |
| Provides the configuration of each MBS session provided by MBS        |
| broadcast in the current cell.                                        |
+-----------------------------------------------------------------------+
| ***mbs-NeighbourCellList***                                           |
|                                                                       |
| List of neighbour cells providing one or more MBS broadcast services  |
| via broadcast MRB that are provided by the current cell. This field   |
| is used by the UE together with *mtch-NeighbourCell* field signalled  |
| for each MBS session in the corresponding *MBS-SessionInfo*. When an  |
| empty *mbs-NeighbourCellList* list is signalled, the UE shall assume  |
| that MBS broadcast services signalled in *mbs-SessionInfoList* in the |
| *MBSBroadcastConfiguration* message are not provided in any neighbour |
| cell. When a non-empty *mbs-NeighbourCellList* is signalled, the      |
| current serving cell does not provide information about MBS broadcast |
| services of a neighbour cell that is not included in                  |
| *mbs-NeighbourCellList*, i.e., the UE cannot determine the presence   |
| or absence of an MBS service of a neighbour cell that is absent. When |
| the field *mbs-NeighbourCellList* is absent, the current serving cell |
| does not provide information about MBS broadcast services in the      |
| neighbouring cells, i.e. the UE cannot determine the presence or      |
| absence of an MBS service in neighbouring cells based on the absence  |
| of this field.                                                        |
+-----------------------------------------------------------------------+

#### *-- MBSInterestIndication*

The *MBSInterestIndication* message is used to inform network that the
UE is receiving/ interested to receive or no longer receiving/
interested to receive MBS broadcast service(s) via a broadcast MRB.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*MBSInterestIndication message*

\-- ASN1START

\-- TAG-MBSINTERESTINDICATION-START

MBSInterestIndication-r17 ::= SEQUENCE {

criticalExtensions CHOICE {

mbsInterestIndication-r17 MBSInterestIndication-r17-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

MBSInterestIndication-r17-IEs ::= SEQUENCE {

mbs-FreqList-r17 CarrierFreqListMBS-r17 OPTIONAL,

mbs-Priority-r17 ENUMERATED {true} OPTIONAL,

mbs-ServiceList-r17 MBS-ServiceList-r17 OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension MBSInterestIndication-v1800 OPTIONAL

}

MBSInterestIndication-v1800 ::= SEQUENCE {

mbs-NonServingInfoList-r18 MBS-NonServingInfoList-r18 OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-MBSINTERESTINDICATION-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MBSInterestIndication* field descriptions                            |
+=======================================================================+
| ***mbs-FreqList***                                                    |
|                                                                       |
| List of MBS frequencies on which the UE is receiving or interested to |
| receive MBS broadcast service via a broadcast MRB.                    |
+-----------------------------------------------------------------------+
| ***mbs-NonServingInfoList***                                          |
|                                                                       |
| Indicates information for MBS broadcast reception on the non-serving  |
| cell.                                                                 |
+-----------------------------------------------------------------------+
| ***mbs-Priority***                                                    |
|                                                                       |
| Indicates whether the UE prioritises MBS broadcast reception above    |
| unicast and MBS multicast reception. The field is present (i.e. value |
| *true*), if the UE prioritises reception of broadcast services, on    |
| frequencies indicated in *mbs-FreqLis*t, above a reception of any of  |
| the unicast bearers and multicast MRBs. Otherwise the field is        |
| absent.                                                               |
+-----------------------------------------------------------------------+
| ***mbs-ServiceList***                                                 |
|                                                                       |
| List of MBS broadcast services which the UE is receiving or           |
| interested to receive.                                                |
+-----------------------------------------------------------------------+

#### *-- MBSMulticastConfiguration*

The *MBSMulticastConfiguration* message contains the control information
applicable for MBS multicast services transmitted via multicast MRBs for
RRC_INACTIVE UEs.

Signalling radio bearer: N/A

RLC-SAP: UM

Logical channel: multicast MCCH

Direction: Network to UE

*MBSMulticastConfiguration* message

\-- ASN1START

\-- TAG-MBSMULTICASTCONFIGURATION-START

MBSMulticastConfiguration-r18 ::= SEQUENCE {

criticalExtensions CHOICE {

mbsMulticastConfiguration-r18 MBSMulticastConfiguration-r18-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

MBSMulticastConfiguration-r18-IEs ::= SEQUENCE {

mbs-SessionInfoListMulticast-r18 MBS-SessionInfoListMulticast-r18
OPTIONAL, \-- Need R

mbs-NeighbourCellList-r18 MBS-NeighbourCellList-r17 OPTIONAL, \-- Need S

drx-ConfigPTM-List-r18 SEQUENCE (SIZE (1..maxNrofDRX-ConfigPTM-r17)) OF
DRX-ConfigPTM-r17 OPTIONAL, \-- Need R

pdsch-ConfigMTCH-r18 PDSCH-ConfigBroadcast-r17 OPTIONAL, \-- Need S

mtch-SSB-MappingWindowList-r18 MTCH-SSB-MappingWindowList-r17 OPTIONAL,
\-- Need R

thresholdMBS-List-r18 SEQUENCE (SIZE (1..maxNrofThresholdMBS-r18)) OF
ThresholdMBS-r18 OPTIONAL, \-- Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

ThresholdMBS-r18 ::= SEQUENCE {

rsrp-r18 RSRP-Range OPTIONAL, \-- Need R

rsrq-r18 RSRQ-Range OPTIONAL \-- Need R

}

\-- TAG-MBSMULTICASTCONFIGURATION-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MBSMulticastConfiguration* field descriptions                        |
+-----------------------------------------------------------------------+
| ***mbs-NeighbourCellList***                                           |
|                                                                       |
| List of neighbour cells providing one or more MBS multicast services  |
| for RRC_INACTIVE that are provided by the current cell. This field is |
| used by the UE together with *mtch-NeighbourCell* field signalled for |
| each MBS session in the corresponding *MBS-SessionInfo*. When an      |
| empty *mbs-NeighbourCellList* list is signalled, the UE shall assume  |
| that MBS multicast services signalled in                              |
| *mbs-SessionInfoListMulticast* in the *MBSMulticastConfiguration*     |
| message are not provided in any neighbour cell. When a non-empty      |
| *mbs-NeighbourCellList* is signalled, the current serving cell does   |
| not provide information about MBS multicast services of a neighbour   |
| cell that is not included in *mbs-NeighbourCellList*, i.e., the UE    |
| cannot determine the presence or absence of an MBS multicast service  |
| of a neighbour cell that is absent. When the field                    |
| *mbs-NeighbourCellList* is absent, the current serving cell does not  |
| provide information about MBS multicast services in the neighbouring  |
| cells, i.e. the UE cannot determine the presence or absence of an MBS |
| multicast service in neighbouring cells based on the absence of this  |
| field.                                                                |
+=======================================================================+
| ***mbs-SessionInfoListMulticast***                                    |
|                                                                       |
| Provides the configuration of MBS multicast session(s) in the current |
| cell.                                                                 |
+-----------------------------------------------------------------------+
| ***pdsch-ConfigMTCH***                                                |
|                                                                       |
| Provides parameters for acquiring the PDSCH for multicast MTCH. When  |
| this field is absent, the UE shall use parameters in                  |
| *pdsch-ConfigMCCH* in *SIB24* to acquire the PDSCH for multicast      |
| MTCH.                                                                 |
+-----------------------------------------------------------------------+
| ***thresholdMBS-List***                                               |
|                                                                       |
| List of reception quality thresholds for RRC connection resume for a  |
| UE receiving multicast in RRC_INACTIVE.                               |
+-----------------------------------------------------------------------+

#### *-- MCGFailureInformation*

The *MCGFailureInformation* message is used to provide information
regarding NR MCG failures detected by the UE.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*MCGFailureInformation* message

\-- ASN1START

\-- TAG-MCGFAILUREINFORMATION-START

MCGFailureInformation-r16 ::= SEQUENCE {

criticalExtensions CHOICE {

mcgFailureInformation-r16 MCGFailureInformation-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

MCGFailureInformation-r16-IEs ::= SEQUENCE {

failureReportMCG-r16 FailureReportMCG-r16 OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

FailureReportMCG-r16 ::= SEQUENCE {

failureType-r16 ENUMERATED {t310-Expiry, randomAccessProblem,
rlc-MaxNumRetx,

t312-Expiry-r16, lbt-Failure-r16, beamFailureRecoveryFailure-r16,

bh-RLF-r16, spare1} OPTIONAL,

measResultFreqList-r16 MeasResultList2NR OPTIONAL,

measResultFreqListEUTRA-r16 MeasResultList2EUTRA OPTIONAL,

measResultSCG-r16 OCTET STRING (CONTAINING MeasResultSCG-Failure)
OPTIONAL,

measResultSCG-EUTRA-r16 OCTET STRING OPTIONAL,

measResultFreqListUTRA-FDD-r16 MeasResultList2UTRA OPTIONAL,

\...

}

MeasResultList2UTRA ::= SEQUENCE (SIZE (1..maxFreq)) OF
MeasResult2UTRA-FDD-r16

MeasResult2UTRA-FDD-r16 ::= SEQUENCE {

carrierFreq-r16 ARFCN-ValueUTRA-FDD-r16,

measResultNeighCellList-r16 MeasResultListUTRA-FDD-r16

}

MeasResultList2EUTRA ::= SEQUENCE (SIZE (1..maxFreq)) OF
MeasResult2EUTRA-r16

\-- TAG-MCGFAILUREINFORMATION-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MCGFailureInformation field descriptions*                            |
+-----------------------------------------------------------------------+
| ***measResultFreqList***                                              |
|                                                                       |
| The field contains available results of measurements on NR            |
| frequencies the UE is configured to measure by the *measConfig*       |
| associated with the MCG.                                              |
+-----------------------------------------------------------------------+
| ***measResultFreqListEUTRA***                                         |
|                                                                       |
| The field contains available results of measurements on E-UTRA        |
| frequencies the UE is configured to measure by *measConfig*           |
| associated with the MCG.                                              |
+-----------------------------------------------------------------------+
| ***measResultFreqListUTRA-FDD***                                      |
|                                                                       |
| The field contains available results of measurements on UTRA FDD      |
| frequencies the UE is configured to measure by measConfig associated  |
| with the MCG.                                                         |
+-----------------------------------------------------------------------+
| ***measResultSCG***                                                   |
|                                                                       |
| The field contains the *MeasResultSCG-Failure* IE which includes      |
| available measurement results on NR frequencies the UE is configured  |
| to measure by the *measConfig* associated with the SCG.               |
+-----------------------------------------------------------------------+
| ***measResultSCG-EUTRA***                                             |
|                                                                       |
| The field contains the EUTRA *MeasResultSCG-FailureMRDC* IE which     |
| includes available results of measurements on E-UTRA frequencies the  |
| UE is configured to measure by the E-UTRA                             |
| *RRCConnectionReconfiguration* message as specified in TS 36.331      |
| \[10\].                                                               |
+=======================================================================+

#### -- *MeasurementReport*

The *MeasurementReport* message is used for the indication of
measurement results.

Signalling radio bearer: SRB1, SRB3

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*MeasurementReport message*

\-- ASN1START

\-- TAG-MEASUREMENTREPORT-START

MeasurementReport ::= SEQUENCE {

criticalExtensions CHOICE {

measurementReport MeasurementReport-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

MeasurementReport-IEs ::= SEQUENCE {

measResults MeasResults,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

\-- TAG-MEASUREMENTREPORT-STOP

\-- ASN1STOP

#### -- *MeasurementReportAppLayer*

The *MeasurementReportAppLayer* message is used for sending application
layer measurement report.

Signalling radio bearer: SRB4, SRB5

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*MeasurementReportAppLayer message*

\-- ASN1START

\-- TAG-MEASUREMENTREPORTAPPLAYER-START

MeasurementReportAppLayer-r17 ::= SEQUENCE {

criticalExtensions CHOICE {

measurementReportAppLayer-r17 MeasurementReportAppLayer-r17-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

MeasurementReportAppLayer-r17-IEs ::= SEQUENCE {

measurementReportAppLayerList-r17 MeasurementReportAppLayerList-r17,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension MeasurementReportAppLayer-v1800-IEs OPTIONAL

}

MeasurementReportAppLayer-v1800-IEs ::= SEQUENCE {

measurementReportAppLayerList-v1800 MeasurementReportAppLayerList-v1800
OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

MeasurementReportAppLayerList-r17 ::= SEQUENCE (SIZE
(1..maxNrofAppLayerMeas-r17)) OF MeasReportAppLayer-r17

MeasurementReportAppLayerList-v1800 ::= SEQUENCE (SIZE
(1..maxNrofAppLayerMeas-r17)) OF MeasReportAppLayer-v1800

MeasReportAppLayer-r17 ::= SEQUENCE {

measConfigAppLayerId-r17 MeasConfigAppLayerId-r17,

measReportAppLayerContainer-r17 OCTET STRING OPTIONAL,

appLayerSessionStatus-r17 ENUMERATED {start, stop} OPTIONAL,

ran-VisibleMeasurements-r17 RAN-VisibleMeasurements-r17 OPTIONAL

}

MeasReportAppLayer-v1800 ::= SEQUENCE {

appLayerIdleInactiveConfig-r18 AppLayerIdleInactiveConfig-r18 OPTIONAL,

measReportAppLayerContainerList-r18 SEQUENCE (SIZE
(1..maxNrofAppLayerReports-r18)) OF OCTET STRING OPTIONAL,

\...

}

RAN-VisibleMeasurements-r17 ::= SEQUENCE {

appLayerBufferLevelList-r17 SEQUENCE (SIZE (1..8)) OF
AppLayerBufferLevel-r17 OPTIONAL,

playoutDelayForMediaStartup-r17 INTEGER (0..30000) OPTIONAL,

pdu-SessionIdList-r17 SEQUENCE (SIZE (1..maxNrofPDU-Sessions-r17)) OF
PDU-SessionID OPTIONAL,

\...,

\[\[

pdu-SessionIdListExt-v1800 SEQUENCE (SIZE (1..maxNrofPDU-Sessions-r17))
OF QFI-List-r18 OPTIONAL

\]\]

}

AppLayerBufferLevel-r17 ::= INTEGER (0..30000)

QFI-List-r18 ::= SEQUENCE (SIZE (1..maxNrofQFIs)) OF QFI

\-- TAG-MEASUREMENTREPORTAPPLAYER-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MeasurementReportAppLayer* field descriptions                        |
+=======================================================================+
| ***measurementReportAppLayerList***                                   |
|                                                                       |
| The field contains a list of application layer measurement reports.   |
| If *measurementReportAppLayerList-v1800* is present, it contains the  |
| same number of entries, listed in the same order as in                |
| *measurementReportAppLayerList-r17.*                                  |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *MeasReportAppLayer* field descriptions                               |
+=======================================================================+
| ***appLayerSessionStatus***                                           |
|                                                                       |
| Indicates that an application layer measurement session in the        |
| application layer starts or ends. For application layer measurements  |
| applicable to RRC_IDLE or RRC_INACTIVE, the UE transmits              |
| *appLayerSessionStatus* upon transfer to RRC_CONNECTED if             |
| *transmissionOfSessionStartStop* is set to *true* for the application |
| layer measurement configuration.                                      |
+-----------------------------------------------------------------------+
| ***measReportAppLayerContainer***                                     |
|                                                                       |
| The field contains the application layer measurement report           |
| container, see Annex L (normative) in TS 26.247 \[68\], clause 16.5   |
| in TS 26.114 \[69\] and clause 9.4 in TS 26.118 \[70\].               |
+-----------------------------------------------------------------------+
| ***measReportAppLayerContainerList***                                 |
|                                                                       |
| The field contains a list of application layer measurement report     |
| containers for each *measConfigAppLayerId*, see Annex L (normative)   |
| in TS 26.247 \[68\], clause 16.5 in TS 26.114 \[69\] and clause 9.4   |
| in TS 26.118 \[70\].                                                  |
+-----------------------------------------------------------------------+
| ***ran-VisibleMeasurements***                                         |
|                                                                       |
| The field contains the RAN visible application layer measurement      |
| report.                                                               |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *RAN-VisibleMeasurements* field descriptions                          |
+=======================================================================+
| ***appLayerBufferLevelList***                                         |
|                                                                       |
| The field indicates a list of application layer buffer levels, and    |
| each *AppLayerBufferLevel* indicates the application layer buffer     |
| level in ms. Value 0 corresponds to 0 ms, value 1 corresponds to 10   |
| ms, value 2 corresponds to 20 ms and so on. If the buffer level is    |
| larger than the maximum value of 30000 (5 minutes), the UE reports    |
| 30000.                                                                |
+-----------------------------------------------------------------------+
| ***playoutDelayForMediaStartup***                                     |
|                                                                       |
| Indicates the application layer playout delay for media start-up in   |
| ms. Value 0 corresponds to 0 ms, value 1 corresponds to 1 ms, value 2 |
| corresponds to 2 ms and so on. If the playout delay for media         |
| start-up is larger than the maximum value of 30000 ms, the UE reports |
| 30000.                                                                |
+-----------------------------------------------------------------------+
| ***pdu-SessionIdList***                                               |
|                                                                       |
| List of PDU session identities and QoS flow identities per PDU        |
| session associated with the application data flows subject to the RAN |
| visible application layer measurements. If                            |
| *pdu-SessionIdListExt-v1800* is present, it contains the same number  |
| of entries, listed in the same order as in *pdu-SessionIdList-r17.*   |
+-----------------------------------------------------------------------+

#### -- *MIB*

The *MIB* includes the system information transmitted on BCH.

Signalling radio bearer: N/A

RLC-SAP: TM

Logical channel: BCCH

Direction: Network to UE

*MIB*

\-- ASN1START

\-- TAG-MIB-START

MIB ::= SEQUENCE {

systemFrameNumber BIT STRING (SIZE (6)),

subCarrierSpacingCommon ENUMERATED {scs15or60, scs30or120},

ssb-SubcarrierOffset INTEGER (0..15),

dmrs-TypeA-Position ENUMERATED {pos2, pos3},

pdcch-ConfigSIB1 PDCCH-ConfigSIB1,

cellBarred ENUMERATED {barred, notBarred},

intraFreqReselection ENUMERATED {allowed, notAllowed},

spare BIT STRING (SIZE (1))

}

\-- TAG-MIB-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MIB* field descriptions                                              |
+=======================================================================+
| ***cellBarred***                                                      |
|                                                                       |
| Value *barred* means that the cell is barred, as defined in TS 38.304 |
| \[20\]. This field is ignored by IAB-MT and NCR-MT. This field is     |
| ignored for connectivity to NTN or ATG.                               |
+-----------------------------------------------------------------------+
| ***dmrs-TypeA-Position***                                             |
|                                                                       |
| Position of (first) DM-RS for downlink (see TS 38.211 \[16\], clause  |
| 7.4.1.1.2) and uplink (see TS 38.211 \[16\], clause 6.4.1.1.3).       |
+-----------------------------------------------------------------------+
| ***intraFreqReselection***                                            |
|                                                                       |
| Controls cell selection/reselection to intra-frequency cells when the |
| highest ranked cell is barred, or treated as barred by the UE, as     |
| specified in TS 38.304 \[20\]. This field is ignored by IAB-MT,       |
| NCR-MT and (e)RedCap UE.                                              |
+-----------------------------------------------------------------------+
| ***pdcch-ConfigSIB1***                                                |
|                                                                       |
| Determines a common *ControlResourceSet* (CORESET), a common search   |
| space and necessary PDCCH parameters. If the field                    |
| *ssb-SubcarrierOffset* indicates that *SIB1* is absent, the field     |
| *pdcch-ConfigSIB1* indicates the frequency positions where the UE may |
| find SS/PBCH block with *SIB1* or the frequency range where the       |
| network does not provide SS/PBCH block with *SIB1* (see TS 38.213     |
| \[13\], clause 13).                                                   |
+-----------------------------------------------------------------------+
| ***ssb-SubcarrierOffset***                                            |
|                                                                       |
| Corresponds to k~SSB~ (see TS 38.213 \[13\]), which is the frequency  |
| domain offset between SSB and the overall resource block grid in      |
| number of subcarriers. (See TS 38.211 \[16\], clause 7.4.3.1). For    |
| operation with shared spectrum channel access in FR1 (see 37.213      |
| \[48\]), this field corresponds to ${\overline{k}}_{\text{SSB}}$, and |
| k~SSB~ is obtained from ${\overline{k}}_{\text{SSB}}$ (see TS 38.211  |
| \[16\], clause 7.4.3.1); the LSB of this field is used also for       |
| deriving the QCL relation between SS/PBCH blocks as specified in TS   |
| 38.213 \[13\], clause 4.1.                                            |
|                                                                       |
| The value range of this field may be extended by an additional most   |
| significant bit encoded within PBCH as specified in TS 38.213 \[13\]. |
|                                                                       |
| This field may indicate that this cell does not provide *SIB1* and    |
| that there is hence no CORESET#0 configured in *MIB* (see TS 38.213   |
| \[13\], clause 13). In this case, the field *pdcch-ConfigSIB1* may    |
| indicate the frequency positions where the UE may (not) find a        |
| SS/PBCH with a control resource set and search space for *SIB1* (see  |
| TS 38.213 \[13\], clause 13).                                         |
+-----------------------------------------------------------------------+
| ***subCarrierSpacingCommon***                                         |
|                                                                       |
| Subcarrier spacing for *SIB1*, Msg.2/4 and MsgB for initial access,   |
| paging and broadcast SI-messages. If the UE acquires this *MIB* on an |
| FR1 carrier frequency, the value *scs15or60* corresponds to 15 kHz    |
| and the value *scs30or120* corresponds to 30 kHz. If the UE acquires  |
| this *MIB* on an FR2 carrier frequency, the value *scs15or60*         |
| corresponds to 60 kHz and the value *scs30or120* corresponds to 120   |
| kHz. For operation with shared spectrum channel access in FR1 (see    |
| 37.213 \[48\]) and for operation in FR2-2, the subcarrier spacing for |
| *SIB1*, Msg.2/4 and MsgB for initial access, paging and broadcast     |
| SI-messages is same as that for the corresponding SSB. For operation  |
| with shared spectrum channel access, this field instead is used for   |
| deriving the QCL relation between SS/PBCH blocks as specified in TS   |
| 38.213 \[13\], clause 4.1.                                            |
+-----------------------------------------------------------------------+
| ***systemFrameNumber***                                               |
|                                                                       |
| The 6 most significant bits (MSB) of the 10-bit System Frame Number   |
| (SFN). The 4 LSB of the SFN are conveyed in the PBCH transport block  |
| as part of channel coding (i.e. outside the *MIB* encoding), as       |
| defined in clause 7.1 in TS 38.212 \[17\].                            |
+-----------------------------------------------------------------------+

#### -- *MobilityFromNRCommand*

The *MobilityFromNRCommand* message is used to command handover from NR
to E-UTRA/EPC, E-UTRA/5GC or UTRA-FDD.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*MobilityFromNRCommand* message

\-- ASN1START

\-- TAG-MOBILITYFROMNRCOMMAND-START

MobilityFromNRCommand ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

mobilityFromNRCommand MobilityFromNRCommand-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

MobilityFromNRCommand-IEs ::= SEQUENCE {

targetRAT-Type ENUMERATED { eutra, utra-fdd-v1610, spare2, spare1,
\...},

targetRAT-MessageContainer OCTET STRING,

nas-SecurityParamFromNR OCTET STRING OPTIONAL, \-- Cond HO-ToEPCUTRAN

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension MobilityFromNRCommand-v1610-IEs OPTIONAL

}

MobilityFromNRCommand-v1610-IEs ::= SEQUENCE {

voiceFallbackIndication-r16 ENUMERATED {true} OPTIONAL, \-- Need N

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-MOBILITYFROMNRCOMMAND-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MobilityFromNRCommand-IEs* field descriptions                        |
+=======================================================================+
| ***nas-SecurityParamFromNR***                                         |
|                                                                       |
| If *targetRAT-Type* is *eutra*, this field is used to deliver the key |
| synchronisation and Key freshness for the NR to LTE/EPC handovers and |
| a part of the downlink NAS COUNT as specified in TS 33.501 \[11\] and |
| the content of the parameter is defined in TS 24.501 \[23\]. If       |
| *targetRAT-Type* is *utra-fdd*, this field is used to deliver the key |
| synchronisation and Key freshness for the NR to FDD UTRAN handover    |
| and a part of the downlink NAS COUNT as specified in TS 33.501 \[11\] |
| and the content of the parameter is defined in TS 24.501 \[23\].      |
+-----------------------------------------------------------------------+
| ***targetRAT-MessageContainer***                                      |
|                                                                       |
| The field contains a message specified in another standard, as        |
| indicated by the *targetRAT-Type*, and carries information about the  |
| target cell identifier(s) and radio parameters relevant for the       |
| target radio access technology. A complete message is included, as    |
| specified in the other standard. See NOTE 1                           |
+-----------------------------------------------------------------------+
| ***targetRAT-Type***                                                  |
|                                                                       |
| Indicates the target RAT type.                                        |
+-----------------------------------------------------------------------+
| ***voiceFallbackIndication***                                         |
|                                                                       |
| Indicates the handover is triggered by EPS fallback for IMS voice as  |
| specified in TS 23.502 \[43\].                                        |
+-----------------------------------------------------------------------+

NOTE 1: The correspondence between the value of the *targetRAT-Type*,
the standard to apply, and the message contained within the
*targetRAT-MessageContainer* is shown in the table below:

  --------------------------------------------------------------------------
  targetRAT-Type   Standard to apply   targetRAT-MessageContainer
  ---------------- ------------------- -------------------------------------
  *eutra*          TS 36.331 \[10\]    *DL-DCCH-Message* including the
                   (clause 5.4.2)      *RRCConnectionReconfiguration*

  *utra-fdd*       TS 25.331 \[45\]    *Handover TO UTRAN command*
                   (clause 10.2.16a)   
  --------------------------------------------------------------------------

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *HO-ToEPCUTRAN*      This field is mandatory present in case of inter
                       system handover to \"EPC\" or \"FDD UTRAN\".
                       Otherwise it is absent.

  -----------------------------------------------------------------------

#### -- *Paging*

The *Paging* message is used for the notification of one or more UEs.

Signalling radio bearer: N/A

RLC-SAP: TM

Logical channel: PCCH

Direction: Network to UE

*Paging* message

\-- ASN1START

\-- TAG-PAGING-START

Paging ::= SEQUENCE {

pagingRecordList PagingRecordList OPTIONAL, \-- Need N

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension Paging-v1700-IEs OPTIONAL

}

Paging-v1700-IEs ::= SEQUENCE {

pagingRecordList-v1700 PagingRecordList-v1700 OPTIONAL, \-- Need N

pagingGroupList-r17 PagingGroupList-r17 OPTIONAL, \-- Need N

nonCriticalExtension Paging-v1800-IEs OPTIONAL

}

Paging-v1800-IEs ::= SEQUENCE {

pagingRecordList-v1800 PagingRecordList-v1800 OPTIONAL, \-- Need N

pagingGroupList-v1800 PagingGroupList-v1800 OPTIONAL, \-- Need N

nonCriticalExtension SEQUENCE {} OPTIONAL

}

PagingRecordList ::= SEQUENCE (SIZE(1..maxNrofPageRec)) OF PagingRecord

PagingRecordList-v1700 ::= SEQUENCE (SIZE(1..maxNrofPageRec)) OF
PagingRecord-v1700

PagingGroupList-r17 ::= SEQUENCE (SIZE(1..maxNrofPageGroup-r17)) OF
TMGI-r17

PagingRecordList-v1800 ::= SEQUENCE (SIZE(1..maxNrofPageRec)) OF
PagingRecord-v1800

PagingGroupList-v1800 ::= SEQUENCE (SIZE(1..maxNrofPageGroup-r17)) OF
GroupPaging-r18

PagingRecord ::= SEQUENCE {

ue-Identity PagingUE-Identity,

accessType ENUMERATED {non3GPP} OPTIONAL, \-- Need N

\...

}

PagingRecord-v1700 ::= SEQUENCE {

pagingCause-r17 ENUMERATED {voice} OPTIONAL \-- Need N

}

PagingRecord-v1800 ::= SEQUENCE {

mt-SDT ENUMERATED {true} OPTIONAL \-- Need N

}

PagingUE-Identity ::= CHOICE {

ng-5G-S-TMSI NG-5G-S-TMSI,

fullI-RNTI I-RNTI-Value,

\...

}

GroupPaging-r18 ::= SEQUENCE {

inactiveReceptionAllowed-r18 ENUMERATED {true} OPTIONAL \-- Need N

}

\-- TAG-PAGING-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *PagingRecord* field descriptions                                     |
+=======================================================================+
| ***accessType***                                                      |
|                                                                       |
| Indicates whether the *Paging* message is originated due to the PDU   |
| sessions from the non-3GPP access.                                    |
+-----------------------------------------------------------------------+
| ***inactiveReceptionAllowed***                                        |
|                                                                       |
| Indicates whether the UE with a valid PTM configuration for a *TMGI*  |
| in the *PagingGroupList* stays in RRC_INACTIVE to receive the         |
| corresponding MBS multicast session.                                  |
+-----------------------------------------------------------------------+
| ***mt-SDT***                                                          |
|                                                                       |
| Mobile Terminated SDT indication. The network includes *mt-SDT*       |
| indication in paging message only if the UE\'s I-RNTI is included in  |
| the paging message.                                                   |
+-----------------------------------------------------------------------+
| ***pagingRecordList***                                                |
|                                                                       |
| If the network includes pagingRecordList-v1700, it includes the same  |
| number of entries, and listed in the same order, as in                |
| pagingRecordList (i.e. without suffix). If the network includes       |
| *pagingRecordList-v1800*, it includes the same number of entries, and |
| listed in the same order, as in *pagingRecordList* (i.e. without      |
| suffix). The first element in *pagingRecordList-v1700* corresponds to |
| the first UE identity in *pagingRecordList* (i.e. without suffix).    |
| The second element in *pagingRecordList-v1700* corresponds to the     |
| second UE identity in *pagingRecordList* (i.e. without suffix), and   |
| so on. The first element in *pagingRecordList-v1800* corresponds to   |
| the first UE identity in *pagingRecordList* (i.e. without suffix).    |
| The second element in *pagingRecordList-v1800* corresponds to the     |
| second UE identity in *pagingRecordList* (i.e. without suffix), and   |
| so on.                                                                |
+-----------------------------------------------------------------------+
| ***pagingCause***                                                     |
|                                                                       |
| Indicates whether the Paging message is originated due to IMS voice.  |
| If this field is present, it implies that the corresponding paging    |
| entry is for IMS voice. If upper layers indicate the support of       |
| paging cause and if this field is not present but                     |
| pagingRecordList-v1700 is present, it implies that the corresponding  |
| paging entry is for a service other than IMS voice. Otherwise, paging |
| cause is undetermined.                                                |
+-----------------------------------------------------------------------+
| ***pagingGroupList***                                                 |
|                                                                       |
| If the network includes *pagingGroupList-v1800*, it includes the same |
| number of elements, and listed in the same order, as in               |
| *pagingGroupList-r17*. The first element corresponds to the first     |
| TMGI in *pagingGroupList-r17*. The second element corresponds to the  |
| second TMGI in *pagingGroupList-r17*, and so on.                      |
+-----------------------------------------------------------------------+

#### -- *RRCReestablishment*

The *RRCReestablishment* message is used to re-establish SRB1.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*RRCReestablishment* message

\-- ASN1START

\-- TAG-RRCREESTABLISHMENT-START

RRCReestablishment ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcReestablishment RRCReestablishment-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCReestablishment-IEs ::= SEQUENCE {

nextHopChainingCount NextHopChainingCount,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RRCReestablishment-v1700-IEs OPTIONAL

}

RRCReestablishment-v1700-IEs ::= SEQUENCE {

sl-L2RemoteUE-Config-r17 SetupRelease {SL-L2RemoteUE-Config-r17}
OPTIONAL, \-- Cond L2RemoteUE

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-RRCREESTABLISHMENT-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCReestablishment-IEs* field descriptions                           |
+=======================================================================+
| ***sl-L2RemoteUE-Config***                                            |
|                                                                       |
| Contains dedicated configurations used for L2 U2N relay related       |
| operation. The network configures only the SRAP configuration for     |
| local UE ID.                                                          |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *L2RemoteUE*         The field is mandatory present for L2 U2N Remote
                       UE; otherwise it is absent.

  -----------------------------------------------------------------------

#### -- *RRCReestablishmentComplete*

The *RRCReestablishmentComplete* message is used to confirm the
successful completion of an RRC connection re-establishment.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*RRCReestablishmentComplete* message

\-- ASN1START

\-- TAG-RRCREESTABLISHMENTCOMPLETE-START

RRCReestablishmentComplete ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcReestablishmentComplete RRCReestablishmentComplete-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCReestablishmentComplete-IEs ::= SEQUENCE {

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RRCReestablishmentComplete-v1610-IEs OPTIONAL

}

RRCReestablishmentComplete-v1610-IEs ::= SEQUENCE {

ue-MeasurementsAvailable-r16 UE-MeasurementsAvailable-r16 OPTIONAL,

nonCriticalExtension RRCReestablishmentComplete-v1800-IEs OPTIONAL

}

RRCReestablishmentComplete-v1800-IEs ::= SEQUENCE {

flightPathInfoAvailable-r18 ENUMERATED {true} OPTIONAL,

measConfigReportAppLayerAvailable-r18 ENUMERATED {true} OPTIONAL,

musim-CapRestrictionInd-r18 ENUMERATED {true} OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-RRCREESTABLISHMENTCOMPLETE-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCReestablishmentComplete-IEs* field descriptions                   |
+=======================================================================+
| ***measConfigReportAppLayerAvailable***                               |
|                                                                       |
| Indication that the UE has at least one application layer measurement |
| configuration with *appLayerIdleInactiveConfig* configured.           |
+-----------------------------------------------------------------------+
| ***musim-CapRestrictionInd***                                         |
|                                                                       |
| This field indicates the UE temporary capability restriction due to   |
| MUSIM operation.                                                      |
+-----------------------------------------------------------------------+

#### -- *RRCReestablishmentRequest*

The *RRCReestablishmentRequest* message is used to request the
reestablishment of an RRC connection.

Signalling radio bearer: SRB0

RLC-SAP: TM

Logical channel: CCCH

Direction: UE to Network

*RRCReestablishmentRequest* message

\-- ASN1START

\-- TAG-RRCREESTABLISHMENTREQUEST-START

RRCReestablishmentRequest ::= SEQUENCE {

rrcReestablishmentRequest RRCReestablishmentRequest-IEs

}

RRCReestablishmentRequest-IEs ::= SEQUENCE {

ue-Identity ReestabUE-Identity,

reestablishmentCause ReestablishmentCause,

spare BIT STRING (SIZE (1))

}

ReestabUE-Identity ::= SEQUENCE {

c-RNTI RNTI-Value,

physCellId PhysCellId,

shortMAC-I ShortMAC-I

}

ReestablishmentCause ::= ENUMERATED {reconfigurationFailure,
handoverFailure, otherFailure, spare1}

\-- TAG-RRCREESTABLISHMENTREQUEST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *ReestabUE-Identity* field descriptions                               |
+=======================================================================+
| ***physCellId***                                                      |
|                                                                       |
| The Physical Cell Identity of the PCell the UE was connected to prior |
| to the failure.                                                       |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *RRCReestablishmentRequest-IEs* field descriptions                    |
+=======================================================================+
| ***reestablishmentCause***                                            |
|                                                                       |
| Indicates the failure cause that triggered the re-establishment       |
| procedure. gNB is not expected to reject a                            |
| *RRCReestablishmentRequest* due to unknown cause value being used by  |
| the UE.                                                               |
+-----------------------------------------------------------------------+
| ***ue-Identity***                                                     |
|                                                                       |
| UE identity included to retrieve UE context and to facilitate         |
| contention resolution by lower layers.                                |
+-----------------------------------------------------------------------+

#### -- *RRCReconfiguration*

The *RRCReconfiguration* message is the command to modify an RRC
connection. It may convey information for measurement configuration,
mobility control, radio resource configuration (including RBs, MAC main
configuration and physical channel configuration) and AS security
configuration.

Signalling radio bearer: SRB1 or SRB3

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*RRCReconfiguration message*

\-- ASN1START

\-- TAG-RRCRECONFIGURATION-START

RRCReconfiguration ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcReconfiguration RRCReconfiguration-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCReconfiguration-IEs ::= SEQUENCE {

radioBearerConfig RadioBearerConfig OPTIONAL, \-- Need M

secondaryCellGroup OCTET STRING (CONTAINING CellGroupConfig) OPTIONAL,
\-- Cond SCG

measConfig MeasConfig OPTIONAL, \-- Need M

lateNonCriticalExtension OCTET STRING (CONTAINING
RRCReconfiguration-v15t0-IEs) OPTIONAL,

nonCriticalExtension RRCReconfiguration-v1530-IEs OPTIONAL

}

\-- Regular non-critical extensions:

RRCReconfiguration-v1530-IEs ::= SEQUENCE {

masterCellGroup OCTET STRING (CONTAINING CellGroupConfig) OPTIONAL, \--
Need M

fullConfig ENUMERATED {true} OPTIONAL, \-- Cond FullConfig

dedicatedNAS-MessageList SEQUENCE (SIZE(1..maxDRB)) OF
DedicatedNAS-Message OPTIONAL, \-- Cond nonHO

masterKeyUpdate MasterKeyUpdate OPTIONAL, \-- Cond MasterKeyChange

dedicatedSIB1-Delivery OCTET STRING (CONTAINING SIB1) OPTIONAL, \-- Need
N

dedicatedSystemInformationDelivery OCTET STRING (CONTAINING
SystemInformation) OPTIONAL, \-- Need N

otherConfig OtherConfig OPTIONAL, \-- Need M

nonCriticalExtension RRCReconfiguration-v1540-IEs OPTIONAL

}

RRCReconfiguration-v1540-IEs ::= SEQUENCE {

otherConfig-v1540 OtherConfig-v1540 OPTIONAL, \-- Need M

nonCriticalExtension RRCReconfiguration-v1560-IEs OPTIONAL

}

RRCReconfiguration-v1560-IEs ::= SEQUENCE {

mrdc-SecondaryCellGroupConfig SetupRelease {
MRDC-SecondaryCellGroupConfig } OPTIONAL, \-- Need M

radioBearerConfig2 OCTET STRING (CONTAINING RadioBearerConfig) OPTIONAL,
\-- Need M

sk-Counter SK-Counter OPTIONAL, \-- Need N

nonCriticalExtension RRCReconfiguration-v1610-IEs OPTIONAL

}

RRCReconfiguration-v1610-IEs ::= SEQUENCE {

otherConfig-v1610 OtherConfig-v1610 OPTIONAL, \-- Need M

bap-Config-r16 SetupRelease { BAP-Config-r16 } OPTIONAL, \-- Need M

iab-IP-AddressConfigurationList-r16 IAB-IP-AddressConfigurationList-r16
OPTIONAL, \-- Need M

conditionalReconfiguration-r16 ConditionalReconfiguration-r16 OPTIONAL,
\-- Need M

daps-SourceRelease-r16 ENUMERATED{true} OPTIONAL, \-- Need N

t316-r16 SetupRelease {T316-r16} OPTIONAL, \-- Need M

needForGapsConfigNR-r16 SetupRelease {NeedForGapsConfigNR-r16} OPTIONAL,
\-- Need M

onDemandSIB-Request-r16 SetupRelease { OnDemandSIB-Request-r16 }
OPTIONAL, \-- Need M

dedicatedPosSysInfoDelivery-r16 OCTET STRING (CONTAINING
PosSystemInformation-r16-IEs) OPTIONAL, \-- Need N

sl-ConfigDedicatedNR-r16 SetupRelease {SL-ConfigDedicatedNR-r16}
OPTIONAL, \-- Need M

sl-ConfigDedicatedEUTRA-Info-r16 SetupRelease
{SL-ConfigDedicatedEUTRA-Info-r16} OPTIONAL, \-- Need M

targetCellSMTC-SCG-r16 SSB-MTC OPTIONAL, \-- Need S

nonCriticalExtension RRCReconfiguration-v1700-IEs OPTIONAL

}

RRCReconfiguration-v1700-IEs ::= SEQUENCE {

otherConfig-v1700 OtherConfig-v1700 OPTIONAL, \-- Need M

sl-L2RelayUE-Config-r17 SetupRelease { SL-L2RelayUE-Config-r17 }
OPTIONAL, \-- Need M

sl-L2RemoteUE-Config-r17 SetupRelease { SL-L2RemoteUE-Config-r17 }
OPTIONAL, \-- Need M

dedicatedPagingDelivery-r17 OCTET STRING (CONTAINING Paging) OPTIONAL,
\-- Cond PagingRelay

needForGapNCSG-ConfigNR-r17 SetupRelease {NeedForGapNCSG-ConfigNR-r17}
OPTIONAL, \-- Need M

needForGapNCSG-ConfigEUTRA-r17 SetupRelease
{NeedForGapNCSG-ConfigEUTRA-r17} OPTIONAL, \-- Need M

musim-GapConfig-r17 SetupRelease {MUSIM-GapConfig-r17} OPTIONAL, \--
Need M

ul-GapFR2-Config-r17 SetupRelease { UL-GapFR2-Config-r17 } OPTIONAL, \--
Need M

scg-State-r17 ENUMERATED { deactivated } OPTIONAL, \-- Need S

appLayerMeasConfig-r17 AppLayerMeasConfig-r17 OPTIONAL, \-- Need M

ue-TxTEG-RequestUL-TDOA-Config-r17 SetupRelease
{UE-TxTEG-RequestUL-TDOA-Config-r17} OPTIONAL, \-- Need M

nonCriticalExtension RRCReconfiguration-v1800-IEs OPTIONAL

}

RRCReconfiguration-v1800-IEs ::= SEQUENCE {

needForInterruptionConfigNR-r18 ENUMERATED { disabled, enabled }
OPTIONAL, \-- Need M

aerial-Config-r18 SetupRelease { Aerial-Config-r18 } OPTIONAL, \-- Need
M

sl-IndirectPathAddChange-r18 SetupRelease { SL-IndirectPathAddChange-r18
} OPTIONAL, \-- Need M

n3c-IndirectPathAddChange-r18 SetupRelease {
N3C-IndirectPathAddChange-r18 } OPTIONAL, \-- Need M

n3c-IndirectPathConfigRelay-r18 SetupRelease {
N3C-IndirectPathConfigRelay-r18 } OPTIONAL, \-- Need M

otherConfig-v1800 OtherConfig-v1800 OPTIONAL, \-- Need M

srs-PosResourceSetAggBW-CombinationList-r18 SetupRelease {
SRS-PosResourceSetAggBW-CombinationList-r18 } OPTIONAL, \-- Need M

ltm-Config-r18 SetupRelease {LTM-Config-r18} OPTIONAL, \-- Need M

nonCriticalExtension RRCReconfiguration-v1830-IEs OPTIONAL

}

RRCReconfiguration-v1830-IEs ::= SEQUENCE {

otherConfig-v1830 OtherConfig-v1830 OPTIONAL, \-- Need M

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- Late non-critical Rel-15 extensions:

RRCReconfiguration-v15t0-IEs ::= SEQUENCE {

\-- Following field is only to be used for late REL-15 extensions

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RRCReconfiguration-v16k0-IEs OPTIONAL

}

RRCReconfiguration-v16k0-IEs ::= SEQUENCE {

sl-ConfigDedicatedNR-v16k0 SetupRelease {SL-ConfigDedicatedNR-v16k0}
OPTIONAL, \-- Need M

nonCriticalExtension SEQUENCE{} OPTIONAL

}

MRDC-SecondaryCellGroupConfig ::= SEQUENCE {

mrdc-ReleaseAndAdd ENUMERATED {true} OPTIONAL, \-- Need N

mrdc-SecondaryCellGroup CHOICE {

nr-SCG OCTET STRING (CONTAINING RRCReconfiguration),

eutra-SCG OCTET STRING

}

}

BAP-Config-r16 ::= SEQUENCE {

bap-Address-r16 BIT STRING (SIZE (10)) OPTIONAL, \-- Need M

defaultUL-BAP-RoutingID-r16 BAP-RoutingID-r16 OPTIONAL, \-- Need M

defaultUL-BH-RLC-Channel-r16 BH-RLC-ChannelID-r16 OPTIONAL, \-- Need M

flowControlFeedbackType-r16 ENUMERATED {perBH-RLC-Channel, perRoutingID,
both} OPTIONAL, \-- Need R

\...

}

MasterKeyUpdate ::= SEQUENCE {

keySetChangeIndicator BOOLEAN,

nextHopChainingCount NextHopChainingCount,

nas-Container OCTET STRING OPTIONAL, \-- Cond securityNASC

\...

}

OnDemandSIB-Request-r16 ::= SEQUENCE {

onDemandSIB-RequestProhibitTimer-r16 ENUMERATED {s0, s0dot5, s1, s2, s5,
s10, s20, s30}

}

T316-r16 ::= ENUMERATED {ms50, ms100, ms200, ms300, ms400, ms500, ms600,
ms1000, ms1500, ms2000}

IAB-IP-AddressConfigurationList-r16 ::= SEQUENCE {

iab-IP-AddressToAddModList-r16 SEQUENCE (SIZE(1..maxIAB-IP-Address-r16))
OF IAB-IP-AddressConfiguration-r16 OPTIONAL, \-- Need N

iab-IP-AddressToReleaseList-r16 SEQUENCE
(SIZE(1..maxIAB-IP-Address-r16)) OF IAB-IP-AddressIndex-r16 OPTIONAL,
\-- Need N

\...

}

IAB-IP-AddressConfiguration-r16 ::= SEQUENCE {

iab-IP-AddressIndex-r16 IAB-IP-AddressIndex-r16,

iab-IP-Address-r16 IAB-IP-Address-r16 OPTIONAL, \-- Need M

iab-IP-Usage-r16 IAB-IP-Usage-r16 OPTIONAL, \-- Need M

iab-donor-DU-BAP-Address-r16 BIT STRING (SIZE(10)) OPTIONAL, \-- Need M

\...

}

SL-ConfigDedicatedEUTRA-Info-r16 ::= SEQUENCE {

sl-ConfigDedicatedEUTRA-r16 OCTET STRING OPTIONAL, \-- Need M

sl-TimeOffsetEUTRA-List-r16 SEQUENCE (SIZE (8)) OF
SL-TimeOffsetEUTRA-r16 OPTIONAL \-- Need M

}

SL-TimeOffsetEUTRA-r16 ::= ENUMERATED {ms0, ms0dot25, ms0dot5,
ms0dot625, ms0dot75, ms1, ms1dot25, ms1dot5, ms1dot75,

ms2, ms2dot5, ms3, ms4, ms5, ms6, ms8, ms10, ms20}

UE-TxTEG-RequestUL-TDOA-Config-r17 ::= CHOICE {

oneShot-r17 NULL,

periodicReporting-r17 ENUMERATED { ms160, ms320, ms1280, ms2560,
ms61440, ms81920, ms368640, ms737280 }

}

SRS-PosResourceSetAggBW-CombinationList-r18 ::= SEQUENCE (SIZE(1..
maxNrOfLinkedSRS-PosResSetComb-r18)) OF
SRS-PosResourceSetLinkedForAggBW-List-r18

SRS-PosResourceSetLinkedForAggBW-List-r18 ::= SEQUENCE
(SIZE(2..maxNrOfLinkedSRS-PosResourceSet-r18)) OF
SRS-PosResourceSetLinkedForAggBW-r18

\-- TAG-RRCRECONFIGURATION-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCReconfiguration-IEs* field descriptions                           |
+=======================================================================+
| ***appLayerMeasConfig***                                              |
|                                                                       |
| This field is used to configure application layer measurements. This  |
| field is absent when the UE is configured to operate with shared      |
| spectrum channel access or if *sl-L2RemoteUE-Config-r17* is           |
| configured or not released.                                           |
+-----------------------------------------------------------------------+
| ***bap-Config***                                                      |
|                                                                       |
| This field is used to configure the BAP entity for IAB nodes.         |
+-----------------------------------------------------------------------+
| ***bap-Address***                                                     |
|                                                                       |
| Indicates the BAP address of an IAB-node. The BAP address of an       |
| IAB-node cannot be changed once configured for the cell group to the  |
| BAP entity.                                                           |
+-----------------------------------------------------------------------+
| ***conditionalReconfiguration***                                      |
|                                                                       |
| Configuration of candidate target SpCell(s) and execution             |
| condition(s) for conditional handover, conditional PSCell addition or |
| conditional PSCell change. The field is absent if any DAPS bearer is  |
| configured, if the *sl-L2RemoteUE-Config* or *sl-L2RelayUE-Config* is |
| configured, or if the *RRCReconfiguration* message is contained       |
| within *condRRCReconfig*. When the *masterCellGroup* and/or           |
| *secondaryCellGroup* includes *ReconfigurationWithSync*, if this      |
| field is present, it only includes configurations/fields specific to  |
| subsequent CPAC. The *RRCReconfiguration* message contained in        |
| *DLInformationTransferMRDC* cannot contain the field                  |
| *conditionalReconfiguration* for conditional PSCell change or for     |
| conditional PSCell addition. The network does not include this field  |
| in an *RRCReconfiguration* message contained within a *LTM-Config*    |
| IE*.*                                                                 |
+-----------------------------------------------------------------------+
| ***daps-SourceRelease***                                              |
|                                                                       |
| Indicates to UE that the source cell part of DAPS operation is to be  |
| stopped and the source cell part of DAPS configuration is to be       |
| released.                                                             |
+-----------------------------------------------------------------------+
| ***dedicatedNAS-MessageList***                                        |
|                                                                       |
| This field is used to transfer UE specific NAS layer information      |
| between the network and the UE. The RRC layer is transparent for each |
| PDU in the list.                                                      |
+-----------------------------------------------------------------------+
| ***dedicatedPagingDelivery***                                         |
|                                                                       |
| This field is used to transfer *Paging* message for the associated L2 |
| U2N Remote UE to the L2 U2N Relay UE in RRC_CONNECTED.                |
+-----------------------------------------------------------------------+
| ***dedicatedPosSysInfoDelivery***                                     |
|                                                                       |
| This field is used to transfer *SIBPos* to the UE in RRC_CONNECTED.   |
+-----------------------------------------------------------------------+
| ***dedicatedSIB1-Delivery***                                          |
|                                                                       |
| This field is used to transfer *SIB1* to the UE (including L2 U2N     |
| Remote UE). The field has the same values as the corresponding        |
| configuration in *servingCellConfigCommon*.                           |
+-----------------------------------------------------------------------+
| ***dedicatedSystemInformationDelivery***                              |
|                                                                       |
| This field is used to transfer *SIB6*, *SIB7*, *SIB8, SIB19, SIB20,   |
| SIB21, SIB25* to the UE with an active BWP with no common search      |
| space configured or the L2 U2N Remote UE in RRC_CONNECTED. For UEs in |
| RRC_CONNECTED (including L2 U2N Remote UE), this field is also used   |
| to transfer the SIBs requested on-demand.                             |
+-----------------------------------------------------------------------+
| ***defaultUL-BAP-RoutingID***                                         |
|                                                                       |
| This field is used for IAB-node to configure the default uplink       |
| Routing ID, which is used by IAB-node during IAB-node                 |
| bootstrapping*,* migration, IAB-MT RRC resume and IAB-MT RRC          |
| re-establishment for *F1-C* and *non-F1* traffic. The                 |
| *defaultUL-BAP-RoutingID* can be (re-)configured when IAB-node IP     |
| address for *F1-C* related traffic changes. This field is mandatory   |
| only for IAB-node bootstrapping.                                      |
+-----------------------------------------------------------------------+
| ***defaultUL-BH-RLC-Channel***                                        |
|                                                                       |
| This field is used for IAB-nodes to configure the default uplink BH   |
| RLC channel*,* which is used by IAB-node during IAB-node              |
| bootstrapping*,* migration, IAB-MT RRC resume and IAB-MT RRC          |
| re-establishment *for F1-C and non-F1 traffic*. The                   |
| *defaultUL-BH-RLC-Channel* can be (re-)configured when IAB-node IP    |
| address for *F1-C* related traffic changes, and the new IP address is |
| anchored at a different IAB-donor-DU. This field is mandatory for     |
| IAB-node bootstrapping. If the IAB-MT is operating in EN-DC, the      |
| default uplink BH RLC channel is referring to an RLC channel on the   |
| SCG; Otherwise, it is referring to an RLC channel either on the MCG   |
| or on the SCG depending on whether the MN or the SN configures this   |
| field.                                                                |
+-----------------------------------------------------------------------+
| ***flowControlFeedbackType***                                         |
|                                                                       |
| This field is only used for IAB-node that support hop-by-hop flow     |
| control to configure the type of flow control feedback. Value         |
| *perBH-RLC-Channel* indicates that the IAB-node shall provide flow    |
| control feedback per BH RLC channel, value *perRoutingID* indicates   |
| that the IAB-node shall provide flow control feedback per routing ID, |
| and value *both* indicates that the IAB-node shall provide flow       |
| control feedback both per BH RLC channel and per routing ID.          |
+-----------------------------------------------------------------------+
| ***fullConfig***                                                      |
|                                                                       |
| Indicates that the full configuration option is applicable for the    |
| *RRCReconfiguration* message for intra-system intra-RAT HO. For       |
| inter-RAT HO from E-UTRA to NR, *fullConfig* indicates whether or not |
| delta signalling of SDAP/PDCP from source RAT is applicable. This     |
| field is absent if any DAPS bearer is configured or when the          |
| *RRCReconfiguration* message is transmitted on SRB3, and in an        |
| *RRCReconfiguration* message for SCG contained in another             |
| *RRCReconfiguration* message (or *RRCConnectionReconfiguration*       |
| message, see TS 36.331 \[10\]) transmitted on SRB1.                   |
+-----------------------------------------------------------------------+
| ***iab-IP-Address***                                                  |
|                                                                       |
| This field is used to provide the IP address information for          |
| IAB-node.                                                             |
+-----------------------------------------------------------------------+
| ***iab-IP-AddressIndex***                                             |
|                                                                       |
| This field is used to identify a configuration of an IP address.      |
+-----------------------------------------------------------------------+
| ***iab-IP-AddressToAddModList***                                      |
|                                                                       |
| List of IP addresses allocated for IAB-node to be added and modified. |
+-----------------------------------------------------------------------+
| ***iab-IP-AddressToReleaseList***                                     |
|                                                                       |
| List of IP address allocated for IAB-node to be released.             |
+-----------------------------------------------------------------------+
| ***iab-IP-Usage***                                                    |
|                                                                       |
| This field is used to indicate the usage of the assigned IP address.  |
| If this field is not configured, the assigned IP address is used for  |
| all traffic.                                                          |
+-----------------------------------------------------------------------+
| ***iab-donor-DU-BAP-Address***                                        |
|                                                                       |
| This field is used to indicate the BAP address of the IAB-donor-DU    |
| where the IP address is anchored.                                     |
+-----------------------------------------------------------------------+
| ***keySetChangeIndicator***                                           |
|                                                                       |
| Indicates whether UE shall derive a new K~gNB~. If                    |
| *reconfigurationWithSync* is included, value *true* indicates that a  |
| K~gNB~ key is derived from a K~AMF~ key taken into use through the    |
| latest successful NAS SMC procedure, or N2 handover procedure with    |
| K~AMF~ change, as described in TS 33.501 \[11\] for K~gNB~ re-keying. |
| Value *false* indicates that the new K~gNB~ key is obtained from the  |
| current K~gNB~ key or from the NH as described in TS 33.501 \[11\].   |
+-----------------------------------------------------------------------+
| ***ltm-Config***                                                      |
|                                                                       |
| The network does not configure this field in an *RRCReconfiguration*  |
| message within an *LTM-Config* IE and *ConditionalReconfiguration*    |
| IE.                                                                   |
+-----------------------------------------------------------------------+
| ***masterCellGroup***                                                 |
|                                                                       |
| Configuration of master cell group.                                   |
+-----------------------------------------------------------------------+
| ***mrdc-ReleaseAndAdd***                                              |
|                                                                       |
| This field indicates that the current SCG configuration is released   |
| and a new SCG is added at the same time.                              |
+-----------------------------------------------------------------------+
| ***mrdc-SecondaryCellGroup***                                         |
|                                                                       |
| Includes an RRC message for SCG configuration in NR-DC or NE-DC.\     |
| For NR-DC (nr-SCG), *mrdc-SecondaryCellGroup* contains the            |
| *RRCReconfiguration* message as generated (entirely) by SN gNB. In    |
| this version of the specification, the RRC message can only include   |
| fields *secondaryCellGroup, otherConfig, conditionalReconfiguration,* |
| *ltm-Config,* *measConfig,* *bap-Config,*                             |
| *IAB-IP-AddressConfigurationList* and *appLayerMeasConfig*.           |
|                                                                       |
| For NE-DC (eutra-SCG), *mrdc-SecondaryCellGroup* includes the E-UTRA  |
| *RRCConnectionReconfiguration* message as specified in TS 36.331      |
| \[10\]. In this version of the specification, the E-UTRA RRC message  |
| can only include the field *scg-Configuration*.                       |
+-----------------------------------------------------------------------+
| ***mrdc-SecondaryCellGroupConfig***                                   |
|                                                                       |
| This field is used to configure and release an SCG in NR-DC and       |
| NE-DC. In an *RRCReconfiguration* message within an *LTM-Config* IE   |
| associated with the MCG, if this field is present its value can only  |
| be set to *release*.                                                  |
+-----------------------------------------------------------------------+
| ***musim-GapConfig***                                                 |
|                                                                       |
| Indicates the MUSIM gap configuration and controls setup/release of   |
| MUSIM gaps. In this version of the specification, the network does    |
| not configure MUSIM gap together preconfigured measurement gap for    |
| positioning. For the UE supporting *musim-GapPriorityPreference*, the |
| network can configure MUSIM gap together with concurrent measurement  |
| gap. Otherwise, the network does not configure MUSIM gap together     |
| with concurrent measurement gap.                                      |
+-----------------------------------------------------------------------+
| ***nas-Container***                                                   |
|                                                                       |
| This field is used to transfer UE specific NAS layer information      |
| between the network and the UE. The RRC layer is transparent for this |
| field, although it affects activation of AS security after            |
| inter-system handover to NR. The content is defined in TS 24.501      |
| \[23\].                                                               |
+-----------------------------------------------------------------------+
| ***needForGapsConfigNR***                                             |
|                                                                       |
| Configuration for the UE to report measurement gap requirement        |
| information of NR target bands in the *RRCReconfigurationComplete*    |
| and *RRCResumeComplete* message.                                      |
+-----------------------------------------------------------------------+
| ***needForGapNCSG-ConfigEUTRA***                                      |
|                                                                       |
| Configuration for the UE to report measurement gap and NCSG           |
| requirement information of E‑UTRA target bands in the                 |
| *RRCReconfigurationComplete* and *RRCResumeComplete* message.         |
+-----------------------------------------------------------------------+
| ***needForGapNCSG-ConfigNR***                                         |
|                                                                       |
| Configuration for the UE to report measurement gap and NCSG           |
| requirement information of NR target bands in the                     |
| *RRCReconfigurationComplete* and *RRCResumeComplete* message.         |
+-----------------------------------------------------------------------+
| ***needForInterruptionConfigNR***                                     |
|                                                                       |
| Indicates whether the UE shall report interruption requirement        |
| information of NR target bands in the *RRCReconfigurationComplete*    |
| and *RRCResumeComplete* message. The network sets this field to       |
| *enabled* only if the *needForGapsConfigNR* is configured. The        |
| network sets this field to *disabled* if the *needForGapsConfigNR* is |
| released.                                                             |
+-----------------------------------------------------------------------+
| ***nextHopChainingCount***                                            |
|                                                                       |
| Parameter NCC: See TS 33.501 \[11\]                                   |
+-----------------------------------------------------------------------+
| ***onDemandSIB-Request***                                             |
|                                                                       |
| Indicates that the UE is allowed to request SIB(s) on-demand while in |
| RRC_CONNECTED according to clause 5.2.2.3.5.                          |
+-----------------------------------------------------------------------+
| ***onDemandSIB-RequestProhibitTimer***                                |
|                                                                       |
| Prohibit timer for requesting SIB(s) on-demand while in RRC_CONNECTED |
| according to clause 5.2.2.3.5. Value in seconds. Value s0 means       |
| prohibit timer is set to 0 seconds, value s0dot5 means prohibit timer |
| is set to 0.5 seconds, value s1 means prohibit timer is set to 1      |
| second and so on.                                                     |
+-----------------------------------------------------------------------+
| ***otherConfig***                                                     |
|                                                                       |
| Contains configuration related to other configurations. When          |
| configured for the SCG, only fields *drx-PreferenceConfig,            |
| maxBW-PreferenceConfig, maxBW-PreferenceConfigFR2-2,                  |
| maxCC-PreferenceConfig, maxMIMO-LayerPreferenceConfig*,               |
| *maxMIMO-LayerPreferenceConfigFR2-2*,                                 |
| *minSchedulingOffsetPreferenceConfig,                                 |
| minSchedulingOffsetPreferenceConfigExt,                               |
| rlm-RelaxationReportingConfig, bfd-RelaxationReportingConfig,         |
| btNameList, wlanNameList, sensorNameList*, *obtainCommonLocation*,    |
| *idc-AssistanceConfig*, *multiRx-PreferenceReportingConfigFR2*,       |
| *ul-TrafficInfoReportingConfig*, *n3c-RelayUE-InfoReportConfig,       |
| successPSCell-Config* and *sn-InitiatedPSCellChange* can be included. |
+-----------------------------------------------------------------------+
| ***radioBearerConfig***                                               |
|                                                                       |
| Configuration of Radio Bearers (DRBs, SRBs, multicast MRBs) including |
| SDAP/PDCP. In (NG)EN-DC this field may only be present if the         |
| *RRCReconfiguration* is transmitted over SRB3. SRB4 should not be     |
| configured if *sl-L2RemoteUE-Config-r17* is configured or not         |
| released.                                                             |
+-----------------------------------------------------------------------+
| ***radioBearerConfig2***                                              |
|                                                                       |
| Configuration of Radio Bearers (DRBs, SRBs) including SDAP/PDCP. This |
| field can only be used if the UE supports NR-DC or NE-DC.             |
+-----------------------------------------------------------------------+
| ***scg-State***                                                       |
|                                                                       |
| Indicates that the SCG is in deactivated state.                       |
|                                                                       |
| This field is not used                                                |
|                                                                       |
| > \- in an *RRCReconfiguration* message received:                     |
| >                                                                     |
| > \- within *mrdc-SecondaryCellGroup*, or                             |
| >                                                                     |
| > \- in an E-UTRA *RRCConnectionReconfiguration* message, or          |
| >                                                                     |
| > \- in an E-UTRA *RRCConnectionResume* message or                    |
| >                                                                     |
| > \- in an *RRCReconfiguration* message received via SRB3, except if  |
| > the *RRCReconfiguration* message is included in                     |
| > *DLInformationTransferMRDC*.                                        |
|                                                                       |
| The field is absent if CPA, CPC, or subsequent CPAC is configured for |
| the UE, or if the *RRCReconfiguration* message is contained in        |
| *CondRRCReconfig,* or PSCell is configured with *tag2*, or if the     |
| *RRCReconfiguration* message is included within an *LTM-Config* IE.   |
+-----------------------------------------------------------------------+
| ***sl-L2RelayUE-Config***                                             |
|                                                                       |
| Contains L2 U2N relay operation related configurations used by a UE   |
| acting as or to be acting as a L2 U2N Relay UE or L2 U2U relay        |
| operation related configuration used by a UE acting as a L2 U2U Relay |
| UE. In case of L2 U2N relay operation, the field is absent if         |
| *conditionalReconfiguration* is configured for CHO.                   |
+-----------------------------------------------------------------------+
| ***sl-L2RemoteUE-Config***                                            |
|                                                                       |
| Contains L2 U2N relay operation related configurations used by a UE   |
| acting as or to be acting as a L2 U2N Remote UE or L2 U2U relay       |
| operation related configuration used by a UE acting as a L2 U2U       |
| Remote UE. In case of L2 U2N relay operation, the field is absent if  |
| *conditionalReconfiguration* is configured for CHO, or if             |
| *appLayerMeasConfig* or SRB4 is configured/not released.              |
+-----------------------------------------------------------------------+
| ***secondaryCellGroup***                                              |
|                                                                       |
| Configuration of secondary cell group ((NG)EN-DC or NR-DC).           |
+-----------------------------------------------------------------------+
| ***sk-Counter***                                                      |
|                                                                       |
| A counter used upon initial configuration of S-K~gNB~ or S-K~eNB~, as |
| well as upon refresh of S-K~gNB~ or S-K~eNB~. This field is always    |
| included either upon initial configuration of an NR SCG or upon       |
| configuration of the first RB with *keyToUse* set to *secondary*,     |
| whichever happens first. This field is absent if there is neither any |
| NR SCG nor any RB with *keyToUse* set to *secondary*, or if the       |
| *RRCReconfiguration* message is contained in *condRRCReconfig* for    |
| subsequent CPAC.                                                      |
+-----------------------------------------------------------------------+
| ***sl-ConfigDedicatedNR***                                            |
|                                                                       |
| This field is used to provide the dedicated configurations for NR     |
| sidelink communication/discovery/positioning.                         |
+-----------------------------------------------------------------------+
| ***sl-ConfigDedicatedEUTRA-Info***                                    |
|                                                                       |
| This field includes the E-UTRA *RRCConnectionReconfiguration* as      |
| specified in TS 36.331 \[10\]. In this version of the specification,  |
| the E-UTRA *RRCConnectionReconfiguration* can only includes sidelink  |
| related fields for V2X sidelink communication, i.e.                   |
| *sl-V2X-ConfigDedicated*, *sl-V2X-SPS-Config*, *measConfig* and/or    |
| *otherConfig*.                                                        |
+-----------------------------------------------------------------------+
| ***srs-PosResourceSetLinkedForAggBWList***                            |
|                                                                       |
| This field indicates the SRS resource sets across two or three        |
| carriers which are linked for SRS bandwidth aggregation in            |
| RRC_CONNECTED state as defined in clause 6.2.1.4 of TS 38.214 \[19\]. |
+-----------------------------------------------------------------------+
| ***sl-TimeOffsetEUTRA***                                              |
|                                                                       |
| This field indicates the possible time offset to (de)activation of    |
| V2X sidelink transmission after receiving DCI format 3_1 used for     |
| scheduling V2X sidelink communication. Value *ms0dpt75* corresponds   |
| to 0.75ms, *ms1* corresponds to 1ms and so on. The network includes   |
| this field only when *sl-ConfigDedicatedEUTRA* is configured.         |
+-----------------------------------------------------------------------+
| ***targetCellSMTC-SCG***                                              |
|                                                                       |
| The SSB periodicity/offset/duration configuration of target cell for  |
| NR PSCell addition and SN change. When UE receives this field, UE     |
| applies the configuration based on the timing reference of NR PCell   |
| for PSCell addition and PSCell change for the case of no              |
| reconfiguration with sync of MCG, and UE applies the configuration    |
| based on the timing reference of target NR PCell for the case of      |
| reconfiguration with sync of MCG. If both this field and the *smtc*   |
| in *secondaryCellGroup* -\> *SpCellConfig* -\>                        |
| *reconfigurationWithSync* are absent, the UE uses the SMTC in the     |
| *measObjectNR* having the same SSB frequency and subcarrier spacing,  |
| as configured before the reception of the RRC message.                |
+-----------------------------------------------------------------------+
| ***t316***                                                            |
|                                                                       |
| Indicates the value for timer T316 as described in clause 7.1. Value  |
| *ms50* corresponds to 50 ms, value *ms100* corresponds to 100 ms and  |
| so on. This field can be configured only if the UE is configured with |
| split SRB1 or SRB3.                                                   |
+-----------------------------------------------------------------------+
| ***ue-TxTEG-RequestUL-TDOA-Config***                                  |
|                                                                       |
| Configures the periodicity of UE reporting for the association        |
| between Tx TEG and SRS Positioning resources. When configured with    |
| *oneShot* UE reports the association only one time. When configured   |
| with *periodicReporting* UE reports the association periodically and  |
| the *periodicReporting* indicates the periodicity. Value *ms160*      |
| corresponds to 160ms, value *ms320* corresponds to 320ms and so on.   |
+-----------------------------------------------------------------------+
| ***ul-GapFR2-Config***                                                |
|                                                                       |
| Indicates the FR2 UL gap configuration to UE. In EN-DC and NGEN-DC,   |
| the SN decides and configures the FR2 UL gap pattern. In NE-DC, the   |
| MN decides and configures the FR2 UL gap pattern. In NR-DC without    |
| FR2-FR2 band combination, the network entity which is configured with |
| FR2 serving cell(s) decides and configures the FR2 UL gap pattern.    |
+-----------------------------------------------------------------------+

+-------------------+--------------------------------------------------+
| Conditional       | Explanation                                      |
| Presence          |                                                  |
+===================+==================================================+
| *nonHO*           | The field is absent in case of reconfiguration   |
|                   | with sync within NR or to NR; otherwise it is    |
|                   | optionally present, need N.                      |
+-------------------+--------------------------------------------------+
| *securityNASC*    | This field is mandatory present in case of inter |
|                   | system handover. Otherwise the field is          |
|                   | optionally present, need N.                      |
+-------------------+--------------------------------------------------+
| *MasterKeyChange* | This field is mandatory present in case          |
|                   | *masterCellGroup* includes                       |
|                   | *ReconfigurationWithSync* and                    |
|                   | *RadioBearerConfig* includes *SecurityConfig*    |
|                   | with *SecurityAlgorithmConfig*, indicating a     |
|                   | change of the AS security algorithms associated  |
|                   | to the master key. If *ReconfigurationWithSync*  |
|                   | is included for other cases, this field is       |
|                   | optionally present, need N. If                   |
|                   | *ReconfigurationWithSync* is part of an          |
|                   | *RRCReconfiguration* message within an           |
|                   | *LTM-Config* IE associated with the MCG, the     |
|                   | field is absent. Otherwise the field is absent.  |
+-------------------+--------------------------------------------------+
| *FullConfig*      | The field is mandatory present in case of        |
|                   | inter-system handover from E-UTRA/EPC to NR. It  |
|                   | is optionally present, Need N, during a          |
|                   | reconfiguration with sync which is not related   |
|                   | to an LTM cell switch or subsequent CPAC, and    |
|                   | also in first reconfiguration after              |
|                   | reestablishment; or for intra-system handover    |
|                   | from E-UTRA/5GC to NR. It is absent otherwise.   |
+-------------------+--------------------------------------------------+
| *SCG*             | The field is mandatory present in:               |
|                   |                                                  |
|                   | \- an *RRCReconfiguration* message contained in  |
|                   | an *RRCResume* message (or in an                 |
|                   | *RRCConnectionResume* message, see TS 36.331     |
|                   | \[10\]),                                         |
|                   |                                                  |
|                   | \- an *RRCReconfiguration* message contained in  |
|                   | an *RRCConnectionReconfiguration* message, see   |
|                   | TS 36.331 \[10\], which is contained in          |
|                   | *DLInformationTransferMRDC* transmitted on SRB3  |
|                   | (as a response to *ULInformationTransferMRDC*    |
|                   | including an *MCGFailureInformation*).           |
|                   |                                                  |
|                   | The field is optional present, Need M, in:       |
|                   |                                                  |
|                   | \- an *RRCReconfiguration* message transmitted   |
|                   | on SRB3,                                         |
|                   |                                                  |
|                   | \- an *RRCReconfiguration* message contained in  |
|                   | another *RRCReconfiguration* message (or in an   |
|                   | *RRCConnectionReconfiguration* message, see TS   |
|                   | 36.331 \[10\]) transmitted on SRB1               |
|                   |                                                  |
|                   | \- an *RRCReconfiguration* message contained in  |
|                   | another *RRCReconfiguration* message which is    |
|                   | contained in *DLInformationTransferMRDC*         |
|                   | transmitted on SRB3 (as a response to            |
|                   | *ULInformationTransferMRDC* including an         |
|                   | *MCGFailureInformation*).                        |
|                   |                                                  |
|                   | Otherwise, the field is absent.                  |
+-------------------+--------------------------------------------------+
| *PagingRelay*     | For L2 U2N Relay UE, the field is optionally     |
|                   | present, Need N. Otherwise, it is absent.        |
+-------------------+--------------------------------------------------+

#### *-- RRCReconfigurationComplete*

The *RRCReconfigurationComplete* message is used to confirm the
successful completion of an RRC connection reconfiguration.

Signalling radio bearer: SRB1 or SRB3

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*RRCReconfigurationComplete message*

\-- ASN1START

\-- TAG-RRCRECONFIGURATIONCOMPLETE-START

RRCReconfigurationComplete ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcReconfigurationComplete RRCReconfigurationComplete-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCReconfigurationComplete-IEs ::= SEQUENCE {

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RRCReconfigurationComplete-v1530-IEs OPTIONAL

}

RRCReconfigurationComplete-v1530-IEs ::= SEQUENCE {

uplinkTxDirectCurrentList UplinkTxDirectCurrentList OPTIONAL,

nonCriticalExtension RRCReconfigurationComplete-v1560-IEs OPTIONAL

}

RRCReconfigurationComplete-v1560-IEs ::= SEQUENCE {

scg-Response CHOICE {

nr-SCG-Response OCTET STRING (CONTAINING RRCReconfigurationComplete),

eutra-SCG-Response OCTET STRING

} OPTIONAL,

nonCriticalExtension RRCReconfigurationComplete-v1610-IEs OPTIONAL

}

RRCReconfigurationComplete-v1610-IEs ::= SEQUENCE {

ue-MeasurementsAvailable-r16 UE-MeasurementsAvailable-r16 OPTIONAL,

needForGapsInfoNR-r16 NeedForGapsInfoNR-r16 OPTIONAL,

nonCriticalExtension RRCReconfigurationComplete-v1640-IEs OPTIONAL

}

RRCReconfigurationComplete-v1640-IEs ::= SEQUENCE {

uplinkTxDirectCurrentTwoCarrierList-r16
UplinkTxDirectCurrentTwoCarrierList-r16 OPTIONAL,

nonCriticalExtension RRCReconfigurationComplete-v1700-IEs OPTIONAL

}

RRCReconfigurationComplete-v1700-IEs ::= SEQUENCE {

needForGapNCSG-InfoNR-r17 NeedForGapNCSG-InfoNR-r17 OPTIONAL,

needForGapNCSG-InfoEUTRA-r17 NeedForGapNCSG-InfoEUTRA-r17 OPTIONAL,

selectedCondRRCReconfig-r17 CondReconfigId-r16 OPTIONAL,

nonCriticalExtension RRCReconfigurationComplete-v1720-IEs OPTIONAL

}

RRCReconfigurationComplete-v1720-IEs ::= SEQUENCE {

uplinkTxDirectCurrentMoreCarrierList-r17
UplinkTxDirectCurrentMoreCarrierList-r17 OPTIONAL,

nonCriticalExtension RRCReconfigurationComplete-v1800-IEs OPTIONAL

}

RRCReconfigurationComplete-v1800-IEs ::= SEQUENCE {

needForInterruptionInfoNR-r18 NeedForInterruptionInfoNR-r18 OPTIONAL,

flightPathInfoAvailable-r18 ENUMERATED {true} OPTIONAL,

selectedPSCellForCHO-WithSCG-r18 SelectedPSCellForCHO-WithSCG-r18
OPTIONAL,

selectedSK-Counter-r18 SK-Counter OPTIONAL,

measConfigReportAppLayerAvailable-r18 ENUMERATED {true} OPTIONAL,

appliedLTM-CandidateId-r18 LTM-CandidateId-r18 OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-RRCRECONFIGURATIONCOMPLETE-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCReconfigurationComplete-IEs* field descriptions                   |
+=======================================================================+
| ***measConfigReportAppLayerAvailable***                               |
|                                                                       |
| Indication that the UE has at least one application layer measurement |
| configuration with *appLayerIdleInactiveConfig* configured.           |
+-----------------------------------------------------------------------+
| ***needForGapsInfoNR***                                               |
|                                                                       |
| This field is used to indicate the measurement gap requirement        |
| information of the UE for NR target bands.                            |
+-----------------------------------------------------------------------+
| ***needForGapNCSG-InfoEUTRA***                                        |
|                                                                       |
| This field is used to indicate the measurement gap and NCSG           |
| requirement information of the UE for E‑UTRA target bands.            |
+-----------------------------------------------------------------------+
| ***needForGapNCSG-InfoNR***                                           |
|                                                                       |
| This field is used to indicate the measurement gap and NCSG           |
| requirement information of the UE for NR target bands.                |
+-----------------------------------------------------------------------+
| ***needForInterruptionInfoNR***                                       |
|                                                                       |
| This field indicates whether interruption is needed while performing  |
| measurement on NR target bands without measurement gap.               |
+-----------------------------------------------------------------------+
| ***scg-Response***                                                    |
|                                                                       |
| In case of NR-DC (*nr-SCG-Response*), this field includes the         |
| *RRCReconfigurationComplete* message. In case of NE-DC                |
| (*eutra-SCG-Response*), this field includes the E-UTRA                |
| *RRCConnectionReconfigurationComplete* message as specified in TS     |
| 36.331 \[10\]*.*                                                      |
+-----------------------------------------------------------------------+
| ***selectedCondRRCReconfig***                                         |
|                                                                       |
| This field indicates the ID of the selected conditional               |
| reconfiguration the UE applied upon the execution of CPA or inter-SN  |
| CPC or subsequent CPAC.                                               |
+-----------------------------------------------------------------------+
| ***selectedPSCellForCHO-WithSCG***                                    |
|                                                                       |
| This field indicates the information of the selected target PSCell to |
| target MN at execution of a conditional reconfiguration for CHO with  |
| candidate SCG(s).                                                     |
+-----------------------------------------------------------------------+
| ***selectedSK-Counter***                                              |
|                                                                       |
| This field includes the selected *sk-counter* value for security key  |
| update upon the execution of subsequent CPAC.                         |
+-----------------------------------------------------------------------+
| ***uplinkTxDirectCurrentList***                                       |
|                                                                       |
| The Tx Direct Current locations for the configured serving cells and  |
| BWPs if requested by the NW (see *reportUplinkTxDirectCurrent* in     |
| *CellGroupConfig*).                                                   |
+-----------------------------------------------------------------------+
| ***uplinkTxDirectCurrentMoreCarrierList***                            |
|                                                                       |
| The Tx Direct Current locations for the configured intra-band CA      |
| requested by *reportUplinkTxDirectCurrentMoreCarrier-r17*.            |
+-----------------------------------------------------------------------+
| ***uplinkTxDirectCurrentTwoCarrierList***                             |
|                                                                       |
| The Tx Direct Current locations for the configured uplink intra-band  |
| CA with two carriers if requested by the NW (see                      |
| *reportUplinkTxDirectCurrentTwoCarrier-r16* in *CellGroupConfig*).    |
+-----------------------------------------------------------------------+

#### -- *RRCReject*

The *RRCReject* message is used to reject an RRC connection
establishment or an RRC connection resumption.

Signalling radio bearer: SRB0

RLC-SAP: TM

Logical channel: CCCH

Direction: Network to UE

*RRCReject* message

\-- ASN1START

\-- TAG-RRCREJECT-START

RRCReject ::= SEQUENCE {

criticalExtensions CHOICE {

rrcReject RRCReject-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCReject-IEs ::= SEQUENCE {

waitTime RejectWaitTime OPTIONAL, \-- Need N

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

\-- TAG-RRCREJECT-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCReject-IEs* field descriptions                                    |
+=======================================================================+
| ***waitTime***                                                        |
|                                                                       |
| Wait time value in seconds. The field is always included.             |
+-----------------------------------------------------------------------+

#### -- *RRCRelease*

The *RRCRelease* message is used to command the release of an RRC
connection or the suspension of the RRC connection.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*RRCRelease* message

\-- ASN1START

\-- TAG-RRCRELEASE-START

RRCRelease ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcRelease RRCRelease-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCRelease-IEs ::= SEQUENCE {

redirectedCarrierInfo RedirectedCarrierInfo OPTIONAL, \-- Need N

cellReselectionPriorities CellReselectionPriorities OPTIONAL, \-- Need R

suspendConfig SuspendConfig OPTIONAL, \-- Need R

deprioritisationReq SEQUENCE {

deprioritisationType ENUMERATED {frequency, nr},

deprioritisationTimer ENUMERATED {min5, min10, min15, min30}

} OPTIONAL, \-- Need N

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RRCRelease-v1540-IEs OPTIONAL

}

RRCRelease-v1540-IEs ::= SEQUENCE {

waitTime RejectWaitTime OPTIONAL, \-- Need N

nonCriticalExtension RRCRelease-v1610-IEs OPTIONAL

}

RRCRelease-v1610-IEs ::= SEQUENCE {

voiceFallbackIndication-r16 ENUMERATED {true} OPTIONAL, \-- Need N

measIdleConfig-r16 SetupRelease {MeasIdleConfigDedicated-r16} OPTIONAL,
\-- Need M

nonCriticalExtension RRCRelease-v1650-IEs OPTIONAL

}

RRCRelease-v1650-IEs ::= SEQUENCE {

mpsPriorityIndication-r16 ENUMERATED {true} OPTIONAL, \-- Cond
Redirection2

nonCriticalExtension RRCRelease-v1710-IEs OPTIONAL

}

RRCRelease-v1710-IEs ::= SEQUENCE {

noLastCellUpdate-r17 ENUMERATED {true} OPTIONAL, \-- Need S

nonCriticalExtension SEQUENCE {} OPTIONAL

}

RedirectedCarrierInfo ::= CHOICE {

nr CarrierInfoNR,

eutra RedirectedCarrierInfo-EUTRA,

\...

}

RedirectedCarrierInfo-EUTRA ::= SEQUENCE {

eutraFrequency ARFCN-ValueEUTRA,

cnType ENUMERATED {epc,fiveGC} OPTIONAL \-- Need N

}

CarrierInfoNR ::= SEQUENCE {

carrierFreq ARFCN-ValueNR,

ssbSubcarrierSpacing SubcarrierSpacing,

smtc SSB-MTC OPTIONAL, \-- Need S

\...

}

SuspendConfig ::= SEQUENCE {

fullI-RNTI I-RNTI-Value,

shortI-RNTI ShortI-RNTI-Value,

ran-PagingCycle PagingCycle,

ran-NotificationAreaInfo RAN-NotificationAreaInfo OPTIONAL, \-- Need M

t380 PeriodicRNAU-TimerValue OPTIONAL, \-- Need R

nextHopChainingCount NextHopChainingCount,

\...,

\[\[

sl-UEIdentityRemote-r17 RNTI-Value OPTIONAL, \-- Cond L2RemoteUE

sdt-Config-r17 SetupRelease { SDT-Config-r17 } OPTIONAL, \-- Need M

srs-PosRRC-Inactive-r17 SetupRelease { SRS-PosRRC-Inactive-r17 }
OPTIONAL, \-- Need M

ran-ExtendedPagingCycle-r17 ExtendedPagingCycle-r17 OPTIONAL \-- Cond
RANPaging

\]\],

\[\[

ncd-SSB-RedCapInitialBWP-SDT-r17 SetupRelease {NonCellDefiningSSB-r17}
OPTIONAL \-- Need M

\]\],

\[\[

resumeIndication-r18 ENUMERATED {true} OPTIONAL, \-- Need N

srs-PosRRC-InactiveEnhanced-r18 SetupRelease {
SRS-PosRRC-InactiveEnhanced-r18 } OPTIONAL, \-- Need M

ran-ExtendedPagingCycleConfig-r18 ExtendedPagingCycleConfig-r18
OPTIONAL, \-- Cond RANPaging

multicastConfigInactive-r18 SetupRelease { MulticastConfigInactive-r18 }
OPTIONAL \-- Need M

\]\]

}

PeriodicRNAU-TimerValue ::= ENUMERATED { min5, min10, min20, min30,
min60, min120, min360, min720}

CellReselectionPriorities ::= SEQUENCE {

freqPriorityListEUTRA FreqPriorityListEUTRA OPTIONAL, \-- Need M

freqPriorityListNR FreqPriorityListNR OPTIONAL, \-- Need M

t320 ENUMERATED {min5, min10, min20, min30, min60, min120, min180,
spare1} OPTIONAL, \-- Need R

\...,

\[\[

freqPriorityListDedicatedSlicing-r17
FreqPriorityListDedicatedSlicing-r17 OPTIONAL \-- Need M

\]\]

}

PagingCycle ::= ENUMERATED {rf32, rf64, rf128, rf256}

FreqPriorityListEUTRA ::= SEQUENCE (SIZE (1..maxFreq)) OF
FreqPriorityEUTRA

FreqPriorityListNR ::= SEQUENCE (SIZE (1..maxFreq)) OF FreqPriorityNR

FreqPriorityEUTRA ::= SEQUENCE {

carrierFreq ARFCN-ValueEUTRA,

cellReselectionPriority CellReselectionPriority,

cellReselectionSubPriority CellReselectionSubPriority OPTIONAL \-- Need
R

}

FreqPriorityNR ::= SEQUENCE {

carrierFreq ARFCN-ValueNR,

cellReselectionPriority CellReselectionPriority,

cellReselectionSubPriority CellReselectionSubPriority OPTIONAL \-- Need
R

}

RAN-NotificationAreaInfo ::= CHOICE {

cellList PLMN-RAN-AreaCellList,

ran-AreaConfigList PLMN-RAN-AreaConfigList,

\...

}

PLMN-RAN-AreaCellList ::= SEQUENCE (SIZE (1.. maxPLMNIdentities)) OF
PLMN-RAN-AreaCell

PLMN-RAN-AreaCell ::= SEQUENCE {

plmn-Identity PLMN-Identity OPTIONAL, \-- Need S

ran-AreaCells SEQUENCE (SIZE (1..32)) OF CellIdentity

}

PLMN-RAN-AreaConfigList ::= SEQUENCE (SIZE (1..maxPLMNIdentities)) OF
PLMN-RAN-AreaConfig

PLMN-RAN-AreaConfig ::= SEQUENCE {

plmn-Identity PLMN-Identity OPTIONAL, \-- Need S

ran-Area SEQUENCE (SIZE (1..16)) OF RAN-AreaConfig

}

RAN-AreaConfig ::= SEQUENCE {

trackingAreaCode TrackingAreaCode,

ran-AreaCodeList SEQUENCE (SIZE (1..32)) OF RAN-AreaCode OPTIONAL \--
Need R

}

SDT-Config-r17 ::= SEQUENCE {

sdt-DRB-List-r17 SEQUENCE (SIZE (0..maxDRB)) OF DRB-Identity OPTIONAL,
\-- Need M

sdt-SRB2-Indication-r17 ENUMERATED {allowed} OPTIONAL, \-- Need R

sdt-MAC-PHY-CG-Config-r17 SetupRelease {SDT-CG-Config-r17} OPTIONAL, \--
Need M

sdt-DRB-ContinueROHC-r17 ENUMERATED { cell, rna } OPTIONAL \-- Need S

}

SDT-CG-Config-r17 ::= OCTET STRING (CONTAINING
SDT-MAC-PHY-CG-Config-r17)

SDT-MAC-PHY-CG-Config-r17 ::= SEQUENCE {

\-- CG-SDT specific configuration

cg-SDT-ConfigLCH-RestrictionToAddModList-r17 SEQUENCE
(SIZE(1..maxLC-ID)) OF CG-SDT-ConfigLCH-Restriction-r17 OPTIONAL, \--
Need N

cg-SDT-ConfigLCH-RestrictionToReleaseList-r17 SEQUENCE
(SIZE(1..maxLC-ID)) OF LogicalChannelIdentity OPTIONAL, \-- Need N

cg-SDT-ConfigInitialBWP-NUL-r17 SetupRelease
{BWP-UplinkDedicatedSDT-r17} OPTIONAL, \-- Need M

cg-SDT-ConfigInitialBWP-SUL-r17 SetupRelease
{BWP-UplinkDedicatedSDT-r17} OPTIONAL, \-- Need M

cg-SDT-ConfigInitialBWP-DL-r17 BWP-DownlinkDedicatedSDT-r17 OPTIONAL,
\-- Need M

cg-SDT-TimeAlignmentTimer-r17 TimeAlignmentTimer OPTIONAL, \-- Need M

cg-SDT-RSRP-ThresholdSSB-r17 RSRP-Range OPTIONAL, \-- Need M

cg-SDT-TA-ValidationConfig-r17 SetupRelease {
CG-SDT-TA-ValidationConfig-r17 } OPTIONAL, \-- Need M

cg-SDT-CS-RNTI-r17 RNTI-Value OPTIONAL, \-- Need M

\...,

\[\[

cg-SDT-ConfigLCH-RestrictionToAddModListExt-v1800 SEQUENCE
(SIZE(1..maxLC-ID)) OF CG-SDT-ConfigLCH-RestrictionExt-v1800

OPTIONAL, \-- Need N

cg-MT-SDT-MaxDurationToNextCG-Occasion-r18 ENUMERATED {

ms10, ms100, sec1, sec10, sec60, sec100, sec300, sec600,

sec1200, sec1800, sec3600,

spare5, spare4, spare3, spare2, spare1} OPTIONAL \-- Need R

\]\]

}

CG-SDT-TA-ValidationConfig-r17 ::= SEQUENCE {

cg-SDT-RSRP-ChangeThreshold-r17 ENUMERATED { dB2, dB4, dB6, dB8, dB10,
dB14, dB18, dB22,

dB26, dB30, dB34, spare5, spare4, spare3, spare2, spare1}

}

BWP-DownlinkDedicatedSDT-r17 ::= SEQUENCE {

pdcch-Config-r17 SetupRelease { PDCCH-Config } OPTIONAL, \-- Need M

pdsch-Config-r17 SetupRelease { PDSCH-Config } OPTIONAL, \-- Need M

\...

}

BWP-UplinkDedicatedSDT-r17 ::= SEQUENCE {

pusch-Config-r17 SetupRelease { PUSCH-Config } OPTIONAL, \-- Need M

configuredGrantConfigToAddModList-r17
ConfiguredGrantConfigToAddModList-r16 OPTIONAL, \-- Need N

configuredGrantConfigToReleaseList-r17
ConfiguredGrantConfigToReleaseList-r16 OPTIONAL, \-- Need N

\...

}

CG-SDT-ConfigLCH-Restriction-r17 ::= SEQUENCE {

logicalChannelIdentity-r17 LogicalChannelIdentity,

configuredGrantType1Allowed-r17 ENUMERATED {true} OPTIONAL, \-- Need R

allowedCG-List-r17 SEQUENCE (SIZE (0..
maxNrofConfiguredGrantConfigMAC-1-r16)) OF
ConfiguredGrantConfigIndexMAC-r16

OPTIONAL \-- Need R

}

CG-SDT-ConfigLCH-RestrictionExt-v1800 ::= SEQUENCE {

cg-SDT-MaxDurationToNextCG-Occasion-r18 ENUMERATED {

ms10, ms100, sec1, sec10, sec60, sec100, sec300, sec600,

sec1200, sec1800, sec3600,

spare5, spare4, spare3, spare2, spare1} OPTIONAL \-- Need R

}

SRS-PosRRC-Inactive-r17 ::= OCTET STRING (CONTAINING
SRS-PosRRC-InactiveConfig-r17)

SRS-PosRRC-InactiveConfig-r17 ::= SEQUENCE {

srs-PosConfigNUL-r17 SRS-PosConfig-r17 OPTIONAL, \-- Need R

srs-PosConfigSUL-r17 SRS-PosConfig-r17 OPTIONAL, \-- Need R

bwp-NUL-r17 BWP OPTIONAL, \-- Need S

bwp-SUL-r17 BWP OPTIONAL, \-- Need S

inactivePosSRS-TimeAlignmentTimer-r17 TimeAlignmentTimer OPTIONAL, \--
Need M

inactivePosSRS-RSRP-ChangeThreshold-r17 RSRP-ChangeThreshold-r17
OPTIONAL \-- Need M

}

RSRP-ChangeThreshold-r17 ::= ENUMERATED {dB4, dB6, dB8, dB10, dB14,
dB18, dB22, dB26, dB30, dB34, spare6, spare5, spare4, spare3, spare2,
spare1}

SRS-PosConfig-r17 ::= SEQUENCE {

srs-PosResourceSetToReleaseList-r17 SEQUENCE
(SIZE(1..maxNrofSRS-PosResourceSets-r16)) OF SRS-PosResourceSetId-r16
OPTIONAL,\-- Need N

srs-PosResourceSetToAddModList-r17 SEQUENCE
(SIZE(1..maxNrofSRS-PosResourceSets-r16)) OF SRS-PosResourceSet-r16
OPTIONAL,\-- Need N

srs-PosResourceToReleaseList-r17 SEQUENCE
(SIZE(1..maxNrofSRS-PosResources-r16)) OF SRS-PosResourceId-r16
OPTIONAL,\-- Need N

srs-PosResourceToAddModList-r17 SEQUENCE
(SIZE(1..maxNrofSRS-PosResources-r16)) OF SRS-PosResource-r16 OPTIONAL
\-- Need N

}

SRS-PosRRC-InactiveEnhanced-r18 ::= OCTET STRING (CONTAINING
SRS-PosRRC-InactiveEnhancedConfig-r18)

SRS-PosRRC-InactiveEnhancedConfig-r18 ::= SEQUENCE {

srs-PosRRC-InactiveAggBW-ConfigList-r18 SetupRelease {
SRS-PosRRC-InactiveAggBW-ConfigList-r18 } OPTIONAL, \-- Need M

srs-PosTx-Hopping-r18 SetupRelease { SRS-PosTx-Hopping-r18 } OPTIONAL,
\-- Need M

srs-PosRRC-InactiveValidityAreaPreConfigList-r18 SetupRelease {
SRS-PosRRC-InactiveValidityAreaPreConfigList-r18 } OPTIONAL, \-- Need M

srs-PosRRC-InactiveValidityAreaNonPreConfig-r18 SetupRelease {
SRS-PosRRC-InactiveValidityAreaConfig-r18 } OPTIONAL, \-- Need M

\...,

\[\[

srs-PosRRC-InactiveAggBW-AdditionalCarriers-r18 SetupRelease
{SRS-PosRRC-InactiveAggBW-AdditionalCarriers-r18 } OPTIONAL \-- Need M

\]\]

}

SRS-PosRRC-InactiveAggBW-AdditionalCarriers-r18 ::= SEQUENCE{

aggregatedPosSRS-CarrierList-r18 SEQUENCE
(SIZE(1..maxNrOfLinkedSRS-CarriersInactive-1-r18)) OF
SRS-PosConfigPerULCarrier-r18 OPTIONAL, \-- Need R

\...

}

SRS-PosConfigPerULCarrier-r18 ::= SEQUENCE{

freqInfo-r18 ARFCN-ValueNR,

srs-PosConfig-r18 SRS-PosConfig-r17,

scs-SpecificCarrier-r18 SCS-SpecificCarrier OPTIONAL, \-- Need R

bwp-r18 BWP OPTIONAL, \-- Need R

\...

}

SRS-PosRRC-InactiveValidityAreaPreConfigList-r18 ::= SEQUENCE
(SIZE(1..maxNrOfVA-r18)) OF SRS-PosRRC-InactiveValidityAreaConfig-r18

SRS-PosRRC-InactiveValidityAreaConfig-r18 ::= SEQUENCE {

srs-PosConfigValidityArea-r18 SEQUENCE (SIZE(1..maxNrOfCellsInVA-r18))
OF CellIdentity,

srs-PosConfigNUL-r18 SRS-PosConfig-r17 OPTIONAL, \-- Need R

srs-PosConfigSUL-r18 SRS-PosConfig-r17 OPTIONAL, \-- Need R

bwp-NUL-r18 BWP OPTIONAL, \-- Need S

bwp-SUL-r18 BWP OPTIONAL, \-- Need S

areaValidityTA-Config-r18 AreaValidityTA-Config-r18 OPTIONAL, \-- Need R

\...,

\[\[

srs-PosConfigValidityAreaExt-v1830 SEQUENCE
(SIZE(1..maxNrOfCellsInVA-Ext-r18)) OF CellIdentity OPTIONAL \-- Need R

\]\],

\[\[

srs-PosRRC-InactiveAggBW-AdditionalCarriersPerVA-r18 SetupRelease
{SRS-PosRRC-InactiveAggBW-AdditionalCarriers-r18 }

OPTIONAL, \-- Need M

srs-PosRRC-InactiveAggBW-ConfigListPerVA-r18 SetupRelease
{SRS-PosRRC-InactiveAggBW-ConfigList-r18 } OPTIONAL \-- Need M

\]\]

}

AreaValidityTA-Config-r18 ::= SEQUENCE {

inactivePosSRS-ValidityAreaTAT-r18 ENUMERATED {ms1280, ms1920, ms2560,
ms5120, ms10240, ms20480, ms40960, infinity},

inactivePosSRS-ValidityAreaRSRP-r18 RSRP-ChangeThreshold-r17 OPTIONAL,
\-- Need R

autonomousTA-AdjustmentEnabled-r18 ENUMERATED {true} OPTIONAL \-- Need R

}

SRS-PosRRC-InactiveAggBW-ConfigList-r18 ::= SEQUENCE
(SIZE(1..maxNrOfLinkedSRS-PosResSetCombInactive-r18)) OF

SRS-InactivePosResourceSetLinkedForAggBW-List-r18

SRS-InactivePosResourceSetLinkedForAggBW-List-r18 ::= SEQUENCE (SIZE
(2..maxNrOfLinkedSRS-PosResourceSet-r18)) OF

SRS-PosResourceSetLinkedForAggBW-r18

ExtendedPagingCycle-r17 ::= ENUMERATED {rf256, rf512, rf1024, spare1}

ExtendedPagingCycleConfig-r18 ::= SEQUENCE {

extendedPagingCycle-r18 ENUMERATED {hf2, hf4, hf8, hf16, hf32, hf64,
hf128,hf256, hf512, hf1024,

spare6, spare5, spare4, spare3, spare2, spare1},

pagingPTWLength-r18 ENUMERATED {ms1280, ms2560, ms3840, ms5120, ms6400,
ms7680, ms8960, ms10240, ms11520,

ms12800, ms14080, ms15360, ms16640, ms17920, ms19200, ms20480, ms21760,

ms23040, ms24320, ms25600, ms26880, ms28160, ms29440, ms30720, ms32000,

ms33280, ms34560, ms35840, ms37120, ms38400, ms39680, ms40960}

}

MulticastConfigInactive-r18::= SEQUENCE {

inactivePTM-Config-r18 OCTET STRING (CONTAINING
MBSMulticastConfiguration-r18) OPTIONAL, \-- Need S

inactiveMCCH-Config-r18 OCTET STRING (CONTAINING SystemInformation)
OPTIONAL \-- Need N

}

\-- TAG-RRCRELEASE-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCRelease-IEs* field descriptions                                   |
+=======================================================================+
| ***cellReselectionPriorities***                                       |
|                                                                       |
| Dedicated priorities to be used for cell reselection as specified in  |
| TS 38.304 \[20\]*.* The maximum number of NR carrier frequencies that |
| the network can configure through *FreqPriorityListNR* and            |
| *FreqPriorityListDedicatedSlicing* together is eight. If the same     |
| frequency is configured in both *FreqPriorityListNR* and              |
| *FreqPriorityListDedicatedSlicing*, the frequency is only counted     |
| once.                                                                 |
+-----------------------------------------------------------------------+
| ***cnType***                                                          |
|                                                                       |
| Indicate that the UE is redirected to EPC or 5GC.                     |
+-----------------------------------------------------------------------+
| ***deprioritisationReq***                                             |
|                                                                       |
| Indicates whether the current frequency or RAT is to be               |
| de-prioritised.                                                       |
+-----------------------------------------------------------------------+
| ***deprioritisationTimer***                                           |
|                                                                       |
| Indicates the value for timer T325 (see clause 5.3.8.3 and TS 38.304  |
| \[20\]). Value *minN* corresponds to N minutes.                       |
+-----------------------------------------------------------------------+
| ***srs-PosRRC-InactiveEnhanced***                                     |
|                                                                       |
| Contains the SRS for positioning configuration in RRC_INACTIVE state  |
| that is applicable for a validity area. The field also contains       |
| bandwidth aggregation (see TS 38.214 \[19\], clause 6.2.1.4.2) and    |
| frequency hopping configurations (see TS 38.214 \[19\], clause        |
| 6.2.1.4.1) for SRS for positioning in RRC_INACTIVE state.             |
+-----------------------------------------------------------------------+
| ***measIdleConfig***                                                  |
|                                                                       |
| Indicates measurement configuration to be stored and used by the UE   |
| while in RRC_IDLE or RRC_INACTIVE.                                    |
+-----------------------------------------------------------------------+
| ***mpsPriorityIndication***                                           |
|                                                                       |
| Indicates the UE can set the establishment cause to                   |
| *mps-PriorityAccess* for a new connection following a redirect to NR  |
| or set the resume cause to *mps-PriorityAccess* for a resume          |
| following a redirect to NR. If the target RAT is E-UTRA, see TS       |
| 36.331 \[10\]. The gNB sets the indication only for UEs authorized to |
| receive MPS treatment as indicated by ARP and/or QoS characteristics  |
| at the gNB, and it is applicable only for this instance of release    |
| with redirection to carrier/RAT included in the                       |
| *redirectedCarrierInfo* field in the *RRCRelease* message.            |
+-----------------------------------------------------------------------+
| ***multicastConfigInactive***                                         |
|                                                                       |
| Indicates whether the UE is configured to receive MBS multicast in    |
| RRC_INACTIVE. The presence of this field indicates the UE is          |
| configured to receive MBS multicast in RRC_INACTIVE; otherwise, the   |
| UE is not configured to receive MBS multicast in RRC_INACTIVE.        |
+-----------------------------------------------------------------------+
| ***noLastCellUpdate***                                                |
|                                                                       |
| Presence of the field indicates that the last used cell for PEI shall |
| not be updated. When the field is absent, the PEI-capable UE shall    |
| update its last used cell with the current cell. The UE shall not     |
| update its last used cell with the current cell if the AS security is |
| not activated.                                                        |
+-----------------------------------------------------------------------+
| ***redirectedCarrierInfo***                                           |
|                                                                       |
| Indicates a carrier frequency (downlink for FDD) and is used to       |
| redirect the UE to an NR or an inter-RAT carrier frequency, by means  |
| of cell selection at transition to RRC_IDLE or RRC_INACTIVE as        |
| specified in TS 38.304 \[20\]. Based on UE capability, the network    |
| may include *redirectedCarrierInfo* in *RRCRelease* message with      |
| *suspendConfig* if this message is sent in response to an             |
| *RRCResumeRequest* or an *RRCResumeRequest1* which is triggered by    |
| the NAS layer (see 5.3.1.4 in TS 24.501 \[23\]).                      |
+-----------------------------------------------------------------------+
| ***srs-PosRRC-Inactive***                                             |
|                                                                       |
| Contains the SRS for positioning configuration in RRC_INACTIVE state. |
+-----------------------------------------------------------------------+
| ***suspendConfig***                                                   |
|                                                                       |
| Indicates configuration for the RRC_INACTIVE state. The network does  |
| not configure *suspendConfig* when the network redirect the UE to an  |
| inter-RAT carrier frequency or if the UE is configured with a DAPS    |
| bearer.                                                               |
+-----------------------------------------------------------------------+
| ***voiceFallbackIndication***                                         |
|                                                                       |
| Indicates the RRC release is triggered by EPS fallback for IMS voice  |
| as specified in TS 23.502 \[43\].                                     |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *CarrierInfoNR* field descriptions                                    |
+=======================================================================+
| ***carrierFreq***                                                     |
|                                                                       |
| Indicates the redirected NR frequency.                                |
+-----------------------------------------------------------------------+
| ***ssbSubcarrierSpacing***                                            |
|                                                                       |
| Subcarrier spacing of SSB in the redirected SSB frequency.            |
|                                                                       |
| Only the following values are applicable depending on the used        |
| frequency:                                                            |
|                                                                       |
| FR1: 15 or 30 kHz                                                     |
|                                                                       |
| FR2-1/FR2-NTN: 120 or 240 kHz                                         |
|                                                                       |
| FR2-2: 120, 480, or 960 kHz                                           |
+-----------------------------------------------------------------------+
| ***smtc***                                                            |
|                                                                       |
| The SSB periodicity/offset/duration configuration for the redirected  |
| SSB frequency. It is based on timing reference of PCell. If the field |
| is absent, the UE uses the SMTC configured in the measObjectNR having |
| the same SSB frequency and subcarrier spacing.                        |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *RAN-NotificationAreaInfo* field descriptions                         |
+=======================================================================+
| ***cellList***                                                        |
|                                                                       |
| A list of cells configured as RAN area.                               |
+-----------------------------------------------------------------------+
| ***ran-AreaConfigList***                                              |
|                                                                       |
| A list of RAN area codes or RA code(s) as RAN area.                   |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *PLMN-RAN-AreaConfig* field descriptions                              |
+=======================================================================+
| ***plmn-Identity***                                                   |
|                                                                       |
| PLMN Identity to which the cells in *ran-Area* belong. If the field   |
| is absent the UE not in SNPN access mode uses the ID of the           |
| registered PLMN. This field is not included for UE in SNPN access     |
| mode (for UE in SNPN access mode the *ran-Area* always belongs to the |
| registered SNPN).                                                     |
+-----------------------------------------------------------------------+
| ***ran-AreaCodeList***                                                |
|                                                                       |
| The total number of RAN-AreaCodes of all PLMNs does not exceed 32.    |
+-----------------------------------------------------------------------+
| ***ran-Area***                                                        |
|                                                                       |
| Indicates whether TA code(s) or RAN area code(s) are used for the RAN |
| notification area. The network uses only TA code(s) or both TA        |
| code(s) and RAN area code(s) to configure a UE. The total number of   |
| TACs across all PLMNs does not exceed 16.                             |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *PLMN-RAN-AreaCell* field descriptions                                |
+=======================================================================+
| ***plmn-Identity***                                                   |
|                                                                       |
| PLMN Identity to which the cells in *ran-AreaCells* belong. If the    |
| field is absent the UE not in SNPN access mode uses the ID of the     |
| registered PLMN. This field is not included for UE in SNPN access     |
| mode (for UE in SNPN access mode the *ran-AreaCells* always belongs   |
| to the registered SNPN).                                              |
+-----------------------------------------------------------------------+
| ***ran-AreaCells***                                                   |
|                                                                       |
| The total number of cells of all PLMNs does not exceed 32.            |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SDT-Config* field descriptions                                       |
+=======================================================================+
| ***sdt-DRB-ContinueROHC***                                            |
|                                                                       |
| Indicates whether the PDCP entity of the radio bearers configured for |
| SDT continues or resets the ROHC header compression protocol during   |
| PDCP re-establishment during SDT procedure, as specified in TS 38.323 |
| \[5\]. Value *cell* indicates that ROHC header compression continues  |
| when the UE resumes for SDT in the same cell as the PCell when the    |
| RRCRelease message was received. Value *rna* indicates that ROHC      |
| header compression continues when the UE resumes for SDT in a cell    |
| belonging to the same RNA as the PCell where the RRCRelease message   |
| was received. If the field is absent, the UE releases any stored      |
| value for this field and the PDCP entity of the radio bearers         |
| configured for SDT always resets the ROHC header compression protocol |
| during PDCP re-establishment when SDT procedure is initiated, as      |
| specified in TS 38.323 \[5\].                                         |
+-----------------------------------------------------------------------+
| ***sdt-DRB-List***                                                    |
|                                                                       |
| Indicates the ID(s) of the DRB(s) that are configured for SDT. If     |
| size of the sequence is zero, then the UE assumes that none of the    |
| DRBs are configured for SDT. The network only configures MN           |
| terminated MCG bearers for SDT.                                       |
+-----------------------------------------------------------------------+
| ***sdt-SRB2-Indication***                                             |
|                                                                       |
| Indicates whether SRB2 is configured for SDT or not.                  |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SDT-MAC-PHY-CG-Config* field descriptions                            |
+=======================================================================+
| ***cg-MT-SDT-MaxDurationToNextCG-Occasion***                          |
|                                                                       |
| The maximum duration until the next CG-SDT occasion as specified in   |
| TS 38.321 \[3\] for MT-SDT. If configured, the CG-SDT resource can    |
| only be used for the initial CG-SDT transmission if the duration      |
| between the initiation of the CG-SDT procedure and the next CG-SDT    |
| occasion is less than the value configured by this field.             |
+-----------------------------------------------------------------------+
| ***cg-SDT-ConfigInitialBWP-DL***                                      |
|                                                                       |
| Downlink BWP configuration for CG-SDT. If a UE is an (e)RedCap UE and |
| if the *initialDownlinkBWP-RedCap* is configured in                   |
| *downlinkConfigCommon* in *SIB1*, this field is configured for        |
| *initialDownlinkBWP-RedCap*, otherwise it is configured for           |
| *initialDownlinkBWP*.                                                 |
+-----------------------------------------------------------------------+
| ***cg-SDT-ConfigInitialBWP-NUL***                                     |
|                                                                       |
| UL BWP configuration for CG-SDT on NUL carrier. If a UE is an         |
| (e)RedCap UE and if the *initialUplinkBWP-RedCap* is configured in    |
| *uplinkConfigCommon* in *SIB1*, this field is configured for          |
| *initialUplinkBWP-RedCap*, otherwise it is configured for             |
| *initialUplinkBWP* for NUL.                                           |
+-----------------------------------------------------------------------+
| ***cg-SDT-ConfigInitialBWP-SUL***                                     |
|                                                                       |
| UL BWP configuration for CG-SDT on SUL carrier configured for the     |
| *initialUplinkBWP* for SUL.                                           |
+-----------------------------------------------------------------------+
| ***cg-SDT-ConfigLCH-RestrictionToAddModList,                          |
| cg-SDT-ConfigLCH-RestrictionToAddModListExt,                          |
| cg-SDT-ConfigLCH-RestrictionToReleaseList***                          |
|                                                                       |
| Lists for adding and releasing logical channel mapping restrictions   |
| for CG-SDT. If the network includes                                   |
| *cg-SDT-ConfigLCH-RestrictionToAddModListExt*, it includes the same   |
| number of entries, and listed in the same order, as in                |
| *cg-SDT-ConfigLCH-RestrictionToAddModList*.                           |
+-----------------------------------------------------------------------+
| ***cg-SDT-CS-RNTI***                                                  |
|                                                                       |
| The CS-RNTI value for CG-SDT as specified in TS 38.321 \[3\].         |
+-----------------------------------------------------------------------+
| ***cg-SDT-RSRP-ThresholdSSB***                                        |
|                                                                       |
| An RSRP threshold configured for SSB selection for CG-SDT as          |
| specified in TS 38.321 \[3\].                                         |
+-----------------------------------------------------------------------+
| ***cg-SDT-TA-ValidationConfig***                                      |
|                                                                       |
| Configuration for the RSRP based TA validation. If this field is not  |
| configured, then the UE does not perform RSRP based TA validation.    |
+-----------------------------------------------------------------------+
| ***cg-SDT-timeAlignmentTimer***                                       |
|                                                                       |
| TAT value for CG-SDT as specified in TS 38.321 \[3\]. The network     |
| always configures this field when *sdt-MAC-PHY-CG-Config* is          |
| configured. This field is associated with the PTAG indicated by       |
| *tag-Id.*                                                             |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *CG-SDT-ConfigLCH-Restriction* field descriptions                     |
+-----------------------------------------------------------------------+
| ***allowedCG-List***                                                  |
|                                                                       |
| This restriction applies only when the UL grant is a configured grant |
| for CG-SDT. If present, UL MAC SDUs from this logical channel can     |
| only be mapped to the indicated CG-SDT configured grant               |
| configuration. If the size of the sequence is zero, then UL MAC SDUs  |
| from this logical channel cannot be mapped to any CG-SDT configured   |
| grant configurations. If the field is not present, UL MAC SDUs from   |
| this logical channel can be mapped to any CG-SDT configured grant     |
| configurations. If the field *configuredGrantType1Allowed* is         |
| present, only those CG-SDT configured grant type 1 configurations     |
| indicated in this sequence are allowed for use by this logical        |
| channel; otherwise, this sequence shall not include any CG-SDT        |
| configured grant type 1 configuration. Corresponds to                 |
| \"*allowedCG*-*List*\" as specified in TS 38.321 \[3\].               |
+-----------------------------------------------------------------------+
| ***cg-SDT-MaxDurationToNextCG-Occasion***                             |
|                                                                       |
| The maximum duration until the next CG-SDT occasion for the logical   |
| channel identified by the *logicalChannelIdentity* as specified in TS |
| 38.321 \[3\]. If configured, the CG-SDT resource can only be used for |
| the initial CG-SDT transmission if the duration between the           |
| initiation of the CG-SDT procedure and the next CG-SDT occasion is    |
| less than the value configured by this field as specified in TS       |
| 38.321 \[3\].                                                         |
+-----------------------------------------------------------------------+
| ***configuredGrantType1Allowed***                                     |
|                                                                       |
| If present, or if the capability *lcp-Restriction* as specified in TS |
| 38.306 \[26\] is not supported, UL MAC SDUs from this logical channel |
| can be transmitted on a configured grant type 1 for CG-SDT.           |
| Otherwise, UL MAC SDUs from this logical channel cannot be            |
| transmitted on a configured grant type 1 for CG-SDT. Corresponds to   |
| \"*configuredGrantType1Allowed*\" in TS 38.321 \[3\].                 |
+-----------------------------------------------------------------------+
| ***logicalChannelIdentity***                                          |
|                                                                       |
| ID used commonly for the MAC logical channel and for the RLC bearer   |
| associated with a *servedRadioBearer* configured for SDT.             |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *CG-SDT-TA-ValidationConfig* field descriptions                       |
+=======================================================================+
| ***cg-SDT-RSRP-ChangeThreshold***                                     |
|                                                                       |
| The RSRP threshold for TA validation for CG-SDT as specified in TS    |
| 38.321 \[3\]. Value *dB2* corresponds to 2 dB, value *dB4*            |
| corresponds to 4 dB and so on.                                        |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SRS-PosRRC-InactiveConfig* field descriptions                        |
+=======================================================================+
| ***bwp-NUL***                                                         |
|                                                                       |
| BWP configuration for SRS for Positioning during the RRC_INACTIVE     |
| state in Normal Uplink Carrier. If the field is absent UE is          |
| configured with an SRS for Positioning associated with the initial UL |
| BWP and transmitted, during the RRC_INACTIVE state, inside the        |
| initial UL BWP with the same CP and SCS as configured for initial UL  |
| BWP.                                                                  |
+-----------------------------------------------------------------------+
| ***bwp-SUL***                                                         |
|                                                                       |
| BWP configuration for SRS for Positioning during the RRC_INACTIVE     |
| state in Supplementary Uplink Carrier. If the field is absent UE is   |
| configured with an SRS for Positioning associated with the initial UL |
| BWP and transmitted, during the RRC_INACTIVE state, inside the        |
| initial UL BWP with the same CP and SCS as configured for initial UL  |
| BWP.                                                                  |
+-----------------------------------------------------------------------+
| ***inactivePosSRS-RSRP-ChangeThreshold***                             |
|                                                                       |
| RSRP threshold for the increase/decrease of RSRP for time alignment   |
| validation as specified in TS 38.321 \[3\].                           |
+-----------------------------------------------------------------------+
| ***inactivePosSRS-TimeAlignmentTimer***                               |
|                                                                       |
| TAT value for SRS for positioning transmission during RRC_INACTIVE    |
| state as specified in TS 38.321 \[3\]. The network always configures  |
| this field when *srs-PosRRC-Inactive* is configured.                  |
+-----------------------------------------------------------------------+
| ***srs-PosConfigNUL***                                                |
|                                                                       |
| SRS for Positioning configuration in RRC_INACTIVE state in Normal     |
| Uplink Carrier.                                                       |
+-----------------------------------------------------------------------+
| ***srs-PosConfigSUL***                                                |
|                                                                       |
| SRS for Positioning configuration in RRC_INACTIVE state in            |
| Supplementary Uplink Carrier.                                         |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SRS-PosRRC-InactiveEnhancedConfig* field descriptions                |
+=======================================================================+
| ***srs-PosRRC-InactiveAggBW-ConfigList***                             |
|                                                                       |
| SRS for positioning configuration with additional one or two          |
| carrier(s) configuration where the primary carrier is provided by     |
| *srs-PosRRC-Inactive-r17* for bandwidth aggregation and additional    |
| carriers are provided by                                              |
| *srs-PosRRC-InactiveAggBW-AdditionalCarriers-r18* and to be used in   |
| RRC_INACTIVE state (see TS 38.214 \[19\], clause 6.2.1.4.2). This     |
| field is included only if *srs-PosRRC-Inactive-r17* and               |
| *srs-PosRRC-InactiveAggBW-AdditionalCarriers-r18* are configured.     |
+-----------------------------------------------------------------------+
| ***srs-PosRRC-InactiveValidityAreaNonPreConfig***                     |
|                                                                       |
| Contains the SRS for positioning configuration to be applied          |
| immediately upon reception. The configuration is valid across a       |
| number of cells as indicated in *srs-PosConfigValidityArea* in        |
| RRC_INACTIVE state.                                                   |
+-----------------------------------------------------------------------+
| ***srs-PosRRC-InactiveValidityAreaPreConfigList***                    |
|                                                                       |
| Contains the SRS for positioning configurations to be applied when a  |
| trigger for an event is met and which is valid across a number of     |
| cells comprising a validity area during RRC_INACTIVE state. For each  |
| validity area, the UE is preconfigured with only one SRS for          |
| positioning configuration.                                            |
+-----------------------------------------------------------------------+
| ***srs-PosTx-Hopping***                                               |
|                                                                       |
| Contains configuration related to the SRS for Positioning with        |
| frequency hopping for RRC_INACTIVE state (see TS 38.214 \[19\],       |
| clause 6.2.1.4.1).                                                    |
+-----------------------------------------------------------------------+
| ***srs-PosRRC-InactiveAggBW-AdditionalCarriers***                     |
|                                                                       |
| Additional carriers of Positioning SRS resource for carrier           |
| agregation for positioning SRS transmission without validity area in  |
| RRC_INACTIVE.                                                         |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SRS-PosRRC-InactiveValidityAreaConfig* field descriptions            |
+=======================================================================+
| ***autonomousTA-AdjustmentEnabled***                                  |
|                                                                       |
| This field indicates that UE may adjust the TA value and stored RSRP  |
| autonomously after cell reselection within a validity area, if        |
| configured.                                                           |
+-----------------------------------------------------------------------+
| ***bwp-NUL***                                                         |
|                                                                       |
| BWP configuration for SRS for Positioning during the RRC_INACTIVE     |
| state in Normal Uplink Carrier. If the field is absent UE is          |
| configured with an SRS for Positioning associated with the initial UL |
| BWP and transmitted, during the RRC_INACTIVE state, inside the        |
| initial UL BWP with the same CP and SCS as configured for initial UL  |
| BWP.                                                                  |
+-----------------------------------------------------------------------+
| ***bwp-SUL***                                                         |
|                                                                       |
| BWP configuration for SRS for Positioning during the RRC_INACTIVE     |
| state in Supplementary Uplink Carrier. If the field is absent UE is   |
| configured with an SRS for Positioning associated with the initial UL |
| BWP and transmitted, during the RRC_INACTIVE state, inside the        |
| initial UL BWP with the same CP and SCS as configured for initial UL  |
| BWP.                                                                  |
+-----------------------------------------------------------------------+
| ***inactivePosSRS-ValidityAreaRSRP***                                 |
|                                                                       |
| RSRP threshold for the increase/decrease of RSRP for validity area    |
| time alignment validation as specified in TS 38.321 \[3\].            |
+-----------------------------------------------------------------------+
| ***inactivePosSRS-ValidityAreaTAT***                                  |
|                                                                       |
| Time alignment timer value for SRS for positioning transmission       |
| during RRC_INACTIVE state which is applicable in a validity area.     |
+-----------------------------------------------------------------------+
| ***srs-PosConfigValidityArea, srs-PosConfigValidityAreaExt***         |
|                                                                       |
| This field provides list of cells present in the validity area. The   |
| maximum number of cells in a validity area is 32 which can be         |
| provided by using these two fields *srs-PosConfigValidityArea* and    |
| *srs-PosConfigValidityAreaExt*.                                       |
+-----------------------------------------------------------------------+
| ***srs-PosRRC-InactiveAggBW-AdditionalCarriersPerVA***                |
|                                                                       |
| SRS resource configuration on additional one or two carriers in each  |
| validity area for positioning SRS transmission for carrier            |
| aggregation in RRC_INACTIVE.                                          |
+-----------------------------------------------------------------------+
| ***srs-PosRRC-InactiveAggBW-ConfigListPerVA***                        |
|                                                                       |
| Linkage for positioning SRS transmission in RRC_INACTIVE in each      |
| validity area. The field is included only if                          |
| *srs-PosRRC-InactiveAggBW-AdditionalCarriersPerVA-r18* is configured. |
+-----------------------------------------------------------------------+
| ***srs-PosRRC-InactiveValidityArea***                                 |
|                                                                       |
| Provides a list of cells where SRS Positioning Configuration in       |
| RRC_INACTIVE state is valid.                                          |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SuspendConfig* field descriptions                                    |
+=======================================================================+
| ***ncd-SSB-RedCapInitialBWP-SDT***                                    |
|                                                                       |
| Indicates that the UE uses the RedCap-specific initial DL BWP         |
| associated with the NCD-SSB for SDT. The network configures this      |
| field if an (e)RedCap UE is configured with SDT in the                |
| RedCap-specific initial DL BWP not associated with CD-SSB. If         |
| configured, the NCD-SSB indicated by this field can only be used      |
| during the SDT procedure for CG-SDT or RA-SDT. In the MIB associated  |
| with this NCD-SSB, the *systemFrameNumber* field indicates the frame  |
| boundary and frame number of the NCD-SSB. The                         |
| *subCarrierSpacingCommon* and *dmrs-TypeA-Position* field in the MIBs |
| associated with CD-SSB and NCD-SSB in the same cell are configured    |
| with the same values, respectively.                                   |
+-----------------------------------------------------------------------+
| ***ran-ExtendedPagingCycle***                                         |
|                                                                       |
| The extended DRX (eDRX) cycle for RAN-initiated paging to be applied  |
| by the UE as defined in TS 38.304 \[20\]. Value *rf256* corresponds   |
| to 256 radio frames, value *rf512* corresponds to 512 radio frames    |
| and so on. Value of the field indicates an eDRX cycle which is        |
| shorter or equal to the IDLE mode eDRX cycle configured for the UE.   |
+-----------------------------------------------------------------------+
| ***ran-ExtendedPagingCycleConfig***                                   |
|                                                                       |
| The extended DRX (eDRX) configuraiton for RAN-initiated paging to be  |
| applied by the UE when the eDRX cycle for RAN-initiated paging is     |
| longer than 10.24s.                                                   |
+-----------------------------------------------------------------------+
| ***ran-NotificationAreaInfo***                                        |
|                                                                       |
| Network ensures that the UE in RRC_INACTIVE always has a valid        |
| *ran-NotificationAreaInfo*.                                           |
+-----------------------------------------------------------------------+
| ***ran-PagingCycle***                                                 |
|                                                                       |
| Refers to the UE specific cycle for RAN-initiated paging. Value       |
| *rf32* corresponds to 32 radio frames, value *rf64* corresponds to 64 |
| radio frames and so on.                                               |
+-----------------------------------------------------------------------+
| ***resumeIndication***                                                |
|                                                                       |
| Indicates that the UE shall trigger the RRC connection resume         |
| procedure after receiving this *RRCRelease* message, as specified in  |
| clause 5.3.8.3. The network only includes this field in the           |
| *RRCRelease* message used to terminate an ongoing SDT procedure.      |
+-----------------------------------------------------------------------+
| ***sl-UEIdentityRemote***                                             |
|                                                                       |
| Indicates the C-RNTI to the L2 U2N Remote UE.                         |
+-----------------------------------------------------------------------+
| ***t380***                                                            |
|                                                                       |
| Refers to the timer that triggers the periodic RNAU procedure in UE.  |
| Value *min5* corresponds to 5 minutes, value *min10* corresponds to   |
| 10 minutes and so on.                                                 |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *MulticastConfigInactive* field descriptions                          |
+=======================================================================+
| ***inactivePTM-Config***                                              |
|                                                                       |
| Indicates the multicast session(s) that can be received in            |
| RRC_INACTIVE and optionally the corresponding PTM configuration       |
| (which includes *mrb-ListMulticast*, *pdsch-ConfigIndex*,             |
| *mtch-SSB-MappingWindowIndex*, etc.) for the cell where the multicast |
| session(s) was configured in RRC_CONNECTED. If absent, UE considers   |
| that all joined multicast sessions can be received in RRC_INACTIVE.   |
+-----------------------------------------------------------------------+
| ***inactiveMCCH-Config***                                             |
|                                                                       |
| Indicates multicast MCCH/MTCH configuration for MBS multicast         |
| reception in RRC_INACTIVE in the cell where the multicast session(s)  |
| was configured in RRC_CONNECTED. Only *SIB24* is allowed to be        |
| included.                                                             |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *ExtendedPagingCycleConfig* field descriptions                        |
+=======================================================================+
| ***extendedPagingCycle***                                             |
|                                                                       |
| The eDRX cycle longer than 10.24 s for RAN-initiated paging to be     |
| applied by the UE. Value hf2 corresponds to 2 hyper frames, value hf4 |
| corresponds to 4 hyper frames and so on. Value of the field is        |
| shorter than or equal to the IDLE mode eDRX cycle configured for the  |
| UE.                                                                   |
+-----------------------------------------------------------------------+
| ***pagingPTWLength***                                                 |
|                                                                       |
| The length of paging transmission window for RAN-initiated paging to  |
| be applied by the UE as defined in TS 38.304 \[20\]. Value ms1280     |
| corresponds to 1280 milliseconds, value ms2560 corresponds to 2560    |
| milliseconds and so on.                                               |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *L2RemoteUE*         The field is mandatory present for L2 U2N Remote
                       UE\'s RNAU; otherwise it is absent.

  *RANPaging*          This field is optionally present, Need R, if the
                       UE is configured with IDLE eDRX, see TS 24.501
                       \[23\]; otherwise the field is not present.

  *Redirection2*       The field is optionally present, Need R, if
                       *redirectedCarrierInfo* is included; otherwise the
                       field is not present.
  -----------------------------------------------------------------------

#### -- *RRCResume*

The *RRCResume* message is used to resume the suspended RRC connection.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*RRCResume* message

\-- ASN1START

\-- TAG-RRCRESUME-START

RRCResume ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcResume RRCResume-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCResume-IEs ::= SEQUENCE {

radioBearerConfig RadioBearerConfig OPTIONAL, \-- Need M

masterCellGroup OCTET STRING (CONTAINING CellGroupConfig) OPTIONAL, \--
Need M

measConfig MeasConfig OPTIONAL, \-- Need M

fullConfig ENUMERATED {true} OPTIONAL, \-- Need N

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RRCResume-v1560-IEs OPTIONAL

}

RRCResume-v1560-IEs ::= SEQUENCE {

radioBearerConfig2 OCTET STRING (CONTAINING RadioBearerConfig) OPTIONAL,
\-- Need M

sk-Counter SK-Counter OPTIONAL, \-- Need N

nonCriticalExtension RRCResume-v1610-IEs OPTIONAL

}

RRCResume-v1610-IEs ::= SEQUENCE {

idleModeMeasurementReq-r16 ENUMERATED {true} OPTIONAL, \-- Need N

restoreMCG-SCells-r16 ENUMERATED {true} OPTIONAL, \-- Need N

restoreSCG-r16 ENUMERATED {true} OPTIONAL, \-- Need N

mrdc-SecondaryCellGroup-r16 CHOICE {

nr-SCG-r16 OCTET STRING (CONTAINING RRCReconfiguration),

eutra-SCG-r16 OCTET STRING

} OPTIONAL, \-- Cond RestoreSCG

needForGapsConfigNR-r16 SetupRelease {NeedForGapsConfigNR-r16} OPTIONAL,
\-- Need M

nonCriticalExtension RRCResume-v1700-IEs OPTIONAL

}

RRCResume-v1700-IEs ::= SEQUENCE {

sl-ConfigDedicatedNR-r17 SetupRelease {SL-ConfigDedicatedNR-r16}
OPTIONAL, \-- Cond L2RemoteUE

sl-L2RemoteUE-Config-r17 SetupRelease {SL-L2RemoteUE-Config-r17}
OPTIONAL, \-- Cond L2RemoteUE

needForGapNCSG-ConfigNR-r17 SetupRelease {NeedForGapNCSG-ConfigNR-r17}
OPTIONAL, \-- Need M

needForGapNCSG-ConfigEUTRA-r17 SetupRelease
{NeedForGapNCSG-ConfigEUTRA-r17} OPTIONAL, \-- Need M

scg-State-r17 ENUMERATED {deactivated} OPTIONAL, \-- Need S

appLayerMeasConfig-r17 AppLayerMeasConfig-r17 OPTIONAL, \-- Need M

nonCriticalExtension RRCResume-v1800-IEs OPTIONAL

}

RRCResume-v1800-IEs ::= SEQUENCE {

needForInterruptionConfigNR-r18 ENUMERATED { disabled, enabled }
OPTIONAL, \-- Need M

reselectionMeasurementReq-r18 ENUMERATED { true } OPTIONAL, \-- Need N

validatedMeasurementsReq-r18 ENUMERATED { true } OPTIONAL, \-- Need N

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-RRCRESUME-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCResume-IEs* field descriptions                                    |
+=======================================================================+
| ***appLayerMeasConfig***                                              |
|                                                                       |
| This field is used to configure application layer measurements. This  |
| field is absent when the UE is configured to operate with shared      |
| spectrum channel access.                                              |
+-----------------------------------------------------------------------+
| ***idleModeMeasurementReq***                                          |
|                                                                       |
| This field indicates that the UE shall report the idle/inactive       |
| measurements, if available, to the network in the *RRCResumeComplete* |
| message                                                               |
+-----------------------------------------------------------------------+
| ***masterCellGroup***                                                 |
|                                                                       |
| Configuration of the master cell group.                               |
+-----------------------------------------------------------------------+
| ***mrdc-SecondaryCellGroup***                                         |
|                                                                       |
| Includes an RRC message for SCG configuration in NR-DC or NE-DC.      |
|                                                                       |
| For NR-DC (*nr-SCG*), *mrdc-SecondaryCellGroup* contains the          |
| *RRCReconfiguration* message as generated (entirely) by SN gNB. In    |
| this version of the specification, the RRC message can only include   |
| fields *secondaryCellGroup* (with at least                            |
| *reconfigurationWithSync*)*,* *otherConfig* and *measConfig*.         |
|                                                                       |
| For NE-DC (*eutra-SCG*), *mrdc-SecondaryCellGroup* includes the       |
| E-UTRA *RRCConnectionReconfiguration* message as specified in TS      |
| 36.331 \[10\]. In this version of the specification, the E-UTRA RRC   |
| message only include the field *scg-Configuration* with at least      |
| *mobilityControlInfoSCG*.                                             |
+-----------------------------------------------------------------------+
| ***needForGapsConfigNR***                                             |
|                                                                       |
| Configuration for the UE to report measurement gap requirement        |
| information of NR target bands in the *RRCReconfigurationComplete*    |
| and *RRCResumeComplete* message.                                      |
+-----------------------------------------------------------------------+
| ***needForGapNCSG-ConfigEUTRA***                                      |
|                                                                       |
| Configuration for the UE to report measurement gap and NCSG           |
| requirement information of E‑UTRA target bands in the                 |
| *RRCReconfigurationComplete* and *RRCResumeComplete* message.         |
+-----------------------------------------------------------------------+
| ***needForGapNCSG-ConfigNR***                                         |
|                                                                       |
| Configuration for the UE to report measurement gap and NCSG           |
| requirement information of NR target bands in the                     |
| *RRCReconfigurationComplete* and *RRCResumeComplete* message.         |
+-----------------------------------------------------------------------+
| ***needForInterruptionConfigNR***                                     |
|                                                                       |
| Indicates whether the UE shall report interruption requirement        |
| information of NR target bands in the *RRCReconfigurationComplete*    |
| and *RRCResumeComplete* message. The network sets this field to       |
| *enabled* only if the *needForGapsConfigNR* is configured. The        |
| network sets this field to *disabled* if the *needForGapsConfigNR* is |
| released.                                                             |
+-----------------------------------------------------------------------+
| ***radioBearerConfig***                                               |
|                                                                       |
| Configuration of Radio Bearers (DRBs, SRBs, multicast MRBs) including |
| SDAP/PDCP.                                                            |
+-----------------------------------------------------------------------+
| ***radioBearerConfig2***                                              |
|                                                                       |
| Configuration of Radio Bearers (DRBs, SRBs) including SDAP/PDCP. This |
| field can only be used if the UE supports NR-DC or NE-DC.             |
+-----------------------------------------------------------------------+
| ***reselectionMeasurementReq***                                       |
|                                                                       |
| This field indicates that the UE shall report the reselection         |
| measurements, if available, to the network in the *RRCResumeComplete* |
| message.                                                              |
+-----------------------------------------------------------------------+
| ***restoreMCG-SCells***                                               |
|                                                                       |
| Indicates that the UE shall restore the MCG SCells from the UE        |
| Inactive AS Context, if stored.                                       |
+-----------------------------------------------------------------------+
| ***restoreSCG***                                                      |
|                                                                       |
| Indicates that the UE shall restore the SCG configurations from the   |
| UE Inactive AS Context, if stored.                                    |
+-----------------------------------------------------------------------+
| ***scg-State***                                                       |
|                                                                       |
| Indicates that the SCG is in deactivated state.                       |
+-----------------------------------------------------------------------+
| ***sk-Counter***                                                      |
|                                                                       |
| A counter used to derive S-K~gNB~ or S-K~eNB~ based on the newly      |
| derived K~gNB~ during RRC Resume. The field is only included when     |
| there is one or more RB with *keyToUse* set to *secondary* *or        |
| mrdc-SecondaryCellGroup* is included.                                 |
+-----------------------------------------------------------------------+
| ***sl-ConfigDedicatedNR***                                            |
|                                                                       |
| This field is used to provide the dedicated configurations for NR     |
| sidelink communication/discovery used by L2 U2N Remote UE.            |
+-----------------------------------------------------------------------+
| ***sl-L2RemoteUE-Config***                                            |
|                                                                       |
| Contains L2 U2N relay operation related configurations used by L2 U2N |
| Remote UE. The field is absent if *appLayerMeasConfig* or SRB4 is     |
| configured/not released.                                              |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *L2RemoteUE*         The field is mandatory present for L2 U2N Remote
                       UE; otherwise it is absent.

  *RestoreSCG*         The field is mandatory present if *restoreSCG* is
                       included. It is optionally present, Need M,
                       otherwise.
  -----------------------------------------------------------------------

#### -- *RRCResumeComplete*

The *RRCResumeComplete* message is used to confirm the successful
completion of an RRC connection resumption.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*RRCResumeComplete* message

\-- ASN1START

\-- TAG-RRCRESUMECOMPLETE-START

RRCResumeComplete ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcResumeComplete RRCResumeComplete-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCResumeComplete-IEs ::= SEQUENCE {

dedicatedNAS-Message DedicatedNAS-Message OPTIONAL,

selectedPLMN-Identity INTEGER (1..maxPLMN) OPTIONAL,

uplinkTxDirectCurrentList UplinkTxDirectCurrentList OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RRCResumeComplete-v1610-IEs OPTIONAL

}

RRCResumeComplete-v1610-IEs ::= SEQUENCE {

idleMeasAvailable-r16 ENUMERATED {true} OPTIONAL,

measResultIdleEUTRA-r16 MeasResultIdleEUTRA-r16 OPTIONAL,

measResultIdleNR-r16 MeasResultIdleNR-r16 OPTIONAL,

scg-Response-r16 CHOICE {

nr-SCG-Response OCTET STRING (CONTAINING RRCReconfigurationComplete),

eutra-SCG-Response OCTET STRING

} OPTIONAL,

ue-MeasurementsAvailable-r16 UE-MeasurementsAvailable-r16 OPTIONAL,

mobilityHistoryAvail-r16 ENUMERATED {true} OPTIONAL,

mobilityState-r16 ENUMERATED {normal, medium, high, spare} OPTIONAL,

needForGapsInfoNR-r16 NeedForGapsInfoNR-r16 OPTIONAL,

nonCriticalExtension RRCResumeComplete-v1640-IEs OPTIONAL

}

RRCResumeComplete-v1640-IEs ::= SEQUENCE {

uplinkTxDirectCurrentTwoCarrierList-r16
UplinkTxDirectCurrentTwoCarrierList-r16 OPTIONAL,

nonCriticalExtension RRCResumeComplete-v1700-IEs OPTIONAL

}

RRCResumeComplete-v1700-IEs ::= SEQUENCE {

needForGapNCSG-InfoNR-r17 NeedForGapNCSG-InfoNR-r17 OPTIONAL,

needForGapNCSG-InfoEUTRA-r17 NeedForGapNCSG-InfoEUTRA-r17 OPTIONAL,

nonCriticalExtension RRCResumeComplete-v1720-IEs OPTIONAL

}

RRCResumeComplete-v1720-IEs ::= SEQUENCE {

uplinkTxDirectCurrentMoreCarrierList-r17
UplinkTxDirectCurrentMoreCarrierList-r17 OPTIONAL,

nonCriticalExtension RRCResumeComplete-v1800-IEs OPTIONAL

}

RRCResumeComplete-v1800-IEs ::= SEQUENCE {

needForInterruptionInfoNR-r18 NeedForInterruptionInfoNR-r18 OPTIONAL,

musim-CapRestrictionInd-r18 ENUMERATED {true} OPTIONAL,

flightPathInfoAvailable-r18 ENUMERATED {true} OPTIONAL,

measConfigReportAppLayerAvailable-r18 ENUMERATED {true} OPTIONAL,

measResultReselectionNR-r18 MeasResultIdleNR-r16 OPTIONAL,

reselectionMeasAvailable-r18 ENUMERATED {true} OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-RRCRESUMECOMPLETE-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCResumeComplete-IEs* field descriptions                            |
+=======================================================================+
| ***idleMeasAvailable***                                               |
|                                                                       |
| Indication that the UE has idle/inactive measurement report           |
| available.                                                            |
+-----------------------------------------------------------------------+
| ***measConfigReportAppLayerAvailable***                               |
|                                                                       |
| Indication that the UE has at least one application layer measurement |
| configuration with *appLayerIdleInactiveConfig* configured.           |
+-----------------------------------------------------------------------+
| ***measResultIdleEUTRA***                                             |
|                                                                       |
| EUTRA measurement results performed during RRC_INACTIVE.              |
+-----------------------------------------------------------------------+
| ***measResultIdleNR***                                                |
|                                                                       |
| NR measurement results performed during RRC_INACTIVE.                 |
+-----------------------------------------------------------------------+
| ***musim-CapRestrictionInd***                                         |
|                                                                       |
| This field indicates the UE temporary capability restriction due to   |
| MUSIM operation.                                                      |
+-----------------------------------------------------------------------+
| ***needForGapsInfoNR***                                               |
|                                                                       |
| This field is used to indicate the measurement gap requirement        |
| information of the UE for NR target bands.                            |
+-----------------------------------------------------------------------+
| ***needForGapNCSG-InfoEUTRA***                                        |
|                                                                       |
| This field is used to indicate the measurement gap and NCSG           |
| requirement information of the UE for E‑UTRA target bands             |
+-----------------------------------------------------------------------+
| ***needForGapNCSG-InfoNR***                                           |
|                                                                       |
| This field is used to indicate the measurement gap and NCSG           |
| requirement information of the UE for NR target bands                 |
+-----------------------------------------------------------------------+
| ***needForInterruptionInfoNR***                                       |
|                                                                       |
| This field indicates whether interruption is needed while performing  |
| measurement on NR target bands without measurement gap.               |
+-----------------------------------------------------------------------+
| ***reselectionMeasAvailable***                                        |
|                                                                       |
| Indication that the UE has reselection measurement report available.  |
+-----------------------------------------------------------------------+
| ***selectedPLMN-Identity***                                           |
|                                                                       |
| Index of the PLMN selected by the UE from the *plmn-IdentityInfoList* |
| or *npn-IdentityInfoList* fields included in *SIB1*.                  |
+-----------------------------------------------------------------------+
| ***uplinkTxDirectCurrentList***                                       |
|                                                                       |
| The Tx Direct Current locations for the configured serving cells and  |
| BWPs if requested by the NW (see *reportUplinkTxDirectCurrent* in     |
| *CellGroupConfig*).                                                   |
+-----------------------------------------------------------------------+
| ***uplinkTxDirectCurrentMoreCarrierList***                            |
|                                                                       |
| The Tx Direct Current locations for the configured intra-band CA      |
| requested by *reportUplinkTxDirectCurrentMoreCarrier-r17*.            |
+-----------------------------------------------------------------------+
| ***uplinkTxDirectCurrentTwoCarrierList***                             |
|                                                                       |
| The Tx Direct Current locations for the configured uplink intra-band  |
| CA with two carriers if requested by the NW (see                      |
| *reportUplinkTxDirectCurrentTwoCarrier-r16* in *CellGroupConfig*).    |
+-----------------------------------------------------------------------+

#### -- *RRCResumeRequest*

The *RRCResumeRequest* message is used to request the resumption of a
suspended RRC connection or perform an RNA update.

Signalling radio bearer: SRB0

RLC-SAP: TM

Logical channel: CCCH

Direction: UE to Network

*RRCResumeRequest* message

\-- ASN1START

\-- TAG-RRCRESUMEREQUEST-START

RRCResumeRequest ::= SEQUENCE {

rrcResumeRequest RRCResumeRequest-IEs

}

RRCResumeRequest-IEs ::= SEQUENCE {

resumeIdentity ShortI-RNTI-Value,

resumeMAC-I BIT STRING (SIZE (16)),

resumeCause ResumeCause,

spare BIT STRING (SIZE (1))

}

\-- TAG-RRCRESUMEREQUEST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCResumeRequest-IEs* field descriptions                             |
+=======================================================================+
| ***resumeCause***                                                     |
|                                                                       |
| Provides the resume cause for the RRC connection resume request as    |
| provided by the upper layers or RRC. The network is not expected to   |
| reject an *RRCResumeRequest* due to unknown cause value being used by |
| the UE.                                                               |
+-----------------------------------------------------------------------+
| ***resumeIdentity***                                                  |
|                                                                       |
| UE identity to facilitate UE context retrieval at gNB.                |
+-----------------------------------------------------------------------+
| ***resumeMAC-I***                                                     |
|                                                                       |
| Authentication token to facilitate UE authentication at gNB. The 16   |
| least significant bits of the MAC-I calculated using the AS security  |
| configuration as specified in 5.3.13.3.                               |
+-----------------------------------------------------------------------+

#### -- *RRCResumeRequest1*

The *RRCResumeRequest1* message is used to request the resumption of a
suspended RRC connection or perform an RNA update.

Signalling radio bearer: SRB0

RLC-SAP: TM

Logical channel: CCCH1

Direction: UE to Network

*RRCResumeRequest1* message

\-- ASN1START

\-- TAG-RRCRESUMEREQUEST1-START

RRCResumeRequest1 ::= SEQUENCE {

rrcResumeRequest1 RRCResumeRequest1-IEs

}

RRCResumeRequest1-IEs ::= SEQUENCE {

resumeIdentity I-RNTI-Value,

resumeMAC-I BIT STRING (SIZE (16)),

resumeCause ResumeCause,

spare BIT STRING (SIZE (1))

}

\-- TAG-RRCRESUMEREQUEST1-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCResumeRequest1-IEs* field descriptions                            |
+=======================================================================+
| ***resumeCause***                                                     |
|                                                                       |
| Provides the resume cause for the *RRCResumeRequest1* as provided by  |
| the upper layers or RRC. A gNB is not expected to reject an           |
| *RRCResumeRequest1* due to unknown cause value being used by the UE.  |
+-----------------------------------------------------------------------+
| ***resumeIdentity***                                                  |
|                                                                       |
| UE identity to facilitate UE context retrieval at gNB.                |
+-----------------------------------------------------------------------+
| ***resumeMAC-I***                                                     |
|                                                                       |
| Authentication token to facilitate UE authentication at gNB. The 16   |
| least significant bits of the MAC-I calculated using the AS security  |
| configuration as specified in 5.3.13.3.                               |
+-----------------------------------------------------------------------+

#### -- *RRCSetup*

The *RRCSetup* message is used to establish SRB1.

Signalling radio bearer: SRB0

RLC-SAP: TM

Logical channel: CCCH

Direction: Network to UE

*RRCSetup* message

\-- ASN1START

\-- TAG-RRCSETUP-START

RRCSetup ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcSetup RRCSetup-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCSetup-IEs ::= SEQUENCE {

radioBearerConfig RadioBearerConfig,

masterCellGroup OCTET STRING (CONTAINING CellGroupConfig),

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RRCSetup-v1700-IEs OPTIONAL

}

RRCSetup-v1700-IEs ::= SEQUENCE {

sl-ConfigDedicatedNR-r17 SL-ConfigDedicatedNR-r16 OPTIONAL, \-- Cond
L2RemoteUE

sl-L2RemoteUE-Config-r17 SL-L2RemoteUE-Config-r17 OPTIONAL, \-- Cond
L2RemoteUE

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-RRCSETUP-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCSetup-IEs* field descriptions                                     |
+=======================================================================+
| ***masterCellGroup***                                                 |
|                                                                       |
| The network configures only the RLC bearer for the SRB1,              |
| *mac-CellGroupConfig*, *physicalCellGroupConfig* and *spCellConfig*.  |
+-----------------------------------------------------------------------+
| ***radioBearerConfig***                                               |
|                                                                       |
| Only SRB1 can be configured in RRC setup.                             |
+-----------------------------------------------------------------------+
| ***sl-ConfigDedicatedNR***                                            |
|                                                                       |
| Contains dedicated configurations for NR sidelink communication. The  |
| network configures only the PC5 Relay RLC channel and                 |
| *sl-PHY-MAC-RLC-Config* used for the SRB1.                            |
+-----------------------------------------------------------------------+
| ***sl-L2RemoteUE-Config***                                            |
|                                                                       |
| Contains dedicated configurations used for L2 U2N relay related       |
| operation. The network configures only the SRAP configuration used    |
| for the SRB1 and local UE ID.                                         |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *L2RemoteUE*         The field is mandatory present for L2 U2N Remote
                       UE; otherwise it is absent.

  -----------------------------------------------------------------------

#### -- *RRCSetupComplete*

The *RRCSetupComplete* message is used to confirm the successful
completion of an RRC connection establishment.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*RRCSetupComplete* message

\-- ASN1START

\-- TAG-RRCSETUPCOMPLETE-START

RRCSetupComplete ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcSetupComplete RRCSetupComplete-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCSetupComplete-IEs ::= SEQUENCE {

selectedPLMN-Identity INTEGER (1..maxPLMN),

registeredAMF RegisteredAMF OPTIONAL,

guami-Type ENUMERATED {native, mapped} OPTIONAL,

s-NSSAI-List SEQUENCE (SIZE (1..maxNrofS-NSSAI)) OF S-NSSAI OPTIONAL,

dedicatedNAS-Message DedicatedNAS-Message,

ng-5G-S-TMSI-Value CHOICE {

ng-5G-S-TMSI NG-5G-S-TMSI,

ng-5G-S-TMSI-Part2 BIT STRING (SIZE (9))

} OPTIONAL,

lateNonCriticalExtension OCTET STRING (CONTAINING
RRCSetupComplete-v15s0-IEs) OPTIONAL,

nonCriticalExtension RRCSetupComplete-v1610-IEs OPTIONAL

}

\-- Regular non-critical extensions:

RRCSetupComplete-v1610-IEs ::= SEQUENCE {

iab-NodeIndication-r16 ENUMERATED {true} OPTIONAL,

idleMeasAvailable-r16 ENUMERATED {true} OPTIONAL,

ue-MeasurementsAvailable-r16 UE-MeasurementsAvailable-r16 OPTIONAL,

mobilityHistoryAvail-r16 ENUMERATED {true} OPTIONAL,

mobilityState-r16 ENUMERATED {normal, medium, high, spare} OPTIONAL,

nonCriticalExtension RRCSetupComplete-v1690-IEs OPTIONAL

}

RRCSetupComplete-v1690-IEs ::= SEQUENCE {

ul-RRC-Segmentation-r16 ENUMERATED {true} OPTIONAL,

nonCriticalExtension RRCSetupComplete-v1700-IEs OPTIONAL

}

RRCSetupComplete-v1700-IEs ::= SEQUENCE {

onboardingRequest-r17 ENUMERATED {true} OPTIONAL,

nonCriticalExtension RRCSetupComplete-v1800-IEs OPTIONAL

}

RRCSetupComplete-v1800-IEs ::= SEQUENCE {

ncr-NodeIndication-r18 ENUMERATED {true} OPTIONAL,

musim-CapRestrictionInd-r18 ENUMERATED {true} OPTIONAL,

flightPathInfoAvailable-r18 ENUMERATED {true} OPTIONAL,

measConfigReportAppLayerAvailable-r18 ENUMERATED {true} OPTIONAL,

mobileIAB-NodeIndication-r18 ENUMERATED {true} OPTIONAL,

reselectionMeasAvailable-r18 ENUMERATED {true} OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

\-- Late non-critical extensions:

RRCSetupComplete-v15s0-IEs ::= SEQUENCE {

\-- Following field is only for REL-15 late non-critical extensions

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RRCSetupComplete-v16j0-IEs OPTIONAL

}

RRCSetupComplete-v16j0-IEs ::= SEQUENCE {

\-- Following field is only for REL-16 late non-critical extensions

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension RRCSetupComplete-v17b0-IEs OPTIONAL

}

RRCSetupComplete-v17b0-IEs ::= SEQUENCE {

ul-RRC-MaxCapaSegments-r17 ENUMERATED {true} OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

RegisteredAMF ::= SEQUENCE {

plmn-Identity PLMN-Identity OPTIONAL,

amf-Identifier AMF-Identifier

}

\-- TAG-RRCSETUPCOMPLETE-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCSetupComplete-IEs* field descriptions                             |
+=======================================================================+
| ***guami-Type***                                                      |
|                                                                       |
| This field is used to indicate whether the GUAMI included is native   |
| (derived from native 5G-GUTI) or mapped (from EPS, derived from EPS   |
| GUTI) as specified in TS 24.501 \[23\].                               |
+-----------------------------------------------------------------------+
| ***iab-NodeIndication***                                              |
|                                                                       |
| This field is used to indicate that the connection is being           |
| established by an IAB-node as specified in TS 38.300 \[2\]. If this   |
| field is included, the UE shall not include the field                 |
| *mobileIAB-NodeIndication*.                                           |
+-----------------------------------------------------------------------+
| ***idleMeasAvailable***                                               |
|                                                                       |
| Indication that the UE has idle/inactive measurement report           |
| available.                                                            |
+-----------------------------------------------------------------------+
| ***measConfigReportAppLayerAvailable***                               |
|                                                                       |
| Indication that the UE has at least one application layer measurement |
| configuration with *appLayerIdleInactiveConfig* configured.           |
+-----------------------------------------------------------------------+
| ***mobileIAB-NodeIndication***                                        |
|                                                                       |
| This field is used to indicate that the connection is being           |
| established by a mobile IAB-node as specified in TS 38.300 \[2\]. If  |
| this field is included, the UE shall not include the field            |
| *iab-NodeIndication*.                                                 |
+-----------------------------------------------------------------------+
| ***mobilityState***                                                   |
|                                                                       |
| This field indicates the UE mobility state (as defined in TS 38.304   |
| \[20\], clause 5.2.4.3) just prior to UE going into RRC_CONNECTED     |
| state. The UE indicates the value of *medium* and *high* when being   |
| in Medium-mobility and High-mobility states respectively. Otherwise   |
| the UE indicates the value *normal*.                                  |
+-----------------------------------------------------------------------+
| ***musim-CapRestrictionInd***                                         |
|                                                                       |
| This field indicates the UE temporary capability restriction due to   |
| MUSIM operation.                                                      |
+-----------------------------------------------------------------------+
| ***ncr-NodeIndication***                                              |
|                                                                       |
| This field is used to indicate that the connection is being           |
| established by an NCR-node as specified in TS 38.300 \[2\].           |
+-----------------------------------------------------------------------+
| ***ng-5G-S-TMSI-Part2***                                              |
|                                                                       |
| The leftmost 9 bits of 5G-S-TMSI.                                     |
+-----------------------------------------------------------------------+
| ***onboardingRequest***                                               |
|                                                                       |
| This field indicates that the connection is being established for UE  |
| onboarding in the selected onboarding SNPN, see TS 23.501 \[32\].     |
+-----------------------------------------------------------------------+
| ***registeredAMF***                                                   |
|                                                                       |
| This field is used to transfer the GUAMI of the AMF where the UE is   |
| registered, as provided by upper layers, see TS 23.003 \[21\].        |
+-----------------------------------------------------------------------+
| ***reselectionMeasAvailable***                                        |
|                                                                       |
| Indication that the UE has reselection measurement report available.  |
+-----------------------------------------------------------------------+
| ***selectedPLMN-Identity***                                           |
|                                                                       |
| Index of the PLMN or SNPN selected by the UE from the                 |
| *plmn-IdentityInfoList* or *npn-IdentityInfoList* fields included in  |
| SIB1.                                                                 |
+-----------------------------------------------------------------------+
| ***ul-RRC-MaxCapaSegments***                                          |
|                                                                       |
| This field indicates that the UE supports uplink RRC segmentation of  |
| *UECapabilityInformation* according to the network indication         |
| *rrc-MaxCapaSegAllowed*.                                              |
+-----------------------------------------------------------------------+
| ***ul-RRC-Segmentation***                                             |
|                                                                       |
| This field indicates the UE supports uplink RRC segmentation of       |
| *UECapabilityInformation* according to the network indication         |
| *rrc-SegAllowed.*                                                     |
+-----------------------------------------------------------------------+

#### *-- RRCSetupRequest*

The *RRCSetupRequest* message is used to request the establishment of an
RRC connection.

Signalling radio bearer: SRB0

RLC-SAP: TM

Logical channel: CCCH

Direction: UE to Network

*RRCSetupRequest message*

\-- ASN1START

\-- TAG-RRCSETUPREQUEST-START

RRCSetupRequest ::= SEQUENCE {

rrcSetupRequest RRCSetupRequest-IEs

}

RRCSetupRequest-IEs ::= SEQUENCE {

ue-Identity InitialUE-Identity,

establishmentCause EstablishmentCause,

spare BIT STRING (SIZE (1))

}

InitialUE-Identity ::= CHOICE {

ng-5G-S-TMSI-Part1 BIT STRING (SIZE (39)),

randomValue BIT STRING (SIZE (39))

}

EstablishmentCause ::= ENUMERATED {

emergency, highPriorityAccess, mt-Access, mo-Signalling,

mo-Data, mo-VoiceCall, mo-VideoCall, mo-SMS, mps-PriorityAccess,
mcs-PriorityAccess,

spare6, spare5, spare4, spare3, spare2, spare1}

\-- TAG-RRCSETUPREQUEST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCSetupRequest-IEs* field descriptions                              |
+=======================================================================+
| ***establishmentCause***                                              |
|                                                                       |
| Provides the establishment cause for the *RRCSetupRequest* in         |
| accordance with the information received from upper layers. gNB is    |
| not expected to reject an *RRCSetupRequest* due to unknown cause      |
| value being used by the UE.                                           |
+-----------------------------------------------------------------------+
| ***ue-Identity***                                                     |
|                                                                       |
| UE identity included to facilitate contention resolution by lower     |
| layers.                                                               |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *InitialUE-Identity* field descriptions                               |
+=======================================================================+
| ***ng-5G-S-TMSI-Part1***                                              |
|                                                                       |
| The rightmost 39 bits of 5G-S-TMSI.                                   |
+-----------------------------------------------------------------------+
| ***randomValue***                                                     |
|                                                                       |
| Integer value in the range 0 to 2^39^ -- 1.                           |
+-----------------------------------------------------------------------+

#### -- *RRCSystemInfoRequest*

The *RRCSystemInfoRequest* message is used to request SI message(s)
required by the UE as specified in clause 5.2.2.3.3 and 5.2.2.3.3a.

Signalling radio bearer: SRB0

RLC-SAP: TM

Logical channel: CCCH

Direction: UE to Network

*RRCSystemInfoRequest* message

\-- ASN1START

\-- TAG-RRCSYSTEMINFOREQUEST-START

RRCSystemInfoRequest ::= SEQUENCE {

criticalExtensions CHOICE {

rrcSystemInfoRequest RRCSystemInfoRequest-IEs,

criticalExtensionsFuture-r16 CHOICE {

rrcPosSystemInfoRequest-r16 RRC-PosSystemInfoRequest-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

}

RRCSystemInfoRequest-IEs ::= SEQUENCE {

requested-SI-List BIT STRING (SIZE (maxSI-Message)), \--32bits

spare BIT STRING (SIZE (12))

}

RRC-PosSystemInfoRequest-r16-IEs ::= SEQUENCE {

requestedPosSI-List BIT STRING (SIZE (maxSI-Message)), \--32bits

spare BIT STRING (SIZE (11))

}

\-- TAG-RRCSYSTEMINFOREQUEST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RRCSystemInfoRequest-IEs* field descriptions                         |
+=======================================================================+
| ***requested-SI-List***                                               |
|                                                                       |
| Contains a list of requested SI messages which are configured by      |
| *schedulingInfoList* in *si-SchedulingInfo* and *schedulingInfoList2* |
| in *si-SchedulingInfo-v1700* (if present) in SIB1.                    |
|                                                                       |
| If *si-SchedulingInfo-v1700* is not present:                          |
|                                                                       |
| \- According to the order of entry in the list of SI messages         |
| configured by *schedulingInfoList* in *si-SchedulingInfo* in *SIB1*,  |
| first bit corresponds to first/leftmost listed SI message, second bit |
| corresponds to second listed SI message, and so on.                   |
|                                                                       |
| If *si-SchedulingInfo-v1700* is present:                              |
|                                                                       |
| \- The UE generates a list of concatenated SI messages by appending   |
| the SI messages containing type1 SIB configured by                    |
| *schedulingInfoList2* in *si-SchedulingInfo-v1700* to the SI messages |
| configured by *schedulingInfoList* in *si-SchedulingInfo*.            |
|                                                                       |
| \- According to the order of entry in the list of concatenated SI     |
| messages, first bit corresponds to first/leftmost listed SI message,  |
| second bit corresponds to second listed SI message, and so on.        |
+-----------------------------------------------------------------------+
| ***requestedPosSI-List***                                             |
|                                                                       |
| Contains a list of requested SI messages which are configured by      |
| *posSchedulingInfoList* in *posSI-SchedulingInfo* and                 |
| *schedulingInfoList2* in *si-SchedulingInfo-v1700* (if present) in    |
| SIB1.                                                                 |
|                                                                       |
| If *si-SchedulingInfo-v1700* is not present:                          |
|                                                                       |
| \- According to the order of entry in the list of SI messages         |
| configured by *pos*S*chedulingInfoList* in *posSI*-*SchedulingInfo*   |
| in *SIB1*, first bit corresponds to first/leftmost listed SI message, |
| second bit corresponds to second listed SI message, and so on.        |
|                                                                       |
| If *si-SchedulingInfo-v1700* is present:                              |
|                                                                       |
| \- The UE creates a list of concatenated SI messages by appending the |
| SI messages containing type2 SIB configured by *schedulingInfoList2*  |
| in *si-SchedulingInfo-v1700* to the SI messages configured by         |
| *posSchedulingInfoList* in *posSI-SchedulingInfo*.                    |
|                                                                       |
| \- According to the order of entry in the list of concatenated SI     |
| messages, first bit corresponds to first/leftmost listed SI message,  |
| second bit corresponds to second listed SI message, and so on.        |
+-----------------------------------------------------------------------+

#### *-- SCGFailureInformation*

The *SCGFailureInformation* message is used to provide information
regarding NR SCG failures detected by the UE.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*SCGFailureInformation* message

\-- ASN1START

\-- TAG-SCGFAILUREINFORMATION-START

SCGFailureInformation ::= SEQUENCE {

criticalExtensions CHOICE {

scgFailureInformation SCGFailureInformation-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

SCGFailureInformation-IEs ::= SEQUENCE {

failureReportSCG FailureReportSCG OPTIONAL,

nonCriticalExtension SCGFailureInformation-v1590-IEs OPTIONAL

}

SCGFailureInformation-v1590-IEs ::= SEQUENCE {

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

FailureReportSCG ::= SEQUENCE {

failureType ENUMERATED {

t310-Expiry, randomAccessProblem,

rlc-MaxNumRetx,

synchReconfigFailureSCG, scg-ReconfigFailure,

srb3-IntegrityFailure, other-r16, spare1},

measResultFreqList MeasResultFreqList OPTIONAL,

measResultSCG-Failure OCTET STRING (CONTAINING MeasResultSCG-Failure)
OPTIONAL,

\...,

\[\[

locationInfo-r16 LocationInfo-r16 OPTIONAL,

failureType-v1610 ENUMERATED {scg-lbtFailure-r16,
beamFailureRecoveryFailure-r16,

t312-Expiry-r16, bh-RLF-r16, beamFailure-r17, spare3, spare2, spare1}
OPTIONAL

\]\],

\[\[

previousPSCellId-r17 SEQUENCE {

physCellId-r17 PhysCellId,

carrierFreq-r17 ARFCN-ValueNR

} OPTIONAL,

failedPSCellId-r17 SEQUENCE {

physCellId-r17 PhysCellId,

carrierFreq-r17 ARFCN-ValueNR

} OPTIONAL,

timeSCGFailure-r17 INTEGER (0..1023) OPTIONAL,

perRAInfoList-r17 PerRAInfoList-r16 OPTIONAL

\]\],

\[\[

perRAInfoList-v17b0 PerRAInfoList-v1660 OPTIONAL

\]\],

\[\[

perRAInfoList-v1840 PerRAInfoList-v1800 OPTIONAL

\]\]

}

MeasResultFreqList ::= SEQUENCE (SIZE (1..maxFreq)) OF MeasResult2NR

\-- TAG-SCGFAILUREINFORMATION-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SCGFailureInformation field descriptions*                            |
+-----------------------------------------------------------------------+
| ***measResultFreqList***                                              |
|                                                                       |
| The field contains available results of measurements on NR            |
| frequencies the UE is configured to measure by *measConfig*.          |
+-----------------------------------------------------------------------+
| ***measResultSCG-Failure***                                           |
|                                                                       |
| The field contains the *MeasResultSCG-Failure* IE which includes      |
| available results of measurements on NR frequencies the UE is         |
| configured to measure by the NR SCG *RRCReconfiguration* message.     |
+-----------------------------------------------------------------------+
| ***previousPSCellId***                                                |
|                                                                       |
| This field indicates the physical cell id and carrier frequency of    |
| the cell that is the source PSCell of the last PSCell change. In case |
| of PSCell addition failure, this field is absent.                     |
+-----------------------------------------------------------------------+
| ***failedPSCellId***                                                  |
|                                                                       |
| This field indicates the physical cell id and carrier frequency of    |
| the cell in which SCG failure is detected or the target PSCell of the |
| failed PSCell change or failed PSCell addition.                       |
+-----------------------------------------------------------------------+
| ***timeSCGFailure***                                                  |
|                                                                       |
| This field is used to indicate the time elapsed since the last        |
| execution of *RRCReconfiguration* with *reconfigurationWithSync* for  |
| the SCG until the SCG failure. Actual value = field value \* 100ms.   |
| The maximum value 1023 means 102.3s or longer.                        |
+=======================================================================+

#### *-- SCGFailureInformationEUTRA*

The *SCGFailureInformationEUTRA* message is used to provide information
regarding E-UTRA SCG failures detected by the UE.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*SCGFailureInformationEUTRA* message

\-- ASN1START

\-- TAG-SCGFAILUREINFORMATIONEUTRA-START

SCGFailureInformationEUTRA ::= SEQUENCE {

criticalExtensions CHOICE {

scgFailureInformationEUTRA SCGFailureInformationEUTRA-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

SCGFailureInformationEUTRA-IEs ::= SEQUENCE {

failureReportSCG-EUTRA FailureReportSCG-EUTRA OPTIONAL,

nonCriticalExtension SCGFailureInformationEUTRA-v1590-IEs OPTIONAL

}

SCGFailureInformationEUTRA-v1590-IEs ::= SEQUENCE {

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

FailureReportSCG-EUTRA ::= SEQUENCE {

failureType ENUMERATED {

t313-Expiry, randomAccessProblem,rlc-MaxNumRetx,

scg-ChangeFailure, spare4,

spare3, spare2, spare1},

measResultFreqListMRDC MeasResultFreqListFailMRDC OPTIONAL,

measResultSCG-FailureMRDC OCTET STRING OPTIONAL,

\...,

\[\[

locationInfo-r16 LocationInfo-r16 OPTIONAL

\]\]

}

MeasResultFreqListFailMRDC ::= SEQUENCE (SIZE (1.. maxFreq)) OF
MeasResult2EUTRA

\-- TAG-SCGFAILUREINFORMATIONEUTRA-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SCGFailureInformationEUTRA field descriptions*                       |
+-----------------------------------------------------------------------+
| ***measResultFreqListMRDC***                                          |
|                                                                       |
| The field contains available results of measurements on E-UTRA        |
| frequencies the UE is configured to measure by *measConfig*.          |
+-----------------------------------------------------------------------+
| ***measResultSCG-FailureMRDC***                                       |
|                                                                       |
| Includes the E-UTRA *MeasResultSCG-FailureMRDC* IE as specified in TS |
| 36.331 \[10\]. The field contains available results of measurements   |
| on E-UTRA frequencies the UE is configured to measure by the E-UTRA   |
| *RRCConnectionReconfiguration* message.                               |
+=======================================================================+

#### -- *SecurityModeCommand*

The *SecurityModeCommand* message is used to command the activation of
AS security.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*SecurityModeCommand* message

\-- ASN1START

\-- TAG-SECURITYMODECOMMAND-START

SecurityModeCommand ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

securityModeCommand SecurityModeCommand-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

SecurityModeCommand-IEs ::= SEQUENCE {

securityConfigSMC SecurityConfigSMC,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

SecurityConfigSMC ::= SEQUENCE {

securityAlgorithmConfig SecurityAlgorithmConfig,

\...

}

\-- TAG-SECURITYMODECOMMAND-STOP

\-- ASN1STOP

#### -- *SecurityModeComplete*

The *SecurityModeComplete* message is used to confirm the successful
completion of a security mode command.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*SecurityModeComplete* message

\-- ASN1START

\-- TAG-SECURITYMODECOMPLETE-START

SecurityModeComplete ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

securityModeComplete SecurityModeComplete-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

SecurityModeComplete-IEs ::= SEQUENCE {

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

\-- TAG-SECURITYMODECOMPLETE-STOP

\-- ASN1STOP

#### -- *SecurityModeFailure*

The *SecurityModeFailure* message is used to indicate an unsuccessful
completion of a security mode command.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*SecurityModeFailure* message

\-- ASN1START

\-- TAG-SECURITYMODEFAILURE-START

SecurityModeFailure ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

securityModeFailure SecurityModeFailure-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

SecurityModeFailure-IEs ::= SEQUENCE {

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

\-- TAG-SECURITYMODEFAILURE-STOP

\-- ASN1STOP

#### -- *SIB1*

*SIB1* contains information relevant when evaluating if a UE is allowed
to access a cell and defines the scheduling of other system information.
It also contains radio resource configuration information that is common
for all UEs and barring information applied to the unified access
control.

Signalling radio bearer: N/A

RLC-SAP: TM

Logical channels: BCCH

Direction: Network to UE

*SIB1* message

\-- ASN1START

\-- TAG-SIB1-START

SIB1 ::= SEQUENCE {

cellSelectionInfo SEQUENCE {

q-RxLevMin Q-RxLevMin,

q-RxLevMinOffset INTEGER (1..8) OPTIONAL, \-- Need S

q-RxLevMinSUL Q-RxLevMin OPTIONAL, \-- Need R

q-QualMin Q-QualMin OPTIONAL, \-- Need S

q-QualMinOffset INTEGER (1..8) OPTIONAL \-- Need S

} OPTIONAL, \-- Cond Standalone

cellAccessRelatedInfo CellAccessRelatedInfo,

connEstFailureControl ConnEstFailureControl OPTIONAL, \-- Need R

si-SchedulingInfo SI-SchedulingInfo OPTIONAL, \-- Need R

servingCellConfigCommon ServingCellConfigCommonSIB OPTIONAL, \-- Need R

ims-EmergencySupport ENUMERATED {true} OPTIONAL, \-- Need R

eCallOverIMS-Support ENUMERATED {true} OPTIONAL, \-- Need R

ue-TimersAndConstants UE-TimersAndConstants OPTIONAL, \-- Need R

uac-BarringInfo SEQUENCE {

uac-BarringForCommon UAC-BarringPerCatList OPTIONAL, \-- Need S

uac-BarringPerPLMN-List UAC-BarringPerPLMN-List OPTIONAL, \-- Need S

uac-BarringInfoSetList UAC-BarringInfoSetList,

uac-AccessCategory1-SelectionAssistanceInfo CHOICE {

plmnCommon UAC-AccessCategory1-SelectionAssistanceInfo,

individualPLMNList SEQUENCE (SIZE (2..maxPLMN)) OF
UAC-AccessCategory1-SelectionAssistanceInfo

} OPTIONAL \-- Need S

} OPTIONAL, \-- Need R

useFullResumeID ENUMERATED {true} OPTIONAL, \-- Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SIB1-v1610-IEs OPTIONAL

}

SIB1-v1610-IEs ::= SEQUENCE {

idleModeMeasurementsEUTRA-r16 ENUMERATED{true} OPTIONAL, \-- Need R

idleModeMeasurementsNR-r16 ENUMERATED{true} OPTIONAL, \-- Need R

posSI-SchedulingInfo-r16 PosSI-SchedulingInfo-r16 OPTIONAL, \-- Need R

nonCriticalExtension SIB1-v1630-IEs OPTIONAL

}

SIB1-v1630-IEs ::= SEQUENCE {

uac-BarringInfo-v1630 SEQUENCE {

uac-AC1-SelectAssistInfo-r16 SEQUENCE (SIZE (2..maxPLMN)) OF
UAC-AC1-SelectAssistInfo-r16

} OPTIONAL, \-- Need R

nonCriticalExtension SIB1-v1700-IEs OPTIONAL

}

SIB1-v1700-IEs ::= SEQUENCE {

hsdn-Cell-r17 ENUMERATED {true} OPTIONAL, \-- Need R

uac-BarringInfo-v1700 SEQUENCE {

uac-BarringInfoSetList-v1700 UAC-BarringInfoSetList-v1700

} OPTIONAL, \-- Cond MINT

sdt-ConfigCommon-r17 SDT-ConfigCommonSIB-r17 OPTIONAL, \-- Need R

redCap-ConfigCommon-r17 RedCap-ConfigCommonSIB-r17 OPTIONAL, \-- Need R

featurePriorities-r17 SEQUENCE {

redCapPriority-r17 FeaturePriority-r17 OPTIONAL, \-- Need R

slicingPriority-r17 FeaturePriority-r17 OPTIONAL, \-- Need R

msg3-Repetitions-Priority-r17 FeaturePriority-r17 OPTIONAL, \-- Need R

sdt-Priority-r17 FeaturePriority-r17 OPTIONAL \-- Need R

} OPTIONAL, \-- Need R

si-SchedulingInfo-v1700 SI-SchedulingInfo-v1700 OPTIONAL, \-- Need R

hyperSFN-r17 BIT STRING (SIZE (10)) OPTIONAL, \-- Need R

eDRX-AllowedIdle-r17 ENUMERATED {true} OPTIONAL, \-- Need R

eDRX-AllowedInactive-r17 ENUMERATED {true} OPTIONAL, \-- Cond EDRX-RC

intraFreqReselectionRedCap-r17 ENUMERATED {allowed, notAllowed}
OPTIONAL, \-- Need S

cellBarredNTN-r17 ENUMERATED {barred, notBarred} OPTIONAL, \-- Need S

nonCriticalExtension SIB1-v1740-IEs OPTIONAL

}

SIB1-v1740-IEs ::= SEQUENCE {

si-SchedulingInfo-v1740 SI-SchedulingInfo-v1740 OPTIONAL, \-- Need R

nonCriticalExtension SIB1-v1800-IEs OPTIONAL

}

SIB1-v1800-IEs ::= SEQUENCE {

ncr-Support-r18 ENUMERATED {true} OPTIONAL, \-- Need S

mt-SDT-ConfigCommonSIB-r18 MT-SDT-ConfigCommonSIB-r18 OPTIONAL, \-- Need
R

musim-CapRestrictionAllowed-r18 ENUMERATED {true} OPTIONAL, \-- Need R

featurePriorities-v1800 SEQUENCE {

msg1-Repetitions-Priority-r18 FeaturePriority-r17 OPTIONAL, \-- Need R

eRedCapPriority-r18 FeaturePriority-r17 OPTIONAL \-- Need R

} OPTIONAL, \-- Need R

si-SchedulingInfo-v1800 SI-SchedulingInfo-v1800 OPTIONAL, \-- Need R

cellBarredATG-r18 ENUMERATED {barred, notBarred} OPTIONAL, \-- Need S

cellBarredNES-r18 ENUMERATED {notBarred} OPTIONAL, \-- Need R

mobileIAB-Cell-r18 ENUMERATED {true} OPTIONAL, \-- Need R

eDRX-AllowedInactive-r18 ENUMERATED {true} OPTIONAL, \-- Cond EDRX-RC

intraFreqReselection-eRedCap-r18 ENUMERATED {allowed, notAllowed}
OPTIONAL, \-- Need S

nonServingCellMII-r18 ENUMERATED {true} OPTIONAL, \-- Need R

sdt-BeamFailureRecoveryProhibitTimer-r18 ENUMERATED {ms50, ms100, ms200,
ms500, ms1000, ms1500, ms2000, ms3000}

OPTIONAL, \-- Need R

eRedCap-ConfigCommon-r18 ERedCap-ConfigCommonSIB-r18 OPTIONAL, \-- Need
R

cellBarredFixedVSAT-r18 ENUMERATED {barred, notBarred} OPTIONAL, \--
Cond NTN

cellBarredMobileVSAT-r18 ENUMERATED {barred, notBarred} OPTIONAL, \--
Cond NTN

reselectionMeasurementsNR-r18 ENUMERATED{true} OPTIONAL, \-- Need R

cellBarred2RxXR-r18 ENUMERATED {barred} OPTIONAL, \-- Need R

intraFreqReselection2RxXR-r18 ENUMERATED {allowed, notAllowed} OPTIONAL,
\-- Cond 2RxXR

barringExemptEmergencyCall-r18 ENUMERATED {true} OPTIONAL, \-- Cond
EM-Barring

n3c-Support-r18 ENUMERATED {true} OPTIONAL, \-- Need R

nonCriticalExtension SEQUENCE {} OPTIONAL

}

UAC-AccessCategory1-SelectionAssistanceInfo ::= ENUMERATED {a, b, c}

UAC-AC1-SelectAssistInfo-r16 ::= ENUMERATED {a, b, c, notConfigured}

SDT-ConfigCommonSIB-r17 ::= SEQUENCE {

sdt-RSRP-Threshold-r17 RSRP-Range OPTIONAL, \-- Need R

sdt-LogicalChannelSR-DelayTimer-r17 ENUMERATED { sf20, sf40, sf64,
sf128, sf512, sf1024, sf2560, spare1} OPTIONAL, \-- Need R

sdt-DataVolumeThreshold-r17 ENUMERATED {byte32, byte100, byte200,
byte400, byte600, byte800, byte1000, byte2000, byte4000,

byte8000, byte9000, byte10000, byte12000, byte24000, byte48000,
byte96000},

t319a-r17 ENUMERATED { ms100, ms200, ms300, ms400, ms600, ms1000,
ms2000,

ms3000, ms4000, spare7, spare6, spare5, spare4, spare3, spare2, spare1}

}

RedCap-ConfigCommonSIB-r17 ::= SEQUENCE {

halfDuplexRedCapAllowed-r17 ENUMERATED {true} OPTIONAL, \-- Need R

cellBarredRedCap-r17 SEQUENCE {

cellBarredRedCap1Rx-r17 ENUMERATED {barred, notBarred},

cellBarredRedCap2Rx-r17 ENUMERATED {barred, notBarred}

} OPTIONAL, \-- Need R

\...

}

ERedCap-ConfigCommonSIB-r18 ::= SEQUENCE {

cellBarred-eRedCap-r18 SEQUENCE {

cellBarred-eRedCap1Rx-r18 ENUMERATED {barred, notBarred},

cellBarred-eRedCap2Rx-r18 ENUMERATED {barred, notBarred}

}

}

FeaturePriority-r17 ::= INTEGER (0..7)

MT-SDT-ConfigCommonSIB-r18 ::= SEQUENCE {

mt-SDT-RSRP-Threshold-r18 RSRP-Range OPTIONAL, \-- Need S

sdt-LogicalChannelSR-DelayTimer-r18 ENUMERATED { sf20, sf40, sf64,
sf128, sf512, sf1024, sf2560, spare1} OPTIONAL, \-- Cond MT-SDT1

t319a-r18 ENUMERATED { ms100, ms200, ms300, ms400, ms600, ms1000,
ms2000,

ms3000, ms4000, spare7, spare6, spare5, spare4,

spare3, spare2, spare1} OPTIONAL \-- Cond MT-SDT2

}

\-- TAG-SIB1-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB1* field descriptions                                             |
+=======================================================================+
| ***barringExemptEmergencyCall***                                      |
|                                                                       |
| Indicates whether the cell allows emergency bearer services for UEs   |
| who would otherwise consider the cell as barred as specified in TS    |
| 38.304 \[20\].                                                        |
+-----------------------------------------------------------------------+
| ***cellBarred2RxXR***                                                 |
|                                                                       |
| Value *barred* means that the cell is barred for a 2Rx XR UE          |
| indicating *supportOf2RxXR* for the selected frequency band as        |
| specified in clause 5.2.2.4.2. This field is ignored by all UEs not   |
| indicating *supportOf2RxXR* for the selected frequency band. This     |
| field may be configured only if the cell operates in a frequency band |
| where 4Rx antenna ports are mandated as specified in TS 38.101-1      |
| \[15\]. If this field is absent on a cell operating in a frequency    |
| band where 4RX antenna ports are mandated, a 2RX XR UE shall treat    |
| the cell as not barred, as specified in TS 38.304 \[20\].             |
+-----------------------------------------------------------------------+
| ***cellBarredATG***                                                   |
|                                                                       |
| Value *barred* means that the cell is barred for connectivity to ATG, |
| as defined in TS 38.304 \[20\]. Value *notBarred* means that the cell |
| is allowed for connectivity to ATG. If not present, the UE considers  |
| the cell is not allowed for connectivity to ATG, as defined in TS     |
| 38.304 \[20\]. This field is only applicable to ATG-capable UEs.      |
+-----------------------------------------------------------------------+
| ***cellBarred-eRedCap1Rx***                                           |
|                                                                       |
| Value *barred* means that the cell is barred for an eRedCap UE        |
| supporting 1 Rx branch on the selected frequency band as specified in |
| clause 5.2.2.4.2, as defined in TS 38.304 \[20\]. This field is       |
| ignored by non-eRedCap UEs. An eRedCap UE supporting 2 Rx on the      |
| selected frequency band as specified in clause 5.2.2.4.2 shall ignore |
| this field when *cellBarred-eRedCap2Rx* is set to *notBarred*.        |
+-----------------------------------------------------------------------+
| ***cellBarred-eRedCap2Rx***                                           |
|                                                                       |
| Value *barred* means that the cell is barred for an eRedCap UE        |
| supporting 2 Rx branches on the selected frequency band as specified  |
| in clause 5.2.2.4.2, as defined in TS 38.304 \[20\]. This field is    |
| ignored by non-eRedCap UEs. An eRedCap UE supporting 1 Rx on the      |
| selected frequency band as specified in clause 5.2.2.4.2 shall ignore |
| this field when *cellBarred-eRedCap1Rx* is set to *notBarred*.        |
+-----------------------------------------------------------------------+
| ***cellBarredFixedVSAT***                                             |
|                                                                       |
| Value *barred* means that the cell is barred for fixed VSAT UEs, as   |
| defined in TS 38.304 \[20\]. If not present, the cell is not allowed  |
| for fixed VSAT UEs. This field is ignored by non-VSAT UEs.            |
+-----------------------------------------------------------------------+
| ***cellBarredMobileVSAT***                                            |
|                                                                       |
| Value *barred* means that the cell is barred for mobile VSAT UEs, as  |
| defined in TS 38.304 \[20\]. If not present, the cell is not allowed  |
| for mobile VSAT UEs. This field is ignored by non-VSAT UEs.           |
+-----------------------------------------------------------------------+
| ***cellBarredNES***                                                   |
|                                                                       |
| This field indicates the cell barring status for UEs supporting       |
| *nes-CellDTX-DRX* on the selected frequency band as described in      |
| 5.2.2.4.2.                                                            |
+-----------------------------------------------------------------------+
| ***cellBarredNTN***                                                   |
|                                                                       |
| Value *barred* means that the cell is barred for connectivity to NTN, |
| as defined in TS 38.304 \[20\]. Value *notBarred* means that the cell |
| is allowed for connectivity to NTN. If not present, the UE considers  |
| the cell is not allowed for connectivity to NTN, as defined in TS     |
| 38.304 \[20\]. This field is only applicable to NTN-capable UEs.      |
+-----------------------------------------------------------------------+
| ***cellBarredRedCap1Rx***                                             |
|                                                                       |
| Value *barred* means that the cell is barred for a RedCap UE          |
| supporting 1 Rx branch on the selected frequency band as specified in |
| clause 5.2.2.4.2, as defined in TS 38.304 \[20\]. This field is       |
| ignored by non-RedCap UEs. A RedCap UE supporting 2 Rx on the         |
| selected frequency band as specified in clause 5.2.2.4.2 shall ignore |
| this field when *cellBarredRedCap2Rx* is set to *notBarred*.          |
+-----------------------------------------------------------------------+
| ***cellBarredRedCap2Rx***                                             |
|                                                                       |
| Value *barred* means that the cell is barred for a RedCap UE          |
| supporting 2 Rx branches on the selected frequency band as specified  |
| in clause 5.2.2.4.2, as defined in TS 38.304 \[20\]. This field is    |
| ignored by non-RedCap UEs. A RedCap UE supporting 1 Rx on the         |
| selected frequency band as specified in clause 5.2.2.4.2 shall ignore |
| this field when *cellBarredRedCap1Rx* is set to *notBarred*.          |
+-----------------------------------------------------------------------+
| ***cellSelectionInfo***                                               |
|                                                                       |
| Parameters for cell selection related to the serving cell.            |
+-----------------------------------------------------------------------+
| ***eCallOverIMS-Support***                                            |
|                                                                       |
| Indicates whether the cell supports eCall over IMS services as        |
| defined in TS 23.501 \[32\]. If absent, eCall over IMS is not         |
| supported by the network in the cell.                                 |
+-----------------------------------------------------------------------+
| ***eDRX-AllowedIdle***                                                |
|                                                                       |
| The presence of this field indicates that extended DRX for CN paging  |
| is allowed in the cell for UEs in RRC_IDLE or RRC_INACTIVE. The UE    |
| shall stop using extended DRX for CN paging in RRC_IDLE or            |
| RRC_INACTIVE if *eDRX-AllowedIdle* is not present.                    |
+-----------------------------------------------------------------------+
| ***eDRX-AllowedInactive***                                            |
|                                                                       |
| The presence of *eDRX-AllowedInactive-r17* indicates that extended    |
| DRX cycle equal to or shorter than 10.24 s for RAN paging is allowed  |
| in the cell for UEs in RRC_INACTIVE. The UE shall stop using extended |
| DRX cycle equal to or shorter than 10.24 s for RAN paging in          |
| RRC_INACTIVE if *eDRX-AllowedInactive-r17* is not present. The        |
| presence of *eDRX-AllowedInactive-r18* indicates that extended DRX    |
| cycle longer than 10.24 s for RAN paging is allowed in the cell for   |
| UEs in RRC_INACTIVE. The UE shall stop using extended DRX cycle       |
| longer than 10.24 s for RAN paging in RRC_INACTIVE if                 |
| *eDRX-AllowedInactive-r18* is not present.                            |
+-----------------------------------------------------------------------+
| ***featurePriorities***                                               |
|                                                                       |
| Indicates priorities for features, such as (e)RedCap, Slicing, SDT,   |
| MSG1-Repetitions and MSG3-Repetitions for Coverage Enhancements.      |
| These priorities are used to determine which                          |
| *FeatureCombinationPreambles* the UE shall use when a feature maps to |
| more than one *FeatureCombinationPreambles*, as specified in TS       |
| 38.321 \[3\]. A lower value means a higher priority. The network does |
| not signal the same priority for more than one feature. The network   |
| signals a priority for all feature that map to at least one           |
| *FeatureCombinationPreambles*.                                        |
+-----------------------------------------------------------------------+
| ***halfDuplexRedCap-Allowed***                                        |
|                                                                       |
| The presence of this field indicates that the cell supports           |
| half-duplex FDD (e)RedCap UEs.                                        |
+-----------------------------------------------------------------------+
| ***hsdn-Cell***                                                       |
|                                                                       |
| This field indicates this is a HSDN cell as specified in TS 38.304    |
| \[20\].                                                               |
+-----------------------------------------------------------------------+
| ***hyperSFN***                                                        |
|                                                                       |
| Indicates hyper SFN which increments by one when the SFN wraps        |
| around. This field is excluded when determining changes in system     |
| information, i.e. changes of hyper SFN should not result in system    |
| information change notifications.                                     |
+-----------------------------------------------------------------------+
| ***idleModeMeasurementsEUTRA***                                       |
|                                                                       |
| This field indicates that a UE that is configured for EUTRA           |
| idle/inactive measurements shall perform the measurements while       |
| camping in this cell and report availability of these measurements    |
| when establishing or resuming a connection in this cell. If absent, a |
| UE is not required to perform EUTRA idle/inactive measurements.       |
+-----------------------------------------------------------------------+
| ***idleModeMeasurementsNR***                                          |
|                                                                       |
| This field indicates that a UE that is configured for NR              |
| idle/inactive measurements shall perform the measurements while       |
| camping in this cell and report availability of these measurements    |
| when establishing or resuming a connection in this cell. If absent, a |
| UE is not required to perform NR idle/inactive measurements.          |
+-----------------------------------------------------------------------+
| ***ims-EmergencySupport***                                            |
|                                                                       |
| Indicates whether the cell supports IMS emergency bearer services for |
| UEs in limited service mode. If absent, IMS emergency call is not     |
| supported by the network in the cell for UEs in limited service mode. |
+-----------------------------------------------------------------------+
| ***intraFreqReselection2RxXR***                                       |
|                                                                       |
| This field controls cell selection/reselection to intra-frequency     |
| cells for 2Rx XR UEs when this cell is barred or treated as barred by |
| the 2Rx XR UE, as specified in TS 38.304 \[20\]. This field is        |
| ignored by all UEs that are not 2Rx XR UEs. This field may be         |
| configured only if the cell operates in a frequency band where 4Rx    |
| antenna ports are mandated, as specified in TS 38.101-1 \[15\].       |
+-----------------------------------------------------------------------+
| ***intraFreqReselection-eRedCap***                                    |
|                                                                       |
| Controls cell selection/reselection to intra-frequency cells for      |
| eRedCap UEs when this cell is barred, or treated as barred by the     |
| eRedCap UE, as specified in TS 38.304 \[20\]. If not present, an      |
| eRedCap UE treats the cell as barred, i.e., the UE considers that the |
| cell does not support eRedCap.                                        |
+-----------------------------------------------------------------------+
| ***intraFreqReselectionRedCap***                                      |
|                                                                       |
| Controls cell selection/reselection to intra-frequency cells for      |
| RedCap UEs when this cell is barred, or treated as barred by the      |
| RedCap UE, as specified in TS 38.304 \[20\]. If not present, a RedCap |
| UE treats the cell as barred, i.e.,the UE considers that the cell     |
| does not support RedCap.                                              |
+-----------------------------------------------------------------------+
| ***mobileIAB-Cell***                                                  |
|                                                                       |
| The presence of this field indicates that this is a mobile IAB cell.  |
+-----------------------------------------------------------------------+
| ***mt-SDT-RSRP-Threshold***                                           |
|                                                                       |
| RSRP threshold used to determine whether MT-SDT procedure can be      |
| initiated, as specified in TS 38.321 \[3\]. If the field is absent,   |
| and the field *sdt-RSRP-Threshold* is present, the UE applies the     |
| value in the field *sdt-RSRP-Threshold*.                              |
+-----------------------------------------------------------------------+
| ***musim-CapRestrictionAllowed***                                     |
|                                                                       |
| Indicates the UE is allowed to send the *musim-CapRestrictionInd* in  |
| *RRCSetupComplete*, *RRCResumeComplete* and                           |
| *RRCReestablishmentComplete* messages.                                |
+-----------------------------------------------------------------------+
| ***n3c-Support***                                                     |
|                                                                       |
| This field indicates the support of N3C MP. If the field is present,  |
| the UE can perform early detection of candidate N3C relay UEs. If     |
| absent, a UE is not required to perform early detection of candidate  |
| N3C relay UEs.                                                        |
+-----------------------------------------------------------------------+
| ***ncr-Support***                                                     |
|                                                                       |
| This field combines both the support of NCR and the cell status for   |
| NCR. If the field is present, the cell supports NCR and the cell is   |
| also considered as a candidate for cell (re)selection for NCR-node;   |
| if the field is absent, the cell does not support NCR and/or the cell |
| is barred for NCR-node.                                               |
+-----------------------------------------------------------------------+
| ***nonServingCellMII***                                               |
|                                                                       |
| Indicates whether the *MBSInterestIndication* message for MBS         |
| broadcast reception on a non-serving cell is allowed to be            |
| transmitted to the serving gNB.                                       |
+-----------------------------------------------------------------------+
| ***q-QualMin***                                                       |
|                                                                       |
| Parameter \"Q~qualmin~\" in TS 38.304 \[20\], applicable for serving  |
| cell. If the field is absent, the UE applies the (default) value of   |
| negative infinity for Q~qualmin~.                                     |
+-----------------------------------------------------------------------+
| ***q-QualMinOffset***                                                 |
|                                                                       |
| Parameter \"Q~qualminoffset~\" in TS 38.304 \[20\]. Actual value      |
| Q~qualminoffset~ = field value \[dB\]. If the field is absent, the UE |
| applies the (default) value of 0 dB for Q~qualminoffset~. Affects the |
| minimum required quality level in the cell.                           |
+-----------------------------------------------------------------------+
| ***q-RxLevMin***                                                      |
|                                                                       |
| Parameter \"Q~rxlevmin~\" in TS 38.304 \[20\], applicable for serving |
| cell.                                                                 |
+-----------------------------------------------------------------------+
| ***q-RxLevMinOffset***                                                |
|                                                                       |
| Parameter \"Q~rxlevminoffset~\" in TS 38.304 \[20\]. Actual value     |
| Q~rxlevminoffset~ = field value \* 2 \[dB\]. If absent, the UE        |
| applies the (default) value of 0 dB for Q~rxlevminoffset~*.* Affects  |
| the minimum required Rx level in the cell.                            |
+-----------------------------------------------------------------------+
| ***q-RxLevMinSUL***                                                   |
|                                                                       |
| Parameter \"Q~rxlevmin~\" in TS 38.304 \[20\], applicable for serving |
| cell.                                                                 |
+-----------------------------------------------------------------------+
| ***reselectionMeasurementsNR***                                       |
|                                                                       |
| This field indicates that a UE that is configured for NR reselection  |
| measurements shall report availability of these measurements when     |
| establishing or resuming a connection in this cell.                   |
+-----------------------------------------------------------------------+
| ***sdt-BeamFailureRecoveryProhibitTimer***                            |
|                                                                       |
| The value of the prohibit timer used for RACH for beam failure        |
| indication during SDT as specified in TS 38.321 \[3\]. Value *ms50*   |
| corresponds to 50 milliseconds, value *ms100* corresponds to 100      |
| milliseconds and so on.                                               |
+-----------------------------------------------------------------------+
| ***sdt-DataVolumeThreshold***                                         |
|                                                                       |
| Data volume threshold used to determine whether SDT can be initiated, |
| as specified in TS 38.321 \[3\]. Value *byte32* corresponds to 32     |
| bytes, value *byte100* corresponds to 100 bytes, and so on.           |
+-----------------------------------------------------------------------+
| ***sdt-LogicalChannelSR-DelayTimer***                                 |
|                                                                       |
| The value of *logicalChannelSR-DelayTimer* applied during SDT for     |
| logical channels configured with SDT, as specified in TS 38.321       |
| \[3\]. Value in number of subframes. Value *sf20* corresponds to 20   |
| subframes, *sf40* corresponds to 40 subframes, and so on. If          |
| *sdt-LogicalChannelSR-DelayTimer-r18* is absent and                   |
| *sdt-LogicalChannelSR-DelayTimer-r17* is present then, the UE applies |
| the value configured in *sdt-LogicalChannelSR-DelayTimer-r17* for     |
| this field. If this field is not configured, then                     |
| logicalChannelSR-DelayTimer is not applied for SDT logical channels.  |
+-----------------------------------------------------------------------+
| ***sdt-RSRP-Threshold***                                              |
|                                                                       |
| RSRP threshold used to determine whether SDT procedure can be         |
| initiated, as specified in TS 38.321 \[3\].                           |
+-----------------------------------------------------------------------+
| ***servingCellConfigCommon***                                         |
|                                                                       |
| Configuration of the serving cell.                                    |
+-----------------------------------------------------------------------+
| ***t319a***                                                           |
|                                                                       |
| Initial value of the timer T319a used for detection of SDT failure.   |
| Value *ms100* corresponds to 100 milliseconds, value *ms200*          |
| corresponds to 200 milliseconds and so on. If *t319a-r18* is absent,  |
| the UE applies the value configured in *t319a-r17.*                   |
+-----------------------------------------------------------------------+
| ***uac-AccessCategory1-SelectionAssistanceInfo***                     |
|                                                                       |
| Information used to determine whether Access Category 1 applies to    |
| the UE, as defined in TS 22.261 \[25\]. If *plmnCommon* is chosen,    |
| the *UAC-AccessCategory1-SelectionAssistanceInfo* is applicable to    |
| all the PLMNs and SNPNs in *plmn-IdentityInfoList* and                |
| *npn-IdentityInfoList*. If *individualPLMNList* is chosen, the 1^st^  |
| entry in the list corresponds to the first network within all of the  |
| PLMNs and SNPNs across the *plmn-IdentityList* and the                |
| *npn-IdentityInfoList*, the 2^nd^ entry in the list corresponds to    |
| the second network within all of the PLMNs and SNPNs across the       |
| *plmn-IdentityList* and the *npn-IdentityInfoList* and so on. If      |
| *uac-AC1-SelectAssistInfo-r16* is present, the UE shall ignore the    |
| *uac-AccessCategory1-SelectionAssistanceInfo*.                        |
+-----------------------------------------------------------------------+
| ***uac-AC1-SelectAssistInfo***                                        |
|                                                                       |
| Information used to determine whether Access Category 1 applies to    |
| the UE, as defined in TS 22.261 \[25\]. The 1^st^ entry in the list   |
| corresponds to the first network within all of the PLMNs and SNPNs    |
| across the *plmn-IdentityList* and *npn-IdentityInfoList*, the 2^nd^  |
| entry in the list corresponds to the second network within all of the |
| PLMNs and SNPNs across the *plmn-IdentityList* and the                |
| *npn-IdentityInfoList* and so on. Value *notConfigured* indicates     |
| that Access Category1 is not configured for the corresponding         |
| PLMN/SNPN.                                                            |
+-----------------------------------------------------------------------+
| ***uac-BarringForCommon***                                            |
|                                                                       |
| Common access control parameters for each access category. Common     |
| values are used for all PLMNs/SNPNs, unless overwritten by the        |
| PLMN/SNPN specific configuration provided in                          |
| *uac-BarringPerPLMN-List*. The parameters are specified by providing  |
| an index to the set of configurations (*uac-BarringInfoSetList*). UE  |
| behaviour upon absence of this field is specified in clause 5.3.14.2. |
+-----------------------------------------------------------------------+
| ***ue-TimersAndConstants***                                           |
|                                                                       |
| Timer and constant values to be used by the UE. The cell operating as |
| PCell always provides this field.                                     |
+-----------------------------------------------------------------------+
| ***useFullResumeID***                                                 |
|                                                                       |
| Indicates which resume identifier and Resume request message should   |
| be used. UE uses *fullI-RNTI* and *RRCResumeRequest1* if the field is |
| present, or *shortI-RNTI* and *RRCResumeRequest* if the field is      |
| absent.                                                               |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *2RxXR*              This field is mandatory present if
                       *cellBarred2RxXR* is present, otherwise it is
                       absent, Need R.

  *EDRX-RC*            The field is optionally present, Need R, in a cell
                       that enables *eDRX-AllowedIdle*, otherwise it is
                       absent.

  *EM-Barring*         The field is optionally present, Need R, in a cell
                       that supports (e)RedCap or 2Rx XR UEs, otherwise
                       it is absent.

  *MINT*               The field is optionally present, Need R, in a cell
                       that provides a configuration for disaster
                       roaming, otherwise it is absent, Need R.

  *MT-SDT1*            This field is optionally present, Need S, in a
                       cell that supports MT-SDT if
                       *sdt-ConfigCommon-r17* is not present, otherwise
                       it is absent.

  *MT-SDT2*            This field is mandatory present in a cell that
                       supports MT-SDT if *sdt-ConfigCommon-r17* is not
                       present, otherwise it is absent.

  *NTN*                The field is optionally present, Need S, in a cell
                       where *cellBarredNTN* is included with value
                       *notBarred*, otherwise it is absent.

  *Standalone*         The field is mandatory present in a cell that
                       supports standalone operation, otherwise it is
                       absent.
  -----------------------------------------------------------------------

#### -- *SidelinkUEInformationNR*

The *SidelinkUEinformationNR* message is used for the indication of NR
sidelink UE information to the network.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*SidelinkUEInformationNR* message

\-- ASN1START

\-- TAG-SIDELINKUEINFORMATIONNR-START

SidelinkUEInformationNR-r16::= SEQUENCE {

criticalExtensions CHOICE {

sidelinkUEInformationNR-r16 SidelinkUEInformationNR-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

SidelinkUEInformationNR-r16-IEs ::= SEQUENCE {

sl-RxInterestedFreqList-r16 SL-InterestedFreqList-r16 OPTIONAL,

sl-TxResourceReqList-r16 SL-TxResourceReqList-r16 OPTIONAL,

sl-FailureList-r16 SL-FailureList-r16 OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SidelinkUEInformationNR-v1700-IEs OPTIONAL

}

SidelinkUEInformationNR-v1700-IEs ::= SEQUENCE {

sl-TxResourceReqList-v1700 SL-TxResourceReqList-v1700 OPTIONAL,

sl-RxDRX-ReportList-v1700 SL-RxDRX-ReportList-v1700 OPTIONAL,

sl-RxInterestedGC-BC-DestList-r17 SL-RxInterestedGC-BC-DestList-r17
OPTIONAL,

sl-RxInterestedFreqListDisc-r17 SL-InterestedFreqList-r16 OPTIONAL,

sl-TxResourceReqListDisc-r17 SL-TxResourceReqListDisc-r17 OPTIONAL,

sl-TxResourceReqListCommRelay-r17 SL-TxResourceReqListCommRelay-r17
OPTIONAL,

ue-Type-r17 ENUMERATED {relayUE, remoteUE} OPTIONAL,

sl-SourceIdentityRemoteUE-r17 SL-SourceIdentity-r17 OPTIONAL,

nonCriticalExtension SidelinkUEInformationNR-v1800-IEs OPTIONAL

}

SidelinkUEInformationNR-v1800-IEs ::= SEQUENCE {

sl-CarrierFailureList-r18 SL-CarrierFailureList-r18 OPTIONAL,

sl-TxResourceReqListL2-U2U-r18 SEQUENCE (SIZE (1..maxNrofSL-Dest-r16))
OF SL-TxResourceReqL2-U2U-r18 OPTIONAL,

sl-PosRxInterestedFreqList-r18 SL-InterestedFreqList-r16 OPTIONAL,

sl-PosTxResourceReqList-r18 SL-PosTxResourceReqList-r18 OPTIONAL,

nonCriticalExtension SidelinkUEInformationNR-v1840-IEs OPTIONAL

}

SidelinkUEInformationNR-v1840-IEs ::= SEQUENCE {

sl-PosRxInterestedFreqList2-r18 SL-InterestedFreqList-r16 OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

SL-InterestedFreqList-r16 ::= SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
INTEGER (1..maxNrofFreqSL-r16)

SL-TxResourceReqList-r16 ::= SEQUENCE (SIZE (1..maxNrofSL-Dest-r16)) OF
SL-TxResourceReq-r16

SL-PosTxResourceReqList-r18 ::= SEQUENCE (SIZE (1..maxNrofSL-Dest-r16))
OF SL-PosTxResourceReq-r18

SL-TxResourceReq-r16 ::= SEQUENCE {

sl-DestinationIdentity-r16 SL-DestinationIdentity-r16,

sl-CastType-r16 ENUMERATED {broadcast, groupcast, unicast, spare1},

sl-RLC-ModeIndicationList-r16 SEQUENCE (SIZE (1.. maxNrofSLRB-r16)) OF
SL-RLC-ModeIndication-r16 OPTIONAL,

sl-QoS-InfoList-r16 SEQUENCE (SIZE (1..maxNrofSL-QFIsPerDest-r16)) OF
SL-QoS-Info-r16 OPTIONAL,

sl-TypeTxSyncList-r16 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-TypeTxSync-r16 OPTIONAL,

sl-TxInterestedFreqList-r16 SL-TxInterestedFreqList-r16 OPTIONAL,

sl-CapabilityInformationSidelink-r16 OCTET STRING OPTIONAL

}

SL-TxResourceReqList-v1700 ::= SEQUENCE (SIZE (1..maxNrofSL-Dest-r16))
OF SL-TxResourceReq-v1700

SL-RxDRX-ReportList-v1700 ::= SEQUENCE (SIZE (1..maxNrofSL-Dest-r16)) OF
SL-RxDRX-Report-v1700

SL-TxResourceReq-v1700 ::= SEQUENCE {

sl-DRX-InfoFromRxList-r17 SEQUENCE (SIZE (1..maxNrofSL-RxInfoSet-r17))
OF SL-DRX-ConfigUC-SemiStatic-r17 OPTIONAL,

sl-DRX-Indication-r17 ENUMERATED {on, off} OPTIONAL,

\...,

\[\[

sl-QoS-InfoList-v1800 SEQUENCE (SIZE (1..maxNrofSL-QFIsPerDest-r16)) OF
SL-QoS-Info-v1800 OPTIONAL

\]\]

}

SL-RxDRX-Report-v1700 ::= SEQUENCE {

sl-DRX-ConfigFromTx-r17 SL-DRX-ConfigUC-SemiStatic-r17,

\...

}

SL-RxInterestedGC-BC-DestList-r17 ::= SEQUENCE (SIZE
(1..maxNrofSL-Dest-r16)) OF SL-RxInterestedGC-BC-Dest-r17

SL-RxInterestedGC-BC-Dest-r17 ::= SEQUENCE {

sl-RxInterestedQoS-InfoList-r17 SEQUENCE (SIZE
(1..maxNrofSL-QFIsPerDest-r16)) OF SL-QoS-Info-r16,

sl-DestinationIdentity-r16 SL-DestinationIdentity-r16

}

SL-TxResourceReqListDisc-r17 ::= SEQUENCE (SIZE (1..maxNrofSL-Dest-r16))
OF SL-TxResourceReqDisc-r17

SL-TxResourceReqDisc-r17 ::= SEQUENCE {

sl-DestinationIdentityDisc-r17 SL-DestinationIdentity-r16,

sl-SourceIdentityRelayUE-r17 SL-SourceIdentity-r17 OPTIONAL,

sl-CastTypeDisc-r17 ENUMERATED {broadcast, groupcast, unicast, spare1},

sl-TxInterestedFreqListDisc-r17 SL-TxInterestedFreqList-r16,

sl-TypeTxSyncListDisc-r17 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-TypeTxSync-r16,

sl-DiscoveryType-r17 ENUMERATED {relay, non-Relay},

\...,

\[\[

ue-TypeU2U-r18 ENUMERATED {relayUE, remoteUE} OPTIONAL

\]\]

}

SL-TxResourceReqListCommRelay-r17 ::= SEQUENCE (SIZE
(1..maxNrofSL-Dest-r16)) OF SL-TxResourceReqCommRelayInfo-r17

SL-TxResourceReqCommRelayInfo-r17 ::= SEQUENCE {

sl-RelayDRXConfig-r17 SL-TxResourceReq-v1700 OPTIONAL,

sl-TxResourceReqCommRelay-r17 SL-TxResourceReqCommRelay-r17

}

SL-TxResourceReqCommRelay-r17 ::= CHOICE {

sl-TxResourceReqL2U2N-Relay-r17 SL-TxResourceReqL2U2N-Relay-r17,

sl-TxResourceReqL3U2N-Relay-r17 SL-TxResourceReq-r16

}

SL-TxResourceReqL2U2N-Relay-r17 ::= SEQUENCE {

sl-DestinationIdentityL2U2N-r17 SL-DestinationIdentity-r16 OPTIONAL,

sl-TxInterestedFreqListL2U2N-r17 SL-TxInterestedFreqList-r16,

sl-TypeTxSyncListL2U2N-r17 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-TypeTxSync-r16,

sl-LocalID-Request-r17 ENUMERATED {true} OPTIONAL,

sl-PagingIdentityRemoteUE-r17 SL-PagingIdentityRemoteUE-r17 OPTIONAL,

sl-CapabilityInformationSidelink-r17 OCTET STRING OPTIONAL,

\...

}

SL-TxResourceReqL2-U2U-r18 ::= SEQUENCE {

sl-DestinationIdentityL2-U2U-r18 SL-DestinationIdentity-r16 OPTIONAL,

sl-TxInterestedFreqListL2-U2U-r18 SL-TxInterestedFreqList-r16,

sl-TypeTxSyncListL2-U2U-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-TypeTxSync-r16,

sl-CapabilityInformationSidelink-r18 OCTET STRING OPTIONAL,

sl-U2U-InfoList-r18 SEQUENCE (SIZE (1.. maxNrofRemoteUE-r17)) OF
SL-U2U-Info-r18 OPTIONAL,

sl-RLC-ModeIndicationListL2-U2U-r18 SEQUENCE (SIZE (1..
maxNrofSLRB-r16)) OF SL-RLC-Mode-r18 OPTIONAL,

\...

}

SL-U2U-Info-r18 ::= SEQUENCE {

sl-U2U-Identity-r18 CHOICE {

sl-TargetUE-Identity-r18 SL-DestinationIdentity-r16,

sl-SourceUE-Identity-r18 SL-SourceIdentity-r17

},

sl-E2E-QoS-InfoList-r18 SEQUENCE (SIZE (1.. maxNrofSL-QFIsPerDest-r16))
OF SL-QoS-Info-r16 OPTIONAL,

sl-PerHop-QoS-InfoList-r18 SEQUENCE (SIZE (1..
maxNrofSL-QFIsPerDest-r16)) OF SL-SplitQoS-Info-r18 OPTIONAL,

sl-PerSLRB-QoS-InfoList-r18 SEQUENCE (SIZE (1.. maxNrofSLRB-r16)) OF
SL-PerSLRB-QoS-Info-r18 OPTIONAL,

sl-CapabilityInformationTargetRemoteUE-r18 OCTET STRING OPTIONAL

}

SL-PosTxResourceReq-r18 ::= SEQUENCE {

sl-PosDestinationIdentity-r18 SL-DestinationIdentity-r16,

sl-PosCastType-r18 ENUMERATED {broadcast, groupcast, unicast, spare1},

sl-PosTxInterestedFreqList-r18 SL-TxInterestedFreqList-r16 OPTIONAL,

sl-PosTypeTxSyncList-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-TypeTxSync-r16 OPTIONAL,

sl-PosQoS-InfoList-r18 SEQUENCE (SIZE (1..maxNrofSL-PRS-PerDest-r18)) OF
SL-PRS-QoS-Info-r18 OPTIONAL,

sl-CapabilityInformationSidelink-r18 OCTET STRING OPTIONAL,

\...,

\[\[

sl-PosTxInterestedFreqList2-r18 SL-TxInterestedFreqList-r16 OPTIONAL

\]\]

}

SL-TxInterestedFreqList-r16 ::= SEQUENCE (SIZE (1..maxNrofFreqSL-r16))
OF INTEGER (1..maxNrofFreqSL-r16)

SL-QoS-Info-r16 ::= SEQUENCE {

sl-QoS-FlowIdentity-r16 SL-QoS-FlowIdentity-r16,

sl-QoS-Profile-r16 SL-QoS-Profile-r16 OPTIONAL

}

SL-QoS-Info-v1800 ::= SEQUENCE {

sl-TxInterestedFreqList-r18 SL-TxInterestedFreqList-r16,

sl-TxProfile-r18 SL-TxProfile-r18 OPTIONAL,

\...

}

SL-TxProfile-r18 ::= ENUMERATED {backwardsCompatible,
backwardsIncompatible}

SL-RLC-ModeIndication-r16 ::= SEQUENCE {

sl-Mode-r16 CHOICE {

sl-AM-Mode-r16 NULL,

sl-UM-Mode-r16 NULL

},

sl-QoS-InfoList-r16 SEQUENCE (SIZE (1..maxNrofSL-QFIsPerDest-r16)) OF
SL-QoS-Info-r16

}

SL-FailureList-r16 ::= SEQUENCE (SIZE (1..maxNrofSL-Dest-r16)) OF
SL-Failure-r16

SL-Failure-r16 ::= SEQUENCE {

sl-DestinationIdentity-r16 SL-DestinationIdentity-r16,

sl-Failure-r16 ENUMERATED {rlf,configFailure, drxReject-v1710, spare5,
spare4, spare3, spare2, spare1}

}

SL-CarrierFailureList-r18 ::= SEQUENCE (SIZE (1..maxNrofSL-Dest-r16)) OF
SL-CarrierFailure-r18

SL-CarrierFailure-r18 ::= SEQUENCE {

sl-DestinationIdentity-r18 SL-DestinationIdentity-r16,

sl-CarrierFailure-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF INTEGER
(1..maxNrofFreqSL-r16)

}

SL-SplitQoS-Info-r18 ::= SEQUENCE {

sl-QoS-FlowIdentity-r18 SL-QoS-FlowIdentity-r16,

sl-SplitPacketDelayBudget-r18 INTEGER (0..1023) OPTIONAL,

\...

}

SL-PerSLRB-QoS-Info-r18 ::= SEQUENCE {

sl-RemoteUE-SLRB-Identity-r18 SLRB-Uu-ConfigIndex-r16,

sl-QoS-ProfilePerSLRB-r18 SL-QoS-Profile-r16 OPTIONAL

}

SL-PRS-QoS-Info-r18 ::= SEQUENCE {

sl-PRS-Priority-r18 INTEGER (1..8) OPTIONAL,

sl-PRS-DelayBudget-r18 INTEGER (0..1023) OPTIONAL,

sl-PRS-Bandwidth-r18 ENUMERATED {mhz5, mhz10, mhz15, mhz20, mhz25,
mhz30, mhz35, mhz40,

mhz45, mhz50, mhz60, mhz70, mhz80, mhz90, mhz100, mhz200, mhz400,

spare15, spare14, spare13, spare12, spare11, spare10, spare9, spare8,

spare7, spare6, spare5, spare4, spare3, spare2, spare1} OPTIONAL,

\...

}

SL-RLC-Mode-r18 ::= CHOICE {

sl-AM-Mode-r18 NULL,

sl-UM-Mode-r18 NULL

}

\-- TAG-SIDELINKUEINFORMATIONNR-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SidelinkUEinformationNR* field descriptions                          |
+-----------------------------------------------------------------------+
| ***sl-PosRxInterestedFreqList***                                      |
|                                                                       |
| Indicates the index of frequency where dedicated SL-PRS resource      |
| pool(s) locates on which the UE is interested to perform SL-PRS       |
| measurement. The value 1 corresponds to the frequency of first entry  |
| in *sl-PosFreqInfoList* broadcast in *SIB23*, the value 2 corresponds |
| to the frequency of second entry in *sl-PosFreqInfoList* broadcast in |
| *SIB23* and so on. In this release, only value 1 can be included in   |
| the interested frequency list.                                        |
+-----------------------------------------------------------------------+
| ***sl-PosRxInterestedFreqList2***                                     |
|                                                                       |
| Indicates the index of frequency where shared SL-PRS resource pool(s) |
| locates on which the UE is interested to perform SL-PRS measurement.  |
| The value 1 corresponds to the frequency of first entry in            |
| *sl-FreqInfoList* broadcast in *SIB12*, the value 2 corresponds to    |
| the frequency of first entry in *sl-FreqInfoListSizeExt* broadcast in |
| *SIB12,* the value 3 corresponds to the frequency of second entry in  |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12* and so on. The list of  |
| interested frequencies indicated by this field should be a subset of  |
| the frequencies indicated by the field *sl-RxInterestedFreqList*.     |
+-----------------------------------------------------------------------+
| ***sl-PosTxResourceReqList***                                         |
|                                                                       |
| List of parameters to request the transmission resources for NR       |
| sidelink positioning for the associated destination.                  |
+=======================================================================+
| ***sl-RxDRX-ReportList***                                             |
|                                                                       |
| Indicates the accepted DRX configuration that is received from the    |
| peer UE and reported to the network for NR sidelink unicast           |
| communication.                                                        |
+-----------------------------------------------------------------------+
| ***sl-RxInterestedFreqList***                                         |
|                                                                       |
| Indicates the index of frequency on which the UE is interested to     |
| receive NR sidelink communication. The value 1 corresponds to the     |
| frequency of first entry in *sl-FreqInfoList* broadcast in *SIB12*,   |
| the value 2 corresponds to the frequency of first entry in            |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12*, the value 3            |
| corresponds to the frequency of second entry in                       |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12* and so on.              |
+-----------------------------------------------------------------------+
| ***sl-RxInterestedGC-BC-DestList***                                   |
|                                                                       |
| Indicates the reported QoS profile and associated destination for     |
| which UE is interested in reception to the network for NR sidelink    |
| groupcast and broadcast communication, or for NR sidelink discovery   |
| or ProSe Direct Link Establishment Request as described in TS 24.554  |
| \[72\], or for Direct Link Establishment Request (TS 24.587 \[57\]).  |
+-----------------------------------------------------------------------+
| ***sl-SourceIdentityRemoteUE***                                       |
|                                                                       |
| This field is used to indicate the Source Layer-2 ID to be used to    |
| establish PC5 link with the target L2 U2N Relay UE for path switch.   |
+-----------------------------------------------------------------------+
| ***sl-TxResourceReq***                                                |
|                                                                       |
| Parameters to request the transmission resources for NR sidelink      |
| communication to the network in the Sidelink UE Information report.   |
+-----------------------------------------------------------------------+
| ***sl-TxResourceReqList***                                            |
|                                                                       |
| List of parameters to request the transmission resources for NR       |
| sidelink communication for the associated destination. If             |
| *sl-TxResourceReqList-v1700* is present, it shall contain the same    |
| number of entries, listed in the same order as in                     |
| *sl-TxResourceReqList-r16*.                                           |
+-----------------------------------------------------------------------+
| ***ue-Type***                                                         |
|                                                                       |
| Indicates the UE is acting as U2N Relay UE or U2N Remote UE.          |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SL-TxResourceReq* field descriptions                                 |
+-----------------------------------------------------------------------+
| ***sl-CapabilityInformationSidelink***                                |
|                                                                       |
| Includes the *UECapabilityInformationSidelink* message (which can be  |
| also included in *ueCapabilityInformationSidelink-r16* in             |
| *UECapabilityEnquirySidelink* from peer UE) received from the peer    |
| UE.                                                                   |
+=======================================================================+
| ***sl-CastType***                                                     |
|                                                                       |
| Indicates the cast type for the corresponding destination for which   |
| to request the resource.                                              |
+-----------------------------------------------------------------------+
| ***sl-DestinationIdentity***                                          |
|                                                                       |
| Indicates the destination for which the TX resource request and       |
| allocation from the network are concerned.                            |
+-----------------------------------------------------------------------+
| ***sl-DRX-Indication***                                               |
|                                                                       |
| Indicates the sidelink DRX is applied (value *on*) or not applied     |
| (value *off*) for the associated destination. This field is only      |
| valid for NR sidelink groupcast communication.                        |
+-----------------------------------------------------------------------+
| ***sl-DRX-InfoFromRxList***                                           |
|                                                                       |
| Indicates list of the sidelink DRX configurations as assistance       |
| information received from the peer UE for NR sidelink unicast         |
| communication.                                                        |
+-----------------------------------------------------------------------+
| ***sl-QoS-InfoList***                                                 |
|                                                                       |
| Includes the QoS profile of the sidelink QoS flow as specified in TS  |
| 23.287 \[55\]. If *sl-QoS-InfoList-v1800* is included, shall include  |
| the same number of entries, and listed in the same order, as in       |
| *sl-QoS-InfoList-r16*.                                                |
+-----------------------------------------------------------------------+
| ***sl-QoS-FlowIdentity***                                             |
|                                                                       |
| This identity uniquely identifies one sidelink QoS flow between the   |
| UE and the network in the scope of UE, which is unique for different  |
| destination and cast type.                                            |
+-----------------------------------------------------------------------+
| ***sl-RLC-ModeIndicationList***                                       |
|                                                                       |
| Each entry of this field indicates the RLC mode and optionally the    |
| related QoS profiles for the sidelink radio bearer, which has not     |
| been configured by the network and is initiated by another UE in      |
| unicast. The RLC mode for one sidelink radio bearer is aligned        |
| between UE and NW by the *sl-QoS-FlowIdentity*.                       |
+-----------------------------------------------------------------------+
| ***sl-TxInterestedFreqList***                                         |
|                                                                       |
| Each entry of this field indicates the index of frequency on which    |
| the UE is interested to transmit NR sidelink communication, for each  |
| destination. The value 1 corresponds to the frequency of first entry  |
| in *sl-FreqInfoList* broadcast in *SIB12*, the value 2 corresponds to |
| the frequency of first entry in *sl-FreqInfoListSizeExt broadcast* in |
| *SIB12*, the value 3 corresponds to the frequency of second entry in  |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12* and so on.              |
+-----------------------------------------------------------------------+
| ***sl-TypeTxSyncList***                                               |
|                                                                       |
| A list of synchronization reference used by the UE. The UE shall      |
| include the same number of entries, listed in the same order, as in   |
| *sl-TxInterestedFreqList*, i.e. one for each carrier frequency        |
| included in *sl-TxInterestedFreqList*.                                |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SL-Failure* field descriptions                                       |
+=======================================================================+
| ***sl-DestinationIdentity***                                          |
|                                                                       |
| Indicates the destination for which the SL failure is reporting for   |
| unicast.                                                              |
+-----------------------------------------------------------------------+
| ***sl-Failure***                                                      |
|                                                                       |
| Indicates the sidelink cause for the sidelink RLF (value *rlf*),      |
| sidelink AS configuration failure (value *configFailure*) and the     |
| rejection of sidelink DRX configuration (value *drxReject-v1710*) for |
| the associated destination for unicast.                               |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SL-RxDRX-Report* field descriptions                                  |
+=======================================================================+
| ***sl-DRX-ConfigFromTx***                                             |
|                                                                       |
| Indicates the sidelink DRX configuration received from the peer UE    |
| for NR sidelink unicast communication.                                |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SL-RxInterestedGC-BC-Dest* field descriptions                        |
+=======================================================================+
| ***sl-RxInterestedQoS-InfoList***                                     |
|                                                                       |
| Indicates the QoS profile for which UE reports its interested service |
| to which SL DRX is applied to the network, for NR sidelink groupcast  |
| or broadcast reception.                                               |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SL-TxResourceReqDisc* field descriptions                             |
+-----------------------------------------------------------------------+
| ***sl-CastTypeDisc***                                                 |
|                                                                       |
| Indicates the cast type for the NR sidelink discovery messages. Only  |
| value *broadcast* can be set in this release.                         |
+-----------------------------------------------------------------------+
| ***sl-DestinationIdentityDisc***                                      |
|                                                                       |
| This field is used to indicate the destination L2 ID for which the TX |
| resource request and allocation from the network are concerned for    |
| relay discovery and non-relay discovery.                              |
+-----------------------------------------------------------------------+
| ***sl-SourceIdentityRelayUE***                                        |
|                                                                       |
| This field is used to indicate the source L2 ID of relay-related      |
| discovery transmission by L2 U2N Relay UE.                            |
+-----------------------------------------------------------------------+
| ***sl-TxInterestedFreqListDisc***                                     |
|                                                                       |
| Each entry of this field indicates the index of frequency on which    |
| the UE is interested to transmit NR sidelink discovery. The value 1   |
| corresponds to the frequency of first entry in *sl-FreqInfoList*      |
| broadcast in *SIB12*, the value 2 corresponds to the frequency of     |
| second entry in *sl-FreqInfoList broadcast* in *SIB12* and so on. In  |
| this release, only value 1 can be included in the interested          |
| frequency list. In this release, only one entry can be included in    |
| the list.                                                             |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-PosTxResourceReq* field descriptions                              |
+-----------------------------------------------------------------------+
| ***sl-CapabilityInformationSidelink***                                |
|                                                                       |
| Includes the *UECapabilityInformationSidelink* message (which can be  |
| also included in *ueCapabilityInformationSidelink-r16* in             |
| *UECapabilityEnquirySidelink* from peer UE) received from the peer    |
| UE.                                                                   |
+-----------------------------------------------------------------------+
| ***sl-PosCastType***                                                  |
|                                                                       |
| Indicates the cast type for the SL-PRS transmission.                  |
+-----------------------------------------------------------------------+
| ***sl-PosDestinationIdentity***                                       |
|                                                                       |
| This field is used to indicate the destination L2 ID for which the TX |
| resource request and allocation from the network are concerned for    |
| SL-PRS transmission                                                   |
+-----------------------------------------------------------------------+
| ***sl-PosQoS-InfoList***                                              |
|                                                                       |
| This field is used to indicate the QoS information for SL-PRS         |
| transmission.                                                         |
+-----------------------------------------------------------------------+
| ***sl-PosTxInterestedFreqList***                                      |
|                                                                       |
| Each entry of this field indicates the index of frequency in *SIB23*  |
| on which the UE is interested to transmit SL-PRS. The value 1         |
| corresponds to the frequency of first entry in *sl-PosFreqInfoList*   |
| broadcast in *SIB23*, the value 2 corresponds to the frequency of     |
| second entry in *sl-PosFreqInfoList* broadcast in *SIB23* and so on.  |
| In this release, only value 1 can be included in the interested       |
| frequency list. In this release, only one entry can be included in    |
| the list.                                                             |
+-----------------------------------------------------------------------+
| ***sl-PosTxInterestedFreqList2***                                     |
|                                                                       |
| Each entry of this field indicates the index of frequency in *SIB12*  |
| on which the UE is interested to transmit SL-PRS. The value 1         |
| corresponds to the frequency of first entry in *sl-PosFreqInfoList*   |
| broadcast in *SIB12*, the value 2 corresponds to the frequency of     |
| first entry in *sl-FreqInfoListSizeExt broadcast* in *SIB12*, the     |
| value 3 corresponds to the frequency of second entry in               |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12* and so on. The list of  |
| interested frequencies indicated by this field should be a subset of  |
| the frequencies indicated by the field *sl-TxInterestedFreqList*.     |
+-----------------------------------------------------------------------+
| ***sl-PosTypeTxSyncList***                                            |
|                                                                       |
| A list of synchronization references used by the UE. The UE shall     |
| include the same number of entries, listed in the same order, as in   |
| *sl-PosTxInterestedFreqList*, i.e. one for each carrier frequency     |
| included in *sl-PosTxInterestedFreqList*.                             |
+-----------------------------------------------------------------------+
| ***sl-PRS-DelayBudget***                                              |
|                                                                       |
| Indicates the SL-PRS delay budget provided by upper layers (see TS    |
| 38.355 \[77\]).                                                       |
+-----------------------------------------------------------------------+
| ***sl-PRS-Priority***                                                 |
|                                                                       |
| Indicates the priority of SL-PRS provided by upper layers (see TS     |
| 38.355 \[77\]). Value 1 is the highest priority whereas value 8 is    |
| the lowest priority.                                                  |
+-----------------------------------------------------------------------+
| ***sl-PRS-Bandwidth***                                                |
|                                                                       |
| Indicates the desired bandwidth of the requested SL-PRS resources     |
| provided by upper layers (see TS 38.355 \[77\]) in the unit of MHz.   |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-TxResourceReqCommRelayInfo* field descriptions                    |
+-----------------------------------------------------------------------+
| ***sl-RelayDRXConfig***                                               |
|                                                                       |
| This field is used to indicate the applied sidelink DRX configuration |
| for the relay related communication.                                  |
+-----------------------------------------------------------------------+
| ***sl-DestinationIdentityL2U2N***                                     |
|                                                                       |
| This field is used to indicate the destination L2 ID for which the TX |
| resource request and allocation from the network are concerned for    |
| the established PC5 link for relay by L2 U2N Relay UE.                |
+-----------------------------------------------------------------------+
| ***sl-LocalID-Request***                                              |
|                                                                       |
| This field is used to request local UE ID for the corresponding       |
| destination by the L2 U2N Relay UE.                                   |
+-----------------------------------------------------------------------+
| ***sl-TxInterestedFreqListL2U2N***                                    |
|                                                                       |
| Each entry of this field indicates the index of frequency on which    |
| the UE is interested to transmit NR sidelink communication for        |
| established PC5 link for relay. The value 1 corresponds to the        |
| frequency of first entry in *sl-FreqInfoList* broadcast in SIB12, the |
| value 2 corresponds to the frequency of second entry in               |
| *sl-FreqInfoList* broadcast in *SIB12* and so on. In this release,    |
| only value 1 can be included in the interested frequency list. In     |
| this release, only one entry can be included in the list.             |
+-----------------------------------------------------------------------+
| ***sl-PagingIdentityRemoteUE***                                       |
|                                                                       |
| This field is used to indicate the paging UE ID(s) for the            |
| corresponding destination(s) by the L2 U2N Relay UE.                  |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-QoS-Info* field descriptions                                      |
+-----------------------------------------------------------------------+
| ***sl-TxInterestedFreqList***                                         |
|                                                                       |
| Each entry of this field indicates the index of frequency on which    |
| the UE is interested to transmit NR sidelink communication, for each  |
| QoS flow. The value 1 corresponds to the frequency of first entry in  |
| *sl-FreqInfoList* broadcast in *SIB12*, the value 2 corresponds to    |
| the frequency of first entry in *sl-FreqInfoListSizeExt* broadcast in |
| *SIB12*, the value 3 corresponds to the frequency of second entry in  |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12* and so on.              |
+-----------------------------------------------------------------------+
| ***sl-TxProfile***                                                    |
|                                                                       |
| Indicating Tx profile for each QoS flow, i.e., compatibility of       |
| supporting SL CA operation. The IE of *SL-TxProfile* is referred by   |
| upper layer signaling as specified TS 24.588 \[78\].                  |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-CarrierFailure* field descriptions                                |
+-----------------------------------------------------------------------+
| ***sl-CarrierFailure***                                               |
|                                                                       |
| Indicate the carrier(s) where the Sidelink carrier failure has been   |
| indicated by lower layer as specified in TS 38.321 \[3\]. The value 1 |
| corresponds to the frequency of first entry in *sl-FreqInfoList*      |
| broadcast in *SIB12*, the value 2 corresponds to the frequency of     |
| first entry in *sl-FreqInfoListSizeExt* broadcast in *SIB12*, the     |
| value 3 corresponds to the frequency of second entry in               |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12* and so on.              |
+-----------------------------------------------------------------------+
| ***sl-DestinationIdentity***                                          |
|                                                                       |
| This field is used to indicate the destination L2 ID for which the    |
| per-carrier failure report is concerned.                              |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-TxResourceReqL2-U2U* field descriptions                           |
+-----------------------------------------------------------------------+
| ***sl-CapabilityInformationSidelink***                                |
|                                                                       |
| Includes the *UECapabilityInformationSidelink* message (which can be  |
| also included in *ueCapabilityInformationSidelink-r16* in             |
| *UECapabilityEnquirySidelink* from the L2 U2U Relay UE) received from |
| the L2 U2U Relay UE.                                                  |
+-----------------------------------------------------------------------+
| ***sl-DestinationIdentityL2-U2U***                                    |
|                                                                       |
| This field is used to indicate the destination L2 ID for which the TX |
| resource request and allocation from the network are concerned for    |
| the established per-hop PC5 link between the L2 U2U Remote UE and L2  |
| U2U Relay UE.                                                         |
+-----------------------------------------------------------------------+
| ***sl-TxInterestedFreqListL2-U2U***                                   |
|                                                                       |
| Each entry of this field indicates the index of frequency on which    |
| the UE is interested to transmit NR sidelink communication for        |
| established per-hop PC5 link. The value 1 corresponds to the          |
| frequency of first entry in sl-FreqInfoList broadcast in SIB12, the   |
| value 2 corresponds to the frequency of second entry in               |
| sl-FreqInfoList broadcast in SIB12 and so on. In this release, only   |
| value 1 can be included in the interested frequency list. In this     |
| release, only one entry can be included in the list.                  |
+-----------------------------------------------------------------------+
| ***sl-U2U-InfoList***                                                 |
|                                                                       |
| This field indicates the information related to a list of end-to-end  |
| PC5 links.                                                            |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-U2U-Info* field descriptions                                      |
+-----------------------------------------------------------------------+
| ***sl-CapabilityInformationTargetRemoteUE***                          |
|                                                                       |
| Includes the *UECapabilityInformationSidelink* message (which can be  |
| also included in *ueCapabilityInformationSidelink-r16* in             |
| *UECapabilityEnquirySidelink* from the target L2 U2U Remote UE)       |
| received from the target L2 U2U Remote UE. In this version of the     |
| specification, only *outOfOrderDeliverySidelink-r16* and              |
| *accessStratumReleaseSidelink-r16* are included in the                |
| *UECapabilityInformationSidelink* message.                            |
+-----------------------------------------------------------------------+
| ***sl-E2E-QoS-InfoList***                                             |
|                                                                       |
| This field is used by L2 U2U Remote UE to indicate a list of          |
| end-to-end QoS info.                                                  |
+-----------------------------------------------------------------------+
| ***sl-PerHop-QoS-InfoList***                                          |
|                                                                       |
| This field is used by L2 U2U Remote UE to indicate a list of split    |
| QoS info for the first hop.                                           |
+-----------------------------------------------------------------------+
| ***sl-PerSLRB-QoS-InfoList***                                         |
|                                                                       |
| This field is used by L2 U2U Relay UE to indicate a list of split QoS |
| info for the second hop in per-SLRB level, with each entry in         |
| accordance with an end-to-end SLRB.                                   |
+-----------------------------------------------------------------------+
| ***sl-U2U-Identity***                                                 |
|                                                                       |
| This field is to identify an end-to-end PC5 link. For a L2 U2U Remote |
| UE acting as source UE it includes *sl-TargetUE-Identity* to indicate |
| the target L2 U2U Remote UE on the second hop, and for a L2 U2U Relay |
| UE, it includes *sl-SourceUE-Identity* to indicate the source L2 U2U  |
| Remote UE on the first hop.                                           |
+=======================================================================+

#### -- *SystemInformation*

The *SystemInformation* message is used to convey one or more System
Information Blocks or Positioning System Information Blocks. All the
SIBs or posSIBs included are transmitted with the same periodicity.

Signalling radio bearer: N/A

RLC-SAP: TM

Logical channels: BCCH

Direction: Network to UE

*SystemInformation message*

\-- ASN1START

\-- TAG-SYSTEMINFORMATION-START

SystemInformation ::= SEQUENCE {

criticalExtensions CHOICE {

systemInformation SystemInformation-IEs,

criticalExtensionsFuture-r16 CHOICE {

posSystemInformation-r16 PosSystemInformation-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

}

SystemInformation-IEs ::= SEQUENCE {

sib-TypeAndInfo SEQUENCE (SIZE (1..maxSIB)) OF CHOICE {

sib2 SIB2,

sib3 SIB3,

sib4 SIB4,

sib5 SIB5,

sib6 SIB6,

sib7 SIB7,

sib8 SIB8,

sib9 SIB9,

\...,

sib10-v1610 SIB10-r16,

sib11-v1610 SIB11-r16,

sib12-v1610 SIB12-r16,

sib13-v1610 SIB13-r16,

sib14-v1610 SIB14-r16,

sib15-v1700 SIB15-r17,

sib16-v1700 SIB16-r17,

sib17-v1700 SIB17-r17,

sib18-v1700 SIB18-r17,

sib19-v1700 SIB19-r17,

sib20-v1700 SIB20-r17,

sib21-v1700 SIB21-r17,

sib22-v1800 SIB22-r18,

sib23-v1800 SIB23-r18,

sib24-v1800 SIB24-r18,

sib25-v1800 SIB25-r18,

sib17bis-v1820 SIB17bis-r18

},

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-SYSTEMINFORMATION-STOP

\-- ASN1STOP

#### -- *UEAssistanceInformation*

The *UEAssistanceInformation* message is used for the indication of UE
assistance information to the network.

Signalling radio bearer: SRB1, SRB3

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*UEAssistanceInformation message*

\-- ASN1START

\-- TAG-UEASSISTANCEINFORMATION-START

UEAssistanceInformation ::= SEQUENCE {

criticalExtensions CHOICE {

ueAssistanceInformation UEAssistanceInformation-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

UEAssistanceInformation-IEs ::= SEQUENCE {

delayBudgetReport DelayBudgetReport OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension UEAssistanceInformation-v1540-IEs OPTIONAL

}

DelayBudgetReport::= CHOICE {

type1 ENUMERATED {

msMinus1280, msMinus640, msMinus320, msMinus160,msMinus80, msMinus60,
msMinus40,

msMinus20, ms0, ms20,ms40, ms60, ms80, ms160, ms320, ms640, ms1280},

\...

}

UEAssistanceInformation-v1540-IEs ::= SEQUENCE {

overheatingAssistance OverheatingAssistance OPTIONAL,

nonCriticalExtension UEAssistanceInformation-v1610-IEs OPTIONAL

}

OverheatingAssistance ::= SEQUENCE {

reducedMaxCCs ReducedMaxCCs-r16 OPTIONAL,

reducedMaxBW-FR1 ReducedMaxBW-FRx-r16 OPTIONAL,

reducedMaxBW-FR2 ReducedMaxBW-FRx-r16 OPTIONAL,

reducedMaxMIMO-LayersFR1 SEQUENCE {

reducedMIMO-LayersFR1-DL MIMO-LayersDL,

reducedMIMO-LayersFR1-UL MIMO-LayersUL

} OPTIONAL,

reducedMaxMIMO-LayersFR2 SEQUENCE {

reducedMIMO-LayersFR2-DL MIMO-LayersDL,

reducedMIMO-LayersFR2-UL MIMO-LayersUL

} OPTIONAL

}

OverheatingAssistance-r17 ::= SEQUENCE {

reducedMaxBW-FR2-2-r17 SEQUENCE {

reducedBW-FR2-2-DL-r17 ReducedAggregatedBandwidth-r17,

reducedBW-FR2-2-UL-r17 ReducedAggregatedBandwidth-r17

} OPTIONAL,

reducedMaxMIMO-LayersFR2-2 SEQUENCE {

reducedMIMO-LayersFR2-2-DL MIMO-LayersDL,

reducedMIMO-LayersFR2-2-UL MIMO-LayersUL

} OPTIONAL

}

ReducedAggregatedBandwidth ::= ENUMERATED {mhz0, mhz10, mhz20, mhz30,
mhz40, mhz50, mhz60, mhz80, mhz100, mhz200, mhz300, mhz400}

ReducedAggregatedBandwidth-r17 ::= ENUMERATED {mhz0, mhz100, mhz200,
mhz400, mhz800, mhz1200, mhz1600, mhz2000}

UEAssistanceInformation-v1610-IEs ::= SEQUENCE {

idc-Assistance-r16 IDC-Assistance-r16 OPTIONAL,

drx-Preference-r16 DRX-Preference-r16 OPTIONAL,

maxBW-Preference-r16 MaxBW-Preference-r16 OPTIONAL,

maxCC-Preference-r16 MaxCC-Preference-r16 OPTIONAL,

maxMIMO-LayerPreference-r16 MaxMIMO-LayerPreference-r16 OPTIONAL,

minSchedulingOffsetPreference-r16 MinSchedulingOffsetPreference-r16
OPTIONAL,

releasePreference-r16 ReleasePreference-r16 OPTIONAL,

sl-UE-AssistanceInformationNR-r16 SL-UE-AssistanceInformationNR-r16
OPTIONAL,

referenceTimeInfoPreference-r16 BOOLEAN OPTIONAL,

nonCriticalExtension UEAssistanceInformation-v1700-IEs OPTIONAL

}

UEAssistanceInformation-v1700-IEs ::= SEQUENCE {

ul-GapFR2-Preference-r17 UL-GapFR2-Preference-r17 OPTIONAL,

musim-Assistance-r17 MUSIM-Assistance-r17 OPTIONAL,

overheatingAssistance-r17 OverheatingAssistance-r17 OPTIONAL,

maxBW-PreferenceFR2-2-r17 MaxBW-PreferenceFR2-2-r17 OPTIONAL,

maxMIMO-LayerPreferenceFR2-2-r17 MaxMIMO-LayerPreferenceFR2-2-r17
OPTIONAL,

minSchedulingOffsetPreferenceExt-r17
MinSchedulingOffsetPreferenceExt-r17 OPTIONAL,

rlm-MeasRelaxationState-r17 BOOLEAN OPTIONAL,

bfd-MeasRelaxationState-r17 BIT STRING (SIZE (1..maxNrofServingCells))
OPTIONAL,

nonSDT-DataIndication-r17 SEQUENCE {

resumeCause-r17 ResumeCause OPTIONAL

} OPTIONAL,

scg-DeactivationPreference-r17 ENUMERATED { scg-DeactivationPreferred,
noPreference } OPTIONAL,

uplinkData-r17 ENUMERATED { true } OPTIONAL,

rrm-MeasRelaxationFulfilment-r17 BOOLEAN OPTIONAL,

propagationDelayDifference-r17 PropagationDelayDifference-r17 OPTIONAL,

nonCriticalExtension UEAssistanceInformation-v1800-IEs OPTIONAL

}

UEAssistanceInformation-v1800-IEs ::= SEQUENCE {

idc-FDM-Assistance-r18 IDC-FDM-Assistance-r18 OPTIONAL,

idc-TDM-Assistance-r18 IDC-TDM-Assistance-r18 OPTIONAL,

multiRx-PreferenceFR2-r18 ENUMERATED {single, multiple } OPTIONAL,

musim-Assistance-v1800 MUSIM-Assistance-v1800 OPTIONAL,

flightPathInfoAvailable-r18 ENUMERATED {true} OPTIONAL,

ul-TrafficInfo-r18 UL-TrafficInfo-r18 OPTIONAL,

n3c-RelayUE-InfoList-r18 SEQUENCE (SIZE (0..8)) OF N3C-RelayUE-Info-r18
OPTIONAL,

sl-PRS-UE-AssistanceInformationNR-r18
SL-PRS-UE-AssistanceInformationNR-r18 OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

IDC-Assistance-r16 ::= SEQUENCE {

affectedCarrierFreqList-r16 AffectedCarrierFreqList-r16 OPTIONAL,

affectedCarrierFreqCombList-r16 AffectedCarrierFreqCombList-r16
OPTIONAL,

\...

}

AffectedCarrierFreqList-r16 ::= SEQUENCE (SIZE (1.. maxFreqIDC-r16)) OF
AffectedCarrierFreq-r16

AffectedCarrierFreq-r16 ::= SEQUENCE {

carrierFreq-r16 ARFCN-ValueNR,

interferenceDirection-r16 ENUMERATED {nr, other, both, spare}

}

AffectedCarrierFreqCombList-r16 ::= SEQUENCE (SIZE (1..maxCombIDC-r16))
OF AffectedCarrierFreqComb-r16

AffectedCarrierFreqComb-r16 ::= SEQUENCE {

affectedCarrierFreqComb-r16 SEQUENCE (SIZE (2..maxNrofServingCells)) OF
ARFCN-ValueNR OPTIONAL,

victimSystemType-r16 VictimSystemType-r16

}

VictimSystemType-r16 ::= SEQUENCE {

gps-r16 ENUMERATED {true} OPTIONAL,

glonass-r16 ENUMERATED {true} OPTIONAL,

bds-r16 ENUMERATED {true} OPTIONAL,

galileo-r16 ENUMERATED {true} OPTIONAL,

navIC-r16 ENUMERATED {true} OPTIONAL,

wlan-r16 ENUMERATED {true} OPTIONAL,

bluetooth-r16 ENUMERATED {true} OPTIONAL,

\...,

\[\[

uwb-r18 ENUMERATED {true} OPTIONAL

\]\]

}

DRX-Preference-r16 ::= SEQUENCE {

preferredDRX-InactivityTimer-r16 ENUMERATED {

ms0, ms1, ms2, ms3, ms4, ms5, ms6, ms8, ms10, ms20, ms30, ms40, ms50,
ms60, ms80,

ms100, ms200, ms300, ms500, ms750, ms1280, ms1920, ms2560, spare9,
spare8,

spare7, spare6, spare5, spare4, spare3, spare2, spare1} OPTIONAL,

preferredDRX-LongCycle-r16 ENUMERATED {

ms10, ms20, ms32, ms40, ms60, ms64, ms70, ms80, ms128, ms160, ms256,
ms320, ms512,

ms640, ms1024, ms1280, ms2048, ms2560, ms5120, ms10240, spare12,
spare11, spare10,

spare9, spare8, spare7, spare6, spare5, spare4, spare3, spare2, spare1 }
OPTIONAL,

preferredDRX-ShortCycle-r16 ENUMERATED {

ms2, ms3, ms4, ms5, ms6, ms7, ms8, ms10, ms14, ms16, ms20, ms30, ms32,

ms35, ms40, ms64, ms80, ms128, ms160, ms256, ms320, ms512, ms640,
spare9,

spare8, spare7, spare6, spare5, spare4, spare3, spare2, spare1 }
OPTIONAL,

preferredDRX-ShortCycleTimer-r16 INTEGER (1..16) OPTIONAL

}

MaxBW-Preference-r16 ::= SEQUENCE {

reducedMaxBW-FR1-r16 ReducedMaxBW-FRx-r16 OPTIONAL,

reducedMaxBW-FR2-r16 ReducedMaxBW-FRx-r16 OPTIONAL

}

MaxBW-PreferenceFR2-2-r17 ::= SEQUENCE {

reducedMaxBW-FR2-2-r17 SEQUENCE {

reducedBW-FR2-2-DL-r17 ReducedAggregatedBandwidth-r17 OPTIONAL,

reducedBW-FR2-2-UL-r17 ReducedAggregatedBandwidth-r17 OPTIONAL

} OPTIONAL

}

MaxCC-Preference-r16 ::= SEQUENCE {

reducedMaxCCs-r16 ReducedMaxCCs-r16 OPTIONAL

}

MaxMIMO-LayerPreference-r16 ::= SEQUENCE {

reducedMaxMIMO-LayersFR1-r16 SEQUENCE {

reducedMIMO-LayersFR1-DL-r16 INTEGER (1..8),

reducedMIMO-LayersFR1-UL-r16 INTEGER (1..4)

} OPTIONAL,

reducedMaxMIMO-LayersFR2-r16 SEQUENCE {

reducedMIMO-LayersFR2-DL-r16 INTEGER (1..8),

reducedMIMO-LayersFR2-UL-r16 INTEGER (1..4)

} OPTIONAL

}

MaxMIMO-LayerPreferenceFR2-2-r17 ::= SEQUENCE {

reducedMaxMIMO-LayersFR2-2-r17 SEQUENCE {

reducedMIMO-LayersFR2-2-DL-r17 INTEGER (1..8),

reducedMIMO-LayersFR2-2-UL-r17 INTEGER (1..4)

} OPTIONAL

}

MinSchedulingOffsetPreference-r16 ::= SEQUENCE {

preferredK0-r16 SEQUENCE {

preferredK0-SCS-15kHz-r16 ENUMERATED {sl1, sl2, sl4, sl6} OPTIONAL,

preferredK0-SCS-30kHz-r16 ENUMERATED {sl1, sl2, sl4, sl6} OPTIONAL,

preferredK0-SCS-60kHz-r16 ENUMERATED {sl2, sl4, sl8, sl12} OPTIONAL,

preferredK0-SCS-120kHz-r16 ENUMERATED {sl2, sl4, sl8, sl12} OPTIONAL

} OPTIONAL,

preferredK2-r16 SEQUENCE {

preferredK2-SCS-15kHz-r16 ENUMERATED {sl1, sl2, sl4, sl6} OPTIONAL,

preferredK2-SCS-30kHz-r16 ENUMERATED {sl1, sl2, sl4, sl6} OPTIONAL,

preferredK2-SCS-60kHz-r16 ENUMERATED {sl2, sl4, sl8, sl12} OPTIONAL,

preferredK2-SCS-120kHz-r16 ENUMERATED {sl2, sl4, sl8, sl12} OPTIONAL

} OPTIONAL

}

MinSchedulingOffsetPreferenceExt-r17 ::= SEQUENCE {

preferredK0-r17 SEQUENCE {

preferredK0-SCS-480kHz-r17 ENUMERATED {sl8, sl16, sl32, sl48} OPTIONAL,

preferredK0-SCS-960kHz-r17 ENUMERATED {sl8, sl16, sl32, sl48} OPTIONAL

} OPTIONAL,

preferredK2-r17 SEQUENCE {

preferredK2-SCS-480kHz-r17 ENUMERATED {sl8, sl16, sl32, sl48} OPTIONAL,

preferredK2-SCS-960kHz-r17 ENUMERATED {sl8, sl16, sl32, sl48} OPTIONAL

} OPTIONAL

}

MUSIM-Assistance-r17 ::= SEQUENCE {

musim-PreferredRRC-State-r17 ENUMERATED {idle, inactive, outOfConnected}
OPTIONAL,

musim-GapPreferenceList-r17 MUSIM-GapPreferenceList-r17 OPTIONAL

}

MUSIM-GapPreferenceList-r17 ::= SEQUENCE (SIZE (1..4)) OF
MUSIM-GapInfo-r17

MUSIM-Assistance-v1800 ::= SEQUENCE {

musim-GapPriorityPreferenceList-r18 MUSIM-GapPriorityPreferenceList-r18
OPTIONAL,

musim-GapKeepPreference-r18 ENUMERATED {true} OPTIONAL,

musim-CapRestriction-r18 MUSIM-CapRestriction-r18 OPTIONAL,

musim-NeedForGapsInfoNR-r18 NeedForGapsInfoNR-r16 OPTIONAL,

\...

}

MUSIM-GapPriorityPreferenceList-r18 ::= SEQUENCE (SIZE (1..3)) OF
GapPriority-r17

MUSIM-CapRestriction-r18 ::= SEQUENCE {

musim-Cell-SCG-ToRelease-r18 MUSIM-Cell-SCG-ToRelease-r18 OPTIONAL,

musim-CellToAffectList-r18 MUSIM-CellToAffectList-r18 OPTIONAL,

musim-AffectedBandsList-r18 MUSIM-AffectedBandsList-r18 OPTIONAL,

musim-AvoidedBandsList-r18 MUSIM-AvoidedBandsList-r18 OPTIONAL,

musim-MaxCC-r18 MUSIM-MaxCC-r18 OPTIONAL

}

MUSIM-Cell-SCG-ToRelease-r18 ::= SEQUENCE {

musim-CellToRelease-r18 MUSIM-CellToRelease-r18 OPTIONAL,

scg-ReleasePreference-r18 ENUMERATED {true} OPTIONAL

}

MUSIM-CellToRelease-r18 ::= SEQUENCE (SIZE (1..maxNrofServingCells)) OF
ServCellIndex

MUSIM-CellToAffectList-r18::= SEQUENCE (SIZE (1..maxNrofServingCells))
OF MUSIM-CellToAffect-r18

MUSIM-CellToAffect-r18 ::= SEQUENCE {

musim-ServCellIndex-r18 ServCellIndex,

musim-MIMO-Layers-DL-r18 INTEGER (1..8) OPTIONAL,

musim-MIMO-Layers-UL-r18 INTEGER (1..4) OPTIONAL,

musim-SupportedBandwidth-DL-r18 SupportedBandwidth-v1700 OPTIONAL,

musim-SupportedBandwidth-UL-r18 SupportedBandwidth-v1700 OPTIONAL

}

MUSIM-AffectedBandsList-r18 ::= SEQUENCE (SIZE
(1..maxBandComb-MUSIM-r18)) OF MUSIM-AffectedBands-r18

MUSIM-AffectedBands-r18 ::= SEQUENCE (SIZE
(1..maxCandidateBandIndex-r18)) OF
MUSIM-CapabilityRestrictedBandParameters-r18

MUSIM-CapabilityRestrictedBandParameters-r18 ::= SEQUENCE {

musim-bandEntryIndex-r18 MUSIM-BandEntryIndex-r18,

musim-CapabilityRestricted-r18 SEQUENCE {

musim-MIMO-Layers-DL-r18 INTEGER (1..8) OPTIONAL,

musim-MIMO-Layers-UL-r18 INTEGER (1..4) OPTIONAL,

musim-SupportedBandwidth-DL-r18 SupportedBandwidth-v1700 OPTIONAL,

musim-SupportedBandwidth-UL-r18 SupportedBandwidth-v1700 OPTIONAL

}

}

MUSIM-AvoidedBandsList-r18 ::= SEQUENCE (SIZE
(1..maxBandComb-MUSIM-r18)) OF MUSIM-AvoidedBands-r18

MUSIM-AvoidedBands-r18 ::= SEQUENCE (SIZE
(1..maxCandidateBandIndex-r18)) OF MUSIM-BandEntryIndex-r18

MUSIM-BandEntryIndex-r18 ::= INTEGER(1.. maxCandidateBandIndex-r18)

MUSIM-MaxCC-r18 ::= SEQUENCE {

musim-MaxCC-TotalDL-r18 INTEGER (1..32) OPTIONAL,

musim-MaxCC-TotalUL-r18 INTEGER (1..32) OPTIONAL,

musim-MaxCC-FR1-DL-r18 INTEGER (1..32) OPTIONAL,

musim-MaxCC-FR1-UL-r18 INTEGER (1..32) OPTIONAL,

musim-MaxCC-FR2-1-DL-r18 INTEGER (1..32) OPTIONAL,

musim-MaxCC-FR2-1-UL-r18 INTEGER (1..32) OPTIONAL,

musim-MaxCC-FR2-2-DL-r18 INTEGER (1..32) OPTIONAL,

musim-MaxCC-FR2-2-UL-r18 INTEGER (1..32) OPTIONAL

}

ReleasePreference-r16 ::= SEQUENCE {

preferredRRC-State-r16 ENUMERATED {idle, inactive, connected,
outOfConnected}

}

ReducedMaxBW-FRx-r16 ::= SEQUENCE {

reducedBW-DL-r16 ReducedAggregatedBandwidth,

reducedBW-UL-r16 ReducedAggregatedBandwidth

}

ReducedMaxCCs-r16 ::= SEQUENCE {

reducedCCsDL-r16 INTEGER (0..31),

reducedCCsUL-r16 INTEGER (0..31)

}

SL-UE-AssistanceInformationNR-r16 ::= SEQUENCE (SIZE
(1..maxNrofTrafficPattern-r16)) OF SL-TrafficPatternInfo-r16

SL-TrafficPatternInfo-r16::= SEQUENCE {

trafficPeriodicity-r16 ENUMERATED {ms20, ms50, ms100, ms200, ms300,
ms400, ms500, ms600, ms700, ms800, ms900, ms1000},

timingOffset-r16 INTEGER (0..10239),

messageSize-r16 BIT STRING (SIZE (8)),

sl-QoS-FlowIdentity-r16 SL-QoS-FlowIdentity-r16

}

UL-GapFR2-Preference-r17::= SEQUENCE {

ul-GapFR2-PatternPreference-r17 INTEGER (0..3) OPTIONAL

}

PropagationDelayDifference-r17 ::= SEQUENCE (SIZE (1..4)) OF INTEGER
(-270..270)

IDC-FDM-Assistance-r18 ::= SEQUENCE {

affectedCarrierFreqRangeList-r18 AffectedCarrierFreqRangeList-r18
OPTIONAL,

affectedCarrierFreqRangeCombList-r18
AffectedCarrierFreqRangeCombList-r18 OPTIONAL,

\...

}

IDC-TDM-Assistance-r18 ::= SEQUENCE {

cycleLength-r18 ENUMERATED {ms2, ms3, ms4, ms5, ms6, ms7, ms8, ms10,
ms14, ms16, ms20, ms30,

ms32, ms35, ms40, ms60, ms64, ms70, ms80, ms96, ms100, ms128, ms160,

ms256, ms320, ms512, ms640, ms1024, ms1280, ms2048, ms2560, ms5120,
ms10240},

startOffset-r18 INTEGER (0..10239),

slotOffset-r18 INTEGER (0..31),

activeDuration-r18 CHOICE {

subMilliSeconds-r18 INTEGER (1..31),

milliSeconds-r18 ENUMERATED {

ms1, ms2, ms3, ms4, ms5, ms6, ms8, ms10, ms20, ms30, ms40, ms50, ms60,

ms80, ms100, ms200, ms300, ms400, ms500, ms600, ms800, ms1000, ms1200,

ms1600, spare8, spare7, spare6, spare5, spare4, spare3, spare2, spare1 }

},

\...

}

AffectedCarrierFreqRangeList-r18 ::= SEQUENCE (SIZE (1..maxFreqIDC-r16))
OF AffectedCarrierFreqRange-r18

AffectedCarrierFreqRange-r18 ::= SEQUENCE {

affectedFreqRange-r18 AffectedFreqRange-r18,

interferenceDirection-r18 ENUMERATED {nr, other, both, spare},

victimSystemType-r18 VictimSystemType-r16 OPTIONAL

}

AffectedCarrierFreqRangeCombList-r18 ::= SEQUENCE (SIZE
(1..maxCombIDC-r16)) OF AffectedCarrierFreqRangeComb-r18

AffectedCarrierFreqRangeComb-r18 ::= SEQUENCE {

affectedCarrierFreqRangeComb-r18 SEQUENCE (SIZE
(2..maxNrofServingCells)) OF AffectedFreqRange-r18,

interferenceDirection-r18 ENUMERATED {nr, other, both, spare},

victimSystemType-r18 VictimSystemType-r16 OPTIONAL

}

AffectedFreqRange-r18 ::= SEQUENCE {

centerFreq-r18 ARFCN-ValueNR,

affectedBandwidth-r18 ENUMERATED {khz200, khz400, khz600, khz800, mhz1,
mhz2, mhz3, mhz4, mhz5, mhz6,

mhz8, mhz10, mhz20, mhz30, mhz40, mhz50, mhz60, mhz80, mhz100, mhz200,

mhz300, mhz400, spare10, spare9, spare8, spare7, spare6, spare5, spare4,

spare3, spare2, spare1}

}

UL-TrafficInfo-r18 ::= SEQUENCE (SIZE (1..maxNrofPDU-Sessions-r17)) OF
PDU-SessionUL-TrafficInfo-r18

PDU-SessionUL-TrafficInfo-r18 ::= SEQUENCE {

pdu-SessionID-r18 PDU-SessionID,

qos-FlowUL-TrafficInfoList-r18 SEQUENCE (SIZE (1..maxNrofQFIs)) OF
QOS-FlowUL-TrafficInfo-r18

}

QOS-FlowUL-TrafficInfo-r18 ::= SEQUENCE {

qfi-r18 QFI,

jitterRange-r18 SEQUENCE {

lowerBound-r18 JitterBound-r18,

upperBound-r18 JitterBound-r18

} OPTIONAL,

burstArrivalTime-r18 CHOICE {

referenceTime ReferenceTime-r16,

referenceSFN-AndSlot ReferenceSFN-AndSlot-r18

} OPTIONAL,

trafficPeriodicity-r18 INTEGER (1..640000) OPTIONAL,

pdu-SetIdentification-r18 BOOLEAN OPTIONAL,

psi-Identification-r18 BOOLEAN OPTIONAL,

\...

}

ReferenceSFN-AndSlot-r18 ::= SEQUENCE {

referenceSFN-r18 INTEGER (0..1023),

referenceSlot-r18 INTEGER (0..639)

}

JitterBound-r18 ::= ENUMERATED {ms0, ms0dot5, ms1, ms1dot5, ms2,
ms2dot5, ms3, ms3dot5, ms4, ms4dot5, ms5, ms5dot5, ms6, ms6dot5, ms7,
beyondMs7}

SL-PRS-UE-AssistanceInformationNR-r18 ::= SEQUENCE (SIZE
(1..maxNrofSL-PRS-TxConfig-r18)) OF SL-PRS-TxInfo-r18

SL-PRS-TxInfo-r18 ::= SEQUENCE {

sl-PRS-Periodicity-r18 ENUMERATED {ms100, ms200, ms300, ms400, ms500,
ms600, ms700, ms800, ms900, ms1000, spare6,

spare5, spare4, spare3, spare2, spare1},

sl-PRS-Priority-r18 INTEGER (1..8) OPTIONAL,

sl-PRS-DelayBudget-r18 INTEGER (0..1023) OPTIONAL,

sl-PRS-Bandwidth-r18 ENUMERATED {mhz5, mhz10, mhz15, mhz20, mhz25,
mhz30, mhz35, mhz40,

mhz45, mhz50, mhz60, mhz70, mhz80, mhz90, mhz100, mhz200, mhz400,

spare15, spare14, spare13, spare12, spare11, spare10, spare9, spare8,

spare7, spare6, spare5, spare4, spare3, spare2, spare1} OPTIONAL,

\...

}

\-- TAG-UEASSISTANCEINFORMATION-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UEAssistanceInformation* field descriptions                          |
+=======================================================================+
| ***activeDuration***                                                  |
|                                                                       |
| Indicates the UE\'s preferred active duration to resolve the IDC      |
| problem. Value in multiples of 1/32 ms (subMilliSeconds) or in ms     |
| (milliSecond). For the latter, value ms1 corresponds to 1 ms, value   |
| ms2 corresponds to 2 ms, and so on.                                   |
+-----------------------------------------------------------------------+
| ***affectedBandwidth***                                               |
|                                                                       |
| Indicates the bandwidth around the center frequency of the carrier    |
| frequency range which is affected by the IDC problem. Value mhz5      |
| corresponds to 5 MHz, value mhz10 corresponds to 10 MHz and so on. If |
| *candidateBandwidth* is not configured, the UE is allowed to report   |
| the frequency range for any bandwidth as indicated by                 |
| *affectedBandwidth*, within the frequency band limitation as defined  |
| in TS 38.101-1 \[15\], TS 38.101-2 \[39\], TS 38.101-3 \[34\] and TS  |
| 38.101-5 \[75\].                                                      |
+-----------------------------------------------------------------------+
| ***affectedCarrierFreqList***                                         |
|                                                                       |
| Indicates a list of NR carrier frequencies that are affected by IDC   |
| problem.                                                              |
+-----------------------------------------------------------------------+
| ***affectedCarrierFreqRangeList***                                    |
|                                                                       |
| Indicates a list of NR carrier frequency ranges that are affected by  |
| IDC problem.                                                          |
+-----------------------------------------------------------------------+
| ***affectedCarrierFreqCombList***                                     |
|                                                                       |
| Indicates a list of NR carrier frequency combinations that are        |
| affected by IDC problems due to Inter-Modulation Distortion and       |
| harmonics from NR when configured with UL CA or NR-DC.                |
+-----------------------------------------------------------------------+
| ***affectedCarrierFreqRangeCombList***                                |
|                                                                       |
| Indicates a list of NR carrier frequency range combinations that are  |
| affected by IDC problems due to Inter-Modulation Distortion and       |
| harmonics from NR when configured with UL CA or NR-DC                 |
+-----------------------------------------------------------------------+
| ***bfd-MeasRelaxationState***                                         |
|                                                                       |
| Indicates the relaxation state of BFD measurements. Each bit          |
| corresponds to a serving cell of the cell group. A serving cell is    |
| mapped to the (*servCellIndex*+1)-th bit, starting from MSB. A bit    |
| that is set to 1 indicates that the UE is performing BFD measurements |
| relaxation on the serving cell mapped on the bit. A bit that is set   |
| to 0 indicates that the UE is not performing BFD measurements         |
| relaxation on the serving cell mapped on the bit. If a serving cell   |
| is not configured to the UE, the corresponding bit is set to 0.       |
+-----------------------------------------------------------------------+
| ***centerFreq***                                                      |
|                                                                       |
| Indicates the center frequency of the carrier frequency range which   |
| is affected by the IDC problem.                                       |
+-----------------------------------------------------------------------+
| ***cycleLength***                                                     |
|                                                                       |
| Indicates the UE\'s preferred cycle length to resolve the IDC         |
| problem. Value in ms. Value *ms2* corresponds to 2 ms, value *ms3*    |
| corresponds to 3 ms, and so on.                                       |
+-----------------------------------------------------------------------+
| ***delayBudgetReport***                                               |
|                                                                       |
| Indicates the UE-preferred adjustment to connected mode DRX.          |
+-----------------------------------------------------------------------+
| ***interferenceDirection***                                           |
|                                                                       |
| Indicates the direction of IDC interference. Value *nr* indicates     |
| that only NR is victim of IDC interference, value *other* indicates   |
| that only another radio is victim of IDC interference and value       |
| *both* indicates that both NR and another radio are victims of IDC    |
| interference. The other radio refers to either the ISM radio or GNSS  |
| (see TR 36.816 \[44\]).                                               |
+-----------------------------------------------------------------------+
| ***minSchedulingOffsetPreference***                                   |
|                                                                       |
| Indicates the UE\'s preferences on *minimumSchedulingOffset* of       |
| cross-slot scheduling for power saving.                               |
+-----------------------------------------------------------------------+
| ***minSchedulingOffsetPreferenceExt***                                |
|                                                                       |
| Indicates the UE\'s preferences on *minimumSchedulingOffset* of       |
| cross-slot scheduling for power saving for SCS 480 kHz and/or 960     |
| kHz.                                                                  |
+-----------------------------------------------------------------------+
| ***multiRx-PreferenceFR2***                                           |
|                                                                       |
| Indicates the UE\'s preference on single FR2 Rx operation to address  |
| overheating or power saving. This field is allowed to be reported     |
| only when UE is configured with serving cells operating on FR2.       |
+-----------------------------------------------------------------------+
| ***musim-AffectedBandsList***                                         |
|                                                                       |
| Indicates the UE\'s preference on the band(s) and/or combination(s)   |
| of bands with restricted capability for MUSIM operation. If the       |
| *MUSIM-CapabilityRestrictedBandParameters-r18* with same              |
| *musim-bandEntryIndex* appears more than once in the list of bands in |
| a *MUSIM-AffectedBands* entry, the UE supports intra-band             |
| non-contiguous CA with restricted capability for MUSIM operation for  |
| this band. UE explicitly indicates each band and each combination of  |
| bands that are affected. The Network should respect these capability  |
| restrictions when configuring the UE with bands or band combinations  |
| that contain these bands and/or combination of bands. Fields          |
| *musim-MIMO-Layers-DL/UL* and *musim-SupportedBandwidth-DL/UL*        |
| indicate the max number of MIMO layers and max bandwidth on each CC   |
| of the band, respectively. The band(s) and/or combination(s) of bands |
| are supported in UE capability, and the *musim-MIMO-Layers-DL/UL* and |
| *musim-SupportedBandwidth-DL/UL* range up to the concerned capability |
| of band(s) and/or combination(s) of bands in UE capability.           |
+-----------------------------------------------------------------------+
| ***musim-AvoidedBandsList***                                          |
|                                                                       |
| Indicates the UE\'s preference on band(s) and/or combination(s) of    |
| bands to be avoided for MUSIM purpose. UE explicitly indicates each   |
| band and each combination of bands to be avoided. The list may        |
| include the band of the PCell. The Network should respect these       |
| capability restrictions for the band combinations that contain these  |
| bands and/or combination of bands. The band(s) and/or combination(s)  |
| of bands is a subset of the band combination(s) in UE capability.     |
+-----------------------------------------------------------------------+
| ***musim-bandEntryIndex***                                            |
|                                                                       |
| Indicates an NR band by referring to the position of a band entry in  |
| *musim-CandidateBandList* IE. Value 1 identifies the first band in    |
| the *musim-CandidateBandList* IE, value 2 identifies the second band  |
| in the *musim-CandidateBandList* IE, and so on.                       |
+-----------------------------------------------------------------------+
| ***musim-CapabilityRestricted***                                      |
|                                                                       |
| Indicates the UE\'s preference on the temporary capability            |
| restriction on the band for MUSIM operation.                          |
+-----------------------------------------------------------------------+
| ***musim-CapRestriction***                                            |
|                                                                       |
| Indicates the UE\'s preference on SCell(s) or PSCell to be released,  |
| serving cell(s) with restricted capability, band(s) or combination(s) |
| of bands with restricted capability, or band(s) or band               |
| combination(s) to be avoided for UE temporary capabilities            |
| restriction.                                                          |
+-----------------------------------------------------------------------+
| ***musim-Cell-SCG-ToRelease***                                        |
|                                                                       |
| Indicates the UE\'s preference on any serving cell(s), except for     |
| Pcell, and/or SCG to be released for MUSIM operation.                 |
+-----------------------------------------------------------------------+
| ***musim-CellToAffectList***                                          |
|                                                                       |
| Indicates the UE\'s preference on the temporary capability            |
| restriction on the serving cell(s) for MUSIM operation.               |
+-----------------------------------------------------------------------+
| ***musim-CellToRelease***                                             |
|                                                                       |
| Indicates the UE\'s preference on the temporary capability            |
| restriction on the serving cell(s) to release, except PCell, for      |
| MUSIM operation.                                                      |
+-----------------------------------------------------------------------+
| ***musim-GapKeepPreference***                                         |
|                                                                       |
| Indicates the UE\'s preference to keep all colliding gaps for         |
| requested MUSIM gap(s). If the field is absent, the colliding MUSIM   |
| gaps with lower priority shall be dropped as specified in TS 38.133   |
| \[14\].                                                               |
+-----------------------------------------------------------------------+
| ***musim-GapPreferenceList***                                         |
|                                                                       |
| Indicates the UE\'s MUSIM gap preference and related MUSIM gap        |
| configuration, as defined in TS 38.133 \[14\] clause 9.1.10.          |
+-----------------------------------------------------------------------+
| ***musim-GapPriorityPreferenceList***                                 |
|                                                                       |
| Indicates the UE\'s MUSIM gap priority preference for periodic MUSIM  |
| gaps as specified in TS 38.133\[14\].                                 |
|                                                                       |
| If the UE includes *musim-GapPriorityPreferenceList-r18*, it includes |
| the same number of entries, and listed in the same order for periodic |
| gaps, as in *musim-GapPreferenceList-r17*.                            |
+-----------------------------------------------------------------------+
| ***musim-MaxCC***                                                     |
|                                                                       |
| Indicates the UE\'s preference on the temporary capability            |
| restriction on maximum number of CCs per DL/UL in total, and per      |
| FR1/FR2-1/F2-2.                                                       |
+-----------------------------------------------------------------------+
| ***musim-NeedForGapsInfoNR***                                         |
|                                                                       |
| This field is used to indicate the measurement gap requirement        |
| information of the UE for NR target bands when in MUSIM operation     |
| while NR-DC or NE-DC is not configured.                               |
+-----------------------------------------------------------------------+
| ***musim-PreferredRRC-State***                                        |
|                                                                       |
| Indicates the UE\'s preferred RRC state when leaving RRC_CONNECTED.   |
+-----------------------------------------------------------------------+
| ***n3c-RelayUE-InfoList***                                            |
|                                                                       |
| Information of available N3C relay UE(s).                             |
+-----------------------------------------------------------------------+
| ***nonSDT-DataIndication***                                           |
|                                                                       |
| Informs the network about the arrival of data and/or signaling mapped |
| to radio bearers not configured for SDT while SDT procedure is        |
| ongoing.                                                              |
+-----------------------------------------------------------------------+
| ***preferredDRX-InactivityTimer***                                    |
|                                                                       |
| Indicates the UE\'s preferred DRX inactivity timer length for power   |
| saving. Value in ms (milliSecond). *ms0* corresponds to 0, *ms1*      |
| corresponds to 1 ms, *ms2* corresponds to 2 ms, and so on. If the     |
| field is absent from the *DRX-Preference* IE, it is interpreted as    |
| the UE having no preference for the DRX inactivity timer. If          |
| secondary DRX group is configured, the *preferredDRX-InactivityTimer* |
| only applies to the default DRX group.                                |
+-----------------------------------------------------------------------+
| ***preferredDRX-LongCycle***                                          |
|                                                                       |
| Indicates the UE\'s preferred long DRX cycle length for power saving. |
| Value in ms. *ms10* corresponds to 10ms, *ms20* corresponds to 20 ms, |
| *ms32* corresponds to 32 ms, and so on. If *preferredDRX-ShortCycle*  |
| is provided, the value of *preferredDRX-LongCycle* shall be a         |
| multiple of the *preferredDRX-ShortCycle* value. If the field is      |
| absent from the *DRX-Preference* IE, it is interpreted as the UE      |
| having no preference for the long DRX cycle.                          |
+-----------------------------------------------------------------------+
| ***preferredDRX-ShortCycle***                                         |
|                                                                       |
| Indicates the UE\'s preferred short DRX cycle length for power        |
| saving. Value in ms. *ms2* corresponds to 2ms, *ms3* corresponds to 3 |
| ms, *ms4* corresponds to 4 ms, and so on. If the field is absent from |
| the *DRX-Preference* IE, it is interpreted as the UE having no        |
| preference for the short DRX cycle.                                   |
+-----------------------------------------------------------------------+
| ***preferredDRX-ShortCycleTimer***                                    |
|                                                                       |
| Indicates the UE\'s preferred short DRX cycle timer for power saving. |
| Value in multiples of *preferredDRX-ShortCycle*. A value of 1         |
| corresponds to *preferredDRX-ShortCycle*, a value of 2 corresponds to |
| 2 \* *preferredDRX-ShortCycle* and so on. If the field is absent from |
| the *DRX-Preference* IE, it is interpreted as the UE having no        |
| preference for the short DRX cycle timer. A preference for the short  |
| DRX cycle is indicated when a preference for the short DRX cycle      |
| timer is indicated.                                                   |
+-----------------------------------------------------------------------+
| ***preferredK0***                                                     |
|                                                                       |
| Indicates the UE\'s preferred value of *k0* (slot offset between DCI  |
| and its scheduled PDSCH - see TS 38.214 \[19\], clause 5.1.2.1) for   |
| cross-slot scheduling for power saving. Value is defined for each     |
| subcarrier spacing (numerology) in units of slots. *sl1* corresponds  |
| to 1 slot, *sl2* corresponds to 2 slots, *sl4* corresponds to 4       |
| slots, and so on. If a value for a subcarrier spacing is absent, it   |
| is interpreted as the UE having no preference on *k0* for cross-slot  |
| scheduling for that subcarrier spacing. If the field is absent from   |
| the *MinSchedulingOffsetPreference* IE, it is interpreted as the UE   |
| having no preference on *k0* for cross-slot scheduling.               |
+-----------------------------------------------------------------------+
| ***preferredK2***                                                     |
|                                                                       |
| Indicates the UE\'s preferred value of *k2* (slot offset between DCI  |
| and its scheduled PUSCH - see TS 38.214 \[19\], clause 6.1.2.1) for   |
| cross-slot scheduling for power saving. Value is defined for each     |
| subcarrier spacing (numerology) in units of slots. *sl1* corresponds  |
| to 1 slot, *sl2* corresponds to 2 slots, *sl4* corresponds to 4       |
| slots, and so on. If a value for a subcarrier spacing is absent, it   |
| is interpreted as the UE having no preference on *k2* for cross-slot  |
| scheduling for that subcarrier spacing. If the field is absent from   |
| the *MinSchedulingOffsetPreference* IE, it is interpreted as the UE   |
| having no preference on *k2* for cross-slot scheduling.               |
+-----------------------------------------------------------------------+
| ***preferredRRC-State***                                              |
|                                                                       |
| Indicates the UE\'s preferred RRC state. The value *idle* is          |
| indicated if the UE prefers to be released from RRC_CONNECTED and     |
| transition to RRC_IDLE. The value *inactive* is indicated if the UE   |
| prefers to be released from RRC_CONNECTED and transition to           |
| RRC_INACTIVE. The value *connected* is indicated if the UE prefers to |
| revert an earlier indication to leave RRC_CONNECTED state. The value  |
| *outOfConnected* is indicated if the UE prefers to be released from   |
| RRC_CONNECTED and has no preferred RRC state to transition to. The    |
| value *connected* can only be indicated if the UE is configured with  |
| *connectedReporting*.                                                 |
+-----------------------------------------------------------------------+
| ***propagationDelayDifference***                                      |
|                                                                       |
| Indicates the one-way service link propagation delay difference       |
| between serving cell and each neighbour cell included in              |
| *neighCellInfoList,* defined as neighbour cell\'s service link        |
| propagation delay minus serving cell\'s service link propagation      |
| delay, in number of ms. First entry in *propagationDelayDifference*   |
| corresponds to first entry in *neighCellInfoList*, second entry in    |
| *propagationDelayDifference* corresponds to second entry in           |
| *neighCellInfoList*, and so on.                                       |
+-----------------------------------------------------------------------+
| ***reducedCCsDL***                                                    |
|                                                                       |
| Indicates the UE\'s preference on reduced configuration corresponding |
| to the maximum number of downlink SCells indicated by the field, to   |
| address overheating or power saving.                                  |
|                                                                       |
| When indicated to address overheating, this maximum number includes   |
| SCells of the NR MCG, PSCell and SCells of the SCG. This maximum      |
| number only includes PSCell and SCells of the SCG in (NG)EN-DC.       |
|                                                                       |
| When indicated to address power saving, this maximum number includes  |
| PSCell and SCells of the cell group that this UE assistance           |
| information is associated with. The maximum number of downlink SCells |
| can only range up to the current active configuration when indicated  |
| to address power savings.                                             |
+-----------------------------------------------------------------------+
| ***reducedCCsUL***                                                    |
|                                                                       |
| Indicates the UE\'s preference on reduced configuration corresponding |
| to the maximum number of uplink SCells indicated by the field, to     |
| address overheating or power saving.                                  |
|                                                                       |
| When indicated to address overheating, this maximum number includes   |
| SCells of the NR MCG, PSCell and SCells of the SCG. This maximum      |
| number only includes PSCell and SCells of the SCG in (NG)EN-DC.       |
|                                                                       |
| When indicated to address power saving, this maximum number includes  |
| PSCell and SCells of the cell group that this UE assistance           |
| information is associated with. The maximum number of uplink SCells   |
| can only range up to the current active configuration when indicated  |
| to address power savings.                                             |
+-----------------------------------------------------------------------+
| ***reducedMaxBW-FR1***                                                |
|                                                                       |
| Indicates the UE\'s preference on reduced configuration corresponding |
| to the maximum aggregated bandwidth across all downlink carrier(s)    |
| and across all uplink carrier(s) of FR1, to address overheating or    |
| power saving. This field is allowed to be reported only when UE is    |
| configured with serving cell(s) operating on FR1. The aggregated      |
| bandwidth across all downlink carrier(s) of FR1 is the sum of         |
| bandwidth of active downlink BWP(s) across all activated downlink     |
| carrier(s) of FR1. The aggregated bandwidth across all uplink         |
| carrier(s) of FR1 is the sum of bandwidth of active uplink BWP(s)     |
| across all activated uplink carrier(s) of FR1. If the field is absent |
| from the *MaxBW-Preference* IE or the *OverheatingAssistance* IE, it  |
| is interpreted as the UE having no preference on the maximum          |
| aggregated bandwidth of FR1.                                          |
|                                                                       |
| When indicated to address overheating, this maximum aggregated        |
| bandwidth includes carrier(s) of FR1 of both the NR MCG and the SCG.  |
| This maximum aggregated bandwidth only includes carriers of FR1 of    |
| the SCG in (NG)EN-DC. Value *mhz0* is not used when indicated to      |
| address overheating.                                                  |
|                                                                       |
| When indicated to address power saving, this maximum aggregated       |
| bandwidth includes carrier(s) of FR1 of the cell group that this UE   |
| assistance information is associated with. The aggregated bandwidth   |
| can only range up to the current active configuration when indicated  |
| to address power savings.                                             |
+-----------------------------------------------------------------------+
| ***reducedMaxBW-FR2***                                                |
|                                                                       |
| Indicates the UE\'s preference on reduced configuration corresponding |
| to the maximum aggregated bandwidth across all downlink carrier(s)    |
| and across all uplink carrier(s) of FR2-1, to address overheating or  |
| power saving. This field is allowed to be reported only when UE is    |
| configured with serving cell(s) operating on FR2-1. The aggregated    |
| bandwidth across all downlink carrier(s) of FR2-1 is the sum of       |
| bandwidth of active downlink BWP(s) across all activated downlink     |
| carrier(s) of FR2-1. The aggregated bandwidth across all uplink       |
| carrier(s) of FR2-1 is the sum of bandwidth of active uplink BWP(s)   |
| across all activated uplink carrier(s) of FR2-1. If the field is      |
| absent from the *MaxBW-Preference* IE or the *OverheatingAssistance*  |
| IE, it is interpreted as the UE having no preference on the maximum   |
| aggregated bandwidth of FR2-1.                                        |
|                                                                       |
| When indicated to address overheating, this maximum aggregated        |
| bandwidth includes carrier(s) of FR2-1 of both the NR MCG and the NR  |
| SCG. This maximum aggregated bandwidth only includes carriers of      |
| FR2-1 of the SCG in (NG)EN-DC.                                        |
|                                                                       |
| When indicated to address power saving, this maximum aggregated       |
| bandwidth includes carrier(s) of FR2-1 of the cell group that this UE |
| assistance information is associated with. The aggregated bandwidth   |
| can only range up to the current active configuration when indicated  |
| to address power savings.                                             |
+-----------------------------------------------------------------------+
| ***reducedMaxBW-FR2-2***                                              |
|                                                                       |
| Indicates the UE\'s preference on reduced configuration corresponding |
| to the maximum aggregated bandwidth across all downlink carrier(s)    |
| and across all uplink carrier(s) of FR2-2, to address overheating or  |
| power saving. This field is allowed to be reported only when UE is    |
| configured with serving cell(s) operating on FR2-2. The aggregated    |
| bandwidth across all downlink carrier(s) of FR2-2 is the sum of       |
| bandwidth of active downlink BWP(s) across all activated downlink     |
| carrier(s) of FR2-2. The aggregated bandwidth across all uplink       |
| carrier(s) of FR2-2 is the sum of bandwidth of active uplink BWP(s)   |
| across all activated uplink carrier(s) of FR2-2. If the field is      |
| absent from the *MaxBW-PreferenceFR2-2* IE or the                     |
| *OverheatingAssistance* IE, it is interpreted as the UE having no     |
| preference on the maximum aggregated bandwidth of FR2-2.              |
|                                                                       |
| When indicated to address overheating, this maximum aggregated        |
| bandwidth includes carrier(s) of FR2-2 of both the NR MCG and the NR  |
| SCG. This maximum aggregated bandwidth only includes carriers of      |
| FR2-2 of the SCG in (NG)EN-DC.                                        |
|                                                                       |
| When indicated to address power saving, this maximum aggregated       |
| bandwidth includes carrier(s) of FR2-2 of the cell group that this UE |
| assistance information is associated with. The aggregated bandwidth   |
| can only range up to the current active configuration when indicated  |
| to address power savings.                                             |
+-----------------------------------------------------------------------+
| ***reducedMIMO-LayersFR1-DL***                                        |
|                                                                       |
| Indicates the UE\'s preference on reduced configuration corresponding |
| to the maximum number of downlink MIMO layers of each serving cell    |
| operating on FR1 indicated by the field, to address overheating or    |
| power saving. This field is allowed to be reported only when UE is    |
| configured with serving cells operating on FR1. The maximum number of |
| downlink MIMO layers can only range up to the maximum number of MIMO  |
| layers configured across all activated downlink carrier(s) of FR1 in  |
| the cell group when indicated to address power savings.               |
+-----------------------------------------------------------------------+
| ***reducedMIMO-LayersFR1-UL***                                        |
|                                                                       |
| Indicates the UE\'s preference on reduced configuration corresponding |
| to the maximum number of uplink MIMO layers of each serving cell      |
| operating on FR1 indicated by the field, to address overheating or    |
| power saving (see NOTE 1). This field is allowed to be reported only  |
| when UE is configured with serving cells operating on FR1. The        |
| maximum number of uplink MIMO layers can only range up to the maximum |
| number of MIMO layers configured across all activated uplink          |
| carrier(s) of FR1 in the cell group when indicated to address power   |
| savings.                                                              |
+-----------------------------------------------------------------------+
| ***reducedMIMO-LayersFR2-DL***                                        |
|                                                                       |
| Indicates the UE\'s preference on reduced configuration corresponding |
| to the maximum number of downlink MIMO layers of each serving cell    |
| operating on FR2-1 indicated by the field, to address overheating or  |
| power saving. This field is allowed to be reported only when UE is    |
| configured with serving cells operating on FR2-1. The maximum number  |
| of downlink MIMO layers can only range up to the maximum number of    |
| MIMO layers configured across all activated downlink carrier(s) of    |
| FR2-1 in the cell group when indicated to address power savings.      |
+-----------------------------------------------------------------------+
| ***reducedMIMO-LayersFR2-UL***                                        |
|                                                                       |
| Indicates the UE\'s preference on reduced configuration corresponding |
| to the maximum number of uplink MIMO layers of each serving cell      |
| operating on FR2-1 indicated by the field, to address overheating or  |
| power saving (see NOTE 1). This field is allowed to be reported only  |
| when UE is configured with serving cells operating on FR2-1. The      |
| maximum number of uplink MIMO layers can only range up to the maximum |
| number of MIMO layers configured across all activated uplink          |
| carrier(s) of FR2-1 in the cell group when indicated to address power |
| savings.                                                              |
+-----------------------------------------------------------------------+
| ***reducedMIMO-LayersFR2-2-DL***                                      |
|                                                                       |
| Indicates the UE\'s preference on reduced configuration corresponding |
| to the maximum number of downlink MIMO layers of each serving cell    |
| operating on FR2-2 indicated by the field, to address overheating or  |
| power saving. This field is allowed to be reported only when UE is    |
| configured with serving cells operating on FR2-2. The maximum number  |
| of downlink MIMO layers can only range up to the maximum number of    |
| MIMO layers configured across all activated downlink carrier(s) of    |
| FR2-2 in the cell group when indicated to address power savings.      |
+-----------------------------------------------------------------------+
| ***reducedMIMO-LayersFR2-2-UL***                                      |
|                                                                       |
| Indicates the UE\'s preference on reduced configuration corresponding |
| to the maximum number of uplink MIMO layers of each serving cell      |
| operating on FR2-2 indicated by the field, to address overheating or  |
| power saving (see NOTE 1). This field is allowed to be reported only  |
| when UE is configured with serving cells operating on FR2-2. The      |
| maximum number of uplink MIMO layers can only range up to the maximum |
| number of MIMO layers configured across all activated uplink          |
| carrier(s) of FR2-2 in the cell group when indicated to address power |
| savings.                                                              |
+-----------------------------------------------------------------------+
| ***referenceTimeInfoPreference***                                     |
|                                                                       |
| Indicates whether the UE prefers being provisioned with the timing    |
| information specified in the IE *ReferenceTimeInfo*.                  |
+-----------------------------------------------------------------------+
| ***resumeCause***                                                     |
|                                                                       |
| Provides the resume cause based on the information received from the  |
| upper layers.                                                         |
+-----------------------------------------------------------------------+
| ***rlm-MeasRelaxationState***                                         |
|                                                                       |
| Indicates the relaxation state of RLM measurements. Value *true*      |
| indicates that the UE is performing relaxation of RLM measurements,   |
| and value *false* indicates that the UE is not performing relaxation  |
| of RLM measurements.                                                  |
+-----------------------------------------------------------------------+
| ***rrm-MeasRelaxationFulfilment***                                    |
|                                                                       |
| Indicates whether the UE fulfils the relaxed measurement criterion    |
| for stationary UE in 5.7.4.4. Value true indicates that the UE        |
| fulfils the criterion, and value false indicates that the UE does not |
| fulfil the criterion.                                                 |
+-----------------------------------------------------------------------+
| ***sl-QoS-FlowIdentity***                                             |
|                                                                       |
| This identity uniquely identifies one sidelink QoS flow between the   |
| UE and the network in the scope of UE, which is unique for different  |
| destination and cast type.                                            |
+-----------------------------------------------------------------------+
| ***sl-PRS-Bandwidth***                                                |
|                                                                       |
| Indicates the desired bandwidth of the requested SL-PRS resources     |
| provided by upper layers (see TS 38.355 \[77\]) in the unit of MHz.   |
+-----------------------------------------------------------------------+
| ***sl-PRS-DelayBudget***                                              |
|                                                                       |
| Indicates the SL-PRS delay budget provided by upper layers (see TS    |
| 38.355 \[77\]).                                                       |
+-----------------------------------------------------------------------+
| ***sl-PRS-Periodicity***                                              |
|                                                                       |
| Indicates the periodicity of SL-PRS transmission.                     |
+-----------------------------------------------------------------------+
| ***sl-PRS-Priority***                                                 |
|                                                                       |
| Indicates the priority of SL-PRS provided by upper layers (see TS     |
| 38.355 \[77\]). Value 1 is the highest priority whereas value 8 is    |
| the lowest priority.                                                  |
+-----------------------------------------------------------------------+
| ***sl-UE-AssistanceInformationNR***                                   |
|                                                                       |
| Indicates the traffic characteristic of sidelink logical channel(s),  |
| specified in the IE *SL-TrafficPatternInfo,* that are setup for NR    |
| sidelink communication.                                               |
+-----------------------------------------------------------------------+
| ***slotOffset***                                                      |
|                                                                       |
| Indicates the UE\'s preferred slot offset to resolve the IDC problem, |
| in multiples of 1/32 ms.                                              |
+-----------------------------------------------------------------------+
| ***startOffset***                                                     |
|                                                                       |
| Indicates the UE\'s preferred start offset to resolve the IDC         |
| problem, in multiples of 1 ms.                                        |
+-----------------------------------------------------------------------+
| ***type1***                                                           |
|                                                                       |
| Indicates the preferred amount of increment/decrement to the long DRX |
| cycle length with respect to the current configuration. Value in      |
| number of milliseconds. Value *ms40* corresponds to 40 milliseconds,  |
| *msMinus40* corresponds to -40 milliseconds and so on.                |
+-----------------------------------------------------------------------+
| ***ul-GapFR2-PatternPreference***                                     |
|                                                                       |
| Indicates the UE\'s preference on FR2 UL gap pattern as defined in TS |
| 38.133 \[14\].                                                        |
+-----------------------------------------------------------------------+
| ***victimSystemType***                                                |
|                                                                       |
| Indicate the list of victim system types to which IDC interference is |
| caused from NR. Value *gps*, *glonass*, *bds*, *galileo* and *navIC*  |
| indicates the type of GNSS. Value *wlan* indicates WLAN and value     |
| *bluetooth* indicates Bluetooth. Value *uwb* indicates Ultra Wide     |
| Band.                                                                 |
+-----------------------------------------------------------------------+

NOTE 1: The field may also indicate the UE\'s preference on reduced
configuration corresponding to the maximum number of SRS ports (i.e.
*nrofSRS-Ports*) of each serving cell operating on the associated
frequency range.

+-----------------------------------------------------------------------+
| *SL-TrafficPatternInfo field descriptions*                            |
+=======================================================================+
| ***messageSize***                                                     |
|                                                                       |
| Indicates the maximum TB size based on the observed traffic pattern.  |
| The value refers to the index of TS 38.321 \[3\], table 6.1.3.1-2.    |
+-----------------------------------------------------------------------+
| ***timingOffset***                                                    |
|                                                                       |
| This field indicates the estimated timing for a packet arrival in a   |
| sidelink logical channel. Specifically, the value indicates the       |
| timing offset with respect to subframe#0 of SFN#0 in milliseconds.    |
+-----------------------------------------------------------------------+
| ***trafficPeriodicity***                                              |
|                                                                       |
| This field indicates the estimated data arrival periodicity in a      |
| sidelink logical channel. Value ms20 corresponds to 20 ms, ms50       |
| corresponds to 50 ms and so on.                                       |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *UL-TrafficInfo field descriptions*                                   |
+=======================================================================+
| ***burstArrivalTime***                                                |
|                                                                       |
| Indicates the expected arrival time of the first packet of the Data   |
| Burst for the concerned QoS flow. If the UE provides both             |
| *burstArrivalTime* and *jitterRange, burstArrivalTime* is used as a   |
| reference time for the indicated jitter range.                        |
|                                                                       |
| If *burstArrivalTime* is indicated as *referenceTime*, the indicated  |
| time in 10ns unit from the origin is *refDays*\*86400\*1000\*100000 + |
| *refSeconds*\*1000\*100000 + *refMilliSeconds*\*100000 +              |
| *refTenNanoSeconds*. The *refDays* field specifies the sequential     |
| number of days (with day count starting at 0) from 00:00:00 on        |
| Gregorian calendar date 6 January, 1980 (start of GPS time).          |
|                                                                       |
| If *burstArrivalTime* is indicated as *referenceSFN-AndSlot*, it      |
| refers to the UL timing of the closest SFN and slot of the PCell with |
| the indicated number.                                                 |
+-----------------------------------------------------------------------+
| ***jitterRange***                                                     |
|                                                                       |
| Indicates the maximum deviation of the arrival time of the first      |
| packet of a Data Burst compared to the time indicated with            |
| *burstArrivalTime* and the periodicity of the Data Bursts.            |
| *lowerBound* indicates the negative deviation while *upperBound*      |
| indicates the positive deviation. This field shall only be reported   |
| together with the *burstArrivalTime* or after the *burstArrivalTime*  |
| has been already reported. Value ms0 corresponds to 0 ms, value 0dot5 |
| to 0.5 ms, value ms1 to 1 ms and so on. Value *beyondMs7* indicates   |
| the jitter bound is higher than 7 ms. Value 0 ms means there is no    |
| Data Burst arrival time deviation from the indicated                  |
| *burstArrivalTime*.                                                   |
+-----------------------------------------------------------------------+
| ***pdu-SetIdentification***                                           |
|                                                                       |
| Indicates whether the UE is able to identify PDU Set(s) for the QoS   |
| flow. If set to *true*, the UE is able to identify PDU Set(s) for the |
| associated QoS flow, otherwise, the UE is not able to do so. Before   |
| receiving this indication, the network assumes the value is set to    |
| *false*.                                                              |
+-----------------------------------------------------------------------+
| ***psi-Identification***                                              |
|                                                                       |
| Indicates whether the UE is able to identify PSI(s) for the QoS flow. |
| This field shall only be set to *true* if *pdu-SetIdentification* is  |
| also set to *true* (or was set to *true* previously for the same QoS  |
| flow). If set to *true*, the UE is able to identify PSI(s) for the    |
| associated QoS flow, otherwise, the UE is not able to do so. Before   |
| receiving this indication, the network assumes the value is set to    |
| *false*.                                                              |
+-----------------------------------------------------------------------+
| ***qfi***                                                             |
|                                                                       |
| Identity of the QoS flow to which this UL traffic information refers. |
+-----------------------------------------------------------------------+
| ***trafficPeriodicity***                                              |
|                                                                       |
| Indicates the average time period between the start times of two data |
| bursts, expressed in the number of microseconds.                      |
+-----------------------------------------------------------------------+

#### -- *UECapabilityEnquiry*

The *UECapabilityEnquiry* message is used to request UE radio access
capabilities for NR as well as for other RATs.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*UECapabilityEnquiry* message

\-- ASN1START

\-- TAG-UECAPABILITYENQUIRY-START

UECapabilityEnquiry ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

ueCapabilityEnquiry UECapabilityEnquiry-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

UECapabilityEnquiry-IEs ::= SEQUENCE {

ue-CapabilityRAT-RequestList UE-CapabilityRAT-RequestList,

lateNonCriticalExtension OCTET STRING OPTIONAL,

ue-CapabilityEnquiryExt OCTET STRING (CONTAINING
UECapabilityEnquiry-v1560-IEs) OPTIONAL \-- Need N

}

UECapabilityEnquiry-v1560-IEs ::= SEQUENCE {

capabilityRequestFilterCommon UE-CapabilityRequestFilterCommon OPTIONAL,
\-- Need N

nonCriticalExtension UECapabilityEnquiry-v1610-IEs OPTIONAL

}

UECapabilityEnquiry-v1610-IEs ::= SEQUENCE {

rrc-SegAllowed-r16 ENUMERATED {enabled} OPTIONAL, \-- Need N

nonCriticalExtension UECapabilityEnquiry-v17b0-IEs OPTIONAL

}

UECapabilityEnquiry-v17b0-IEs ::= SEQUENCE {

rrc-MaxCapaSegAllowed-r17 INTEGER (2..16) OPTIONAL, \-- Need N

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-UECAPABILITYENQUIRY-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UECapabilityEnquiry-IEs* field descriptions                          |
+=======================================================================+
| ***rrc-MaxCapaSegAllowed***                                           |
|                                                                       |
| This field is used to enable the UL message segment transfer for      |
| *UECapabilityInformation* message with the number of segments allowed |
| by the network. The field is present only if *rrc-SegAllowed* is not  |
| present.                                                              |
+-----------------------------------------------------------------------+
| ***rrc-SegAllowed***                                                  |
|                                                                       |
| This field is used to enable the UL message segment transfer for      |
| *UECapabilityInformation* message. The field is present only if       |
| *rrc-MaxCapaSegAllowe*d is not present.                               |
+-----------------------------------------------------------------------+

#### -- *UECapabilityInformation*

The IE *UECapabilityInformation* message is used to transfer UE radio
access capabilities requested by the network.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*UECapabilityInformation* message

\-- ASN1START

\-- TAG-UECAPABILITYINFORMATION-START

UECapabilityInformation ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

ueCapabilityInformation UECapabilityInformation-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

UECapabilityInformation-IEs ::= SEQUENCE {

ue-CapabilityRAT-ContainerList UE-CapabilityRAT-ContainerList OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

\-- TAG-UECAPABILITYINFORMATION-STOP

\-- ASN1STOP

#### -- *UEInformationRequest*

The *UEInformationRequest* message is used by the network to retrieve
information from the UE.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: Network to UE

*UEInformationRequest* message

\-- ASN1START

\-- TAG-UEINFORMATIONREQUEST-START

UEInformationRequest-r16 ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

ueInformationRequest-r16 UEInformationRequest-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

UEInformationRequest-r16-IEs ::= SEQUENCE {

idleModeMeasurementReq-r16 ENUMERATED{true} OPTIONAL, \-- Need N

logMeasReportReq-r16 ENUMERATED {true} OPTIONAL, \-- Need N

connEstFailReportReq-r16 ENUMERATED {true} OPTIONAL, \-- Need N

ra-ReportReq-r16 ENUMERATED {true} OPTIONAL, \-- Need N

rlf-ReportReq-r16 ENUMERATED {true} OPTIONAL, \-- Need N

mobilityHistoryReportReq-r16 ENUMERATED {true} OPTIONAL, \-- Need N

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension UEInformationRequest-v1700-IEs OPTIONAL

}

UEInformationRequest-v1700-IEs ::= SEQUENCE {

successHO-ReportReq-r17 ENUMERATED {true} OPTIONAL, \-- Need N

coarseLocationRequest-r17 ENUMERATED {true} OPTIONAL, \-- Need N

nonCriticalExtension UEInformationRequest-v1800-IEs OPTIONAL

}

UEInformationRequest-v1800-IEs ::= SEQUENCE {

flightPathInfoReq-r18 FlightPathInfoReportConfig-r18 OPTIONAL, \-- Need
N

successPSCell-ReportReq-r18 ENUMERATED {true} OPTIONAL, \-- Need N

reselectionMeasurementReq-r18 ENUMERATED {true} OPTIONAL, \-- Need N

validatedMeasurementsReq-r18 ENUMERATED {true} OPTIONAL, \-- Need N

nonCriticalExtension SEQUENCE {} OPTIONAL

}

FlightPathInfoReportConfig-r18 ::= SEQUENCE {

maxWayPointNumber-r18 INTEGER (1..maxWayPoint-r18),

includeTimeStamp-r18 ENUMERATED {true} OPTIONAL \-- Need N

}

\-- TAG-UEINFORMATIONREQUEST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UEInformationRequest-IEs* field descriptions                         |
+=======================================================================+
| ***coarseLocationRequest***                                           |
|                                                                       |
| This field is used to request UE to report coarse location            |
| information.                                                          |
+-----------------------------------------------------------------------+
| ***connEstFailReportReq***                                            |
|                                                                       |
| This field is used to indicate whether the UE shall report            |
| information about the connection failure.                             |
+-----------------------------------------------------------------------+
| ***flightPathInfoReq***                                               |
|                                                                       |
| This field is used to indicate whether the UE shall report the flight |
| path information, if available, and to specify the flight path        |
| information report configuration.                                     |
+-----------------------------------------------------------------------+
| ***idleModeMeasurementReq***                                          |
|                                                                       |
| This field indicates that the UE shall report the idle/inactive       |
| measurement information, if available, to the network in the          |
| *UEInformationResponse* message.                                      |
+-----------------------------------------------------------------------+
| ***logMeasReportReq***                                                |
|                                                                       |
| This field is used to indicate whether the UE shall report            |
| information about logged measurements.                                |
+-----------------------------------------------------------------------+
| ***mobilityHistoryReportReq***                                        |
|                                                                       |
| This field is used to indicate whether the UE shall report            |
| information about mobility history information.                       |
+-----------------------------------------------------------------------+
| ***ra-ReportReq***                                                    |
|                                                                       |
| This field is used to indicate whether the UE shall report            |
| information about the random access procedure.                        |
+-----------------------------------------------------------------------+
| ***reselectionMeasurementReq***                                       |
|                                                                       |
| This field indicates that the UE shall report the reselection         |
| measurement information, if available, to the network in the          |
| *UEInformationResponse* message.                                      |
+-----------------------------------------------------------------------+
| ***rlf-ReportReq***                                                   |
|                                                                       |
| This field is used to indicate whether the UE shall report            |
| information about the radio link failure.                             |
+-----------------------------------------------------------------------+
| ***successHO-ReportReq***                                             |
|                                                                       |
| This field is used to indicate whether the UE shall report            |
| information about the successful handover report.                     |
+-----------------------------------------------------------------------+
| ***successPSCell-ReportReq***                                         |
|                                                                       |
| This field is used to indicate whether the UE shall report            |
| information about the successful PSCell change or addition report.    |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *FlightPathInfoReportConfig* field descriptions                       |
+=======================================================================+
| ***includeTimeStamp***                                                |
|                                                                       |
| Indicates whether time stamp of each way point can be reported in the |
| flight path information report if time stamp information is available |
| at the UE.                                                            |
+-----------------------------------------------------------------------+
| ***maxWayPointNumber***                                               |
|                                                                       |
| Indicates the maximum number of way points UE can include in the      |
| flight path information report if this information is available at    |
| the UE.                                                               |
+-----------------------------------------------------------------------+

#### -- *UEInformationResponse*

The *UEInformationResponse* message is used by the UE to transfer
information requested by the network.

Signalling radio bearer: SRB1 or SRB2 (when logged measurement
information is included)

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to network

*UEInformationResponse message*

\-- ASN1START

\-- TAG-UEINFORMATIONRESPONSE-START

UEInformationResponse-r16 ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

ueInformationResponse-r16 UEInformationResponse-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

UEInformationResponse-r16-IEs ::= SEQUENCE {

measResultIdleEUTRA-r16 MeasResultIdleEUTRA-r16 OPTIONAL,

measResultIdleNR-r16 MeasResultIdleNR-r16 OPTIONAL,

logMeasReport-r16 LogMeasReport-r16 OPTIONAL,

connEstFailReport-r16 ConnEstFailReport-r16 OPTIONAL,

ra-ReportList-r16 RA-ReportList-r16 OPTIONAL,

rlf-Report-r16 RLF-Report-r16 OPTIONAL,

mobilityHistoryReport-r16 MobilityHistoryReport-r16 OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension UEInformationResponse-v1700-IEs OPTIONAL

}

UEInformationResponse-v1700-IEs ::= SEQUENCE {

successHO-Report-r17 SuccessHO-Report-r17 OPTIONAL,

connEstFailReportList-r17 ConnEstFailReportList-r17 OPTIONAL,

coarseLocationInfo-r17 OCTET STRING OPTIONAL,

nonCriticalExtension UEInformationResponse-v1800-IEs OPTIONAL

}

UEInformationResponse-v1800-IEs ::= SEQUENCE {

flightPathInfoReport-r18 FlightPathInfoReport-r18 OPTIONAL,

successPSCell-Report-r18 SuccessPSCell-Report-r18 OPTIONAL,

measResultReselectionNR-r18 MeasResultIdleNR-r16 OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

FlightPathInfoReport-r18 ::= SEQUENCE (SIZE (0..maxWayPoint-r18)) OF
WayPoint-r18

WayPoint-r18 ::= SEQUENCE {

wayPointLocation-r18 OCTET STRING,

timeStamp-r18 AbsoluteTimeInfo-r16 OPTIONAL

}

LogMeasReport-r16 ::= SEQUENCE {

absoluteTimeStamp-r16 AbsoluteTimeInfo-r16,

traceReference-r16 TraceReference-r16,

traceRecordingSessionRef-r16 OCTET STRING (SIZE (2)),

tce-Id-r16 OCTET STRING (SIZE (1)),

logMeasInfoList-r16 LogMeasInfoList-r16,

logMeasAvailable-r16 ENUMERATED {true} OPTIONAL,

logMeasAvailableBT-r16 ENUMERATED {true} OPTIONAL,

logMeasAvailableWLAN-r16 ENUMERATED {true} OPTIONAL,

\...

}

LogMeasInfoList-r16 ::= SEQUENCE (SIZE (1..maxLogMeasReport-r16)) OF
LogMeasInfo-r16

LogMeasInfo-r16 ::= SEQUENCE {

locationInfo-r16 LocationInfo-r16 OPTIONAL,

relativeTimeStamp-r16 INTEGER (0..7200),

servCellIdentity-r16 CGI-Info-Logging-r16 OPTIONAL,

measResultServingCell-r16 MeasResultServingCell-r16 OPTIONAL,

measResultNeighCells-r16 SEQUENCE {

measResultNeighCellListNR MeasResultListLogging2NR-r16 OPTIONAL,

measResultNeighCellListEUTRA MeasResultList2EUTRA-r16 OPTIONAL

},

anyCellSelectionDetected-r16 ENUMERATED {true} OPTIONAL,

\...,

\[\[

inDeviceCoexDetected-r17 ENUMERATED {true} OPTIONAL

\]\]

}

ConnEstFailReport-r16 ::= SEQUENCE {

measResultFailedCell-r16 MeasResultFailedCell-r16,

locationInfo-r16 LocationInfo-r16 OPTIONAL,

measResultNeighCells-r16 SEQUENCE {

measResultNeighCellListNR MeasResultList2NR-r16 OPTIONAL,

measResultNeighCellListEUTRA MeasResultList2EUTRA-r16 OPTIONAL

},

numberOfConnFail-r16 INTEGER (1..8),

perRAInfoList-r16 PerRAInfoList-r16,

timeSinceFailure-r16 TimeSinceFailure-r16,

\...

}

ConnEstFailReportList-r17 ::= SEQUENCE (SIZE (1..maxCEFReport-r17)) OF
ConnEstFailReport-r16

MeasResultServingCell-r16 ::= SEQUENCE {

resultsSSB-Cell MeasQuantityResults,

resultsSSB SEQUENCE{

best-ssb-Index SSB-Index,

best-ssb-Results MeasQuantityResults,

numberOfGoodSSB INTEGER (1..maxNrofSSBs-r16)

} OPTIONAL

}

MeasResultFailedCell-r16 ::= SEQUENCE {

cgi-Info CGI-Info-Logging-r16,

measResult-r16 SEQUENCE {

cellResults-r16 SEQUENCE{

resultsSSB-Cell-r16 MeasQuantityResults

},

rsIndexResults-r16 SEQUENCE{

resultsSSB-Indexes-r16 ResultsPerSSB-IndexList

}

}

}

RA-ReportList-r16 ::= SEQUENCE (SIZE (1..maxRAReport-r16)) OF
RA-Report-r16

RA-Report-r16 ::= SEQUENCE {

cellId-r16 CHOICE {

cellGlobalId-r16 CGI-Info-Logging-r16,

pci-arfcn-r16 PCI-ARFCN-NR-r16

},

ra-InformationCommon-r16 RA-InformationCommon-r16 OPTIONAL,

raPurpose-r16 ENUMERATED {accessRelated, beamFailureRecovery,
reconfigurationWithSync, ulUnSynchronized,

schedulingRequestFailure, noPUCCHResourceAvailable, requestForOtherSI,

msg3RequestForOtherSI-r17, lbt-Failure-r18, spare7, spare6, spare5,
spare4, spare3,

spare2, spare1},

\...,

\[\[

spCellID-r17 CGI-Info-Logging-r16 OPTIONAL

\]\],

\[\[

sdt-Failed-r18 ENUMERATED {true} OPTIONAL

\]\]

}

RA-InformationCommon-r16 ::= SEQUENCE {

absoluteFrequencyPointA-r16 ARFCN-ValueNR,

locationAndBandwidth-r16 INTEGER (0..37949),

subcarrierSpacing-r16 SubcarrierSpacing,

msg1-FrequencyStart-r16 INTEGER (0..maxNrofPhysicalResourceBlocks-1)
OPTIONAL,

msg1-FrequencyStartCFRA-r16 INTEGER (0..maxNrofPhysicalResourceBlocks-1)
OPTIONAL,

msg1-SubcarrierSpacing-r16 SubcarrierSpacing OPTIONAL,

msg1-SubcarrierSpacingCFRA-r16 SubcarrierSpacing OPTIONAL,

msg1-FDM-r16 ENUMERATED {one, two, four, eight} OPTIONAL,

msg1-FDMCFRA-r16 ENUMERATED {one, two, four, eight} OPTIONAL,

perRAInfoList-r16 PerRAInfoList-r16,

\...,

\[\[

perRAInfoList-v1660 PerRAInfoList-v1660 OPTIONAL

\]\],

\[\[

msg1-SCS-From-prach-ConfigurationIndex-r16 ENUMERATED {kHz1dot25, kHz5,
spare2, spare1} OPTIONAL

\]\],

\[\[

msg1-SCS-From-prach-ConfigurationIndexCFRA-r16 ENUMERATED {kHz1dot25,
kHz5, spare2, spare1} OPTIONAL

\]\],

\[\[

msgA-RO-FrequencyStart-r17 INTEGER (0..maxNrofPhysicalResourceBlocks-1)
OPTIONAL,

msgA-RO-FrequencyStartCFRA-r17 INTEGER
(0..maxNrofPhysicalResourceBlocks-1) OPTIONAL,

msgA-SubcarrierSpacing-r17 SubcarrierSpacing OPTIONAL,

msgA-RO-FDM-r17 ENUMERATED {one, two, four, eight} OPTIONAL,

msgA-RO-FDMCFRA-r17 ENUMERATED {one, two, four, eight} OPTIONAL,

msgA-SCS-From-prach-ConfigurationIndex-r17 ENUMERATED {kHz1dot25, kHz5,
spare2, spare1} OPTIONAL,

msgA-TransMax-r17 ENUMERATED {n1, n2, n4, n6, n8, n10, n20, n50, n100,
n200} OPTIONAL,

msgA-MCS-r17 INTEGER (0..15) OPTIONAL,

nrofPRBs-PerMsgA-PO-r17 INTEGER (1..32) OPTIONAL,

msgA-PUSCH-TimeDomainAllocation-r17 INTEGER (1..maxNrofUL-Allocations)
OPTIONAL,

frequencyStartMsgA-PUSCH-r17 INTEGER
(0..maxNrofPhysicalResourceBlocks-1) OPTIONAL,

nrofMsgA-PO-FDM-r17 ENUMERATED {one, two, four, eight} OPTIONAL,

dlPathlossRSRP-r17 RSRP-Range OPTIONAL,

intendedSIBs-r17 SEQUENCE (SIZE (1..maxSIB)) OF SIB-Type-r17 OPTIONAL,

ssbsForSI-Acquisition-r17 SEQUENCE (SIZE (1..maxNrofSSBs-r16)) OF
SSB-Index OPTIONAL,

msgA-PUSCH-PayloadSize-r17 BIT STRING (SIZE (5)) OPTIONAL,

onDemandSISuccess-r17 ENUMERATED {true} OPTIONAL

\]\],

\[\[

usedFeatureCombination-r18 ReportedFeatureCombination-r18 OPTIONAL,

triggeredFeatureCombination-r18 ReportedFeatureCombination-r18 OPTIONAL,

startPreambleForThisPartition-r18 INTEGER (0..63) OPTIONAL,

numberOfPreamblesPerSSB-ForThisPartition-r18 INTEGER (1..64) OPTIONAL,

attemptedBWP-InfoList-r18 SEQUENCE (SIZE (1..maxNrofBWPs)) OF
AttemptedBWP-Info-r18 OPTIONAL,

numberOfLBT-Failures-r18 INTEGER (1..128) OPTIONAL,

perRAInfoList-v1800 PerRAInfoList-v1800 OPTIONAL,

intendedSIBs-r18 SEQUENCE (SIZE (1..maxSIB)) OF SIB-Type-r18 OPTIONAL

\]\]

}

AttemptedBWP-Info-r18 ::= SEQUENCE {

locationAndBandwidth-r18 INTEGER (0..37949),

subcarrierSpacing-r18 SubcarrierSpacing

}

ReportedFeatureCombination-r18 ::= SEQUENCE {

redCap-r18 ENUMERATED {true} OPTIONAL,

smallData-r18 ENUMERATED {true} OPTIONAL,

nsag-r18 NSAG-List-r17 OPTIONAL,

msg3-Repetitions-r18 ENUMERATED {true} OPTIONAL,

msg1-Repetitions-r18 ENUMERATED {true} OPTIONAL,

eRedCap-r18 ENUMERATED {true} OPTIONAL,

triggered-S-NSSAI-List-r18 SEQUENCE (SIZE (1..maxNrofS-NSSAI)) OF
S-NSSAI OPTIONAL

}

PerRAInfoList-r16 ::= SEQUENCE (SIZE (1..200)) OF PerRAInfo-r16

PerRAInfoList-v1660 ::= SEQUENCE (SIZE (1..200)) OF
PerRACSI-RSInfo-v1660

PerRAInfo-r16 ::= CHOICE {

perRASSBInfoList-r16 PerRASSBInfo-r16,

perRACSI-RSInfoList-r16 PerRACSI-RSInfo-r16

}

PerRAInfoList-v1800 ::= SEQUENCE (SIZE (1..200)) OF PerRAInfo-v1800

PerRAInfo-v1800 ::= CHOICE {

perRASSBInfoList-v1800 PerRASSBInfo-v1800,

perRACSI-RSInfoList-v1800 PerRACSI-RSInfo-v1800

}

PerRASSBInfo-r16 ::= SEQUENCE {

ssb-Index-r16 SSB-Index,

numberOfPreamblesSentOnSSB-r16 INTEGER (1..200),

perRAAttemptInfoList-r16 PerRAAttemptInfoList-r16

}

PerRASSBInfo-v1800 ::= SEQUENCE {

allPreamblesBlocked ENUMERATED {true} OPTIONAL,

lbt-Detected-r18 ENUMERATED {true} OPTIONAL,

\...

}

PerRACSI-RSInfo-r16 ::= SEQUENCE {

csi-RS-Index-r16 CSI-RS-Index,

numberOfPreamblesSentOnCSI-RS-r16 INTEGER (1..200)

}

PerRACSI-RSInfo-v1660 ::= SEQUENCE {

csi-RS-Index-v1660 INTEGER (1..96) OPTIONAL

}

PerRACSI-RSInfo-v1800 ::= SEQUENCE {

allPreamblesBlocked ENUMERATED {true} OPTIONAL,

lbt-Detected-r18 ENUMERATED {true} OPTIONAL,

\...

}

PerRAAttemptInfoList-r16 ::= SEQUENCE (SIZE (1..200)) OF
PerRAAttemptInfo-r16

PerRAAttemptInfo-r16 ::= SEQUENCE {

contentionDetected-r16 BOOLEAN OPTIONAL,

dlRSRPAboveThreshold-r16 BOOLEAN OPTIONAL,

\...,

\[\[

fallbackToFourStepRA-r17 ENUMERATED {true} OPTIONAL

\]\]

}

SIB-Type-r17 ::= ENUMERATED {sibType2, sibType3, sibType4, sibType5,
sibType9, sibType10, sibType11, sibType12,

sibType13, sibType14, posSIB-v1810, spare5, spare4, spare3, spare2,
spare1}

SIB-Type-r18 ::= ENUMERATED {sibType15, sibType16, sibType17, sibType18,
sibType19, sibType20,

sibType21, sibType22, sibType23, sibType24, sibType25, spare5, spare4,

spare3, spare2, spare1}

RLF-Report-r16 ::= CHOICE {

nr-RLF-Report-r16 SEQUENCE {

measResultLastServCell-r16 MeasResultRLFNR-r16,

measResultNeighCells-r16 SEQUENCE {

measResultListNR-r16 MeasResultList2NR-r16 OPTIONAL,

measResultListEUTRA-r16 MeasResultList2EUTRA-r16 OPTIONAL

} OPTIONAL,

c-RNTI-r16 RNTI-Value,

previousPCellId-r16 CHOICE {

nrPreviousCell-r16 CGI-Info-Logging-r16,

eutraPreviousCell-r16 CGI-InfoEUTRALogging

} OPTIONAL,

failedPCellId-r16 CHOICE {

nrFailedPCellId-r16 CHOICE {

cellGlobalId-r16 CGI-Info-Logging-r16,

pci-arfcn-r16 PCI-ARFCN-NR-r16

},

eutraFailedPCellId-r16 CHOICE {

cellGlobalId-r16 CGI-InfoEUTRALogging,

pci-arfcn-r16 PCI-ARFCN-EUTRA-r16

}

},

reconnectCellId-r16 CHOICE {

nrReconnectCellId-r16 CGI-Info-Logging-r16,

eutraReconnectCellId-r16 CGI-InfoEUTRALogging

} OPTIONAL,

timeUntilReconnection-r16 TimeUntilReconnection-r16 OPTIONAL,

reestablishmentCellId-r16 CGI-Info-Logging-r16 OPTIONAL,

timeConnFailure-r16 INTEGER (0..1023) OPTIONAL,

timeSinceFailure-r16 TimeSinceFailure-r16,

connectionFailureType-r16 ENUMERATED {rlf, hof},

rlf-Cause-r16 ENUMERATED {t310-Expiry, randomAccessProblem,
rlc-MaxNumRetx,

beamFailureRecoveryFailure, lbtFailure-r16,

bh-rlfRecoveryFailure, t312-expiry-r17, spare1},

locationInfo-r16 LocationInfo-r16 OPTIONAL,

noSuitableCellFound-r16 ENUMERATED {true} OPTIONAL,

ra-InformationCommon-r16 RA-InformationCommon-r16 OPTIONAL,

\...,

\[\[

csi-rsRLMConfigBitmap-v1650 BIT STRING (SIZE (96)) OPTIONAL

\]\],

\[\[

lastHO-Type-r17 ENUMERATED {cho, daps, spare2, spare1} OPTIONAL,

timeConnSourceDAPS-Failure-r17 TimeConnSourceDAPS-Failure-r17 OPTIONAL,

timeSinceCHO-Reconfig-r17 TimeSinceCHO-Reconfig-r17 OPTIONAL,

choCellId-r17 CHOICE {

cellGlobalId-r17 CGI-Info-Logging-r16,

pci-arfcn-r17 PCI-ARFCN-NR-r16

} OPTIONAL,

choCandidateCellList-r17 ChoCandidateCellList-r17 OPTIONAL

\]\],

\[\[

pSCellId-r18 CHOICE {

cellGlobalId-r18 CGI-Info-Logging-r16,

pci-arfcn-r18 PCI-ARFCN-NR-r16

} OPTIONAL,

mcg-RecoveryFailureCause-r18 ENUMERATED {t316-Expiry, scg-Deactivated,
spare2, spare1} OPTIONAL,

scg-FailureCause-r18 ENUMERATED {t310-Expiry, randomAccessProblem,
rlc-MaxNumRetx,

synchReconfigFailureSCG, scg-ReconfigFailure,

srb3-IntegrityFailure, scg-lbtFailure, beamFailureRecoveryFailure,

t312-Expiry, bh-RLF, beamFailure, spare5, spare4, spare3, spare2, spare1
}

OPTIONAL,

elapsedTimeSCG-Failure-r18 ElapsedTimeSCG-Failure-r18 OPTIONAL,

voiceFallbackHO-r18 ENUMERATED {true} OPTIONAL,

measResultLastServCellRSSI-r18 RSSI-Range-r16 OPTIONAL,

measResultNeighFreqListRSSI-r18 MeasResultNeighFreqListRSSI-r18
OPTIONAL,

bwp-Info-r18 AttemptedBWP-Info-r18 OPTIONAL,

elapsedTimeT316-r18 ElapsedTimeT316-r18 OPTIONAL,

scg-FailedAfterMCG-r18 ENUMERATED {true} OPTIONAL\
\]\]

},

eutra-RLF-Report-r16 SEQUENCE {

failedPCellId-EUTRA CGI-InfoEUTRALogging,

measResult-RLF-Report-EUTRA-r16 OCTET STRING,

\...,

\[\[

measResult-RLF-Report-EUTRA-v1690 OCTET STRING OPTIONAL

\]\]

}

}

SuccessHO-Report-r17 ::= SEQUENCE {

sourceCellInfo-r17 SEQUENCE {

sourcePCellId-r17 CGI-Info-Logging-r16,

sourceCellMeas-r17 MeasResultSuccessHONR-r17 OPTIONAL,

rlf-InSourceDAPS-r17 ENUMERATED {true} OPTIONAL

},

targetCellInfo-r17 SEQUENCE {

targetPCellId-r17 CGI-Info-Logging-r16,

targetCellMeas-r17 MeasResultSuccessHONR-r17 OPTIONAL

},

measResultNeighCells-r17 SEQUENCE {

measResultListNR-r17 MeasResultList2NR-r16 OPTIONAL,

measResultListEUTRA-r17 MeasResultList2EUTRA-r16 OPTIONAL

} OPTIONAL,

locationInfo-r17 LocationInfo-r16 OPTIONAL,

timeSinceCHO-Reconfig-r17 TimeSinceCHO-Reconfig-r17 OPTIONAL,

shr-Cause-r17 SHR-Cause-r17 OPTIONAL,

ra-InformationCommon-r17 RA-InformationCommon-r16 OPTIONAL,

upInterruptionTimeAtHO-r17 UPInterruptionTimeAtHO-r17 OPTIONAL,

c-RNTI-r17 RNTI-Value OPTIONAL,

\...,

\[\[

targetCell-PCI-ARFCN-r17 PCI-ARFCN-NR-r16 OPTIONAL

\]\],

\[\[

eutra-TargetCellInfo-r18 SEQUENCE {

targetPCellId-r18 CHOICE {

cellGlobalId-r18 CGI-Info-Logging-r16,

pci-arfcn-r18 PCI-ARFCN-EUTRA-r16

},

targetCellMeas-r18 MeasQuantityResultsEUTRA OPTIONAL

} OPTIONAL,

measResultServCellRSSI-r18 RSSI-Range-r16 OPTIONAL,

measResultNeighFreqListRSSI-r18 MeasResultNeighFreqListRSSI-r18
OPTIONAL,

eutra-C-RNTI-r18 EUTRA-C-RNTI OPTIONAL,

timeSinceSHR-r18 TimeSinceSHR-r18 OPTIONAL

\]\]

}

SuccessPSCell-Report-r18 ::= SEQUENCE {

pCellId-r18 CGI-Info-Logging-r16,

sourcePSCellInfo-r18 SEQUENCE {

sourcePSCellId-r18 CHOICE {

cellGlobalId-r18 CGI-Info-Logging-r16,

pci-arfcn-r18 PCI-ARFCN-EUTRA-r16

},

sourcePSCellMeas-r18 MeasResultSuccessHONR-r17 OPTIONAL

} OPTIONAL,

targetPSCellInfo-r18 SEQUENCE {

targetPSCellId-r18 CHOICE {

cellGlobalId-r18 CGI-Info-Logging-r16,

pci-arfcn-r18 PCI-ARFCN-NR-r16

},

targetPSCellMeas-r18 MeasResultSuccessHONR-r17 OPTIONAL

},

measResultNeighCells-r18 SEQUENCE {

measResultListNR-r18 MeasResultList2NR-r16 OPTIONAL,

measResultListEUTRA-r18 MeasResultList2EUTRA-r16 OPTIONAL

} OPTIONAL,

spr-Cause-r18 SPR-Cause-r18 OPTIONAL,

timeSinceCPAC-Reconfig-r18 TimeSinceCPAC-Reconfig-r18 OPTIONAL,

locationInfo-r18 LocationInfo-r16 OPTIONAL,

ra-InformationCommon-r18 RA-InformationCommon-r16 OPTIONAL,

sn-InitiatedPSCellChange-r18 ENUMERATED {true} OPTIONAL,

\...

}

MeasResultNeighFreqListRSSI-r18 ::= SEQUENCE(SIZE (1..maxFreq)) OF
MeasResultNeighFreqRSSI-r18

MeasResultNeighFreqRSSI-r18 ::= SEQUENCE {

ssbFrequency-r18 ARFCN-ValueNR OPTIONAL,

ssbSubcarrierSpacing-r18 SubcarrierSpacing OPTIONAL,

refFreqCSI-RS-r18 ARFCN-ValueNR OPTIONAL,

measResult-RSSI-r18 RSSI-Range-r16 OPTIONAL

}

MeasResultList2NR-r16 ::= SEQUENCE(SIZE (1..maxFreq)) OF
MeasResult2NR-r16

MeasResultList2EUTRA-r16 ::= SEQUENCE(SIZE (1..maxFreq)) OF
MeasResult2EUTRA-r16

MeasResult2NR-r16 ::= SEQUENCE {

ssbFrequency-r16 ARFCN-ValueNR OPTIONAL,

refFreqCSI-RS-r16 ARFCN-ValueNR OPTIONAL,

measResultList-r16 MeasResultListNR

}

MeasResultListLogging2NR-r16 ::= SEQUENCE(SIZE (1..maxFreq)) OF
MeasResultLogging2NR-r16

MeasResultLogging2NR-r16 ::= SEQUENCE {

carrierFreq-r16 ARFCN-ValueNR,

measResultListLoggingNR-r16 MeasResultListLoggingNR-r16

}

MeasResultListLoggingNR-r16 ::= SEQUENCE (SIZE (1..maxCellReport)) OF
MeasResultLoggingNR-r16

MeasResultLoggingNR-r16 ::= SEQUENCE {

physCellId-r16 PhysCellId,

resultsSSB-Cell-r16 MeasQuantityResults,

numberOfGoodSSB-r16 INTEGER (1..maxNrofSSBs-r16) OPTIONAL

}

MeasResult2EUTRA-r16 ::= SEQUENCE {

carrierFreq-r16 ARFCN-ValueEUTRA,

measResultList-r16 MeasResultListEUTRA

}

MeasResultRLFNR-r16 ::= SEQUENCE {

measResult-r16 SEQUENCE {

cellResults-r16 SEQUENCE{

resultsSSB-Cell-r16 MeasQuantityResults OPTIONAL,

resultsCSI-RS-Cell-r16 MeasQuantityResults OPTIONAL

},

rsIndexResults-r16 SEQUENCE{

resultsSSB-Indexes-r16 ResultsPerSSB-IndexList OPTIONAL,

ssbRLMConfigBitmap-r16 BIT STRING (SIZE (64)) OPTIONAL,

resultsCSI-RS-Indexes-r16 ResultsPerCSI-RS-IndexList OPTIONAL,

csi-rsRLMConfigBitmap-r16 BIT STRING (SIZE (96)) OPTIONAL

} OPTIONAL

}

}

MeasResultSuccessHONR-r17::= SEQUENCE {

measResult-r17 SEQUENCE {

cellResults-r17 SEQUENCE{

resultsSSB-Cell-r17 MeasQuantityResults OPTIONAL,

resultsCSI-RS-Cell-r17 MeasQuantityResults OPTIONAL

},

rsIndexResults-r17 SEQUENCE{

resultsSSB-Indexes-r17 ResultsPerSSB-IndexList OPTIONAL,

resultsCSI-RS-Indexes-r17 ResultsPerCSI-RS-IndexList OPTIONAL

}

}

}

ChoCandidateCellList-r17 ::= SEQUENCE(SIZE (1..maxNrofCondCells-r16)) OF
ChoCandidateCell-r17

ChoCandidateCell-r17 ::= CHOICE {

cellGlobalId-r17 CGI-Info-Logging-r16,

pci-arfcn-r17 PCI-ARFCN-NR-r16

}

SHR-Cause-r17 ::= SEQUENCE {

t304-cause-r17 ENUMERATED {true} OPTIONAL,

t310-cause-r17 ENUMERATED {true} OPTIONAL,

t312-cause-r17 ENUMERATED {true} OPTIONAL,

sourceDAPS-Failure-r17 ENUMERATED {true} OPTIONAL,

\...

}

SPR-Cause-r18 ::= SEQUENCE {

t304-cause-r18 ENUMERATED {true} OPTIONAL,

t310-cause-r18 ENUMERATED {true} OPTIONAL,

t312-cause-r18 ENUMERATED {true} OPTIONAL,

\...

}

TimeSinceFailure-r16 ::= INTEGER (0..172800)

MobilityHistoryReport-r16 ::= VisitedCellInfoList-r16

TimeUntilReconnection-r16 ::= INTEGER (0..172800)

TimeSinceCHO-Reconfig-r17 ::= INTEGER (0..1023)

TimeSinceCPAC-Reconfig-r18 ::= INTEGER (0.. 1023)

TimeConnSourceDAPS-Failure-r17 ::= INTEGER (0..1023)

UPInterruptionTimeAtHO-r17 ::= INTEGER (0..1023)

ElapsedTimeT316-r18 ::= INTEGER (0..2000)

ElapsedTimeSCG-Failure-r18 ::= INTEGER (0..1023)

TimeSinceSHR-r18 ::= INTEGER (0..172800)

\-- TAG-UEINFORMATIONRESPONSE-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UEInformationResponse-IEs* field descriptions                        |
+=======================================================================+
| ***coarseLocationInfo***                                              |
|                                                                       |
| Parameter type Ellipsoid-Point defined in TS 37.355 \[49\]. The       |
| first/leftmost bit of the first octet contains the most significant   |
| bit. The least significant bits of *degreesLatitude* and              |
| *degreesLongitude* are set to 0 to meet the accuracy requirement      |
| corresponds to a granularity of approximately 2 km.                   |
|                                                                       |
| It is up to UE implementation how many LSBs are set to 0 to meet the  |
| accuracy requirement.                                                 |
+-----------------------------------------------------------------------+
| ***connEstFailReport***                                               |
|                                                                       |
| This field is used to provide connection establishment failure or     |
| connection resume failure information*.*                              |
+-----------------------------------------------------------------------+
| ***connEstFailReportList***                                           |
|                                                                       |
| This field is used to provide the list of *connEstFailReport* that    |
| are stored by the UE for the past up to *maxCEFReport-r17.*           |
+-----------------------------------------------------------------------+
| ***flightPathInfoReport***                                            |
|                                                                       |
| This field is used to provide the flight path information as list of  |
| waypoints and, if available, corresponding timestamps. List of size   |
| zero indicates the previously provided flight path information is no  |
| longer valid.                                                         |
+-----------------------------------------------------------------------+
| ***logMeasReport***                                                   |
|                                                                       |
| This field is used to provide the measurement results stored by the   |
| UE associated to logged MDT.                                          |
+-----------------------------------------------------------------------+
| ***measResultIdleEUTRA***                                             |
|                                                                       |
| EUTRA measurement results performed during RRC_INACTIVE or RRC_IDLE.  |
+-----------------------------------------------------------------------+
| ***measResultIdleNR***                                                |
|                                                                       |
| NR measurement results performed during RRC_INACTIVE or RRC_IDLE.     |
+-----------------------------------------------------------------------+
| ***ra-ReportList***                                                   |
|                                                                       |
| This field is used to provide the list of RA reports that is stored   |
| by the UE for up to *maxRAReport-r16* number of random access         |
| procedures. If the UE is an eRedCap UE, this field is used to provide |
| the list of RA reports that is stored by the UE for up to 2 number of |
| random access procedures.                                             |
+-----------------------------------------------------------------------+
| ***rlf-Report***                                                      |
|                                                                       |
| This field is used to indicate the RLF report related contents.       |
+-----------------------------------------------------------------------+
| ***successHO-Report***                                                |
|                                                                       |
| This field is used to provide the successful handover report if       |
| triggered based on the successful handover configuration.             |
+-----------------------------------------------------------------------+
| ***successPSCell-Report***                                            |
|                                                                       |
| This field is used to provide the successful PSCell change or         |
| addition report if triggered based on the successful PSCell change or |
| addition report configuration.                                        |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *LogMeasReport* field descriptions                                    |
+=======================================================================+
| ***absoluteTimeStamp***                                               |
|                                                                       |
| Indicates the absolute time when the logged measurement configuration |
| logging is provided, as indicated by NR within *absoluteTimeInfo*.    |
+-----------------------------------------------------------------------+
| ***anyCellSelectionDetected***                                        |
|                                                                       |
| This field is used to indicate the detection of *any cell selection*  |
| state, as defined in TS 38.304 \[20\]. The UE sets this field when    |
| performing the logging of measurement results in RRC_IDLE or          |
| RRC_INACTIVE and there is no suitable cell or no acceptable cell.     |
+-----------------------------------------------------------------------+
| ***inDeviceCoexDetected***                                            |
|                                                                       |
| Indicates that measurement logging is suspended due to IDC problem    |
| detection.                                                            |
+-----------------------------------------------------------------------+
| ***measResultServingCell***                                           |
|                                                                       |
| This field refers to the log measurement results taken in the Serving |
| cell.                                                                 |
+-----------------------------------------------------------------------+
| ***numberOfGoodSSB***                                                 |
|                                                                       |
| Indicates the number of good beams (beams that are above              |
| *absThreshSS-BlocksConsolidation,* if configured by the network)      |
| associated to the cells within the R value range (which is configured |
| by network for cell reselection) of the highest ranked cell as part   |
| of the beam level measurements. If the UE has no SSB of a neighbour   |
| cell whose measurement quantity is above the                          |
| *absThreshSS-BlocksConsolidation* or if the network has not           |
| configured the *absThreshSS-BlocksConsolidation*, then the UE does    |
| not include *numberOfGoodSSB* for the corresponding neighbour cell.   |
| If the UE has no SSB of the serving cell whose measurement quantity   |
| is above the *absThreshSS-BlocksConsolidation* or if the network has  |
| not configured the *absThreshSS-BlocksConsolidation*, then the UE     |
| shall set the *numberOfGoodSSB* for the serving cell to one.          |
+-----------------------------------------------------------------------+
| ***relativeTimeStamp***                                               |
|                                                                       |
| Indicates the time of logging measurement results, measured relative  |
| to the *absoluteTimeStamp*. Value in seconds.                         |
+-----------------------------------------------------------------------+
| ***tce-Id***                                                          |
|                                                                       |
| Parameter Trace Collection Entity Id: See TS 32.422 \[52\].           |
+-----------------------------------------------------------------------+
| ***traceRecordingSessionRef***                                        |
|                                                                       |
| Parameter Trace Recording Session Reference: See TS 32.422 \[52\].    |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *ConnEstFailReport* field descriptions                                |
+=======================================================================+
| ***measResultFailedCell***                                            |
|                                                                       |
| This field refers to the last measurement results taken in the cell,  |
| where connection establishment failure or connection resume failure   |
| happened.                                                             |
+-----------------------------------------------------------------------+
| ***measResultNeighCells***                                            |
|                                                                       |
| This field refers to the neighbour cell measurements when connection  |
| establishment failure or connection resume failure happened.          |
+-----------------------------------------------------------------------+
| ***numberOfConnFail***                                                |
|                                                                       |
| This field is used to indicate the latest number of consecutive       |
| failed RRCSetup or RRCResume procedures in the same cell independent  |
| of RRC state transition.                                              |
+-----------------------------------------------------------------------+
| ***timeSinceFailure***                                                |
|                                                                       |
| This field is used to indicate the time that elapsed since the        |
| connection (establishment or resume) failure. Value in seconds. The   |
| maximum value 172800 means 172800s or longer.                         |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *RA-InformationCommon* field descriptions                             |
+=======================================================================+
| ***absoluteFrequencyPointA***                                         |
|                                                                       |
| This field indicates the absolute frequency position of the reference |
| resource block (Common RB 0).                                         |
+-----------------------------------------------------------------------+
| ***allPreamblesBlocked***                                             |
|                                                                       |
| This field is included when the all the preamble transmission         |
| attempts in the corresponding beam (SSB or CSI-RS) are blocked by     |
| failed LBT.                                                           |
+-----------------------------------------------------------------------+
| ***attemptedBWP-InfoList***                                           |
|                                                                       |
| This field indicates *locationAndBandwidth* and *subcarrierSpacing*   |
| of all the bandwidth parts in which the consistent LBT failures are   |
| triggered at the moment of successful RA completion.                  |
+-----------------------------------------------------------------------+
| ***locationAndBandwidth***                                            |
|                                                                       |
| Frequency domain location and bandwidth of the bandwidth part         |
| associated to the random-access resources used by the UE or of the    |
| bandwidth part in which the consistent LBT failures is triggered and  |
| not cancelled prior to successful completion of random access         |
| procedure (if this field is included in *attemptedBWP-InfoList*) or   |
| prior to RLF/HOF (if this field is included in                        |
| *attemptedBWP-InfoList* or *bwp-Info*).                               |
+-----------------------------------------------------------------------+
| ***numberOfLBT-Failures***                                            |
|                                                                       |
| This field is used to indicate the total number of preamble           |
| transmission attempts for which LBT failure indication is received in |
| the RA procedure. If the number of LBT failure indications received   |
| from lower layers during the RA procedure exceeds or equals to 128,   |
| UE sets the field to 128.This field is optional present when there is |
| at least one preamble transmission attempt for which LBT failure      |
| indication is received during the RA procedure, otherwise it is       |
| absent.                                                               |
+-----------------------------------------------------------------------+
| ***numberOfPreamblesPerSSB-ForThisPartition***                        |
|                                                                       |
| This field determines how many consecutive preambles are associated   |
| to the used feature or combination of features starting from the      |
| starting preamble(s) per SSB.                                         |
+-----------------------------------------------------------------------+
| ***perRAInfoList, perRAInfoList-v1660***                              |
|                                                                       |
| This field provides detailed information about each of the random     |
| access attempts in the chronological order of the random access       |
| attempts. If *perRAInfoList-v1660* is present, it shall contain the   |
| same number of entries, listed in the same order as in                |
| *perRAInfoList-r16*.                                                  |
+-----------------------------------------------------------------------+
| ***startPreambleForThisPartition***                                   |
|                                                                       |
| This field indicates the first preamble associated with the used      |
| feature or combination of features.                                   |
+-----------------------------------------------------------------------+
| ***subcarrierSpacing***                                               |
|                                                                       |
| Subcarrier spacing used in the bandwidth part associated to the       |
| random-access resources used by the UE or of the bandwidth part in    |
| which the consistent LBT failures is triggered and not cancelled      |
| prior to successful completion of random access procedure (if this    |
| field is included in *attemptedBWP-InfoList*) or prior to RLF/HOF (if |
| this field is included in *attemptedBWP-InfoList* or *bwp-Info*).     |
+-----------------------------------------------------------------------+
| ***triggeredFeatureCombination***                                     |
|                                                                       |
| One or more features (e.g., *RedCap*, *Slicing*, *SDT* and *MSG3      |
| repetition)* that triggers the random-access procedure. When          |
| triggered feature is *Slicing*, UE includes all the S-NSSAIs          |
| associated to the slices triggering the access attempt in the         |
| random-access procedure.                                              |
+-----------------------------------------------------------------------+
| ***usedFeatureCombination***                                          |
|                                                                       |
| The feature or combination of features (e.g., *redCap*, *smallData*,  |
| *nsag* and *msg3-Repetitions*) associated to the used random-access   |
| resources as specified in TS 38.321\[3\].                             |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *RA-Report* field descriptions                                        |
+=======================================================================+
| ***cellID***                                                          |
|                                                                       |
| This field indicates the CGI of the cell in which the associated      |
| random access procedure was performed.                                |
+-----------------------------------------------------------------------+
| ***contentionDetected***                                              |
|                                                                       |
| This field is used to indicate that contention was detected for the   |
| transmitted preamble in the given random access attempt or not. This  |
| field is not included when the UE performs random access attempt is   |
| using contention free random-access resources or when the *raPurpose* |
| is set to *requestForOtherSI* or when the RA attempt is a 2-step RA   |
| attempt and fallback to 4-step RA did not occur (i.e.                 |
| *fallbackToFourStepRA* is not included).                              |
+-----------------------------------------------------------------------+
| ***csi-RS-Index, csi-RS-Index-v1660***                                |
|                                                                       |
| This field is used to indicate the CSI-RS index corresponding to the  |
| random access attempt.                                                |
|                                                                       |
| If the random access procedure is for beam failure recovery, the      |
| field indicates the NZP-CSI-RS-ResourceId. For CSI-RS index larger    |
| than maxNrofCSI-RS-ResourcesRRM-1, the index value is the sum of      |
| csi-RS-Index (without suffix) and csi-RS-Index-v1660.                 |
+-----------------------------------------------------------------------+
| ***dlPathlossRSRP***                                                  |
|                                                                       |
| Measeured RSRP of the DL pathloss reference obtained at the time of   |
| *RA_Type* selection stage of the RA procedure as captured in TS       |
| 38.321 \[3\].                                                         |
+-----------------------------------------------------------------------+
| ***dlRSRPAboveThreshold***                                            |
|                                                                       |
| In 4 step random access procedure, this field is used to indicate     |
| whether the DL beam (SSB) quality associated to the random access     |
| attempt was above or below the threshold *rsrp-ThresholdSSB* in       |
| *beamFailureRecoveryConfig* in UL BWP configuration of UL BWP         |
| selected for random access procedure initiated for beam failure       |
| recovery; Otherwise, if the UE has received *rsrp-ThresholdSSB* in    |
| *FeatureCombinationPreambles* used for the feature specific random    |
| access, the field is used to indicate whether DL beam (SSB) quality   |
| associated to the random access attempt was above or below this       |
| *rsrp-ThresholdSSB-r17*, else *rsrp-ThresholdSSB* in                  |
| *rach-ConfigCommon* in UL BWP configuration of UL BWP selected for    |
| random access procedure.                                              |
|                                                                       |
| In 2 step random access procedure, if the UE has received             |
| *msgA-RSRP-ThresholdSSB* in *FeatureCombinationPreambles* used for    |
| the feature specific random access, the field is used to indicate     |
| whether DL beam (SSB) quality associated to the random access attempt |
| was above or below this *rsrp-ThresholdSSB-r17*, else this field is   |
| used to indicate whether the DL beam (SSB) quality associated to the  |
| random access attempt was above or below the threshold                |
| *msgA-RSRP-ThresholdSSB* in *rach-ConfigCommonTwoStepRA* in UL BWP    |
| configuration of UL BWP selected for random access procedure.         |
+-----------------------------------------------------------------------+
| ***fallbackToFourStepRA***                                            |
|                                                                       |
| This field indicates if a fallback indication in MsgB is received     |
| (according to TS 38.321 \[3\]) for the 2-step random access attempt.  |
+-----------------------------------------------------------------------+
| ***intendedSIBs***                                                    |
|                                                                       |
| This field indicates the SIB(s) the UE wanted to receive as a result  |
| of the on demand SI request (when the RA procedure is a used as a SI  |
| request) initiated by the UE. That is, it indicates the one(s) of the |
| SIB(s) in the SI message(s) requested to be broadcast that the UE was |
| interested in. Value *posSIB* indicates that the UE wanted to receive |
| one or more positioning SIB(s).                                       |
+-----------------------------------------------------------------------+
| ***lbt-Detected***                                                    |
|                                                                       |
| This field is included when there is at least one LBT failure         |
| indication received prior to change of beam for preamble transmission |
| during RA procedure, otherwise this field is absent.                  |
+-----------------------------------------------------------------------+
| ***msg1-SCS-From-prach-ConfigurationIndex***                          |
|                                                                       |
| This field is set by the UE with the corresponding SCS for CBRA as    |
| derived from the *prach-ConfigurationIndex* in *RACH-ConfigGeneric*   |
| when the *msg1-SubcarrierSpacing* is absent; otherwise, this field is |
| absent.                                                               |
+-----------------------------------------------------------------------+
| ***msg1-SCS-From-prach-ConfigurationIndexCFRA***                      |
|                                                                       |
| This field is set by the UE with the corresponding SCS for CFRA as    |
| derived from the *prach-ConfigurationIndex* in *RACH-ConfigGeneric*   |
| when the *msg1-SubcarrierSpacing* is absent; otherwise, this field is |
| absent.                                                               |
+-----------------------------------------------------------------------+
| ***msgA-PUSCH-PayloadSize***                                          |
|                                                                       |
| This field indicates the size of the overall payload available in the |
| UE buffer at the time of initiating the 2 step RA procedure. The      |
| value refers to the index of TS 38.321 \[3\], table 6.1.3.1-1,        |
| corresponding to the UE buffer size.                                  |
+-----------------------------------------------------------------------+
| ***msgA-RO-FDM***                                                     |
|                                                                       |
| This field indicates the number of msgA PRACH transmission occasions  |
| Frequency-Division Multiplexed in one time instance for the PRACH     |
| resources configured for 2-step CBRA..                                |
+-----------------------------------------------------------------------+
| ***msgA-RO-FDMCFRA***                                                 |
|                                                                       |
| This field indicates the number of msgA PRACH transmission occasions  |
| Frequency-Division Multiplexed in one time instance for the PRACH     |
| resources configured for 2-step CFRA.                                 |
+-----------------------------------------------------------------------+
| ***msgA-RO-FrequencyStart***                                          |
|                                                                       |
| This field indicates the lowest resource block of the contention      |
| based random-access resources for 2-step CBRA in the random-access    |
| procedure. The indication has the form of the offset of the lowest    |
| PRACH transmissions occasion with respect to PRB 0 in the frequency   |
| domain.                                                               |
+-----------------------------------------------------------------------+
| ***msgA-RO-FrequencyStartCFRA***                                      |
|                                                                       |
| This field indicates the lowest resource block of the contention free |
| random-access resources for the 2-step CFRA in the random-access      |
| procedure. The indication has the form of the offset of the lowest    |
| PRACH transmissions occasion with respect to PRB 0 in the frequency   |
| domain.                                                               |
+-----------------------------------------------------------------------+
| ***msgA-SCS-From-prach-ConfigurationIndex***                          |
|                                                                       |
| This field is set by the UE with the corresponding SCS as derived     |
| from the *msgA-PRACH-ConfigurationIndex* in                           |
| *RACH-ConfigGenericTwoStepRA* (see tables Table 6.3.3.1-1, Table      |
| 6.3.3.1-2, Table 6.3.3.2-2 and Table 6.3.3.2-3, TS 38.211 \[16\])     |
| when the *msgA-SubcarrierSpacing* is absent and when only 2-step      |
| random-access resources are available in the UL BWP used in the       |
| random-access procedure; otherwise, this field is absent.             |
+-----------------------------------------------------------------------+
| ***numberOfPreamblesSentOnCSI-RS***                                   |
|                                                                       |
| This field is used to indicate the total number of successive RA      |
| preambles that were transmitted on the corresponding CSI-RS.          |
+-----------------------------------------------------------------------+
| ***numberOfPreamblesSentOnSSB***                                      |
|                                                                       |
| This field is used to indicate the total number of successive RA      |
| preambles that were transmitted on the corresponding SS/PBCH block.   |
+-----------------------------------------------------------------------+
| ***onDemandSISuccess***                                               |
|                                                                       |
| This field is set to *true* when the RA report entry is included      |
| because of either msg1 based on demand SI request or msg3 based on    |
| demand SI request and if the on-demand SI request is successful.      |
| Otherwise, the field is absent.                                       |
+-----------------------------------------------------------------------+
| ***perRAAttemptInfoList***                                            |
|                                                                       |
| This field provides detailed information about a random access        |
| attempt.                                                              |
+-----------------------------------------------------------------------+
| ***perRACSI-RSInfoList***                                             |
|                                                                       |
| This field provides detailed information about the successive random  |
| access attempts associated to the same CSI-RS.                        |
+-----------------------------------------------------------------------+
| ***perRASSBInfoList***                                                |
|                                                                       |
| This field provides detailed information about the successive random  |
| access attempts associated to the same SS/PBCH block.                 |
+-----------------------------------------------------------------------+
| ***ra-InformationCommon***                                            |
|                                                                       |
| This field is used to provide information on random access attempts.  |
| This field is mandatory present.                                      |
+-----------------------------------------------------------------------+
| ***raPurpose***                                                       |
|                                                                       |
| This field is used to indicate the RA scenario for which the RA       |
| report entry is triggered. The RA accesses associated to Initial      |
| access from RRC_IDLE, RRC re-establishment procedure, transition from |
| RRC-INACTIVE. The indicator *beamFailureRecovery* is used in case of  |
| successful beam failure recovery related RA procedure in the SpCell   |
| \[3\]. The indicator *reconfigurationWithSync* is used if the UE      |
| executes a reconfiguration with sync. The indicator                   |
| *ulUnSynchronized* is used if the random access procedure is          |
| initiated in a SpCell by DL or UL data arrival during RRC_CONNECTED   |
| when the timeAlignmentTimer is not running in the PTAG or if the RA   |
| procedure is initiated in a serving cell by a PDCCH order \[3\]. The  |
| indicator *schedulingRequestFailure* is used in case of SR failures   |
| \[3\]. The indicator *noPUCCHResourceAvailable* is used when the UE   |
| has no valid SR PUCCH resources configured \[3\]. The indicator       |
| *requestForOtherSI* is used for MSG1 based on demand SI request. The  |
| indicator *msg3RequestForOtherSI* is used in case of MSG3 based SI    |
| request. The indication *lbtFailure* is used when the UE initiates    |
| RACH in SpCell due to consistent uplink LBT failures \[3\]. The field |
| can also be used for the SCG-related RA-Report when the *raPurpose*   |
| is set to *beamFailureRecovery*, *reconfigurationWithSync*,           |
| *ulUnSynchronized*, *schedulingRequestFailure*,                       |
| *noPUCCHResourceAvailable* and *lbtFailure*.                          |
+-----------------------------------------------------------------------+
| ***sdt-Failed***                                                      |
|                                                                       |
| This field is included when the RA report entry is included because   |
| of SDT and if the SDT transmission failed. Otherwise, the field is    |
| absent.                                                               |
+-----------------------------------------------------------------------+
| ***spCellID***                                                        |
|                                                                       |
| This field is used to indicate the CGI of the SpCell of the cell      |
| group associated to the SCell in which the associated random access   |
| procedure was performed. If the UE performs RA procedure on a SCell   |
| associated to the MCG, then this field is set to the CGI of the PCell |
| and if the UE performs RA procedure on a SCell associated to the SCG, |
| then this field is set to the CGI of the PSCell. If the CGI of the    |
| PSCell is not available at the UE for the RA procedure performed on a |
| SCell associated to the SCG or for the RA procedure on the PSCell,    |
| this field is set to the CGI of the PCell. Otherwise, the field is    |
| absent.                                                               |
+-----------------------------------------------------------------------+
| ***ssb-Index***                                                       |
|                                                                       |
| This field is used to indicate the SS/PBCH index of the SS/PBCH block |
| corresponding to the random access attempt.                           |
+-----------------------------------------------------------------------+
| ***ssbsForSI-Acquisition***                                           |
|                                                                       |
| This field indicates the SSB(s) (in the form of SSB index(es)) that   |
| the UE used to receive the requested SI message(s). The field is      |
| present if the purpose of the random access procedure was to request  |
| on-demand SI (i.e. if the *raPurpose* is set to *requestForOtherSI*   |
| or *msg3RequestForOtherSI*). Otherwise, the field is absent.          |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *RLF-Report* field descriptions                                       |
+=======================================================================+
| ***bwp-Info***                                                        |
|                                                                       |
| This field is used to indicate the BWP information in which the UE    |
| detected consistent uplink LBT failure. This field is set only when   |
| the detected consistent uplink LBT failure did not trigger the random |
| access procedure.                                                     |
+-----------------------------------------------------------------------+
| ***choCandidateCellList***                                            |
|                                                                       |
| This field is used to indicate the list of candidate target cells for |
| conditional handover included in *condRRCReconfig* at the time of     |
| connection failure. The field does not include the candidate target   |
| cells included in *measResultNeighCells*.                             |
+-----------------------------------------------------------------------+
| ***choCellId***                                                       |
|                                                                       |
| This field is used to indicate the candidate target cell for          |
| conditional handover included in *condRRCReconfig* that the UE        |
| selected for CHO based recovery while T311 is running.                |
+-----------------------------------------------------------------------+
| ***connectionFailureType***                                           |
|                                                                       |
| This field is used to indicate whether the connection failure is due  |
| to radio link failure or handover failure.                            |
+-----------------------------------------------------------------------+
| ***csi-rsRLMConfigBitmap,csi-rsRLMConfigBitmap-v1650***               |
|                                                                       |
| These fields are used to indicate the CSI-RS indexes configured in    |
| the RLM configurations for the active BWP when the UE declares RLF or |
| HOF. The UE first fills in the *csi-rsRLMConfigBitmap-r16* to         |
| indicate the first 96 CSI-RS indexes and then                         |
| *csi-rsRLMConfigBitmap-v1650* to indicate the latter 96 CSI-RS        |
| indexes. The first/leftmost bit in *csi-rsRLMConfigBitmap-r16*        |
| corresponds to CSI-RS index 0, the second bit corresponds to CSI-RS   |
| index 1. The first/leftmost bit in *csi-rsRLMConfigBitmap-v1650*      |
| corresponds to CSI-RS index 96, the second bit corresponds to CSI-RS  |
| index 97. These fields are included only if the                       |
| *RadioLinkMonitoringConfig* for the respective BWP is configured.     |
+-----------------------------------------------------------------------+
| ***c-RNTI***                                                          |
|                                                                       |
| This field indicates the C-RNTI used in the PCell upon detecting      |
| radio link failure or the C-RNTI used in the source PCell upon        |
| handover failure.                                                     |
+-----------------------------------------------------------------------+
| ***elapsedTimeSCG-Failure***                                          |
|                                                                       |
| This field is used to indicate the time elapsed between the SCG       |
| failure and the MCG failure. The maximum value *1023* means 1023ms or |
| longer.                                                               |
+-----------------------------------------------------------------------+
| ***elapsedTimeT316***                                                 |
|                                                                       |
| This field is used to indicate the value of the elapsed time of the   |
| timer T316. Value in milliseconds.                                    |
+-----------------------------------------------------------------------+
| ***failedPCellId***                                                   |
|                                                                       |
| This field is used to indicate the PCell in which RLF is detected or  |
| the target PCell of the failed handover. For intra-NR handover        |
| *nrFailedPCellId* is included and for the handover from NR to EUTRA   |
| *eutraFailedPCellId* is included. The UE sets the ARFCN according to  |
| the frequency band used for transmission/ reception when the failure  |
| occurred.                                                             |
+-----------------------------------------------------------------------+
| ***failedPCellId-EUTRA***                                             |
|                                                                       |
| This field is used to indicate the PCell in which RLF is detected or  |
| the source PCell of the failed handover in an E-UTRA RLF report.      |
+-----------------------------------------------------------------------+
| ***lastHO-Type***                                                     |
|                                                                       |
| This field is used to indicate the type of the last executed handover |
| before the last detected connection failure. The field is set to      |
| *cho* if the last executed handover was initiated by a conditional    |
| reconfiguration execution. The field is set to *daps* if the last     |
| executed handover was a DAPS handover.                                |
+-----------------------------------------------------------------------+
| ***mcg-RecoveryFailureCause***                                        |
|                                                                       |
| This field is used to indicate the cause of the fast MCG recovery     |
| failure.                                                              |
+-----------------------------------------------------------------------+
| ***measResultListEUTRA***                                             |
|                                                                       |
| This field refers to the last measurement results taken in the        |
| neighboring EUTRA Cells, when the radio link failure or handover      |
| failure happened.                                                     |
+-----------------------------------------------------------------------+
| ***measResultListNR***                                                |
|                                                                       |
| This field refers to the last measurement results taken in the        |
| neighboring NR Cells, when the radio link failure or handover failure |
| happened.                                                             |
+-----------------------------------------------------------------------+
| ***measResultLastServCell***                                          |
|                                                                       |
| This field refers to the log measurement results taken in the PCell   |
| upon detecting radio link failure or the source PCell upon handover   |
| failure.                                                              |
+-----------------------------------------------------------------------+
| ***measResultLastServCellRSSI***                                      |
|                                                                       |
| This field refers to the log RSSI measurement results in dBm (see TS  |
| 38.215 \[9\]) taken for the frequency of the PCell upon detecting     |
| radio link failure or source PCell upon detecting handover failure.   |
+-----------------------------------------------------------------------+
| ***measResultNeighFreqListRSSI***                                     |
|                                                                       |
| This field is used to log the RSSI measurement results in dBm (see TS |
| 38.215 \[9\]) taken for the neighbouring frequencies upon detecting   |
| radio link failure or handover failure, when UE operates in shared    |
| spectrum.                                                             |
+-----------------------------------------------------------------------+
| ***measResult-RLF-Report-EUTRA***                                     |
|                                                                       |
| Includes the E-UTRA *RLF-Report-r9* IE as specified in TS 36.331      |
| \[10\].                                                               |
+-----------------------------------------------------------------------+
| ***measResult-RLF-Report-EUTRA-v1690***                               |
|                                                                       |
| Includes the E-UTRA *RLF-Report-v9e0* IE as specified in TS 36.331    |
| \[10\].                                                               |
+-----------------------------------------------------------------------+
| ***noSuitableCellFound***                                             |
|                                                                       |
| This field is set by the UE when the T311 expires.                    |
+-----------------------------------------------------------------------+
| ***previousPCellId***                                                 |
|                                                                       |
| This field is used to indicate the source PCell of the last handover  |
| (source PCell when the last executed *RRCReconfiguration* message     |
| including *reconfigurationWithSync* was received). For intra-NR       |
| handover *nrPreviousCell* is included and for the handover from EUTRA |
| to NR *eutraPreviousCell* is included.                                |
+-----------------------------------------------------------------------+
| ***pSCellId***                                                        |
|                                                                       |
| This field is used to indicate the PSCell in which the UE failed to   |
| perform fast MCG recovery procedure or the UE successfully performed  |
| fast MCG recovery procedure.                                          |
+-----------------------------------------------------------------------+
| ***ra-InformationCommon***                                            |
|                                                                       |
| This field is optionally included when c*onnectionFailureType* is set |
| to \'hof\' and a random access procedure is triggered for the failed  |
| reconfiguration with sync, or when *connectionFailureType* is set to  |
| \'rlf\' and the *rlf-Cause* equals to \'randomAccessProblem\' or      |
| \'beamRecoveryFailure\'; otherwise this field is absent.              |
+-----------------------------------------------------------------------+
| ***reconnectCellId***                                                 |
|                                                                       |
| This field is used to indicate the cell in which the UE comes back to |
| connected after connection failure and after failing to perform       |
| reestablishment, or to indicate the suitable cell in which the UE     |
| reconnects after failure in performing *MobilityFromNRCommand* for    |
| voice fallback (without initiating re-establishment procedure). If    |
| the UE comes back to RRC CONNECTED in an NR cell then                 |
| *nrReconnectCellID* is included and if the UE comes back to RRC       |
| CONNECTED in an LTE cell then *eutraReconnectCellID* is included.     |
+-----------------------------------------------------------------------+
| ***reestablishmentCellId***                                           |
|                                                                       |
| If the UE was not configured with *conditionalReconfiguration* at the |
| time of re-establishment attempt, or if the cell selected for the     |
| re-establishment attempt is not a candidate target cell for           |
| conditional reconfiguration, this field is used to indicate the cell  |
| in which the re-establishment attempt was made after connection       |
| failure.                                                              |
+-----------------------------------------------------------------------+
| ***rlf-Cause***                                                       |
|                                                                       |
| This field is used to indicate the cause of the last radio link       |
| failure that was detected. In case of handover failure information    |
| reporting (i.e., the *connectionFailureType* is set to \'*hof*\'),    |
| the UE is allowed to set this field to any value, except for the case |
| in which a radio link failure was detected in the source PCell while  |
| performing a DAPS handover.                                           |
+-----------------------------------------------------------------------+
| ***scg-FailedAfterMCG***                                              |
|                                                                       |
| This field is set if for the SCG failure is detected after MCG        |
| failure while T316 is running.                                        |
+-----------------------------------------------------------------------+
| ***ssbRLMConfigBitmap***                                              |
|                                                                       |
| This field is used to indicate the SS/PBCH block indexes configured   |
| in the RLM configurations for the active BWP when the UE declares RLF |
| or HOF.The first/leftmost bit corresponds to SSB index 0, the second  |
| bit corresponds to SSB index 1. This field is included only if the    |
| *RadioLinkMonitoringConfig* for the respective BWP is configured.     |
+-----------------------------------------------------------------------+
| ***timeConnFailure***                                                 |
|                                                                       |
| This field is used to indicate the time elapsed since the last HO     |
| execution until connection failure. Actual value = field value \*     |
| 100ms. The maximum value 1023 means 102.3s or longer.                 |
+-----------------------------------------------------------------------+
| ***timeConnSourceDAPS-Failure***                                      |
|                                                                       |
| This field is used to indicate the time that elapsed between the last |
| DAPS handover execution and the radio link failure detected in the    |
| source cell while T304 is running. Value in milliseconds. The maximum |
| value 1023 means 1023ms or longer.                                    |
+-----------------------------------------------------------------------+
| ***timeSinceFailure***                                                |
|                                                                       |
| This field is used to indicate the time that elapsed since the        |
| connection (radio link or handover) failure. Value in seconds. The    |
| maximum value 172800 means 172800s or longer. In the case of          |
| failure(s) (either at source or at target or at both) associated to   |
| DAPS handover, this field indicates the time elapsed since the latest |
| connection (radio link or handover) failure.                          |
+-----------------------------------------------------------------------+
| *timeSinceCHO-Reconfig*                                               |
|                                                                       |
| In case of handover failure, this field is used to indicate the time  |
| elapsed between the initiation of the last handover execution towards |
| the target cell and the reception of the latest conditional           |
| reconfiguration. In case of radio link failure, this field is used to |
| indicate the time elapsed between the radio link failure and the      |
| reception of the latest conditional reconfiguration while connected   |
| to the source PCell. Actual value = field value \* 100ms. The maximum |
| value 1023 means 102.3s or longer.                                    |
+-----------------------------------------------------------------------+
| ***timeUntilReconnection***                                           |
|                                                                       |
| This field is used to indicate the time that elapsed between the      |
| connection (radio link or handover) failure and the next time the UE  |
| comes to RRC CONNECTED in an NR or EUTRA cell, after failing to       |
| perform reestablishment. Value in seconds. The maximum value 172800   |
| means 172800s or longer.                                              |
+-----------------------------------------------------------------------+
| ***voiceFallbackHO***                                                 |
|                                                                       |
| This field is set if for the failed mobility from NR, the             |
| *voiceFallbackIndication* was included in the *MobilityFromNRCommand* |
| message.                                                              |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SuccessHO-Report* field descriptions                                 |
+=======================================================================+
| ***c-RNTI***                                                          |
|                                                                       |
| This field indicates the C-RNTI assigned by the target PCell of the   |
| handover for which the successful HO report was generated.            |
+-----------------------------------------------------------------------+
| ***eutra-TargetCellInfo***                                            |
|                                                                       |
| This field is used to indicate the target EUTRA PCell and the last    |
| measurement results of the target PCell of a handover in which the    |
| successful handover triggers the *SuccessHO-Report*.                  |
+-----------------------------------------------------------------------+
| ***eutra-C-RNTI***                                                    |
|                                                                       |
| This field indicates the C-RNTI assigned by the E-UTRA target PCell   |
| of the mobility from NR command for which the successful HO report    |
| was generated.                                                        |
+-----------------------------------------------------------------------+
| ***measResultListNR***                                                |
|                                                                       |
| This field refers to the last measurement results taken in the        |
| neighboring NR Cells when a successful handover is executed.          |
+-----------------------------------------------------------------------+
| ***measResultNeighFreqListRSSI***                                     |
|                                                                       |
| This field is used to log the RSSI measurement results in dBm (see TS |
| 38.215 \[9\]) taken for the neighbouring frequencies upon successful  |
| handover execution.                                                   |
+-----------------------------------------------------------------------+
| ***measResultServCellRSSI***                                          |
|                                                                       |
| This field refers to the log RSSI measurement results in dBm (see TS  |
| 38.215 \[9\]) taken for the frequency of the source PCell upon        |
| successful handover execution.                                        |
+-----------------------------------------------------------------------+
| *rlf-InSourceDAPS*                                                    |
|                                                                       |
| This field indicates whether a radio link failure occurred at the     |
| source cell while T304 was running.                                   |
+-----------------------------------------------------------------------+
| ***shr-Cause***                                                       |
|                                                                       |
| This field is used to indicate the cause of the successful HO report. |
+-----------------------------------------------------------------------+
| ***sourceCellMeas***                                                  |
|                                                                       |
| This field refers to the last measurement results taken in the source |
| PCell of a handover in which the successful handover triggers the     |
| *SuccessHO-Report*.                                                   |
+-----------------------------------------------------------------------+
| ***sourcePCellId***                                                   |
|                                                                       |
| This field is used to indicate the source PCell of a handover in      |
| which the successful handover triggers the *SuccessHO-Report*.        |
+-----------------------------------------------------------------------+
| ***targetPCellId***                                                   |
|                                                                       |
| This field is used to indicate the target PCell of a handover in      |
| which the successful handover triggers the *SuccessHO-Report*.        |
+-----------------------------------------------------------------------+
| ***targetCellMeas***                                                  |
|                                                                       |
| This field refers to the last measurement results taken in the target |
| PCell of a handover in which the successful handover triggers the     |
| *SuccessHO-Report*.                                                   |
+-----------------------------------------------------------------------+
| ***timeSinceCHO-Reconfig***                                           |
|                                                                       |
| This field is used to indicate the time elapsed between the           |
| initiation of the last conditional reconfiguration execution towards  |
| the target cell and the reception of the latest conditional           |
| reconfiguration for this target cell. Actual value = field value \*   |
| 100ms. The maximum value 1023 means 102.3s or longer.                 |
+-----------------------------------------------------------------------+
| ***timeSinceSHR***                                                    |
|                                                                       |
| This field is used to indicate the time elapsed since the execution   |
| of the last MobilityFromNRCommand towards the target EUTRA cell.      |
| Value in seconds. The maximum value 172800 means 172800s or longer.   |
+-----------------------------------------------------------------------+
| ***upInterruptionTimeAtHO***                                          |
|                                                                       |
| This field is used to indicate the time elapsed between the time of   |
| arrival of the last PDCP PDU received from the source cell for any    |
| data radio bearer and the time of arrival of the first non-duplicate  |
| PDCP PDU received from the target cell for any data radio bearer, and |
| it is measured at the time of arrival of the first non-duplicate PDCP |
| PDU received from the target cell for any data radio bearer. The      |
| field is set only in case of DAPS handover.\                          |
| Value in milliseconds. The maximum value 1023 means 1023ms or longer. |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *FlightPathInfoReport* field descriptions                             |
+=======================================================================+
| ***timeStamp***                                                       |
|                                                                       |
| Time stamp that describes estimated time of arrival, if available, of |
| the UE at the corresponding *wayPointLocation*.                       |
+-----------------------------------------------------------------------+
| ***wayPointLocation***                                                |
|                                                                       |
| Location coordinates of the planned waypoint. Parameter type          |
| *LocationCoordinates* defined in TS 37.355 \[49\]. The first/leftmost |
| bit of the first octet contains the most significant bit.             |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SuccessPSCell-Report* field descriptions                             |
+=======================================================================+
| ***measResultListNR***                                                |
|                                                                       |
| This field refers to the last measurement results according to the    |
| initiating node configuration taken in the neighboring NR Cells when  |
| a successful PSCell change/addition is executed.                      |
+-----------------------------------------------------------------------+
| ***pCellId***                                                         |
|                                                                       |
| This field is used to indicate the PCell to which the UE was          |
| connected when the successful PSCell change or addition triggers the  |
| *SuccessPSCell-Report*.                                               |
+-----------------------------------------------------------------------+
| ***sn-InitiatedPSCellChange***                                        |
|                                                                       |
| This field indicates whether the PSCell change procedure for which    |
| the successful PSCell change report is logged is SN initiated or not. |
+-----------------------------------------------------------------------+
| ***spr-Cause***                                                       |
|                                                                       |
| This field is used to indicate the cause of the successful PSCell     |
| change or addition report.                                            |
+-----------------------------------------------------------------------+
| ***sourcePSCellId***                                                  |
|                                                                       |
| This field is used to indicate the source PSCell of a PSCell change   |
| in which the successful PSCell change triggers the                    |
| *SuccessPSCell-Report*.                                               |
+-----------------------------------------------------------------------+
| ***sourcePSCellMeas***                                                |
|                                                                       |
| This field refers to the last measurement results taken in the source |
| PSCell of a PSCell change in which the successful PSCell change       |
| triggers the *SuccessPSCell-Report*.                                  |
+-----------------------------------------------------------------------+
| ***targetPSCellId***                                                  |
|                                                                       |
| This field is used to indicate the target PSCell of a PSCell          |
| change/addition in which the successful PSCell change or addition     |
| triggers the *SuccessPSCell-Report*.                                  |
+-----------------------------------------------------------------------+
| ***targetPSCellMeas***                                                |
|                                                                       |
| This field refers to the last measurement results taken in the target |
| PSCell of a PSCell change/addition in which the successful PSCell     |
| change or addition triggers the *SuccessPSCell-Report*.               |
+-----------------------------------------------------------------------+
| ***timeSinceCPAC-Reconfig***                                          |
|                                                                       |
| This field is used to indicate the time elapsed between the           |
| initiation of the last conditional reconfiguration execution towards  |
| the target PSCell and the reception of the latest conditional         |
| reconfiguration for this target PSCell. Actual value = field value \* |
| 100ms. The maximum value 1023 means 102.3s or longer.                 |
+-----------------------------------------------------------------------+

#### -- *UEPositioningAssistanceInfo*

The *UEPositioningAssistanceInfo* message is used to provide positioning
assistance information as requested by the Network.

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*UEPositioningAssistanceInfo message*

\-- ASN1START

\-- TAG-UEPOSITIONINGASSISTANCEINFO-START

UEPositioningAssistanceInfo-r17 ::= SEQUENCE {

criticalExtensions CHOICE {

uePositioningAssistanceInfo-r17 UEPositioningAssistanceInfo-r17-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

UEPositioningAssistanceInfo-r17-IEs ::= SEQUENCE {

ue-TxTEG-AssociationList-r17 UE-TxTEG-AssociationList-r17 OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension UEPositioningAssistanceInfo-v1720-IEs OPTIONAL

}

UEPositioningAssistanceInfo-v1720-IEs::= SEQUENCE {

ue-TxTEG-TimingErrorMarginValue-r17 ENUMERATED {tc0, tc2, tc4, tc6, tc8,
tc12, tc16, tc20, tc24, tc32, tc40, tc48, tc56,

tc64, tc72, tc80} OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

UE-TxTEG-AssociationList-r17 ::= SEQUENCE (SIZE
(1..maxNrOfTxTEGReport-r17)) OF UE-TxTEG-Association-r17

UE-TxTEG-Association-r17 ::= SEQUENCE {

ue-TxTEG-ID-r17 INTEGER (0..maxNrOfTxTEG-ID-1-r17),

nr-TimeStamp-r17 NR-TimeStamp-r17,

associatedSRS-PosResourceIdList-r17 SEQUENCE
(SIZE(1..maxNrofSRS-PosResources-r16)) OF SRS-PosResourceId-r16,

servCellId-r17 ServCellIndex OPTIONAL

}

NR-TimeStamp-r17 ::= SEQUENCE {

nr-SFN-r17 INTEGER (0..1023),

nr-Slot-r17 CHOICE {

scs15-r17 INTEGER (0..9),

scs30-r17 INTEGER (0..19),

scs60-r17 INTEGER (0..39),

scs120-r17 INTEGER (0..79)

},

\...

}

\-- TAG-UEPOSITIONINGASSISTANCEINFO-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UEPositioningAssistanceInfo* field descriptions                      |
+=======================================================================+
| ***associatedSRS-PosResourceIdList***                                 |
|                                                                       |
| This field indicates list of SRS for Positioning Resources which are  |
| associated to the *ue-TxTEG-ID*.                                      |
+-----------------------------------------------------------------------+
| ***nr-TimeStamp***                                                    |
|                                                                       |
| This field specifies the latest time instance at which the            |
| association is valid prior to the reporting.                          |
+-----------------------------------------------------------------------+
| ***servCellID***                                                      |
|                                                                       |
| This field indicates the serving cell information of SRS for          |
| positioning resources associated to the UE Tx TEG report.             |
+-----------------------------------------------------------------------+
| ***ue-TxTEG-ID***                                                     |
|                                                                       |
| Identifies the ID of UE Tx TEG.                                       |
+-----------------------------------------------------------------------+
| ***ue-TxTEG-TimingErrorMarginValue***                                 |
|                                                                       |
| This field specifies the UE Tx TEG timing error margin value of all   |
| the UE Tx TEGs within one *UEPositioningAssistanceInfo*. Value *tc0*  |
| corresponds to 0 Tc, *tc2* corresponds to 2 Tc and so on (see TS      |
| 37.355 \[49\]).                                                       |
+-----------------------------------------------------------------------+

#### -- *ULDedicatedMessageSegment*

The *ULDedicatedMessageSegment* message is used to transfer segments of
the *UECapabilityInformation* or *MeasurementReportAppLayer* message.
SRB1 is used at transfer of segments of *UECapabilityInformation* and
SRB4 or SRB5 is used at transfer of segments of
*MeasurementReportAppLayer*.

Signalling radio bearer: SRB1, SRB4 or SRB5

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*ULDedicatedMessageSegment message*

\-- ASN1START

\-- TAG-ULDEDICATEDMESSAGESEGMENT-START

ULDedicatedMessageSegment-r16 ::= SEQUENCE {

criticalExtensions CHOICE {

ulDedicatedMessageSegment-r16 ULDedicatedMessageSegment-r16-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

ULDedicatedMessageSegment-r16-IEs ::= SEQUENCE {

segmentNumber-r16 INTEGER (0..15),

rrc-MessageSegmentContainer-r16 OCTET STRING,

rrc-MessageSegmentType-r16 ENUMERATED {notLastSegment, lastSegment},

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-ULDEDICATEDMESSAGESEGMENT-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *ULDedicatedMessageSegment* field descriptions                        |
+=======================================================================+
| ***segmentNumber***                                                   |
|                                                                       |
| Identifies the sequence number of a segment within the encoded UL     |
| DCCH message.                                                         |
+-----------------------------------------------------------------------+
| ***rrc-MessageSegmentContainer***                                     |
|                                                                       |
| Includes a segment of the encoded UL DCCH message. The size of the    |
| included segment in this container should be small enough that the    |
| resulting encoded RRC message PDU is less than or equal to the PDCP   |
| SDU size limit.                                                       |
+-----------------------------------------------------------------------+
| ***rrc-MessageSegmentType***                                          |
|                                                                       |
| Indicates whether the included UL DCCH message segment is the last    |
| segment or not.                                                       |
+-----------------------------------------------------------------------+

#### -- *ULInformationTransfer*

The *ULInformationTransfer* message is used for the uplink transfer of
NAS or non-3GPP dedicated information, or IAB-DU specific F1-C related
information.

Signalling radio bearer: SRB2 or SRB1 (only if SRB2 not established
yet). If SRB2 is suspended, the UE does not send this message until SRB2
is resumed. If only *dedicatedInfoF1c* is included, SRB2 is used.

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to network

*ULInformationTransfer message*

\-- ASN1START

\-- TAG-ULINFORMATIONTRANSFER-START

ULInformationTransfer ::= SEQUENCE {

criticalExtensions CHOICE {

ulInformationTransfer ULInformationTransfer-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

ULInformationTransfer-IEs ::= SEQUENCE {

dedicatedNAS-Message DedicatedNAS-Message OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension ULInformationTransfer-v1700-IEs OPTIONAL

}

ULInformationTransfer-v1700-IEs ::= SEQUENCE {

dedicatedInfoF1c-r17 DedicatedInfoF1c-r17 OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-ULINFORMATIONTRANSFER-STOP

\-- ASN1STOP

#### -- *ULInformationTransferIRAT*

The *ULInformationTransferIRAT* message is used for the uplink transfer
of information terminated at NR MCG but specified by another RAT. In
this version of the specification, the message is used for V2X sidelink
communication messages specified in TS 36.331 \[10\].

Signalling radio bearer: SRB1

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to network

*ULInformationTransferIRAT* message

\-- ASN1START

\-- TAG-ULINFORMATIONTRANSFERIRAT-START

ULInformationTransferIRAT-r16 ::= SEQUENCE {

criticalExtensions CHOICE {

c1 CHOICE {

ulInformationTransferIRAT-r16 ULInformationTransferIRAT-r16-IEs,

spare3 NULL, spare2 NULL, spare1 NULL

},

criticalExtensionsFuture SEQUENCE {}

}

}

ULInformationTransferIRAT-r16-IEs ::= SEQUENCE {

ul-DCCH-MessageEUTRA-r16 OCTET STRING OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-ULINFORMATIONTRANSFERIRAT-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *ULInformationTransferIRAT* field descriptions                        |
+=======================================================================+
| ***ul-DCCH-MessageEUTRA***                                            |
|                                                                       |
| Includes the *UL-DCCH-Message* as defined in TS 36.331 \[10\]. In     |
| this version of the specification, the field is only used to transfer |
| the E-UTRA RRC *MeasurementReport*, E-UTRA RRC                        |
| *SidelinkUEInformation* and the E-UTRA RRC *UEAssistanceInformation   |
| messages*.                                                            |
+-----------------------------------------------------------------------+

#### *-- ULInformationTransferMRDC*

The *ULInformationTransferMRDC* message is used for the uplink transfer
of MR-DC dedicated information (e.g. for transferring the NR or E-UTRA
RRC *MeasurementReport* message, the *FailureInformation* message, the
*UEAssistanceInformation* message, the *RRCReconfigurationComplete*
message, the *IABOtherInformation* message or the NR or E-UTRA RRC
*MCGFailureInformation* message).

Signalling radio bearer: SRB1, SRB3

RLC-SAP: AM

Logical channel: DCCH

Direction: UE to Network

*ULInformationTransferMRDC message*

\-- ASN1START

\-- TAG-ULINFORMATIONTRANSFERMRDC-START

ULInformationTransferMRDC ::= SEQUENCE {

criticalExtensions CHOICE {

c1 CHOICE {

ulInformationTransferMRDC ULInformationTransferMRDC-IEs,

spare3 NULL, spare2 NULL, spare1 NULL

},

criticalExtensionsFuture SEQUENCE {}

}

}

ULInformationTransferMRDC-IEs::= SEQUENCE {

ul-DCCH-MessageNR OCTET STRING OPTIONAL,

ul-DCCH-MessageEUTRA OCTET STRING OPTIONAL,

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-ULINFORMATIONTRANSFERMRDC-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *ULInformationTransferMRDC* field descriptions                        |
+=======================================================================+
| ***ul-DCCH-MessageNR***                                               |
|                                                                       |
| Includes the *UL-DCCH-Message*. In this version of the specification, |
| the field is only used to transfer the NR RRC *MeasurementReport*,    |
| *RRCReconfigurationComplete, UEAssistanceInformation,*                |
| *FailureInformation*, and *IABOtherInformation* messages when sent    |
| via SRB1 and to transfer the NR *MCGFailureInformation* message when  |
| sent via SRB3.                                                        |
+-----------------------------------------------------------------------+
| ***ul-DCCH-MessageEUTRA***                                            |
|                                                                       |
| Includes the *UL-DCCH-Message*. In this version of the specification, |
| the field is only used to transfer the E-UTRA RRC *MeasurementReport* |
| message when sent via SRB1 and to transfer the E-UTRA                 |
| *MCGFailureInformation* message when sent via SRB3.                   |
+-----------------------------------------------------------------------+