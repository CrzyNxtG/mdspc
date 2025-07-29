### 5.1.5 Antenna ports quasi co-location

The UE can be configured with a list of up to *M* *TCI-State*
configurations within the higher layer parameter *PDSCH-Config* to
decode PDSCH according to a detected PDCCH with DCI intended for the UE
and the given serving cell, where M depends on the UE capability
*maxNumberConfiguredTCIstatesPerCC*. Each *TCI-State* contains
parameters for configuring a quasi co-location relationship between one
or two downlink reference signals and the DM-RS ports of the PDSCH, the
DM-RS port of PDCCH or the CSI-RS port(s) of a CSI-RS resource. The
quasi co-location relationship is configured by the higher layer
parameter *qcl-Type1* for the first DL RS, and *qcl-Type2* for the
second DL RS (if configured). For the case of two DL RSs, the QCL types
shall not be the same, regardless of whether the references are to the
same DL RS or different DL RSs. The quasi co-location types
corresponding to each DL RS are given by the higher layer parameter
*qcl-Type* in *QCL-Info* and may take one of the following values:

\- \'typeA\': {Doppler shift, Doppler spread, average delay, delay
spread}

\- \'typeB\': {Doppler shift, Doppler spread}

\- \'typeC\': {Doppler shift, average delay}

\- \'typeD\': {Spatial Rx parameter}

The UE can be configured with a list of up to *128* *TCI-State*
configurations, within the higher layer parameter
*dl-OrJointTCI-StateList* in *PDSCH-Config* for providing a reference
signal for the quasi co-location for DM-RS of PDSCH and DM-RS of PDCCH
in a BWP/CC, for CSI-RS, and to provide a reference signal with
*qcl-Type* set to \'typeD\', if applicable, for determining UL TX
spatial filter for dynamic-grant and configured-grant based PUSCH and
PUCCH resource in a BWP/CC, and SRS.

If the *TCI-State* or *TCI-UL-State* configurations are absent in a BWP
of the CC, the UE can apply the *TCI-State* or *TCI-UL-State*
configurations from a reference BWP of a reference CC configured by
*unifiedTCI-StateRef*. The UE is not expected to be configured with
*tci-StatesToAddModList*, *SpatialRelationInfo* or
*PUCCH-SpatialRelationInfo*, except *SpatialRelationInfoPos* in a CC in
a band, if the UE is configured with *dl-OrJointTCI-StateList* or
*ul-TCI-StateList* in any CC in the same band. The UE can assume that
when the UE is configured with *tci-StatesToAddModList* in any CC in the
CC list configured by *simultaneousTCI-UpdateList1-r16,
simultaneousTCI-UpdateList2-r16,* *simultaneousSpatial-UpdatedList1-r16,
or simultaneousSpatial-UpdatedList2-r16,* the UE is not configured with
*dl-OrJointTCI-StateList* or *ul-TCI-StateList* in any CC within the
same band in the CC list.

The UE receives an activation command, as described in clause 6.1.3.14
of \[10, TS 38.321\], or 6.1.3.47 of \[10, TS 38.321\], used to map up
to 8 TCI states and/or pairs of TCI states, with one TCI state for DL
channels/signals and/or one TCI state for UL channels/signals to the
codepoints of the DCI field *\'Transmission Configuration Indication\'*
for one or for a set of CCs/DL BWPs. When a set of TCI state IDs are
activated for a set of CCs/DL BWPs and if applicable, for a set of
CCs/UL BWPs, where the applicable list of CCs is determined by the
indicated CC in the activation command, the same set of TCI state IDs
are applied for all DL and/or UL BWPs in the indicated CCs. If the
activation command maps *TCI-State(s)* and/or *TCI-UL-State(s)* to only
one TCI codepoint, the UE shall apply the indicated *TCI-State(s)*
and/or *TCI-UL-State(s)* to one or to a set of CCs /DL BWPs, and if
applicable, to one or to a set of CCs /UL BWPs once the indicated
mapping for the one single TCI codepoint is applied as described in
\[11, TS 38.133\].

When the *bwp-id* or *cell* for QCL-TypeA/D source RS in a QCL-Info of
the TCI state is not configured, the UE assumes that QCL-TypeA/D source
RS is configured in the CC/DL BWP where TCI state applies.

When *tci-PresentInDCI* is set as \'enabled\' or *tci-PresentDCI-1-2* is
configured for the CORESET, a UE configured with
*dl-OrJointTCI-StateList* with activated *TCI-State* or
*ul-TCI-StateList* with activated *TCI-UL-State* receives DCI format
1_1/1_2/1_3 providing indicated *TCI-State(s)* and/or *TCI-UL-State(s)*
for a CC or all CCs in the same CC list configured by
*simultaneousU-TCI-UpdateList1-r17, simultaneousU-TCI-UpdateList2-r17,
simultaneousU-TCI-UpdateList3-r17, simultaneousU-TCI-UpdateList4-r17*.
The DCI format 1_3 provides indicated *TCI state(s)*
and/or* TCI-UL-State(s)* for the CC(s) in a *scheduledCellListDCI-1-3*
if the UE is scheduled by the DCI format 1_3 to receive PDSCH at least
on one serving cell in the *scheduledCellListDCI-1-3*. The DCI format
1_1/1_2 can be with or without, if applicable, DL assignment. If the DCI
format 1_1/1_2 is without DL assignment, the UE can assume the
following:

\- CS-RNTI is used to scramble the CRC for the DCI

\- The values of the following DCI fields are set as follows:

\- RV = all \'1\'s

\- MCS = all \'1\'s

\- NDI = 0

\- Set to all \'0\'s for FDRA Type 0, or all \'1\'s for FDRA Type 1, or
all \'0\'s for dynamicSwitch (same as in Table 10.2-4 of \[6, TS
38.213\]).

