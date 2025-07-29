### 6.2.1 UE sounding procedure

The UE may be configured with one or more Sounding Reference Signal
(SRS) resource sets as configured by the higher layer parameter
*SRS-ResourceSet* or *SRS-PosResourceSet*. For each SRS resource set
configured by *SRS-ResourceSet*, a UE may be configured with
![](media/image757.wmf)SRS resources (higher layer parameter
*SRS-Resource*), where the maximum value of K is indicated by UE
capability \[13, 38.306\]. When SRS resource set is configured with the
higher layer parameter *SRS-PosResourceSet,* a UE may be configured with
*K* ≥1 SRS resources (higher layer parameter *SRS-PosResource*), where
the maximum value of K is 16. The SRS resource set applicability is
configured by the higher layer parameter *usage* in *SRS-ResourceSet.*
When the higher layer parameter *usage* is set to \'beamManagement\'*,*
only one SRS resource in each of multiple SRS resource sets may be
transmitted at a given time instant, but the SRS resources in different
SRS resource sets with the same time domain behaviour in the same BWP
may be transmitted simultaneously. For a given CC, multiple SRS
resources across multiple sets with usage "beamManagement" are not
expected to be partially overlapped in time.

During non-active periods of cell DRX if cell DRX is activated for the
serving cell, the UE is not expected to transmit the periodic SRS, or
semi-persistent SRS for channel acquisition that overlap in time with
any non-active periods of cell DRX on the serving cell. SRS for
positioning is not impacted by cell DRX operation.

During non-active periods of cell DRX if cell DRX is activated for a
serving cell, the UE applies the procedures described in this clause
after it determines PUSCH, SRS, and PUCCH transmission on the serving
cell due to cell DRX operations according to clause 5.34.3 of \[11, TS
38.321\].

For the SRS resource set(s) configured *in
srs-ResourceSetToAddModListDCI-0-2* with higher layer parameter *usage*
set to \'*antennaSwitching*\' or \'*beamManagement*\', the UE expects
the same SRS resource set(s) with the same *usage* being configured in
*srs-ResourceSetToAddModList.*

When the UE is configured *dl-OrJointTCI-StateList* or
*ul-TCI-StateList,* the UE can assume that SRS resource(s) in any SRS
resource set, except SRS resource set for positioning and an SRS
resource set configured with *followUnifiedTCI-StateSRS*, can be
configured with *TCI-State* or *TCI-UL-State* or updated as described in
clause 6.1.3.59 or 6.1.3.60 of \[10, TS 38.321\]. The reference RS in
the *TCI-State* can be a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *repetition*, a CSI-RS resource
in an *NZP-CSI-RS-ResourceSet* configured with higher layer parameter
*trs-Info*, or SS/PBCH block associated with the same or different PCI
from the PCI of the serving cell. The reference RS in the
*TCI-UL-State*(s) can be a CSI-RS resource in a *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *repetition*, a CSI-RS resource
in an *NZP-CSI-RS-ResourceSet* configured with higher layer parameter
*trs-Info*, an SRS resource with the higher layer parameter *usage* set
to \'beamManagement\', or SS/PBCH block associated with the same or
different PCI from the PCI of the serving cell.

If an SRS resource set, except an SRS resource set for positioning, is
configured with *followUnifiedTCI-StateSRS*, the UE shall transmit the
target SRS resource(s) within the SRS resource set according to the
spatial relation, if applicable, with a reference to the RS used for
determining UL TX spatial filter. The RS is determined based on an RS
configured with *qcl-Type* set to \'typeD\' in *QCL-Info* of the
indicated *TCI-State* or an RS in the indicated *TCI-UL-State*. The
reference RS in the indicated *TCI-State* can be a CSI-RS resource in a
*NZP-CSI-RS-ResourceSet* configured with higher layer parameter
*repetition*, or a CSI-RS resource in an *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info.* The reference RS in
the indicated *TCI-UL-State* can be a CSI-RS resource in a
*NZP-CSI-RS-ResourceSet* configured with higher layer parameter
*repetition*, a CSI-RS resource in an *NZP-CSI-RS-ResourceSet*
configured with higher layer parameter *trs-Info,* an SRS resource with
the higher layer parameter *usage* set to \'beamManagement\', or SS/PBCH
block associated with the same or different PCI from the PCI of the
serving cell.

When the UE is configured *dl-OrJointTCI-StateList* or *TCI-UL-State*
and is having two indicated TCI-States or TCI-UL-States, and if the UE
is configured with *followUnifiedTCI-StateSRS* to*,* a periodic,
semi-persistent or aperiodic SRS resource set with higher layer
parameter *usage* in *SRS-ResourceSet* set to \'*codebook*\',
\'*nonCodebook*\' or \'*antennaSwitching*\' or to an aperiodic SRS
resource set with higher layer parameter *usage* in *SRS-ResourceSet*
set to \'*beamManagement*\'

\- The UE may be configured by higher layer parameter
*applyIndicatedTCI-State* to the SRS resource set to indicate whether
the UE shall apply the first or the second indicated *TCI-State* or
*TCI-UL-State* to the SRS resource set.

\- When a UE is configured by higher layer parameter *PDCCH-Config* that
contains two different values of *coresetPoolIndex* in
*ControlResourceSet*, the first and second indicated *TCI-States* or
*TCI-UL-States* correspond to the indicated *TCI-States* or
*TCI-UL-States* specific to *coresetPoolIndex* value 0 and value 1,
respectively.

