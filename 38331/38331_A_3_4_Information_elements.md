## A.3.4 Information elements

Each IE (information element) type is specified in an ASN.1 clause
similar to the one shown in the example below.

\-- /example/ ASN1START

PRACH-ConfigSIB ::= SEQUENCE {

rootSequenceIndex INTEGER (0..1023),

prach-ConfigInfo PRACH-ConfigInfo

}

PRACH-Config ::= SEQUENCE {

rootSequenceIndex INTEGER (0..1023),

prach-ConfigInfo PRACH-ConfigInfo OPTIONAL \-- Need N

}

PRACH-ConfigInfo ::= SEQUENCE {

prach-ConfigIndex ENUMERATED {ffs},

highSpeedFlag ENUMERATED {ffs},

zeroCorrelationZoneConfig ENUMERATED {ffs}

}

\-- ASN1STOP

IEs should be introduced whenever there are multiple fields for which
the same set of values apply. IEs may also be defined for other reasons
e.g. to break down a ASN.1 definition in to smaller pieces.

A group of closely related IE type definitions, like the IEs
*PRACH-ConfigSIB* and *PRACH-Config* in this example, are preferably
placed together in a common ASN.1 clause. The IE type identifiers should
in this case have a common base, defined as the *generic type
identifier*. It may be complemented by a suffix to distinguish the
different variants. The \"*PRACH-Config*\" is the generic type
identifier in this example, and the \"*SIB*\" suffix is added to
distinguish the variant. The clause heading and generic references to a
group of closely related IEs defined in this way should use the generic
type identifier.

The same principle should apply if a new version, or an extension
version, of an existing IE is created for *critical* or *non-critical*
extension of the protocol (see clause A.4). The new version, or the
extension version, of the IE is included in the same ASN.1 clause
defining the original. A suffix is added to the type identifier, using
the naming conventions defined in clause A.3.1.2, indicating the release
or version of the where the new version, or extension version, was
introduced.

Local IE type definitions, like the IE *PRACH-ConfigInfo* in the example
above, may be included in the ASN.1 clause and be referenced in the
other IE types defined in the same ASN.1 clause. The use of locally
defined IE types should be encouraged, as a tool to break up large and
complex IE type definitions. It can improve the readability of the code.
There may also be a benefit for the software implementation of the
protocol end-points, as these IE types are typically provided by the
ASN.1 compiler as independent data elements, to be used in the software
implementation.

An IE type defined in a local context, like the IE *PRACH-ConfigInfo*,
should not be referenced directly from other ASN.1 clauses in the RRC
specification. An IE type which is referenced in more than one ASN.1
clause should be defined in a separate clause, with a separate heading
and a separate ASN.1 clause (possibly as one in a set of closely related
IE types, like the IEs *PRACH-ConfigSIB* and *PRACH-Config* in the
example above). Such IE types are also referred to as \'global IEs\'.

NOTE: Referring to an IE type, that is defined as a local IE type in the
context of another ASN.1 clause, does not generate an ASN.1 compilation
error. Nevertheless, using a locally defined IE type in that way makes
the IE type definition difficult to find, as it would not be visible at
an outline level of the specification. It should be avoided.

The ASN.1 clause specifying the contents of one or more IE types, like
in the example above, may be followed by a *field description* table,
where a further description of, e.g., the semantic properties of the
fields of the information elements may be included. This table may be
absent, similar as indicated in clause A.3.3 for the specification of
the PDU type. The general format of the *field description* table is the
same as shown in clause A.3.3 for the specification of the PDU type.