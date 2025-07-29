### 5.18.28 UL PSD range adjustment for IAB

Desired IAB-MT PSD range MAC CE is used by an IAB-node to indicate to
its parent node a recommendation of spatial resources and associated
frequency information where the desired PSD range, contained in the MAC
CE (and provided to help with the node\'s UL TX power control) could
apply. Time resources where these recommendations can apply are
indicated via RRC, while the MAC CE further selects from these time
resources the specific time resource configuration (comprising a list of
slot indices) to which information provided in the MAC CE applies.

The MAC entity may:

1\> if a Desired IAB-MT PSD range query has not been triggered:

2\> trigger a Desired IAB-MT PSD range query for this Serving Cell.

If the MAC entity has UL resources allocated for new transmission the
MAC entity shall:

1\> for each Desired IAB-MT PSD range query that has been triggered and
not cancelled:

2\> if the allocated UL resources can accommodate a Desired IAB-MT PSD
range MAC CE plus its subheader as a result of LCP as defined in clause
5.4.3.1:

3\> instruct the Multiplexing and Assembly procedure to generate the
Desired IAB-MT PSD range MAC CE;

3\> cancel this Desired IAB-MT PSD range query.