\- When a UE is configured by higher layer parameter *PDCCH-Config* that
contains two different values of *coresetPoolIndex* in
*ControlResourceSet*, and the aperiodic SRS resource set which is not
configured with higher layer parameter *applyIndicatedTCI-State* and the
aperiodic SRS resource set is triggered by PDCCH on a CORESET associated
with a *coresetPoolIndex* value, the UE shall apply the indicated
*TCI-State* or *TCI-UL-State* specific to the *coresetPoolIndex* value
to the aperiodic SRS resource set.

\- When two SRS resource sets are configured in
*srs-ResourceSetToAddModList* or *srs-ResourceSetToAddModListDCI-0-2*
with higher layer parameter *usage* in *SRS-ResourceSet* set to
\'codebook\' or \'nonCodebook\', the UE does not expect that the first
indicated *TCI-State* or *TCI-UL-State* is applied to the second SRS
resource set and that the second indicated *TCI-State* or *TCI-UL-State*
is applied to the first SRS resource set.

For aperiodic SRS at least one state of the DCI field is used to select
at least one out of the configured SRS resource set(s).

The following SRS parameters are semi-statically configurable by higher
layer parameter *SRS-Resource* or *SRS-PosResource*.

\- *srs-ResourceId* or *SRS-PosResourceId* determines SRS resource
configuration identity.

\- Number of SRS ports, as defined by the higher layer parameter
*nrofSRS-Ports* or *nrofSRS-Ports-n8* and described in clause 6.4.1.4 of
\[4, TS 38.211\]. If not configured, *nrofSRS-Ports* is 1.

*-* Time domain behaviour of SRS resource configuration as indicated by
the higher layer parameter *resourceType*, which may be periodic,
semi-persistent, aperiodic SRS transmission as defined in clause 6.4.1.4
of \[4, TS 38.211\].

\- Slot level periodicity and slot level offset as defined by the higher
layer parameters *periodicityAndOffset-p* or *periodicityAndOffset-sp*
for an SRS resource of type periodic or semi-persistent. The UE is not
expected to be configured with SRS resources in the same SRS resource
set *SRS-ResourceSet* or *SRS-PosResourceSet* with different slot level
periodicities. For an *SRS-ResourceSet* configured with higher layer
parameter *resourceType* set to \'aperiodic\', a slot level offset is
defined by the higher layer parameter *slotOffset.* For an
*SRS-ResourceSet* configured with higher layer parameter *resourceType*
set to \'aperiodic\', a list of up to four different available slot
offset values from the reference slot *n* + *k* to the slot where the
aperiodic SRS resource set is transmitted where *n* is the slot with
triggering DCI and *k* is *slotOffset,* can be configured by the higher
layer parameter *availableSlotOffsetList.* The parameter
*availableSlotOffsetList* can be configured up to 4 different values*.*
For an *SRS-PosResourceSet* configured with higher layer parameter
r*esourceType* set to \'aperiodic\', the slot level offset is defined by
the higher layer parameter *slotOffset* for each SRS resource.

\- *srs-PosHyperSFN-Index* indicates whether the current hyper-frame
number is even or odd for SRS for positioning transmission, if
configured.

\- Support of time division mapping subsets of ports of the SRS resource
into *S* symbols (*S=2)*, as defined by the higher layer parameter
*nrofSRS-Ports-n8* set to *ports8tdm*, where the SRS ports are evenly
distributed in two consecutive symbols over the symbols in a slot for
the SRS resource according to clause 6.4.1.4.2 in \[4, TS 38.211\]. This
applies when the SRS resource set is configured with higher layer
parameter *usage* in *SRS-ResourceSet* set to \'*codebook*\', or
\'*antennaSwitching*\', and *nrofSRS-Ports-n8* is set to
\'*ports8tdm*\'.

> \- Comb offset hopping pattern with repetition, as defined by the
> higher layer parameter *hoppingWithRepetition*, where the parameter
> can be set to either \'symbol\' or \'repetition\' subject to UE
> capability. When the parameter is set to \'symbol\', the comb offset
> hopping pattern is determined by the symbol index, and the comb offset
> hopping pattern is determined by the symbol index of the first symbol
> of the repetition when the parameter is set to \'repetition\'
> according to clause 6.4.1.4.3 in \[4, TS 38.211\].

\- Number of OFDM symbols in the SRS resource, starting OFDM symbol of
the SRS resource within a slot including repetition factor R as defined
by the higher layer parameter *resourceMapping* and described in clause
6.4.1.4 of \[4, TS 38.211\]. If *R* is not configured for positioning
SRS, then *R* is equal to the number of OFDM symbols in the SRS
resource.

\- SRS bandwidth ![](media/image758.wmf)and ![](media/image759.wmf), as
defined by the higher layer parameter *freqHopping* and described in
clause 6.4.1.4 of \[4, TS 38.211\]. If not configured,
then![](media/image758.wmf)= 0.

\- Frequency hopping bandwidth ![](media/image760.wmf), as defined by
the higher layer parameter *freqHopping* and described in clause 6.4.1.4
of \[4, TS 38.211\]. If not configured, then ![](media/image760.wmf)= 0.

\- Defining partial frequency sounding factor and start RB index for
partial frequency sounding as defined by the higher layer parameters
*FreqScalingFactor* P~F~ and *StartRBIndex k*~F~, respectively, and
described in Clause 6.4.1.4 of \[4, TS 38.211\]. If not configured, then
*P*~F~ = 1 and *k*~F~,= 0.

\- Defining start RB index hopping for partial frequency sounding in
different SRS frequency hopping periods for
aperiodic/periodic/semi-persistent SRS based on the hopping pattern
*k*~hop~ as described in clause 6.4.1.4.3 in \[4, TS 38.211\]. If not
configured, then start RB hopping is not enabled and *k*~hop~ is fixed
to be 0 for all SRS symbols.

