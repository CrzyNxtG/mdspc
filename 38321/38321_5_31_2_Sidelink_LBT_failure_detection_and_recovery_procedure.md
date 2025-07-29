### 5.31.2 Sidelink LBT failure detection and recovery procedure

The MAC entity may be configured by RRC with a Sidelink consistent LBT
failure detection and recovery procedure. Sidelink consistent LBT
failure is detected per RB set by counting SL LBT failure indications,
for all SL transmissions, from the lower layers to the MAC entity.

RRC configures the following parameters in the
*sl-LBT-FailureRecoveryConfig*:

\- *sl-LBT-FailureInstanceMaxCount* for the Sidelink consistent LBT
failure detection;

\- *sl-LBT-FailureDetectionTimer* for the Sidelink consistent LBT
failure detection;

*- sl-LBT-RecoveryTimer* for recovery of the triggered Sidelink
consistent LBT failure.

The following UE variable is used for the Sidelink consistent LBT
failure detection procedure:

\- *SL_LBT_COUNTER* (per RB set): counter for SL LBT failure indication
which is initially set to 0.

For activated SL BWP configured with *sl-LBT-FailureRecoveryConfig*, the
MAC entity shall:

1\> if SL LBT failure indication has been received from lower layers for
an RB set of the configured pool(s) of resources in the SL BWP:

2\> start or restart the *sl-LBT-FailureDetectionTimer* for the RB set;

2\> increment *SL_LBT_COUNTER* for the RB set by 1;

2\> if *SL_LBT_COUNTER* \>= *sl-LBT-FailureInstanceMaxCount*:

3\> trigger Sidelink consistent LBT failure for the RB set in the SL
BWP;

3\> if consistent LBT failure has been triggered in all the RB sets of
the configured pool(s) of resources in the SL BWP:

4\> indicate Sidelink consistent LBT failure based Sidelink RLF
detection for all destination IDs associated to unicast service to upper
layers.

1\> if all triggered Sidelink consistent LBT failures are cancelled in a
RB set; or

1\> if the *sl-LBT-FailureDetectionTimer* expires for a RB set:

2\> set *SL_LBT_COUNTER* to 0 for the RB set.

1\> if *sl-LBT-FailureDetectionTimer* or
*sl-LBT-FailureInstanceMaxCount* is reconfigured by upper layers:

2\> set *SL_LBT_COUNTER* to 0 for all the RB sets.

The *sl-LBT-RecoveryTimer* is used for recovery of the triggered
Sidelink consistent LBT failure, when RRC configures Sidelink resource
allocation mode 2.

The MAC entity shall:

1\> if Sidelink consistent LBT failure has been triggered, and not
cancelled, in the RB set(s), and SL LBT failure MAC CE for the triggered
Sidelink consistent LBT failure has not been generated;

2\> if the *sl-LBT-RecoveryTimer* for the triggered Sidelink consistent
LBT failure is not running:

3\> start the *sl-LBT-RecoveryTimer*.

2\> if UL-SCH resources are available for a new transmission and the
UL-SCH resources can accommodate the SL LBT failure MAC CE plus its
subheader as a result of logical channel prioritization according to
clause 5.4.3.1:

3\> instruct the Multiplexing and Assembly procedure in clause 5.4.3 to
generate the SL LBT failure MAC CE.

2\> else:

3\> trigger a Scheduling Request for SL LBT failure MAC CE.

1\> if a MAC PDU is transmitted and this PDU includes the SL LBT failure
MAC CE:

2\> cancel the triggered Sidelink consistent LBT failure(s) in RB set(s)
for which Sidelink consistent LBT failure was indicated in the
transmitted SL LBT failure MAC CE if the MAC entity has been configured
with Sidelink resource allocation mode 1.

1\> if the *sl-LBT-RecoveryTimer* for the triggered Sidelink consistent
LBT failure(s) expires:

2\> cancel the triggered Sidelink consistent LBT failure(s) in RB set(s)
for which Sidelink consistent LBT failure was detected.

1\> if *sl-LBT-FailureRecoveryConfig* is reconfigured by upper layers
for the BWP:

2\> cancel all the triggered Sidelink consistent LBT failure(s) in the
SL BWP.