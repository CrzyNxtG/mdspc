### A.3.1.1 ASN.1 clauses

The RRC PDU contents are formally and completely described using
abstract syntax notation (ASN.1), see X.680 \[6\], X.681 \[7\].

The complete ASN.1 code is divided into a number of ASN.1 clauses in the
specifications. In order to facilitate the extraction of the complete
ASN.1 code from the specification, each ASN.1 clause begins with the
following:

\- a first text paragraph consisting entirely of an *ASN.1 start tag*,
which consists of a double hyphen followed by a single space and the
text string \"ASN1START\" (in all upper case letters);

\- a second text paragraph consisting entirely of a *block start tag* is
included, which consists of a double hyphen followed by a single space
and the text string \"TAG-NAME-START\" (in all upper case letters),
where the \"NAME\" refers to the main name of the paragraph (in all
upper-case letters).

Similarly, each ASN.1 clause ends with the following:

\- a first text paragraph consisting entirely of a *blockstop tag*,
which consists of a double hyphen followed by a single space and the
text string \"TAG-NAME-STOP\" (in all upper-case letters), where the
\"NAME\" refers to the main name of the paragraph (in all upper-case
letters);

\- a second text paragraph consisting entirely of an *ASN.1 stop tag*,
which consists of a double hyphen followed by a singlespace and the text
\"ASN1STOP\" (in all upper case letters).

This results in the following tags:

\-- ASN1START

\-- TAG-NAME-START

\-- TAG-NAME-STOP

\-- ASN1STOP

The text paragraphs containing either of the start and stop tags should
not contain any ASN.1 code significant for the complete description of
the RRC PDU contents. The complete ASN.1 code may be extracted by
copying all the text paragraphs between an ASN.1 start tag and the
following ASN.1 stop tag in the order they appear, throughout the
specification.

NOTE: A typical procedure for extraction of the complete ASN.1 code
consists of a first step where the entire RRC PDU contents description
(ultimately the entire specification) is saved into a plain text (ASCII)
file format, followed by a second step where the actual extraction takes
place, based on the occurrence of the ASN.1 start and stop tags.