## 5.1 UE procedure for receiving the physical downlink shared channel

For downlink, a maximum of 16 HARQ processes per cell are supported by
the UE, or subject to UE capability, a maximum of 32 HARQ processes per
cell as defined in \[13, TS 38.306\]. The number of processes the UE may
assume will at most be used for the downlink is configured to the UE for
each cell separately by higher layer parameter
*nrofHARQ-ProcessesForPDSCH* or *nrofHARQ-ProcessesForPDSCH-v1700*, and
when no configuration is provided the UE may assume a default number of
8 processes.

A UE shall upon detection of a PDCCH with a configured DCI format 1_0,
1_1, 1_2, 1_3, 4_0, 4_1, or 4_2 decode the corresponding PDSCHs as
indicated by that DCI. When the UE is scheduled with multiple PDSCHs on
a serving cell by a DCI, HARQ process ID indicated by this DCI applies
to the first PDSCH not overlapping with a UL symbol indicated by
*tdd-UL-DL-ConfigurationCommon* or *tdd-UL-DL-ConfigurationDedicated* if
provided, HARQ process ID is then incremented by 1 for each subsequent
PDSCH(s) in the scheduled order, with modulo operation of
*nrofHARQ-ProcessesForPDSCH* applied if *nrofHARQ-ProcessesForPDSCH* is
provided, or with modulo operation of *nrofHARQ-ProcessesForPDSCH-v1700*
applied if or *nrofHARQ-ProcessesForPDSCH-v1700* is provided, or with
modulo operation of 8 applied, otherwise. HARQ process ID is not
incremented for PDSCH(s) not received if at least one of the symbols
indicated by the indexed row of the used resource allocation table in
the slot overlaps with a UL symbol indicated by
*tdd-UL-DL-ConfigurationCommon* or *tdd-UL-DL-ConfigurationDedicated* if
provided. When a UE is configured by the higher layer parameter
*repetitionScheme* set to \'tdmSchemeA\', the PDSCH includes two PDSCH
transmission occasions. For each PDSCH, if either PDSCH occasion
overlaps with a UL symbol indicated by *tdd-UL-DL-ConfigurationCommon*
or *tdd-UL-DL-ConfigurationDedicated* if provided, the PDSCH is not
received and HARQ process ID is not increment for the PDSCH. For any
HARQ process ID(s) in a given scheduled cell, the UE is not expected to
receive a PDSCH that overlaps in time with another PDSCH if the UE is
not capable of receiving FDMed unicast and multicast PDSCH per slot per
carrier. When HARQ feedback for the HARQ process ID is not disabled, or
for the HARQ process associated with the first SPS PDSCH when
*HARQ-feedbackEnablingforSPSactive* is provided and enabled, the UE is
not expected to receive another PDSCH for a given HARQ process until
after the end of the expected transmission of HARQ-ACK for that HARQ
process, where the timing is given by Clause 9.2.3 of \[6, TS 38.213\].
For HARQ-ACK subject to HARQ-ACK deferral described in Clause 9.2.5.4 of
\[6 TS 38.213\], the expected transmission of HARQ-ACK corresponds to
the expected transmission HARQ-ACK in a first slot. When HARQ feedback
for the HARQ process ID is disabled, the UE is not expected to receive
another PDCCH carrying a DCI scheduling a PDSCH or set of
slot-aggregated PDSCH scheduled for the given HARQ process or to receive
another PDSCH without corresponding PDCCH for the given HARQ process
that starts until T~proc,1~ after the end of the reception of the last
PDSCH or slot-aggregated PDSCH for that HARQ process. Except for the
case when a UE is configured by higher layer parameter *PDCCH-Config*
that contains two different values of *coresetPoolIndex* in
*ControlResourceSet* and PDCCHs that schedule two PDSCHs are associated
to different *ControlResourceSets* having different values of
*coresetPoolIndex* and the UE reports its capability of
*outOfOrderOperationDL-r16,* in a given scheduled cell, the UE is not
expected to receive a first PDSCH and a second PDSCH, starting later
than the first PDSCH, with its corresponding HARQ-ACK assigned to be
transmitted on a resource ending before the start of a different
resource for the HARQ-ACK assigned to be transmitted for the first
PDSCH, where the two resources are in different slots for the associated
HARQ-ACK transmissions, each slot is composed of
![](media/image10.wmf)symbols \[4\] or a number of symbols indicated by
*subslotLengthForPUCCH* if provided, and the HARQ-ACK for the two PDSCHs
are associated with the HARQ-ACK codebook of the same priority. Except
for the case when a UE is configured by higher layer parameter
*PDCCH-Config* that contains two different values of *coresetPoolIndex*
in *ControlResourceSet* and PDCCHs that schedule two PDSCHs are
associated to different *ControlResourceSets* having different values of
*coresetPoolIndex* and the UE reports its capability of
*outOfOrderOperationDL-r16,* in a given scheduled cell, the UE is not
expected to receive a first PDSCH and a second PDSCH, starting later
than the first PDSCH, with its corresponding HARQ-ACK assigned to be
transmitted on a resource ending before the start of a different
resource for the HARQ-ACK assigned to be transmitted for the first PDSCH
if the HARQ-ACK for the two PDSCHs are associated with HARQ-ACK
codebooks of different priorities. For any two HARQ process IDs in a
given scheduled cell, if the UE is scheduled to start receiving a first
PDSCH starting in symbol *j* by a PDCCH ending in symbol *i* on a
scheduling cell, the UE is not expected to be scheduled to receive a
PDSCH starting earlier than the end of the first PDSCH with a PDCCH that
ends later than symbol *i* of a scheduling cell,. When the PDCCH
reception includes two PDCCH candidates from two respective search space
sets, as described in clause 10.1 of \[6, TS 38.213\], the PDCCH ending
in symbol *i* is determined based on the PDCCH candidate that ends later
in time. In a given scheduled cell, for any PDSCH corresponding to
SI-RNTI, the UE is not expected to decode a re-transmission of an
earlier PDSCH with a starting symbol less than *N* symbols after the
last symbol of that PDSCH, where the value of *N* depends on the PDSCH
subcarrier spacing configuration *μ,* with *N*=13 for *μ*=0, *N*=13 for
*μ*=1, *N*=20 for *μ*=2, *N*=24 for *μ*=3, *N*=96 for *μ*=5, and *N*=192
for *μ*=6.