\- Defining frequency domain position and configurable shift, as defined
by the higher layer parameters *freqDomainPosition* and
*freqDomainShift*, respectively, and described in clause 6.4.1.4 of \[4,
TS 38.211\]. If *freqDomainPosition* is not configured,
*freqDomainPosition* is zero.

\- Cyclic shift, as defined by the higher layer parameter
*cyclicShift-n2*, *cyclicShift-n4, or cyclicShift-n8* for transmission
comb value 2, 4 or 8, and described in clause 6.4.1.4 of \[4, TS
38.211\]. When cyclic shift hopping is configured by the higher layer
parameter *cyclicShiftHopping* for an SRS resource in an SRS resource
set with the usage configured as \'*antennaSwitching*\' or \'codebook\',
subject to UE capabilities, cyclic shift is updated at every symbol as
described in clause 6.4.1.4 of \[4, TS 38.211\]. For the cyclic shift
hopping, a UE can be configured with a subset of cyclic shifts by the
higher layer parameter *hoppingSubset*, where the cyclic shift hopping
is performed only across the cyclic shifts configured in the subset. For
the cyclic shift hopping, a UE can be configured with finer hopping
granularity by the higher layer parameter *hoppingFinerGranularity.* The
UE is not expecting that *hoppingFinerGranularity* and *hoppingSubset*
are configured simultaneously in *cyclicShiftHopping* for an SRS
resource. The UE is not expecting that the cyclic shift hopping and the
higher layer parameter *nrofSRS-Ports-n8* set to *ports8tdm* are
configured simultaneously for an SRS resource.

\- Transmission comb value, as defined by the higher layer parameter
*transmissionComb* described in clause 6.4.1.4 of \[4, TS 38.211\].

\- Transmission comb offset, as defined by the higher layer parameter
*combOffset-n2*, *combOffset-n4,* and *combOffset-n8* for transmission
comb value 2, 4, or 8, and described in clause 6.4.1.4 of \[4, TS
38.211\]. When comb offset hopping is configured by the higher layer
parameter *combOffsetHopping* for an SRS resource in an SRS resource set
with the usage configured as \'*antennaSwitching*\' or \'codebook\',
subject to UE capabilities, transmission comb offset(s) are updated as
described in clause 6.4.1.4 of \[4, TS 38.211\]. For the comb offset
hopping, a UE can be configured with a subset of comb offsets by the
higher layer parameter *hoppingSubset*, where the comb offset hopping is
performed only across the comb offsets configured in the subset. The UE
is not expecting that the comb offset hopping and the higher layer
parameter *nrofSRS-Ports-n8* set to *ports8tdm* are configured
simultaneously.

\- SRS sequence ID, as defined by the higher layer parameter
*sequenceId* in clause 6.4.1.4 of \[4, TS 38.211\].

\- SRS cyclic shift and/or comb offset hopping ID, as defined by the
higher layer parameter *hoppingId* in *cyclicShiftHopping* and/or
*combOffsetHopping*, respectively.

\- The configuration of the spatial relation between a reference RS and
the target SRS, where the higher layer parameter *spatialRelationInfo*
or *spatialRelationInfoPos*, if configured, contains the ID of the
reference RS. The reference RS may be an SS/PBCH block, CSI-RS
configured on serving cell indicated by higher layer parameter
*servingCellId* if present, same serving cell as the target SRS
otherwise, or an SRS configured on uplink BWP indicated by the higher
layer parameter *uplinkBWP*, and serving cell indicated by the higher
layer parameter *servingCellId* if present, same serving cell as the
target SRS otherwise. When the target SRS is configured by the higher
layer parameter *SRS-PosResourceSet*, the reference RS may also be a DL
PRS configured on a serving cell or a non-serving cell indicated by the
higher layer parameter *dl-PRS*, or an SS/PBCH block of a non-serving
cell indicated by the higher layer parameter *ssb-Ncell*. If the UE is
configured with *dl-OrJointTCI-StateList* or *ul-TCI-StateList*, the
reference RS may additionally be an SS/PBCH block associated with a PCI
different from the PCI of the serving cell.

The UE may be configured by the higher layer parameter *resourceMapping*
in *SRS-Resource* with an SRS resource occupying ![](media/image761.wmf)
adjacent OFDM symbols within the last 6 symbols of the slot, or at any
symbol location within the slot if *resourceMapping-r16* is provided
subject to UE capability, where all antenna ports of the SRS resources
are mapped to each symbol of the resource. When the SRS is configured
with the higher layer parameter *SRS-PosResourceSet* the higher layer
parameter *resourceMapping-r16* in *SRS-PosResource* indicates an SRS
resource occupying $N_{S} \in \left\{ 1,2,4,8,12 \right\}$ adjacent
symbols anywhere within the slot. When the SRS is configured with the
higher layer parameter *SRS-ResourceSet,* the higher layer parameter
*resourceMapping-r17* in *SRS-Resource* indicates an SRS resource
occupying $N_{S} \in \left\{ 1,2,4,8,10,12,14 \right\}$ adjacent symbols
anywhere within the slot. $N_{S}$ is divisible by$\ S*R$, where *S = 2*
when *nrofSRS-Ports-n8* is set to *ports8tdm* is configured and *S = 1*
otherwise, and *R* is the repetition factor.

If a PUSCH with a priority index 0 and SRS configured by *SRS-Resource*
are transmitted in the same slot on a serving cell, the UE may only be
configured to transmit SRS after the transmission of the PUSCH and the
corresponding DM-RS.

If a PUSCH transmission with a priority index 1 or a PUCCH transmission
with a priority index 1 would overlap in time with an SRS transmission
on a serving cell, the UE does not transmit the SRS in the overlapping
symbol(s).

