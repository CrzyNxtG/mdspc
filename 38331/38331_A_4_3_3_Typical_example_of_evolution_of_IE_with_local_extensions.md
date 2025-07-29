### A.4.3.3 Typical example of evolution of IE with local extensions

The following example illustrates the use of the extension marker for a
number of elementary cases (sequence, enumerated, choice). The example
also illustrates how the IE may be revised in case the critical
extension mechanism is used.

NOTE In case there is a need to support further extensions of release n
while the ASN.1 of release (n+1) has been frozen, without requiring the
release n receiver to support decoding of release (n+1) extensions, more
advanced mechanisms are needed e.g. including multiple extension
markers.

\-- /example/ ASN1START

InformationElement1 ::= SEQUENCE {

field1 ENUMERATED {

value1, value2, value3, value4-v880,

\..., value5-v960 },

field2 CHOICE {

field2a BOOLEAN,

field2b InformationElement2b,

\...,

field2c-v960 InformationElement2c-r9

},

\...,

\[\[

field3-r9 InformationElement3-r9 OPTIONAL \-- Need R

\]\],

\[\[

field3-v9a0 InformationElement3-v9a0 OPTIONAL, \-- Need R

field4-r9 InformationElement4 OPTIONAL \-- Need R

\]\]

}

InformationElement1-r10 ::= SEQUENCE {

field1 ENUMERATED {

value1, value2, value3, value4-v880,

value5-v960, value6-v1170, spare2, spare1, \... },

field2 CHOICE {

field2a BOOLEAN,

field2b InformationElement2b,

field2c-v960 InformationElement2c-r9,

\...,

field2d-v12b0 INTEGER (0..63)

},

field3-r9 InformationElement3-r10 OPTIONAL, \-- Need R

field4-r9 InformationElement4 OPTIONAL, \-- Need R

field5-r10 BOOLEAN,

field6-r10 InformationElement6-r10 OPTIONAL, \-- Need R

\...,

\[\[

field3-v1170 InformationElement3-v1170 OPTIONAL \-- Need R

\]\]

}

\-- ASN1STOP

Some remarks regarding the extensions of *InformationElement1* as shown
in the above example:

-- The *InformationElement1* is initially extended with a number of
non-critical extensions. In release 10 however, a critical extension is
introduced for the message using this IE. Consequently, a new version of
the IE *InformationElement1* (i.e. *InformationElement1-r10*) is defined
in which the earlier non-critical extensions are incorporated by means
of a revision of the original field.

-- The *value4-v880* is replacing a spare value defined in the original
protocol version for *field1*. Likewise *value6-v1170* replaces *spare3*
that was originally defined in the r10 version of *field1.*

-- Within the critically extended release 10 version of
*InformationElement1*, the names of the original fields/IEs are not
changed, unless there is a real need to distinguish them from other
fields/IEs. E.g. the *field1* and *InformationElement4* were defined in
the original protocol version (release 8) and hence not tagged.
Moreover, the *field3-r9* is introduced in release 9 and not re-tagged;
although, the *InformationElement3* is also critically extended and
therefore tagged *InformationElement3-r10* in the release 10 version of
InformationElement1.