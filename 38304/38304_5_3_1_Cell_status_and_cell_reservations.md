### 5.3.1 Cell status and cell reservations

Cell status and cell reservations are indicated in the *MIB* or *SIB1*
message as specified in TS 38.331 \[3\] by means of the following
fields:

\- *cellBarred* (IE type: \"barred\" or \"not barred\")\
Indicated in *MIB* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is common for all PLMNs and NPNs. This field is
ignored by UEs supporting NTN for NTN access, or by UEs supporting ATG
for ATG access.

*- cellBarredATG* (IE type: \"barred\" or \"not barred\")\
Indicated in *SIB1* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is common for all PLMNs and NPNs. This field is
only applicable to ATG UEs.

*-* *cellBarred2RxXR* (IE type: \"barred\")\
Indicated in *SIB1* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is common for all PLMNs and NPNs. This field is
only applicable to 2Rx XR UEs.

\- *cellBarred-eRedCap1Rx* (IE type: \"barred\" or \"not barred\")\
Indicated in *SIB1* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is common for all PLMNs and NPNs. This field is
only applicable to eRedCap UEs.

\- *cellBarred-eRedCap2Rx* (IE type: \"barred\" or \"not barred\")\
Indicated in *SIB1* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is common for all PLMNs and NPNs. This field is
only applicable to eRedCap UEs.

\- *cellBarredFixedVSAT* (IE type: \"barred\" or \"not barred\")\
Indicated in *SIB1* message. In case of multiple PLMNs indicated in
*SIB1*, this field is common for all PLMNs. This field is only
applicable to VSAT UEs using NTN access.

\- *cellBarredMobileVSAT* (IE type: \"barred\" or \"not barred\")\
Indicated in *SIB1* message. In case of multiple PLMNs indicated in
*SIB1*, this field is common for all PLMNs. This field is only
applicable to VSAT UEs using NTN access.

\- *cellBarredNES* (IE type: \"not barred\")\
Indicated in *SIB1* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is common for all PLMNs and NPNs. This field is
only applicable to UEs indicating any of the values in *nes-CellDTX-DRX*
as specified in TS 38.306 \[24\].

\- *cellBarredNTN* (IE type: \"barred\" or \"not barred\")\
Indicated in *SIB1* message. In case of multiple PLMNs indicated in
*SIB1*, this field is common for all PLMNs. This field is ignored if the
UE does not support NTN access.

\- *cellBarredRedCap1Rx* (IE type: \"barred\" or \"not barred\")\
Indicated in *SIB1* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is common for all PLMNs and NPNs. This field is
only applicable to RedCap UEs.

\- *cellBarredRedCap2Rx* (IE type: \"barred\" or \"not barred\")\
Indicated in *SIB1* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is common for all PLMNs and NPNs. This field is
only applicable to RedCap UEs.

\- *cellReservedForOperatorUse* (IE type: \"reserved\" or \"not
reserved\")\
Indicated in *SIB1* message*.* In case of multiple PLMNs or NPNs
indicated in *SIB1*, this field is specified per PLMN or per SNPN.

\- *cellReservedForOtherUse* (IE type: \"true\")\
Indicated in *SIB1* message. In case of multiple PLMNs indicated in
*SIB1*, this field is common for all PLMNs.

*- cellReservedForFutureUse* (IE type: \"true\")\
Indicated in *SIB1* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is common for all PLMNs and NPNs.

NOTE 0: IAB-MT ignores the *cellBarred*, *cellReservedForOperatorUse,
cellReservedForFutureUse,* and *intraFreqReselection* (i.e. treats
*intraFreqReselection* as if it was set to *allowed*) as defined in TS
38.331 \[3\]. IAB-MT also ignores *cellReservedForOtherUse* for cell
barring determination (i.e. NPN capable IAB-MT considers
*cellReservedForOtherUse* for determination of an NPN-only cell) as
defined in TS 38.331 \[3\].

NOTE 0a: NCR-MT ignores the *cellBarred*, *cellReservedForOperatorUse,
cellReservedForFutureUse,* and *intraFreqReselection* (i.e. treats
*intraFreqReselection* as if it was set to *allowed*) as defined in TS
38.331 \[3\]. NCR-MT also ignores *cellReservedForOtherUse* for cell
barring determination (i.e. NPN capable NCR-MT considers
*cellReservedForOtherUse* for determination of an NPN-only cell) as
defined in TS 38.331 \[3\].

\- *halfDuplexRedCapAllowed* (IE type: \"true\")\
Indicated in *SIB1* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is common for all PLMNs and NPNs. This field is
only applicable to (e)RedCap UEs.

\- *iab-Support* (IE type: \"true\")\
Indicated in *SIB1* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is specified per PLMN or per SNPN. This field is
only applicable to IAB-MT.

\- *ncr-Support* (IE type: \"true\")\
Indicated in *SIB1* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is common for all PLMNs and NPNs. This field is
only applicable to NCR-MT.

\- *mobileIAB-Support* (IE type: \"true\")\
Indicated in *SIB1* message. In case of multiple PLMNs or NPNs indicated
in *SIB1*, this field is specified per PLMN or per SNPN. This field is
only applicable to mobile IAB-MT.

When cell status is indicated as \"not barred\" and \"not reserved\" for
operator use and not \"true\" for other use and not \"true\" for future
use,

\- UEs shall treat this cell as candidate during the cell selection and
cell reselection procedures.

When cell broadcasts any CAG-IDs or NIDs and the cell status is
indicated as \"not barred\" and \"not reserved\" for operator use and
\"true\" for other use, and not \"true\" for future use:

\- All NPN-capable UEs shall treat this cell as candidate during the
cell selection and cell reselection procedures, other UEs shall treat
this cell as if cell status is \"barred\".

When cell status is indicated as \"true\" for other use, and either cell
does not broadcast any CAG-IDs or NIDs or does not broadcast any CAG-IDs
and the UE is not operating in SNPN Access Mode,

\- The UE shall treat this cell as if cell status is \"barred\".

When cell status is indicated as \"true\" for future use,

\- The UE shall treat this cell as if cell status is \"barred\".

When *cellBarredNES* is absent and *cellBarred* is set to \"barred\",

\- The UE indicating any of the values in *nes-CellDTX-DRX* shall treat
this cell as if cell status is \"barred\".

When *cellBarredNTN* is not broadcast in this cell,

\- For NTN access, the UE shall treat this cell as if cell status is
\"barred\".

When *halfDuplexRedCapAllowed* is not broadcast in this cell,

\- The (e)RedCap UE only capable of operating in half-duplex for FDD
shall treat this cell as if cell status is \"barred\".

When *cellBarredATG* is not broadcast in this cell,

\- For ATG access, the UE shall treat this cell as if cell status is
\"barred\".

When *cellBarredFixedVSAT* is not broadcast in this cell,

\- For NTN access, the fixed VSAT UE shall treat this cell as if cell
status is \"barred\".

When *cellBarredMobileVSAT* is not broadcast in this cell,

\- For NTN access, the mobile VSAT UE shall treat this cell as if cell
status is \"barred\".

When *cellBarred2RxXR* is broadcast in this cell,

\- The 2Rx XR UE shall treat this cell as if cell status is \"barred\".

When *intraFreqReselectionRedCap* is not broadcast in this cell,

\- The RedCap UE shall treat this cell as if cell status is \"barred\".

When *intraFreqReselection-eRedCap* is not broadcast in this cell,

\- The eRedCap UE shall treat this cell as if cell status is \"barred\".

When *cellBarredRedCap1Rx* is set to \"barred\" and
*barringExemptEmergencyCall* is present in *SIB1*, if the cell will not
be treated as barred by the UE for any reason other than the
*cellBarredRedCap1Rx* being set to \"barred\" (see TS 38.331 \[3\]), and
cell selection criteria are fulfilled as defined in clause 5.2.3,

\- The RedCap UE that supports barring exemption for emergency call (see
TS 38.306 \[24\]) and only 1Rx branch shall treat this cell as an
acceptable cell.

When *cellBarredRedCap2Rx* is set to \"barred\" and
*barringExemptEmergencyCall* is present in *SIB1*, if the cell will not
be treated as barred by the UE for any reason other than the
*cellBarredRedCap2Rx* being set to \"barred\" (see TS 38.331 \[3\]), and
cell selection criteria are fulfilled as defined in clause 5.2.3,

\- The RedCap UE that supports barring exemption for emergency call (see
TS 38.306 \[24\]) and 2Rx branches shall treat this cell as an
acceptable cell.

When *cellBarred-eRedCap1Rx* is set to \"barred\" and
*barringExemptEmergencyCall* is present in *SIB1*, if the cell will not
be treated as barred by the UE for any reason other than the
*cellBarred-eRedCap1Rx* being set to \"barred\" (see TS 38.331 \[3\]),
and cell selection criteria are fulfilled as defined in clause 5.2.3,

\- The eRedCap UE that supports barring exemption for emergency call
(see TS 38.306 \[24\]) and only 1Rx branch shall treat this cell as an
acceptable cell.

When *cellBarred-eRedCap2Rx* is set to \"barred\" and
*barringExemptEmergencyCall* is present in *SIB1*, if the cell will not
be treated as barred by the UE for any reason other than the
*cellBarred-eRedCap2Rx* being set to \"barred\" (see TS 38.331 \[3\]),
and cell selection criteria are fulfilled as defined in clause 5.2.3,

\- The eRedCap UE that supports barring exemption for emergency call
(see TS 38.306 \[24\]) and 2Rx branches shall treat this cell as an
acceptable cell.

When *cellBarred2RxXR* and *barringExemptEmergencyCall* are both present
in *SIB1*, if the cell will not be treated as barred by the UE for any
reason other than the *cellBarred2RxXR* being present in *SIB1* (see TS
38.331 \[3\]), and cell selection criteria are fulfilled as defined in
clause 5.2.3,

\- The 2Rx XR UE that supports barring exemption for emergency call (see
TS 38.306 \[24\]) shall treat this cell as an acceptable cell.

When cell status is indicated as \"not barred\" and \"reserved\" for
operator use for any PLMN/SNPN and not \"true\" for other use and not
\"true\" for future use,

\- UEs assigned to Access Identity 11 or 15 operating in their
HPLMN/EHPLMN shall treat this cell as candidate during the cell
selection and reselection procedures if the field
*cellReservedForOperatorUse* for that PLMN set to \"reserved\".

\- UEs assigned to Access Identity 11 or 15 shall treat this cell as
candidate during the cell selection and reselection procedures if the
field *cellReservedForOperatorUse* for selected/registered SNPN is set
to \"reserved\".

\- UEs assigned to an Access Identity 0, 1, 2 and 12 to 14 shall behave
as if the cell status is \"barred\" in case the cell is \"reserved for
operator use\" for the registered PLMN/SNPN or the selected PLMN/SNPN.

\- UEs assigned to Access Identity 3 shall behave as if the cell status
is \"barred\" in case the cell is \"reserved for operator use\" for the
registered PLMN or the selected PLMN.

NOTE 1: Access Identities 11, 15 are only valid for use in the HPLMN/
EHPLMN and registered/selected SNPN; Access Identities 12, 13, 14 are
only valid for use in the home country and registered/selected SNPN as
specified in TS 22.261 \[12\].

NOTE 1a: Access Identity 3 is only valid for PLMNs that indicate to
potential Disaster Inbound Roamers that the UEs can access the PLMN as
specified in TS 22.261 \[12\].

When cell status \"barred\" is indicated or to be treated as if the cell
status is \"barred\",

\- The UE is not permitted to select/reselect this cell, not even for
emergency calls;

\- The UE shall select another cell according to the following rule:

\- If the cell is to be treated as if the cell status is \"barred\" due
to being unable to acquire the *MIB*:

\- the UE may exclude the barred cell as a candidate for cell
selection/reselection for up to 300 seconds.

\- the UE may select another cell on the same frequency if the selection
criteria are fulfilled.

\- else:

\- If the UE is a RedCap UE, the UE shall acquire *SIB1* and, in the
remainder of this procedure, consider \'*intraFreqReselection* in MIB\'
to be \'*intraFreqReselectionRedCap* in *SIB1*\', if available; or,

\- If the UE is an eRedCap UE, the UE shall acquire *SIB1* and, in the
remainder of this procedure, consider \'*intraFreqReselection* in MIB\'
to be \'*intraFreqReselection-eRedCap* in *SIB1*\', if available; or,

\- If the UE is a 2Rx XR UE, the UE shall acquire *SIB1* and, in the
remainder of this procedure, consider \'*intraFreqReselection* in MIB\'
to be \'*intraFreqReselection2RxXR* in *SIB1*\', if available:

\- If the cell is to be treated as if the cell status is \"barred\" due
to being unable to acquire the *SIB1*:

\- the UE may exclude the barred cell as a candidate for cell
selection/reselection for up to 300 seconds.

\- the UE may select another cell on the same frequency if the selection
criteria are fulfilled.

\- If the cell status \"barred\" is indicated in *MIB* but the UE is
unable to acquire the *SIB1*; or

\- If the UE is a RedCap UE and *intraFreqReselectionRedCap* in *SIB1*
is not available; or

\- If the UE is an eRedCap UE and *intraFreqReselection-eRedCap* in
*SIB1* is not available:

\- the UE shall exclude the barred cell as a candidate for cell
selection/reselection for 300 seconds.

\- the UE may select another cell on the same frequency if re-selection
criteria are fulfilled.

\- If the UE is neither a RedCap UE nor an eRedCap UE; or

\- if the UE is a RedCap UE and *intraFreqReselectionRedCap* in *SIB1*
is available; or

\- if the UE is an eRedCap UE and *intraFreqReselection-eRedCap* in
*SIB1* is available:

\- If the field *intraFreqReselection* in *MIB* message is set to
\"allowed\":

\- the UE may select another cell on the same frequency if re-selection
criteria are fulfilled;

\- If the cell is to be treated as if the cell status is \"barred\" due
to being unable to acquire the *SIB1*:

\- the UE may exclude the barred cell as a candidate for cell
selection/reselection for up to 300 seconds;

\- else:

\- the UE shall exclude the barred cell as a candidate for cell
selection/reselection for 300 seconds.

\- If the field *intraFreqReselection* in *MIB* message is set to \"not
allowed\":

\- If the cell is to be treated as if the cell status is \"barred\" due
to being unable to acquire the *SIB1*:

\- the UE may exclude the barred cell as a candidate for cell
selection/reselection for up to 300 seconds;

\- If the cell operates in licensed spectrum:

\- the UE shall not re-select to another cell on the same frequency as
the barred cell and exclude such cell(s) as candidate(s) for cell
selection/reselection for 300 seconds;

\- else:

\- the UE may select to another cell on the same frequency if the
reselection criteria are fulfilled.

\- else:

\- If the cell operates in licensed spectrum, or if this cell belongs to
a PLMN which is indicated as being equivalent to the registered PLMN or
the selected PLMN of the UE, or if this cell belongs to an SNPN which is
equal to or indicated as being equivalent to the registered SNPN or the
selected SNPN of the UE:

\- the UE shall not re-select to another cell on the same frequency as
the barred cell and exclude such cell(s) as candidate(s) for cell
selection/reselection for 300 seconds;

\- else:

\- the UE may select to another cell on the same frequency if the
reselection criteria are fulfilled.

\- the UE shall exclude the barred cell as a candidate for cell
selection/reselection for 300 seconds.

The cell selection of another cell may also include a change of RAT.

NOTE 2: If barring of a cell is triggered by the condition of
*trackingAreaCode* and *trackingAreaList* not being provided, as
specified in TS 38.331 \[3\], the barring only applies to this PLMN and
the UE can re-evaluate the barring condition again due to selection of
another PLMN.