For a UE configured with one or more SRS resource configuration(s), and
when the higher layer parameter *resourceType* in *SRS-Resource* or
*SRS-PosResource* is set to \'periodic\':

\- if the UE is configured with the higher layer parameter
*spatialRelationInfo, spatialRelationInfo-PDC* or
*spatialRelationInfoPos* containing the ID of a reference \'ssb-Index\',
\'ssb-IndexServing\', or \'ssb-IndexNcell\', the UE shall transmit the
target SRS resource with the same spatial domain transmission filter
used for the reception of the reference SS/PBCH block, if the higher
layer parameter *spatialRelationInfo, spatialRelationInfo-PDC* or
*spatialRelationInfoPos* contains the ID of a reference \'csi-RS-Index\'
or \'csi-RS-IndexServing\', the UE shall transmit the target SRS
resource with the same spatial domain transmission filter used for the
reception of the reference periodic CSI-RS or of the reference
semi-persistent CSI-RS, if the higher layer parameter
*spatialRelationInfo, spatialRelationInfo-PDC* or
*spatialRelationInfoPos* containing the ID of a reference \'srs\' or
\'srs-spatialRelation\', the UE shall transmit the target SRS resource
with the same spatial domain transmission filter used for the
transmission of the reference periodic SRS. When the SRS is configured
by the higher layer parameter *SRS-PosResource* and if the higher layer
parameter *spatialRelationInfoPos* contains the ID of a reference
\'dl-PRS\', the UE shall transmit the target SRS resource with the same
spatial domain transmission filter used for the reception of the
reference DL PRS. When the SRS is configured by the higher layer
parameter *SRS-Resource* and if the higher layer parameter
*spatialRelationInfo-PDC* contains the ID of a reference \'dl-PRS-PDC\',
the UE shall transmit the target SRS resource with the same spatial
domain transmission filter used for the reception of the reference DL
PRS for RTT-based propagation delay compensation according to clause 9.

For a UE configured with one or more SRS resource configuration(s), and
when the higher layer parameter *resourceType* in *SRS-Resource* or
*SRS-PosResource* is set to \'semi-persistent\':

\- when a UE receives an activation command, as described in clause
6.1.3.17 or 6.1.3.36 of \[10, TS 38.321\], for an SRS resource, and when
the UE would transmit a PUCCH with HARQ-ACK information in slot *n*
corresponding to the PDSCH carrying the activation command, the
corresponding actions in \[10, TS 38.321\] and the UE assumptions on SRS
transmission corresponding to the configured SRS resource set shall be
applied starting from the first slot that is after slot
$n + {3N}_{slot}^{subframe,µ}$ where *μ* is the SCS configuration for
the PUCCH. The activation command also contains spatial relation
assumptions provided by a list of references to reference signal IDs,
one per element of the activated SRS resource set. When the SRS is
configured with the higher layer parameter *SRS-ResourceSet*, each ID in
the list refers to a reference SS/PBCH block, NZP CSI-RS resource
configured on serving cell indicated by *Resource Serving Cell ID* field
in the activation command if present, same serving cell as the SRS
resource set otherwise, or SRS resource configured on serving cell and
uplink bandwidth part indicated by Resource *Serving Cell ID* field and
*Resource BWP ID* field in the activation command if present, same
serving cell and bandwidth part as the SRS resource set otherwise. When
the SRS is configured with the higher layer parameter
*SRS-PosResourceSet*, each ID in the list of reference signal IDs may
refer to a reference SS/PBCH block on a serving or non-serving cell
indicated by *PCI* field in the activation command, NZP CSI-RS resource
configured on serving cell indicated by *Resource Serving Cell ID* field
in the activation command if present, same serving cell as the SRS
resource set otherwise, SRS resource configured on serving cell and
uplink bandwidth part indicated by Resource *Serving Cell ID* field and
*Resource BWP ID* field in the activation command if present, same
serving cell and bandwidth part as the SRS resource set otherwise, or DL
PRS resource of a serving or non-serving cell associated with a
*dl-PRS-ID* indicated by *DL-PRS ID* field in the activation command.

\- if an SRS resource in the activated resource set is configured with
the higher layer parameter *spatialRelationInfo* or
*spatialRelationInfoPos*, the UE shall assume that the ID of the
reference signal in the activation command overrides the one configured
in *spatialRelationInfo* or *spatialRelationInfoPos.*

\- when a UE receives a deactivation command \[10, TS 38.321\] for an
activated SRS resource set, and when the UE would transmit a PUCCH with
HARQ-ACK information in slot *n* corresponding to the PDSCH carrying the
deactivation command, the corresponding actions in \[10, TS 38.321\] and
UE assumption on cessation of SRS transmission corresponding to the
deactivated SRS resource set shall apply starting from the first slot
that is after slot $n + {3N}_{slot}^{subframe,µ}$ where *μ* is the SCS
configuration for the PUCCH.

\- if the UE is configured with the higher layer parameter
*spatialRelationInfo* or *spatialRelationInfoPos* containing the ID of a
reference \'ssb-Index\', \'ssb-IndexServing\', or \'ssb-IndexNcell\' the
UE shall transmit the target SRS resource with the same spatial domain
transmission filter used for the reception of the reference SS/PBCH
block, if the higher layer parameter *spatialRelationInfo* or
*spatialRelationInfoPos* contains the ID of a reference \'csi-RS-Index\'
or \'csi-RS-IndexServing\', the UE shall transmit the target SRS
resource with the same spatial domain transmission filter used for the
reception of the reference periodic CSI-RS or of the reference
semi-persistent CSI-RS, if the higher layer parameter
*spatialRelationInfo* or *spatialRelationInfoPos* contains the ID of a
reference \'srs\' or \'srs-SpatialRelation\', the UE shall transmit the
target SRS resource with the same spatial domain transmission filter
used for the transmission of the reference periodic SRS or of the
reference semi-persistent SRS. When the SRS is configured by the higher
layer parameter *SRS-PosResourceSet* and if the higher layer parameter
*spatialRelationInfoPos* contains the ID of a reference \'dl-PRS\', the
UE shall transmit the target SRS resource with the same spatial domain
transmission filter used for the reception of the reference DL PRS.