When receiving PDSCH scheduled with SI-RNTI, P-RNTI, MCCH-RNTI, G-RNTI
for broadcast, or Multicast MCCH-RNTI, G-RNTI for multicast in
RRC_INACTIVE state, the UE may assume that the DM-RS port of PDSCH is
quasi co-located with the associated SS/PBCH block with respect to
Doppler shift, Doppler spread, average delay, delay spread, spatial RX
parameters when applicable.

When receiving PDSCH scheduled with RA-RNTI, or MSGB-RNTI, the UE may
assume that the DM-RS port of PDSCH is quasi co-located with the SS/PBCH
block or the CSI-RS resource the UE used for RACH association as
applicable, and transmission with respect to Doppler shift, Doppler
spread, average delay, delay spread, spatial RX parameters when
applicable. When receiving a PDSCH scheduled with RA-RNTI in response to
a random access procedure triggered by a PDCCH order which triggers
contention-free random access procedure for the SpCell \[10, TS
38.321\], the UE may assume that the DM-RS port of the received PDCCH
order and the DM-RS ports of the corresponding PDSCH scheduled with
RA-RNTI are quasi co-located with the same SS/PBCH block or CSI-RS with
respect to Doppler shift, Doppler spread, average delay, delay spread,
spatial RX parameters when applicable. If a UE is configured with
*SSB-MTC-AddtionalPCI* and with *PDCCH-Config* that contains two
different values of *coresetPoolIndex* in *ControlResourceSet*, and if
the UE is configured with *tag2-Id* for the SpCell, if the UE attempts
to detect the DCI format 1_0 with CRC scrambled by the corresponding
RA-RNTI or when receiving a PDSCH scheduled with RA-RNTI in response to
a random access procedure triggered by a PDCCH order which triggers
contention-free random access procedure for the SpCell \[10, TS
38.321\], and if the CORESET used for the PDCCH order transmission is
not associated with the serving cell physical cell ID, the UE may assume
that the DM-RS ports of the received PDSCH are quasi co-located with the
DM-RS antenna port associated with PDCCH receptions in the CORESET for
Type1-PDCCH CSS set with respect to Doppler shift, Doppler spread,
average delay, delay spread, and spatial RX parameters when applicable.

