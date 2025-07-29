# 6 Link recovery procedures

A UE can be provided, for each BWP of a serving cell, a set
${\overline{q}}_{0}$ of periodic CSI-RS resource configuration indexes
by *failureDetectionResourcesToAddModList* and a set
${\overline{q}}_{1}$ of periodic CSI-RS resource configuration indexes
and/or SS/PBCH block indexes by *candidateBeamRSList* or
*candidateBeamRSListExt* or *candidateBeamRS-List* for radio link
quality measurements on the BWP of the serving cell. Instead of the sets
${\overline{q}}_{0}$ and ${\overline{q}}_{1}$, for each BWP of a serving
cell, the UE can be provided respective two sets ${\overline{q}}_{0,0}$
and ${\overline{q}}_{0,1}$ of periodic CSI-RS resource configuration
indexes by *failureDetectionSet1* and *failureDetectionSet2* that can be
activated by a MAC CE \[11 TS 38.321\] and corresponding two sets
${\overline{q}}_{1,0}$ and ${\overline{q}}_{1,1}$ of periodic CSI-RS
resource configuration indexes and/or SS/PBCH block indexes by
*candidateBeamRS-List* and *candidateBeamRS-List2*, respectively, for
radio link quality measurements on the BWP of the serving cell. The set
${\overline{q}}_{0,0}$ is associated with the set ${\overline{q}}_{1,0}$
and the set ${\overline{q}}_{0,1}$ is associated with the set
${\overline{q}}_{1,1}$.

If the UE is not provided ${\overline{q}}_{0}$ by
*failureDetectionResourcesToAddModList* for a BWP of the serving cell,
the UE determines the set ${\overline{q}}_{0}$ to include periodic
CSI-RS resource configuration indexes with same values as the RS indexes
in the RS sets indicated by *TCI-State* for respective CORESETs that the
UE uses for monitoring PDCCH. If the UE is not provided
${\overline{q}}_{0,0}$ and $\ {\overline{q}}_{0,1}$ for a BWP of the
serving cell, the UE determines the set ${\overline{q}}_{0,0}$ and
$\ {\overline{q}}_{0,1}$ to include periodic CSI-RS resource
configuration indexes with same values as the RS indexes in the RS sets
indicated by *TCI-State* for first and second CORESETs that the UE uses
for monitoring PDCCH, respectively, where the UE is provided two
*coresetPoolIndex* values 0 and 1 for the first and second CORESETs, or
is not provided *coresetPoolIndex* value for the first CORESETs and is
provided *coresetPoolIndex* value of 1 for the second CORESETs,
respectively. If there are two RS indexes in a TCI state, the set
${\overline{q}}_{0}$ or ${\overline{q}}_{0,0}$, or
${\overline{q}}_{0,1}$ includes RS indexes configured with *qcl-Type*
set to \'typeD\' for the corresponding TCI states. If a CORESET that the
UE uses for monitoring PDCCH includes two TCI states and the UE is
provided *sfnSchemePdcch* set to \'sfnSchemeA\' or \'sfnSchemeB\', the
set ${\overline{q}}_{0}$ includes RS indexes in the RS sets associated
with the two TCI states.

The UE expects the set ${\overline{q}}_{0}$ to include up to two RS
indexes. If the UE is provided ${\overline{q}}_{0,0}$ or
${\overline{q}}_{0,1}$, the UE expects the set ${\overline{q}}_{0,0}$ or
the set ${\overline{q}}_{0,1}$ to include up to a number of $N_{BFD}$ RS
indexes indicated by *maxBFD-RS-resourcesPerSetPerBWP*. If the UE is not
provided ${\overline{q}}_{0,0}$ or ${\overline{q}}_{0,1}$, and if a
number of active TCI states for PDCCH receptions in the first or second
CORESETs is larger than $N_{BFD}$, the UE determines the set
${\overline{q}}_{0,0}$ or ${\overline{q}}_{0,1}$ to include periodic
CSI-RS resource configuration indexes with same values as the RS indexes
in the RS sets associated with the active TCI states for PDCCH
receptions in the first or second CORESETs corresponding to search space
sets according to an ascending order for PDCCH monitoring periodicity.
If more than one first or second CORESETs correspond to search space
sets with same monitoring periodicity, the UE determines the order of
the first or second CORESETs according to a descending order of a
CORESET index.

