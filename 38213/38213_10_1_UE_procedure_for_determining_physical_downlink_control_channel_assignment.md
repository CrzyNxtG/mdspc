## 10.1 UE procedure for determining physical downlink control channel assignment

A set of PDCCH candidates for a UE to monitor is defined in terms of
PDCCH search space sets. A search space set can be a CSS set or a USS
set. A UE monitors PDCCH candidates in one or more of the following
search spaces sets

\- a Type0-PDCCH CSS set on the primary cell of the MCG configured by

\- *pdcch-ConfigSIB1* in MIB or by *searchSpaceSIB1* in
*PDCCH-ConfigCommon* or by *searchSpaceZero* in *PDCCH-ConfigCommon* for
a DCI format 1_0 with CRC scrambled by a SI-RNTI, or

\- *searchSpaceZero* by providing *searchSpaceID*=0 for
*searchSpaceMCCH* or *searchSpaceMTCH* for a DCI format 4_0 with CRC
scrambled by a MCCH-RNTI or a G-RNTI for broadcast, or

\- *searchSpaceZero* by providing *searchSpaceID*=0 for
*searchspaceMulticastMCCH* for a DCI format 4_0 with CRC scrambled by a
Multicast MCCH-RNTI, or by *searchSpaceMulticastMTCH* for a DCI format
4_1 with CRC scrambled by a G-RNTI for multicast in RRC_INACTIVE state

\- a Type0A-PDCCH CSS set configured by
*searchSpaceOtherSystemInformation* in *PDCCH-ConfigCommon* for a DCI
format 1_0 with CRC scrambled by a SI-RNTI on the primary cell of the
MCG

\- a Type0B-PDCCH CSS set configured by

\- *searchSpaceMCCH* and *searchSpaceMTCH* for a DCI format 4_0 with CRC
scrambled by a MCCH-RNTI or a G-RNTI for broadcast, on the primary cell
of the MCG

\- *searchspaceMulticastMCC*H for a DCI format 4_0 with CRC scrambled by
a Multicast MCCH-RNTI, or by *searchSpaceMulticastMTCH* for a DCI format
4_1 with CRC scrambled by a G-RNTI for PDCCH receptions in RRC_INACTIVE
state

\- a Type1-PDCCH CSS set configured by *ra-SearchSpace* in
*PDCCH-ConfigCommon* for a DCI format with CRC scrambled by a RA-RNTI, a
MsgB-RNTI, or a TC-RNTI on the primary cell

\- a Type1A-PDCCH CSS set configured by *sdt-SearchSpace* in
*PDCCH-ConfigCommon* for a DCI format with CRC scrambled by a C-RNTI or
a CS-RNTI on the primary cell

\- a Type2-PDCCH CSS set configured by *pagingSearchSpace* in
*PDCCH-ConfigCommon* for a DCI format 1_0 with CRC scrambled by a P-RNTI
on the primary cell of the MCG

\- a Type2A-PDCCH CSS set configured by *pei-SearchSpace* in
*pei-ConfigBWP* for a DCI format 2_7 with CRC scrambled by a PEI-RNTI on
the primary cell of the MCG

\- a Type3-PDCCH CSS set configured by

\- *SearchSpace* in *PDCCH-Config* with *searchSpaceType* = *common* for
DCI formats with CRC scrambled by INT-RNTI, SFI-RNTI, TPC-PUSCH-RNTI,
TPC-PUCCH-RNTI, TPC-SRS-RNTI, CI-RNTI, or cellDTRX-RNTI and, only for
the primary cell, C-RNTI, MCS-C-RNTI, CS-RNTI(s), or PS-RNTI, or

\- *SearchSpace* in *pdcch-ConfigMulticast* for DCI formats with CRC
scrambled by G-RNTI, or G-CS-RNTI, or

\- *searchSpaceMCCH* and *searchSpaceMTCH* on a secondary cell for a DCI
format 4_0 with CRC scrambled by a MCCH-RNTI or a G-RNTI for broadcast,
and

\- a USS set configured by

\- *SearchSpace* or by *SearchSpaceExt-v1800* in *PDCCH-Config* with
*searchSpaceType* = *ue-Specific* for DCI formats with CRC scrambled by
C-RNTI, MCS-C-RNTI, SP-CSI-RNTI, CS-RNTI(s), SL-RNTI, SL-CS-RNTI, SL
Semi-Persistent Scheduling V-RNTI, or NCR-RNTI

In the following, DCI formats with CRC scrambled by C-RNTI or CS-RNTI or
MCS-C-RNTI are also referred to as unicast DCI formats, DCI formats with
CRC scrambled by G-RNTI for multicast or G-CS-RNTI are also referred to
as multicast DCI formats, and DCI formats with CRC scrambled by
MCCH-RNTI or G-RNTI for broadcast scheduling PDSCH receptions are also
referred to as broadcast DCI formats, and DCI formats with CRC scrambled
by Multicast MCCH-RNTI or G-RNTI for multicast scheduling PDSCH
receptions in RRC_INACTIVE state are also referred as multicast DCI
formats for RRC_INACTIVE state.

For a DL BWP, if a UE is not provided *searchSpaceSIB1* for Type0-PDCCH
CSS set by *PDCCH-ConfigCommon*, the UE does not monitor PDCCH
candidates for a Type0-PDCCH CSS set on the DL BWP. The Type0-PDCCH CSS
set is defined by the CCE aggregation levels and the number of PDCCH
candidates per CCE aggregation level given in Table 10.1-1.

If the active DL BWP and the initial DL BWP for a UE have same SCS and
same CP length and the active DL BWP includes all RBs of the CORESET
with index 0, or the active DL BWP is the initial DL BWP, or the active
DL BWP includes all RBs of an MBS frequency resource provided by
*cfr-ConfigMCCH-MTCH* or *cfr-ConfigMCCH-MTCH-RedCap* as described in
clause 18, the CORESET configured for Type0-PDCCH CSS set has CORESET
index 0 and the Type0-PDCCH CSS set has search space set index 0.

If the active DL BWP and an MBS frequency resource provided by
*cfr-ConfigMCCH-MTCH* or *cfr-ConfigMCCH-MTCH-RedCap* or determined by
CORESET with index 0 when *cfr-ConfigMCCH-MTCH* or
*cfr-ConfigMCCH-MTCH-RedCap* is not provided for a UE have same SCS and
same CP length and the active DL BWP includes all RBs of the MBS
frequency resource, and if the UE is provided *searchSpaceMCCH* or
*searchSpaceMTCH* for Type0B-PDCCH CSS set on the primary cell or for
Type3-PDCCH CSS set on a secondary cell, the UE monitors PDCCH for
detection of broadcast DCI formats, as described in clause 18, on the
active DL BWP.

For a DL BWP, if a UE is not provided
*searchSpaceOtherSystemInformation* for Type0A-PDCCH CSS set, the UE
does not monitor PDCCH for Type0A-PDCCH CSS set on the DL BWP. The CCE
aggregation levels and the number of PDCCH candidates per CCE
aggregation level for Type0A-PDCCH CSS set are given in Table 10.1-1.

For a DL BWP, if a UE is not provided *ra-SearchSpace* for Type1-PDCCH
CSS set, the UE does not monitor PDCCH for Type1-PDCCH CSS set on the DL
BWP. If the UE has not been provided a Type3-PDCCH CSS set, or a
Type1A-PDCCH CSS set, or a USS set and the UE has received a C-RNTI and
has been provided a Type1-PDCCH CSS set, the UE monitors PDCCH
candidates for DCI format 0_0 and DCI format 1_0 with CRC scrambled by
the C-RNTI in the Type1-PDCCH CSS set.

If a UE is not provided *pagingSearchSpace* for Type2-PDCCH CSS set, the
UE does not monitor PDCCH for Type2-PDCCH CSS set on the DL BWP. The CCE
aggregation levels and the number of PDCCH candidates per CCE
aggregation level for Type2-PDCCH CSS set are given in Table 10.1-1.

If a UE is not provided *pei-SearchSpace* for Type2A-PDCCH CSS set, the
UE does not monitor PDCCH for Type2A-PDCCH CSS set on the DL BWP. The
CCE aggregation levels and the maximum number of PDCCH candidates per
CCE aggregation level for Type2A-PDCCH CSS set are given in Table
10.1-1. If the UE is provided *pei-SearchSpace* with zero value for the
Type2A-PDCCH CSS set index, and for the SS/PBCH block and CORESET
multiplexing patterns 2 and 3, the UE determines PDCCH monitoring
occasions as described in clause 13 and the CCE aggregation levels and
the number of PDCCH candidates per CCE aggregation level for
Type2A-PDCCH CSS set are given in Table 10.1-1.

If a UE is provided a zero value for *searchSpaceID* in
*PDCCH-ConfigCommon* for a Type0/0A/1A/2-PDCCH CSS set, the UE
determines monitoring occasions for PDCCH candidates of the
Type0/0A/1A/2-PDCCH CSS set as described in clause 13, and the UE is
provided a C-RNTI, the UE monitors PDCCH candidates only at monitoring
occasions associated with a SS/PBCH block, where the SS/PBCH block is
determined by the most recent of

\- a DCI format or a MAC CE activation command indicating a TCI state of
the active BWP that includes a CORESET with index 0, as described in
\[6, TS 38.214\], where the TCI-state includes a CSI-RS which is
quasi-co-located with the SS/PBCH block, or

\- a random access procedure that is not initiated by a PDCCH order that
triggers a contention-free random access procedure, or

\- configured-grant based PUSCH transmission in RRC_INACTIVE state as
described in clause 19.1.

If a UE monitors PDCCH candidates for DCI formats with CRC scrambled by
a C-RNTI and the UE is provided a non-zero value for *searchSpaceID* in
*PDCCH-ConfigCommon* for a Type0/0A/1A/2-PDCCH CSS set, or monitors
PDCCH candidates for DCI formats with CRC scrambled by a MCCH-RNTI or a
G-RNTI for broadcast and the UE is provided a non-zero value for
*searchSpaceMCCH* and *searchSpaceMTCH* in *PDCCH-ConfigCommon* for a
Type0B-PDCCH CSS set, or monitors PDCCH candidates for DCI formats with
CRC scrambled by a Multicast MCCH-RNTI or a G-RNTI for multicast in
RRC_INACTIVE state and the UE is provided a non-zero value for
*searchSpaceMulticastMCCH* and *searchSpaceMulticastMTCH* in
*PDCCH-ConfigCommon* for a Type0B-PDCCH CSS set, the UE determines
monitoring occasions for PDCCH candidates of the Type0/0A/1A/2-PDCCH CSS
set, or of the Type0B-PDCCH CSS set, respectively, based on the search
space set associated with the value of *searchSpaceID*.

The UE may assume that the DM-RS antenna port associated with PDCCH
receptions in the CORESET configured by *pdcch-ConfigSIB1* in *MIB*, the
DM-RS antenna port associated with corresponding PDSCH receptions, and
the corresponding SS/PBCH block are quasi co-located with respect to
average gain, quasi co-location \'typeA\' and \'typeD\' properties, when
applicable \[6, TS 38.214\], if the UE is not provided a TCI state
indicating quasi co-location information of the DM-RS antenna port for
PDCCH reception in the CORESET. The value for the DM-RS scrambling
sequence initialization is the cell ID. For operation without shared
spectrum channel access in FR1, FR2-1 and FR2-NTN, a SCS is provided by
*subCarrierSpacingCommon* in *MIB*. For operation with shared spectrum
channel access in FR1 and for operation in FR2-2, a SCS is same as the
SCS of a corresponding SS/PBCH block.

For single cell operation or for operation with carrier aggregation in a
same frequency band, a UE does not expect to monitor a PDCCH in a
Type0/0A/0B/2/3-PDCCH CSS set or in a USS set if a DM-RS for monitoring
a PDCCH in a Type1-PDCCH CSS set is not configured with same *qcl-Type*
set to \'typeD\' properties \[6, TS 38.214\] with a DM-RS for monitoring
the PDCCH in the Type0/0A/0B/2/3-PDCCH CSS set or in the USS set, and if
the PDCCH or an associated PDSCH overlaps in at least one symbol with a
PDCCH the UE monitors in a Type1-PDCCH CSS set or with an associated
PDSCH.

If a UE is provided

\- one or more search space sets by corresponding one or more of
*searchSpaceZero, searchSpaceSIB1*, *searchSpaceOtherSystemInformation*,
*pagingSearchSpace*, *ra-SearchSpace*, and

\- a C-RNTI, an MCS-C-RNTI, or a CS-RNTI

the UE monitors PDCCH candidates for DCI format 0_0 and DCI format 1_0
with CRC scrambled by the C-RNTI, the MCS-C-RNTI, or the CS-RNTI in the
one or more search space sets in a slot where the UE monitors PDCCH
candidates for at least a DCI format 0_0 or a DCI format 1_0 with CRC
scrambled by SI-RNTI, RA-RNTI, MsgB-RNTI, or P-RNTI.

If a UE is provided

\- one or more search space sets by corresponding one or more of
*searchSpaceZero, searchSpaceSIB1*, *searchSpaceOtherSystemInformation*,
*pagingSearchSpace*, *pei-SearchSpace, ra-SearchSpace*, or a CSS set by
*PDCCH-Config*, and

\- a SI-RNTI, a P-RNTI, a PEI-RNTI, a RA-RNTI, a MsgB-RNTI, a SFI-RNTI,
an INT-RNTI, a TPC-PUSCH-RNTI, a TPC-PUCCH-RNTI, or a TPC-SRS-RNTI

then, for a RNTI from any of these RNTIs, the UE does not expect to
process information from more than one DCI format with CRC scrambled
with the RNTI per slot.

Table 10.1-1: CCE aggregation levels and maximum number of PDCCH
candidates per CCE aggregation level for CSS sets configured by
*searchSpaceSIB1*

  ---------------------------------- ------------------------------------
  CCE Aggregation Level              Number of Candidates

  4                                  4

  8                                  2

  16                                 1
  ---------------------------------- ------------------------------------

For each DL BWP configured to a UE in a serving cell, the UE can be
provided by higher layer signalling with

\- $P \leq 3$ CORESETs if *coresetPoolIndex* is not provided, or if a
value of *coresetPoolIndex* is same for all CORESETs if
*coresetPoolIndex* is provided

\- $P \leq 5$ CORESETs if *coresetPoolIndex* is not provided for a first
CORESET, or is provided and has a value 0 for a first CORESET, and is
provided and has a value 1 for a second CORESET

For each CORESET, the UE is provided the following by
*ControlResourceSet*:

\- a CORESET index $p$, by *controlResourceSetId* or by
*controlResourceSetId-v1610*, where

\- $0 < p < 12$ if *coresetPoolIndex* is not provided, or if a value of
*coresetPoolIndex* is same for all CORESETs if *coresetPoolIndex* is
provided;

\- $0 < p < 16$ if *coresetPoolIndex* is not provided for a first
CORESET, or is provided and has a value 0 for a first CORESET, and is
provided and has a value 1 for a second CORESET;

\- a DM-RS scrambling sequence initialization value by
*pdcch-DMRS-ScramblingID*;

\- a precoder granularity for a number of REGs in the frequency domain
where the UE can assume use of a same DM-RS precoder by
*precoderGranularity*;

\- a number of consecutive symbols provided by *duration*;

\- a set of resource blocks provided by *frequencyDomainResources*;

\- CCE-to-REG mapping parameters provided by *cce-REG-MappingType*;