When receiving PDSCH in response to a PUSCH transmission scheduled by a
RAR UL grant or corresponding PUSCH retransmission, or when receiving
PDSCH in response to a PUSCH for Type-2 random access procedure, or a
PUSCH scheduled by a fallbackRAR UL grant or corresponding PUSCH
retransmission, the UE may assume that the DM-RS port of PDSCH is quasi
co-located with the SS/PBCH block the UE selected for RACH association
and transmission with respect to Doppler shift, Doppler spread, average
delay, delay spread, spatial RX parameters when applicable.

If the UE is not configured for PUSCH/PUCCH transmission for at least
one serving cell configured with slot formats comprised of DL and UL
symbols, and if the UE is not capable of simultaneous reception and
transmission on serving cell *c~1~* and serving cell *c~2~*, the UE is
not expected to receive PDSCH on serving cell *c~1~* if the PDSCH
overlaps in time with SRS transmission (including any interruption due
to uplink or downlink RF retuning time \[10, TS 38.321\]) on serving
cell *c~2~* not configured for PUSCH/PUCCH transmission.

The UE is not expected to decode a PDSCH in a serving cell scheduled by
a PDCCH with C-RNTI, CS-RNTI, MCS-C-RNTI, G-RNTI, G-CS-RNTI or MCCH-RNTI
and one or multiple PDSCH(s) required to be received according to this
Clause in the same serving cell without a corresponding PDCCH
transmission if the PDSCHs partially or fully overlap in time except if
the PDCCH scheduling the PDSCH ends at least
14$\bullet 2^{max(0,\mu - 3)}$ symbols before the earliest starting
symbol of the PDSCH(s) without the corresponding PDCCH transmission,
where* μ* and the symbol duration are based on the smallest numerology
between the scheduling PDCCH and the PDSCH, in which case the UE shall
decode the PDSCH scheduled by the PDCCH. When the PDCCH reception
incudes two PDCCH candidates from two respective search space sets, as
described in clause 10 of \[6, TS 38.213\], for the purpose of
determining the PDCCH with C-RNTI, CS-RNTI or MCS-C-RNTI scheduling the
PDSCH ends at least 14$\bullet 2^{max(0,\mu - 3)}$ symbols before the
earliest starting symbol of the PDSCH(s) without the corresponding PDCCH
transmission, the PDCCH candidate that ends later in time is used.

The UE is not expected to decode a PDSCH scheduled with C-RNTI,
MCS-C-RNTI, G-RNTI for multicast or broadcast, MCCH-RNTI, Multicast
MCCH-RNTI, G-CS-RNTI or CS-RNTI if another PDSCH in the same cell
scheduled with RA-RNTI or MSGB-RNTI partially or fully overlap in time.

If cell DTX is activated for the serving cell, the UE is not expected to
decode a PDSCH scheduled without corresponding PDCCH transmission using
SPS-Config that overlap in time with any non-active periods of cell DTX
for the serving cell.

Furthermore, a UE indicating *supportOfERedCap* capability but not
indicating *eRedCapNotReducedBB-BW* is not expected to decode a PDSCH
scheduled with C-RNTI, MCS-C-RNTI, G-RNTI for multicast or broadcast,
MCCH-RNTI, Multicast MCCH-RNTI, G-CS-RNTI or CS-RNTI in the same or next
slot if another PDSCH in the same cell is scheduled with RA-RNTI or
MSGB-RNTI, when the PDSCH scheduled with RA-RNTI or MSGB-RNTI is
allocated more than 25 PRBs when configured with SCS μ = 0 or more than
12 PRBs when configured with SCS μ = 1.

The UE in RRC_IDLE and RRC_INACTIVE modes shall be able to decode two
PDSCHs each scheduled with SI-RNTI, P-RNTI, RA-RNTI or TC-RNTI, where
the PDSCH scheduled with TC-RNTI for a reduced capability UE that
indicates *supportOfERedCap* is allocated no more than 25 PRBs when
configured with SCS μ = 0 or no more than 12 PRBs when configured with
SCS μ = 1, with the two PDSCHs partially or fully overlapping in time in
non-overlapping PRBs.

