### 5.1.1e Selection of Msg1 repetition for SI request

The MAC entity shall:

1\> if *si-RequestResourcesRepetitionNum8* is configured and the RSRP of
the downlink pathloss reference is less than
*rsrp-ThresholdMsg1-RepetitionNum8*:

2\> criteria to apply Msg1 repetition for SI request is considered met
and Msg1 repetition number applicable is 8.

1\> else if *si-RequestResourcesRepetitionNum4* is configured and the
RSRP of the downlink pathloss reference is less than
*rsrp-ThresholdMsg1-RepetitionNum4*:

2\> criteria to apply Msg1 repetition for SI request is considered met
and Msg1 repetition number applicable is 4.

1\> else if *si-RequestResourcesRepetitionNum2* is configured and the
RSRP of the downlink pathloss reference is less than
*rsrp-ThresholdMsg1-RepetitionNum2*:

2\> criteria to apply Msg1 repetition for SI request is considered met
and Msg1 repetition number applicable is 2.

1\> else:

2\> criteria to apply Msg1 repetition for SI request is considered not
met.