\- an antenna port quasi co-location, from a set of antenna port quasi
co-locations provided by *TCI-State*, indicating quasi co-location
information of the DM-RS antenna port for PDCCH reception;

\- an indication for a presence or absence of a transmission
configuration indication (TCI) field for a DCI format, other than DCI
format 1_0, that schedules PDSCH receptions or has associated HARQ-ACK
information without scheduling PDSCH and is provided by a PDCCH in
CORESET $p$, by *tci-PresentInDCI* or *tci-PresentDCI-1-2*.

When *precoderGranularity* = *allContiguousRBs*, a UE does not expect

\- to be configured a set of resource blocks of a CORESET that includes
more than four sub-sets of resource blocks that are not contiguous in
frequency

\- any RE of a CORESET to overlap with any RE determined from

\- *lte-CRS-ToMatchAround* or *LTE-CRS-PatternList*, if the UE is not
provided *pdcchCandidateReception-WithCRSOverlap*, or

\- a SS/PBCH block.

If a UE is provided two TCI states indicating quasi co-location
information of the DM-RS antenna port for PDCCH reception in a CORESET
associated with a Type3-PDCCH CSS set, the UE may assume the quasi
co-location information indicated in both of the two TCI states for the
PDCCH reception in the CORESET.

For each CORESET in a DL BWP of a serving cell, a respective
*frequencyDomainResources* provides a bitmap

\- if a CORESET is not associated with any search space set configured
with *freqMonitorLocations*, the bits of the bitmap have a one-to-one
mapping with non-overlapping groups of 6 consecutive PRBs, in ascending
order of the PRB index in the DL BWP bandwidth of $N_{RB}^{BWP}$ PRBs
with starting common RB position $N_{BWP}^{start}$, where the first
common RB of the first group of 6 PRBs has common RB index
$6 \cdot \left\lceil N_{BWP}^{start}/6 \right\rceil$ if *rb-Offset* is
not provided, or the first common RB of the first group of 6 PRBs has
common RB index $N_{BWP}^{start} + N_{RB}^{offset}$ where
$N_{RB}^{offset}$ is provided by *rb-Offset.*

\- if a CORESET is associated with at least one search space set
configured with *freqMonitorLocations*, the first $N_{RBG,set0}^{size}$
bits of the bitmap have a one-to-one mapping with non-overlapping groups
of 6 consecutive PRBs, in ascending order of the PRB index in each RB
set $k$ in the DL BWP bandwidth of $N_{RB}^{BWP}$ PRBs with starting
common RB position ${RB}_{s0 + k,DL}^{start,\mu}\ $ \[6, TS 38.214\],
where the first common RB of the first group of 6 PRBs has common RB
index ${RB}_{s0 + k,DL}^{start,\mu} + N_{RB}^{offset}$ and *k* is
indicated by *freqMonitorLocations* if provided for a search space set;
otherwise, $k = 0$.
$N_{RBG,set0}^{size} = \left\lfloor {(N}_{RB,set0}^{size} - N_{RB}^{offset})/6 \right\rfloor$,
$N_{RB,set0}^{size}$ is a number of available PRBs in the RB set 0 for
the DL BWP, and $N_{RB}^{offset}$ is provided by *rb-Offset* or
$N_{RB}^{offset} = 0$ if *rb-Offset* is not provided. If a UE is
provided RB sets in the DL BWP, the UE expects that the RBs of the
CORESET are within the union of the PRBs in the RB sets of the DL BWP.

For each CORESET provided by *cfr-ConfigMCCH-MTCH* or
*cfr-ConfigMCCH-MTCH-RedCap* or *cfr-ConfigMulticast* in a CFR of a
serving cell, the quantities $N_{RB}^{BWP}$ and $N_{BWP}^{start}$ in
this clause are replaced by the size of CFR $N_{RB}^{CFR}$ and starting
common RB position of CFR $N_{CFR}^{start}$, respectively.

For a CORESET other than a CORESET with index 0,

\- if a UE has not been provided a configuration of TCI state(s) by
*tci-StatesPDCCH-ToAddList* and *tci-StatesPDCCH-ToReleaseList* for the
CORESET, or has been provided initial configuration of more than one TCI
states for the CORESET by *tci-StatesPDCCH-ToAddList* and
*tci-StatesPDCCH-ToReleaseList* and has not received a MAC CE activation
command for one of the TCI states as described in \[11, TS 38.321\], the
UE assumes that the DM-RS antenna port associated with PDCCH receptions
is quasi co-located with

\- the one or more DL RS configured by a TCI state provided by
*CandidateTCI-State*, where the TCI state is indicated by an LTM Cell
Switch Command MAC CE except during RACH procedure for the RACH-based
LTM if applicable, otherwise,

\- the SS/PBCH block the UE identified during the initial access
procedure, or for a most recent configured grant PUSCH transmission as
described in clause 19 for a same HARQ process;

\- if a UE has been provided a configuration of more than one TCI states
by *tci-StatesPDCCH-ToAddList* and *tci-StatesPDCCH-ToReleaseList* for
the CORESET as part of Reconfiguration with sync procedure as described
in \[12, TS 38.331\] and has not received a MAC CE activation command
for one of the TCI states as described in \[11, TS 38.321\], the UE
assumes that the DM-RS antenna port associated with PDCCH receptions is
quasi co-located with the SS/PBCH block or the CSI-RS resource the UE
identified during the random access procedure initiated by the
Reconfiguration with sync procedure as described in \[12, TS 38.331\].

For a CORESET with index 0,

\- if the UE is provided *TCI-State* and *followUnifiedTCI-State* for
the CORESET, the UE assumes that a DM-RS antenna port for PDCCH
receptions in the CORESET and a DM-RS antenna port for PDSCH receptions
scheduled by DCI formats provided by PDCCH receptions in the CORESET are
quasi co-located with the reference signals provided by the indicated
*TCI-State* \[6, TS 38.214\]

\- else if the UE is provided *dl-OrJointTCI-StateList* and is indicated
a first *TCI-State* and a second *TCI-State*, and
*applyIndicatedTCI-State* for the CORESET

\- if the CORESET is associated with a Type 0/0A/2-PDCCH CSS set that
has search space set index 0

\- if *applyIndicatedTCI-State* = \'first\', the UE assumes that a DM-RS
antenna port for PDCCH receptions in the CORESET is quasi co-located
with the reference signals provided by the first *TCI-State*,

\- if *applyIndicatedTCI-State* = \'second\', the UE assumes that a
DM-RS antenna port for PDCCH receptions in the CORESET is quasi
co-located with the reference signals provided by the second
*TCI-State*,

\- if *applyIndicatedTCI-State* = \'none\', the UE assumes that a DM-RS
antenna port for PDCCH receptions in the CORESET is quasi co-located
with the one or more DL RS configured by a TCI state, where the TCI
state is indicated by a MAC CE activation command for the CORESET, if
any

\- else

\- if *applyIndicatedTCI-State* = \'first\', the UE assumes that a DM-RS
antenna port for PDCCH receptions in the CORESET is quasi co-located
with the reference signals provided by the first *TCI-State*,

\- if *applyIndicatedTCI-State* = \'second\', the UE assumes that a
DM-RS antenna port for PDCCH receptions in the CORESET is quasi
co-located with the reference signals provided by the second
*TCI-State*,

\- if *applyIndicatedTCI-State* = \'both\', the UE assumes that a DM-RS
antenna port for PDCCH receptions in the CORESET is quasi co-located
with the reference signals provided by the first and the second
*TCI-State,*

\- if *applyIndicatedTCI-State* = \'none\', the UE assumes that a DM-RS
antenna port for PDCCH receptions in the CORESET is quasi co-located
with the one or more DL RS configured by a TCI state, where the TCI
state is indicated by a MAC CE activation command for the CORESET.

\- else, the UE assumes that a DM-RS antenna port for PDCCH receptions
in the CORESET is quasi co-located with

\- the one or more DL RS configured by a TCI state, where the TCI state
is indicated by a MAC CE activation command for the CORESET, if any, or

\- the one or more DL RS configured by a TCI state provided by
*CandidateTCI-State*, where the TCI state is indicated by an LTM Cell
Switch Command MAC CE that triggers a RACH-less or RACH-based LTM cell
switch, if any, or

\- a SS/PBCH block the UE identified during a most recent random access
procedure not initiated by a PDCCH order that triggers a contention-free
random access procedure, if no MAC CE activation command indicating a
TCI state for the CORESET is received after the most recent random
access procedure, or a SS/PBCH block the UE identified during a most
recent configured grant PUSCH transmission as described in clause 19 or
22.1.

For a CORESET other than a CORESET with index 0, if a UE is provided a
single TCI state for a CORESET, or if the UE receives a MAC CE
activation command for one or two of the provided TCI states for a
CORESET, the UE assumes that the DM-RS antenna port associated with
PDCCH receptions in the CORESET is quasi co-located with the one or more
DL RS configured by the TCI states. For a CORESET with index 0, the UE
expects that a CSI-RS configured with *qcl-Type* set to \'typeD\' in a
TCI state indicated by a MAC CE activation command for the CORESET is
provided by a SS/PBCH block

\- if the UE receives a MAC CE activation command for one of the TCI
states, the UE applies the activation command in the first slot that is
after slot $k + 3N_{slot}^{subframe,\mu} + {2^{\mu} \bullet k}_{mac}$
where $k$ is the slot where the UE would transmit a PUCCH with HARQ-ACK
information for the PDSCH providing the activation command, $\mu$ is the
SCS configuration for the PUCCH in the slot when the activation command
is applied, and $k_{mac}$ is a number of slots for SCS configuration
$\mu = 0$ provided by *kmac* or $k_{mac} = 0$ if *kmac* is not provided.

If a UE is provided *TCI-State* in *dl-OrJointTCI-StateList*, a DM-RS
antenna port for PDCCH receptions in a CORESET, other than a CORESET
with index 0, associated only with USS sets and/or Type3-PDCCH CSS sets,
and a DM-RS antenna port for PDSCH receptions scheduled by DCI formats
provided by PDCCH receptions in the CORESET are quasi co-located with
reference signals provided by the indicated *TCI-State* \[6, TS
38.214\].

If a UE is provided *followUnifiedTCI-State* for a CORESET, other than a
CORESET with index 0, associated at least with CSS sets other than
Type3-PDCCH CSS sets, a DM-RS antenna port for PDCCH receptions in the
CORESET and a DM-RS antenna port for PDSCH receptions scheduled by DCI
formats provided by PDCCH receptions in the CORESET are quasi co-located
with reference signals provided by the indicated *TCI-State*.

If a UE is provided *dl-OrJointTCI-StateList* and is indicated a first
*TCI-State* and a second *TCI-State*, and is provided
*applyIndicatedTCI-State* for a CORESET, other than a CORESET with index
0,

\- if the CORESET is associated only with USS sets and/or Type3-PDCCH
CSS sets

\- if *applyIndicatedTCI-State* = \'first\', the UE assumes that a DM-RS
antenna port for PDCCH receptions in the CORESET is quasi co-located
with the reference signals provided by the first *TCI-State*

\- if *applyIndicatedTCI-State* = \'second\', the UE assumes that a
DM-RS antenna port for PDCCH receptions in the CORESET is quasi
co-located with the reference signals provided by the second *TCI-State*

\- if *applyIndicatedTCI-State* = \'both\', the UE assumes that a DM-RS
antenna port for PDCCH receptions in the CORESET is quasi co-located
with the reference signals provided by the first *TCI-State* and the
second *TCI-State*

\- if the CORESET is associated at least with CSS sets other than
Type3-PDCCH CSS sets,

\- if *applyIndicatedTCI-State* = \'first\', the UE assumes that a DM-RS
antenna port for PDCCH receptions in the CORESET is quasi co-located
with the reference signals provided by the first *TCI-State*

\- if *applyIndicatedTCI-State* = \'second\', the UE assumes that a
DM-RS antenna port for PDCCH receptions in the CORESET is quasi
co-located with the reference signals provided by the second *TCI-State*

\- if *applyIndicatedTCI-State* = \'both\', the UE assumes that a DM-RS
antenna port for PDCCH receptions in the CORESET is quasi co-located
with the reference signals provided by the first *TCI-State* and the
second *TCI-State*

\- if *applyIndicatedTCI-State* = \'none\', the UE assumes that a DM-RS
antenna port for PDCCH receptions in the CORESET is quasi co-located
with the one or more DL RS configured by a TCI state indicated by a MAC
CE activation command for the CORESET

If the UE is provided *dl-OrJointTCI-StateList* and

\- is not provided *coresetPoolIndex* or is provided *coresetPoolIndex*
with a value of 0 for first CORESETs on an active DL BWP of a serving
cell,

\- is provided *coresetPoolIndex* with a value of 1 for second CORESETs
on the active DL BWP of the serving cells, and

\- is provided *followUnifiedTCI-State* for the first and second
CORESETs, that do not include a CORESET with index 0 and are associated
only with USS sets and/or Type3-PDCCH CSS sets, or with CSS sets other
than Type3-PDCCH CSS sets,

the UE

\- assumes that DM-RS antenna ports for PDCCH receptions in the first
and second CORESETs, and DM-RS antenna ports for PDSCH receptions
scheduled by DCI formats provided by PDCCH receptions in the first and
second CORESETs, are quasi co-located with the reference signals
provided by indicated *TCI-State* specific to the first and second
CORESETs, respectively

\- transmits PUSCH scheduled by DCI formats provided by PDCCH receptions
in the first and second CORESETs using a spatial domain filter
corresponding to *TCI-State* or *TCI-UL-State* specific to the first and
second CORESETs, respectively.

If a UE is provided two *coresetPoolIndex* values 0 and 1 for first and
second CORESETs, or is not provided *coresetPoolIndex* value for first
CORESETs and is provided *coresetPoolIndex* value of 1 for second
CORESETs, respectively, a MAC CE command activating TCI states for the
first or second CORESETs \[11, TS 38.321\] can include
*coresetPoolIndex* value 0 or 1

\- if the UE is provided *SSB_MTC_AdditionalPCI*, the activated TCI
states for the first and/or the second CORESETs are for *physCellId*
from *ServingCellConfigCommon* and the activated TCI states for either
the first or the second CORESETs can be for *physCellId* from
*additionalPCI*.

If a UE is provided by *simultaneousTCI-UpdateList1* or
*simultaneousTCI-UpdateList2* up to two lists of cells for simultaneous
TCI state activation, the UE applies the antenna port quasi co-location
provided by one or two *TCI-State* each with same activated
*tci-StateID* value, to CORESETs with a same index in all configured DL
BWPs of all configured cells in a list determined from a serving cell
index, where one or two *tci-StateID*, the CORESET index, and the
serving cell index are provided by a MAC CE command.

For each DL BWP configured to a UE in a serving cell, the UE is provided
by higher layers with $S \leq 10$ search space sets where, for each
search space set from the $S$ search space sets, the UE is provided the
following by *SearchSpace*:

\- a search space set index $s$, $0 < s < 40$ , by *searchSpaceId*

\- an association between the search space set $\ s$ and a CORESET $p$
by *controlResourceSetId* or by *controlResourceSetId-v1610*

\- a PDCCH monitoring periodicity of $k_{s}$ slots and a PDCCH
monitoring offset of $o_{s}$ slots, by
*monitoringSlotPeriodicityAndOffset* or by
*monitoringSlotPeriodicityAndOffset-r17*

