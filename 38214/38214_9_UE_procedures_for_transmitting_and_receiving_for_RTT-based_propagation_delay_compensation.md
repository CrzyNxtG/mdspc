# 9 UE procedures for transmitting and receiving for RTT-based propagation delay compensation

For operation with RTT-based propagation delay compensation, the UE may
be configured with either:

\- one CSI-RS for tracking with higher layer parameter *pdc-Info* for Rx
-- Tx time difference estimation at UE side and one SRS resource set
with *usage-PDC*, or

\- one PRS configuration of higher layer parameter
*nr-DL-PRS-PDC-ResourceSet* \[12, TS 38.331\] for Rx -- Tx time
difference estimation at UE side and one SRS resource set with
*usage-PDC*.

The related UE procedures for transmitting uplink reference signals and
receiving downlink reference signals for RTT-based propagation delay
compensation are defined as follows:

\- for reception of CSI-RS for tracking with higher layer parameter
*pdc-Info*, the UE follows the procedures for reception of CSI-RS for
tracking defined in Clause 5.1.6.1.1.

\- for reception of the one PRS configuration provided by RRC \[12, TS
38.331\] for RTT-based propagation delay compensation, the UE follows
the procedure for PRS reception for RTT-based propagation delay
compensation defined in Clause 9.1*.*

\- for transmission of an SRS resource set configured with *usage-PDC*,
the UE follows the procedures for SRS transmission defined in Clause
6.2.1.