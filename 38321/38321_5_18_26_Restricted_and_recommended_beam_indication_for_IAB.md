### 5.18.26 Restricted and recommended beam indication for IAB

Child IAB-DU Restricted Beam Indication MAC CE is used by an IAB-DU or
an IAB-donor-DU to indicate to its child node spatial resources and
associated frequency information where simultaneous
transmission/reception from the IAB-MT of the child node and
transmission from the IAB-DU cells of the child node is restricted.
IAB-MT Recommended Beam Indication MAC CE is used by an IAB-node to
indicate to its parent node recommendations for spatial resources and
associated frequency information for transmission/reception from and to
the IAB-MT of the IAB-node. Time resources where these
restrictions/recommendations can apply are indicated via RRC, while the
MAC CE further selects from these time resources the specific time
resource configuration (comprising a list of slot indices) to which
information provided in the MAC CE applies.

Upon reception of a Child IAB-DU Restricted Beam Indication MAC CE the
IAB-node shall:

\- apply the configuration signalled in the MAC CE to the time slots
indicated in *IAB-ResourceConfig* (as specified in TS 38.331 \[5\])
which contains *iab-ResourceConfigID* parameter which matches the
Resource Configuration ID field of the MAC CE.

The MAC entity may:

1\> if an IAB-MT Recommended Beam Indication query has not been
triggered:

2\> trigger an IAB-MT Recommended Beam Indication query for this Serving
Cell.

If the MAC entity has UL resources allocated for new transmission the
MAC entity shall:

1\> for each IAB-MT Recommended Beam Indication query that has been
triggered and not cancelled:

2\> if the allocated UL resources can accommodate a IAB-MT Recommended
Beam Indication MAC CE plus its subheader as a result of LCP as defined
in clause 5.4.3.1:

3\> instruct the Multiplexing and Assembly procedure to generate the
IAB-MT Recommended Beam Indication MAC CE;

3\> cancel this IAB-MT Recommended Beam Indication query.