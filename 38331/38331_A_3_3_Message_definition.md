## A.3.3 Message definition

Each PDU (message) type is specified in an ASN.1 clause similar to the
one shown in the example below.

\-- /example/ ASN1START

RRCConnectionReconfiguration ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

c1 CHOICE{

rrcConnectionReconfiguration-r8 RRCConnectionReconfiguration-r8-IEs,

spare3 NULL, spare2 NULL, spare1 NULL

},

criticalExtensionsFuture SEQUENCE {}

}

}

RRCConnectionReconfiguration-r8-IEs ::= SEQUENCE {

\-- Enter the IEs here.

\...

}

\-- ASN1STOP

Hooks for *critical* and *non-critical* extension should normally be
included in the PDU type specification. How these hooks are used is
further described in clause A.4.

Critical extensions are characterised by a redefinition of the PDU
contents and need to be governed by a mechanism for protocol version
agreement between the encoder and the decoder of the PDU, such that the
encoder is prevented from sending a critically extended version of the
PDU type, which is not comprehended by the decoder.

Critical extension of a PDU type is facilitated by a two-level CHOICE
structure, where the alternative PDU contents are alternatives within
the inner level *c1* CHOICE. Spare alternatives (i.e., *spare3* down to
*spare1* in this case) may be included within the *c1* CHOICE. The
number of spare alternatives to be included in the original PDU
specification should be decided case by case, based on the expected rate
of critical extension in the future releases of the protocol.

Further critical extension, when the spare alternatives from the
original specifications are used up, is facilitated using the
*criticalExtensionsFuture* in the outer level CHOICE.

In PDU types where critical extension is not expected in the future
releases of the protocol, the inner level *c1* CHOICE and the spare
alternatives may be excluded, as shown in the example below.

\-- /example/ ASN1START

RRCConnectionReconfigurationComplete ::= SEQUENCE {

rrc-TransactionIdentifier RRC-TransactionIdentifier,

criticalExtensions CHOICE {

rrcConnectionReconfigurationComplete-r8

RRCConnectionReconfigurationComplete-r8-IEs,

criticalExtensionsFuture SEQUENCE {}

}

}

RRCConnectionReconfigurationComplete-r8-IEs ::= SEQUENCE {

\-- Enter the fields here.

\...

}

\-- ASN1STOP

Non-critical extensions are characterised by the addition of new
information to the original specification of the PDU type. If not
comprehended, a non-critical extension may be skipped by the decoder,
whilst the decoder is still able to complete the decoding of the
comprehended parts of the PDU contents.

Non-critical extensions at locations other than the end of the message
or other than at the end of a field contained in a BIT or OCTET STRING
are facilitated by use of the ASN.1 extension marker \"\...\". The
original specification of a PDU type should normally include the
extension marker at the end of the sequence of information elements
contained.

Non-critical extensions at the end of the message or at the end of a
field that is contained in a BIT or OCTET STRING may be facilitated by
use of an empty sequence that is marked OPTIONAL e.g. as shown in the
following example:

\-- /example/ ASN1START

RRCMessage-r8-IEs ::= SEQUENCE {

field1 InformationElement1,

field2 InformationElement2,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- ASN1STOP

The ASN.1 clause specifying the contents of a PDU type may be followed
by a *field description* table where a further description of, e.g., the
semantic properties of the fields may be included. The general format of
this table is shown in the example below. The field description table is
absent in case there are no fields for which further description needs
to be provided e.g. because the PDU does not include any fields, or
because an IE is defined for each field while there is nothing specific
regarding the use of this IE that needs to be specified.

+-----------------------------------------------------------------------+
| *%PDU-TypeIdentifier%* field descriptions                             |
+=======================================================================+
| ***%field identifier%***                                              |
|                                                                       |
| Field description.                                                    |
+-----------------------------------------------------------------------+
| ***%field identifier%***                                              |
|                                                                       |
| Field description.                                                    |
+-----------------------------------------------------------------------+

The field description table has one column. The header row shall contain
the ASN.1 type identifier of the PDU type.

The following rows are used to provide field descriptions. Each row
shall include a first paragraph with a *field identifier* (in ***bold
and italic*** font style) referring to the part of the PDU to which it
applies. The following paragraphs at the same row may include (in
regular font style), e.g., semantic description, references to other
specifications and/or specification of value units, which are relevant
for the particular part of the PDU.

The parts of the PDU contents that do not require a field description
shall be omitted from the field description table.