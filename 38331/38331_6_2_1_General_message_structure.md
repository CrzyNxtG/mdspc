### 6.2.1 General message structure

#### *-- NR-RRC-Definitions*

This ASN.1 segment is the start of the NR RRC PDU definitions.

\-- ASN1START

\-- TAG-NR-RRC-DEFINITIONS-START

NR-RRC-Definitions DEFINITIONS AUTOMATIC TAGS ::=

BEGIN

\-- TAG-NR-RRC-DEFINITIONS-STOP

\-- ASN1STOP

#### *-- BCCH-BCH-Message*

The *BCCH-BCH-Message* class is the set of RRC messages that may be sent
from the network to the UE via BCH on the BCCH logical channel.

\-- ASN1START

\-- TAG-BCCH-BCH-MESSAGE-START

BCCH-BCH-Message ::= SEQUENCE {

message BCCH-BCH-MessageType

}

BCCH-BCH-MessageType ::= CHOICE {

mib MIB,

messageClassExtension SEQUENCE {}

}

\-- TAG-BCCH-BCH-MESSAGE-STOP

\-- ASN1STOP

#### *-- BCCH-DL-SCH-Message*

The *BCCH-DL-SCH-Message* class is the set of RRC messages that may be
sent from the network to the UE via DL-SCH on the BCCH logical channel.

\-- ASN1START

\-- TAG-BCCH-DL-SCH-MESSAGE-START

BCCH-DL-SCH-Message ::= SEQUENCE {

message BCCH-DL-SCH-MessageType

}

BCCH-DL-SCH-MessageType ::= CHOICE {

c1 CHOICE {

systemInformation SystemInformation,

systemInformationBlockType1 SIB1

},

messageClassExtension SEQUENCE {}

}

\-- TAG-BCCH-DL-SCH-MESSAGE-STOP

\-- ASN1STOP

#### -- *DL-CCCH-Message*

The *DL-CCCH-Message* class is the set of RRC messages that may be sent
from the Network to the UE on the downlink CCCH logical channel.

\-- ASN1START

\-- TAG-DL-CCCH-MESSAGE-START

DL-CCCH-Message ::= SEQUENCE {

message DL-CCCH-MessageType

}

DL-CCCH-MessageType ::= CHOICE {

c1 CHOICE {

rrcReject RRCReject,

rrcSetup RRCSetup,

spare2 NULL,

spare1 NULL

},

messageClassExtension SEQUENCE {}

}

\-- TAG-DL-CCCH-MESSAGE-STOP

\-- ASN1STOP

#### *-- DL-DCCH-Message*

The *DL-DCCH-Message* class is the set of RRC messages that may be sent
from the network to the UE on the downlink DCCH logical channel.

\-- ASN1START

\-- TAG-DL-DCCH-MESSAGE-START

DL-DCCH-Message ::= SEQUENCE {

message DL-DCCH-MessageType

}

DL-DCCH-MessageType ::= CHOICE {

c1 CHOICE {

rrcReconfiguration RRCReconfiguration,

rrcResume RRCResume,

rrcRelease RRCRelease,

rrcReestablishment RRCReestablishment,

securityModeCommand SecurityModeCommand,

dlInformationTransfer DLInformationTransfer,

ueCapabilityEnquiry UECapabilityEnquiry,

counterCheck CounterCheck,

mobilityFromNRCommand MobilityFromNRCommand,

dlDedicatedMessageSegment-r16 DLDedicatedMessageSegment-r16,

ueInformationRequest-r16 UEInformationRequest-r16,

dlInformationTransferMRDC-r16 DLInformationTransferMRDC-r16,

loggedMeasurementConfiguration-r16 LoggedMeasurementConfiguration-r16,

spare3 NULL, spare2 NULL, spare1 NULL

},

messageClassExtension SEQUENCE {}

}

\-- TAG-DL-DCCH-MESSAGE-STOP

\-- ASN1STOP

#### *-- MCCH-Message*

The *MCCH-Message* class is the set of RRC messages that may be sent
from the network to the UE on the MCCH logical channel.

\-- ASN1START

\-- TAG-MCCH-MESSAGE-START

MCCH-Message-r17 ::= SEQUENCE {

message MCCH-MessageType-r17

}

MCCH-MessageType-r17 ::= CHOICE {

c1 CHOICE {

mbsBroadcastConfiguration-r17 MBSBroadcastConfiguration-r17,

spare1 NULL

},

messageClassExtension SEQUENCE {}

}

\-- TAG-MCCH-MESSAGE-STOP

\-- ASN1STOP

#### *-- MulticastMCCH-Message*

The *MulticastMCCH-Message* class is the set of RRC messages that may be
sent from the network to the UE on the multicast MCCH logical channel.

\-- ASN1START

\-- TAG-MULTICASTMCCH-MESSAGE-START

MulticastMCCH-Message-r18 ::= SEQUENCE {

message MulticastMCCH-MessageType-r18

}

