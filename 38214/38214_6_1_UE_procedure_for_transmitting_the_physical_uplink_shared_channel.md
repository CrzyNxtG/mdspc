## 6.1 UE procedure for transmitting the physical uplink shared channel

PUSCH transmission(s) can be dynamically scheduled by an UL grant in a
DCI, or the transmission can correspond to a configured grant Type 1 or
Type 2. The configured grant Type 1 PUSCH transmission is
semi-statically configured to operate upon the reception of higher layer
parameter of *configuredGrantConfig* including
*rrc-ConfiguredUplinkGrant* without the detection of an UL grant in a
DCI. The configured grant Type 2 PUSCH transmission is semi-persistently
scheduled by an UL grant in a valid activation DCI according to clause
10.2 of \[6, TS 38.213\] after the reception of higher layer parameter
*configuredGrantConfig* not including *rrc-ConfiguredUplinkGrant*. If
*configuredGrantConfigToAddModList* is configured, more than one
configured grant configuration of configured grant Type 1 and/or
configured grant Type 2 may be active at the same time on an active BWP
of a serving cell.

The UE can be configured with a list of up to 64 *TCI-UL-State*
configurations within the higher layer parameter *BWP-UplinkDedicated.*
Each *TCI-UL-State* configuration contains a parameter for configuring
one reference signal, if applicable, for determining UL TX spatial
filter for dynamic-grant and configured-grant based PUSCH and PUCCH
resource in a CC, and SRS.

If a UE is configured by higher layer parameter *PDCCH-Config* that
contains *ControlResourceSets* with two different values of
*coresetPoolIndex* for the active BWP of a serving cell, or if a UE is
configured with *SSB-MTC-AddtionalPCI* and with *PDCCH-Config* that
contains two different values of *coresetPoolIndex* in
*ControlResourceSet*, and if the UE is configured with *tag2-Id* and is
configured with *dl-OrJointTCI-StateList* or *TCI-UL-State* for a
serving cell, each *TCI-State* or *TCI-UL-State* is associated with a
*tag-Id-ptr* for determining timing adjustment for a corresponding UL
transmission as described in Clause 4.2 of \[6, TS 38.213\]. The UE does
not expect that *TCI-states* or *TCI-UL-States* associated with one
*coresetPoolIndex* to correspond to two TAGs.

For the PUSCH transmission corresponding to a Type 1 configured grant or
a Type 2 configured grant activated by DCI format 0_0 or 0_1, the
parameters applied for the transmission are provided by
*configuredGrantConfig* except for *dataScramblingIdentityPUSCH*,
*txConfig*, *codebookSubset*, *maxRank*, *scaling* of *UCI-OnPUSCH,*
which are provided by *pusch-Config*. A configured grant PUSCH can be
transmitted with at most 4 layers. For the PUSCH transmission
corresponding to a Type 2 configured grant activated by DCI format 0_2,
the parameters applied for the transmission are provided by
*configuredGrantConfig* except for *dataScramblingIdentityPUSCH*,
*txConfig*, *codebookSubsetDCI-0-2*, *maxRankDCI-0-2*, *scaling* of
*UCI-OnPUSCH*, *resourceAllocationType1GranularityDCI-0-2* provided by
*pusch-Config*. If the UE is provided with *transformPrecoder* in
*configuredGrantConfig*, the UE applies the higher layer parameter
*tp-pi2BPSK*, if provided in *pusch-Config*, according to the procedure
described in clause 6.1.4 for the PUSCH transmission corresponding to a
configured grant.

For PUSCH transmissions corresponding to a Type 1 configured grant based
on eight antenna ports, when the higher layer parameter *txConfig* is
set to *'*codebook*'* and when *maxRank* is greater than 4, the
determination of the *precodingAndNumberOfLayers* is based on the
configuration of *maxRank* equal to 4; when the higher layer parameter
*txConfig* is set to *'*nonCodebook*'* and when *L~max~* \[5, TS38.212\]
is greater than 4, the determination of the *srs-ResourceIndicator* is
based on the configuration of *L~max~* equal to 4.

