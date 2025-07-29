### A.3.1.3 Text references using ASN.1 identifiers

A text reference into the RRC PDU contents description from other parts
of the specification is made using the ASN.1 field identifier of the
referenced type. The ASN.1 field and type identifiers used in text
references should be in the *italic font style*. The \"do not check
spelling and grammar\" attribute in Word should be set. Quotation marks
(i.e., \"\") should not be used around the ASN.1 field or type
identifier.

A reference to an RRC PDU should be made using the corresponding ASN.1
field identifier followed by the word \"message\", e.g., a reference to
the *RRCRelease* message.

A reference to a specific part of an RRC PDU, or to a specific part of
any other ASN.1 type, should be made using the corresponding ASN.1 field
identifier followed by the word \"field\", e.g., a reference to the
*prioritisedBitRate* field in the example below.

\-- /example/ ASN1START

LogicalChannelConfig ::= SEQUENCE {

ul-SpecificParameters SEQUENCE {

priority Priority,

prioritisedBitRate PrioritisedBitRate,

bucketSizeDuration BucketSizeDuration,

logicalChannelGroup INTEGER (0..3)

} OPTIONAL

}

\-- ASN1STOP

NOTE: All the ASN.1 start tags in the ASN.1 clauses, used as examples in
this annex to the specification, are deliberately distorted, in order
not to include them when the ASN.1 description of the RRC PDU contents
is extracted from the specification.

A reference to a specific type of information element should be made
using the corresponding ASN.1 type identifier preceded by the acronym
\"IE\", e.g., a reference to the IE *LogicalChannelConfig* in the
example above.

References to a specific type of information element should only be used
when those are generic, i.e., without regard to the particular context
wherein the specific type of information element is used. If the
reference is related to a particular context, e.g., an RRC PDU type
(message) wherein the information element is used, the corresponding
field identifier in that context should be used in the text reference.

A reference to a specific value of an ASN.1 field should be made using
the corresponding ASN.1 value without using quotation marks around the
ASN.1 value, e.g., \'if the *status* field is set to value *true*\'.