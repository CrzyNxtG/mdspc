### 5.1.1 Random Access procedure initialization

The Random Access procedure described in this clause is initiated by a
PDCCH order, by the MAC entity itself, or by RRC for the events in
accordance with TS 38.300 \[2\]. There is only one Random Access
procedure ongoing at any point in time in a MAC entity. The Random
Access procedure on an SCell or an LTM candidate cell shall only be
initiated by a PDCCH order with *ra-PreambleIndex* different from
0b000000.

NOTE 1: If a new Random Access procedure is triggered while another is
already ongoing in the MAC entity, it is up to UE implementation whether
to continue with the ongoing procedure or start with the new procedure
(e.g. for SI request).

NOTE 2: If there was an ongoing Random Access procedure that is
triggered by a PDCCH order while the UE receives another PDCCH order
indicating the same Random Access Preamble, PRACH mask index and uplink
carrier, the Random Access procedure is considered as the same Random
Access procedure as the ongoing one and not initialized again.

When a Random Access procedure is initiated, UE selects a set of Random
Access resources as specified in clause 5.1.1b and initialises the
following parameters for the Random Access procedure according to the
values configured by RRC for the selected set of Random Access
resources:

\- *prach-ConfigurationIndex*: the available set of PRACH occasions for
the transmission of the Random Access Preamble for Msg1. These are also
applicable to the MSGA PRACH if the PRACH occasions are shared between
2-step and 4-step RA types;

\- *prach-ConfigurationPeriodScaling-IAB*: the scaling factor defined in
TS 38.211 \[8\] and applicable to IAB-MTs, extending the periodicity of
the PRACH occasions baseline configuration indicated by
*prach-ConfigurationIndex*;

\- *prach-ConfigurationFrameOffset-IAB*: the frame offset defined in TS
38.211 \[8\] and applicable to IAB-MTs, altering the ROs frame defined
in the baseline configuration indicated by *prach-ConfigurationIndex*;

\- *prach-ConfigurationSOffset-IAB*: the subframe/slot offset defined in
TS 38.211 \[8\] and applicable to IAB-MTs, altering the ROs subframe or
slot defined in the baseline configuration indicated by
*prach-ConfigurationIndex*;

\- *msgA-PRACH-ConfigurationIndex*: the available set of PRACH occasions
for the transmission of the Random Access Preamble for MSGA in 2-step RA
type;

\- *preambleReceivedTargetPower*: initial Random Access Preamble power
for 4-step RA type;

\- *msgA-PreambleReceivedTargetPower*: initial Random Access Preamble
power for 2-step RA type;

\- *rsrp-ThresholdSSB*: an RSRP threshold for the selection of the SSB
for 4-step RA type. If the Random Access procedure is initiated for beam
failure recovery, *rsrp-ThresholdSSB* used for the selection of the SSB
within *candidateBeamRSList* refers to *rsrp-ThresholdSSB* in
*BeamFailureRecoveryConfig* IE;

\- *rsrp-ThresholdCSI-RS*: an RSRP threshold for the selection of CSI-RS
for 4-step RA type. If the Random Access procedure is initiated for beam
failure recovery, *rsrp-ThresholdCSI-RS* is equal to *rsrp-ThresholdSSB*
in *BeamFailureRecoveryConfig* IE;

\- *msgA-RSRP-ThresholdSSB*: an RSRP threshold for the selection of the
SSB for 2-step RA type;

\- *rsrp-ThresholdSSB-SUL*: an RSRP threshold for the selection between
the NUL carrier and the SUL carrier;

*- msgA-RSRP-Threshold*: an RSRP threshold for selection between 2-step
RA type and 4-step RA type when both 2-step and 4-step RA type Random
Access Resources are configured in the UL BWP;

*- rsrp-ThresholdMsg1-RepetitionNum2*: an RSRP threshold for Msg1
repetition with repetition number 2 (see clause 5.1.1b);

*- rsrp-ThresholdMsg1-RepetitionNum4*: an RSRP threshold for Msg1
repetition with repetition number 4 (see clause 5.1.1b);

*- rsrp-ThresholdMsg1-RepetitionNum8*: an RSRP threshold for Msg1
repetition with repetition number 8 (see clause 5.1.1b);