\- a PDCCH monitoring pattern within a slot, indicating first symbol(s)
of the CORESET for PDCCH monitoring within each slot where the UE
monitors PDCCH, by *monitoringSymbolsWithinSlot*

\- a duration of $T_{s} < k_{s}$ indicating a number of slots that the
search space set $s$ exists by *duration*, or a number of slots in
consecutive groups of slots where the search space set $s$ can exist by
*duration-r17*

\- a bitmap, by *monitoringSlotsWithinSlotGroup*, that applies per group
of slots and provides a PDCCH monitoring pattern indicating slots in a
group of slots for PDCCH monitoring

\- a size of the group of slots is same as a size of
*monitoringSlotsWithinSlotGroup*

\- for a Type1-PDCCH CSS set provided by *ra-SearchSpace* in dedicated
RRC signaling, or for a Type3-PDCCH CSS set, or for a USS set, the PDCCH
monitoring pattern indicates only consecutive slots in the group of
slots for PDCCH monitoring and, at least for one combination
$\left( X_{s},Y_{s} \right)$ indicated by the UE as a capability, a
number of the consecutive slots is not larger than $Y_{s}$

\- for a Type1-PDCCH CSS set provided by *ra-SearchSpace* in *SIB1*, the
PDCCH monitoring pattern indicates only up to 1 slot in the group of
slots for PDCCH monitoring

\- for a Type0-PDCCH CSS set or for a Type0A-PDCCH CSS set, or for a
Type2-PDCCH CSS set, the PDCCH monitoring pattern indicates slots in the
group of slots for PDCCH monitoring, and the slots are not restricted to
be consecutive, and the number of those slots is not larger than the
size of *monitoringSlotsWithinSlotGroup*

\- a number of PDCCH candidates $M_{s}^{(L)}$ per CCE aggregation level
$L$ by *aggregationLevel1*, *aggregationLevel2*, *aggregationLevel4*,
*aggregationLevel8*, and *aggregationLevel16*, for CCE aggregation level
1, CCE aggregation level 2, CCE aggregation level 4, CCE aggregation
level 8, and CCE aggregation level 16, respectively

\- an indication that search space set $s$ is either a CSS set or a USS
set by *searchSpaceType*

\- if search space set $s$ is a CSS set

\- an indication by *dci-Format0-0-AndFormat1-0* to monitor PDCCH
candidates for DCI format 0_0 and DCI format 1_0

\- an indication by *dci-Format2-0* to monitor one or two PDCCH
candidates, or to monitor one PDCCH candidate per RB set if the UE is
provided *freqMonitorLocations* for the search space set, for DCI format
2_0 and a corresponding CCE aggregation level

\- an indication by *dci-Format2-1* to monitor PDCCH candidates for DCI
format 2_1

\- an indication by *dci-Format2-2* to monitor PDCCH candidates for DCI
format 2_2

\- an indication by *dci-Format2-3* to monitor PDCCH candidates for DCI
format 2_3

\- an indication by *dci-Format2-4* to monitor PDCCH candidates for DCI
format 2_4

\- an indication by *dci-Format2-6* to monitor PDCCH candidates for DCI
format 2_6

\- an indication by *dci-Format2-9* to monitor PDCCH candidates for DCI
format 2_9

\- an indication by *dci-Format4-0* to monitor PDCCH candidates for DCI
format 4_0

\- an indication by *dci-Format4-1*, or *dci-Format4-2*, or
*dci-Format4-1-AndFormat4-2* to monitor PDCCH candidates for DCI format
4_1, or DCI format 4_2, or for both DCI format 4_1 and DCI format 4_2,
respectively

\- an indication by *searchSpaceLinkingId* that search space set $s$ is
linked to another search space set for which is provided a same value
for *searchSpaceLinkingId*

\- if search space set $s$ is a USS set,

\- an indication by *dci-Formats* to monitor PDCCH candidates either for
DCI format 0_0 and DCI format 1_0, or for DCI format 0_1 and DCI format
1_1, or

\- an indication by *dci-FormatsExt* to monitor PDCCH candidates for DCI
format 0_2 and DCI format 1_2, or for DCI format 0_1, DCI format 1_1,
DCI format 0_2, and DCI format 1_2, or

\- an indication by *dci-FormatsMC* to monitor PDCCH candidates for one
or both of DCI format 0_3 and DCI format 1_3, or

\- an indication by *dci-FormatsSL* to monitor PDCCH candidates for DCI
format 0_0 and DCI format 1_0, or for DCI format 0_1 and DCI format 1_1,
or for DCI format 3_0, or for DCI format 3_1, or for DCI format 3_0 and
DCI format 3_1, or

\- an indication by *dci-FormatsNCR* to monitor PDCCH candidates for DCI
format 2_8

\- a bitmap by *freqMonitorLocations*, if provided, to indicate an index
of one or more RB sets for the search space set $s$, where the MSB $k$
in the bitmap corresponds to RB set $k - 1$ in the DL BWP. For RB set
$k$ indicated in the bitmap, the first PRB of the frequency domain
monitoring location confined within the RB set is given by
${RB}_{s0 + k,DL}^{start,\mu} + N_{RB}^{offset}$, where
${RB}_{s0 + k,DL}^{start,\mu}$ is the index of first common RB of the RB
set $k$ \[6, TS 38.214\], and $N_{RB}^{offset}$ is provided by
*rb-Offset* or $N_{RB}^{offset} = 0$ if *rb-Offset* is not provided. For
each RB set with a corresponding value of 1 in the bitmap, the frequency
domain resource allocation pattern for the monitoring location is
determined based on the first $N_{RBG,\ set\ 0}^{size}$ bits in
*frequencyDomainResources* provided by the associated CORESET
configuration.

If the *monitoringSymbolsWithinSlot* indicates to a UE to monitor PDCCH
in a subset of up to three consecutive symbols that are same in every
slot where the UE monitors PDCCH for all search space sets, the UE does
not expect to be configured with a PDCCH SCS other than 15 kHz if the
subset includes at least one symbol after the third symbol.

A UE does not expect to be provided a first symbol and a number of
consecutive symbols for a CORESET that results to a PDCCH candidate
mapping to symbols of different slots.

A UE does not expect any two PDCCH monitoring occasions on an active DL
BWP, for a same search space set or for different search space sets, in
a same CORESET to be separated by a non-zero number of symbols that is
smaller than the CORESET duration.

A UE determines a PDCCH monitoring occasion on an active DL BWP from the
PDCCH monitoring periodicity, the PDCCH monitoring offset, and the PDCCH
monitoring pattern within a slot. If *monitoringSlotsWithinSlotGroup* is
not provided, the UE determines that PDCCH monitoring occasions exist in
a slot with number $n_{s,f}^{\mu}$ \[4, TS 38.211\] in a frame with
number $n_{f}$ if ($n_{f}$
$N_{slot\ }^{frame,\ \mu}$+$\ n_{s,f\ }^{\mu}$-$\ o_{s}$)$\ modk_{s} = 0$$\left( n_{f}N_{slot}^{frame,\mu} + n_{s,f}^{\mu} - o_{p,s} \right)mod\ k_{p,s} = 0$.
The UE monitors PDCCH candidates for search space set $s$ for $T_{s}$
consecutive slots, starting from slot $n_{s,f}^{\mu}$, and does not
monitor PDCCH candidates for search space set $s$ for the next
$k_{s} - T_{s}$ consecutive slots. If *monitoringSlotsWithinSlotGroup*
is provided, for search space set $s$, the UE determines that the slot
with number $n_{s,f}^{\mu}$ \[4, TS 38.211\] in a frame with number
$n_{f}$ satisfying ($n_{f}$
$N_{slot\ }^{frame,\ \mu}$+$\ n_{s,f\ }^{\mu}$-$\ o_{s}$)$\ modk_{s} = 0$
is the first slot in a first group of $L_{s}$ slots and that PDCCH
monitoring occasions exist in $T_{s}/L_{s}$ consecutive groups of slots
starting from the first group, where $L_{s}$ is the size of
*monitoringSlotsWithinSlotGroup*. The UE monitors PDCCH candidates for
search space set $s$ within $each\ of\ the\ T_{s}/L_{s}\ $ consecutive
groups of slots according to *monitoringSlotsWithinSlotGroup*, starting
from slot $n_{s,f}^{\mu}$, and does not monitor PDCCH candidates for
search space set $s$ for the next $k_{s} - T_{s}$ consecutive slots.

A USS at CCE aggregation level
$L \in \left\{ 1,\ 2,\ 4,\ 8,\ 16 \right\}$ is defined by a set of PDCCH
candidates for CCE aggregation level $L$.

If a UE is configured with *CrossCarrierSchedulingConfig* for a serving
cell, the carrier indicator field value corresponds to the value
indicated by *cif-InSchedulingCell* in *CrossCarrierSchedulingConfig.*
If a UE is configured with *MC-DCI-SetofCells* for a set of serving
cells, the UE is provided *nCI-Value* for the set of serving cells*.*

For an active DL BWP of a serving cell on which a UE monitors PDCCH
candidates in a USS, if the UE is not configured with a carrier
indicator field, the UE monitors the PDCCH candidates without carrier
indicator field. For an active DL BWP of a serving cell on which a UE
monitors PDCCH candidates in a USS, if a UE is configured with a carrier
indicator field, the UE monitors the PDCCH candidates with carrier
indicator field.

A UE does not expect to monitor PDCCH candidates on an active DL BWP of
a secondary cell if the UE is configured to monitor PDCCH candidates for
detection of DCI formats scheduling on that secondary cell in another
serving cell. For a serving cell included in *MC-DCI-SetofCells*, if
provided, the UE does not expect to monitor PDCCH candidates on more
than one scheduling cell for detection of DCI formats scheduling on the
serving cell. For the active DL BWP of a serving cell on which the UE
monitors PDCCH candidates, the UE monitors PDCCH candidates at least for
the same serving cell.

For a search space set $s$ associated with CORESET $p$, the CCE indexes
for aggregation level $L$ corresponding to PDCCH candidate
$m_{{s,n}_{CI}}^{(L)}\ $ of the search space set in slot $n_{s,f}^{\mu}$
for an active DL BWP of a serving cell corresponding to carrier
indicator field value $n_{CI}$, or corresponding to value $n_{CI}$ of
*nCI-Value* associated with a set of serving cells *MC-DCI-SetofCells*,
are given by

$$L \cdot \left\{ \left( Y_{p,n_{s,f}^{\mu}} + \left\lfloor \frac{m_{{s,n}_{CI}}^{(L)} \cdot N_{CCE,p}}{L \cdot M_{s,\max}^{(L)}} \right\rfloor + n_{CI} \right)mod\left\lfloor \frac{N_{CCE,p}}{L} \right\rfloor \right\} + i$$

where

for any CSS, $Y_{p,n_{s,f}^{\mu}} = 0$;

for a USS,
$Y_{p,n_{s,f}^{\mu}} = \left( {A_{p} \cdot Y}_{p,n_{s,f}^{\mu} - 1} \right)modD$,
$Y_{p, - 1} = n_{RNTI} \neq 0$, $A_{p} = 39827$ for $pmod3 = 0$,
$A_{p} = 39829$ for $pmod3 = 1$, $A_{p} = 39839$ for $pmod3 = 2$, and
$D = 65537$;

$i = 0,\cdots,L - 1$;

$N_{CCE,p}$ is the number of CCEs, numbered from 0 to $N_{CCE,p} - 1$,
in CORESET $p$ and, if any, per RB set

\- for CORESET 0, the CCEs are obtained prior to puncturing, if any, of
corresponding RBs \[4, TS 38.211\];

$n_{CI}$ is

\- the carrier indicator field value, if provided by
*cif-InSchedulingCell* in *CrossCarrierSchedulingConfig* for the serving
cell on which PDCCH is monitored, except for scheduling of the serving
cell from the same serving cell in which case $n_{CI} = 0$;

\- the *nCI-Value* provided for the set of serving cells
*MC-DCI-SetofCells*, if *MC-DCI-SetofCells* is provided;

\- otherwise, including for any CSS, $n_{CI} = 0$

$m_{{s,n}_{CI}}^{(L)} = 0,\cdots,M_{s,n_{CI}}^{(L)} - 1$, where
$M_{s,n_{CI}}^{(L)}$ is the number of PDCCH candidates the UE is
configured to monitor for aggregation level $L$ of a search space set
$s$ for a serving cell corresponding to $n_{CI}$;

for any CSS, $M_{s,\max}^{(L)} = M_{s,0}^{(L)}$;

for a USS, $M_{s,\max}^{(L)}$ is the maximum of $M_{s,n_{CI}}^{(L)}$
over all configured $n_{CI}$ values for a CCE aggregation level $L$ of
search space set $s$ ;

the RNTI value used for $n_{RNTI}$ is the C-RNTI.

For search space sets $s_{i}$ and $s_{j}$ that include
*searchSpaceLinkingId* with same value, a UE monitors, in monitoring
occasions with same index according to each of search space sets $s_{i}$
and $s_{j}$ in a slot, PDCCH candidates $m_{s_{i},n_{CI}}^{(L)}$ and
$m_{s_{j},n_{CI}}^{(L)}$, with
$m_{s_{i},n_{CI}}^{(L)} = m_{s_{j},n_{CI}}^{(L)}$, for detection of a
DCI format with same information. The UE expects
$k_{s_{i}} = k_{s_{j}}$,
$o_{s_{i}} = o_{s_{j}},\ T_{s_{i}} = T_{s_{j}}$,
$M_{s_{i}}^{(L)} = M_{s_{j}}^{(L)}$, and a same number of
non-overlapping PDCCH monitoring occasions per slot based on
corresponding *monitoringSymbolsWithinSlot*, for search space sets
$s_{i}$ and $s_{j}$. For CORESET $p_{i}$ associated with the search
space set $s_{i}$ and for CORESET $p_{j}$ associated with the search
space set $s_{j}$, the UE is provided *tci-PresentInDCI* or
*tci-PresentDCI-1-*2 for either none or both of CORESETs $p_{i}$ and
$p_{j}$. For CORESET $p_{i}$ associated with the search space set
$s_{i}$ and for CORESET $p_{j}$ associated with the search space set
$s_{j}$, the UE is either not provided *coresetPoolIndex* value of 1 for
any of the two CORESETs, or is provided *coresetPoolIndex* value of 1
for both CORESETs.

A UE can indicate by *numBD-twoPDCCH-r17* a capability for counting
PDCCH candidates $m_{s_{i},n_{CI}}^{(L)}$ and $m_{s_{j},n_{CI}}^{(L)}$
either as 2 PDCCH candidates or as 3 PDCCH candidates.

For search space sets $s_{i}$ and $s_{j}$ that include
*searchSpaceLinkingId* with same value, and for search space sets
$s_{k}$ and $s_{l}$ that include *searchSpaceLinkingId* with same value,
a UE expects to simultaneously monitor PDCCH candidates
$m_{s_{i},n_{CI,1}}^{(8)} = m_{s_{j},n_{CI,1}}^{(8)}$, and
$m_{s_{k},n_{CI,2}}^{(16)}$= $m_{s_{l},n_{CI,2}}^{(16)}$ only if a first
CCE of $m_{s_{i},n_{CI,1}}^{(8)}$ or $m_{s_{j},n_{CI,1}}^{(8)}$ has
different index than a first CCE of $m_{s_{k},n_{CI,2}}^{(16)}$ or
$m_{s_{l},n_{CI,2}}^{(16)}$ in a CORESET configured with
*cce-REG-MappingType* = \'*nonInterleaved*\' and with duration of one
symbol.

