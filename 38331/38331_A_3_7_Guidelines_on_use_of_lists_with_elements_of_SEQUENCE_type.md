## A.3.7 Guidelines on use of lists with elements of SEQUENCE type

Where an information element has the form of a list (the SEQUENCE OF
construct in ASN.1) with the type of the list elements being a SEQUENCE
data type, an information element shall be defined for the list elements
even if it would not otherwise be needed.

For example, a list of PLMN identities with reservation flags is defined
as in the following example:

\-- /example/ ASN1START

PLMN-IdentityInfoList ::= SEQUENCE (SIZE (1..6)) OF PLMN-IdentityInfo

PLMN-IdentityInfo ::= SEQUENCE {

plmn-Identity PLMN-Identity,

cellReservedForOperatorUse ENUMERATED {reserved, notReserved}

}

\-- ASN1STOP

rather than as in the following (bad) example, which may cause generated
code to contain types with unpredictable names:

\-- /bad example/ ASN1START

PLMN-IdentityList ::= SEQUENCE (SIZE (1..6)) OF SEQUENCE {

plmn-Identity PLMN-Identity,

cellReservedForOperatorUse ENUMERATED {reserved, notReserved}

}

\-- ASN1STOP