After a UE receives an initial higher layer configuration of
*dl-OrJointTCI-StateList* where more than one *TCI-State* can be used as
an indicated TCI state and before application of an indicated TCI state
from the configured TCI states:

\- The UE assumes that DM-RS of PDSCH and DM-RS of PDCCH that are not
received during the RACH procedure, and the CSI-RS applying the
indicated TCI state are quasi co-located with the reference signal(s) in
the *CandidateTCI-State* indicated in the LTM Cell Switch Command MAC CE
\[10, 38.321\] if applicable, otherwise.

\- The UE assumes that DM-RS of PDSCH and DM-RS of PDCCH and the CSI-RS
applying the indicated TCI state are quasi co-located with the SS/PBCH
block the UE identified during the initial access procedure

After a UE receives an initial higher layer configuration of
*dl-OrJointTCI-StateList* where more than one *TCI-State* can be used as
an indicated TCI state or an initial higher layer configuration of
*ul-TCI-StateList* where more than one *TCI-UL-State* can be used as an
indicated TCI state and before application of an indicated TCI state
from the configured TCI states:

\- The UE determines the UL TX spatial filter, if applicable, for
dynamic-grant based PUSCH that is not transmitted during the RACH
procedure and configured-grant based PUSCH and PUCCH that are not
transmitted during the RACH procedure, and for SRS applying the
indicated TCI state, from the *CandidateTCI-State* or
*CandidateTCI-UL-State* indicated in the LTM Cell Switch Command MAC CE
\[10, 38.321\] if applicable, otherwise.

\- The UE assumes that the UL TX spatial filter, if applicable, for
dynamic-grant and configured-grant based PUSCH and PUCCH, and for SRS
applying the indicated TCI state, is the same as that for a PUSCH
transmission scheduled by a RAR UL grant or a MsgA PUSCH transmission
during the initial access procedure

After a UE receives a higher layer configuration of
*dl-OrJointTCI-StateList* where more than one *TCI-State* can be used as
an indicated TCI state as part of a Reconfiguration with sync procedure
as described in \[12, TS 38.331\] and before applying an indicated TCI
state from the configured TCI states:

\- The UE assumes that DM-RS of PDSCH and DM-RS of PDCCH, and the CSI-RS
applying the indicated TCI state are quasi co-located with the SS/PBCH
block or the CSI-RS resource the UE identified during the random access
procedure initiated by the Reconfiguration with sync procedure as
described in \[12, TS 38.331\].

After a UE receives a higher layer configuration of
*dl-OrJointTCI-StateList* where more than one *TCI-State* can be used as
an indicated TCI state or a higher layer configuration of
*ul-TCI-StateList* where more than one *TCI-UL-State* can be used as an
indicated TCI state as part of a Reconfiguration with sync procedure as
described in \[12, TS 38.331\] and before applying an indicated TCI
state from the configured TCI states:

\- The UE assumes that the UL TX spatial filter, if applicable, for
dynamic-grant and configured-grant based PUSCH and PUCCH, and for SRS
applying the indicated TCI state, is the same as that for a PUSCH
transmission scheduled by a RAR UL grant or a MsgA PUSCH transmission
during random access procedure initiated by the Reconfiguration with
sync procedure as described in \[12, TS 38.331\].

If a UE receives a higher layer configuration of
*dl-OrJointTCI-StateList* where only one *TCI-State* can be used as an
indicated TCI state*,* the UE obtains the QCL assumptions from that TCI
state for DM-RS of PDSCH and DM-RS of PDCCH, and the CSI -RS applying
the indicated TCI state.

If a UE receives a higher layer configuration of
*dl-OrJointTCI-StateList* where only one *TCI-State* can be used as an
indicated TCI state or a higher layer configuration of
*ul-TCI-StateList* where only one *TCI-UL-State* can be used as an
indicated TCI state, the UE determines an UL TX spatial filter, if
applicable, from that TCI state for dynamic-grant and configured-grant
based PUSCH and PUCCH, and SRS applying the indicated TCI state.

When a UE configured with *dl-OrJointTCI-StateList* would transmit a
PUCCH with positive HARQ-ACK or a PUSCH with positive HARQ-ACK
corresponding to the DCI carrying the TCI State indication and without
DL assignment, or corresponding to one or more PDSCH(s) scheduled by the
DCI carrying the TCI State indication, and if the indicated TCI State(s)
is/are different from the previously indicated one(s), the indicated
*TCI-State(s)* and/or *TCI-UL-State(s)* should be applied starting from
the first slot that is at least $\ beamAppTime$ symbols after the last
symbol of the PUCCH or the PUSCH, and if the UE receives more than one
indicated TCI state for a CC/BWP to be applied starting from the first
slot that is at least $\ beamAppTime$ symbols after the last symbol of
the PUCCH or the PUSCH, the indicated TCI state carried in the latest
DCI, for the corresponding *coresetPoolIndex* value when applicable, in
time corresponding to positive HARQ-ACK value is applied. The first slot
and the $\ beamAppTime$ symbols are both determined on the active BWP
with the smallest SCS among the BWP(s) from the CCs applying the
indicated *TCI-State(s)* or *TCI-UL-State(s)* that are active at the end
of the PUCCH or the PUSCH carrying the positive HARQ-ACK. The indicated
*TCI-State(s)* or *TCI-UL-State(s)* is/are based on the activated TCI
states in each slot where the UE applies the indicated *TCI-State(s)* or
*TCI-UL-State(s)* to DL channel(s)/signal(s) or UL channel(s)/signal(s).

When a UE is configured with *dl-OrJointTCI-StateList* and is having one
indicated *TCI-state*, and if the UE is configured with
*unifiedTCI-StateType* set as 'separate', and if the UE receives a TCI
codepoint mapped with either of {*TCI-State*, *TCI-UL-State*}, the UE
shall update the one indicated {*TCI-State*, *TCI-UL-State}* and
maintain the other {*TCI-State*, *TCI-UL-State*} that is not updated by
the received TCI codepoint.

