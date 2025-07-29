## A.3.9 Guidelines on use of ToAddModList and ToReleaseList

In order to benefit from delta signalling when modifying lists with many
and/or large elements, so-called add/mod- and release- lists should be
used. Instead of a single list containing all elements of the list, the
ASN.1 provides two lists. One list is used to convey the actual elements
that are to be added to the list or modified in the list. The second
list conveys only the identities (IDs) of the list elements that are to
be released from the list. In other words, the ASN.1 defines only means
to signal modifications to a list maintained in the receiver (typically
the UE). An example is provided below:

\-- /example/ ASN1START

AnExampleIE ::= SEQUENCE {

elementsToAddModList SEQUENCE (SIZE (1..maxNrofElements)) OF Element
OPTIONAL, \-- Need N

elementsToReleaseList SEQUENCE (SIZE (1..maxNrofElements)) OF ElementId
OPTIONAL, \-- Need N

\...

}

Element ::= SEQUENCE {

elementId ElementId,

aField INTEG ER (0..16777215),

anotherField OCTET STRING,

\...

}

ElementId ::= INTEGER (0..maxNrofElements-1)

maxNrofElements INTEGER ::= 50

maxNrofElements-1 INTEGER ::= 49

\-- /example/ ASN1STOP

As can be seen, the elements of the list must contain an identity
(INTEGER) that identifies the elements unambiguously upon addition,
modification and removal. It is recommended to define an IE for that
identifier (here ElementId) so that it can be used both for a field
inside the element as well as in the *elementsToReleaseList*.

Both lists should be made OPTIONAL and flagged as \"Need N\". The need
code reflects that the UE does not maintain the received lists as such
but rather updates its configuration using the information therein. In
other words, it is not possible to provide via delta signalling an
update to a previously signalled *elementsToAddModList* or
elementsToReleaseList (which Need M would imply). The update is always
in relation to the UE\'s internal configuration.

Note that the release of a field (a list element as well as any other
field) releases all its sub-fields (sub-fields configured by
elementsToAddModList and any other sub-field).

If no procedural text is provided for a set of ToAddModList and
ToReleaseList, the following generic procedure applies:

The UE shall:

1\> for each *ElementId* in the *elementsToReleaseList*,:

2\> if the current UE configuration includes an *Element* with the given
*ElementId*:

3\> release the *Element* from the current UE configuration;

1\> for each *Element* in the *elementsToAddModList*:

2\> if the current UE configuration includes an *Element* with the given
*ElementId*:

3\> modify the configured *Element* in accordance with the received
*Element*;

2\> else:

3\> add received *Element* to the UE configuration.