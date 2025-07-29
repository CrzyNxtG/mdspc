## A.3.10 Guidelines on use of lists (without ToAddModList and ToReleaseList)

As per clause 6.1.3, when using lists without the ToAddModList and
ToReleaseList structure, the contents of the lists are always replaced.
To illustrate this, an example is provided below:

\-- /example/ ASN1START

\-- TAG_EXAMPLE_LISTS_START

AnExampleIE ::= SEQUENCE {

elementList SEQUENCE (SIZE (1..maxNrofElements)) OF Element OPTIONAL,
\-- Need M

\...,

\[\[

elementListExt-v2030 SEQUENCE (SIZE (1..maxNrofElementsExt)) OF Element
OPTIONAL, \-- Need M

\]\]

}

Element ::= SEQUENCE {

useFeatureX BOOLEAN,

aField INTEGER (0..127) OPTIONAL, \-- Need M

anotherField INTEGER (0..127) OPTIONAL, \-- Need R

\...

}

maxNrofElements INTEGER ::= 8

maxNrofElements-1 INTEGER ::= 7

maxNrofElementsExt INTEGER ::= 8

maxNrofElementsExt-1 INTEGER ::= 7

\-- TAG_EXAMPLE_LISTS_STOP

\-- /example/ ASN1STOP

As can be seen, the *elementList* list itself uses Need M, but each list
entry *Element* contains mandatory, Need M and Need R fields. If the
list is first signalled to UE with 3 entries, and subsequently again
with 2 entries, UE shall retain only the latter list, i.e. the list with
2 elements will completely replace the list with 3 elements. That also
means that the field *aField* will be treated as if it was newly
created, i.e. network must include it if it wishes UE to utilize the
field even if it was previously signalled. This also implies that the
Need M field (*aField*) will be treated in the same way as the Need R
field (*anotherField*), i.e. delta signalling is not applied and the
network has to signal the field to ensure UE does not release the value
(which is why Need M should not normally be used in the entries of these
lists).