When a UE is configured with *dl-OrJointTCI-StateList* and is having two
indicated *TCI-states*, if the UE receives a TCI codepoint mapped with a
sub-set of first and second *TCI-State(s)* and/or a sub-set of first and
second *TCI-UL-State(s)*, the UE shall update the first/second
*TCI-State(s)* and/or first/second *TCI-UL-State(s)* mapped to the TCI
codepoint, when applicable, and keep the previously indicated
first/second *TCI-State(s)* and/or first/second *TCI-UL-State(s)* that
is/are not updated by the TCI codepoint.

If a UE is configured with *pdsch-TimeDomainAllocationListForMultiPDSCH*
in which one or more rows contain multiple *SLIV*s for PDSCH on a DL BWP
of a serving cell, and the UE is receiving a DCI carrying the
*TCI-State* indication and without DL assignment, the UE does not expect
that the number of indicated *SLIV*s in the row of the
*pdsch-TimeDomainAllocationListForMultiPDSCH* by the DCI is more than
one.

If the UE is configured with *PDCCH-Config* that contains two different
values of *coresetPoolIndex* in *ControlResourceSet*, the UE receives an
activation command associated with each *coresetPoolIndex*, as described
in clause 6.1.3.14 of \[10, TS 38.321\] or 6.1.3.47 of \[10, TS
38.321\], used to map up to 8 TCI states and/or pairs of TCI states,
with one TCI state for DL channels/signals and/or one TCI state for UL
channels/signals to the codepoints of the DCI field *\'Transmission
Configuration Indication\'* in one CC/DL BWP. When a set of TCI state
IDs are activated for a *coresetPoolIndex*, the activated TCI states
corresponding to one *coresetPoolIndex* is associated with the serving
cell physical cell ID and activated TCI states corresponding to another
*coresetPoolIndex* can be associated with another physical cell ID, if
the UE is further configured with *SSB-MTC-AddtionalPCI*.

When a UE supports two TCI states in a codepoint of the DCI field
\'*Transmission Configuration Indication\'* the UE may receive an
activation command, as described in clause 6.1.3.24 of \[10, TS
38.321\], the activation command is used to map up to 8 combinations of
one or two TCI states to the codepoints of the DCI field *\'Transmission
Configuration Indication\'*. The UE is not expected to receive more than
8 TCI states in the activation command.

If the UE is provided a set of serving cells by
*mc-DCI-SetOfCellsToAddModList-r18*, the UE does not expect to receive
an activation command mapping two *TCI-States* and/or two
*TCI-UL-States* to only one TCI codepoint, or to be provided
*PDCCH-Config* that is associated with two different values of
*coresetPoolIndex* for scheduling on a serving cell from the set of
serving cells.

When a UE configured with *dl-OrJointTCI-StateList* supports
*tci-JointTCI-UpdateMultiActiveTCI-PerCC-r18*, the UE may receive an
activation command, as described in clause 6.1.3.70 of \[10, TS
38.321\], the activation command is used to map up to 8 sets of TCI
states to the codepoints of the DCI field \'Transmission Configuration
Indication\' for one or for a set of CCs/DL BWPs, and if applicable, for
one or for a set of CCs/UL BWPs, where each set is comprised of up to
two TCI state(s) for DL and UL signals/channels.

When a UE configured with *dl-OrJointTCI-StateList* supports
*tci-SeparateTCI-UpdateMultiActiveTCI-PerCC-r18*, the UE may receive an
activation command, as described in clause 6.1.3.71 of \[10, TS
38.321\], the activation command is used to map up to 8 sets of TCI
states to the codepoints of the DCI field \'Transmission Configuration
Indication\' for one or for a set of CCs/DL BWPs, and if applicable, for
one or for a set of CCs/UL BWPs, where each set is comprised of up to
two TCI state(s) for DL channels/signals and up to two TCI state(s) for
UL channels/signals.

When the DCI field *\'Transmission Configuration Indication\'* is
present in DCI format 1_2 and when the number of codepoints S in the DCI
field *\'Transmission Configuration Indication\'* of DCI format 1_2 is
smaller than the number of TCI codepoints that are activated by the
activation command, as described in clauses 6.1.3.14, 6.1.3.24,
6.1.3.47, 6.1.3.70 and 6.1.3.71 of \[10, TS 38.321\], only the first S
activated codepoints are applied for DCI format 1_2.

When the UE would transmit a PUCCH with HARQ-ACK information in slot *n*
corresponding to the PDSCH carrying the activation command, the
indicated mapping between TCI states and codepoints of the DCI field
*\'Transmission Configuration Indication\'* should be applied starting
from the first slot that is after
slot$\ n + {3N}_{slot}^{subframe,µ} + {\frac{2^{\mu}}{2^{\mu_{K_{mac}}}} \bullet k}_{mac}$
where *μ* is the SCS configuration for the PUCCH and $\mu_{K_{mac}}\ $is
the subcarrier spacing configuration for $k_{mac}$ with a value of 0 for
frequency range 1 and for FR2-NTN, and $k_{mac}$ is provided by *K-Mac*
or $k_{mac} = 0$ if *K-Mac* is not provided. If *tci-PresentInDCI* is
set to \'enabled\' or *tci-PresentDCI-1-2* is configured for the CORESET
scheduling the PDSCH, and the time offset between the reception of the
DL DCI and the corresponding PDSCH is equal to or greater than
*timeDurationForQCL* if applicable, after a UE receives an initial
higher layer configuration of TCI states and before reception of the
activation command,

\- the UE assumes that DM-RS of ports of PDSCH of a serving cell are
quasi co-located with the reference signal(s) in the
*CandidateTCI-State* indicated in the LTM Cell Switch Command MAC CE
\[10, 38.321\], except during RACH procedure for RACH-based LTM, if
applicable, otherwise

