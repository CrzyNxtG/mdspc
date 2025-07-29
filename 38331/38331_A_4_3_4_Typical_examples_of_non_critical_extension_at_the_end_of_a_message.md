### A.4.3.4 Typical examples of non critical extension at the end of a message

The following example illustrates the use of non-critical extensions at
the end of the message or at the end of a field that is contained in a
BIT or OCTET STRING i.e. when an empty sequence is used.

\-- /example/ ASN1START

RRCMessage-r8-IEs ::= SEQUENCE {

field1 InformationElement1,

field2 InformationElement2,

field3 InformationElement3 OPTIONAL, \-- Need N

nonCriticalExtension RRCMessage-v860-IEs OPTIONAL

}

RRCMessage-v860-IEs ::= SEQUENCE {

field4-v860 InformationElement4 OPTIONAL, \-- Need S

field5-v860 BOOLEAN OPTIONAL, \-- Cond C54

nonCriticalExtension RRCMessage-v940-IEs OPTIONAL

}

RRCMessage-v940-IEs ::= SEQUENCE {

field6-v940 InformationElement6-r9 OPTIONAL, \-- Need R

nonCriticalExtensions SEQUENCE {} OPTIONAL

}

\-- ASN1STOP

Some remarks regarding the extensions shown in the above example:

-- The *InformationElement4* is introduced in the original version of
the protocol (release 8) and hence no suffix is used.