If a UE

\- is not provided *coresetPoolIndex* or is provided *coresetPoolIndex*
with a value of 0 for first CORESETs on an active DL BWP of a serving
cell,

\- is provided *coresetPoolIndex* with a value of 1 for second CORESETs
on the active DL BWP of the serving cells, and

\- is provided *SSB-MTCAdditionalPCI*

SS/PBCH block indexes associated with a physical cell identity other
than the one provided by *physCellId* in *ServingCellConfigCommon* can
be provided in ${\overline{q}}_{1,1}$ set and the corresponding
${\overline{q}}_{0,1}$ set is associated with the physical cell
identity.

The UE expects single port RS in the set ${\overline{q}}_{0}$, or
${\overline{q}}_{0,0}$, or ${\overline{q}}_{0,1}$. The UE expects
single-port or two-port CSI-RS with frequency density equal to 1 or 3
REs per RB in the set ${\overline{q}}_{1}$, or ${\overline{q}}_{1,0}$,
or ${\overline{q}}_{1,1}$. The thresholds Q~out,LR~ and Q~in,LR~
correspond to the default value of *rlmInSyncOutOfSyncThreshold*, as
described in \[10, TS 38.133\] for Q~out~, and to the value provided by
*rsrp-ThresholdSSB* or *rsrp-ThresholdBFR*, respectively.

The physical layer in the UE assesses the radio link quality according
to the set ${\overline{q}}_{0}$, ${\overline{q}}_{0,0}$, or
${\overline{q}}_{0,1}$, of resource configurations against the threshold
Q~out,LR~. For the set ${\overline{q}}_{0}$, the UE assesses the radio
link quality only according to SS/PBCH blocks on the PCell or the PSCell
or periodic CSI-RS resource configurations that are quasi co-located, as
described in \[6, TS 38.214\], with the DM-RS of PDCCH receptions by the
UE. The UE applies the Q~in,LR~ threshold to the L1-RSRP measurement
obtained from a SS/PBCH block. The UE applies the Q~in,LR~ threshold to
the L1-RSRP measurement obtained for a CSI-RS resource after scaling a
respective CSI-RS reception power with a value provided by
*powerControlOffsetSS*.

In non-DRX mode operation, the physical layer in the UE provides an
indication to higher layers when the radio link quality for all
corresponding resource configurations in the set ${\overline{q}}_{0}$,
or in the set ${\overline{q}}_{0,0}$ or ${\overline{q}}_{0,1}$, that the
UE uses to assess the radio link quality is worse than the threshold
Q~out,LR~. The physical layer informs the higher layers when the radio
link quality is worse than the threshold Q~out,LR~ with a periodicity
determined by the maximum between the shortest periodicity among the
SS/PBCH blocks on the PCell or the PSCell and/or the periodic CSI-RS
configurations in the set ${\overline{q}}_{0}$, ${\overline{q}}_{0,0}$,
or ${\overline{q}}_{0,1}$ that the UE uses to assess the radio link
quality and 2 msec. In DRX mode operation, the physical layer provides
an indication to higher layers when the radio link quality is worse than
the threshold Q~out,LR~ with a periodicity determined as described in
\[10, TS 38.133\].

For the PCell or the PSCell, upon request from higher layers, the UE
provides to higher layers the periodic CSI-RS configuration indexes
and/or SS/PBCH block indexes from the set ${\overline{q}}_{1}$, or
${\overline{q}}_{1,0}$, or ${\overline{q}}_{1,1}$ and the corresponding
L1-RSRP measurements that are larger than or equal to the Q~in,LR~
threshold.

For the SCell, upon request from higher layers, the UE indicates to
higher layers whether there is at least one periodic CSI-RS
configuration index or SS/PBCH block index from the set
${\overline{q}}_{1}$, or ${\overline{q}}_{1,0}$, or
${\overline{q}}_{1,1}$ with corresponding L1-RSRP measurements that is
larger than or equal to the Q~in,LR~ threshold, and provides the
periodic CSI-RS configuration indexes and/or SS/PBCH block indexes from
the set ${\overline{q}}_{1}$, or ${\overline{q}}_{1,0}$, or
${\overline{q}}_{1,1}$ and the corresponding L1-RSRP measurements that
are larger than or equal to the Q~in,LR~ threshold, if any.