\- the UE may assume that the DM-RS ports of PDSCH of a serving cell are
quasi co-located with the SS/PBCH block determined in the initial access
procedure with respect to *qcl-Type* set to \'typeA\', and when
applicable, also with respect to *qcl-Type* set to \'typeD\'.

If a UE is configured with the higher layer parameter *tci-PresentInDCI*
that is set as \'enabled\' for the CORESET scheduling a PDSCH, the UE
assumes that the TCI field is present in the DCI format 1_1 or format
1_3 of the PDCCH transmitted on the CORESET. If a UE is configured with
the higher layer parameter *tci-PresentDCI-1-2* for the CORESET
scheduling the PDSCH, the UE assumes that the TCI field with a DCI field
size indicated by *tci-PresentDCI-1-2* is present in the DCI format 1_2
of the PDCCH transmitted on the CORESET. If a UE is configured with the
higher layer parameter *tci-PresentInDCI* that is set as \'enabled\' for
the CORESET scheduling the multicast PDSCH, the UE assumes that the TCI
field is present in the DCI format 4_2 of the PDCCH transmitted on the
CORESET. If the PDSCH is scheduled by a DCI format not having the TCI
field present, and the time offset between the reception of the DL DCI
and the corresponding PDSCH of a serving cell is equal to or greater
than a threshold *timeDurationForQCL* if applicable, where the threshold
is based on reported UE capability \[13, TS 38.306\], for determining
PDSCH antenna port quasi co-location, the UE assumes that the TCI state
or the QCL assumption for the PDSCH is identical to the TCI state or QCL
assumption whichever is applied for the CORESET used for the PDCCH
transmission within the active BWP of the serving cell.

When a UE is configured with both *sfnSchemePDCCH* and *sfnSchemePDSCH*
scheduled by DCI format 1_0 or by DCI format 1_1/1_2, if the time offset
between the reception of the DL DCI and the corresponding PDSCH of a
serving cell is equal to or greater than a threshold
*timeDurationForQCL* if applicable:

\- if the UE supports *sfn-DefaultDL-BeamSetup-r17* for DCI scheduling
without TCI field, the UE assumes that the TCI state(s) or the QCL
assumption(s) for the PDSCH is identical to the TCI state(s) or QCL
assumption(s) whichever is applied for the CORESET used for the
reception of the DL DCI within the active BWP of the serving cell
regardless of the number of active TCI states of the CORESET. If the UE
does not support *sfn-SchemeA-DynamicSwitching-r17* or
*sfn-SchemeB-DynamicSwitching-r17*, the UE should be activated with the
CORESET with two TCI states.

\- else if the UE does not support *sfn-DefaultDL-BeamSetup-r17* for DCI
scheduling without TCI field, the UE shall expect TCI field present when
scheduled by DCI format 1_1/1_2.

When a UE is configured with *sfnSchemePDSCH* and *sfnSchemePDCCH* is
not configured, when scheduled by DCI format 1_1/1_2, if the time offset
between the reception of the DL DCI and the corresponding PDSCH of a
serving cell is equal to or greater than a threshold
*timeDurationForQCL* if applicable, the UE shall expect TCI field
present.

For PDSCH scheduled by DCI format 1_0 or by DCI format 1_1/1_2 without
TCI field, when a UE is configured with *sfnSchemePDCCH* set to
\'sfnSchemeA\' and *sfnSchemePDSCH* is not configured, and there is no
TCI codepoint with two TCI states in the activation command, and if the
time offset between the reception of the DL DCI and the corresponding
PDSCH is equal or larger than the threshold *timeDurationForQCL* if
applicable and the CORESET which schedules the PDSCH is indicated with
two TCI states, the UE assumes that the TCI state or the QCL assumption
for the PDSCH is identical to the first TCI state or QCL assumption
which is applied for the CORESET used for the PDCCH transmission within
the active BWP of the serving cell.

If a UE is not provided *dl-OrJointTCI-StateList-r17*, and if a PDSCH is
scheduled by a DCI format having the TCI field present, the TCI field in
DCI in the scheduling component carrier points to the activated TCI
states in the scheduled component carrier or DL BWP, the UE shall use
the *TCI-State* according to the value of the \'*Transmission
Configuration Indication*\' field in the detected PDCCH with DCI for
determining PDSCH antenna port quasi co-location. The UE may assume that
the DM-RS ports of PDSCH of a serving cell are quasi co-located with the
RS(s) in the TCI state with respect to the QCL type parameter(s) given
by the indicated TCI state if the time offset between the reception of
the DL DCI and the corresponding PDSCH is equal to or greater than a
threshold *timeDurationForQCL*, where the threshold is based on reported
UE capability \[13, TS 38.306\]. For a single slot PDSCH, the indicated
TCI state(s) should be based on the activated TCI states in the slot
with the scheduled PDSCH. For a multi-slot PDSCH or the UE is configured
with higher layer parameter
*pdsch-TimeDomainAllocationListForMultiPDSCH*, the indicated TCI
state(s) should be based on the activated TCI states in the first slot
with the scheduled PDSCH(s), and UE shall expect the activated TCI
states are the same across the slots with the scheduled PDSCH(s). When
the UE is configured with CORESET associated with a search space set for
cross-carrier scheduling and the UE is not configured with
*enableDefaultBeamForCCS*, or when the UE is configured with CORESET
associated with a search space set for DCI format 1_3 and the UE is not
configured with *enabledDefaultBeamForMultiCellScheduling,* the UE
expects *tci-PresentInDCI* is set as \'enabled\' or *tci-PresentDCI-1-2*
is configured for the CORESET, and if one or more of the TCI states
configured for the serving cell scheduled by the search space set
contains *qcl-Type* set to \'typeD\', the UE expects the time offset
between the reception of the detected PDCCH in the search space set and
a corresponding PDSCH is larger than or equal to the threshold
*timeDurationForQCL.*

