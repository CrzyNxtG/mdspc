### 5.1.2 Random Access Resource selection

If the selected *RA_TYPE* is set to *4-stepRA*, the MAC entity shall:

1\> if the Random Access procedure was initiated for SpCell beam failure
recovery (as specified in clause 5.17); and

1\> if the *beamFailureRecoveryTimer* (in clause 5.17) is either running
or not configured; and

1\> if the contention-free Random Access Resources for beam failure
recovery request associated with any of the SSBs and/or CSI-RSs have
been explicitly provided by RRC; and

1\> if at least one of the SSBs with SS-RSRP above *rsrp-ThresholdSSB*
amongst the SSBs in *candidateBeamRSList* or the CSI-RSs with CSI-RSRP
above *rsrp-ThresholdCSI-RS* amongst the CSI-RSs in
*candidateBeamRSList* is available:

2\> select an SSB with SS-RSRP above *rsrp-ThresholdSSB* amongst the
SSBs in *candidateBeamRSList* or a CSI-RS with CSI-RSRP above
*rsrp-ThresholdCSI-RS* amongst the CSI-RSs in *candidateBeamRSList*;

2\> if CSI-RS is selected, and there is no *ra-PreambleIndex* associated
with the selected CSI-RS:

3\> set the *PREAMBLE_INDEX* to a *ra-PreambleIndex* corresponding to
the SSB in *candidateBeamRSList* which is quasi-colocated with the
selected CSI-RS as specified in TS 38.214 \[7\].

2\> else:

3\> set the *PREAMBLE_INDEX* to a *ra-PreambleIndex* corresponding to
the selected SSB or CSI-RS from the set of Random Access Preambles for
beam failure recovery request.

1\> else if the *ra-PreambleIndex* has been explicitly provided by
PDCCH; and

1\> if the *ra-PreambleIndex* is not 0b000000:

2\> set the *PREAMBLE_INDEX* to the signalled *ra-PreambleIndex*;

2\> select the SSB signalled by PDCCH.

1\> else if contention-free Random Access Resources have been explicitly
provided by an LTM Cell Switch Command MAC CE and the SS-RSRP of the SSB
signalled by the LTM Cell Switch Command MAC CE is above
*rsrp-ThresholdSSB*:

2\> set the *PREAMBLE_INDEX* to the Random Access Preamble index
signalled by the LTM Cell Switch Command MAC CE;

2\> select the SSB signalled by the LTM Cell Switch Command MAC CE.

1\> else if contention-free Random Access Resources have not been
explicitly provided by an LTM Cell Switch Command MAC CE, the Random
Access procedure was not initiated for recovery using an LTM candidate
configuration as specified in TS 38.331 \[5\] clause 5.3.7.3,
contention-free Random Access Resources associated with SSBs have been
explicitly provided in *rach-ConfigDedicated* and at least one SSB with
SS-RSRP above *rsrp-ThresholdSSB* amongst the associated SSBs is
available:

2\> select an SSB with SS-RSRP above *rsrp-ThresholdSSB* amongst the
associated SSBs;

2\> set the *PREAMBLE_INDEX* to a *ra-PreambleIndex* corresponding to
the selected SSB.

1\> else if contention-free Random Access Resources have not been
explicitly provided by an LTM Cell Switch Command MAC CE, the Random
Access procedure was not initiated for recovery using an LTM candidate
configuration as specified in TS 38.331 \[5\] clause 5.3.7.3,
contention-free Random Access Resources associated with CSI-RSs have
been explicitly provided in *rach-ConfigDedicated* and at least one
CSI-RS with CSI-RSRP above *rsrp-ThresholdCSI-RS* amongst the associated
CSI-RSs is available:

2\> select a CSI-RS with CSI-RSRP above *rsrp-ThresholdCSI-RS* amongst
the associated CSI-RSs;

