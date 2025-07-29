### 5.26.2 TA validation for SRS transmission in RRC_INACTIVE

RRC configures the following parameters for validation for SRS
transmission in RRC_INACTIVE:

\- *inactivePosSRS-RSRP-ChangeThreshold*: RSRP threshold for the
increase/decrease of RSRP for time alignment validation;

\- *inactivePosSRS-ValidityAreaRSRP*: RSRP threshold for the
increase/decrease of RSRP for time alignment validation when SRS
positioning validity area is configured.

The MAC entity shall:

1\> if the UE receives configuration for SRS transmission in
RRC_INACTIVE:

2\> store the RSRP of the downlink pathloss reference with the current
RSRP value of the downlink pathloss reference as in TS 38.331 \[5\].

1\> else if the UE is configured with SRS transmission in RRC_INACTIVE:

2\> if Timing Advance Command MAC CE is received as in clause 5.2, or;

2\> if Timing Advance Command or Absolute Timing Advance Command is
received for Random Access procedure that is successfully completed:

3\> update the stored the RSRP of the downlink pathloss reference with
the current RSRP value of the downlink pathloss reference.

2\> if the UE is configured Positioning with SRS with validity area and
the upper layer indicates the MAC to update the stored RSRP:

3\> update the RSRP of the downlink pathloss reference with the current
RSRP value of the downlink pathloss reference of the camped cell as
specified in TS 38.331 \[5\].

The MAC entity shall consider the TA to be valid when the following
conditions are fulfilled:

1\> compared to the stored downlink pathloss reference RSRP value, the
current RSRP value of the downlink pathloss reference of the camped cell
as specified in TS 38.331 \[5\] has not increased/decreased by more than
*inactivePosSRS-RSRP-ChangeThreshold*, if configured, or
*inactivePosSRS-ValidityAreaRSRP*, if configured, when SRS positioning
validity area is configured; and

1\> *inactivePosSRS-TimeAlignmentTimer* is running or
*inactivePosSRS-ValidityAreaTAT* is running when SRS positioning
validity area is configured.