Independent of the configuration of *tci-PresentInDCI* and
*tci-PresentDCI-1-2* in RRC connected mode, if the UE is not provided
*dl-OrJointTCI-StateList-r17*, and if the offset between the reception
of the DL DCI and the corresponding PDSCH is less than the threshold
*timeDurationForQCL* and at least one configured TCI state for the
serving cell of scheduled PDSCH contains *qcl-Type* set to \'typeD\',

\- the UE may assume that the DM-RS ports of PDSCH(s) of a serving cell
are quasi co-located with the RS(s) with respect to the QCL parameter(s)
used for PDCCH quasi co-location indication of the CORESET associated
with a monitored search space with the lowest *controlResourceSetId* in
the latest slot in which one or more CORESETs within the active BWP of
the serving cell are monitored by the UE. In this case, if the
*qcl-Type* is set to \'typeD\' of the PDSCH DM-RS is different from that
of the PDCCH DM-RS with which they overlap in at least one symbol, the
UE is expected to prioritize the reception of PDCCH associated with that
CORESET. This also applies to the intra-band CA case (when PDSCH and the
CORESET are in different component carriers).

\- If a UE is configured with
*enableDefaultTCI-StatePerCoresetPoolIndex* and the UE is configured by
higher layer parameter *PDCCH-Config* that contains two different values
of *coresetPoolIndex* in different *ControlResourceSets,*

\- the UE may assume that the DM-RS ports of PDSCH associated with a
value of *coresetPoolIndex* of a serving cell are quasi co-located with
the RS(s) with respect to the QCL parameter(s) used for PDCCH quasi
co-location indication of the CORESET associated with a monitored search
space with the lowest *controlResourceSetId* among CORESETs, which are
configured with the same value of *coresetPoolIndex* as the PDCCH
scheduling that PDSCH, in the latest slot in which one or more CORESETs
associated with the same value of *coresetPoolIndex* as the PDCCH
scheduling that PDSCH within the active BWP of the serving cell are
monitored by the UE. In this case, if the \'QCL-TypeD\' of the PDSCH
DM-RS is different from that of the PDCCH DM-RS with which they overlap
in at least one symbol and they are associated with same value of
*coresetPoolIndex*, the UE is expected to prioritize the reception of
PDCCH associated with that CORESET. This also applies to the intra-band
CA case (when PDSCH and the CORESET are in different component
carriers).

\- If a UE is configured with *enableTwoDefaultTCI-States*, and at least
one TCI codepoint indicates two TCI states, the UE may assume that the
DM-RS ports of PDSCH or PDSCH transmission occasions of a serving cell
are quasi co-located with the RS(s) with respect to the QCL parameter(s)
associated with the TCI states corresponding to the lowest codepoint
among the TCI codepoints containing two different TCI states. When the
UE is configured by higher layer parameter *repetitionScheme* set to
\'tdmSchemeA\' or is configured with higher layer parameter
*repetitionNumber*, and the offset between the reception of the DL DCI
and the first PDSCH transmission occasion is less than the threshold
*timeDurationForQCL,* the mapping of the TCI states to PDSCH
transmission occasions is determined according to clause 5.1.2.1 by
replacing the indicated TCI states with the TCI states corresponding to
the lowest codepoint among the TCI codepoints containing two different
TCI states based on the activated TCI states in the slot with the first
PDSCH transmission occasion. In this case, if the \'QCL-TypeD\' in both
of the TCI states corresponding to the lowest codepoint among the TCI
codepoints containing two different TCI states is different from that of
the PDCCH DM-RS with which they overlap in at least one symbol, the UE
is expected to prioritize the reception of PDCCH associated with that
CORESET. This also applies to the intra-band CA case (when PDSCH and the
CORESET are in different component carriers)

\- If a UE is not configured with *sfnSchemePDSCH*, and the UE is
configured with *sfnSchemePDCCH* set to \'sfnSchemeA\' and there is no
TCI codepoint with two TCI states in the activation command and the
CORESET associated with a monitored search space with the lowest CORESET
ID in the latest slot is indicated with two TCI states, the UE may
assume that the DM-RS ports of PDSCH of a serving cell are quasi
co-located with the RS(s) with respect to the QCL parameter(s)
associated with the first TCI state of two TCI states indicated for the
CORESET. In this case, if the *qcl-Type* is set to \'typeD\' of the
PDSCH DM-RS is different from that of the PDCCH DM-RS with which they
overlap in at least one symbol, the UE is expected to prioritize the
reception of PDCCH associated with that CORESET with single active TCI
state. This also applies to the intra-band CA case (when PDSCH and the
CORESET are in different component carriers).

\- In all cases above, if none of configured TCI states for the serving
cell of scheduled PDSCH is configured with *qcl-Type* set to \'typeD\',
the UE shall obtain the other QCL assumptions from the indicated TCI
state(s) for its scheduled PDSCH irrespective of the time offset between
the reception of the DL DCI and the corresponding PDSCH.

Independent of the configuration of *tci-PresentInDCI* and
*tci-PresentDCI-1-2* in RRC connected mode, if the UE is provided
*dl-OrJointTCI-StateList-r17*, and if the offset between the reception
of the DL DCI and the corresponding PDSCH is less than the threshold
*timeDurationForQCL* and at least one configured TCI state for the
serving cell of scheduled PDSCH contains *qcl-Type* set to \'typeD\',
regardless of configuration of *followUnifiedTCI-State*,

\- if the indicated TCI state is associated with the PCI of the serving
cell, the indicated TCI state is applied to PDSCH reception.