The UE:

\- is expected to decode PDSCH scheduled with MCCH-RNTI or Multicast
MCCH-RNTI, and PBCH in PCell that partially or fully overlaps in time in
non-overlapping PRBs in PCell.

\- is not expected to decode PDSCH scheduled with G-RNTI for broadcast
and PBCH in PCell that partially or fully overlaps in time in
non-overlapping PRBs in PCell.

\- is not expected to decode PDSCH scheduled with G-RNTI for multicast
and PBCH in PCell that partially or fully overlaps in time in
non-overlapping PRBs in PCell.

On a frequency range 1 cell, the UE shall be able to decode a PDSCH
scheduled with C-RNTI, MCS-C-RNTI, or CS-RNTI and, during a process of
P-RNTI triggered SI acquisition, another PDSCH scheduled with SI-RNTI
that partially or fully overlap in time in non-overlapping PRBs, unless
the PDSCH scheduled with C-RNTI, MCS-C-RNTI, or CS-RNTI requires
Capability 2 processing time according to clause 5.3 in which case the
UE may skip decoding of the scheduled PDSCH with C-RNTI, MCS-C-RNTI, or
CS-RNTI.

On a frequency range 2 cell, the UE is not expected to decode a PDSCH
scheduled with C-RNTI, MCS-C-RNTI, or CS-RNTI if in the same cell,
during a process of P-RNTI triggered SI acquisition, another PDSCH
scheduled with SI-RNTI partially or fully overlap in time.

A UE that indicates *supportOfERedCap* capability but does not indicate
*eRedCapNotReducedBB-BW*, during a process of P-RNTI triggered SI
acquisition, when the total number of PRBs for the PDSCH scheduled with
SI-RNTI and the PDSCH scheduled with C-RNTI, MCS-C-RNTI, or CS-RNTI
scheduled in the slot is larger than 25 PRBs if configured with SCS µ =
0 or larger than 12 PRBs if configured with SCS µ = 1, the UE may skip
decoding of the scheduled PDSCH with C-RNTI, MCS-C-RNTI, or CS-RNTI.

The UE is expected to decode a PDSCH scheduled with C-RNTI, MCS-C-RNTI,
or CS-RNTI during a process of autonomous SI acquisition.

In RRC_CONNECTED state, the maximum number of PDSCHs scheduled per slot
per component carrier with C-RNTI/CS-RNTI and G-RNTI/G-CS-RNTI/MCCH-RNTI
that the UE shall be able to decode is the same as the indicated UE
capability for the number of unicast PDSCHs per slot per component
carrier. In RRC_INACTIVE state, if the UE is capable of receiving TDMed
unicast and multicast per slot per component carrier, the UE shall be
able to decode one PDSCH scheduled with C-RNTI and one PDSCH scheduled
with G-RNTI/Multicast MCCH-RNTI per slot per component carrier. If the
UE is capable of receiving FDMed unicast and multicast PDSCH per slot
per carrier, the UE shall be able to decode a PDSCH scheduled by a DCI
format with C-RNTI or a PDSCH scheduled for a retransmission of a TB by
a DCI format with CS-RNTI and a PDSCH scheduled by a DCI format with
G-RNTI for multicast or a PDSCH scheduled for a retransmission of a TB
by a DCI format with G-CS-RNTI that partially or fully overlap in time
in non-overlapping PRBs. If the UE is capable of receiving FDMed unicast
and broadcast PDSCH per slot per carrier, the UE shall be able to decode
a PDSCH scheduled by a DCI format with C-RNTI or a PDSCH scheduled for a
retransmission of a TB by a DCI format with CS-RNTI and a PDSCH
scheduled with G-RNTI for broadcast/MCCH-RNTI that partially or fully
overlap in time in non-overlapping PRBs. For a reduced capability UE
that indicates *supportOfERedCap* but not indicating
*eRedCapNotReducedBB-BW*, if the UE is capable of receiving FDMed
unicast and multicast/broadcast PDSCH per slot, the UE can decode the
two PDSCHs, with the two PDSCHs partially or fully overlapping in time
in non-overlapping PRBs,

