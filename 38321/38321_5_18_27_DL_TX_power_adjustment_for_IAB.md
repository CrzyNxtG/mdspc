### 5.18.27 DL TX power adjustment for IAB

DL TX Power Adjustment MAC CE is used by an IAB-DU or an IAB-donor-DU to
indicate to its child node spatial resources and associated frequency
information where the DL TX power adjustment contained in the MAC CE
applies. Desired DL TX Power Adjustment MAC CE is used by an IAB-node to
indicate to its parent node recommendations for such a restriction. Time
resources where these restrictions/recommendations can apply are
indicated via RRC, while the MAC CE further selects from these time
resources the specific time resource configuration (comprising a list of
slot indices) to which information provided in the MAC CE applies.

Upon reception of a DL TX Power Adjustment MAC CE the IAB-node shall:

\- apply the configuration signalled in the MAC CE to the time slots
indicated in *IAB-ResourceConfig* (as specified in TS 38.331 \[5\])
which contains *iab-ResourceConfigID* parameter which matches the
Resource Configuration ID field of the MAC CE.

The MAC entity may:

1\> if a Desired DL TX Power Adjustment query has not been triggered:

2\> trigger a Desired DL TX Power Adjustment query for this Serving
Cell.

If the MAC entity has UL resources allocated for new transmission the
MAC entity shall:

1\> for each Desired DL TX Power Adjustment query that has been
triggered and not cancelled:

2\> if the allocated UL resources can accommodate a Desired DL TX Power
Adjustment MAC CE plus its subheader as a result of LCP as defined in
clause 5.4.3.1:

3\> instruct the Multiplexing and Assembly procedure to generate the
Desired DL TX Power Adjustment MAC CE;

3\> cancel this Desired DL TX Power Adjustment query.