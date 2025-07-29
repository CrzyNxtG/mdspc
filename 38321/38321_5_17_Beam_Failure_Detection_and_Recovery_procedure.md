## 5.17 Beam Failure Detection and Recovery procedure

The MAC entity may be configured by RRC per Serving Cell or per BFD-RS
set with a beam failure recovery procedure which is used for indicating
to the serving gNB of a new SSB or CSI-RS when beam failure is detected
on the serving SSB(s)/CSI-RS(s). Beam failure is detected by counting
beam failure instance indication from the lower layers to the MAC
entity. If *beamFailureRecoveryConfig* is reconfigured by upper layers
during an ongoing Random Access procedure for beam failure recovery for
SpCell, the MAC entity shall stop the ongoing Random Access procedure
and initiate a Random Access procedure using the new configuration. The
Serving Cell is configured with two BFD-RS sets if and only if
*failureDetectionSet1* and *failureDetectionSet2* are configured for the
active DL BWP of the Serving Cell. When the SCG is deactivated, the UE
performs beam failure detection on the PSCell if *bfd-and-RLM* is set to
*true*.

RRC configures the following parameters in the
*beamFailureRecoveryConfig*, *beamFailureRecoverySpCellConfig*,
*beamFailureRecoverySCellConfig* and the *radioLinkMonitoringConfig* for
the Beam Failure Detection and Recovery procedure:

\- *beamFailureInstanceMaxCount* for the beam failure detection (per
Serving Cell or per BFD-RS set of Serving Cell configured with two
BFD-RS sets);

\- *beamFailureDetectionTimer* for the beam failure detection (per
Serving Cell or per BFD-RS set of Serving Cell configured with two
BFD-RS sets);

\- *beamFailureRecoveryTimer* for the beam failure recovery procedure
for SpCell;

\- *rsrp-ThresholdSSB*: an RSRP threshold for the SpCell beam failure
recovery;

\- *rsrp-ThresholdBFR*: an RSRP threshold for the SCell beam failure
recovery or for the beam failure recovery of BFD-RS set of Serving Cell;

\- *powerRampingStep*: *powerRampingStep* for the SpCell beam failure
recovery;

\- *powerRampingStepHighPriority*: *powerRampingStepHighPriority* for
the SpCell beam failure recovery;

\- *preambleReceivedTargetPower*: *preambleReceivedTargetPower* for the
SpCell beam failure recovery;

\- *preambleTransMax*: *preambleTransMax* for the SpCell beam failure
recovery;

\- *scalingFactorBI*: *scalingFactorBI* for the SpCell beam failure
recovery;

\- *ssb-perRACH-Occasion*: *ssb-perRACH-Occasion* for the SpCell beam
failure recovery using contention-free Random Access Resources;

\- *ra-ResponseWindow*: the time window to monitor response(s) for the
SpCell beam failure recovery using contention-free Random Access
Resources;

\- *prach-ConfigurationIndex*: *prach-ConfigurationIndex* for the SpCell
beam failure recovery using contention-free Random Access Resources;

\- *ra-ssb-OccasionMaskIndex*: *ra-ssb-OccasionMaskIndex* for the SpCell
beam failure recovery using contention-free Random Access Resources;

\- *ra-OccasionList*: *ra-OccasionList* for the SpCell beam failure
recovery using contention-free Random Access Resources;

\- *candidateBeamRSList*: list of candidate beams for SpCell beam
failure recovery;

\- *candidateBeamRS-List-r16*: list of candidate beams for SCell beam
failure recovery or list of candidate beams for beam failure recovery of
a Serving Cell for BFD-RS set one;

\- *candidateBeamRS-List2-r17*: list of candidate beams for beam failure
recovery of a Serving Cell for BFD-RS set two.

The following UE variables are used for the beam failure detection
procedure:

\- *BFI_COUNTER* (per Serving Cell or per BFD-RS set of Serving Cell
configured with two BFD-RS sets): counter for beam failure instance
indication which is initially set to 0.

The MAC entity shall for each Serving Cell configured for beam failure
detection:

1\> if the Serving Cell is configured with two BFD-RS sets:

2\> if beam failure instance indication for a BFD-RS set has been
received from lower layers:

3\> start or restart the *beamFailureDetectionTimer* of the BFD-RS set;

3\> increment *BFI_COUNTER* of the BFD-RS set by 1;

3\> if *BFI_COUNTER* of the BFD-RS set \>=
*beamFailureInstanceMaxCount*:

4\> trigger a BFR for this BFD-RS set of the Serving Cell;

2\> if BFR is triggered for both BFD-RS sets of the SpCell and the Beam
Failure Recovery procedure is not successfully completed for any of the
BFD-RS sets:

3\> initiate a Random Access procedure (see clause 5.1) on the SpCell;

2\> if the Serving Cell is SpCell and the Random Access procedure
initiated for beam failure recovery of both BFD-RS sets of SpCell is
successfully completed (see clause 5.1):

3\> set *BFI_COUNTER* of each BFD-RS set of SpCell to 0.

3\> consider the Beam Failure Recovery procedure successfully completed.

2\> if the *beamFailureDetectionTimer* of a BFD-RS set expires; or

2\> if *beamFailureDetectionTimer*, *beamFailureInstanceMaxCount*, or
any of the reference signals used for beam failure detection is
reconfigured by upper layers or by the BFD-RS Indication MAC CE
associated with a BFD-RS set of the Serving Cell; or

2\> if the reference signal(s) associated with a BFD-RS set of the
Serving Cell used for beam failure detection is changed:

3\> set *BFI_COUNTER* of the BFD-RS set to 0.

2\> if a PDCCH addressed to C-RNTI indicating uplink grant for a new
transmission is received for the HARQ process used for the transmission
of the Enhanced BFR MAC CE or Truncated Enhanced BFR MAC CE which
contains beam failure recovery information of a BFD-RS set of the
Serving Cell:

3\> set *BFI_COUNTER* of the BFD-RS set to 0;

3\> consider the Beam Failure Recovery procedure successfully completed
for this BFD-RS set and cancel all the triggered BFRs of this BFD-RS set
of the Serving Cell.

2\> if the Serving Cell is SCell and the SCell is deactivated as
specified in clause 5.9:

3\> set *BFI_COUNTER* of each BFD-RS set of SCell to 0;

3\> consider the Beam Failure Recovery procedure successfully completed
and cancel all the triggered BFRs of all BFD-RS sets of the Serving
Cell.

1\> else:

2\> if beam failure instance indication has been received from lower
layers:

3\> start or restart the *beamFailureDetectionTimer*;

3\> increment *BFI_COUNTER* by 1;

3\> if *BFI_COUNTER* \>= *beamFailureInstanceMaxCount*:

4\> if the Serving Cell is SCell:

5\> trigger a BFR for this Serving Cell;

4\> else if the Serving Cell is PSCell and, the SCG is deactivated:

5\> if beam failure of the PSCell has not been indicated to upper layers
since the SCG was deactivated or since the deactivated SCG was last
reconfigured with BFD-RS:

6\> indicate beam failure of the PSCell to upper layers.

NOTE: After beam failure is indicated to upper layers, the UE may stop
the *beamFailureDetectionTimer* and lower layer beam failure indication
while *BFI_COUNTER* \>= *beamFailureInstanceMaxCount* for the
deactivated SCG.

4\> else:

5\> initiate a Random Access procedure (see clause 5.1) on the SpCell;

5\> if beam failure is detected for an NCR-MT:

6\> indicate to NCR-Fwd to cease forwarding.

2\> if the *beamFailureDetectionTimer* expires; or

> 2\> if *beamFailureDetectionTimer*, *beamFailureInstanceMaxCount*, or
> any of the reference signals used for beam failure detection is
> reconfigured by upper layers associated with this Serving Cell; or

2\> if the reference signal(s) associated with this Serving Cell used
for beam failure detection is changed:

3\> set *BFI_COUNTER* to 0.

2\> if the Serving Cell is SpCell and the Random Access procedure
initiated for SpCell beam failure recovery is successfully completed
(see clause 5.1):

3\> set *BFI_COUNTER* to 0;

3\> stop the *beamFailureRecoveryTimer*, if configured;