*- rsrp-ThresholdMsg3*: an RSRP threshold for Msg3 repetition (see
clause 5.1.1b);

*- FeatureCombination*: feature or a combination of features associated
with a set of Random Access resources;

*- featurePriorities*: priorities for features, such as (e)RedCap,
Slicing, etc. (see clause 5.1.1d);

\- *msgA-TransMax*: The maximum number of MSGA transmissions when both
4-step and 2-step RA type Random Access Resources are configured;

\- *candidateBeamRSList*: a list of reference signals (CSI-RS and/or
SSB) identifying the candidate beams for recovery and the associated
Random Access parameters;

\- *recoverySearchSpaceId*: the search space identity for monitoring the
response of the beam failure recovery request;

\- *powerRampingStep*: the power-ramping factor;

\- *msgA-PreamblePowerRampingStep*: the power ramping factor for MSGA
preamble;

\- *powerRampingStepHighPriority*: the power-ramping factor in case of
prioritized Random Access procedure;

\- *scalingFactorBI*: a scaling factor for prioritized Random Access
procedure;

\- *ra-PreambleIndex*: Random Access Preamble;

\- *ra-ssb-OccasionMaskIndex*: defines PRACH occasion(s) associated with
an SSB in which the MAC entity may transmit a Random Access Preamble
(see clause 7.4);

\- *msgA-SSB-SharedRO-MaskIndex*: Indicates the subset of 4-step RA type
PRACH occasions shared with 2-step RA type PRACH occasions for each SSB.
If 2-step RA type PRACH occasions are shared with 4-step RA type PRACH
occasions and *msgA-SSB-SharedRO-MaskIndex* is not configured, then all
4-step RA type PRACH occasions are available for 2-step RA type (see
clause 7.4);

\- *ssb-SharedRO-MaskIndex*: defines PRACH occasions, on which preambles
are allocated for a feature or a combination of features, associated
with an SSB in which the MAC entity may transmit a Random Access
Preamble (see clause 7.4);

\- *ra-OccasionList*: defines PRACH occasion(s) associated with a CSI-RS
in which the MAC entity may transmit a Random Access Preamble;

\- *ra-PreambleStartIndex*: the starting index of Random Access
Preamble(s) for on-demand SI request;

\- *startPreambleForThisPartition*: the first preamble associated with
the set of Random Access Resources applicable to the Random Access
procedure;

\- *preambleTransMax*: the maximum number of Random Access Preamble
transmission;

\- *preambleTransMax-Msg1-Repetition*: the maximum number of Random
Access Preamble transmissions with a given Msg1 repetition number before
switching to Msg1 repetition with the next available higher Msg1
repetition number;

\- *ssb-perRACH-OccasionAndCB-PreamblesPerSSB*: defines the number of
SSBs mapped to each PRACH occasion for 4-step RA type and the number of
contention-based Random Access Preambles mapped to each SSB;

\- *msgA-CB-PreamblesPerSSB-PerSharedRO*: defines the number of
contention-based Random Access Preambles for 2-step RA type mapped to
each SSB when the PRACH occasions are shared between 2-step and 4-step
RA types;

\- *msgA-SSB-PerRACH-OccasionAndCB-PreamblesPerSSB*: defines the number
of SSBs mapped to each PRACH occasion for 2-step RA type and the number
of contention-based Random Access Preambles mapped to each SSB;

\- *numberOfPreamblesPerSSB-ForThisPartition*: defines the number of
consecutive preambles for a feature or a combination of features mapped
to each SSB;

\- *msgA-PUSCH-ResourceGroupA*: defines MSGA PUSCH resources that the UE
shall use when performing MSGA transmission using Random Access
Preambles group A;

\- *msgA-PUSCH-ResourceGroupB*: defines MSGA PUSCH resources that the UE
shall use when performing MSGA transmission using Random Access
Preambles group B;

\- *msgA-PUSCH-Resource-Index*: identifies the index of the PUSCH
resource used for MSGA in case of contention-free Random Access with
2-step RA type;

\- if *groupBconfigured* is configured, then Random Access Preambles
group B is configured for 4-step RA type.

