## 17.1 First procedures for RedCap UE

In this clause, the term \'UE\' refers to a RedCap UE that indicates
*supportOfRedCap* or *supportOfERedCap*.

A UE expects the initial DL BWP and the active DL BWP after the UE
(re)establishes dedicated RRC connection to be smaller than or equal to
the maximum DL bandwidth that the UE supports. A UE can be provided a DL
BWP by *initialDownlinkBWP-RedCap*, and an UL BWP by
*initialUplinkBWP-RedCap*. If *initialUplinkBWP* indicates an UL BWP
that is larger than a maximum UL BWP that a UE supports, the UE expects
to be provided an UL BWP by *initialUplinkBWP-RedCap* that is smaller
than or equal to the maximum UL bandwidth that the UE supports.

If a UE is provided *controlResourceSetZero* and *searchSpaceZero* in
*PDCCH-ConfigSIB1* or *PDCCH-ConfigCommon*, the UE determines a CORESET
for a search space set from *controlResourcesetZero* as described in
clause 13 and for Tables 13-1 through 13-10, and determines
corresponding PDCCH monitoring occasions as described in clause 13 and
for Tables 13-11 through 13-15. If the active DL BWP is not the initial
DL BWP, the UE determines PDCCH monitoring occasions for the search
space set if the CORESET bandwidth is within the active DL BWP and the
active DL BWP has same SCS configuration and same cyclic prefix

\- as the DL BWP by *initialDownlinkBWP-RedCap* if provided, and

\- as the DL BWP provided by *initialDownlinkBWP* if provided or as
those for the PDCCH reception in the CORESET for Type0-PDCCH CSS set if
*initialDownlinkBWP* is not provided.

For unpaired spectrum operation, a RedCap UE does not expect to receive
a configuration where the center frequency for an initial DL BWP in
which the UE is configured to monitor Type1-PDCCH CSS set, or a CSS set
provided by *sdt-SearchSpace* for PUSCH transmission in RRC_INACTIVE
state as described in clause 19.1 or clause 19.2, is different than the
center frequency for an initial UL BWP in which the RedCap UE may
transmit Msg1/Msg3 or MsgA.

A UE can be provided by *BWP-DownlinkDedicated* a DL BWP, other than the
initial DL BWP. A UE can be provided by *BWP-UplinkDedicated* an UL BWP,
other than the initial UL BWP, that is smaller than or equal to the
maximum UL bandwidth that the UE supports.

If a UE is provided an UL BWP by *initialUplinkBWP-RedCap* and is
provided *rach-ConfigCommon* or *msgA-ConfigCommon* in
*BWP-UplinkCommon* for the UL BWP, the UE uses corresponding parameters
to perform the procedures in clauses 8.1, 8.1A, and 8.3; otherwise, the
UE uses corresponding parameters from *rach-ConfigCommon* or
*msgA-ConfigCommon* in *BWP-UplinkCommon* for the UL BWP provided by
*initialUplinkBWP*.

If a UE is provided *initialUplinkBWP-RedCap* and does not have
dedicated PUCCH resource configuration, the UE transmits PUCCH with
HARQ-ACK information as described in clause 9.2.1 using a PUCCH resource
set provided by *pucch-ResourceCommonRedCap*, except that frequency
hopping for the PUCCH transmission is disabled if *intra-SlotFH* is
present in *PUCCH-ConfigCommon*. If frequency hopping of the PUCCH
transmission is disabled then, for the PUCCH transmission, the UE
determines the initial cyclic shift index in the set of initial cyclic
shift indexes as $r_{\text{PUCCH}}\text{mod}N_{CS}$ and determines the
PRB index as

\-
${RB}_{\text{BWP}}^{\text{offset}} + {RB}_{\text{BWP}}^{\text{offset-add}} + \left\lfloor \frac{r_{\text{PUCCH}}}{N_{CS}} \right\rfloor$,
if *intra-SlotFH* = \'*fromLowerEdge*\'

\-
${N_{\text{BWP}}^{\text{size}} - RB}_{\text{BWP}}^{\text{offset}} - {RB}_{\text{BWP}}^{\text{offset-add}} - 1 - \left\lfloor \frac{r_{\text{PUCCH}}}{N_{CS}} \right\rfloor$,
otherwise

where ${RB}_{\text{BWP}}^{\text{offset-add}}$ is provided by
*additionalPRBOffset*, if provided; otherwise,
${RB}_{\text{BWP}}^{\text{offset-add}} = 0.$