When the UE is configured *dl-OrJointTCI-StateList* or
*ul-TCI-StateList*, the UE shall perform PUSCH transmission
corresponding to a Type 1 configured grant or a Type 2 configured grant
or a dynamic grant according to the spatial relation, if applicable,
with a reference to the RS for determining UL Tx spatial filter. The RS
is determined based on an RS configured with *qcl-Type* set to \'typeD\'
of the indicated *TCI-State* or an RS in the indicated *TCI-UL-State*.
The reference RS in the indicated *TCI-State* can be a CSI-RS resource
in a *NZP-CSI-RS-ResourceSet* configured with higher layer parameter
*repetition*, or a CSI-RS resource in an *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info.* The reference RS in
the indicated *TCI-UL-State* can be a CSI-RS resource in a
*NZP-CSI-RS-ResourceSet* configured with higher layer parameter
*repetition*, a CSI-RS resource in an *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info*, an SRS resource in an
SRS resource set with the higher layer parameter *usage* set to
\'beamManagement\', or SS/PBCH block associated with the same or
different PCI from the PCI of the serving cell. When
*nrofSlotsInCG-Period* is configured for Type 1 configured grant or Type
2 configured grant, HARQ process ID for the first configured PUSCH grant
and each subsequent valid configured PUSCH grant within a *periodicity*
of the configuration is determined as in clause 5.4.1 of \[10, TS
38.321\], where a valid configured PUSCH grant is the one not colliding
with the DL symbol(s) indicated by *tdd-UL-DL-ConfigurationCommon* or
*tdd-UL-DL-ConfigurationDedicated* if provided, and not colliding with a
symbol(s) of an SS/PBCH block with index provided by
*ssb-PositionsInBurst* as described in clause 11.1 of \[6, TS 38.213\].

When a UE is configured with *dl-OrJointTCI-StateList* or *TCI-UL-State*
and is having two indicated TCI-States or TCI-UL-States,

\- a UE having a PUSCH transmission scheduled or activated by DCI format
0_0 should apply the first indicated TCI state to the PUSCH
transmission,

\- a UE configured with a PUSCH transmission corresponding to a Type 1
configured grant is expected to be configured with the higher layer
parameter *applyIndicatedTCI-State* indicating the *first*, the *second*
or *both* of the indicated TCI states to be applied for the PUSCH
transmission. If \'both\' TCI states are indicated, the UE should apply
the first indicated TCI state to the PUSCH transmission occasion(s) or
the PUSCH antenna port(s) associated with the first SRS resource set for
CB/NCB transmission, and the second indicated TCI state to the PUSCH
transmission occasion(s) or the PUSCH antenna port(s) associated with
the second SRS resource set for CB/NCB transmission; otherwise the UE
should apply either the \'first\' or \'second\' indicated TCI state to
all PUSCH transmission occasions.

\- If the UE is configured by higher layer parameter *PDCCH-Config* that
contains two different values of *coresetPoolIndex* in different
*ControlResourceSets* in the active DL BWP, the first and the second
indicated TCI states correspond to the indicated TCI-States or
TCI-UL-States specific to coresetPoolIndex value 0 and value 1,
respectively, and *applyIndicatedTCI-State* does not indicate *both* of
the indicated TCI states to be applied for the PUSCH transmission.

For the PUSCH retransmission scheduled by a PDCCH with CRC scrambled by
CS-RNTI with NDI=1, the parameters in *pusch-Config* are applied for the
PUSCH transmission except for *p0-NominalWithoutGrant, p0-PUSCH-Alpha,
powerControlLoopToUse,* *pathlossReferenceIndex* described in clause 7.1
of \[6, TS 38.213\], *mcs-Table, mcs-TableTransformPrecoder* described
in clause 6.1.4.1 and *transformPrecoder* described in clause 6.1.3.

For a UE configured with two uplinks in a serving cell, PUSCH
retransmission for a TB on the serving cell is not expected to be on a
different uplink than the uplink used for the PUSCH initial transmission
of that TB.

A UE shall upon detection of a PDCCH with a configured DCI format 0_0,
0_1, 0_2 or 0_3 transmit the corresponding PUSCH as indicated by that
DCI unless the UE does not generate a transport block as described in
\[10, TS 38.321\]. Upon detection of a DCI format 0_1 or 0_2 with
\'*UL-SCH indicator*\' set to \'0\' and with a non-zero \'*CSI
request*\' where the associated *reportQuantity* in *CSI-ReportConfig*
set to \'*none*\' for all CSI report(s) triggered by \'*CSI request*\'
in this DCI format 0_1 or 0_2, the UE ignores all fields in this DCI
except the \'*CSI request*\' and the UE shall not transmit the
corresponding PUSCH as indicated by this DCI format 0_1 or 0_2. Upon
detection of a DCI format 0_3 with \'*UL-SCH indicator*\' set to \'0\'
and with a non-zero \'*CSI request*\' where the associated
*reportQuantity* in *CSI-ReportConfig* set to \'*none*\' for all CSI
report(s) triggered by \'*CSI request*\' in this DCI format 0_3, the UE
ignores all fields for the scheduled cell with the smallest serving cell
index in this DCI except the \'*CSI request*\' and the UE shall not
transmit the corresponding PUSCH on the serving cell with the smallest
serving cell index as indicated by this DCI format 0_3.

