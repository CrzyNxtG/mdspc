## A.4.2 Critical extension of messages and fields

The mechanisms to critically extend a message are defined in A.3.3.
There are both \"outer branch\" and \"inner branch\" mechanisms
available. The \"outer branch\" consists of a CHOICE having the name
*criticalExtensions*, with two values, *c1* and
*criticalExtensionsFuture*. The *criticalExtensionsFuture* branch
consists of an empty SEQUENCE, while the c1 branch contains the \"inner
branch\" mechanism.

The \"inner branch\" structure is a CHOICE with values of the form
\"*MessageName-rX-IEs*\" (e.g.,
\"*RRCConnectionReconfiguration-r8-IEs*\") or \"*spareX*\", with the
spare values having type NULL. The \"-rX-IEs\" structures contain the
*complete* structure of the message IEs for the appropriate release;
i.e., the critical extension branch for the Rel-10 version of a message
includes all Rel-8 and Rel-9 fields (that are not obviated in the later
version), rather than containing only the additional Rel-10 fields.

The following guidelines may be used when deciding which mechanism to
introduce for a particular message, i.e. only an \'outer branch\', or an
\'outer branch\' in combination with an \'inner branch\' including a
certain number of spares:

\- For certain messages, e.g. initial uplink messages, messages
transmitted on a broadcast channel, critical extension may not be
applicable.

\- An outer branch may be sufficient for messages not including any
fields.

\- The number of spares within inner branch should reflect the
likelihood that the message will be critically extended in future
releases (since each release with a critical extension for the message
consumes one of the spare values). The estimation of the critical
extension likelihood may be based on the number, size and changeability
of the fields included in the message.

\- In messages where an inner branch extension mechanism is available,
all spare values of the inner branch should be used before any critical
extensions are added using the outer branch.

The following example illustrates the use of the critical extension
mechanism by showing the ASN.1 of the original and of a later release

\-- /example/ ASN1START \-- Original release

RRCMessage ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

c1 CHOICE{

rrcMessage-r8 RRCMessage-r8-IEs,

spare3 NULL, spare2 NULL, spare1 NULL

},

criticalExtensionsFuture SEQUENCE {}

}

}

\-- ASN1STOP

\-- /example/ ASN1START \-- Later release

RRCMessage ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

c1 CHOICE{

rrcMessage-r8 RRCMessage-r8-IEs,

rrcMessage-r10 RRCMessage-r10-IEs,

rrcMessage-r11 RRCMessage-r11-IEs,

rrcMessage-r14 RRCMessage-r14-IEs

},

later CHOICE {

c2 CHOICE{

rrcMessage-r16 RRCMessage-r16-IEs,

spare7 NULL, spare6 NULL, spare5 NULL, spare4 NULL,

spare3 NULL, spare2 NULL, spare1 NULL

},

criticalExtensionsFuture SEQUENCE {}

}

}

}

\-- ASN1STOP

It is important to note that critical extensions may also be used at the
level of individual fields i.e. a field may be replaced by a critically
extended version. When sending the extended version, the original
version may also be included (e.g. original field is mandatory, E-UTRAN
is unaware if UE supports the extended version). In such cases, a UE
supporting both versions may be required to ignore the original field.
The following example illustrates the use of the critical extension
mechanism by showing the ASN.1 of the original and of a later release.

\-- /example/ ASN1START \-- Original release

RRCMessage ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

c1 CHOICE{

rrcMessage-r8 RRCMessage-r8-IEs,

spare3 NULL, spare2 NULL, spare1 NULL

},

criticalExtensionsFuture SEQUENCE {}

}

}

RRCMessage-rN-IEs ::= SEQUENCE {

field1-rN ENUMERATED {

value1, value2, value3, value4} OPTIONAL, \-- Need N

field2-rN InformationElement2-rN OPTIONAL, \-- Need N

nonCriticalExtension RRCConnectionReconfiguration-vMxy-IEs OPTIONAL

}

RRCConnectionReconfiguration-vMxy-IEs ::= SEQUENCE {

field2-rM InformationElement2-rM OPTIONAL, \-- Cond NoField2rN

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- ASN1STOP

  --------------------------------------------------------------------------
  Conditional    Explanation
  presence       
  -------------- -----------------------------------------------------------
  *NoField2rN*   The field is optionally present, need N, if field2-rN is
                 absent. Otherwise the field is absent

  --------------------------------------------------------------------------

Finally, it is noted that a critical extension may be introduced in the
same release as the one in which the original field was introduced e.g.
to correct an essential ASN.1 error. In such cases a UE capability may
be introduced, to assist the network in deciding whether or not to use
the critical extension.

In the case of list fields (SEQUENCE OF types in ASN.1) using the
ToAddMod/ToRelease construction, the use of critical extensions to
increase the size of a list should be avoided; that is, replacing the
original list field by a new field also used to signal entries
previously covered by the original field (i.e. extensions done according
to the following example) should be avoided:

\-- /example/ ASN1START \-- Discouraged example

ContainingStructure ::= SEQUENCE {

listElementToAddModList SEQUENCE (SIZE (1..maxNrofListElements)) OF
ListElement OPTIONAL, \-- Need N

\...,

\[\[

listElementToAddModList-rN SEQUENCE (SIZE (1..maxNrofListElements-rN))
OF ListElement OPTIONAL \-- Need N

\]\]

}\-- ASN1STOP

Instead, a non-critical list extension mechanism should typically be
used, such that the extension field only adds the new entries of the
list. This approach is further described in clause A.4.3.6.

If the critical extension mechanism for a list is used, it should be
clarified in the field description that the two versions of the list are
not configured together, and that the network should release the
contents of the original version when configuring the replacement
version.