\- if the indicated TCI state is associated with a PCI different from
the serving cell, the UE may assume that the DM-RS ports of PDSCH(s) of
a serving cell are quasi co-located with the RS(s) with respect to the
QCL parameter(s) used for PDCCH quasi co-location indication of the
CORESET associated with a monitored search space with the lowest
*controlResourceSetId* in the latest slot in which one or more CORESETs
within the active BWP of the serving cell are monitored by the UE. In
the CA case, if the \'QCL-TypeD\' of the PDSCH DM-RSs from respective
CCs in a band are different in a slot, the QCL-TypeD assumption of the
PDSCH DM-RS in the CC with lowest CC ID in the band is applied to all
the PDSCH DM-RSs in the CCs in the band. In this case, if the *qcl-Type*
is set to \'typeD\' of the PDSCH DM-RS is different from that of the
PDCCH DM-RS with which they overlap in at least one symbol, the UE is
expected to prioritize the reception of PDCCH associated with that
CORESET. This also applies to the intra-band CA case (when PDSCH and the
CORESET are in different component carriers).

Independent of the configuration of *tci-PresentInDCI* and
*tci-PresentDCI-1-2* in RRC connected mode, for a UE that is provided
*dl-OrJointTCI-StateList-r17*, if a PDSCH of a serving cell is scheduled
by a CORESET that does not follow the indicated TCI state, and if the
time offset between the reception of the DL DCI and the corresponding
PDSCH is equal to or greater than a threshold *timeDurationForQCL* if
applicable, the indicated TCI state is applied to the PDSCH of the
serving cell..

If the PDCCH carrying the scheduling DCI is received on one component
carrier, and a PDSCH scheduled by that DCI is on another component
carrier:

\- The *timeDurationForQCL* is determined based on the subcarrier
spacing of the scheduled PDSCH. If µ~PDCCH~ \< µ~PDSCH~ an additional
timing delay $d\frac{2^{\mu_{PDSCH}}}{2^{\mu_{PDCCH}}}$ is added to the
*timeDurationForQCL*, where *d* is defined in 5.2.1.5.1a-1, otherwise
*d* is zero;

\- When the UE is configured with *enableDefaultBeamForCCS* or
*enabledDefaultBeamForMultiCellScheduling*, if the offset between the
reception of the DL DCI and the corresponding PDSCH is less than the
threshold *timeDurationForQCL,* or if the DL DCI does not have the TCI
field present, the UE obtains its QCL assumption for the scheduled PDSCH
from the activated TCI state with the lowest ID applicable to PDSCH in
the active BWP of the scheduled cell.

A UE that has indicated a capability
*beamCorrespondenceWithoutUL-BeamSweeping* set to \'supported\', as
described in \[13, TS 38.306\], can determine a spatial domain filter to
be used while performing the applicable channel access procedures
described in \[16, TS 37.213\] prior to a UL transmission on the channel
as follows:

\- if UE is indicated with an SRI corresponding to the UL transmission,
the UE may use a spatial domain filter that is same as the spatial
domain transmission filter associated with the indicated SRI,

\- if UE is configured with *SRS-spatialRelationInfo* for the UL
transmission, the UE may use a spatial domain filter that is same as the
spatial domain filter associated with *referenceSignal* in the
corresponding *SRS-spatialRelationInfo*,

\- if UE is configured with *TCI-State* in *dl-OrJointTCI-StateList* or
*TCI-UL-State* in *ul-TCI-StateList*, the UE may use a spatial domain
filter that is same as the spatial domain receive filter the UE may use
to receive the DL reference signal associated with the indicated TCI
state.

When the PDCCH reception includes two PDCCH from two respective search
space sets, as described in clause 10.1 of \[6, TS 38.213\], for the
purpose of determining the time offset between the reception of the DL
DCI and the corresponding PDSCH, the PDCCH candidate that ends later in
time is used. When the PDCCH reception includes two PDCCH candidates
from two respective search space sets, as described in clause 10.1 of
\[6, TS 38.213\], for the configuration of *tci-PresentInDCI* or
*tci-PresentDCI-1-2*, the UE expects the same configuration in the first
and second CORESETs associated with the two PDCCH candidates; and if the
PDSCH is scheduled by a DCI format not having the TCI field present and
if the scheduling offset is equal to or larger than
*timeDurationForQCL,* if applicable, PDSCH QCL assumption is based on
the CORESET with lower ID among the first and second CORESETs associated
with the two PDCCH candidates.

For a periodic CSI-RS resource in an *NZP-CSI-RS-ResourceSet* configured
with higher layer parameter *trs-Info*, the UE shall expect that a
TCI-State indicates one of the following quasi co-location type(s):

\- \'typeC\' with an SS/PBCH block and, when applicable, \'typeD\' with
the same SS/PBCH block where SS/PBCH block may have a PCI different from
the PCI of the serving cell. The UE can assume center frequency, SCS,
SFN offset are the same for SS/PBCH block from the serving cell and
SS/PBCH block having a PCI different from the serving cell, or

\- \'typeC\' with an SS/PBCH block and, when applicable,\'typeD\' with a
CSI-RS resource in an *NZP-CSI-RS-ResourceSet* configured with higher
layer parameter *repetition,* where SS/PBCH block may have a PCI
different from the PCI of the serving cell. The UE can assume center
frequency, SCS, SFN offset are the same for SS/PBCH block from the
serving cell and SS/PBCH block having a PCI different from the serving
cell.

For periodic/semi-persistent CSI-RS, if the UE is configured with
*dl-OrJointTCI-StateList,* the UE can assume that the indicated
*TCI-State* is not applied.

For an aperiodic CSI-RS resource in an *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info,* the UE shall expect
that a *TCI-State* indicates *qcl-Type* set to \'typeA\' with a periodic
CSI-RS resource in a *NZP-CSI-RS-ResourceSet* configured with higher
layer parameter *trs-Info* and, when applicable, *qcl-Type* set to
\'typeD\' with the same periodic CSI-RS resource.