\- if the total number of PRBs allocated is no more than 25 PRBs when
configured with SCS μ = 0 or no more than 12 PRBs when configured with
SCS μ = 1,

\- otherwise, the UE may skip decoding one of the two PDSCHs.

If the UE is configured by higher layers to decode a PDCCH with its CRC
scrambled by a CS-RNTI or G-CS-RNTI, the UE shall receive PDSCH
transmissions without corresponding PDCCH transmissions using the
higher-layer-provided PDSCH configuration for those PDSCHs.

The UE is not expected to support reception of:

\- FDMed broadcast MCCH PDSCH and broadcast MTCH PDSCH in PCell or
SCell, or

\- FDMed multiple broadcast MTCH PDSCHs in PCell or SCell, or

\- FDMed broadcast MCCH/broadcast MTCH/multicast PDSCH and SIB PDSCH in
PCell, or

\- FDMed multicast PDSCHs in PCell or SCell, or

\- FDMed multicast PDSCH and MCCH/broadcast MTCH PDSCH in PCell or
SCell, or

\- FDMed broadcast MCCH/broadcast MTCH/multicast PDSCH and paging PDSCH.

The UE in RRC_INACTIVE state is not expected to support reception of:

\- FDMed multicast MCCH PDSCH and multicast MTCH PDSCH in Pcell, or

\- FDMed multiple multicast MTCH PDSCHs in Pcell, or

\- FDMed broadcast MCCH/broadcast MTCH/multicast MCCH/multicast MTCH and
SIB PDSCH in Pcell, or

\- FDMed multicast MCCH/multicast MTCH and broadcast MCCH/broadcast MTCH
in Pcell, or

\- FDMed multicast MCCH/multicast MTCH and paging PDSCH in Pcell.

If a UE is configured by higher layer parameter *PDCCH-Config* that
contains two different values of *coresetPoolIndex* in
*ControlResourceSet*, the UE may expect to receive multiple PDCCHs
scheduling fully/partially/non-overlapped PDSCHs in time and frequency
domain. The UE may expect the reception of full/partially-overlapped
PDSCHs in time, only when PDCCHs that schedule two PDSCHs are associated
to different *ControlResourceSets* having different values of
*coresetPoolIndex*. For a CORESET without *coresetPoolIndex*, the UE may
assume that the CORESET is assigned with *coresetPoolIndex* as 0. When
the UE is configured with *SSB-MTC-AdditionalPCI*, *ControlResourceSets*
corresponding to different *coresetPoolIndex* values may be associated
with different physical cell IDs via activated TCI states of the
*ControlResourceSets*, where *ControlResourceSets* corresponding to one
*coresetPoolIndex* is associated with the serving cell physical cell ID
and *ControlResourceSets* corresponding to another *coresetPoolIndex*
can be associated with another physical cell ID. When the UE is
scheduled with full/partially/non-overlapped PDSCHs in time and
frequency domain, the full scheduling information for receiving a PDSCH
is indicated and carried only by the corresponding PDCCH, the UE is
expected to be scheduled with the same active BWP and the same SCS. When
the UE is scheduled with full/partially-overlapped PDSCHs in time and
frequency domain, the UE can be scheduled with at most two codewords
simultaneously. When PDCCHs that schedule two PDSCHs are associated to
different *ControlResourceSets* having different values of
*coresetPoolIndex* and the UE reports its capability of
*outOfOrderOperationDL-r16,* the following operations are allowed:

\- For any two HARQ process IDs in a given scheduled cell, if the UE is
scheduled to start receiving a first PDSCH starting in symbol *j* by a
PDCCH associated with a value of *coresetPoolIndex* ending in symbol
*i*, the UE can be scheduled to receive a PDSCH starting earlier than
the end of the first PDSCH with a PDCCH associated with a different
value of *coresetPoolIndex* that ends later than symbol *i*.

\- In a given scheduled cell, the UE can receive a first PDSCH in slot
*i*, with the corresponding HARQ-ACK assigned to be transmitted in slot
*j*, and a second PDSCH associated with a value of *coresetPoolIndex*
different from that of the first PDSCH starting later than the first
PDSCH with its corresponding HARQ-ACK assigned to be transmitted in a
slot before slot *j*.