If a UE

\- is provided *monitoringCapabilityConfig* = *r16monitoringcapability*
for a downlink cell,

\- is provided, by *searchSpaceLinkingId* a same value for search space
sets $s_{i}$ and $s_{j}$ on the downlink cell, and

\- indicates *numBD-twoPDCCH-r17* with value of 3

the UE counts each PDCCH candidate for the one of the search space sets
$s_{i}$ and $s_{j}$ that the UE monitors PDCCH in the later span, as two
PDCCH candidates. The UE does not expect a first PDCCH candidate from
search space set $s_{i}$ or $s_{j}$ and a second PDCCH candidate from a
search space set $s_{k}$ that does not include *searchSpaceLinkingId* to
use a same set of CCEs and same scrambling in a same CORESET, and
provide respective first and second DCI formats with same size, in any
span other than the first span in a slot.

A UE does not expect to be provided *freqMonitorLocations* for a search
space set $s$ in a serving cell if *intraCellGuardBandsDL-List*
indicates that no intra-cell guard-bands are configured for the serving
cell.

A UE that

\- is configured for operation with carrier aggregation, and

\- indicates support of search space sharing through
*searchSpaceSharingCA-UL* or through *searchSpaceSharingCA-DL*, and

\- has a PDCCH candidate with CCE aggregation level $L$ in CORESET $p$
associated with search space set $s_{i}$ of a scheduling cell for
detection of a first DCI format, other than DCI format 0_0 or DCI format
1_0, having a first size and scheduling

\- PUSCH transmission or configured grant Type 2 PUSCH release on
serving cell $n_{CI,2}$, or

\- PDSCH reception or having associated HARQ-ACK information without
scheduling PDSCH reception on serving cell $n_{CI,2}$

can receive a corresponding PDCCH through a PDCCH candidate with CCE
aggregation level $L$ in CORESET $p$ associated with search space set
$s_{j}$ of the scheduling cell for detection of a second DCI format
having a second size and associated with scheduling on serving cell
$n_{CI,1}$ if the first size and the second size are same and if neither
of search space sets $s_{i}$ and $s_{j}$ includes
*searchSpaceLinkingId*.

A UE expects to monitor PDCCH candidates for up to 4 sizes of DCI
formats that include up to 3 sizes of DCI formats with CRC scrambled by
C-RNTI per serving cell. The UE counts a number of sizes for DCI formats
per serving cell based on a number of configured PDCCH candidates in
respective search space sets for the corresponding active DL BWP. If the
UE monitors PDCCH candidates for detection of one or both of DCI format
0_3 and DCI format 1_3 for scheduling on serving cells from a set of
serving cells, the serving cell for counting the size of one or both DCI
format 0_3 and DCI format 1_3, respectively, is

\- the scheduling cell, if the scheduling cell is included in the set of
serving cells and the UE is provided search space sets for the PDCCH
candidates only on the scheduling cell

\- a serving cell from the set of serving cells, if search space sets
with same *searchSpaceId* for one or both of DCI format 0_3 and DCI
format 1_3, respectively, are provided on the serving cell and on the
scheduling cell.

A UE does not expect to detect, in a same PDCCH monitoring occasion, a
DCI format with CRC scrambled by a SI-RNTI, RA-RNTI, MsgB-RNTI, TC-RNTI,
P-RNTI, C-RNTI, CS-RNTI, MCS-RNTI, MCCH-RNTI, G-RNTI, G-CS-RNTI, or
Multicast MCCH-RNTI and a DCI format with CRC scrambled by a SL-RNTI or
a SL-CS-RNTI for scheduling respective PDSCH reception and PSSCH
transmission on a same serving cell.

A PDCCH candidate with index $m_{{s_{j},n}_{CI}}^{(L)}$ for a search
space set $s_{j}$ using a set of $L$ CCEs in a CORESET $p$ on the active
DL BWP for serving cell $n_{CI}$, or for set of serving cells associated
with *nCI-Value* having value $n_{CI}$, is not counted for monitoring if
there is a PDCCH candidate with index $m_{{s_{i},n}_{CI}}^{(L)}$ for a
search space set $s_{i}{< s}_{j}$, or if there is a PDCCH candidate with
index $n_{{s_{j},n}_{CI}}^{(L)}$ and
$n_{{s_{j},n}_{CI}}^{(L)} < m_{{s_{j},n}_{CI}}^{(L)}$, in the CORESET
$p$ on the active DL BWP for serving cell $n_{CI}$, or for set of
serving cells $n_{CI}$, respectively, using a same set of $L$ CCEs, the
PDCCH candidates have identical scrambling, and the corresponding DCI
formats for the PDCCH candidates have a same size; otherwise, the PDCCH
candidate with index $m_{{s_{j},n}_{CI}}^{(L)}$ is counted for
monitoring.

For search space sets $s_{i}$ and $s_{j}$ that include
*searchSpaceLinkingId* with same value, and for search space set $s_{k}$
that does not include *searchSpaceLinkingId*, when a UE

\- monitors PDCCH candidates
$m_{s_{i},n_{CI,1}}^{(L)} = m_{s_{j},n_{CI,1}}^{(L)}$ for detection of a
first DCI format,

\- monitors PDCCH candidate $m_{s_{k},n_{CI,2}}^{(L)}$ for detection of
a second DCI format having a same size as the first DCI format,

\- the PDCCH candidate $m_{s_{i},n_{CI,1}}^{(L)}$, or the PDCCH
candidate $m_{s_{j},n_{CI,1}}^{(L)}$, and the PDCCH candidate
$m_{s_{k},n_{CI,2}}^{(L)}$ have identical scrambling and use a same set
of CCEs over same symbols in a slot in a CORESET $p$,

the PDCCH candidate $m_{s_{k},n_{CI,2}}^{(L)}$ is not counted for
monitoring and the UE assumes that a detected DCI format is the first
DCI format. A UE may monitor PDCCH candidate $m_{s_{k},n_{CI,2}}^{(L)}$
depending on a corresponding capability \[18, TS 38.306\].

For search space sets $s_{i}$ and $s_{j}$ that include
*searchSpaceLinkingId* with same value, and for search space set $s_{k}$
that does not include *searchSpaceLinkingId*, when a UE

\- monitors PDCCH candidates $m_{s_{i},n_{CI,1}}^{(8)} =$
$m_{s_{j},n_{CI,1}}^{(8)}$ for detection of a first DCI format and
monitors PDCCH candidate $m_{s_{k},n_{CI,2}}^{(16)}$ for detection of a
second DCI format, or monitors PDCCH candidates
$m_{s_{i},n_{CI,1}}^{(16)} = m_{s_{j},n_{CI,1}}^{(16)}$ for detection of
the first DCI format and monitors PDCCH candidate
$m_{s_{k},n_{CI,2}}^{(8)}$ for detection of the second DCI format, and

\- one of the PDCCH candidates $m_{s_{i},n_{CI,1}}^{(8)}$ and
$m_{s_{j},n_{CI,1}}^{(8)}$, and the PDCCH candidate
$m_{s_{k},n_{CI,2}}^{(16)}$, or one of the PDCCH candidates
$m_{s_{i},n_{CI,1}}^{(16)}$ and $m_{s_{j},n_{CI,1}}^{(16)}$, and the
PDCCH candidate $m_{s_{k},n_{CI,2}}^{(8)}$, have a first CCE with same
index and are simultaneously monitored in a CORESET $p$ with
*cce-REG-MappingType* = \'*nonInterleaved*\' and duration of one symbol,

the UE assumes that a detected DCI format is the first DCI format.

For search space sets $s_{i}$ and $s_{j}$, that include
*searchSpaceLinkingId* with same value, and for search space sets
$s_{k}$ and $s_{l}$ that include *searchSpaceLinkingId* with same value,
and for detection of DCI formats with same size, a UE expects different
CCEs or different scrambling in a CORESET $p$ for any of first PDCCH
candidates $m_{s_{i},n_{CI,1}}^{(L)}$ and $m_{s_{j},n_{CI,1}}^{(L)}$,
with $m_{s_{i},n_{CI,1}}^{(L)} = m_{s_{j},n_{CI,1}}^{(L)}$, and any of
second PDCCH candidates $m_{s_{k},n_{CI,2}}^{(L)}$ and
$m_{s_{l},n_{CI,2}}^{(L)}$, with
$m_{s_{k},n_{CI,2}}^{(L)} = m_{s_{l},n_{CI,2}}^{(L)}$ that the UE would
simultaneously monitor.

Table 10.1-2 provides the maximum number of monitored PDCCH candidates,
$M_{PDCCH}^{max,slot,\mu}$, per slot for a UE in a DL BWP with SCS
configuration $\mu$ for operation with a single serving cell.

Table 10.1-2: Maximum number
$\mathbf{M}_{\mathbf{PDCCH}}^{\mathbf{max,slot,\mu}}$ of monitored PDCCH
candidates per slot for a DL BWP with SCS configuration
$\mathbf{\mu \in}\left\{ \mathbf{0,\ 1,2,3} \right\}$ for a single
serving cell

  ------------------ -----------------------------------------------------------
  $$\mathbf{\mu}$$   Maximum number of monitored PDCCH candidates per slot and
                     per serving cell
                     $\mathbf{M}_{\mathbf{PDCCH}}^{\mathbf{max,slot,\mu}}$

  0                  44

  1                  36

  2                  22

  3                  20
  ------------------ -----------------------------------------------------------

Table 10.1-2A provides the maximum number of monitored PDCCH candidates,
$M_{PDCCH}^{max,(X,Y),\mu}$, per span for a UE in a DL BWP with SCS
configuration $\mu$ for operation with a single serving cell.

Table 10.1-2A: Maximum number
$\mathbf{M}_{\mathbf{PDCCH}}^{\mathbf{max,}\left( \mathbf{X,Y} \right)\mathbf{,\mu}}$
of monitored PDCCH candidates in a span for combination $\mathbf{(X,Y)}$
for a DL BWP with SCS configuration
$\mathbf{\mu \in}\left\{ \mathbf{0,\ 1} \right\}$ for a single serving
cell

+------------------+-------------------------------+-------------------------------+-------------------------------+
|                  | Maximum number                                                                                |
|                  | $\mathbf{M}_{\mathbf{PDCCH}}^{\mathbf{max,}\left( \mathbf{X,Y} \right)\mathbf{,\mu}}$ of      |
|                  | monitored PDCCH candidates per span for combination $\left( \mathbf{X,Y} \right)$ and per     |
|                  | serving cell                                                                                  |
+------------------+-------------------------------+-------------------------------+-------------------------------+
| $$\mathbf{\mu}$$ | (2, 2)                        | (4, 3)                        | (7, 3)                        |
+------------------+-------------------------------+-------------------------------+-------------------------------+
| 0                | 14                            | 28                            | 44                            |
+------------------+-------------------------------+-------------------------------+-------------------------------+
| 1                | 12                            | 24                            | 36                            |
+------------------+-------------------------------+-------------------------------+-------------------------------+

Table 10.1-2B provides the maximum number of monitored PDCCH candidates,
$M_{PDCCH}^{max,X_{s},\mu}$, per group of $X_{s}$ slots for combination
$(X_{s},Y_{s})$ for a UE in a DL BWP with SCS configuration $\mu$ for
operation with a single serving cell.

Table 10.1-2B: Maximum number
$\mathbf{M}_{\mathbf{PDCCH}}^{\mathbf{max,}\mathbf{X}_{\mathbf{s}}\mathbf{,\mu}}$
of monitored PDCCH candidates per group of $\mathbf{X}_{\mathbf{s}}$
slots for combination
$\left( \mathbf{X}_{\mathbf{s}}\mathbf{,}\mathbf{Y}_{\mathbf{s}} \right)$
for a DL BWP with SCS configuration
$\mathbf{\mu \in}\left\{ \mathbf{5,\ 6} \right\}$ for a single serving
cell

+------------------+-----------------------+-----------------------+-----------------------+-----------------------+
|                  | Maximum number                                                                                |
|                  | $\mathbf{M}_{\mathbf{PDCCH}}^{\mathbf{max,}\mathbf{X}_{\mathbf{s}}\mathbf{,\mu}}$ of          |
|                  | monitored PDCCH candidates in a group of $\mathbf{X}_{\mathbf{s}}$ slots per combination      |
|                  | $\left( \mathbf{X}_{\mathbf{s}}\mathbf{,}\mathbf{Y}_{\mathbf{s}} \right)$ and per serving     |
|                  | cell                                                                                          |
+------------------+-----------------------+-----------------------+-----------------------+-----------------------+
| $$\mathbf{\mu}$$ | (4, 1)                | (4, 2)                | (8, 1)                | (8, 4)                |
+------------------+-----------------------+-----------------------+-----------------------+-----------------------+
| 5                | 20                    | 20                    | \-                    | \-                    |
+------------------+-----------------------+-----------------------+-----------------------+-----------------------+
| 6                | 10                    | 10                    | 20                    | 20                    |
+------------------+-----------------------+-----------------------+-----------------------+-----------------------+

Table 10.1-3 provides the maximum number of non-overlapped CCEs,
$C_{PDCCH}^{max,slot,\mu}$, for a DL BWP with SCS configuration $\mu$
that a UE is expected to monitor corresponding PDCCH candidates per slot
for operation with a single serving cell.

CCEs for PDCCH candidates are non-overlapped if they correspond to

\- different CORESET indexes, or

\- different first symbols for the reception of the respective PDCCH
candidates.

Table 10.1-3: Maximum number
$\mathbf{C}_{\mathbf{PDCCH}}^{\mathbf{max,slot,\mu}}$ of non-overlapped
CCEs per slot for a DL BWP with SCS configuration
$\mathbf{\mu \in}\left\{ \mathbf{0,\ 1,2,3} \right\}$ for a single
serving cell

  ------------------ ----------------------------------------------------------
  $$\mathbf{\mu}$$   Maximum number of non-overlapped CCEs per slot and per
                     serving cell
                     $\mathbf{C}_{\mathbf{PDCCH}}^{\mathbf{max,slot,\mu}}$

  0                  56

  1                  56

  2                  48

  3                  32
  ------------------ ----------------------------------------------------------

Table 10.1-3A provides the maximum number of non-overlapped CCEs,
$C_{PDCCH}^{max,(X,Y),\mu}$, for a DL BWP with SCS configuration $\mu$
that a UE is expected to monitor corresponding PDCCH candidates per span
for operation with a single serving cell.

Table 10.1-3A: Maximum number
$\mathbf{C}_{\mathbf{PDCCH}}^{\mathbf{max,}\left( \mathbf{X,Y} \right)\mathbf{,\mu}}$
of non-overlapped CCEs in a span for combination
$\left( \mathbf{X,Y} \right)$ for a DL BWP with SCS configuration
$\mathbf{\mu \in}\left\{ \mathbf{0,\ 1} \right\}$ for a single serving
cell

+---------+-------------------------------+-------------------------------+-------------------------------+
|         | Maximum number                                                                                |
|         | $\mathbf{C}_{\mathbf{PDCCH}}^{\mathbf{max,}\left( \mathbf{X,Y} \right)\mathbf{,\mu}}$ of      |
|         | non-overlapped CCEs per span for combination $\left( \mathbf{X,Y} \right)$ and per serving    |
|         | cell                                                                                          |
+---------+-------------------------------+-------------------------------+-------------------------------+
| $$\mu$$ | (2, 2)                        | (4, 3)                        | (7, 3)                        |
+---------+-------------------------------+-------------------------------+-------------------------------+
| 0       | 18                            | 36                            | 56                            |
+---------+-------------------------------+-------------------------------+-------------------------------+
| 1       | 18                            | 36                            | 56                            |
+---------+-------------------------------+-------------------------------+-------------------------------+