For the PCell or the PSCell, a UE can be provided a CORESET through a
link to a search space set provided by *recoverySearchSpaceId,* as
described in clause 10.1, for monitoring PDCCH in the CORESET. If the UE
is provided *recoverySearchSpaceId*, the UE does not expect to be
provided another search space set for monitoring PDCCH in the CORESET
associated with the search space set provided by
*recoverySearchSpaceId*.

For the PCell or the PSCell, the UE can be provided, by
*PRACH-ResourceDedicatedBFR*, a configuration for PRACH transmission as
described in clause 8.1. For PRACH transmission in slot $n$ and
according to antenna port quasi co-location parameters associated with
periodic CSI-RS resource configuration or with SS/PBCH block associated
with index $q_{new}$ provided by higher layers \[11, TS 38.321\], the UE
monitors PDCCH in a search space set provided by *recoverySearchSpaceId*
for detection of a DCI format with CRC scrambled by C-RNTI or MCS-C-RNTI
starting from slot $n + 4 + {2^{\mu} \bullet k}_{mac}$, where $\mu$ is
the SCS configuration for the PRACH transmission and $k_{mac}$ is a
number of slots provided by *kmac* \[12, TS 38.331\] or $k_{mac} = 0$ if
*kmac* is not provided, within a window configured by
*BeamFailureRecoveryConfig*. For PDCCH monitoring in a search space set
provided by *recoverySearchSpaceId* and for corresponding PDSCH
receptions, the UE assumes the same antenna port quasi-collocation
parameters as the ones associated with index $q_{new}$ until the UE
receives by higher layers an activation for a TCI state or any of the
parameters *tci-StatesPDCCH-ToAddList* and/or
*tci-StatesPDCCH-ToReleaseList*. After the UE detects a DCI format with
CRC scrambled by C-RNTI or MCS-C-RNTI in the search space set provided
by *recoverySearchSpaceId*, the UE continues to monitor PDCCH candidates
in the search space set provided by *recoverySearchSpaceId* until the UE
receives a MAC CE activation command for a TCI state or
*tci-StatesPDCCH-ToAddList* and/or *tci-StatesPDCCH-ToReleaseList.*

For the PCell or the PSCell, after 28 symbols from a last symbol of a
first PDCCH reception in a search space set provided by
*recoverySearchSpaceId* for which the UE detects a DCI format with CRC
scrambled by C-RNTI or MCS-C-RNTI and until the UE receives an
activation command for *PUCCH-SpatialRelationInfo* \[11, TS 38.321\] or
is provided *PUCCH-SpatialRelationInfo* for PUCCH resource(s), the UE
transmits a PUCCH on a same cell as the PRACH transmission using

\- a same spatial filter as for the last PRACH transmission

\- a power determined as described in clause 7.2.1 with $q_{u} = 0$,
${q_{d} = q}_{new}$, and $l = 0$

For the PCell or the PSCell and for sets ${\overline{q}}_{0}$ and
${\overline{q}}_{1}$, after 28 symbols from a last symbol of a first
PDCCH reception in a search space set provided by
*recoverySearchSpaceId* where a UE detects a DCI format with CRC
scrambled by C-RNTI or MCS-C-RNTI, the UE assumes same antenna port
quasi-collocation parameters as the ones associated with index $q_{new}$
for PDCCH monitoring in a CORESET with index 0.

If a UE is provided *dl-OrJointTCI-StateList* or *ul-TCI-StateList* and
is indicated one or two TCI state(s) for the PCell or the PSCell \[6, TS
38.214\] associated with ${\overline{q}}_{0}$ and ${\overline{q}}_{1}$,
after 28 symbols from a last symbol of a first PDCCH reception in a
search space set provided by *recoverySearchSpaceId* where the UE
detects a DCI format with CRC scrambled by C-RNTI or MCS-C-RNTI, the UE