If PDCCHs that schedule corresponding PDSCHs are associated to the same
or different *ControlResourceSets* having the same value of
*coresetPoolIndex*, the UE procedure for receiving the PDSCH upon
detection of a PDCCH follows Clause 5.1.

A UE does not expect to be configured with *repetitionScheme* if the UE
is configured with higher layer parameter *repetitionNumber* for the
same PDSCH.

When a UE is configured by higher layer parameter *repetitionScheme* set
to one of \'fdmSchemeA*\'*, \'fdmSchemeB*\'*, \'tdmSchemeA*\'*, if the
UE not configured with *dl-OrJointTCI-StateList* is indicated with two
TCI states in a codepoint of the DCI field *\'Transmission Configuration
Indication\'* or if the UE configured with *dl-OrJointTCI-StateList* is
having two indicated TCI States to be applied to PDSCH and the UE is
indicated with DM-RS port(s) within one CDM group in the DCI field
\'*Antenna Port(s)\'*.

\- When the UE is set to \'fdmSchemeA*\',* the UE shall receive a single
PDSCH transmission occasion of the TB with each TCI state associated to
a non-overlapping frequency domain resource allocation as described in
Clause 5.1.2.3.

\- When the UE is set to \'fdmSchemeB*\'*, the UE shall receive two
PDSCH transmission occasions of the same TB with each TCI state
associated to a PDSCH transmission occasion which has non-overlapping
frequency domain resource allocation with respect to the other PDSCH
transmission occasion as described in Clause 5.1.2.3.

\- When the UE is set to \'tdmSchemeA*\'*, the UE shall receive two
PDSCH transmission occasions of the same TB with each TCI state
associated to a PDSCH transmission occasion which has non-overlapping
time domain resource allocation with respect to the other PDSCH
transmission occasion and both PDSCH transmission occasions shall be
received within a given slot as described in Clause 5.1.2.1.

When a UE is configured by the higher layer parameter *repetitionNumber*
in *PDSCH-TimeDomainResourceAllocation*, the UE not configured with
*dl-OrJointTCI-StateList* may expect to be indicated with one or two TCI
states in a codepoint of the DCI field *\'Transmission Configuration
Indication\'* or when the UE configured with *dl-OrJointTCI-StateList*
may expect to apply one or two indicated TCI states to the PDSCH,
together with the DCI field \'*Time domain resource assignment*\'
indicating an entry which contains *repetitionNumber* in
*PDSCH-TimeDomainResourceAllocation* and DM-RS port(s) within one CDM
group in the DCI field \'*Antenna Port(s)\'*.

\- When two TCI states are indicated in a DCI with \'*Transmission
Configuration Indication*\' field for the UE not configured with
*dl-OrJointTCI-StateList*, or when the UE configured with
*dl-OrJointTCI-StateList* is having two indicated TCI States to be
applied to PDSCH, the UE may expect to receive multiple slot level PDSCH
transmission occasions of the same TB with two TCI states used across
multiple PDSCH transmission occasions in the *repetitionNumber*
consecutive slots as defined in Clause 5.1.2.1.

\- When one TCI state is indicated in a DCI with \'*Transmission
Configuration Indication*\' field for the UE not configured with
*dl-OrJointTCI-StateList*, or when the UE configured with
*dl-OrJointTCI-StateList* is having one indicated TCI states to be
applied to PDSCH, the UE may expect to receive multiple slot level PDSCH
transmission occasions of the same TB with one TCI state used across
multiple PDSCH transmission occasions in the *repetitionNumber*
consecutive slots as defined in Clause 5.1.2.1.

When a UE is not indicated with a DCI that DCI field \'*Time domain
resource assignment*\' indicating an entry which contains
*repetitionNumber* in *PDSCH-TimeDomainResourceAllocation*, and it is
indicated with two TCI states in a codepoint of the DCI field
*\'Transmission Configuration Indication\'* for the UE not configured
with *dl-OrJointTCI-StateList*, or when the UE configured with
*dl-OrJointTCI-StateList* is having two indicated TCI States to be
applied to PDSCH, and is indicated with DM-RS port(s) within two CDM
groups in the DCI field \'*Antenna Port(s)\'* and it is not configured
with higher layer parameter *sfnSchemePDSCH*, the UE may expect to
receive a single PDSCH where the association between the DM-RS ports and
the TCI states are as defined in Clause 5.1.6.2.