Table 10.1-3B provides the maximum number of non-overlapped CCEs,
$C_{PDCCH}^{max,X_{s},\mu}$, for a DL BWP with SCS configuration $\mu$
that a UE is expected to monitor corresponding PDCCH candidates per
group of $X_{s}$ slots for combination $\left( X_{s},Y_{s} \right)$ for
operation with a single serving cell.

Table 10.1-3B: Maximum number
$\mathbf{C}_{\mathbf{PDCCH}}^{\mathbf{max,}\mathbf{X}_{\mathbf{s}}\mathbf{,\mu}}$
of non-overlapped CCEs in a group of $\mathbf{X}_{\mathbf{s}}$ slots for
any combination
$\left( \mathbf{X}_{\mathbf{s}}\mathbf{,}\mathbf{Y}_{\mathbf{s}} \right)$
for a DL BWP with SCS configuration
$\mathbf{\mu \in}\left\{ \mathbf{5,\ 6} \right\}$ for a single serving
cell

+------------------+-----------------------+-----------------------+-----------------------+-----------------------+
|                  | Maximum number of non-overlapped CCEs in a group of $\mathbf{X}_{\mathbf{s}}$ slots per       |
|                  | combination $\left( \mathbf{X}_{\mathbf{s}}\mathbf{,}\mathbf{Y}_{\mathbf{s}} \right)$ and per |
|                  | serving cell                                                                                  |
|                  | $\mathbf{C}_{\mathbf{PDCCH}}^{\mathbf{max,}\mathbf{X}_{\mathbf{s}}\mathbf{,\mu}}$             |
+------------------+-----------------------+-----------------------+-----------------------+-----------------------+
| $$\mathbf{\mu}$$ | (4, 1)                | (4, 2)                | (8, 1)                | (8, 4)                |
+------------------+-----------------------+-----------------------+-----------------------+-----------------------+
| 5                | 32                    | 32                    | \-                    | \-                    |
+------------------+-----------------------+-----------------------+-----------------------+-----------------------+
| 6                | 16                    | 16                    | 32                    | 32                    |
+------------------+-----------------------+-----------------------+-----------------------+-----------------------+

In the following, if a UE monitors PDCCH candidates on a scheduling cell
for detection of DCI format 0_3 or DCI format 1_3 for scheduling on
serving cells from a set of serving cells, the serving cell for counting
the PDCCH candidates and a corresponding number of non-overlapping CCEs
is

\- the scheduling cell, if the scheduling cell is included in the set of
serving cells and the UE is provided search space sets for the PDCCH
candidates only on the scheduling cell

\- a serving cell from the set of serving cells, if search space sets
with same *searchSpaceId* for one or both of DCI format 0_3 and DCI
format 1_3, respectively, are provided on the serving cell and on the
scheduling cell.

For the following procedures in this clause, downlink cells are
scheduled cells on which a UE is provided search space sets.

If a UE

\- does not report *pdcch-BlindDetectionCA, pdcch-BlindDetectionCA1*,
*pdcch-BlindDetectionCA2*, or *pdcch-BlindDetectionCA3*, or is not
provided *BDFactorR*, $\gamma = R$

\- reports *pdcch-BlindDetectionCA*, *pdcch-BlindDetectionCA1*,
*pdcch-BlindDetectionCA2*, or *pdcch-BlindDetectionCA3*, the UE can be
indicated by *BDFactorR* either $\gamma = 1$ or $\gamma = R$

If a UE is configured with
$N_{\text{cells,0}}^{\text{DL,}\mu} + N_{\text{cells,1}}^{\text{DL,}\mu}$
downlink cells for which the UE is not provided
*monitoringCapabilityConfig,* or is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* and is not
provided *CORESETPoolIndex*, with associated PDCCH candidates monitored
in the active DL BWPs of the scheduling cells using SCS configuration
$\mu$ where
$\sum_{\mu = 0}^{3}\left( N_{\text{cells,0}}^{\text{DL,}\mu} + \gamma \bullet N_{\text{cells,1}}^{\text{DL,}\mu} \right) \leq N_{\text{cells}}^{\text{cap}}$,
the UE is not required to monitor, on the active DL BWPs of the
scheduling cells,

\- more than
$M_{\text{PDCCH}}^{\text{total,slot,}\mu} = M_{\text{PDCCH}}^{\text{max,slot,}\mu}$
PDCCH candidates or more than
$C_{\text{PDCCH}}^{\text{total,slot,}\mu} = C_{\text{PDCCH}}^{\text{max,slot,}\mu}$
non-overlapped CCEs per slot for each scheduled cell when the scheduling
cell is from the $N_{\text{cells,0}}^{\text{DL,}\mu}$ downlink cells, or

\- more than
$M_{\text{PDCCH}}^{\text{total,slot,}\mu} = \gamma \bullet M_{\text{PDCCH}}^{\text{max,slot,}\mu}$
PDCCH candidates or more than
$C_{\text{PDCCH}}^{\text{total,slot,}\mu} = \gamma \bullet C_{\text{PDCCH}}^{\text{max,slot,}\mu}$
non-overlapped CCEs per slot for each scheduled cell when the scheduling
cell is from the $N_{\text{cells,1}}^{\text{DL,}\mu}$ downlink cells

\- more than $M_{\text{PDCCH}}^{\text{max,slot,}\mu}$ PDCCH candidates
or more than $C_{\text{PDCCH}}^{\text{max,slot,}\mu}$ non-overlapped
CCEs per slot for CORESETs with same *coresetPoolIndex* value for each
scheduled cell when the scheduling cell is from the
$N_{\text{cells,1}}^{\text{DL,}\mu}$ downlink cells

$N_{\text{cells}}^{\text{cap}}$ is replaced by
$N_{\text{cells,r15}}^{\text{cap-r16}}$, if a UE is configured with
downlink cells for which the UE is provided both
*monitoringCapabilityConfig* = *r15monitoringcapability* and
*monitoringCapabilityConfig* = *r16monitoringcapability*.
$N_{\text{cells}}^{\text{cap}}$ is replaced by
$N_{\text{cells, r15/r17}}^{\text{cap-r17}}$, if a UE is configured with
downlink cells for which the UE is provided both
*monitoringCapabilityConfig* = *r15monitoringcapability* and
*monitoringCapabilityConfig* =
*r17monitoringcapability.*$\ N_{\text{cells}}^{\text{cap}}$ is replaced
by $N_{\text{cells, r15/ \{r16, r17\} }}^{\text{cap-r17}}$, if a UE is
configured with downlink cells for which the UE is provided both
*monitoringCapabilityConfig* = *r15monitoringcapability* and
*monitoringCapabilityConfig* = *r16monitoringcapability* and
*monitoringCapabilityConfig* = *r17monitoringcapability*.

If a UE

\- is configured with
$N_{\text{cells,0}}^{\text{DL,}\mu} + N_{\text{cells,1}}^{\text{DL,}\mu}$
downlink cells for which the UE is not provided
*monitoringCapabilityConfig,* or is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* and is not
provided *coresetPoolIndex*,

\- with associated PDCCH candidates monitored in the active DL BWPs of
the scheduling cell(s) using SCS configuration $\mu$, where
$\sum_{\mu = 0}^{3}\left( N_{\text{cells,0}}^{\text{DL,}\mu} + \gamma \bullet N_{\text{cells,1}}^{\text{DL,}\mu} \right) > N_{\text{cells}}^{\text{cap}}$,
and

\- a DL BWP of an activated cell is the active DL BWP of the activated
cell, and a DL BWP of a deactivated cell is the DL BWP with index
provided by *firstActiveDownlinkBWP-Id* for the deactivated cell,

the UE is not required to monitor more than
$M_{\text{PDCCH}}^{\text{total,slot,}\mu} = \left\lfloor N_{\text{cells}}^{\text{cap}} \cdot M_{\text{PDCCH}}^{\text{max,slot,}\mu} \cdot \frac{\left( N_{\text{cells,0}}^{\text{DL,}\mu} + \gamma \bullet N_{\text{cells,1}}^{\text{DL,}\mu} \right)}{\sum_{j = 0}^{3}\left( N_{\text{cells,0}}^{\text{DL,}j} + \gamma \bullet N_{\text{cells,1}}^{\text{DL,}j} \right)} \right\rfloor$
PDCCH candidates or more than
$C_{\text{PDCCH}}^{\text{total,slot,}\mu} = \left\lfloor N_{\text{cells}}^{\text{cap}} \cdot C_{\text{PDCCH}}^{\text{max,slot,}\mu} \cdot \frac{\left( N_{\text{cells,0}}^{\text{DL,}\mu} + \gamma \bullet N_{\text{cells,1}}^{\text{DL,}\mu} \right)}{\sum_{j = 0}^{3}\left( N_{\text{cells,0}}^{\text{DL,}j} + \gamma \bullet N_{\text{cells,1}}^{\text{DL,}j} \right)} \right\rfloor$
non-overlapped CCEs per slot on the active DL BWP(s) of scheduling
cell(s) from the
$N_{\text{cells,0}}^{\text{DL,}\mu} + N_{\text{cells,1}}^{\text{DL,}\mu}$
downlink cells. $N_{\text{cells}}^{\text{cap}}$ is replaced by
$N_{\text{cells,r15}}^{\text{cap-r16}}\ $if a UE is configured with
downlink cells for which the UE is provided both
*monitoringCapabilityConfig* = *r15monitoringcapability* and
*monitoringCapabilityConfig* = *r16monitoringcapability*.
$N_{\text{cells}}^{\text{cap}}$ is replaced by
$N_{\text{cells, r15/r17}}^{\text{cap-r17}}$, if a UE is configured with
downlink cells for which the UE is provided both
*monitoringCapabilityConfig* = *r15monitoringcapability* and
*monitoringCapabilityConfig* =
*r17monitoringcapability.*$\ N_{\text{cells}}^{\text{cap}}$ is replaced
by $N_{\text{cells, r15/ \{r16, r17\} }}^{\text{cap-r17}}$. If a UE is
configured with downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* and
*monitoringCapabilityConfig* = *r16monitoringcapability* and
*monitoringCapabilityConfig* = *r17monitoringcapability*.

For each scheduled cell from the $N_{\text{cells,0}}^{\text{DL,}\mu}$
downlink cells, the UE is not required to monitor on the active DL BWP
with SCS configuration $\mu$ of the scheduling cell more than
$\min\left( M_{\text{PDCCH}}^{\text{max,slot,}\mu},M_{\text{PDCCH}}^{\text{total,slot,}\mu} \right)$
PDCCH candidates or more than
$\min\left( C_{\text{PDCCH}}^{\text{max,slot,}\mu},C_{\text{PDCCH}}^{\text{total,slot,}\mu} \right)$
non-overlapped CCEs per slot.

For each scheduled cell from the $N_{\text{cells,1}}^{\text{DL,}\mu}$
downlink cells, the UE is not required to monitor on the active DL BWP
with SCS configuration $\mu$ of the scheduling cell

\- more than
$\min\left( {\gamma \bullet M}_{\text{PDCCH}}^{\text{max,slot,}\mu},M_{\text{PDCCH}}^{\text{total,slot,}\mu} \right)$
PDCCH candidates or more than
$\min\left( {\gamma \bullet C}_{\text{PDCCH}}^{\text{max,slot,}\mu},C_{\text{PDCCH}}^{\text{total,slot,}\mu} \right)$
non-overlapped CCEs per slot

\- more than
$\min\left( M_{\text{PDCCH}}^{\text{max,slot,}\mu},M_{\text{PDCCH}}^{\text{total,slot,}\mu} \right)$
PDCCH candidates or more than
$\min\left( C_{\text{PDCCH}}^{\text{max,slot,}\mu},C_{\text{PDCCH}}^{\text{total,slot,}\mu} \right)$
non-overlapped CCEs per slot for CORESETs with same *coresetPoolIndex*
value

If a UE is configured with $N_{cells,r16}^{DL,\mu}$ downlink cells for
which the UE is provided *monitoringCapabilityConfig* =
*r16monitoringcapability* and with associated PDCCH candidates monitored
in the active DL BWPs of the scheduling cells using SCS configuration
$\mu$, and with $N_{cells,r16}^{DL,(X,Y),\mu}$ of the
$N_{cells,r16}^{DL,\mu}$ downlink cells using combination $(X,Y)$ for
PDCCH monitoring, where
$\sum_{\mu = 0}^{1}N_{cells,r16}^{DL,\mu} \leq N_{\text{cells}}^{\text{cap-r16}}$,
the UE is not required to monitor, on the active DL BWP of the
scheduling cell, more than
$M_{\text{PDCCH}}^{\text{total,(X,Y),}\mu} = M_{\text{PDCCH}}^{\text{max,(X,Y),}\mu}$
PDCCH candidates or more than
$C_{\text{PDCCH}}^{\text{total,(X,Y),}\mu} = C_{\text{PDCCH}}^{\text{max,(X,Y),}\mu}$
non-overlapped CCEs per span for each scheduled cell when the scheduling
cell is from the $N_{cells,r16}^{DL,(X,Y),\mu}$ downlink cells. If a UE
is configured with downlink cells for which the UE is provided both
*monitoringCapabilityConfig* = *r15monitoringcapability* and
*monitoringCapabilityConfig* = *r16monitoringcapability*,
$N_{\text{cells}}^{\text{cap-r16}}$ is replaced by
$N_{\text{cells,r16}}^{\text{cap-r16}}$. If a UE is configured with
downlink cells for which the UE is provided both
*monitoringCapabilityConfig* = *r16monitoringcapability* and
*monitoringCapabilityConfig* = *r17monitoringcapability,*
$\ N_{\text{cells}}^{\text{cap}}$ is replaced by
$N_{\text{cells, r16/r17}}^{\text{cap-r17}}$*.*$\ $If a UE is configured
with downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* and
*monitoringCapabilityConfig* = *r16monitoringcapability* and
*monitoringCapabilityConfig* = *r17monitoringcapability,*
$\ N_{\text{cells}}^{\text{cap}}$ is replaced by
$N_{\text{cells, r16/ \{r15, r17\} }}^{\text{cap-r17}}$*.*

If a UE is configured only with $N_{cells,r16}^{DL,\mu}$ downlink cells
for which the UE is provided *monitoringCapabilityConfig* =
*r16monitoringcapability* and with associated PDCCH candidates monitored
in the active DL BWPs of the scheduling cells using SCS configuration
$\mu$, and with $N_{cells,r16}^{DL,(X,Y),\mu}$ of the
$N_{cells,r16}^{DL,\mu}$ downlink cells using combination $(X,Y)$ for
PDCCH monitoring, where
$\sum_{\mu = 0}^{1}N_{cells,r16}^{DL,\mu} > N_{\text{cells}}^{\text{cap-r16}}$,
a DL BWP of an activated cell is the active DL BWP of the activated
cell, and a DL BWP of a deactivated cell is the DL BWP with index
provided by *firstActiveDownlinkBWP-Id* for the deactivated cell, the UE
is not required to monitor more than
$M_{\text{PDCCH}}^{\text{total,(X,Y),}\mu} = \left\lfloor N_{\text{cells}}^{\text{cap-r16}} \cdot M_{\text{PDCCH}}^{\text{max,(X,Y),}\mu} \cdot \frac{N_{cells,r16}^{DL,(X,Y),\mu}}{\sum_{j = 0}^{1}N_{cells,r16}^{DL,j}} \right\rfloor$
PDCCH candidates or more than
$C_{\text{PDCCH}}^{\text{total,(X,Y),}\mu} = \left\lfloor N_{\text{cells}}^{\text{cap-r16}} \cdot C_{\text{PDCCH}}^{\text{max,(X,Y),}\mu} \cdot \frac{N_{cells,r16}^{DL,(X,Y),\mu}}{\sum_{j = 0}^{1}N_{cells,r16}^{DL,j}} \right\rfloor$
non-overlapped CCEs