\- if *SSB-MTC-AdditionalPCI* is not provided, monitors PDCCH in all
CORESETs, and receives PDSCH and aperiodic CSI-RS resource in a CSI-RS
resource set with same indicated TCI state as for the PDCCH and PDSCH,
using the same antenna port quasi co-location parameters as the ones
associated with the corresponding index $q_{\text{new}}$, if any

\- transmits PUSCH, PUCCH and SRS that uses a same spatial domain filter
with same indicated TCI state as for the PUSCH and the PUCCH, using a
same spatial domain filter as for the last PRACH transmission using the
following parameters for determination of a corresponding power as
described in clauses 7.1.1, 7.2.1, and 7.3.1

\- the RS index ${q_{d} = q}_{new}$ for obtaining the downlink pathloss
estimate

\- the values of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$,
$\alpha_{b,f,c}(j)$, and the PUSCH power control adjustment state $l$
provided by *p0AlphaSetforPUSCH* associated with the smallest value of
*ul-powercontrolId* for the PCell or the PSCell

\- the value of $P_{\text{O\_UE\_PUCCH}}\left( q_{u} \right)$ and the
PUCCH power control adjustment state $l$ provided by
*p0AlphaSetforPUCCH* associated with the smallest value of
*ul-powercontrolId* for the PCell or the PSCell

\- the values of $P_{\text{O\_UE\_SRS},b,f,c}\left( q_{s} \right)$,
$\alpha_{SRS,b,f,c}\left( q_{s} \right)$, and the SRS power control
adjustment state $l$ provided by *p0AlphaSetforSRS* associated with the
smallest value of *ul-powercontrolId* for the PCell or the PSCell

For the remaining of this clause, if a PDCCH reception includes two
PDCCH candidates from two linked search space sets based on
*searchSpaceLinkingId*, as described in clause 10.1, the last symbol of
the PDCCH reception is the last symbol of the PDCCH candidate that ends
later. The PDCCH reception includes the two PDCCH candidates also when
the UE is not required to monitor one of the two PDCCH candidates as
described in clauses 10 (except clause 10.4), 11.1, 11.1.1 and 17.2.

For the PCell or the PSCell, if BFR MAC CE \[11, TS 38.321\] is provided
in Msg3 or MsgA of contention based random access procedure, and if a
PUCCH resource is provided with *PUCCH-SpatialRelationInfo*, after 28
symbols from the last symbol of the PDCCH reception that determines the
completion of the contention based random access procedure as described
in clause 5.1.4a or in clause 5.1.5 of \[11, TS 38.321\], the UE
transmits the PUCCH on a same cell as the PRACH transmission using

\- a same spatial filter as for the last PRACH transmission

\- a power determined as described in clause 7.2.1 with $q_{u} = 0$,
${q_{d} = q}_{new}$, and $l = 0$, where $q_{new}$ is the SS/PBCH block
index selected for the last PRACH transmission.

If a UE is provided *dl-OrJointTCI-StateList* or *ul-TCI-StateList* and
is indicated one or two TCI state(s) for the PCell or the PSCell
associated with ${\overline{q}}_{0}$ and ${\overline{q}}_{1}$, and the
UE provides BFR MAC CE in Msg3 or MsgA of contention based random access
procedure, after 28 symbols from the last symbol of the PDCCH reception
that determines the completion of the contention based random access
procedure as described in \[11, TS 38.321\], the UE

\- if *SSB-MTC-AdditionalPCI* is not provided, monitors PDCCH in all
CORESETs, and receives PDSCH and aperiodic CSI-RS resource in a CSI-RS
resource set with same indicated TCI state as for the PDCCH and PDSCH
using the same antenna port quasi co-location parameters as the ones
associated with the corresponding index $q_{\text{new}}$, if any

\- transmits PUSCH, PUCCH and SRS that uses a same spatial domain filter
with same indicated TCI state as for the PUSCH and PUCCH, using a same
spatial domain filter as for the last PRACH transmission using the
following parameters for determination of a corresponding power as
described in clauses 7.1.1, 7.2.1, and 7.3.1

\- the RS index ${q_{d} = q}_{new}$ for obtaining the downlink pathloss
estimate

