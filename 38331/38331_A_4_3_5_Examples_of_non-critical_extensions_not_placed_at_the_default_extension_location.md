### A.4.3.5 Examples of non-critical extensions not placed at the default extension location

The following example illustrates the use of non-critical extensions in
case an extension is not placed at the default extension location.

#### -- *ParentIE-WithEM*

The IE *ParentIE-WithEM*is an example of a high level IE including the
extension marker (EM). The root encoding of this IE includes two lower
level IEs *ChildIE1-WithoutEM* and *ChildIE2-WithoutEM* which not
include the extension marker. Consequently, non-critical extensions of
the Child-IEs have to be included at the level of the Parent-IE.

The example illustrates how the two extension IEs
*ChildIE1-WithoutEM-vNx0* and *ChildIE2-WithoutEM-vNx0* (both in release
N) are used to connect non-critical extensions with a default extension
location in the lower level IEs to the actual extension location in this
IE.

*ParentIE-WithEM* information element

\-- /example/ ASN1START

ParentIE-WithEM ::= SEQUENCE {

\-- Root encoding, including:

childIE1-WithoutEM ChildIE1-WithoutEM OPTIONAL, \-- Need N

childIE2-WithoutEM ChildIE2-WithoutEM OPTIONAL, \-- Need N

\...,

\[\[

childIE1-WithoutEM-vNx0 ChildIE1-WithoutEM-vNx0 OPTIONAL, \-- Need N

childIE2-WithoutEM-vNx0 ChildIE2-WithoutEM-vNx0 OPTIONAL \-- Need N

\]\]

}

\-- ASN1STOP

Some remarks regarding the extensions shown in the above example:

-- The fields *childIEx-WithoutEM-vNx0* may not really need to be
optional (depends on what is defined at the next lower level).

-- In general, especially when there are several nesting levels, fields
should be marked as optional only when there is a clear reason.

#### *-- ChildIE1-WithoutEM*

The IE *ChildIE1-WithoutEM* is an example of a lower level IE, used to
control certain radio configurations including a configurable feature
which can be setup or released using the local IE
*ChIE1-ConfigurableFeature*. The example illustrates how the new field
*chIE1-NewField* is added in release N to the configuration of the
configurable feature. The example is based on the following assumptions:

-- When initially configuring as well as when modifying the new field,
the original fields of the configurable feature have to be provided also
i.e. as if the extended ones were present within the setup branch of
this feature.

-- When the configurable feature is released, the new field should be
released also.

-- When omitting the original fields of the configurable feature the UE
continues using the existing values (which is used to optimise the
signalling for features that typically continue unchanged upon
handover).

-- When omitting the new field of the configurable feature the UE
releases the existing values and discontinues the associated
functionality (which may be used to support release of unsupported
functionality upon handover to an eNB supporting an earlier protocol
version).

The above assumptions, which affect the use of conditions and need
codes, may not always apply. Hence, the example should not be re-used
blindly.

*ChildIE1-WithoutEM* information element

\-- /example/ ASN1START

ChildIE1-WithoutEM ::= SEQUENCE {

\-- Root encoding, including:

chIE1-ConfigurableFeature ChIE1-ConfigurableFeature OPTIONAL \-- Need N

}

ChildIE1-WithoutEM-vNx0 ::= SEQUENCE {

chIE1-ConfigurableFeature-vNx0 ChIE1-ConfigurableFeature-vNx0 OPTIONAL
\-- Cond ConfigF

}

ChIE1-ConfigurableFeature ::= CHOICE {

release NULL,

setup SEQUENCE {

\-- Root encoding

}

}

ChIE1-ConfigurableFeature-vNx0 ::= SEQUENCE {

chIE1-NewField-rN INTEGER (0..31)

}

\-- ASN1STOP

  -------------------------------------------------------------------------
  Conditional   Explanation
  presence      
  ------------- -----------------------------------------------------------
  *ConfigF*     The field is optional present, need R, in case of
                chIE1-ConfigurableFeature is included and set to \"setup\";
                otherwise the field is absent and the UE shall delete any
                existing value for this field.

  -------------------------------------------------------------------------

#### *-- ChildIE2-WithoutEM*

The IE *ChildIE2-WithoutEM* is an example of a lower level IE, typically
used to control certain radio configurations. The example illustrates
how the new field *chIE1-NewField* is added in release N to the
configuration of the configurable feature.

*ChildIE2-WithoutEM* information element

\-- /example/ ASN1START

ChildIE2-WithoutEM ::= CHOICE {

release NULL,

setup SEQUENCE {

\-- Root encoding

}

}

ChildIE2-WithoutEM-vNx0 ::= SEQUENCE {

chIE2-NewField-rN INTEGER (0..31) OPTIONAL \-- Cond ConfigF

}

