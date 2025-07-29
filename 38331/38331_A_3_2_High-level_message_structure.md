## A.3.2 High-level message structure

Within each logical channel type, the associated RRC PDU (message) types
are alternatives within a CHOICE, as shown in the example below.

\-- /example/ ASN1START

DL-DCCH-Message ::= SEQUENCE {

message DL-DCCH-MessageType

}

DL-DCCH-MessageType ::= CHOICE {

c1 CHOICE {

dlInformationTransfer DLInformationTransfer,

handoverFromEUTRAPreparationRequest HandoverFromEUTRAPreparationRequest,

mobilityFromEUTRACommand MobilityFromEUTRACommand,

rrcConnectionReconfiguration RRCConnectionReconfiguration,

rrcConnectionRelease RRCConnectionRelease,

securityModeCommand SecurityModeCommand,

ueCapabilityEnquiry UECapabilityEnquiry,

spare1 NULL

},

messageClassExtension SEQUENCE {}

}

\-- ASN1STOP

A nested two-level CHOICE structure is used, where the alternative PDU
types are alternatives within the inner level *c1* CHOICE.

Spare alternatives (i.e., *spare1* in this case) may be included within
the *c1* CHOICE to facilitate future extension. The number of such spare
alternatives should not extend the total number of alternatives beyond
an integer-power-of-two number of alternatives (i.e., eight in this
case).

Further extension of the number of alternative PDU types is facilitated
using the *messageClassExtension* alternative in the outer level CHOICE.