When the UE is scheduled with multiple PUSCHs on a serving cell by a
DCI, HARQ process ID indicated by this DCI applies to the first PUSCH
not overlapping with a DL symbol indicated by
*tdd-UL-DL-ConfigurationCommon* or *tdd-UL-DL-ConfigurationDedicated* if
provided, or a symbol of an SS/PBCH block with index provided by
*ssb-PositionsInBurst*, HARQ process ID is then incremented by 1 for
each subsequent PUSCH(s) in the scheduled order, with modulo operation
of *nrofHARQ-ProcessesForPUSCH* applied if *nrofHARQ-ProcessesForPUSCH*
is provided, or with modulo operation of 16 applied, otherwise. HARQ
process ID is not incremented for PUSCH(s) not transmitted if at least
one of the symbols indicated by the indexed row of the used resource
allocation table in the slot overlaps with a DL symbol indicated by
*tdd-UL-DL-ConfigurationCommon* or *tdd-UL-DL-ConfigurationDedicated* if
provided, or a symbol of an SS/PBCH block with index provided by
*ssb-PositionsInBurst*. For any HARQ process ID(s) in a given scheduled
cell, the UE is not expected to transmit a PUSCH that overlaps in time
with another PUSCH. Except for the case when a UE is configured by
higher layer parameter *PDCCH-Config* that contains two different values
of *coresetPoolIndex* in *ControlResourceSet* for the active BWP of a
serving cell and PDCCHs that schedule two PUSCHs are associated to
different *ControlResourceSets* having different values of
*coresetPoolIndex* and the UE reports its capability of
*outOfOrderOperationUL-r16* or *outOfOrderOperationUL-r18,* for any two
HARQ process IDs in a given scheduled cell, if the UE is scheduled to
start a first PUSCH transmission starting in symbol *j* by a PDCCH
ending in symbol *i* on a scheduling cell,, the UE is not expected to be
scheduled to transmit a PUSCH starting earlier than the end of the first
PUSCH by a PDCCH that ends later than symbol *i* of the scheduling cell.
When the PDCCH reception includes two PDCCH candidates from two
respective search space sets, as described in clause 10.1 of \[6, TS
38.213\], for the purpose of determining the PDCCH ending in symbol *i*,
the PDCCH candidate that ends later in time is used. The UE is not
expected to be scheduled to transmit another PUSCH by a DCI format 0_0
with CRC scrambled by TC-RNTI, for a given HARQ process with the DCI
received before the end of the expected transmission of the last PUSCH
for that HARQ process if the latter is scheduled by a DCI format 0_0
with CRC scrambled by TC-RNTI or by an UL grant in RA Response. The UE
is not expected to be scheduled to transmit another PUSCH by DCI format
0_0, 0_1, 0_2 or 0_3 scrambled by C-RNTI, CS-RNTI or MCS-C-RNTI for a
given HARQ process with the DCI received before the end of the expected
transmission of the last PUSCH for that HARQ process if the latter is
scheduled by a DCI with CRC scrambled by C-RNTI, CS-RNTI or MCS-C-RNTI.

If a UE is configured by higher layer parameter *PDCCH-Config* that
contains two different values of *coresetPoolIndex* in
*ControlResourceSet* for the active BWP of a serving cell and PDCCHs
that schedule two PUSCHs are associated to different
*ControlResourceSets* having different values of *coresetPoolIndex* and
the UE reports its capability of *outOfOrderOperationUL-r16* or
*outOfOrderOperationUL-r18,* for any two HARQ process IDs in a given
scheduled cell, if the UE is scheduled to start a first PUSCH
transmission starting in symbol *j* by a PDCCH associated with a value
of *coresetPoolIndex* ending in symbol *i*, the UE can be scheduled to
transmit a PUSCH starting earlier than the end of the first PUSCH by a
PDCCH associated with a different value of *coresetPoolIndex* that ends
later than symbol *i*.