\-- ASN1STOP

  -------------------------------------------------------------------------
  Conditional   Explanation
  presence      
  ------------- -----------------------------------------------------------
  *ConfigF*     The field is optional present, need R, in case of
                chIE2-ConfigurableFeature is included and set to \"setup\";
                otherwise the field is absent and the UE shall delete any
                existing value for this field.

  -------------------------------------------------------------------------

[]{#_Toc46440049 .anchor}A.4.3.6 Non-critical extensions of lists with
ToAddMod/ToRelease

When the size of a list using the ToAddMod/ToRelease construction is
extended and/or fields are added to the list element structure, the list
should be non-critically extended in accordance with the following
general principles:

-- When only the size of the list is extended, this extension is
reflected in a non-critical extension of the list, with a \"SizeExt\"
suffix added to the end of the field name (before the -vNxy suffix). The
differential size of the extended list uses the suffix \"Diff\". A new
ToRelease list is needed, and its range should include only the increase
in list size. In many cases, extending the list size will also require
an extended list element ID type to account for the increased size of
the list; in these cases the element type will need to be extended to
include the extended element ID, resulting in a more complex extension
(see example 3 for further discussion of this case). The field
description table should indicate that the UE considers the original
list and the extension list as a single list; thus entries added with
the original list can be modified by the extension list (or removed by
the extension of the ToRelease list), or vice versa. The result is as
shown in the following example:

\-- /example 1/ ASN1START

ContainingStructure ::= SEQUENCE {

listElementToAddModList SEQUENCE (SIZE (1..maxNrofListElements)) OF
ListElement OPTIONAL, \-- Need N

listElementToReleaseList SEQUENCE (SIZE (1..maxNrofListElements)) OF
ListElementId OPTIONAL, \-- Need N

\...,

\[\[

\-- Non-critical extension lists

listElementToAddModListSizeExt-vNxy SEQUENCE (SIZE
(1..maxNrofListElementsDiff-rN)) OF ListElement OPTIONAL, \-- Need N

listElementToReleaseListSizeExt-vNxy SEQUENCE (SIZE
(1..maxNrofListElementsDiff-rN)) OF ListElementId OPTIONAL \-- Need N

\]\]

}

\-- ASN1STOP

-- When fields are added to the list element structure, an extension
marker should normally be used if available. If no extension marker is
available or if overhead or other considerations prevent using the
extension marker, an extension structure should be created for the new
fields, with the suffix \"Ext\" added to the end of the field name and
the element structure type name (before the -vNxy suffix), and a
parallel ToAddMod list introduced to hold the new structures, also with
the \"Ext\" suffix. The field description table should indicate that the
parallel list contains the same number of entries, and in the same
order, as the original list. No new ToRelease list is typically needed
(unless the list element ID type changes). It should typically be
ensured that the contained fields in the \"Ext\" elements are releasable
without release and add of the entire list element; this can, for
instance, be ensured by having the new fields be OPTIONAL Need R. If
multiple extensions of the same list are needed, the version suffix
should distinguish the lists (e.g. *listElementToAddModListExt-vNwz*
added after *listElementToAddModListExt-vNxy*). The result is as shown
in the following example:

\-- /example 2/ ASN1START

ContainingStructure ::= SEQUENCE {

listElementToAddModList SEQUENCE (SIZE (1..maxNrofListElements)) OF
ListElement OPTIONAL, \-- Need N

listElementToReleaseList SEQUENCE (SIZE (1..maxNrofListElements)) OF
ListElementId OPTIONAL, \-- Need N

\...,

\[\[

\-- Parallel list

listElementToAddModListExt-vNxy SEQUENCE (SIZE (1..maxNrofListElements))
OF ListElementExt-vNxy OPTIONAL \-- Need N

\]\],

\[\[

\-- Second parallel list from a later spec version

listElementToAddModListExt-vNwz SEQUENCE (SIZE (1..maxNrofListElements))
OF ListElementExt-vNwz OPTIONAL \-- Need N

\]\]

}

ListElement ::= SEQUENCE {

elementId ListElementId,

field1 INTEGER (0..3),

field2 ENUMERATED { value1, value2, value3 }

}

ListElementExt-vNxy ::= SEQUENCE {

field3-rN BIT STRING (SIZE (8)) OPTIONAL \-- Need R

}

ListElementExt-vNwz ::= SEQUENCE {

field4-rN INTEGER (0..255) OPTIONAL \-- Need R

}

\-- ASN1STOP

-- When the size of a list is extended and fields are added to the list
element structure, an extension marker should normally be used for the
added fields if available, and the list extended with the non-critical
mechanism as described in example 1 above*.* Note that if the list
element ID type changes in this case, the new ID can be added after the
extension marker, and the entries of the size-extended ToRelease list
should have the type of the new ID (e.g. *ListElementId-vNxy*). If no
extension marker is available or if overhead or other considerations
prevent using the extension marker, an extension structure should be
created for the new fields and a parallel list with ToAddMod introduced
to hold the extension structures, as in the second example above, for
entries of the original list and for entries of the extension list
holding new entries. The field description table should indicate that
the parallel list contains the same number of entries, and in the same
order, as the concatenation of the original list and the extension list.
An extended ToRelease list is needed, but no additional parallel
ToRelease list is needed (i.e. there is no
*listElementToReleaseListExt-vNxy* in the example below), as the
original and extended ToRelease lists suffice to release any element of
the combined list. The extended element ID type should be captured as a
non-critical extension of the original element ID type, with the field
description indicating that if the extended ID is present, the original
ID is ignored. The result is as shown in the following example:

\-- /example 3/ ASN1START

ContainingStructure ::= SEQUENCE {

listElementToAddModList SEQUENCE (SIZE (1..maxNrofListElements)) OF
ListElement OPTIONAL, \-- Need N

listElementToReleaseList SEQUENCE (SIZE (1..maxNrofListElements)) OF
ListElementId OPTIONAL, \-- Need N

\...,

\[\[

\-- Non-critical extension lists

listElementToAddModListSizeExt-vNxy SEQUENCE (SIZE
(1..maxNrofListElementsDiff-rN)) OF ListElement OPTIONAL, \-- Need N

listElementToReleaseListSizeExt-vNxy SEQUENCE (SIZE
(1..maxNrofListElementsDiff-rN)) OF ListElementId-vNxy OPTIONAL, \--
Need N

\-- Parallel list with maxNrofListElements-rN = maxNrofListElements +
maxNrofListElementsDiff-rN

listElementToAddModListExt-vNxy SEQUENCE (SIZE
(1..maxNrofListElements-rN)) OF ListElementExt-vNxy OPTIONAL \-- Need N

\]\]

}

ListElement ::= SEQUENCE {

elementId ListElementId,

field1 INTEGER (0..3),

field2 ENUMERATED { value1, value2, value3 }

}

ListElementExt-vNxy ::= SEQUENCE {

\-- Field description should indicate that if the elementId-vNxy is
present, the elementId (without suffix) is ignored

elementId-vNxy ListElementId-vNxy OPTIONAL, \-- Need S

field3-rN BIT STRING (SIZE (8)) OPTIONAL \-- Need R

}

ListElementId ::= INTEGER (0..maxNrofListElements-1)

ListElementId-vNxy ::= INTEGER
(maxNrofListElements..maxNrofListElements-1-rN)

\-- ASN1STOP

-- When different extensions are made to a list in separate releases,
the extension mechanisms described above may interact. In case fields
are added in Rel-M (*listElementToAddModListExt-vMxy*) and later the
list size is extended in Rel-N (*listElementToAddModListSizeExt-vNwz*),
the size-extended list in Rel-N should be a single list extending the
combination of *listElementToAddModList* and
*listElementToAddModListExt-vMxy*. This requires creating a new type
(*ListElement-rN*) to contain the combined fields of *ListElement* and
*ListElementExt-vMxy*. A corresponding ToRelease list is needed. The
result is as shown in the following example:

\-- /example 4/ ASN1START

ContainingStructure ::= SEQUENCE {

listElementToAddModList SEQUENCE (SIZE (1..maxNrofListElements)) OF
ListElement OPTIONAL, \-- Need N

listElementToReleaseList SEQUENCE (SIZE (1..maxNrofListElements)) OF
ListElementId OPTIONAL, \-- Need N

\...,

\[\[

\-- Parallel list (Rel-M)

listElementToAddModListExt-vMxy SEQUENCE (SIZE (1..maxNrofListElements))
OF ListElementExt-vMxy OPTIONAL \-- Need N

\]\],

\[\[

\-- Size-extended list (Rel-N) with maxNrofListElements-rN =
maxNrofListElements + maxNrofListElementsDiff-rN

listElementToAddModListSizeExt-vNwz SEQUENCE (SIZE
(1..maxNrofListElementsDiff-rN)) OF ListElement-rN OPTIONAL, \-- Need N

listElementToReleaseListSizeExt-vNwz SEQUENCE (SIZE
(1..maxNrofListElementsDiff-rN)) OF ListElementId-vNwz OPTIONAL \-- Need
N

\]\]

}

ListElement ::= SEQUENCE {

elementId ListElementId,

field1 INTEGER (0..3),

field2 ENUMERATED { value1, value2, value3 }

}

ListElementExt-vMxy ::= SEQUENCE {

field3-rM BIT STRING (SIZE (8)) OPTIONAL \-- Need R

}

ListElement-rN ::= SEQUENCE {

elementId-vNwz ListElementId-vNwz,

field1 INTEGER (0..3),

field2 ENUMERATED { value1, value2, value3 },

field3-rN BIT STRING (SIZE (8)) OPTIONAL \-- Need R

}

ListElementId ::= INTEGER (0..maxNrofListElements-1)

ListElementId-vNwz ::= INTEGER
(maxNrofListElements..maxNrofListElementsDiff-1-rN)

\-- ASN1STOP