\- the values of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$,
$\alpha_{b,f,c}(j)$, and the PUSCH power control adjustment state $l$
provided by *p0AlphaSetforPUSCH* associated with the smallest value of
*ul-powercontrolId* for the PCell or the PSCell

\- the value of $P_{\text{O\_UE\_PUCCH}}\left( q_{u} \right)$ and the
PUCCH power control adjustment state $l$ provided by
*p0AlphaSetforPUCCH* associated with the smallest value of
*ul-powercontrolId* for the PCell or the PSCell

\- the values of $P_{\text{O\_UE\_SRS},b,f,c}\left( q_{s} \right)$,
$\alpha_{SRS,b,f,c}\left( q_{s} \right)$, and the SRS power control
adjustment state $l$ provided by *p0AlphaSetforSRS* associated with the
smallest value of *ul-powercontrolId* for the PCell or the PSCell

A UE can be provided, by *schedulingRequestID-BFR-SCell*, a
configuration for PUCCH transmission with a link recovery request (LRR)
as described in clause 9.2.4 for the UE to transmit PUCCH \[11, TS
38.321\]. If the PCell or the PSCell is associated with sets
${\overline{q}}_{0,0}$ and ${\overline{q}}_{1,0}$, and with sets
${\overline{q}}_{0,1}$ and ${\overline{q}}_{1,1}$, the UE can be
provided by *schedulingRequestID-BFR* a first configuration for PUCCH
transmission with a LRR and, if the UE provides *twoLRRcapability*, the
UE can be provided by *schedulingRequestID-BFR2* a second configuration
for PUCCH transmission with a LRR. If the UE is provided only the first
configuration, the UE transmits a PUCCH with LRR for either set
${\overline{q}}_{0,0}$ or ${\overline{q}}_{0,1}$. If the UE is provided
both the first and second configurations, the UE uses the first
configuration to transmt a PUCCH with LRR associated with set
${\overline{q}}_{0,0}$ and the second configuration to transmit a PUCCH
with LRR associated with set ${\overline{q}}_{0,1}$ \[11, TS 38.321\].

The UE can provide in a first PUSCH MAC CE index(es) for at least
corresponding SCell(s) with radio link quality worse than Q~out,LR~,
indication(s) of presence of $q_{\text{new}}$ for corresponding
SCell(s), and index(es) $q_{\text{new}}$ for a periodic CSI-RS
configuration or for a SS/PBCH block provided by higher layers, as
described in \[11, TS 38.321\], if any, for corresponding SCell(s).
After 28 symbols from a last symbol of a PDCCH reception with a DCI
format scheduling a PUSCH transmission with a same HARQ process number
as for the transmission of the first PUSCH and having a toggled NDI
field value, the UE

\- monitors PDCCH in all CORESETs on the SCell(s) indicated by the MAC
CE using the same antenna port quasi co-location parameters as the ones
associated with the corresponding index(es) $q_{\text{new}}$, if any

\- transmits PUCCH on a PUCCH-SCell using a same spatial domain filter
as the one corresponding to $q_{\text{new}}$, if any, for periodic
CSI-RS or SS/PBCH block reception, as described in clause 9.2.2, and
using a power determined as described in clause 7.2.1 with
$q_{\text{u}} = 0$, ${q_{\text{d}} = q}_{\text{new}}$, and $l = 0$, if

\- the UE is provided *PUCCH-SpatialRelationInfo* for the PUCCH,

\- a PUCCH with the LRR was either not transmitted or was transmitted on
the PCell or the PSCell, and

\- the PUCCH-SCell is included in the SCell(s) indicated by the MAC-CE

where the SCS configuration for the 28 symbols is the smallest of the
SCS configurations of the active DL BWP for the PDCCH reception and of
the active DL BWP(s) of the at least one SCell.

For serving cells associated with ${\overline{q}}_{0}$ and
${\overline{q}}_{1}$, if a UE is provided *dl-OrJointTCI-StateList* or
*ul-TCI-StateList* and is indicated one or two TCI state(s), after 28
symbols from a last symbol of a PDCCH reception with a DCI format
scheduling a PUSCH transmission with a same HARQ process number as for
the transmission of the first PUSCH and having a toggled NDI field
value, the UE