\- Amongst the contention-based Random Access Preambles associated with
an SSB (as defined in TS 38.213 \[6\]), the first
*numberOfRA-PreamblesGroupA* included in *groupBconfigured* Random
Access Preambles belong to Random Access Preambles group A. The
remaining Random Access Preambles associated with the SSB belong to
Random Access Preambles group B (if configured).

\- if *groupB-ConfiguredTwoStepRA* is configured, then Random Access
Preambles group B is configured for 2-step RA type.

\- Amongst the contention-based Random Access Preambles for 2-step RA
type associated with an SSB (as defined in TS 38.213 \[6\]), the first
*numberOfRA-PreamblesGroupA* included in *GroupB-ConfiguredTwoStepRA*
Random Access Preambles belong to Random Access Preambles group A. The
remaining Random Access Preambles associated with the SSB belong to
Random Access Preambles group B (if configured).

NOTE 3: If Random Access Preambles group B is supported by the cell
Random Access Preambles group B is included for each SSB.

\- if Random Access Preambles group B is configured for 4-step RA type:

\- *ra-Msg3SizeGroupA*: the threshold to determine the groups of Random
Access Preambles for 4-step RA type;

\- *msg3-DeltaPreamble*: ∆*~PREAMBLE_Msg3~* in TS 38.213 \[6\];

\- *messagePowerOffsetGroupB*: the power offset for preamble selection
included in *groupBconfigured*;

\- *numberOfRA-PreamblesGroupA*: defines the number of Random Access
Preambles in Random Access Preamble group A for each SSB included in
*groupBconfigured*.

\- if Random Access Preambles group B is configured for 2-step RA type:

\- *msgA-DeltaPreamble*: ∆*~MsgA_PUSCH~* in TS 38.213 \[6\];

\- *messagePowerOffsetGroupB*: the power offset for preamble selection
included in *GroupB-ConfiguredTwoStepRA*;

\- *numberOfRA-PreamblesGroupA*: defines the number of Random Access
Preambles in Random Access Preamble group A for each SSB included in
*GroupB-ConfiguredTwoStepRA*;

\- *ra-MsgA-SizeGroupA*: the threshold to determine the groups of Random
Access Preambles for 2-step RA type.

\- the set of Random Access Preambles and/or PRACH occasions for SI
request, if any;

\- the set of Random Access Preambles and/or PRACH occasions for beam
failure recovery request, if any;

\- the set of Random Access Preambles and/or PRACH occasions for
reconfiguration with sync, if any;

\- *ra-ResponseWindow*: the time window to monitor RA response(s)
(SpCell only);

\- *ra-ContentionResolutionTimer*: the Contention Resolution Timer
(SpCell only);

\- *msgB-ResponseWindow*: the time window to monitor RA response(s) for
2-step RA type (SpCell only).

In addition, the following information for related Serving Cell is
assumed to be available for UEs:

\- if Random Access Preambles group B is configured:

\- if the Serving Cell for the Random Access procedure is configured
with supplementary uplink as specified in TS 38.331 \[5\], and SUL
carrier is selected for performing Random Access Procedure:

\- P~CMAX,f,c~ of the SUL carrier as specified in TS 38.101-1 \[14\], TS
38.101-2 \[15\], and TS 38.101-3 \[16\].

\- else:

\- P~CMAX,f,c~ of the NUL carrier as specified in TS 38.101-1 \[14\], TS
38.101-2 \[15\], and TS 38.101-3 \[16\].

The following UE variables are used for the Random Access procedure:

\- *PREAMBLE_INDEX*;

\- *PREAMBLE_TRANSMISSION_COUNTER*;

\- *PREAMBLE_POWER_RAMPING_COUNTER*;

\- *PREAMBLE_POWER_RAMPING_STEP*;

\- *PREAMBLE_RECEIVED_TARGET_POWER*;

\- *PREAMBLE_BACKOFF*;

\- *PCMAX*;

\- *SCALING_FACTOR_BI*;

\- *TEMPORARY_C-RNTI*;

\- *RA_TYPE*;

\- *POWER_OFFSET_2STEP_RA*;

\- *MSGA_PREAMBLE_POWER_RAMPING_STEP*.

When the Random Access procedure is initiated on a Serving Cell or for
an LTM candidate cell, the MAC entity shall:

1\> flush the Msg3 buffer;

1\> flush the MSGA buffer;

