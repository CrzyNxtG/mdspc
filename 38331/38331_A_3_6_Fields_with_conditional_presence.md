## A.3.6 Fields with conditional presence

A field with conditional presence is declared with the keyword OPTIONAL.
In addition, a short comment text shall be included at the end of the
paragraph including the keyword OPTIONAL. The comment text includes the
keyword \"Cond\", followed by a condition tag associated with the field
(\"UL\" in this example):

\-- /example/ ASN1START

LogicalChannelConfig ::= SEQUENCE {

ul-SpecificParameters SEQUENCE {

priority INTEGER (0),

\...

} OPTIONAL \-- Cond UL

}

\-- ASN1STOP

When conditionally present fields are included in an ASN.1 clause, the
field description table after the ASN.1 clause shall be followed by a
*conditional presence* table. The conditional presence table specifies
the conditions for including the fields with conditional presence in the
particular ASN.1 clause.

  -------------------------------------------------------------------------
  Conditional   Explanation
  presence      
  ------------- -----------------------------------------------------------
  UL            Specification of the conditions for including the field
                associated with the condition tag = \"UL\". Semantics in
                case of optional presence under certain conditions may also
                be specified.

  -------------------------------------------------------------------------

The conditional presence table has two columns. The first column
(heading: \"Conditional presence\") contains the condition tag (in
*italic* font style), which links the fields with a condition tag in the
ASN.1 clause to an entry in the table. The second column (heading:
\"Explanation\") contains a text specification of the conditions and
requirements for the presence of the field. The second column may also
include semantics, in case of an optional presence of the field, under
certain conditions i.e. using the same predefined tags as defined for
optional fields in A.3.5.

Conditional presence should primarily be used when presence of a field
depends on the presence and/or value of other fields within the same
message. If the presence of a field depends on whether another
feature/function has been configured, while this function can be
configured independently e.g. by another message and/or at another point
in time, the relation is best reflected by means of a statement in the
field description table.

If the ASN.1 clause does not include any fields with conditional
presence, the conditional presence table shall not be included.

Whenever a field is only applicable in specific cases e.g. TDD, use of
conditional presence should be considered.