MulticastMCCH-MessageType-r18 ::= CHOICE {

c1 CHOICE {

mbsMulticastConfiguration-r18 MBSMulticastConfiguration-r18,

spare1 NULL

},

messageClassExtension SEQUENCE {}

}

\-- TAG-MULTICASTMCCH-MESSAGE-STOP

\-- ASN1STOP

#### *-- PCCH-Message*

The *PCCH-Message* class is the set of RRC messages that may be sent
from the Network to the UE on the PCCH logical channel.

\-- ASN1START

\-- TAG-PCCH-PCH-MESSAGE-START

PCCH-Message ::= SEQUENCE {

message PCCH-MessageType

}

PCCH-MessageType ::= CHOICE {

c1 CHOICE {

paging Paging,

spare1 NULL

},

messageClassExtension SEQUENCE {}

}

\-- TAG-PCCH-PCH-MESSAGE-STOP

\-- ASN1STOP

#### -- *UL-CCCH-Message*

The *UL-CCCH-Message* class is the set of 48-bits RRC messages that may
be sent from the UE to the Network on the uplink CCCH logical channel.

\-- ASN1START

\-- TAG-UL-CCCH-MESSAGE-START

UL-CCCH-Message ::= SEQUENCE {

message UL-CCCH-MessageType

}

UL-CCCH-MessageType ::= CHOICE {

c1 CHOICE {

rrcSetupRequest RRCSetupRequest,

rrcResumeRequest RRCResumeRequest,

rrcReestablishmentRequest RRCReestablishmentRequest,

rrcSystemInfoRequest RRCSystemInfoRequest

},

messageClassExtension SEQUENCE {}

}

\-- TAG-UL-CCCH-MESSAGE-STOP

\-- ASN1STOP

#### *-- UL-CCCH1-Message*

The *UL-CCCH1-Message* class is the set of 64-bits RRC messages that may
be sent from the UE to the Network on the uplink CCCH1 logical channel.

\-- ASN1START

\-- TAG-UL-CCCH1-MESSAGE-START

UL-CCCH1-Message ::= SEQUENCE {

message UL-CCCH1-MessageType

}

UL-CCCH1-MessageType ::= CHOICE {

c1 CHOICE {

rrcResumeRequest1 RRCResumeRequest1,

spare3 NULL,

spare2 NULL,

spare1 NULL

},

messageClassExtension SEQUENCE {}

}

\-- TAG-UL-CCCH1-MESSAGE-STOP

\-- ASN1STOP

#### *-- UL-DCCH-Message*

The *UL-DCCH-Message* class is the set of RRC messages that may be sent
from the UE to the network on the uplink DCCH logical channel.

\-- ASN1START

\-- TAG-UL-DCCH-MESSAGE-START

UL-DCCH-Message ::= SEQUENCE {

message UL-DCCH-MessageType

}

UL-DCCH-MessageType ::= CHOICE {

c1 CHOICE {

measurementReport MeasurementReport,

rrcReconfigurationComplete RRCReconfigurationComplete,

rrcSetupComplete RRCSetupComplete,

rrcReestablishmentComplete RRCReestablishmentComplete,

rrcResumeComplete RRCResumeComplete,

securityModeComplete SecurityModeComplete,

securityModeFailure SecurityModeFailure,

ulInformationTransfer ULInformationTransfer,

locationMeasurementIndication LocationMeasurementIndication,

ueCapabilityInformation UECapabilityInformation,

counterCheckResponse CounterCheckResponse,

ueAssistanceInformation UEAssistanceInformation,

failureInformation FailureInformation,

ulInformationTransferMRDC ULInformationTransferMRDC,

scgFailureInformation SCGFailureInformation,

scgFailureInformationEUTRA SCGFailureInformationEUTRA

},

messageClassExtension CHOICE {

c2 CHOICE {

ulDedicatedMessageSegment-r16 ULDedicatedMessageSegment-r16,

dedicatedSIBRequest-r16 DedicatedSIBRequest-r16,

mcgFailureInformation-r16 MCGFailureInformation-r16,

ueInformationResponse-r16 UEInformationResponse-r16,

sidelinkUEInformationNR-r16 SidelinkUEInformationNR-r16,

ulInformationTransferIRAT-r16 ULInformationTransferIRAT-r16,

iabOtherInformation-r16 IABOtherInformation-r16,

mbsInterestIndication-r17 MBSInterestIndication-r17,

uePositioningAssistanceInfo-r17 UEPositioningAssistanceInfo-r17,

measurementReportAppLayer-r17 MeasurementReportAppLayer-r17,

indirectPathFailureInformation-r18 IndirectPathFailureInformation-r18,
spare5 NULL, spare4 NULL, spare3 NULL, spare2 NULL, spare1 NULL

},

messageClassExtensionFuture-r16 SEQUENCE {}

}

}

\-- TAG-UL-DCCH-MESSAGE-STOP

\-- ASN1STOP