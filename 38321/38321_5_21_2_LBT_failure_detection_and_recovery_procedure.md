### 5.21.2 LBT failure detection and recovery procedure

The MAC entity may be configured by RRC with a consistent LBT failure
recovery procedure. Consistent LBT failure is detected per UL BWP by
counting LBT failure indications, for all UL transmissions, from the
lower layers to the MAC entity.

RRC configures the following parameters in the
*lbt-FailureRecoveryConfig*:

\- *lbt-FailureInstanceMaxCount* for the consistent LBT failure
detection;

\- *lbt-FailureDetectionTimer* for the consistent LBT failure detection;

The following UE variable is used for the consistent LBT failure
detection procedure:

\- *LBT_COUNTER* (per Serving Cell): counter for LBT failure indication
which is initially set to 0.

For each activated Serving Cell configured with
*lbt-FailureRecoveryConfig*, the MAC entity shall:

1\> if LBT failure indication has been received from lower layers:

2\> start or restart the *lbt-FailureDetectionTimer*;

2\> increment *LBT_COUNTER* by 1;

2\> if *LBT_COUNTER* \>= *lbt-FailureInstanceMaxCount*:

3\> trigger consistent LBT failure for the active UL BWP in this Serving
Cell;

3\> if this Serving Cell is the SpCell:

4\> if consistent LBT failure has been triggered in all UL BWPs
configured with PRACH occasions on same carrier in this Serving Cell:

5\> indicate consistent LBT failure to upper layers.

4\> else:

5\> stop any ongoing Random Access procedure in this Serving Cell;

5\> switch the active UL BWP to a UL BWP, on same carrier in this
Serving Cell, configured with PRACH occasion and for which consistent
LBT failure has not been triggered;

5\> initiate a Random Access Procedure (as specified in clause 5.1.1).

1\> if all triggered consistent LBT failures are cancelled in this
Serving Cell; or

1\> if the *lbt-FailureDetectionTimer* expires; or

1\> if *lbt-FailureDetectionTimer* or *lbt-FailureInstanceMaxCount* is
reconfigured by upper layers:

2\> set *LBT_COUNTER* to 0.

The MAC entity shall:

1\> if consistent LBT failure has been triggered, and not cancelled, in
the SpCell; and

1\> if UL-SCH resources are available for a new transmission in the
SpCell and these UL-SCH resources can accommodate the LBT failure MAC CE
plus its subheader as a result of logical channel prioritization:

2\> instruct the Multiplexing and Assembly procedure to generate the LBT
failure MAC CE.

1\> else if consistent LBT failure has been triggered, and not
cancelled, in at least one SCell:

2\> if UL-SCH resources are available for a new transmission in a
Serving Cell for which consistent LBT failure has not been triggered and
these UL-SCH resources can accommodate the LBT failure MAC CE plus its
subheader as a result of logical channel prioritization:

3\> instruct the Multiplexing and Assembly procedure to generate the LBT
failure MAC CE.

2\> else:

3\> trigger a Scheduling Request for LBT failure MAC CE.

1\> if a MAC PDU is transmitted and LBT failure indication is not
received from lower layers and this PDU includes the LBT failure MAC CE:

2\> cancel all the triggered consistent LBT failure(s) in SCell(s) for
which consistent LBT failure was indicated in the transmitted LBT
failure MAC CE.

1\> if consistent LBT failure is triggered and not cancelled in the
SpCell; and

1\> if the Random Access procedure is considered successfully completed
(see clause 5.1) in the SpCell:

2\> cancel all the triggered consistent LBT failure(s) in the SpCell.

1\> if *lbt-FailureRecoveryConfig* is reconfigured by upper layers for a
Serving Cell:

2\> cancel all the triggered consistent LBT failure(s) in this Serving
Cell.