\- if *SSB-MTC-AdditionalPCI* is not provided, monitors PDCCH in all
CORESETs, on the SCell (s) indicated by the MAC CE, and receives PDSCH
and aperiodic CSI-RS resource in a CSI-RS resource set using the same
antenna port quasi co-location parameters as the ones associated with
the corresponding index $q_{\text{new}}$, if any

\- transmits PUSCH, PUCCH and SRS that uses a same spatial domain filter
with same indicated TCI state as for the PUSCH and PUCCH, using a same
spatial domain filter as the one corresponding to $q_{\text{new}}$, if
any, and using the following parameters for determination of a
corresponding power as described in clauses 7.1.1, 7.2.1, and 7.3.1

\- the RS index ${q_{d} = q}_{new}$ for obtaining the downlink pathloss
estimate

\- the values of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$,
$\alpha_{b,f,c}(j)$, and the PUSCH power control adjustment state $l$
provided by *p0AlphaSetforPUSCH* associated with the smallest value of
*ul-powercontrolId* for the corresponding SCell

\- the value of $P_{\text{O\_UE\_PUCCH}}\left( q_{u} \right)$ and the
PUCCH power control adjustment state $l$ provided by
*p0AlphaSetforPUCCH* associated with the smallest value of
*ul-powercontrolId* for the corresponding SCell

\- the values of $P_{\text{O\_UE\_SRS},b,f,c}\left( q_{s} \right)$,
$\alpha_{SRS,b,f,c}\left( q_{s} \right)$, and the SRS power control
adjustment state $l$ provided by *p0AlphaSetforSRS* associated with the
smallest value of *ul-powercontrolId* for the corresponding SCell

If there is at least one serving cell associated with sets
${\overline{q}}_{0,0}$ and ${\overline{q}}_{1,0}$, and with sets
${\overline{q}}_{0,1}$ and ${\overline{q}}_{1,1}$, the UE can provide in
a second PUSCH MAC CE index(es) for cell(s) with ${\overline{q}}_{0}$
and/or with at least one of ${\overline{q}}_{0,0}$ and
${\overline{q}}_{0,1}$ having radio link quality worse than Q~out,LR~,
the index(es) of those ${\overline{q}}_{0,0}$ and/or
${\overline{q}}_{0,1}$, and indication(s) of presence of
$q_{\text{new}}$ and of index(es) $q_{\text{new}}$, if any, from
${\overline{q}}_{1}$ and/or corresponding sets ${\overline{q}}_{1,0}$
and/or ${\overline{q}}_{1,1}$ for the serving cells.

For serving cells associated with sets ${\overline{q}}_{0,0}$ and
${\overline{q}}_{1,0}$, and with sets ${\overline{q}}_{0,1}$ and
${\overline{q}}_{1,1}$, and having radio link quality worse than
Q~out,LR~, after 28 symbols from a last symbol of a first PDCCH
reception with a DCI format scheduling a PUSCH transmission with a same
HARQ process number as for transmission of the second PUSCH and having a
toggled NDI field value, the UE assumes antenna port quasi-collocation
parameters

\- corresponding to $q_{\text{new}}$ from ${\overline{q}}_{1,0}$, if
any, for the first CORESETs,

\- corresponding to $q_{\text{new}}$ from ${\overline{q}}_{1,1}$, if
any, for the second CORESETs

where the SCS configuration for the 28 symbols is the smallest of the
SCS configurations of the active DL BWP for the PDCCH reception and of
the active DL BWP(s) of the serving cells.

For a serving cell associated with sets ${\overline{q}}_{0,0}$ and
${\overline{q}}_{1,0}$, and with sets ${\overline{q}}_{0,1}$ and
${\overline{q}}_{1,1}$, and having radio link quality worse than
Q~out,LR~, and if a UE is provided *dl-OrJointTCI-StateList* or
*TCI-UL-State* and is indicated a first *TCI-State* or *TCI-UL-State*
and a second *TCI-State* or *TCI-UL-State*, after 28 symbols from a last
symbol of a first PDCCH reception with a DCI format scheduling a PUSCH
transmission with a same HARQ process number as for the transmission of
the second PUSCH and having a toggled NDI field value, the UE