When two SRS resource sets are configured in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with higher layer parameter *usage* in *SRS-ResourceSet* set to
\'codebook\' or \'nonCodebook\' and higher layer parameter *sTx-2Panel*
is configured and *PDCCH-Config* contains two different values of
*coresetPoolIndex* in *ControlResourceSet* for the active DL BWP of a
serving cell,

\- two PUSCHs that are fully/partially overlapping in time domain and
are fully/partially/non-overlapping in frequency domain can be
dynamically scheduled by UL grant(s) in DCI(s) and/or scheduled by
configured grant(s) Type 1 or Type 2,

\- if dynamically scheduled by UL grant(s) in DCI(s) or activated by
DCI(s) for configured grant Type 2, the DCI field *SRS Resource Set
Indicator* is not present in each of PDCCH

\- two PUSCHs are associated to different values of *coresetPoolIndex*
where for configured grant Type 1, the association is based on higher
layer parameter *srs-ResourceSetId* in *rrc-ConfiguredUplinkGrant* that
indicates either the first or the second SRS resource set with usage
\'codebook\' or \'nonCodeBook\' in *srs-ResourceSetToAddModList*

\- the UE is not expected to be configured with different number of SRS
resources in the two SRS resource sets

\- the UE expects *maxNrofPorts* in *PTRS-UplinkConfig* to be configured
as one if UL PT-RS is configured.

When a UE is configured with *dl-OrJointTCI-StateList* or *TCI-UL-State*
and two SRS resource sets are configured in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with higher layer parameter *usage* in *SRS-ResourceSet* set to
\'codebook\' or \'noncodebook\', and the higher layer parameter
*multiPanelSchemeSDM* or *multiPanelSchemeSFN* is configured, and the
higher layer parameter *rrc-ConfiguredUplinkGrant* does not contain
*srs-ResourceIndicator2* or *precodingAndNumberOfLayers2*, the PUSCH
transmission occasion(s) is associated with the first SRS resource set
if the first indicated *TCI-States* or *TCI-UL-States* applies and is
associated with the second SRS resource set if the second indicated
*TCI-States* or *TCI-UL-States* applies.

When a UE is configured with *dl-OrJointTCI-StateList* or *TCI-UL-State*
and is having two indicated TCI states, and only one SRS resource set is
configured in *srs-ResourceSetToAddModList* or
*srs-ResourceSetToAddModListDCI-0-2* with higher layer parameter *usage*
in *SRS-ResourceSet* set to \'codebook\' or \'noncodebook\', the PUSCH
transmission occasion(s) scheduled or activated by DCI format 0_1 or 0_2
is associated with the first indicated *TCI-States* or *TCI-UL-States*
if applies or is associated with the second indicated *TCI-States* or
*TCI-UL-States* if applies, as indicated by the higher layer parameter
*applyIndicatedTCI-State* configured by *PUSCH-Config.*

When a UE is configured with higher layer parameter *sTx-2Panel* and
*PDCCH-Config* contains two different values of *coresetPoolIndex* in
*ControlResourceSet* for the active DL BWP of a serving cell,

\- the UE is expected to be configured with two SRS resource sets with
usage \'codebook\' or \'nonCodeBook\' in *srs-ResourceSetToAddModList*

\- if the UE is configured to monitor DCI format 0_2 and there is only
one SRS resource set~~s~~ configured by
*srs-ResourceSetToAddModListDCI-0-2* and associated with usage
\'codebook\' or \'nonCodeBook\', the UE monitors only CORESETs
associated with *coresetPoolIndex* value 0*.*

A UE is not expected to be scheduled by a PDCCH ending in symbol $i$ to
transmit a PUSCH on a given serving cell overlapping in time with a
transmission occasion, where the UE is allowed to transmit a PUSCH with
configured grant according to \[10, TS 38.321\], starting in a symbol
$j$ on the same serving cell if the end of symbol $i$ is not at least
$N_{2}$ symbols and an additional time duration *T~switch~* before the
beginning of symbol $j$, if

\- the UE is not provided *prioLowDG-HighCG* or *prioHighDG-LowCG*, or
the UE is provided *prioLowDG-HighCG* or *prioHighDG-LowCG* and the two
PUSCHs have the same priority index as described in Clause 9 of \[6, TS
38.213\] and

\- the UE is not provided *sTx-2Panel,* or is provided *sTx-2Panel* and
the two PUSCHs are associated with the same *coresetPoolIndex* value.