If the UE has an active semi-persistent SRS resource configuration and
has not received a deactivation command, the semi-persistent SRS
configuration is considered to be active, when applicable, in the UL BWP
which is active, otherwise it is considered suspended.

For a UE configured with one or more SRS resource configuration(s), and
when the higher layer parameter *resourceType* in *SRS-Resource* or
*SRS-PosResource* is set to \'aperiodic\':

\- the UE receives a configuration of SRS resource sets,

\- the UE receives a downlink DCI, a group common DCI, or an uplink DCI
based command where a codepoint of the DCI may trigger one or more SRS
resource set(s). For SRS in a resource set with usage set to
\'codebook\' or \'antennaSwitching\', the minimal time interval between
the last symbol of the PDCCH triggering the aperiodic SRS transmission
and the first symbol of SRS resource is *N~2\ ~* symbols and an
additional time duration *T~switch~*. Otherwise, the minimal time
interval between the last symbol of the PDCCH triggering the aperiodic
SRS transmission and the first symbol of SRS resource is *N~2~* +14
symbols and an additional time duration *T~switch~*. The minimal time
interval unit of OFDM symbol is counted based on the minimum subcarrier
spacing given by min(*µ~PDCCH,~ µ~UL~*) where *µ~UL~* is given by
min(*µ~UL,carrier1,~ µ~UL,carrier2,~ µ~SRS~*) when the UE is configured
with the higher layer parameter *uplinkTxSwitchingOption* set to
\'dualUL\' for uplink carrier aggregation, and by *µ~SRS~* otherwise.
*µ~SRS~* and *µ~PDCCH~* are the subcarrier spacing configurations for
triggered SRS and PDCCH carrying the triggering command respectively.

\- *T~switch~*, *µ~UL,carrier1\ ~*and *µ~UL,carrier2~* are defined in
clause 6.4.

\- A UE reporting its UE capability \'srs-TriggeringDCI\' can be
indicated with DCI 0_1 and 0_2 to trigger aperiodic SRS without data and
without CSI as described in clause 7.3.1.1 of \[5, TS 38.212\].
Otherwise, except for DCI format 0_1/0_2 with CRC scrambled by
SP-CSI-RNTI, a UE is not expected to receive a DCI format 0_1/0_2 with
UL-SCH indicator of \"0\" and CSI request of all zero(s) as described in
clause 7.3.1.1 of \[5, TS 38.212\].

\- If the UE receives the DCI triggering aperiodic SRS in slot *n* and
at least one resource set is configured with parameter
*availableSlotOffset* across all configured BWPs in a component carrier
except when SRS is configured with the higher layer parameter
*SRS-PosResource*,

\- If ca-*SlotOffset* is configured, the UE transmits aperiodic SRS in
each of the triggered SRS resource set(s) in the (*t* + 1)-th available
slot counting from slot ![](media/image762.wmf),

\- otherwise the UE transmits aperiodic SRS in each of the triggered SRS
resource set(s) in the (*t* + 1)-th available slot counting from slot
$\left\lfloor n \cdot \frac{2^{\mu_{SRS}}}{2^{\mu_{PDCCH}}} \right\rfloor + k + K_{offset} \cdot \frac{2^{\mu_{SRS}}}{2^{\mu_{K_{offset}}}}$,
where $K_{offset}$ is a parameter configured by higher layer as
specified in clause 4.2 of \[6 TS 38.213\], and where

*- k* is configured via higher layer parameter *slotOffset* for each
triggered SRS resources set and is based on the subcarrier spacing of
the triggered SRS transmission, *µ~SRS~* and *µ~PDCCH~* are the
subcarrier spacing configurations for triggered SRS and PDCCH carrying
the triggering command, respectively.

*-* $\mu_{K_{offset}}$is the subcarrier spacing configuration for
$K_{offset}$ with a value of 0 for frequency range 1 and for FR2-NTN.

*-* $N_{\text{slot, offset, PDCCH}}^{\text{CA}}$ and
$\mu_{\text{offset,PDCCH}}$ are the
$N_{\text{slot, offset}}^{\text{CA}}$ and the![](media/image15.wmf),
respectively, which are determined by higher-layer configured
*ca-SlotOffset* for the cell receiving the PDCCH,
$N_{\text{slot, offset, SRS}}^{\text{CA}}$ and
$\mu_{\text{offset,SRS}}$ are the
$N_{\text{slot, offset}}^{\text{CA}}$ and the![](media/image15.wmf),
respectively, which are determined by higher-layer configured
*ca-SlotOffset* for the cell transmitting the SRS, as defined in \[4, TS
38.211\] clause 4.5.

\- An available slot is a slot satisfying there are UL or flexible
symbol(s) for the time-domain location(s) for all the SRS resources in
the resource set and it satisfies UE capability on the minimum timing
requirement between triggering PDCCH and all the SRS resources in the
resource set. From the first symbol carrying the SRS request DCI to the
last symbol of the triggered SRS resource set, UE does not expect to
receive SFI indication, UL cancellation indication or dynamic scheduling
of DL channel/signal(s) on flexible symbol(s) that may change the
determination of available slot.

