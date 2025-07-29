### 11.2.3 Mandatory information in inter-node RRC messages

For the *AS-Config* transferred within the
*HandoverPreparationInformation*:

\- The source node shall include all fields necessary to reflect the
current AS configuration of the UE, except for the fields
*sourceSCG-NR-Config*, *sourceSCG-EUTRA-Config* and
*sourceRB-SN-Config*, which can be omitted in case the source MN did not
receive the latest configuration from the source SN. For
*RRCReconfiguration* included in the field *rrcReconfiguration*,
*ReconfigurationWithSync* is included with only the mandatory subfields
(e.g. *newUE-Identity* and *t304*) and *ServingCellConfigCommon*;

\- Need codes or conditions specified for subfields according to IEs
defined in clause 6 do not apply. I.e. some fields shall be included
regardless of the \"Need\" or \"Cond\" e.g. *discardTimer*;

\- Based on the received AS configuration, the target node can indicate
the delta (difference) to the current AS configuration (as included in
*HandoverCommand*)to the UE. The fields *newUE-Identity* and *t304*
included in *ReconfigurationWithSync* are not used for delta
configuration purpose.

The *candidateCellInfoListSN*(-*EUTRA*) in *CG-Config* and the
*candidateCellInfoListMN*(*-EUTRA*)/*candidateCellInfoListSN*(-*EUTRA*)
in *CG-ConfigInfo* need not be included in procedures that do not
involve a change of node.

For fields *scg-CellGroupConfig, scg-CellGroupConfigEUTRA* and
*scg-RB-Config* in *CG-Config* (sent upon SN initiated SN change or
other conditions as specified in field descriptions) and fields
*mcg-RB-Config*, *scg-RB-Config* and *sourceConfigSCG* in
*CG-ConfigInfo* (sent upon change of SN):

\- The source node shall include all fields necessary to reflect the
current AS configuration of the UE, unless stated otherwise in the field
description. For *RRCReconfiguration* included in the field
*scg-CellGroupConfig in CG-Config*, *ReconfigurationWithSync* is
included with only the mandatory subfields (e.g. *newUE-Identity* and
*t304*) and *ServingCellConfigCommon*;

\- Need codes or conditions specified for subfields according to IEs
defined in clause 6 do not apply;

\- Based on the received AS configuration, the target node can indicate
the delta (difference) as compared to the current AS configuration to
the UE. The fields *newUE-Identity* and *t304* in
*ReconfigurationWithSync* are always included by the target node, i.e.
they are not used for delta configuration purpose to UE.

For fields in *CG-Config* and *CG-ConfigInfo* listed below, absence of
the field means that the receiver maintains the values informed via the
previous message. Note that every time there is a change in the
configuration covered by a listed field, the MN or SN shall include the
field and it shall provide the full configuration provided by that field
unless stated otherwise. Otherwise, if there is no change, the field can
be omitted:

\- *configRestrictInfo*;

\- *gapPurpose;*

\- *measGapConfig* (for which delta signaling applies);

*- measGapConfigFR2* (for which delta signaling applies);

\- *measResultCellListSFTD*;

*- measResultSFTD-EUTRA*;

\- *sftdFrequencyList-EUTRA*;

*- sftdFrequencyList-NR;*

\- *ue-CapabilityInfo;*

*- servFrequenciesMN-NR;*

*- musim-GapConfigInfo-r18;*

\- *musim-CapRestrictionInfo-r18.*

For other fields in CG-Config and CG-ConfigInfo, the sender shall always
signal the appropriate value even if same as indicated in the previous
inter-node message, unless explicitly stated otherwise.