\- per set of spans on the active DL BWP(s) of all scheduling cell(s)
from the $N_{cells,r16}^{DL,(X,Y),\mu}$ downlink cells within every $X$
symbols, if the union of PDCCH monitoring occasions on all scheduling
cells from the $N_{cells,r16}^{DL,(X,Y),\mu}$ downlink cells results to
PDCCH monitoring according to the combination $(X,Y)$ and any pair of
spans in the set is within $Y$ symbols, where first $X$ symbols start at
a first symbol with a PDCCH monitoring occasion and next $X$ symbols
start at a first symbol with a PDCCH monitoring occasion that is not
included in the first $X$ symbols

\- per set of spans across the active DL BWP(s) of all scheduling cells
from the $N_{cells,r16}^{DL,(X,Y),\mu}$ downlink cells, with at most one
span per scheduling cell for each set of spans, otherwise

where $N_{cells,r16}^{DL,j}$ is a number of configured cells with
associated PDCCH candidates monitored in the active DL BWPs of the
scheduling cells using SCS configuration $j$. If a UE is configured with
downlink cells for which the UE is provided both
*monitoringCapabilityConfig* = *r15monitoringcapability* and
*monitoringCapabilityConfig* = *r16monitoringcapability*,
$N_{\text{cells}}^{\text{cap-r16}}$ is replaced by
$N_{\text{cells,r16}}^{\text{cap-r16}}$. If a UE is configured with
downlink cells for which the UE is provided both
*monitoringCapabilityConfig* = *r16monitoringcapability* and
*monitoringCapabilityConfig* = *r17monitoringcapability,*
$\ N_{\text{cells}}^{\text{cap}}$ is replaced by
$N_{\text{cells, r16/r17}}^{\text{cap-r17}}$*.*$\ $If a UE is configured
with downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* and
*monitoringCapabilityConfig* = *r16monitoringcapability* and
*monitoringCapabilityConfig* = *r17monitoringcapability,*
$\ N_{\text{cells}}^{\text{cap}}$ is replaced by
$N_{\text{cells, r16/ \{r15, r17\} }}^{\text{cap-r17}}$*.*

For each scheduled cell from the $N_{cells,r16}^{DL,(X,Y),\mu}$ downlink
cells using combination $(X,Y)$, the UE is not required to monitor on
the active DL BWP with SCS configuration $\mu$ of the scheduling cell,
more than
$\min\left( M_{PDCCH}^{max,(X,Y),\mu},M_{PDCCH}^{total,(X,Y),\mu} \right)$
PDCCH candidates or more than
$\min\left( C_{PDCCH}^{max,(X,Y),\mu},C_{PDCCH}^{total,(X,Y),\mu} \right)$
non-overlapped CCEs per span.

A UE does not expect to be configured CSS sets, except for CSS sets
provided by *searchSpaceMCCH*, *searchSpaceMTCH*,
*searchSpaceMulticastMCCH*, *searchSpaceMulticastMTCH* or by
*SearchSpace* in *pdcch-ConfigMulticast* for DCI formats with CRC
scrambled by G-RNTI or G-CS-RNTI, that result to corresponding total, or
per scheduled cell, numbers of monitored PDCCH candidates and
non-overlapped CCEs per slot, per group of $X_{s}$ slots for a
corresponding combination $\left( X_{s},Y_{s} \right)$, or per span that
exceed the corresponding maximum numbers per slot, or per group of
$X_{s}$ slots for a corresponding combination
$\left( X_{s},Y_{s} \right)$, or per span, respectively.

For same cell scheduling or for cross-carrier scheduling, a UE does not
expect a number of PDCCH candidates, and a number of corresponding
non-overlapped CCEs per slot, or per group of $X_{s}$ slots for a
corresponding combination $\left( X_{s},Y_{s} \right)$, or per span, on
a secondary cell to be larger than the corresponding numbers that the UE
is capable of monitoring on the secondary cell per slot, or per group of
$X_{s}$ slots for a corresponding combination
$\left( X_{s},Y_{s} \right)$, or per span, respectively. If a UE is
provided *monitoringCapabilityConfig* = *r16monitoringcapability* for
the primary cell, except the first span of each slot, the UE does not
expect a number of PDCCH candidates and a number of corresponding
non-overlapped CCEs per span on the primary cell to be larger than the
corresponding numbers that the UE is capable of monitoring on the
primary cell per span.

If a UE is configured with
$N_{\text{cells,r17,0}}^{\text{DL,}\mu} + N_{\text{cells,r17,1}}^{\text{DL,}\mu}$
downlink cells for which the UE is provided *monitoringCapabilityConfig*
= *r17monitoringcapability* and with associated PDCCH candidates
monitored in the active DL BWPs of the scheduling cells using SCS
configuration $\mu$, and with
$N_{\text{cells,r17,0}}^{\text{DL,}X_{s},\mu} + N_{\text{cells,r17,1}}^{\text{DL,}X_{s},\mu}$
of the
$N_{\text{cells,r17,0}}^{\text{DL,}\mu} + N_{\text{cells,r17,1}}^{\text{DL,}\mu}$
downlink cells using any combination $\left( X_{s},Y_{s} \right)$ for a
group of $X_{s}$ slots for PDCCH monitoring, where
$\sum_{\mu = 5}^{6}\left( N_{\text{cells,r17,0}}^{\text{DL},\mu} + {\gamma \bullet N}_{\text{cells,r17,1}}^{\text{DL},\mu} \right) \leq N_{\text{cells}}^{\text{cap-r17}}$,
the UE is not required to monitor, on the active DL BWP of the
scheduling cell,

\- more than
$M_{\text{PDCCH}}^{\text{total,}X_{s}\text{,}\mu} = M_{\text{PDCCH}}^{\text{max,}X_{s}\text{,}\mu}$
PDCCH candidates or more than
$C_{\text{PDCCH}}^{\text{total,}X_{s}\text{,}\mu} = C_{\text{PDCCH}}^{\text{max,}X_{s}\text{,}\mu}$
non-overlapped CCEs per group of $X_{s}$ slots for each scheduled cell
when the scheduling cell is from the $N_{cells,r17,0}^{DL,X_{s},\mu}$
downlink cells, or

\- more than
$M_{\text{PDCCH}}^{\text{total,}X_{s}\text{,}\mu} = {\gamma \bullet M}_{\text{PDCCH}}^{\text{max,}X_{s}\text{,}\mu}$
PDCCH candidates or more than
$C_{\text{PDCCH}}^{\text{total,}X_{s}\text{,}\mu} = {\gamma \bullet C}_{\text{PDCCH}}^{\text{max,}X_{s}\text{,}\mu}$
non-overlapped CCEs per group of $X_{s}$ slots for each scheduled cell
when the scheduling cell is from the $N_{cells,r17,1}^{DL,X_{s},\mu}$
downlink cells, or

\- more than $M_{\text{PDCCH}}^{\text{max,}X_{s}\text{,}\mu}$ PDCCH
candidates or more than $C_{\text{PDCCH}}^{\text{max,}X_{s}\text{,}\mu}$
non-overlapped CCEs per group of $X_{s}$ slots for CORESETs with same
*coresetPoolIndex* for each scheduled cell when the scheduling cell is
from the $N_{cells,r17,1}^{DL,X_{s},\mu}$ downlink cells

If the UE is configured with downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* and downlink
cells for which the UE is provided *monitoringCapabilityConfig* =
*r17monitoringcapability* for the active DL BWPs,
$N_{\text{cells}}^{\text{cap-r17}}$ is replaced by
$N_{\text{cells,r17/r15}}^{\text{cap-r17}}$. If the UE is configured
with downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* and downlink
cells for which the UE is provided *monitoringCapabilityConfig* =
*r17monitoringcapability* for the active DL BWPs,
$N_{\text{cells}}^{\text{cap-r17}}$ is replaced by
$N_{\text{cells,r17/r16}}^{\text{cap-r17}}$. If the UE is configured
with downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* and downlink
cells for which the UE is provided *monitoringCapabilityConfig* =
*r16monitoringcapability* and downlink cells for which the UE is
provided *monitoringCapabilityConfig* = *r17monitoringcapability* for
the active DL BWPs, $N_{\text{cells}}^{\text{cap-r17}}$ is replaced by
$N_{\text{cells,r17/\{r15,r16\}}}^{\text{cap-r17}}$. If, for one or more
of the cells, the UE is provided with *monitoringCapabilityConfig* =
*r16monitoringcapability*, $\gamma = 1$.

If a UE is configured
$N_{\text{cells,r17,0}}^{\text{DL,}\mu} + N_{\text{cells,r17,1}}^{\text{DL,}\mu}$
downlink cells for which the UE is provided *monitoringCapabilityConfig*
= *r17monitoringcapability* and with associated PDCCH candidates
monitored in the active DL BWPs of the scheduling cells using SCS
configuration $\mu$, and with
$N_{\text{cells,r17,0}}^{\text{DL,}X_{s},\mu} + N_{\text{cells,r17,1}}^{\text{DL,}X_{s},\mu}$
of the
$N_{\text{cells,r17,0}}^{\text{DL,}\mu} + N_{\text{cells,r17,1}}^{\text{DL,}\mu}$
downlink cells using any combination $\left( X_{s},Y_{s} \right)$ for a
group of $X_{s}$ slots for PDCCH monitoring, where
$\sum_{\mu = 5}^{6}\left( N_{\text{cells,r17,0}}^{\text{DL},\mu} + {\gamma \bullet N}_{\text{cells,r17,1}}^{\text{DL},\mu} \right) > N_{\text{cells}}^{\text{cap-r17}}$,
a DL BWP of an activated cell is the active DL BWP of the activated
cell, and a DL BWP of a deactivated cell is the DL BWP with index
provided by *firstActiveDownlinkBWP-Id* for the deactivated cell, the UE
is not required to monitor more than
$M_{PDCCH}^{total,X_{s},\mu} = \left\lfloor N_{\text{cells}}^{\text{cap-r17}} \cdot M_{PDCCH}^{max,X_{s},\mu} \cdot \frac{\left( N_{\text{cells,r17,0}}^{\text{DL,}X_{s},\mu} + {\gamma \bullet N}_{\text{cells,r17,1}}^{\text{DL,}X_{s},\mu} \right)}{\sum_{j = 5}^{6}\left( N_{\text{cells,r17,0}}^{\text{DL},j} + {\gamma \bullet N}_{\text{cells,r17,1}}^{\text{DL},j} \right)} \right\rfloor$
PDCCH candidates, or more than
$C_{PDCCH}^{total,X_{s},\mu} = \left\lfloor N_{\text{cells}}^{\text{cap-r17}} \cdot C_{PDCCH}^{max,X_{s},\mu} \cdot \frac{\left( N_{\text{cells,r17,0}}^{\text{DL,}X_{s},\mu} + {\gamma \bullet N}_{\text{cells,r17,1}}^{\text{DL,}X_{s},\mu} \right)}{\sum_{j = 5}^{6}\left( N_{\text{cells,r17,0}}^{\text{DL},j} + {\gamma \bullet N}_{\text{cells,r17,1}}^{\text{DL},j} \right)} \right\rfloor$
non-overlapped CCEs, per group of $X_{s}$ slots on the active DL BWP(s)
of scheduling cell(s) from the
$N_{\text{cells,r17,0}}^{\text{DL,}X_{s},\mu} + N_{\text{cells,r17,1}}^{\text{DL,}X_{s},\mu}$
downlink cells where
$N_{\text{cells,r17,0}}^{\text{DL},j} + N_{\text{cells,r17,1}}^{\text{DL},j}$
is a number of configured cells with associated PDCCH candidates
monitored in the active DL BWPs of the scheduling cells using SCS
configuration $j$.

If the UE is configured with downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* and downlink
cells for which the UE is provided *monitoringCapabilityConfig* =
*r17monitoringcapability* for the active DL BWPs,
$N_{\text{cells}}^{\text{cap-r17}}$ is replaced by
$N_{\text{cells,r17/r15}}^{\text{cap-r17}}$. If the UE is configured
with downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* and downlink
cells for which the UE is provided *monitoringCapabilityConfig* =
*r17monitoringcapability* for the active DL BWPs,
$N_{\text{cells}}^{\text{cap-r17}}$ is replaced by
$N_{\text{cells,r17/r16}}^{\text{cap-r17}}$. If the UE is configured
with downlink cells for which the UE is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* and downlink
cells for which the UE is provided *monitoringCapabilityConfig* =
*r16monitoringcapability* and downlink cells for which the UE is
provided *monitoringCapabilityConfig* = *r17monitoringcapability* for
the active DL BWPs, $N_{\text{cells}}^{\text{cap-r17}}$ is replaced by
$N_{\text{cells,r17/\{r15,r16\}}}^{\text{cap-r17}}$. If, for one or more
of the cells, the UE is provided with *monitoringCapabilityConfig* =
*r16monitoringcapability*, $\gamma = 1$.

For each scheduled cell from the $N_{cells,r17,0}^{DL,X_{s},\mu}$
downlink cells using any combination $\left( X_{s},Y_{s} \right)$ for a
group of $X_{s}$ slots, the UE is not required to monitor on the active
DL BWP with SCS configuration $\mu$ of the scheduling cell, more than
$\min\left( M_{PDCCH}^{max,X_{s},\mu},M_{PDCCH}^{total,X_{s},\mu} \right)$
PDCCH candidates or more than
$\min\left( C_{PDCCH}^{max,X_{s},\mu},C_{PDCCH}^{total,X_{s},\mu} \right)$
non-overlapped CCEs per group of $X_{s}$ slots.

For each scheduled cell from the $N_{cells,r17,1}^{DL,X_{s},\mu}$
downlink cells using any combination $\left( X_{s},Y_{s} \right)$ for a
group of $X_{s}$ slots, the UE is not required to monitor on the active
DL BWP with SCS configuration $\mu$ of the scheduling cell,

\- more than
$\min\left( {\gamma \bullet M}_{PDCCH}^{max,X_{s},\mu},M_{PDCCH}^{total,X_{s},\mu} \right)$
PDCCH candidates or more than
$\min\left( {\gamma \bullet C}_{PDCCH}^{max,X_{s},\mu},C_{PDCCH}^{total,X_{s},\mu} \right)$
non-overlapped CCEs per group of $X_{s}$ slots

\- more than
$\min\left( M_{PDCCH}^{max,X_{s},\mu},M_{PDCCH}^{total,X_{s},\mu} \right)$
PDCCH candidates or more than
$\min\left( C_{PDCCH}^{max,X_{s},\mu},C_{PDCCH}^{total,X_{s},\mu} \right)$
non-overlapped CCEs per group of $X_{s}$ slots for CORESETs with the
same *coresetPoolIndex* value.