1\> set the *PREAMBLE_TRANSMISSION_COUNTER* to 1;

1\> if the Random Access procedure is initiated on a Serving Cell; or

1\> if the Random Access procedure is initiated by the PDCCH order for
an LTM candidate cell and the PDCCH order indicates preamble initial
transmission; or

1\> if the Random Access procedure is initiated by the PDCCH order for
an LTM candidate cell, which is different from the cell to which the UE
performed the last Random Access Preamble transmission, and the PDCCH
order indicates preamble re-transmission:

2\> set the *PREAMBLE_POWER_RAMPING_COUNTER* to 1;

1\> set the *PREAMBLE_BACKOFF* to 0 ms;

1\> set *POWER_OFFSET_2STEP_RA* to 0 dB;

1\> if the carrier to use for the Random Access procedure is explicitly
signalled:

2\> select the signalled carrier for performing Random Access procedure;

2\> set the *PCMAX* to P~CMAX,f,c~ of the signalled carrier.

1\> else if the carrier to use for the Random Access procedure is not
explicitly signalled; and

1\> if the Serving Cell for the Random Access procedure is configured
with supplementary uplink as specified in TS 38.331 \[5\]; and

1\> if the RSRP of the downlink pathloss reference is less than
*rsrp-ThresholdSSB-SUL*:

2\> select the SUL carrier for performing Random Access procedure;

2\> set the *PCMAX* to P~CMAX,f,c~ of the SUL carrier.

1\> else:

2\> select the NUL carrier for performing Random Access procedure;

2\> set the *PCMAX* to P~CMAX,f,c~ of the NUL carrier.

NOTE 4: Void.

1\> perform the BWP operation as specified in clause 5.15, except when
the Random Access procedure is initiated by the PDCCH order for an LTM
candidate cell;

1\> select the set of Random Access resources applicable to the current
Random Access procedure according to clause 5.1.1b;

1\> if the Random Access procedure is initiated by PDCCH order and if
the *ra-PreambleIndex* explicitly provided by PDCCH is not 0b000000; or

1\> if the Random Access procedure was initiated for SI request (as
specified in TS 38.331 \[5\]) and the Random Access Resources for SI
request have been explicitly provided by RRC; or

1\> if the Random Access procedure was initiated for SpCell beam failure
recovery (as specified in clause 5.17) and if the contention-free Random
Access Resources for beam failure recovery request for 4-step RA type
have been explicitly provided by RRC for the BWP selected for Random
Access procedure; or

1\> if the Random Access procedure was initiated for reconfiguration
with sync not initiated for recovery using an LTM candidate
configuration as specified in TS 38.331 \[5\] clause 5.3.7.3 and if the
contention-free Random Access Resources for 4-step RA type have been
explicitly provided in *rach-ConfigDedicated* for the BWP selected for
Random Access procedure; or

1\> if the contention-free Random Access Resources have been explicitly
provided in the LTM Cell Switch Command MAC CE:

2\> set the *RA_TYPE* to *4-stepRA*.

1\> else if the BWP selected for Random Access procedure is configured
with both 2-step and 4-step RA type Random Access Resources within the
selected set of Random Access resources (as specified in clause 5.1.1b)
and the RSRP of the downlink pathloss reference is above
*msgA-RSRP-Threshold*; or

1\> if the BWP selected for Random Access procedure is only configured
with 2-step RA type Random Access resources within the selected set of
Random Access resources according to clause 5.1.1b; or

1\> if the Random Access procedure was initiated for reconfiguration
with sync not initiated for recovery using an LTM candidate
configuration as specified in TS 38.331 \[5\] clause 5.3.7.3 and if the
contention-free Random Access Resources for 2-step RA type have been
explicitly provided in *rach-ConfigDedicated* for the BWP selected for
Random Access procedure:

2\> set the *RA_TYPE* to *2-stepRA*.

1\> else:

2\> set the *RA_TYPE* to *4-stepRA*.

1\> perform initialization of variables specific to Random Access type
as specified in clause 5.1.1a;

1\> if *RA_TYPE* is set to *2-stepRA*:

2\> perform the Random Access Resource selection procedure for 2-step RA
type (see clause 5.1.2a).

1\> else:

2\> perform the Random Access Resource selection procedure (see clause
5.1.2).