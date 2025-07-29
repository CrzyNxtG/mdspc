### 5.18.30 Case-6 Timing Request

The Case-6 Timing Request MAC CE is used by the IAB-MT to inform its
parent node whether Case-6 timing is required for simultaneous
operation.

The MAC entity may:

1\> if a Case-6 Timing Request query has not been triggered:

2\> trigger a Case-6 Timing Request query for this Serving Cell.

If the MAC entity has UL resources allocated for new transmission the
MAC entity shall:

1\> for each Case-6 Timing Request query that has been triggered and not
cancelled:

2\> if the allocated UL resources can accommodate a Case-6 Timing
Request MAC CE plus its subheader as a result of LCP as defined in
clause 5.4.3.1:

3\> instruct the Multiplexing and Assembly procedure to generate the
Case-6 Timing Request MAC CE;

3\> cancel this Case-6 Timing Request range query.