For cross-carrier scheduling, the number of PDCCH candidates for
monitoring and the number of non-overlapped CCEs per span or per slot or
per group of $X_{s}$ slots are separately counted for each scheduled
cell.

The UE allocates PDCCH candidates for monitoring to USS sets for the
primary cell having an active DL BWP with SCS configuration $\mu$ in a
slot if the UE is not provided *monitoringCapabilityConfig* for the
primary cell or if the UE is provided *monitoringCapabilityConfig* =
*r15monitoringcapability* for the primary cell, or in the first span of
each slot if the UE is provided *monitoringCapabilityConfig* =
*r16monitoringcapability* for the primary cell, or in a group of $X_{s}$
slots for a corresponding combination $\left( X_{s},Y_{s} \right)$ if
the UE is provided *monitoringCapabilityConfig* =
*r17monitoringcapability* for the primary cell, according to the
following pseudocode.

If for the USS sets for scheduling on the primary cell the UE is not
provided *coresetPoolIndex* for first CORESETs, or is provided
*coresetPoolIndex* with value 0 for first CORESETs, and is provided
*coresetPoolIndex* with value 1 for second CORESETs, and if
$\min\left( {\gamma \bullet M}_{\text{PDCCH}}^{\text{max,slot,}\mu},M_{\text{PDCCH}}^{\text{total,slot,}\mu} \right) > \min\left( M_{\text{PDCCH}}^{\text{max,slot,}\mu},M_{\text{PDCCH}}^{\text{total,slot,}\mu} \right)$
or
$\min\left( {\gamma \bullet C}_{\text{PDCCH}}^{\text{max,slot,}\mu},C_{\text{PDCCH}}^{\text{total,slot,}\mu} \right) > \min\left( C_{\text{PDCCH}}^{\text{max,slot,}\mu},C_{\text{PDCCH}}^{\text{total,slot,}\mu} \right)$,
the following pseudocode applies only to USS sets associated with the
first CORESETs. A UE does not expect to monitor PDCCH in a USS set
without allocated PDCCH candidates for monitoring.

In the following pseudocode, if the UE is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* for the primary
cell,$\ M_{\text{PDCCH}}^{\text{max,slot,}\mu}\ $and
$C_{\text{PDCCH}}^{\text{max,slot,}\mu}\ $are replaced by
$M_{\text{PDCCH}}^{\text{max,(X,Y),}\mu}\ $and
$C_{\text{PDCCH}}^{\text{max,(X,Y),}\mu}$ respectively, and
$M_{\text{PDCCH}}^{\text{total,slot,}\mu}\ $and
$C_{\text{PDCCH}}^{\text{total,slot,}\mu}\ $are replaced by
$M_{\text{PDCCH}}^{\text{total,(X,Y),}\mu}\ $and
$C_{\text{PDCCH}}^{\text{total,(X,Y),}\mu}$ respectively.

In the following pseudocode, if the UE is provided
*monitoringCapabilityConfig* = *r17monitoringcapability* for the primary
cell,$\ M_{\text{PDCCH}}^{\text{max,slot,}\mu}\ $and
$C_{\text{PDCCH}}^{\text{max,slot,}\mu}\ $are replaced by
$M_{\text{PDCCH}}^{\text{max,}X_{s}\text{,}\mu}\ $and
$C_{\text{PDCCH}}^{\text{max,}X_{s}\text{,}\mu}$ respectively, and
$M_{\text{PDCCH}}^{\text{total,slot,}\mu}\ $and
$C_{\text{PDCCH}}^{\text{total,slot,}\mu}\ $are replaced by
$M_{\text{PDCCH}}^{\text{total,}X_{s}\text{,}\mu}\ $and
$C_{\text{PDCCH}}^{\text{total,}X_{s}\text{,}\mu}$ respectively.

For all search space sets that a UE monitors PDCCH on the primary cell
within a slot $n$, or within a group of $X_{s}$ slots for a
corresponding combination $\left( X_{s},Y_{s} \right)$, or within a span
in slot $n$, denote by $S_{css}$ a set of CSS sets, except for CSS sets
provided by *searchSpaceMCCH*, *searchSpaceMTCH*,
*searchSpaceMulticastMCCH*, *searchSpaceMulticastMTCH* or by
*SearchSpace* in *pdcch-ConfigMulticast* for DCI formats with CRC
scrambled by G-RNTI or G-CS-RNTI, with cardinality of $I_{css}$ and by
$S_{uss}$ a set of USS sets and CSS sets provided by *searchSpaceMCCH*,
*searchSpaceMTCH* or by *SearchSpace* in *pdcch-ConfigMulticast* for DCI
formats with CRC scrambled by G-RNTI or G-CS-RNTI with cardinality of
$J_{uss}$ with PDCCH candidates and non-overlapping CCEs counted on the
primary cell. The location of search space sets $s_{j}$,
$0 \leq j < J_{uss}$, in $S_{uss}$ is according to an ascending order of
the search space set index.

Denote by $M_{S_{css}(i)}^{(L)}$, $0 \leq i < I_{css}$, the number of
counted PDCCH candidates for monitoring for CSS set $S_{css}(i)$ and by
$M_{S_{uss}(j)}^{(L)}$, $0 \leq j < J_{uss}$, the number of counted
PDCCH candidates for monitoring for search space set $S_{uss}(j)$. If a
UE indicates *numBD-twoPDCCH-r17* with value of 3 and is provided
*searchSpaceLinkingId* with same value for search space sets $s_{j}$ and
$s_{i}$, with $s_{i} < s_{j}$, set
$M_{S_{css}(j)}^{(L)} = 2{\bullet M}_{S_{css}(j)}^{(L)}$ if $s_{i}$ and
$s_{j}$ are CSS sets or set
$M_{S_{uss}(j)}^{(L)} = 2 \bullet M_{S_{uss}(j)}^{(L)}$ if $s_{i}$ and
$s_{j}$ are USS sets.

For the CSS sets in $S_{css}$, a UE monitors
$M_{PDCCH}^{css} = \sum_{i = 0}^{I_{css} - 1}{\sum_{L}^{}M_{S_{css}(i)}^{(L)}}$
PDCCH candidates requiring a total of $C_{PDCCH}^{css}$ non-overlapping
CCEs in a slot, of in group of $X_{s}$ slots for a corresponding
combination $\left( X_{s},Y_{s} \right)$, or in a span.

Denote by $V_{CCE}\left( S_{uss}(j) \right)$ the set of non-overlapping
CCEs for search space set $S_{uss}(j)$ and by
$\text{C}\left( V_{CCE}\left( S_{uss}(j) \right) \right)$; the
cardinality of $V_{CCE}\left( S_{uss}(j) \right)$ where a UE determines
the non-overlapping CCEs for search space set $S_{uss}(j)$ considering
the allocated PDCCH candidates for monitoring for the CSS sets in
$S_{css}$ and the allocated PDCCH candidates for monitoring for all
search space sets $S_{uss}(k)$, $0 \leq k \leq j$.

Set
$M_{PDCCH}^{uss} = \min\left( M_{\text{PDCCH}}^{\text{max,slot,}\mu},M_{\text{PDCCH}}^{\text{total,slot,}\mu} \right) - M_{PDCCH}^{css}$

Set
$C_{PDCCH}^{uss} = \min\left( C_{\text{PDCCH}}^{\text{max,slot,}\mu},C_{\text{PDCCH}}^{\text{total,slot,}\mu} \right) - C_{PDCCH}^{css}$

Set $j = 0$

while $\sum_{L}^{}M_{S_{uss}(j)}^{(L)} \leq M_{PDCCH}^{uss}$ AND
$\text{C}\left( V_{CCE}\left( S_{uss}(j) \right) \right) \leq C_{PDCCH}^{uss}$

allocate $\sum_{L}^{}M_{S_{uss}(j)}^{(L)}$ PDCCH candidates for
monitoring to search space set $S_{uss}(j)$

$M_{PDCCH}^{uss} = M_{PDCCH}^{uss} - \sum_{L}^{}M_{S_{uss}(j)}^{(L)}$;

$C_{PDCCH}^{uss} = C_{PDCCH}^{uss} - \text{C}\left( V_{CCE}\left( S_{uss}(j) \right) \right)$;

$j = j + 1$;

end while

If a UE

\- is configured for single cell operation or for operation with carrier
aggregation in a same frequency band, and

\- monitors PDCCH candidates in overlapping PDCCH monitoring occasions
in multiple CORESETs that have been configured with same or different
*qcl-Type* set to \'typeD\' properties on active DL BWP(s) of one or
more cells

the UE monitors PDCCHs only in a CORESET, and in any other CORESET from
the multiple CORESETs that have been configured with *qcl-Type* set to
same \'typeD\' properties as the CORESET, on the active DL BWP of a cell
from the one or more cells

\- the CORESET corresponds to the CSS set with the lowest index in the
cell with the lowest index containing CSS, if any; otherwise, to the USS
set with the lowest index in the cell with lowest index

\- the lowest USS set index is determined over all USS sets with at
least one PDCCH candidate in overlapping PDCCH monitoring occasions

If a UE

\- is not provided *coresetPoolIndex* for first CORESETs, or is provided
*coresetPoolIndex* with value 0 for first CORESETs, and

\- is provided *coresetPoolIndex* with value 1 for second CORESETs, and

\- is provided *twoQCL-TypeD-ForMultiDCI*

the UE applies the procedures in the above paragraph independently
across the first CORESETs and the second CORESETs.

If a UE

\- is configured for single cell operation or for operation with carrier
aggregation in a same frequency band,

\- monitors PDCCH candidates in overlapping PDCCH monitoring occasions
in multiple CORESETs that have been configured with same or different
*qcl-Type* set to \'typeD\' properties on active DL BWP(s) of one or
more cells, and

\- is provided *twoQCLTypeDforPDCCHRepetition*

the UE monitors PDCCHs only in a first CORESET with *qcl-Type* set to
first \'typeD\' properties and, if any, in a second CORESET with
*qcl-Type* set to second \'typeD\' properties that are different than
the first \'typeD\' properties, and in any other CORESET from the
multiple CORESETs with corresponding *qcl-Type* set to either the first
\'typeD\' properties or to the second \'typeD\' properties

\- the first CORESET corresponds to the CSS set with the lowest index in
the cell with the lowest index containing CSS sets, if any; otherwise,
to the USS set with the lowest index in the cell with lowest index

\- excluding CSS sets and USS sets associated with CORESETs with
*qcl-Type* set to first \'typeD\' properties, the second CORESET
corresponds to the CSS set with the lowest index in the cell with the
lowest index containing CSS sets, if any; otherwise, to the USS set with
the lowest index in the cell with lowest index, where the CSS set or the
USS set includes *searchSpaceLinkingId* with same value as any CSS set
or any USS set associated with CORESETs with *qcl-Type* set to first
\'typeD\' properties

\- the lowest USS set index is determined over all USS sets with at
least one PDCCH candidate in overlapping PDCCH monitoring occasions

If a UE

\- is configured for single cell operation or for operation with carrier
aggregation in a same frequency band,

\- monitors PDCCH candidates in overlapping PDCCH monitoring occasions
in multiple CORESETs that have been configured with same or different
*qcl-Type* set to \'typeD\' properties on active DL BWP(s) of one or
more cells,

\- one or more CORESETs have two activated TCI states, and

\- reports *sfn-QCL-TypeD-Collision-twoTCI*

the UE monitors PDCCHs only in a CORESET with a first *qcl-Type* set to
first \'typeD\' properties and, if any, a second *qcl-Type* set to
second \'typeD\' properties that are different than the first \'typeD\'
properties, and in any other CORESET from the multiple CORESETs with
corresponding *qcl-Type* set to the first \'typeD\' properties and/or to
the second \'typeD\' properties

\- the CORESET corresponds to the CSS set with the lowest index in the
cell with the lowest index containing CSS, if any; otherwise, to the USS
set with the lowest index in the cell with lowest index

\- the lowest USS set index is determined over all USS sets with at
least one PDCCH candidate in overlapping PDCCH monitoring occasions

For the purpose of determining the CORESET, a SS/PBCH block is
considered to have different QCL \'typeD\' properties than a CSI-RS.

For the purpose of determining the CORESET, a first CSI-RS associated
with a SS/PBCH block in a first cell and a second CSI-RS in a second
cell that is also associated with the SS/PBCH block are assumed to have
same QCL \'typeD\' properties.

The allocation of non-overlapping CCEs and of PDCCH candidates for PDCCH
monitoring is according to all search space sets associated with the
multiple CORESETs on the active DL BWP(s) of the one or more cells.

The number of active TCI states is determined from the multiple
CORESETs.

If a UE

\- is configured for single cell operation or for operation with carrier
aggregation in a same frequency band, and

\- monitors PDCCH candidates in overlapping PDCCH monitoring occasions
in multiple CORESETs where none of the CORESETs has TCI-states
configured with *qcl-Type* set to \'typeD\',

the UE is required to monitor PDCCH candidates in overlapping PDCCH
monitoring occasions for search space sets associated with different
CORESETs.

For a scheduled cell and at any time, if a UE is provided a C-RNTI, the
UE expects to have received at most 16 PDCCHs for DCI formats with CRC
scrambled by C-RNTI, CS-RNTI, MCS-C-RNTI, G-RNTI for multicast, or
G-CS-RNTI scheduling 16 PDSCH receptions for which the UE has not
received any corresponding PDSCH symbol and at most 16 PDCCHs for DCI
formats with CRC scrambled by C-RNTI, CS-RNTI, or MCS-C-RNTI scheduling
16 PUSCH transmissions for which the UE has not transmitted any
corresponding PUSCH symbol.

If a UE is not provided *monitoringCapabilityConfig* =
*r16monitoringcapability* for any serving cell, and

\- is not configured for NR-DC operation and indicates through
*pdcch-BlindDetectionCA* a capability to monitor PDCCH candidates for
$N_{cells}^{cap} \geq 4$ downlink cells and the UE is configured with
$N_{cells}^{DL} > 4$ downlink cells or $N_{cells}^{UL} > 4$ uplink
cells, or

\- is configured with NR-DC operation and for a cell group with
$N_{cells}^{DL}$ downlink cells or $N_{cells}^{UL}$ uplink cells

the UE expects to have respectively received at most
${16 \bullet N}_{cells}^{cap}$ PDCCHs for

\- DCI formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a
MCS-C-RNTI, or a G-RNTI for multicast, or a G-CS-RNTI scheduling
${16 \bullet N}_{cells}^{cap}$ PDSCH receptions for which the UE has not
received any corresponding PDSCH symbol over all $N_{cells}^{DL}$
downlink cells

\- DCI formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a
MCS-C-RNTI scheduling ${16 \bullet N}_{cells}^{cap}$ PUSCH transmissions
for which the UE has not transmitted any corresponding PUSCH symbol over
all $N_{cells}^{UL}$ uplink cells

If a UE is provided *monitoringCapabilityConfig* =
*r16monitoringcapability* for all serving cells*,* and

\- is not configured for NR-DC operation and indicates through
*pdcch-MonitoringCA* a capability to monitor PDCCH candidates for
$N_{cells}^{cap - r16} \geq 2$ downlink cells and the UE is configured
with $N_{cells}^{DL} > 2$ downlink cells or $N_{cells}^{UL} > 2$ uplink
cells, or

