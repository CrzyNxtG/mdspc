### 6.1.3 General rules

In the ASN.1 of this specification, the first bit of a bit string refers
to the leftmost bit, unless stated otherwise.

Upon reception of a list not using ToAddModList and ToReleaseList
structure, the UE shall delete all entries of the list currently in the
UE configuration before applying the received list and shall consider
each entry as newly created. This applies also to lists whose size is
extended (i.e. with a second list structure in the ASN.1 comprising
additional entries), unless otherwise specified. This implies that Need
M should not be used for fields in the entries of these lists; if used,
UE will handle such fields equivalent to a Need R.