\- monitors PDCCH that applies the first *TCI-State* state, and receives
PDSCH and aperiodic CSI-RS resource that apply the first *TCI-State*,
using same antenna port quasi co-location parameters as the ones
associated with a corresponding index $q_{\text{new}}$ from
${\overline{q}}_{1,0}$, if any, on the serving cell

\- monitors PDCCH that applies the second *TCI-State*, and receives
PDSCH and aperiodic CSI-RS resource that apply the second *TCI-State*,
on the serving cell using same antenna port quasi co-location parameters
as the ones associated with a corresponding index $q_{\text{new}}$ from
${\overline{q}}_{1,1}$, if any, on the serving cell

\- transmits PUSCH, PUCCH, and SRS that apply the first *TCI-State* or
*TCI-UL-State* using a same spatial domain filter as the one
corresponding to $q_{\text{new}}$ from ${\overline{q}}_{1,0}$, if any,
on the serving cell and using the following parameters for determination
of a corresponding power as described in clauses 7.1.1, 7.2.1, and 7.3.1

\- the RS index ${q_{d} = q}_{new}$ from ${\overline{q}}_{1,0}$, if any,
for obtaining a corresponding downlink pathloss estimate for the serving
cell

\- the values of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$,
$\alpha_{b,f,c}(j)$, and the PUSCH power control adjustment state $l$
provided by *p0AlphaSetforPUSCH* associated with the smallest value of
*ul-powercontrolId* for the serving cell

\- the value of
$P_{O\_ UE\_ PUCCH}\left( q_{u} \right)\left( q_{u} \right)$ and the
PUCCH power control adjustment state $l$ provided by
*p0AlphaSetforPUCCH* associated with the smallest value of
*ul-powercontrolId* for the serving cell

\- the values of $P_{\text{O\_UE\_SRS},b,f,c}\left( q_{s} \right)$,
$\alpha_{SRS,b,f,c}\left( q_{s} \right)$, and the SRS power control
adjustment state $l$ provided by *p0AlphaSetforSRS* associated with the
smallest value of *ul-powercontrolId* for the serving cell

\- transmits PUSCH, PUCCH, and SRS that apply the second *TCI-State* or
*TCI-UL-State* using a same spatial domain filter as the one
corresponding to $q_{\text{new}}$ from ${\overline{q}}_{1,1}$, if any,
on the serving cell and using the following parameters for determination
of a corresponding power as described in clauses 7.1.1, 7.2.1, and 7.3.1

\- the RS index ${q_{d} = q}_{new}$ from ${\overline{q}}_{1,1}$, if any,
for obtaining a corresponding downlink pathloss estimate for the serving
cell

\- the values of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$,
$\alpha_{b,f,c}(j)$, and the PUSCH power control adjustment state $l$
provided by *p0AlphaSetforPUSCH* associated with the smallest value of
*ul-powercontrolId* for the serving cell

\- the value of
$P_{O\_ UE\_ PUCCH}\left( q_{u} \right)\left( q_{u} \right)$ and the
PUCCH power control adjustment state $l$ provided by
*p0AlphaSetforPUCCH* associated with the smallest value of
*ul-powercontrolId* for the serving cell

\- the values of $P_{\text{O\_UE\_SRS},b,f,c}\left( q_{s} \right)$,
$\alpha_{SRS,b,f,c}\left( q_{s} \right)$, and the SRS power control
adjustment state $l$ provided by *p0AlphaSetforSRS* associated with the
smallest value of *ul-powercontrolId* for the serving cell

where the SCS configuration for the 28 symbols is the smallest of the
SCS configurations of the active DL BWP for the PDCCH reception and of
the active DL BWP(s) of the serving cells.

For a serving cell associated with sets ${\overline{q}}_{0,0}$ and
${\overline{q}}_{1,0}$, and with sets ${\overline{q}}_{0,1}$ and
${\overline{q}}_{1,1}$, and having radio link quality worse than
Q~out,LR~, and if a UE is provided two *coresetPoolIndex* values 0 and 1
for the first and second CORESETs, or is not provided *coresetPoolIndex*
value for the first CORESETs and is provided *coresetPoolIndex* value of
1 for the second CORESETs, respectively, and the UE is provided
*dl-OrJointTCI-StateList* or *TCI-UL-State*, after 28 symbols from a
last symbol of a first PDCCH reception with a DCI format scheduling a
PUSCH transmission with a same HARQ process number as for the
transmission of the second PUSCH and having a toggled NDI field value,
the UE