When a UE is not indicated with a DCI that DCI field \'*Time domain
resource assignment*\' indicating an entry which contains
*repetitionNumber* in *PDSCH-TimeDomainResourceAllocation*, and it is
not configured with *dl-OrJointTCI-StateList* and is indicated with one
TCI states in a codepoint of the DCI field *\'Transmission Configuration
Indication\',* or it is configured with *dl-OrJointTCI-StateList* and is
expected to apply one indicated TCI states to PDSCH, the UE procedure
for receiving the PDSCH upon detection of a PDCCH follows Clause 5.1.

When a UE is configured with higher layer parameter *sfnSchemePDSCH* set
to either *\'*sfnSchemeA*\'* or *\'*sfnSchemeB*\'* and

\- if the UE reports its capability of *sfn-SchemeA-DynamicSwitching* or
*sfn-SchemeB-DynamicSwitching*, the UE not configured with
*dl-OrJointTCI-StateList* is indicated with one or two TCI state(s) in a
codepoint of the DCI field *\'Transmission Configuration Indication\'*
in DCI format 1_1/1_2, or the UE configured with
*dl-OrJointTCI-StateList* is having one or two indicated TCI States to
be applied to PDSCH

\- otherwise, the UE not configured with *dl-OrJointTCI-StateList* is
not expected to be indicated with one TCI state per any of TCI codepoint
by MAC CE, and the UE is indicated with two TCI states in a codepoint of
the DCI field *\'Transmission Configuration Indication\'* in DCI format
1_1/1_2, or the UE configured with *dl-OrJointTCI-StateList* is having
two indicated TCI States to be applied to PDSCH

the UE procedure for receiving the PDSCH upon detection of a PDCCH
follows clause 5.1 and the QCL assumption for the PDSCH as defined in
clause 5.1.5.

When a UE is configured with both *sfnSchemePDSCH* and *sfnSchemePDCCH*,
the UE shall expect that *sfnSchemePDSCH* and *sfnSchemePDCCH* are set
to the same scheme, either *\'*sfnSchemeA*\'* or *\'*sfnSchemeB*\'*.

If a UE not configured with *dl-OrJointTCI-StateList* is configured with
*sfnSchemePDCCH* set to \'sfnSchemeA\' and activated with two TCI states
by MAC CE, and the UE does not report its capability of
*sfn-SchemeA-PDCCH-only*, the UE is expected to be configured with
*sfnSchemePDSCH* set to *\'sfnSchemeA\'* and indicated with two TCI
states in a codepoint of the DCI field *\'Transmission Configuration
Indication\',* if the PDSCH is scheduled by DCI format 1_1/1_2.

If a UE configured with *dl-OrJointTCI-StateList* and having two
indicated TCI-States is configured with *sfnSchemePdcch* set to
\'sfnSchemeA\' for a DL BWP and signaled by the higher layer parameter
*applyIndicatedTCI-State* to apply both indicated TCI-States to a PDCCH
on a CORESET, and the UE does not report its capability of
*sfn-SchemeA-PDCCH-only*, the UE is expected to be configured with
*sfnSchemePdsch* set to *\'sfnSchemeA\'* and both indicated TCI-States
are applicable to PDSCH, if the PDSCH is scheduled by DCI format 1_1/1_2
on the PDCCH.

If a UE not configured with *dl-OrJointTCI-StateList* is configured with
*sfnSchemePDCCH* set to \'sfnSchemeB\' and activated with two TCI states
by MAC CE, the UE is expected to be configured with *sfnSchemePDSCH* set
to *\'sfnSchemeB\'* and indicated with two TCI states in a codepoint of
the DCI field *\'Transmission Configuration Indication\',* if the PDSCH
is scheduled by DCI format 1_1/1_2.

