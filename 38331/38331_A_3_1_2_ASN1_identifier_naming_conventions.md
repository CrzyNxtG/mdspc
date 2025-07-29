### A.3.1.2 ASN.1 identifier naming conventions

The naming of identifiers (i.e., the ASN.1 field and type identifiers)
should be based on the following guidelines:

\- Message (PDU) identifiers should be ordinary mixed case without
hyphenation. These identifiers, *e.g.*, the
*RRCConnectionModificationCommand*, should be used for reference in the
procedure text. Abbreviations should be avoided in these identifiers and
abbreviated forms of these identifiers should not be used.

\- Type identifiers other than PDU identifiers should be ordinary mixed
case, with hyphenation used to set off acronyms only where an adjacent
letter is a capital, *e.g.*, *EstablishmentCause, SelectedPLMN* (not
*Selected-PLMN*, since the \"d\" in \"Selected\" is lowercase)*,
InitialUE-Identity* and *MeasSFN-SFN-TimeDifference*.

\- Field identifiers shall start with a lowercase letter and use mixed
case thereafter, *e.g.*, *establishmentCause*. If a field identifier
begins with an acronym (which would normally be in upper case), the
entire acronym is lowercase (*plmn-Identity*, not *pLMN-Identity*). The
acronym is set off with a hyphen (*ue-Identity*, not *ueIdentity*), in
order to facilitate a consistent search pattern with corresponding type
identifiers.

\- Identifiers should convey the meaning of the identifier and should
avoid adding unnecessary postfixes (e.g. abstractions like \'Info\') for
the name.

\- Identifiers that are likely to be keywords of some language,
especially widely used languages, such as C++ or Java, should be avoided
to the extent possible.

\- Identifiers, other than PDU identifiers, longer than 25 characters
should be avoided where possible. It is recommended to use
abbreviations, which should be done in a consistent manner i.e. use
\'Meas\' instead of \'Measurement\' for all occurrences. Examples of
typical abbreviations are given in table A.3.1.2.1-1 below.

\- *For future extension:* When an extension is introduced a suffix is
added to the identifier of the concerned ASN.1 field and/or type. A
suffix of the form \"‑rX\" is used, with X indicating the release, for
ASN.1 fields or types introduced in a later release (i.e. a release
later than the original/first release of the protocol) as well as for
ASN.1 fields or types for which a revision is introduced in a later
release replacing a previous version, *e.g.*, *Foo-r9* for the Rel-9
version of the ASN.1 type *Foo*. A suffix of the form \"‑rXb\" is used
for the first revision of a field that it appears in the same release
(X) as the original version of the field, \"‑rXc\" for a second
intra-release revision and so on. A suffix of the form \"‑vXYZ\" is used
for ASN.1 fields or types that only are an extension of a corresponding
earlier field or type (see clause A.4), e.g., *AnElement-v10b0* for the
extension of the ASN.1 type *AnElement* introduced in version 10.11.0 of
the specification. A number *0\...9, 10, 11, etc.* is used to represent
the first part of the version number, indicating the release of the
protocol. Lower case letters *a, b, c, etc.* are used to represent the
second (and third) part of the version number if they are greater than
9. In the procedural specification, in field descriptions as well as in
headings suffices are not used, unless there is a clear need to
distinguish the extension from the original field.

\- More generally, in case there is a need to distinguish different
variants of an ASN.1 field or IE, a suffix should be added at the end of
the identifiers e.g. *MeasObjectUTRA*, *ConfigCommon*. When there is no
particular need to distinguish the fields (e.g. because the field is
included in different IEs), a common field identifier name may be used.
This may be attractive e.g. in case the procedural specification is the
same for the different variants.

\- It should be avoided to use field identifiers with the same name
within the elements of a CHOICE, including using a CHOICE inside a
SEQUENCE (to avoid certain compiler errors).

Table A.3.1.2-1: Examples of typical abbreviations used in ASN.1
identifiers

  -----------------------------------------------------------------------
  Abbreviation                Abbreviated word
  --------------------------- -------------------------------------------
  Config                      Configuration

  DL                          Downlink

  Ext                         Extension

  Freq                        Frequency

  Id                          Identity

  Ind                         Indication

  Meas                        Measurement

  MIB                         MasterInformationBlock

  Neigh                       Neighbour(ing)

  Param(s)                    Parameter(s)

  Phys                        Physical

  PCI                         Physical Cell Id

  Proc                        Process

  Reconfig                    Reconfiguration

  Reest                       Re-establishment

  Req                         Request

  Rx                          Reception

  Sched                       Scheduling

  SIB                         SystemInformationBlock

  Sync                        Synchronisation

  Thr                         Threshold

  Tx                          Transmission

  UL                          Uplink
  -----------------------------------------------------------------------

NOTE: The table A.3.1.2.1-1 is not exhaustive. Additional abbreviations
may be used in ASN.1 identifiers when needed.