3\> if the Random Access procedure was triggered by beam failure
recovery for NCR-MT:

4\> indicate to NCR-Fwd to resume forwarding using the last forwarding
configuration received by NCR-MT as part of side control information
before beam failure detection;

3\> consider the Beam Failure Recovery procedure successfully completed.

2\> else if the Serving Cell is SCell, and a PDCCH addressed to C-RNTI
indicating uplink grant for a new transmission is received for the HARQ
process used for the transmission of the MAC CE for BFR which contains
beam failure recovery information of this Serving Cell; or

2\> if the SCell is deactivated as specified in clause 5.9:

3\> set *BFI_COUNTER* to 0;

3\> consider the Beam Failure Recovery procedure successfully completed
and cancel all the triggered BFRs for this Serving Cell.

The MAC entity shall:

1\> if the Beam Failure Recovery procedure determines that at least one
BFR has been triggered and not cancelled for an SCell for which
evaluation of the candidate beams according to the requirements as
specified in TS 38.133 \[11\] has been completed and if none of the
Serving Cell(s) of this MAC entity are configured with two BFD-RS sets:

2\> if UL-SCH resources are available for a new transmission and if the
UL-SCH resources can accommodate the BFR MAC CE plus its subheader as a
result of LCP:

3\> instruct the Multiplexing and Assembly procedure to generate the BFR
MAC CE.

2\> else if UL-SCH resources are available for a new transmission and if
the UL-SCH resources can accommodate the Truncated BFR MAC CE plus its
subheader as a result of LCP:

3\> instruct the Multiplexing and Assembly procedure to generate the
Truncated BFR MAC CE.

2\> else:

3\> trigger the SR for SCell beam failure recovery for each SCell for
which BFR has been triggered, not cancelled, and for which evaluation of
the candidate beams according to the requirements as specified in TS
38.133 \[11\] has been completed.

1\> if the Beam Failure Recovery procedure determines that at least one
BFR for any BFD-RS set has been triggered and not cancelled for an SCell
for which evaluation of the candidate beams according to the
requirements as specified in TS 38.133 \[11\] has been completed; or

1\> if the Beam Failure Recovery procedure determines that at least one
BFR for only one BFD-RS set has been triggered and not cancelled for an
SpCell for which evaluation of the candidate beams according to the
requirements as specified in TS 38.133 \[11\] has been completed; or

1\> if the Beam Failure Recovery procedure determines that at least one
BFR has been triggered and not cancelled for an SCell for which
evaluation of the candidate beams according to the requirements as
specified in TS 38.133 \[11\] has been completed and if at least one
Serving Cell of this MAC entity is configured with two BFD-RS sets:

2\> if UL-SCH resources are available for a new transmission and if the
UL-SCH resources can accommodate the Enhanced BFR MAC CE plus its
subheader as a result of LCP:

3\> instruct the Multiplexing and Assembly procedure to generate the
Enhanced BFR MAC CE.

2\> else if UL-SCH resources are available for a new transmission and if
the UL-SCH resources can accommodate the Truncated Enhanced BFR MAC CE
plus its subheader as a result of LCP:

3\> instruct the Multiplexing and Assembly procedure to generate the
Truncated Enhanced BFR MAC CE.

2\> else:

3\> trigger the SR for beam failure recovery of each BFD-RS set for
which BFR has been triggered, not cancelled, and for which evaluation of
the candidate beams according to the requirements as specified in TS
38.133 \[11\] has been completed;

3\> trigger the SR for SCell beam failure recovery for each SCell for
which BFR has been triggered, not cancelled, and for which evaluation of
the candidate beams according to the requirements as specified in TS
38.133 \[11\] has been completed.

All BFRs triggered for an SCell shall be cancelled when a MAC PDU is
transmitted and this PDU includes a MAC CE for BFR which contains beam
failure information of that SCell. All BFRs triggered for a BFD-RS set
of a Serving Cell shall be cancelled when a MAC PDU is transmitted and
this PDU includes an Enhanced BFR MAC CE or Truncated Enhanced BFR MAC
CE which contains beam failure recovery information of that BFD-RS set
of the Serving Cell.