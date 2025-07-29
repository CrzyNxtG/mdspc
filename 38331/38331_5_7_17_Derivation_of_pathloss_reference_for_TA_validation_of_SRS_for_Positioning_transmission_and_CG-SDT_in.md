### 5.7.17 Derivation of pathloss reference for TA validation of SRS for Positioning transmission and CG-SDT in RRC_INACTIVE

Upon request from lower layer for pathloss reference derivation for TA
validation for SRS for Positioning transmission or CG-SDT in
RRC_INACTIVE, the UE shall:

1\> acquire *SIB2,* if stored version is invalid;

1\> if *nrofSS-BlocksToAverage* or *absThreshSS-BlocksConsolidation* is
not present or if a*bsThreshSS-BlocksConsolidation* is present and the
highest beam measurement quantity value is below or equal to
*absThreshSS-BlocksConsolidation*:

2\> derive the downlink pathloss reference RSRP for TA validation as the
highest beam measurement quantity value, where each beam measurement
quantity is described in TS 38.215 \[24\];

1\> else:

2\> derive the downlink pathloss reference RSRP for TA validation as the
linear average of the power values of up to *nrofSS-BlocksToAverage* of
the highest beam measurement quantity values above
*absThreshSS-BlocksConsolidation*, where each beam measurement quantity
is described in TS 38.215 \[24\].

NOTE: If the UE is configured with multiple SSB configurations, the
downlink pathloss reference RSRP for TA validation is derived from the
SSB configured by *SIB1*.