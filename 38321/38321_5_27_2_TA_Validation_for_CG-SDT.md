### 5.27.2 TA Validation for CG-SDT

RRC configures the following parameters for TA validation for CG-SDT:

*- cg-SDT-RSRP-ChangeThreshold*: RSRP threshold for the
increase/decrease of RSRP for time alignment validation.

The MAC entity shall, upon the reception of CG-SDT configuration:

1\> store the current RSRP of the downlink pathloss reference for TA
validation as defined in TS 38.331 \[5\] clause 5.7.17.

The MAC entity shall consider the TA of the initial CG-SDT transmission
with CCCH message to be valid when the following conditions are
fulfilled:

1\> The RSRP values for the stored downlink pathloss reference and the
current downlink pathloss reference are valid according to TS 38.133
\[11\]; and

1\> Compared to the stored downlink pathloss reference RSRP value, the
current RSRP value of the downlink pathloss reference calculated as
specified in TS 38.133 \[11\] has not increased/decreased by more than
*cg-SDT-RSRP-ChangeThreshold*, if configured; and

1\> *cg-SDT-TimeAlignmentTimer* is running.