*- t* is configured via higher layer parameter *availableSlotOffsetList*
with up to four different values of *AvailableSlotOffset* for each
triggered SRS resources set and it is based on the subcarrier spacing of
the triggered SRS transmission. When one or more SRS resource sets
across all configured BWPs in a component carrier are configured, and at
least one resource set is configured with *availableSlotOffsetList*
parameter of more than one values, the indicated value of *t* is
indicated by SOI field in DCI scheduling PUSCH/PDSCH and DCI 0_1/0_2
without data and without CSI request described in \[5, TS 38.212\]. The
UE shall apply indicated value *t* specifically for those sets with
configured *availableSlotOffsetList* parameter. When one or more SRS
resource sets across all configured BWPs in a component carrier are
configured and at least one resource set is configured with
*availableSlotOffsetList* parameter, and the *availableSlotOffsetList*
parameter for each SRS resource set has only one value, the UE shall
apply the configured value specifically for those sets with configured
*availableSlotOffsetList* parameter. For SRS resource set configured
with *availableSlotOffsetList* parameter, each of resource set is
configured with *K* values of *AvailableSlotOffset*. For SRS resource
set configured without *availableSlotOffsetList* parameter, *t* = 0 is
applied for the resource set.

\- If the UE receives the DCI triggering aperiodic SRS in slot *n* and
none of the resource sets is configured with parameter
*availableSlotOffsetList* across all configured BWPs in a component
carrier except when SRS is configured with the higher layer parameter
*SRS-PosResource*

\- if the UE is configured with *ca-SlotOffset* for at least one of the
triggered and triggering cell, the UE transmits aperiodic SRS in each of
the triggered SRS resource set(s) in slot ![](media/image762.wmf)*,*

\- otherwise, the UE transmits aperiodic SRS in each of the triggered
resource set(s) in slot
$K_{s} = \left\lfloor n \cdot \frac{2^{\mu_{SRS}}}{2^{\mu_{PDCCH}}} \right\rfloor + k + K_{offset} \cdot \frac{2^{\mu_{SRS}}}{2^{\mu_{K_{offset}}}}$,
where $K_{offset}$ is a parameter configured by higher layer as
specified in clause 4.2 of \[6 TS 38.213\], and where

*- k* is configured via higher layer parameter *slotOffset* for each
triggered SRS resources set and is based on the subcarrier spacing of
the triggered SRS transmission, *µ~SRS~* and *µ~PDCCH~* are the
subcarrier spacing configurations for triggered SRS and PDCCH carrying
the triggering command respectively;

*-* $\mu_{K_{offset}}$is the subcarrier spacing configuration for
$K_{offset}$ with a value of 0 for frequency range 1 and for FR2-NTN.

\- $N_{\text{slot, offset, PDCCH}}^{\text{CA}}$ and
$\mu_{\text{offset,PDCCH}}\ $are the
${\ N}_{\text{slot, offset}}^{\text{CA}}$ and the![](media/image15.wmf),
respectively, which are determined by higher-layer configured
*ca-SlotOffset* for the cell receiving the PDCCH,
$N_{slot,offset,SRS}^{CA}$ and $\mu_{offset,SRS}$ are the
![](media/image763.wmf){width="0.5833333333333334in"
height="0.2777777777777778in"} and the
![](media/image764.wmf){width="0.3347222222222222in"
height="0.21666666666666667in"}, respectively, which are determined by
higher-layer configured *ca-SlotOffset* for the cell transmitting the
SRS, as defined in \[4, TS 38.211\] clause 4.5.

\- If the UE receives the DCI triggering aperiodic SRS in slot *n* and
when SRS is configured with the higher layer parameter
*SRS-PosResource*, the UE transmits every aperiodic SRS resource in each
of the triggered SRS resource set(s) in slot ![](media/image762.wmf), if
UE is configured with *ca-SlotOffset* for at least one of the triggered
and triggering cell,
$K_{s} = \left\lfloor n \cdot \frac{2^{\mu_{SRS}}}{2^{\mu_{PDCCH}}} \right\rfloor + k + K_{offset} \cdot \frac{2^{\mu_{SRS}}}{2^{\mu_{K_{offset}}}}$,
otherwise, where $K_{offset}$ is a parameter configured by higher layer
as specified in clause 4.2 of \[6 TS 38.213\], and where

*- k* is configured via higher layer parameter *slotOffset* for each
aperiodic SRS resource in each triggered SRS resources set and is based
on the subcarrier spacing of the triggered SRS transmission, *µ~SRS~*
and *µ~PDCCH~* are the subcarrier spacing configurations for triggered
SRS and PDCCH carrying the triggering command respectively;

*-* $\mu_{K_{offset}}$ is the subcarrier spacing configuration for
$K_{offset}$ with a value of 0 for frequency range 1 and for FR2-NTN.

\- $N_{\text{slot, offset, PDCCH}}^{\text{CA}}$ and
$\mu_{\text{offset,PDCCH}}\ $are the
${\ N}_{\text{slot, offset}}^{\text{CA}}$ and the![](media/image15.wmf),
respectively, which are determined by higher-layer configured
*ca-SlotOffset* for the cell receiving the PDCCH,
$N_{slot,offset,SRS}^{CA}$ and $\mu_{offset,SRS}$ are the
![](media/image763.wmf){width="0.5833333333333334in"
height="0.2777777777777778in"} and the
![](media/image764.wmf){width="0.3347222222222222in"
height="0.21666666666666667in"}, respectively, which are determined by
higher-layer configured *ca-SlotOffset* for the cell transmitting the
SRS, as defined in \[4, TS 38.211\] clause 4.5.