If a UE configured with *dl-OrJointTCI-StateList* and having two
indicated TCI-States is configured with *sfnSchemePdcch* set to
\'sfnSchemeB\' for a DL BWP, and signaled by the higher layer parameter
*applyIndicatedTCI-State* to apply both indicated TCI-States to a PDCCH
on a CORESET, the UE is expected to be configured with *sfnSchemePdsch*
set to *\'sfnSchemeB\'* and both indicated TCI-States are applicable to
PDSCH*,* if the PDSCH is scheduled by DCI format 1_1/1_2 on the PDCCH.

When a UE is configured with *sfnSchemePDSCH* and/or *sfnSchemePDCCH*,
the UE shall expect that the *sfnSchemePDSCH* and/or *sfnSchemePDCCH*
configuration are the same within a CC, and the UE shall expect that the
*sfnSchemePDSCH* and/or *sfnSchemePDCCH* configuration are the same in
all CCs in a same frequency band if the UE is configured with CA, where
the UE does not expect to be configured with *sfnSchemePDSCH* and/or
*sfnSchemePDCCH* in initial BWP in each CC.

For the PDSCH scheduled by PDCCH with DCI format 4_0 with CRC scrambled
by MCCH-RNTI, the parameter *pdsch-TimeDomainAllocationList,*
*mcs-Table*, *xOverhead*, *rateMatchPatternToAddModList* and
*RateMatchPatternLTE-CRS* are provided by *pdsch-ConfigMCCH*. For the
PDSCH scheduled by PDCCH with DCI format 4_0 with CRC scrambled by
G-RNTI for broadcast, the parameter *pdsch-TimeDomainAllocationList,*
*mcs-Table*, *xOverhead*, *rateMatchPatternToAddModList* and
*RateMatchPatternLTE-CRS* are provided by *pdsch-ConfigMTCH*, if
configured; or by *pdsch-ConfigMCCH*, otherwise.

For the PDSCH scheduled by PDCCH with DCI format 4_0 with CRC scrambled
by Multicast MCCH-RNTI, the parameter *pdsch-TimeDomainAllocationList,*
*mcs-Table*, *xOverhead*, *rateMatchPatternToAddModList* and
*RateMatchPatternLTE-CRS* are provided by *pdsch-ConfigMCCH* for MBS
multicast. For the PDSCH scheduled by PDCCH with DCI format 4_1 with CRC
scrambled by G-RNTI for multicast in RRC_INACTIVE, the
parameter *pdsch-TimeDomainAllocationList,* *mcs-Table*, *xOverhead*,
*rateMatchPatternToAddModList* and *RateMatchPatternLTE-CRS* are
provided by *pdsch-ConfigMTCH-r18* if configured; or
by *pdsch-ConfigMCCH* for MBS multicast, otherwise.

If more than one PDSCH on a serving cell each without a corresponding
PDCCH transmission are in a slot, after resolving overlapping with
symbols in the slot indicated as uplink by
*tdd-UL-DL-ConfigurationCommon*, or by
*tdd-UL-DL-ConfigurationDedicated*, or determined as non-active periods
of cell DTX, if the serving cell is activated with cell DTX, based on
\[10, TS 38.321\], a UE receives one or more PDSCHs without
corresponding PDCCH transmissions in the slot as specified below.

‒ Step 0: set *j=0*, where *j* is the number of selected PDSCH(s) for
decoding. *Q* is the set of activated PDSCHs without corresponding PDCCH
transmissions within the slot

‒ Step 1: A UE receives one PDSCH with the lowest configured
*sps-ConfigIndex* within *Q*, set *j=j+1*. Designate the received PDSCH
as survivor PDSCH.

‒ Step 2: The survivor PDSCH in step 1 and any other PDSCH(s)
overlapping (even partially) with the survivor PDSCH in step 1 are
excluded from *Q*.

‒ Step 3: Repeat step 1 and 2 until *Q* is empty or *j* is equal to the
number of unicast/multicast PDSCHs in a slot supported by the UE.

For a cell detected in cell search procedure with synchronization raster
defined in Table 5.4.3.1-2 or Table 5.4.3.1-3 of \[8, TS 38.101-1\], the
size of CORESET 0 for the cell in this clause refers to the size of
punctured CORESET 0 as defined in clause 7.3.2.2 of \[4, TS 38.211\] if
any.