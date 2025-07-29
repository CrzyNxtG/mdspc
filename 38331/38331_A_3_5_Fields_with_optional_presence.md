## A.3.5 Fields with optional presence

A field with optional presence may be declared with the keyword DEFAULT.
It identifies a default value to be assumed, if the sender does not
include a value for that field in the encoding:

\-- /example/ ASN1START

PreambleInfo ::= SEQUENCE {

numberOfRA-Preambles INTEGER (1..64) DEFAULT 1,

\...

}

\-- ASN1STOP

Alternatively, a field with optional presence may be declared with the
keyword OPTIONAL. It identifies a field for which a value can be
omitted. The omission carries semantics, which is different from any
normal value of the field:

\-- /example/ ASN1START

PRACH-Config ::= SEQUENCE {

rootSequenceIndex INTEGER (0..1023),

prach-ConfigInfo PRACH-ConfigInfo OPTIONAL \-- Need N

}

\-- ASN1STOP

The semantics of an optionally present field, in the case it is omitted,
should be indicated at the end of the paragraph including the keyword
OPTIONAL, using a short comment text with a need code. The need code
includes the keyword \"Need\", followed by one of the predefined
semantics tags (S, M, N or R) defined in clause 6.1. If the semantics
tag S is used, the semantics of the absent field are further specified
either in the field description table following the ASN.1 clause, or in
procedure text.

The addition of OPTIONAL keywords for capability groups is based on the
following guideline. If there is more than one field in the lower level
IE, then OPTIONAL keyword is added at the group level. If there is only
one field in the lower level IE, OPTIONAL keyword is not added at the
group level.