\- if the UE is configured with the higher layer parameter
*spatialRelationInfo* or *spatialRelationInfoPos* containing the ID of a
reference \'ssb-Index\', \'ssb-IndexServing\' or \'ssb-IndexNcell\', the
UE shall transmit the target SRS resource with the same spatial domain
transmission filter used for the reception of the reference SS/PBCH
block, if the higher layer parameter *spatialRelationInfo* or
*spatialRelationInfoPos* contains the ID of a reference \'csi-RS-Index\'
or \'csi-RS-IndexServing\', the UE shall transmit the target SRS
resource with the same spatial domain transmission filter used for the
reception of the reference periodic CSI-RS or of the reference
semi-persistent CSI-RS, or of the latest reference aperiodic CSI-RS. If
the higher layer parameter *spatialRelationInfo* or
*spatialRelationInfoPos* contains the ID of a reference \'srs\' or
\'srs-SpatialRelation\', the UE shall transmit the target SRS resource
with the same spatial domain transmission filter used for the
transmission of the reference periodic SRS or of the reference
semi-persistent SRS or of the reference aperiodic SRS. When the SRS is
configured by the higher layer parameter *SRS-PosResourceSet* and if the
higher layer parameter *spatialRelationInfoPos* contains the ID of a
reference \'dl-PRS\', the UE shall transmit the target SRS resource with
the same spatial domain transmission filter used for the reception of
the reference DL PRS.

\- when a UE receives an spatial relation update command, as described
in clause 6.1.3.26 of \[10, TS 38.321\], for an SRS resource configured
with the higher layer parameter *SRS-Resource*, and when the HARQ-ACK
corresponding to the PDSCH carrying the update command is transmitted in
slot *n*, the corresponding actions in \[10, TS 38.321\] and the UE
assumptions on updating spatial relation for the SRS resource shall be
applied for SRS transmission starting from the first slot that is after
slot $n + {3N}_{slot}^{subframe,µ}\ $where *μ* is the SCS configuration
for the PUCCH. The update command contains spatial relation assumptions
provided by a list of references to reference signal IDs, one per
element of the updated SRS resource set. Each ID in the list refers to a
reference SS/PBCH block, NZP CSI-RS resource configured on serving cell
indicated by *Resource Serving Cell ID* field in the update command if
present, same serving cell as the SRS resource set otherwise, or SRS
resource configured on serving cell and uplink bandwidth part indicated
by *Resource* *Serving Cell ID* field and *Resource BWP ID* field in the
update command if present, same serving cell and bandwidth part as the
SRS resource set otherwise. When the UE is configured with the higher
layer parameter *usage* in *SRS-ResourceSet* set to
\'antennaSwitching\', the UE shall not expect to be configured with
different spatial relations for SRS resources in the same SRS resource
set.

The UE is not expected to be configured with different time domain
behavior for SRS resources in the same SRS resource set. The UE is also
not expected to be configured with different time domain behavior
between SRS resource and associated SRS resources set.

For operation in the same carrier, the UE is not expected to be
configured on overlapping symbols with a SRS resource configured by the
higher layer parameter *SRS-PosResource* and a SRS resource configured
by the higher layer parameter *SRS-Resource* with *resourceType* of both
SRS resources as \'periodic\'.

For operation in the same carrier, the UE is not expected to be
activated or triggered to transmit SRS on overlapping symbols with a SRS
resource configured by the higher layer parameter *SRS-PosResource* and
a SRS resource configured by the higher layer parameter *SRS-Resource*
with *resourceType* of both SRS resources as \'semi-persistent\' or
\'aperiodic\'.

For operations in the same carrier, the UE is not expected to be
configured on overlapping symbols with more than one SRS resources
configured by the higher layer parameter *SRS-PosResource* with
*resourceType* of the SRS resources as \'periodic\'.

For operations in the same carrier, the UE is not expected to be
activated or triggered to transmit SRS on overlapping symbols with more
than one SRS resources configured by the higher layer parameter
*SRS-PosResource* with *resourceType* of the SRS resources as
\'semi-persistent\' or \'aperiodic\'.

For intra-band and inter-band CA operations, a UE can simultaneously
transmit more than one SRS resource configured by *SRS-PosResource* on
different CCs, subject to UE\'s capability

For intra-band and inter-band CA operations, a UE can simultaneously
transmit more than one SRS resource configured by *SRS-PosResource* and
*SRS-Resource* on different CCs, subject to UE\'s capability.

The SRS request field \[5, TS 38.212\] in DCI format 0_1, 1_1, 0_2 (if
SRS request field is present), 1_2 (if SRS request field is present),
0_3, 1_3 indicates the triggered SRS resource set given in Table
7.3.1.1.2-24 of \[5, TS 38.212\]. The 2-bit SRS request field in DCI
format 2_3 indicates the triggered SRS resource set given in clause 7.3
of \[5, TS 38.212\] and defined by the entries of the higher layer
parameter *srs-ResourceSetToAddModList* if the UE is configured with
higher layer parameter *srs-TPC-PDCCH-Group* set to \'typeB\', or
indicates the SRS transmission on a set of serving cells configured by
higher layers if the UE is configured with higher layer parameter
*srs-TPC-PDCCH-Group* set to \'typeA\'.