2\> set the *PREAMBLE_INDEX* to a *ra-PreambleIndex* corresponding to
the selected CSI-RS.

1\> else if the Random Access procedure was initiated for SI request (as
specified in TS 38.331 \[5\]); and

1\> if the Random Access Resources for SI request have been explicitly
provided by RRC:

2\> if at least one of the SSBs with SS-RSRP above *rsrp-ThresholdSSB*
is available:

3\> select an SSB with SS-RSRP above *rsrp-ThresholdSSB*.

2\> else:

3\> select any SSB.

2\> select a Random Access Preamble corresponding to the selected SSB,
from the Random Access Preamble(s) determined according to
*ra-PreambleStartIndex* as specified in TS 38.331 \[5\];

2\> set the *PREAMBLE_INDEX* to selected Random Access Preamble.

1\> else (i.e. for the contention-based Random Access preamble
selection):

2\> if at least one of the SSBs with SS-RSRP above *rsrp-ThresholdSSB*
is available:

3\> select an SSB with SS-RSRP above *rsrp-ThresholdSSB*.

2\> else:

3\> select any SSB.

2\> if the *RA_TYPE* is switched from *2-stepRA* to *4-stepRA*:

3\> if a Random Access Preambles group was selected during the current
Random Access procedure:

4\> select the same group of Random Access Preambles as was selected for
the 2-step RA type.

3\> else:

4\> if Random Access Preambles group B is configured; and

4\> if the transport block size of the MSGA payload configured in the
*rach-ConfigDedicated* corresponds to the transport block size of the
MSGA payload associated with Random Access Preambles group B:

5\> select the Random Access Preambles group B.

4\> else:

5\> select the Random Access Preambles group A.

2\> else if Msg3 buffer is empty:

3\> if Random Access Preambles group B is configured:

4\> if the potential Msg3 size (UL data available for transmission plus
MAC subheader(s) and, where required, MAC CEs) is greater than
*ra-Msg3SizeGroupA* and the pathloss is less than *PCMAX* (of the
Serving Cell performing the Random Access Procedure) --
*preambleReceivedTargetPower* -- *msg3-DeltaPreamble* --
*messagePowerOffsetGroupB*; or

4\> if the Random Access procedure was initiated for the CCCH logical
channel and the CCCH SDU size plus MAC subheader is greater than
*ra-Msg3SizeGroupA*:

5\> select the Random Access Preambles group B.

4\> else:

5\> select the Random Access Preambles group A.

3\> else:

4\> select the Random Access Preambles group A.

2\> else (i.e. Msg3 is being retransmitted):

3\> select the same group of Random Access Preambles as was used for the
Random Access Preamble transmission attempt corresponding to the first
transmission of Msg3.

2\> select a Random Access Preamble randomly with equal probability from
the Random Access Preambles associated with the selected SSB and the
selected Random Access Preambles group;

2\> set the *PREAMBLE_INDEX* to the selected Random Access Preamble.

1\> if the Random Access procedure was initiated for SI request (as
specified in TS 38.331 \[5\]); and

1\> if *ra-AssociationPeriodIndex* and *si-RequestPeriod* are
configured:

2\> determine the next available PRACH occasion from the PRACH occasions
corresponding to the selected SSB in the association period given by
*ra-AssociationPeriodIndex* in the *si-RequestPeriod* permitted by the
restrictions given by the *ra-ssb-OccasionMaskIndex* if configured (the
MAC entity shall select a PRACH occasion randomly with equal probability
amongst the consecutive PRACH occasions according to clause 8.1 of TS
38.213 \[6\] corresponding to the selected SSB).

1\> else if an SSB is selected above:

2\> if the set of Random Access resources associated with Msg1
repetition is selected for this Random Access procedure:

3\> determine the next available set of PRACH occasions (as specified in
TS 38.213 \[6\]) for the Msg1 repetition number applicable for this
Random Access procedure corresponding to the selected SSB (the MAC
entity shall select a set of PRACH occasions randomly with equal
probability amongst sets of PRACH occasions according to clause 8.1 of
TS 38.213 \[6\] regardless the FR2 UL gap, corresponding to the selected
SSB and selected Msg1 repetition number for this Random Access
procedure; the MAC entity may take into account the possible occurrence
of measurement gaps and MUSIM gaps when determining the next available
set of PRACH occasions corresponding to the selected SSB).

2\> else:

3\> determine the next available PRACH occasion from the PRACH occasions
corresponding to the selected SSB permitted by the restrictions given by
the *ra-ssb-OccasionMaskIndex* if configured, or
*ssb-SharedRO-MaskIndex* if configured, or indicated by PDCCH, or
indicated by the LTM Cell Switch Command MAC CE (the MAC entity shall
select a PRACH occasion randomly with equal probability amongst the
consecutive PRACH occasions according to clause 8.1 of TS 38.213 \[6\]
regardless the FR2 UL gap, corresponding to the selected SSB; the MAC
entity may take into account the possible occurrence of measurement gaps
and MUSIM gaps when determining the next available PRACH occasion
corresponding to the selected SSB).

1\> else if a CSI-RS is selected above:

2\> if there is no contention-free Random Access Resource associated
with the selected CSI-RS:

3\> determine the next available PRACH occasion from the PRACH
occasions, permitted by the restrictions given by the
*ra-ssb-OccasionMaskIndex* if configured, corresponding to the SSB in
*candidateBeamRSList* which is quasi-colocated with the selected CSI-RS
as specified in TS 38.214 \[7\] (the MAC entity shall select a PRACH
occasion randomly with equal probability amongst the consecutive PRACH
occasions according to clause 8.1 of TS 38.213 \[6\] regardless the FR2
UL gap, corresponding to the SSB which is quasi-colocated with the
selected CSI-RS; the MAC entity may take into account the possible
occurrence of measurement gaps and MUSIM gaps when determining the next
available PRACH occasion corresponding to the SSB which is
quasi-colocated with the selected CSI-RS).

2\> else:

3\> determine the next available PRACH occasion from the PRACH occasions
in *ra-OccasionList* corresponding to the selected CSI-RS (the MAC
entity shall select a PRACH occasion randomly with equal probability
amongst the PRACH occasions occurring simultaneously but on different
subcarriers regardless the FR2 UL gap, corresponding to the selected
CSI-RS; the MAC entity may take into account the possible occurrence of
measurement gaps and MUSIM gaps when determining the next available
PRACH occasion corresponding to the selected CSI-RS).

1\> perform the Random Access Preamble transmission procedure (see
clause 5.1.3).

NOTE 1: When the UE determines if there is an SSB with SS-RSRP above
*rsrp-ThresholdSSB* or a CSI-RS with CSI-RSRP above
*rsrp-ThresholdCSI-RS*, the UE uses the latest unfiltered L1-RSRP
measurement.

NOTE 2: Void.

NOTE 3: If an (e)RedCap UE in RRC_IDLE or RRC_INACTIVE mode is
configured with a BWP indicated by *initialDownlinkBWP-RedCap* which is
not associated with any SSB, SS-RSRP measurement is performed based on
the SSB associated with the BWP indicated by *initialDownlinkBWP*. If an
(e)RedCap UE in RRC_INACTIVE mode is configured with SDT and with a BWP
indicated by *initialDownlinkBWP-RedCap* which is associated with
NCD-SSB, SS-RSRP measurement can also be performed based on this NCD-SSB
during SDT.

NOTE 4: If an (e)RedCap UE in RRC_IDLE or RRC_INACTIVE mode is
configured with a BWP indicated by *initialDownlinkBWP-RedCap* which is
not associated with any SSB for RACH, it is up to the UE implementation
to perform a new RSRP measurements before Msg1/MsgA retransmission.