The value $N_{2}$ in symbols is determined according to the UE
processing capability defined in Clause 6.4, and $N_{2}\ $and the symbol
duration are based on the minimum of the subcarrier spacing
corresponding to the PUSCH with configured grant and the subcarrier
spacing of the PDCCH scheduling the PUSCH. The value *T~switch~* is
defined in Clause 6.4.

If a UE receives an ACK for a given HARQ process in CG-DFI in a PDCCH
ending in symbol *i* to terminate a transport block repetition in a
PUSCH transmission with a configured grant on a given serving cell with
the same HARQ process after symbol *i*, the UE is expected to terminate
the repetition of the transport block in a PUSCH transmission starting
from a symbol *j* if the gap between the end of PDCCH of symbol *i* and
the start of the PUSCH transmission in symbol *j* is equal to or more
than *N2* symbols. The value *N2* in symbols is determined according to
the UE processing capability defined in Clause 6.4, and *N2* and the
symbol duration are based on the minimum of the subcarrier spacing
corresponding to the PUSCH and the subcarrier spacing of the PDCCH
indicating CG-DFI. A UE is not expected to be scheduled by a PDCCH
ending in symbol $i$ to transmit a PUSCH on a given serving cell for a
given HARQ process, if there is a transmission occasion where the UE is
allowed to transmit a PUSCH with configured grant according to \[10, TS
38.321\] with the same HARQ process on the same serving cell starting in
a symbol $j$ after symbol $i$, and if the gap between the end of PDCCH
and the beginning of symbol $j$ is less than $N_{2}$ symbols and an
additional time duration *T~switch~*. The value $N_{2}$ in symbols is
determined according to the UE processing capability defined in clause
6.4, and $N_{2}\ $and the symbol duration are based on the minimum of
the subcarrier spacing corresponding to the PUSCH with configured grant
and the subcarrier spacing of the PDCCH scheduling the PUSCH. The value
*T~switch~* is defined in Clause 6.4.

For PUSCH scheduled by DCI format 0_0 on a cell, the UE shall transmit
PUSCH according to the spatial relation, if applicable, corresponding to
the dedicated PUCCH resource with the lowest ID within the active UL BWP
of the cell, as described in Clause 9.2.1 of \[6, TS 38.213\]. If the
dedicated PUCCH resource with the lowest ID within the active UL BWP of
the cell corresponds to two spatial relations, the UE shall transmit the
PUSCH according to the spatial relation with the lower ID.

For PUSCH scheduled by DCI format 0_0 on a cell and if the higher layer
parameter *enableDefaultBeamPL-ForPUSCH0-0* is set \'enabled\', the UE
is not configured with PUCCH resources on the active UL BWP and the UE
is in RRC connected mode, the UE shall transmit PUSCH according to the
spatial relation, if applicable, with a reference to the RS configured
with *qcl-Type* set to \'typeD\' corresponding to the QCL assumption of
the CORESET with the lowest ID on the active DL BWP of the cell. If the
CORESET is indicated with two TCI states, *sfnSchemePdcch* is configured
and the UE supports *sfn-DefaultUL-BeamSetup-r17*, the UE shall use the
first TCI state as the QCL assumption.

For PUSCH scheduled by DCI format 0_0 on a cell and if the higher layer
parameter *enableDefaultBeamPL-ForPUSCH0-0* is set \'enabled\', the UE
is configured with PUCCH resources on the active UL BWP where all the
PUCCH resource(s) are not configured with any spatial relation and the
UE is in RRC connected mode, the UE shall transmit PUSCH according to
the spatial relation, if applicable, with a reference to the RS
configured with *qcl-Type* set to \'typeD\' corresponding to the QCL
assumption of the CORESET with the lowest ID on the active DL BWP of the
cell in case CORESET(s) are configured on the cell. If the CORESET is
indicated with two TCI states, *sfnSchemePdcch* is configured and the UE
supports *sfn-DefaultUL-BeamSetup-r17*, the UE shall use the first TCI
state as the QCL assumption.

For uplink, 16 HARQ processes per cell are supported by the UE, or
subject to UE capability, a maximum of 32 HARQ processes per cell as
defined in \[13, TS 38.306\]. The number of processes the UE may assume
will at most be used for the uplink is configured to the UE for each
cell separately by higher layer parameter *nrofHARQ-ProcessesForPUSCH*,
and when no configuration is provided the UE may assume a default number
of 16 processes.