\- monitors PDCCH in the first CORESETs, and receives PDSCH
scheduled/activated by PDCCH in the first CORESETs, and aperiodic CSI-RS
resource that apply a *TCI-State* specific to the first CORESETs, using
same antenna port quasi co-location parameters as the ones associated
with a corresponding index $q_{\text{new}}$ from ${\overline{q}}_{1,0}$,
if any, for the serving cell

\- monitors PDCCH in the second CORESETs, and receives PDSCH
scheduled/activated by PDCCH in the second CORESETs, and aperiodic
CSI-RS resource that apply a *TCI-State* specific to the second
CORESETs, using the same antenna port quasi co-location parameters as
the ones associated with the corresponding index $q_{\text{new}}$ from
${\overline{q}}_{1,1}$, if any, for the serving cell

\- transmits PUSCH, PUCCH, and SRS that apply *TCI-State* or
*TCI-UL-State* specific to the first CORESETs using a same spatial
domain filter as the one corresponding to $q_{\text{new}}$ from
${\overline{q}}_{1,0}$, if any, for the serving cell and using the
following parameters for determination of a corresponding power as
described in clauses 7.1.1, 7.2.1, and 7.3.1

\- the RS index ${q_{d} = q}_{new}$ from ${\overline{q}}_{1,0}$, if any,
for obtaining a corresponding downlink pathloss estimate for the serving
cell

\- the values of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$,
$\alpha_{b,f,c}(j)$, and the PUSCH power control adjustment state $l$
provided by *p0AlphaSetforPUSCH* associated with the smallest value of
*ul-powercontrolId* for the serving cell

\- the value of
$P_{O\_ UE\_ PUCCH}\left( q_{u} \right)\left( q_{u} \right)$ and the
PUCCH power control adjustment state $l$ provided by
*p0AlphaSetforPUCCH* associated with the smallest value of
*ul-powercontrolId* for the serving cell

\- the values of $P_{\text{O\_UE\_SRS},b,f,c}\left( q_{s} \right)$,
$\alpha_{SRS,b,f,c}\left( q_{s} \right)$, and the SRS power control
adjustment state $l$ provided by *p0AlphaSetforSRS* associated with the
smallest value of *ul-powercontrolId* for the serving cell

\- transmits PUSCH, PUCCH, and SRS that apply *TCI-State* or
*TCI-UL-State* specific to the second CORESETs using a same spatial
domain filter as the one corresponding to $q_{\text{new}}$ from
${\overline{q}}_{1,1}$, if any, for the serving cell and using the
following parameters for determination of a corresponding power as
described in clauses 7.1.1, 7.2.1, and 7.3.1

\- the RS index ${q_{d} = q}_{new}$ from ${\overline{q}}_{1,1}$, if any,
for obtaining a corresponding downlink pathloss estimate for the serving
cell

\- the values of $P_{\text{O\_UE\_PUSCH},b,f,c}(j)$,
$\alpha_{b,f,c}(j)$, and the PUSCH power control adjustment state $l$
provided by *p0AlphaSetforPUSCH* associated with the smallest value of
*ul-powercontrolId* for the serving cell

\- the value of
$P_{O\_ UE\_ PUCCH}\left( q_{u} \right)\left( q_{u} \right)$ and the
PUCCH power control adjustment state $l$ provided by
*p0AlphaSetforPUCCH* associated with the smallest value of
*ul-powercontrolId* for the serving cell

\- the values of $P_{\text{O\_UE\_SRS},b,f,c}$,
$\alpha_{SRS,b,f,c}\left( q_{s} \right)$, and the SRS power control
adjustment state $l$ provided by *p0AlphaSetforSRS* associated with the
smallest value of *ul-powercontrolId* for the serving cell

where the SCS configuration for the 28 symbols is the smallest of the
SCS configurations of the active DL BWP for the PDCCH reception and of
the active DL BWP(s) of the serving cells.