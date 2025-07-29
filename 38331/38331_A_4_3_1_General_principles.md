### A.4.3.1 General principles

The mechanisms to extend a message in a non-critical manner are defined
in A.3.3. W.r.t. the use of extension markers, the following additional
guidelines apply:

\- When further non-critical extensions are added to a message that has
been critically extended, the inclusion of these non-critical extensions
in earlier critical branches of the message should be avoided when
possible.

\- The extension marker (\"\...\") is the primary non-critical extension
mechanism that is used but empty sequences may be used if length
determinant is not required. Examples of cases where a length
determinant is not required:

\- at the end of a message;

\- at the end of a structure contained in a BIT STRING or OCTET STRING.

\- When an extension marker is available, non-critical extensions are
preferably placed at the location (e.g. the IE) where the concerned
parameter belongs from a logical/ functional perspective (referred to as
the \'*default extension location*\').

\- It is desirable to aggregate extensions of the same release or
version of the specification into a group, which should be placed at the
lowest possible level.

\- In specific cases it may be preferable to place extensions elsewhere
(referred to as the \'*actual extension location*\') e.g. when it is
possible to aggregate several extensions in a group. In such a case, the
group should be placed at the lowest suitable level in the message.

\- In case placement at the default extension location affects earlier
critical branches of the message, locating the extension at a following
higher level in the message should be considered.

\- In case an extension is not placed at the default extension location,
an IE should be defined. The IE\'s ASN.1 definition should be placed in
the same ASN.1 clause as the default extension location. In case there
are intermediate levels in-between the actual and the default extension
location, an IE may be defined for each level. Intermediate levels are
primarily introduced for readability and overview. Hence intermediate
levels need not always be introduced e.g. they may not be needed when
the default and the actual extension location are within the same ASN.1
clause.