## A.3.8 Guidelines on use of parameterised SetupRelease type

The usage of the parameterised *SetupRelease* type is like a function
call in programming languages where the element type parameter is passed
as a parameter. The parameterised type only implies a textual change in
abstract syntax where all references to the parameterised type are
replaced by the compiler with the release/setup choice. Two examples of
the usage are shown below:

\-- /example/ ASN1START

RRCMessage-rX-IEs ::= SEQUENCE {

field-rX SetupRelease { IE-rX } OPTIONAL, \-- Need M

\...

}

RRCMessage-rX-IEs ::= SEQUENCE {

field-rX SetupRelease { Element-rX }

} OPTIONAL, \-- Need M

Element-rX ::= SEQUENCE {

field1-rX IE1-rX,

field2-rX IE2-rX OPTIONAL \-- Need N

} OPTIONAL, \-- Need M

\-- /example/ ASN1STOP

The *SetupRelease* is always be used with only named IEs, i.e. the
example below is not allowed:

\-- /example/ ASN1START

RRCMessage-rX-IEs ::= SEQUENCE {

field-rX SetupRelease { SEQUENCE { \-- Unnamed SEQUENCEs are not
allowed!

field1-rX IE1-rX,

field2-rX IE2-rX OPTIONAL \-- Need N

}

} OPTIONAL, \-- Need M

}

\-- /example/ ASN1STOP

Typically, a field defined using the parameterized *SetupRelease* type
does not require procedural or field description text that refers to the
*setup* or *release* values. If such a field anyway requires procedural
text for specific actions, the field is referred to using the values
defined for the type itself, namely, \"setup\" and \"release\". For
example, procedural text for field-rX above could be as follows:

1\> if *field-rX* is set to \"setup\":

2\> do something;

1\> else (*field-rX* is set to \"release\"):

2\> release *field-rX* (if appropriate).