If a UE is not provided *initialUplinkBWP-RedCap* and does not have
dedicated PUCCH resource configuration, the UE transmits PUCCH with
HARQ-ACK information as described in clause 9.2.1 using a PUCCH resource
set provided by *pucch-ResourceCommonRedCap* if
*pucch-ResourceCommonRedCap* is present or by *pucch-ResourceCommon* if
*pucch-ResourceCommonRedCap* is absent. For an initial DL BWP provided
by *initialDownlinkBWP-RedCap*, if a UE in RRC_IDLE state or in
RRC_INACTIVE state monitors PDCCH according to Type1-PDCCH CSS set and
does not monitor PDCCH according to Type2-PDCCH CSS set, the UE does not
expect the initial DL BWP to include SS/PBCH blocks and the CORESET with
index 0.

For an active DL BWP not provided by *BWP-DownlinkDedicated*, if a UE
does not indicate a capability to operate in the active DL BWP without
receiving an SS/PBCH block, the UE in RRC_CONNECTED state assumes that
the active DL BWP includes the SS/PBCH blocks that the UE used to obtain
SIB1 and, for SS/PBCH block and CORESET multiplexing pattern 1, the
CORESET with index 0.

For an active DL BWP provided by *BWP-DownlinkDedicated*, unless a UE
indicates a capability to operate in the active DL BWP without receiving
an SS/PBCH block, the UE in RRC_CONNECTED state assumes that the active
DL BWP includes the SS/PBCH blocks that the UE used to obtain SIB1 or
the SS/PBCH blocks provided by *NonCellDefiningSSB*. If the active DL
BWP includes the SS/PBCH blocks that the UE used to obtain SIB1, for
SS/PBCH block and CORESET multiplexing pattern 1, the UE expects the
active DL BWP to include the CORESET with index 0.

For a RedCap UE indicating a capability to use an initial DL BWP that
includes the SS/PBCH blocks provided by *NonCellDefiningSSB* for PUSCH
transmission in RRC_INACTIVE state, if the UE is provided
*NonCellDefiningSSB* in *ncd-SSB-RedCapInitialBWP-SDT*, then during
procedure of PUSCH transmission in RRC_INACTIVE state (as described in
clause 19) the UE uses the SS/PBCH blocks provided by
*NonCellDefiningSSB* for the purposes for which the UE would otherwise
have used the SS/PBCH blocks that the UE used to obtain SIB1.

If the active DL BWP provided by *BWP-DownlinkDedicated*, or the initial
DL BWP during procedure of PUSCH transmission in RRC_INACTIVE state (as
described in clause 19), includes the SS/PBCH blocks provided by
*NonCellDefiningSSB*, these SS/PBCH blocks and the SS/PBCH blocks that
the UE used to obtain SIB1 have the same QCL properties, if they have
the same index*.*

For a RedCap UE indicated presence of SS/PBCH blocks within an active DL
BWP by *NonCellDefiningSSB*, collision handling between downlink
receptions or uplink transmissions and the SS/PBCH blocks are same as
described for a UE indicated presence of SS/PBCH blocks by
*ssb-PositionsInBurst* in *SIB1* or in *ServingCellConfigCommon*
described in all other clauses, unless otherwise stated.

For monitoring of a PDCCH candidate by a UE configured with
*NonCellDefiningSSB*, if the UE

\- does not monitor PDCCH candidates in a Type0-PDCCH CSS set, and

\- at least one RE for a PDCCH candidate overlaps with at least one RE
of a candidate SS/PBCH block corresponding to a SS/PBCH block index
provided by *NonCellDefiningSSB*,

the UE is not required to monitor the PDCCH candidate.

The SS/PBCH blocks in clause 8.1 for determining valid PRACH occasions
in unpaired spectrum correspond to the SS/PBCH blocks that the UE used
to obtain SIB1.

The SS/PBCH blocks in clause 8.1A for determining valid PUSCH occasions
in unpaired spectrum correspond to the SS/PBCH blocks that the UE used
to obtain SIB1.

The SS/PBCH blocks in clause 6.1.2.1 in \[6, TS 38.214\] and clause 8.3
for determining the $N_{\text{PUSCH}}^{\text{repeat}}$ slots for a PUSCH
transmission in unpaired spectrum correspond to the SS/PBCH blocks that
the UE used to obtain SIB1.

The SS/PBCH blocks in clause 19.1 for determining valid PUSCH occasions
in unpaired spectrum correspond to the SS/PBCH blocks that the UE used
to obtain SIB1.