\- is configured with NR-DC operation and for a cell group with
$N_{cells}^{DL}$ downlink cells or $N_{cells}^{UL}$ uplink cells

the UE expects to have respectively received at most
${16 \bullet N}_{cells}^{cap - r16}$ PDCCHs for

\- DCI formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a
MCS-C-RNTI, or a G-RNTI for multicast, or a G-CS-RNTI scheduling
${16 \bullet N}_{cells}^{cap - r16}$ PDSCH receptions for which the UE
has not received any corresponding PDSCH symbol over all
$N_{cells}^{DL}$ downlink cells

\- DCI formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a
MCS-C-RNTI scheduling ${16 \bullet N}_{cells}^{cap - r16}$ PUSCH
transmissions for which the UE has not transmitted any corresponding
PUSCH symbol over all $N_{cells}^{UL}$ uplink cells.

If a UE is provided *monitoringCapabilityConfig* =
*r16monitoringcapability* for at least one serving cell and is not
provided *monitoringCapabilityConfig* = *r16monitoringcapability* for at
least one serving cell, and

\- is not configured for NR-DC operation, and indicates a capability to
monitor PDCCH candidates for $N_{cells,r15}^{cap - r16} \geq 1$ downlink
cells and $N_{cells,r16}^{cap - r16} \geq 1$ downlink cells, and the UE
is configured with $N_{cells}^{DL} > 1$ downlink cells or
$N_{cells}^{UL} > 1$ uplink cells, or

\- is configured with NR-DC operation and for a cell group with
$N_{cells}^{DL}$ downlink cells or $N_{cells}^{UL}$ uplink cells

the UE expects to have respectively received

\- at most ${16 \bullet N}_{cells,r15}^{cap - r16}$ PDCCHs for DCI
formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a MCS-C-RNTI,
or a G-RNTI for multicast, or a G-CS-RNTI scheduling
${16 \bullet N}_{cells,r15}^{cap - r16}$ PDSCH receptions for which the
UE has not received any corresponding PDSCH symbol over all serving
cells that are not provided *monitoringCapabilityConfig* =
*r16monitoringcapability*

\- at most ${16 \bullet N}_{cells,r15}^{cap - r16}$ PDCCHs for DCI
formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a MCS-C-RNTI
scheduling ${16 \bullet N}_{cells,r15}^{cap - r16}$ PUSCH transmissions
for which the UE has not transmitted any corresponding PUSCH symbol over
all serving cells that are not provided *monitoringCapabilityConfig* =
*r16monitoringcapability*

\- at most ${16 \bullet N}_{cells,r16}^{cap - r16}$ PDCCHs for DCI
formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a MCS-C-RNTI,
or a G-RNTI for multicast, or a G-CS-RNTI scheduling
${16 \bullet N}_{cells,r16}^{cap - r16}$ PDSCH receptions for which the
UE has not received any corresponding PDSCH symbol over all serving
cells that are provided *monitoringCapabilityConfig* =
*r16monitoringcapability*

\- at most ${16 \bullet N}_{cells,r16}^{cap - r16}$ PDCCHs for DCI
formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a MCS-C-RNTI
scheduling ${16 \bullet N}_{cells,r16}^{cap - r16}$ PUSCH transmissions
for which the UE has not transmitted any corresponding PUSCH symbol over
all serving cells that are provided *monitoringCapabilityConfig* =
*r16monitoringcapability*

If a UE is provided serving cells with SCS configuration
$\mu \in \left\{ 5,\ 6 \right\}$ for the active DL BWP, is not
configured for NR-DC operation and indicates through
*pdcch-MonitoringCA* a capability to monitor PDCCH candidates for
$N_{cells}^{cap - r17} \geq 4$ downlink cells and the UE is configured
with $N_{cells}^{DL} > 4$ downlink cells or $N_{cells}^{UL} > 4$ uplink
cells, the UE expects to have respectively received at most
${16 \bullet N}_{cells}^{cap - r17}$ PDCCHs for

\- DCI formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a
MCS-C-RNTI, or a G-RNTI for multicast, or a G-CS-RNTI scheduling
${16 \bullet N}_{cells}^{cap - r17}$ PDSCH receptions for which the UE
has not received any corresponding PDSCH symbol over all
$N_{cells}^{DL}$ downlink cells

\- DCI formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a
MCS-C-RNTI scheduling ${16 \bullet N}_{cells}^{cap - r17}$ PUSCH
transmissions for which the UE has not transmitted any corresponding
PUSCH symbol over all $N_{cells}^{UL}$ uplink cells.

If a UE is provided *monitoringCapabilityConfig* =
*r17monitoringcapability* for at least one serving cell, is provided
*monitoringCapabilityConfig* = *r15monitoringcapability* for at least
one serving cell, is not provided *monitoringCapabilityConfig* =
*r16monitoringcapability* for any serving cell, is not configured for
NR-DC operation, indicates a capability to monitor PDCCH candidates for
$N_{cells,r15/r17}^{cap - r17} \geq 1$ downlink cells and
$N_{cells,r17/r15}^{cap - r17} \geq 1$ downlink cells, and UE is
configured with $N_{cells}^{DL} > 1$ downlink cell or
$N_{cells}^{UL} > 1$ uplink cells, the UE expects to have respectively
received

\- at most ${16 \bullet N}_{cells,r15/r17}^{cap - r17}$ PDCCHs for DCI
formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a MCS-C-RNTI,
or a G-RNTI for multicast, or a G-CS-RNTI scheduling
${16 \bullet N}_{cells,r15/r17}^{cap - r17}$ PDSCH receptions for which
the UE has not received any corresponding PDSCH symbol over all serving
cells that are provided *monitoringCapabilityConfig* =
*r15monitoringcapability*

\- at most ${16 \bullet N}_{cells,r15/r17}^{cap - r17}$ PDCCHs for DCI
formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a MCS-C-RNTI
scheduling ${16 \bullet N}_{cells,r15/r17}^{cap - r17}$ PUSCH
transmissions for which the UE has not transmitted any corresponding
PUSCH symbol over all serving cells that are provided
*monitoringCapabilityConfig* = *r15monitoringcapability*

\- at most ${16 \bullet N}_{cells,r17/r15}^{cap - r17}$ PDCCHs for DCI
formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a MCS-C-RNTI,
or a G-RNTI for multicast, or a G-CS-RNTI scheduling
${16 \bullet N}_{cells,r17/r15}^{cap - r17}$ PDSCH receptions for which
the UE has not received any corresponding PDSCH symbol over all serving
cells with *monitoringCapabilityConfig* = *r17monitoringcapability*

\- at most ${16 \bullet N}_{cells,r17/r15}^{cap - r17}$ PDCCHs for DCI
formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a MCS-C-RNTI
scheduling ${16 \bullet N}_{cells,r17/r15}^{cap - r17}$ PUSCH
transmissions for which the UE has not transmitted any corresponding
PUSCH symbol over all serving cells with *monitoringCapabilityConfig* =
*r17monitoringcapability*

If a UE is provided *monitoringCapabilityConfig* =
*r17monitoringcapability* for at least one serving cell, is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* for at least
one serving cell, is not provided *monitoringCapabilityConfig* =
*r15monitoringcapability* for any serving cell, is not configured for
NR-DC operation, indicates a capability to monitor PDCCH candidates for
$N_{cells,r16/r17}^{cap - r17} \geq 1$ downlink cells and
$N_{cells,r17/r16}^{cap - r17} \geq 1$ downlink cells, and the UE is
configured with $N_{cells}^{DL} > 1$ downlink cells or
$N_{cells}^{UL} > 1$ uplink cells

the UE expects to have respectively received

\- at most ${16 \bullet N}_{cells,r16/r17}^{cap - r17}$ PDCCHs for DCI
formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a MCS-C-RNTI,
or a G-RNTI for multicast, or a G-CS-RNTI scheduling
${16 \bullet N}_{cells,r16/r17}^{cap - r17}$ PDSCH receptions for which
the UE has not received any corresponding PDSCH symbol over all serving
cells that are provided *monitoringCapabilityConfig* =
*r16monitoringcapability*

\- at most ${16 \bullet N}_{cells,r16/r17}^{cap - r17}$ PDCCHs for DCI
formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a MCS-C-RNTI
scheduling ${16 \bullet N}_{cells,r16/r17}^{cap - r17}$ PUSCH
transmissions for which the UE has not transmitted any corresponding
PUSCH symbol over all serving cells that are provided
*monitoringCapabilityConfig* = *r16monitoringcapability*

\- at most ${16 \bullet N}_{cells,r17/r16}^{cap - r17}$ PDCCHs for DCI
formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a MCS-C-RNTI,
or a G-RNTI for multicast, or a G-CS-RNTI scheduling
${16 \bullet N}_{cells,r17/r16}^{cap - r17}$ PDSCH receptions for which
the UE has not received any corresponding PDSCH symbol over all serving
cells with *monitoringCapabilityConfig* = *r17monitoringcapability*

\- at most ${16 \bullet N}_{cells,r17/r16}^{cap - r17}$ PDCCHs for DCI
formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a MCS-C-RNTI
scheduling ${16 \bullet N}_{cells,r17/r16}^{cap - r17}$ PUSCH
transmissions for which the UE has not transmitted any corresponding
PUSCH symbol over all serving cells with *monitoringCapabilityConfig* =
*r17monitoringcapability*

If a UE is provided *monitoringCapabilityConfig* =
*r17monitoringcapability* for at least one serving cell, is provided
*monitoringCapabilityConfig* = *r16monitoringcapability* for at least
one serving cell, and *monitoringCapabilityConfig* =
*r15monitoringcapability* for at least one serving cell, is not
configured for NR-DC operation, indicates a capability to monitor PDCCH
candidates for $N_{cells,r15/\{ r16,r17\}}^{cap - r17} \geq 1$ downlink
cells, $N_{cells,r16/\{ r15,r17\}}^{cap - r17} \geq 1$, and
$N_{cells,r17/\{ r15,r16\}}^{cap - r17} \geq 1$ downlink cells, and is
configured with $N_{cells}^{DL} > 1$ downlink cells or
$N_{cells}^{UL} > 1$ uplink cells

the UE expects to have respectively received

\- at most ${16 \bullet N}_{cells,r15/\{ r16,r17\}}^{cap - r17}$ PDCCHs
for DCI formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a
MCS-C-RNTI, or a G-RNTI for multicast, or a G-CS-RNTI scheduling
${16 \bullet N}_{cells,r15/\{ r16,r17\}}^{cap - r17}$ PDSCH receptions
for which the UE has not received any corresponding PDSCH symbol over
all serving cells that are provided *monitoringCapabilityConfig* =
*r15monitoringcapability*

\- at most ${16 \bullet N}_{cells,r15/\{ r16,r17\}}^{cap - r17}$ PDCCHs
for DCI formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a
MCS-C-RNTI scheduling
${16 \bullet N}_{cells,r15/\{ r16,r17\}}^{cap - r17}$ PUSCH
transmissions for which the UE has not transmitted any corresponding
PUSCH symbol over all serving cells that are provided
*monitoringCapabilityConfig* = *r15monitoringcapability*

\- at most ${16 \bullet N}_{cells,r16/\{ r15,r17\}}^{cap - r17}$ PDCCHs
for DCI formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a
MCS-C-RNTI, or a G-RNTI for multicast, or a G-CS-RNTI scheduling
${16 \bullet N}_{cells,r16/\{ r15,r17\}}^{cap - r17}$ PDSCH receptions
for which the UE has not received any corresponding PDSCH symbol over
all serving cells that are provided *monitoringCapabilityConfig* =
*r16monitoringcapability*

\- at most ${16 \bullet N}_{cells,r16/\{ r15,r17\}}^{cap - r17}$ PDCCHs
for DCI formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a
MCS-C-RNTI scheduling
${16 \bullet N}_{cells,r16/\{ r15,r17\}}^{cap - r17}$ PUSCH
transmissions for which the UE has not transmitted any corresponding
PUSCH symbol over all serving cells that are provided
*monitoringCapabilityConfig* = *r16monitoringcapability*

\- at most ${16 \bullet N}_{cells,r17/\{ r16,r17\}}^{cap - r17}$ PDCCHs
for DCI formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a
MCS-C-RNTI, or a G-RNTI for multicast, or a G-CS-RNTI scheduling
${16 \bullet N}_{cells,r17/\{ r16,r17\}}^{cap - r17}$ PDSCH receptions
for which the UE has not received any corresponding PDSCH symbol over
all serving cells with *monitoringCapabilityConfig* =
*r17monitoringcapability*

\- at most ${16 \bullet N}_{cells,r17/\{ r16,r17\}}^{cap - r17}$ PDCCHs
for DCI formats with CRC scrambled by a C-RNTI, or a CS-RNTI, or a
MCS-C-RNTI scheduling
${16 \bullet N}_{cells,r17/\{ r16,r17\}}^{cap - r17}$ PUSCH
transmissions for which the UE has not transmitted any corresponding
PUSCH symbol over all serving cells with *monitoringCapabilityConfig* =
*r17monitoringcapability*

If a UE

\- is configured to monitor a first PDCCH candidate for a DCI format 0_0
and a DCI format 1_0 from a CSS set and a second PDCCH candidate for a
DCI format 0_0 and a DCI format 1_0 from a USS set, where the CSS set
and the USS set do not include *searchSpaceLinkingId*, in a CORESET with
index zero on an active DL BWP, and

\- the DCI formats 0_0/1_0 associated with the first PDCCH candidate and
the DCI formats 0_0/1_0 associated with the second PDCCH candidate have
same size, and

\- the UE receives the first PDCCH candidate and the second PDCCH
candidate over a same set of CCEs, and

\- the first PDCCH candidate and the second PDCCH candidate have
identical scrambling, and

\- the DCI formats 0_0/1_0 for the first PDCCH candidate and the DCI
formats 0_0/1_0 for the second PDCCH candidate have CRC scrambled by
either C-RNTI, or MCS-C-RNTI, or CS-RNTI

the UE decodes only the DCI formats 0_0/1_0 associated with the first
PDCCH candidate.

If a UE detects a DCI format with inconsistent information, the UE
discards all the information in the DCI format.

A UE configured with a bandwidth part indicator in a DCI format
determines, in case of an active DL BWP or of an active UL BWP change,
that the information in the DCI format is applicable to the new active
DL BWP or UL BWP, respectively, as described in clause 12.

For unpaired spectrum operation, if a UE is not configured for
PUSCH/PUCCH transmission on serving cell $c_{2}$, the UE does not expect
to monitor PDCCH on serving cell $c_{1}$ if the PDCCH overlaps in time
with SRS transmission (including any interruption due to uplink or
downlink RF retuning time \[10, TS 38.133\]) on serving cell $c_{2}$ and
if the UE is not capable of simultaneous reception and transmission on
serving cell $c_{1}$and serving cell $c_{2}$.

If a UE is provided *resourceBlocks* and s*ymbolsInResourceBlock* in
*RateMatchPattern*, or if the UE is additionally provided
*periodicityAndPattern* in *RateMatchPattern*, the UE can determine a
set of RBs in symbols of a slot that are not available for PDSCH
reception scheduled by a DCI format as described in \[6, TS 38.214\]. If
a PDCCH candidate that provides a DCI format is mapped to one or more
REs that overlap with REs of any RB in the set of RBs in symbols of the
slot, the UE does not expect to monitor the PDCCH candidate.

A UE does not expect to be configured with *dci-FormatsSL* and
*dci-FormatsExt* in a same USS.