For a CSI-RS resource in an *NZP-CSI-RS-ResourceSet* configured without
higher layer parameter *trs-Info* and without the higher layer parameter
*repetition*, the UE shall expect that a TCI-State indicates one of the
following quasi co-location type(s):

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with the same CSI-RS resource, or

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with an SS/PBCH block, where SS/PBCH block may have a PCI
different from the PCI of the serving cell. The UE can assume center
frequency, SCS, SFN offset are the same for SS/PBCH block from the
serving cell and SS/PBCH block having a PCI different from the serving
cell, or

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *repetition*, or

\- \'typeB\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* when \'typeD\' is not
applicable.

For a CSI-RS resource in an *NZP-CSI-RS-ResourceSet* configured with
higher layer parameter *repetition,* the UE shall expect that a
TCI-State indicates one of the following quasi co-location type(s):

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with the same CSI-RS resource, or

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *repetition*, or

\- \'typeC\' with an SS/PBCH block and, when applicable, \'typeD\' with
the same SS/PBCH block, the reference RS may additionally be an SS/PBCH
block having a PCI different from the PCI of the serving cell. The UE
can assume center frequency, SCS, SFN offset are the same for SS/PBCH
block from the serving cell and SS/PBCH block having a PCI different
from the serving cell.

For the DM-RS of PDCCH, if the UE is not configured with
*dl-OrJointTCI-StateList,* the UE shall expect that a *TCI-State*
indicates one of the following quasi co-location type(s):

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with the same CSI-RS resource, or

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with a CSI-RS resource in an *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *repetition*, or

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured without higher layer parameter trs-Info and without higher
layer parameter *repetition* and, when applicable, \'typeD\' with the
same CSI-RS resource.

When a UE is configured with *sfnSchemePdcch* set to \'sfnSchemeA\', and
CORESET is activated with two TCI states or is configured with
*applyIndicatedTCI-State* set to \'both\', the UE shall assume that the
DM-RS port(s)of the PDCCH in the CORESET is quasi co-located with the
DL-RSs of the two TCI states. When a UE is configured with
*sfnSchemePdcch* set to \'sfnSchemeB\', and a CORESET is activated with
two TCI states or is configured with *applyIndicatedTCI-State* set to
\'both\', the UE shall assume that the DM-RS port(s)of the PDCCH is
quasi co-located with the DL-RSs of the two TCI states except for quasi
co-location parameters {Doppler shift, Doppler spread} of the second
indicated TCI state.

When a UE is configured by higher layer parameter *cjt-Scheme-PDSCH* and
*dl-OrJointTCI-StateList* and is indicated with two TCI-States applied
for PDSCH reception and reports *twoTCI-StatePDSCH-CJT-TxScheme*:

\- if the UE is configured with *cjtSchemeA*, the UE assumes that PDSCH
DM-RS port(s) are QCLed with the DL RSs of both indicated joint TCI
states with respect to QCL-TypeA.

\- if the UE is configured with *cjtSchemeB*, the UE assumes that PDSCH
DM-RS port(s) are QCLed with the DL RSs of both indicated joint TCI
states with respect to QCL-TypeA except for QCL parameters {Doppler
shift, Doppler spread} of the second indicated joint TCI state.

For the DM-RS of PDSCH, if the UE is not configured with
*dl-OrJointTCI-StateList,* the UE shall expect that a *TCI-State*
indicates one of the following quasi co-location type(s):

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with the same CSI-RS resource*,* or

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with a CSI-RS resource in an *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *repetition*,or

\- typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured without higher layer parameter *trs-Info* and without higher
layer parameter *repetition* and, when applicable, \'typeD\' with the
same CSI-RS resource.

For the DM-RS of PDCCH, if the UE is configured with
*dl-OrJointTCI-StateList,* the UE shall expect that an indicated
*TCI-State* indicates one of the following quasi co-location type(s):

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with the same CSI-RS resource, or

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with a CSI-RS resource in an *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *repetition.*

For the DM-RS of PDSCH, if the UE is configured with
*dl-OrJointTCI-StateList,* the UE shall expect that an indicated
*TCI-State* indicates one of the following quasi co-location type(s):

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with the same CSI-RS resource*,* or

\- \'typeA\' with a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info* and, when applicable,
\'typeD\' with a CSI-RS resource in an *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *repetition.*

When a UE is configured with *sfnSchemePDSCH* set to \'sfnSchemeA\', and
the UE not configured with *dl-OrJointTCI-StateList* is indicated with
two TCI states in a codepoint of the DCI field \'Transmission
Configuration Indication\' in a DCI scheduling a PDSCH or the UE
configured with *dl-OrJointTCI-StateList* is having two indicated TCI
States to be applied to PDSCH, the UE shall assume that the DM-RS
port(s)of the PDSCH is quasi co-located with the DL-RSs of the two TCI
states. When a UE is configured with *sfnSchemePDSCH* set to
\'sfnSchemeB\', and the UE not configured with *dl-OrJointTCI-StateList*
is indicated with two TCI states in a codepoint of the DCI field
\'Transmission Configuration Indication\' in a DCI scheduling a PDSCH or
the UE configured with *dl-OrJointTCI-StateList* is having two indicated
TCI States to be applied to PDSCH, the UE shall assume that the DM-RS
port(s)of the PDSCH is quasi co-located with the DL-RSs of the two TCI
states except for quasi co-location parameters {Doppler shift, Doppler
spread} of the second indicated TCI state.

When a UE is configured with *dl-OrJointTCI-StateList* or *TCI-UL-State*
and is configured by higher layer parameter *PDCCH-Config* that contains
two different values of coresetPoolIndex in *ControlResourceSet*, an
indicated TCI state is specific to a coresetPoolIndex value, when it is
indicated by the DCI field \'Transmission Configuration Indication\' in
DCI format 1_1/1_2 associated with the coresetPoolIndex value.

