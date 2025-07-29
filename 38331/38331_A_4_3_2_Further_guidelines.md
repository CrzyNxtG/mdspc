### A.4.3.2 Further guidelines

Further to the general principles defined in the previous clause, the
following additional guidelines apply regarding the use of extension
markers:

\- Extension markers within SEQUENCE:

\- Extension markers are primarily, but not exclusively, introduced at
the higher nesting levels.

\- Extension markers are introduced for a SEQUENCE comprising several
fields as well as for information elements whose extension would result
in complex structures without it (e.g. re-introducing another list).

\- Extension markers are introduced to make it possible to maintain
important information structures e.g. parameters relevant for one
particular RAT.

\- Extension markers are also used for size critical messages (i.e.
messages on BCCH, BR-BCCH, PCCH and CCCH), although introduced somewhat
more carefully.

\- The extension fields introduced (or frozen) in a specific version of
the specification are grouped together using double brackets.

\- Extension markers within ENUMERATED:

\- Spare values may be used until the number of values reaches the next
power of 2, while the extension marker caters for extension beyond that
limit, given that the use of spare values in a later Release is possible
without any error cases.

\- A suffix of the form \"vXYZ\" is used for the identifier of each new
value, e.g. \"value-vXYZ\".

\- Extension markers within CHOICE:

\- Extension markers are introduced when extension is foreseen and when
comprehension is not required by the receiver i.e. behaviour is defined
for the case where the receiver cannot comprehend the extended value
(e.g. ignoring an optional CHOICE field). It should be noted that
defining the behaviour of a receiver upon receiving a not comprehended
choice value is not required if the sender is aware whether or not the
receiver supports the extended value.

\- A suffix of the form \"vXYZ\" is used for the identifier of each new
choice value, e.g. \"choice-vXYZ\".

Non-critical extensions at the end of a message/ of a field contained in
an OCTET or BIT STRING:

\- When a nonCriticalExtension is actually used, a \"Need\" code should
not be provided for the field, which always is a group including at
least one extension and a field facilitating further possible
extensions. For simplicity, it is recommended not to provide a \"Need\"
code when the field is not actually used either.

Further, more general, guidelines:

\- In case a need code is not provided for a group, a \"Need\" code is
provided for all individual extension fields within the group i.e.
including for fields that are not marked as OPTIONAL. The latter is to
clarify the action upon absence of the whole group.