For PUCCH and SRS on the same carrier, a UE shall not transmit SRS when
semi-persistent or periodic SRS is configured in the same symbol(s) with
PUCCH carrying only CSI report(s), or only L1-RSRP report(s), or only
L1-SINR report(s). A UE shall not transmit SRS when semi-persistent or
periodic SRS is configured or aperiodic SRS is triggered to be
transmitted in the same symbol(s) with PUCCH carrying HARQ-ACK, link
recovery request (as defined in clause 9.2.4 of \[6, 38.213\]) and/or
SR. In the case that SRS is not transmitted due to overlap with PUCCH,
only the SRS symbol(s) that overlap with PUCCH symbol(s) are dropped.
PUCCH shall not be transmitted when aperiodic SRS is triggered to be
transmitted to overlap in the same symbol with PUCCH carrying
semi-persistent/periodic CSI report(s) or semi-persistent/periodic
L1-RSRP report(s) only, or only L1-SINR report(s) and the PUCCH starts
no earlier than $T_{proc,2\ }$ after the last symbol of the PDCCH
carrying the triggering command for the aperiodic SRS, where
$T_{proc,2}$ is the PUSCH preparation time for the corresponding UE
processing capability assuming $d_{2,1} = 1$ and $\mu$ corresponds to
the smallest SCS configuration between the SCS configuration of the
PDCCH carrying the triggering command and the SCS configuration of the
PUCCH.

In case of intra-band contiguous carrier aggregation, or in inter-band
or intra-band non-contiguous CA band combination if simultaneous SRS and
PUCCH/PUSCH transmissions are not supported by UE, the UE is not
expected to be indicated with a SRS transmission from a carrier and to
be configured or scheduled with a PUSCH/UL DM-RS/UL PT-RS/PUCCH
transmission from a different carrier in the same symbol.

In case of intra-band contiguous carrier aggregation, or in inter-band
CA band combination if simultaneous SRS and PRACH transmissions are not
supported by UE, or in case of intra-band non-contiguous CA band
combination if the UE is not configured with higher layer parameter
*intraBandNC-PRACH-simulTx-r17,* the UE shall not transmit
simultaneously SRS resource(s) from a carrier and PRACH from a different
carrier.

In case of intra-band contiguous carrier aggregation, or in inter-band
CA band combination if simultaneous SRS and MsgA transmissions are not
supported by UE, the UE shall not transmit simultaneously SRS
resource(s) from a carrier and MsgA from a different carrier.

In case a SRS resource with *resourceType* set as \'aperiodic\' is
triggered on the OFDM symbol(s) configured with periodic/semi-persistent
SRS transmission, the UE shall transmit the aperiodic SRS resource and
only the periodic/semi-persistent SRS symbol(s) overlapping within the
symbol(s) are dropped, while the periodic/semi-persistent SRS symbol(s)
that are not overlapped with the aperiodic SRS resource are transmitted.
In case a SRS resource with *resourceType* set as \'semi-persistent\' is
triggered on the OFDM symbol(s) configured with periodic SRS
transmission, the UE shall transmit the semi-persistent SRS resource and
only the periodic SRS symbol(s) overlapping within the symbol(s) are
dropped, while the periodic SRS symbol(s) that are not overlapped with
the semi-persistent SRS resource are transmitted.

When the UE is configured with the higher layer parameter *usage* in
*SRS-ResourceSet* set to \'antennaSwitching\', and a guard period of Y
symbols is configured according to Clause 6.2.1.2, the UE shall use the
same priority rules as defined above during the guard period as if SRS
was configured.

When a *spatialRelationInfo* is activated/updated for a semi-persistent
or aperiodic SRS resource configured by the higher layer parameter
*SRS-Resource* by a MAC CE for a set of CCs/BWPs, where the applicable
list of CCs provided by higher layer parameter
*simultaneousSpatial-UpdatedList1* or *simultaneousSpatial-UpdatedList2*
is determined by the indicated CC in the MAC CE, the
*spatialRelationInfo* is applied for the semi-persistent or aperiodic
SRS resource(s) with the same SRS resource ID for all the BWPs in the
determined CCs.

When the higher layer parameter *enableDefaultBeamPL-ForSRS* is set
\'enabled\', and if the higher layer parameter *spatialRelationInfo* for
the SRS resource, except for the SRS resource with the higher layer
parameter *usage* in SRS-ResourceSet set to \'beamManagement\' or for
the SRS resource with the higher layer parameter *usage* in
SRS-ResourceSet set to \'nonCodebook\' with configuration of
*associatedCSI-RS* or for the SRS resource configured by the higher
layer parameter *SRS-PosResourceSet*, or *dl-OrJointTCI-StateList* or
*ul-TCI-StateList* is not configured in frequency range 2 and if the UE
is not configured with higher layer parameter(s) *pathlossReferenceRS*,
and if the UE is not configured with different values of
*coresetPoolIndex* in *ControlResourceSets*, and is not provided at
least one TCI codepoint mapped with two TCI states, the UE shall
transmit the target SRS resource in an active UL BWP of a CC,

\- according to the spatial relation, if applicable, with a reference to
the RS configured with *qcl-Type* set to \'typeD\' corresponding to the
QCL assumption of the CORESET with the lowest *controlResourceSetId* in
the active DL BWP in the CC. If the CORESET is activated with two TCI
states, *sfnSchemePdcch* is configured and the UE supports
*sfn-DefaultUL-BeamSetup-r17*, UE shall use the first TCI state as the
QCL assumption.

\- according to the spatial relation, if applicable, with a reference to
the RS configured with *qcl-Type* set to \'typeD\' in the activated TCI
state with the lowest ID applicable to PDSCH in the active DL BWP of the
CC if the UE is not configured with any CORESET in the active DL BWP of
the CC.

For a SRS resource, if *nrofSRS-Ports-n8* is set to *ports8tdm* or
*combOffsetHopping* is configured, the corresponding UE SRS frequency
hopping procedure is specified in clause 6.4.1.4.3 of \[4, TS 38.211\].
If for a SRS resource *nrofSRS-Ports-n8* is not configured or it is not
set to *ports8tdm* and *combOffsetHopping* is not configured, the UE SRS
frequency hopping procedure is specified in clause 6.4.1.4.3 of \[4, TS
38.211\] and in clause 6.2.1.1.