When a UE is configured with *dl-OrJointTCI-StateList* and is having two
indicated TCI-states, if the UE does not report its capability of
*defaultQCL-TwoTCI* in frequency range 2 and when the offset between the
reception of the scheduling/activation DCI format 1_0/1_1/1_2 and the
scheduled or activated PDSCH reception is less than *timeDurationForQCL*
in frequency range 2, the UE shall apply the first indicated TCI-State
to the scheduled or activated PDSCH reception.

When a UE is configured with *dl-OrJointTCI-StateList*, is configured by
higher layer parameter *PDCCH-Config* that contains two different values
of *coresetPoolIndex* in *ControlResourceSet*, if the UE does not report
its capability of *defaultQCL-PerCORESETPoolIndex* in frequency range 2

\- when the offset between the reception of the scheduling/activation
DCI format 1_0/1_1/1_2 in a CORESET associated with *coresetPoolIndex*
value 0 and the scheduled or activated PDSCH reception is less than
*timeDurationForQCL* in frequency range 2, the UE shall apply the
indicated joint/DL TCI state specific to *coresetPoolIndex* value 0 to
the scheduled or activated PDSCH reception.

\- the UE does not expect that the offset between reception of the
scheduling/activation DCI format 1_0/1_1/1_2 in a CORESET associated
with *coresetPoolIndex* value 1 and scheduled or activated PDSCH
reception is less than *timeDurationForQCL* in frequency range 2.

When a UE is configured with *dl-OrJointTCI-StateList* and is having two
indicated TCI-states:

\- Regardless of the offset between the reception of the scheduling DCI
format 1_0/1_1/1_2 and the scheduled/activated PDSCH reception, if the
UE is in frequency range 1, or the UE reports its capability of
*defaultQCL-TwoTCI* in frequency range 2, or

\- If the UE does not report its capability of *defaultQCL-TwoTCI* in
frequency range 2 and if the scheduling offset between the reception of
the scheduling DCI format 1_0/1_1/1_2 and the scheduled/activated PDSCH
reception is equal to or larger than *timeDurationForQCL*

\- The UE can be configured by higher layer parameter
*applyIndicatedTCI-StateDCI-1-0* to indicate whether the first, the
second, or both of the indicated TCI-state(s) is/are applied to PDSCH
reception scheduled or activated by DCI format 1_0. The UE can be
configured with *applyIndicatedTCI-StateDCI-1-0* with value *both* only
when the UE is configured with *cjt-Scheme-PDSCH* and the UE reports
*twoTCI-StatePDSCH-CJT-TxScheme* or the UE is configured with
*sfnSchemePdsch*. In that case, the UE shall apply both indicated
TCI-states to PDSCH reception scheduled or activated by DCI format 1_0
on a search space other than Type0/0A/2 CSS on CORESET#0.

\- If the UE is not configured with *applyIndicatedTCI-StateDCI-1-0*,
the first indicated TCI-state is applied to PDSCH reception scheduled or
activated by DCI format 1_0.

\- When the UE is configured with *tci-SelectionPresentInDCI* jointly
for both DCI formats 1_1 and 1_2 in the same DL BWP, and when the UE
receives a DCI format 1_1/1_2 that schedules or activates PDSCH
reception, the UE shall determine the indicated joint/DL TCI state(s)
for the PDSCH reception according to the following:

\- If the DCI format 1_1/1_2 indicates codepoint \"00\" for the DCI
field \'TCI selection\', the UE shall apply the first one of two
indicated joint/DL TCI states to all PDSCH DM-RS port(s) of
corresponding PDSCH transmission occasion(s) scheduled or activated by
the DCI format 1_1/1_2.

\- If the DCI format 1_1/1_2 indicates codepoint \"01\" for the DCI
field \'TCI selection\', the UE shall apply the second one of two
indicated joint/DL TCI states to all PDSCH DM-RS port(s) of
corresponding PDSCH transmission occasion(s) scheduled or activated by
the DCI format 1_1/1_2.

\- If the DCI format 1_1/1_2 indicates codepoint \"10\" for the DCI
field \'TCI selection\', the UE shall apply both indicated joint/DL TCI
states to the PDSCH reception scheduled or activated by the DCI format
1_1/1_2.

\- If the UE is not configured with *tci-SelectionPresentInDCI* and when
the UE receives a DCI format 1_1/1_2 that schedules/activates PDSCH
reception, the UE shall apply both indicated TCI-States to the scheduled
or activated PDSCH reception.

When a UE is configured with *dl-OrJointTCI-StateList,* is configured by
higher layer parameter *PDCCH-Config* that contains two different values
of *coresetPoolIndex* in *ControlResourceSet* and is having two
indicated TCI-states, when the offset between the reception of the
scheduling/activation DCI format 1_0/1_1/1_2 and the scheduled or
activated PDSCH reception is less than *timeDurationForQCL* in frequency
range 2, and if the PDSCH and a PDCCH overlaps in at least one symbol

\- If the UE does not report its capability of
*defaultQCL-PerCORESETPoolIndex*, and if the \'QCL-TypeD\' of the PDSCH
DMRS is different from that of PDCCH DMRS, the UE is expected to
prioritize the reception of PDCCH. This also applies to the intra-band
CA case (when PDSCH and the PDCCH are in different component carriers).

When a UE is configured with *dl-OrJointTCI-StateList* and is having two
indicated TCI-states, when the offset between the reception of the
scheduling/activation DCI format 1_0/1_1/1_2 and the scheduled or
activated PDSCH reception is less than *timeDurationForQCL* in frequency
range 2, and if the PDSCH and a PDCCH overlaps in at least one symbol

\- If the UE does not report its capability of *defaultQCL-TwoTCI*, and
if the \'QCL-TypeD\' of the PDSCH DMRS is different from any one of
those of PDCCH DMRS, the UE is expected to prioritize the reception of
PDCCH. This also applies to the intra-band CA case (when PDSCH and the
PDCCH are in different component carriers).