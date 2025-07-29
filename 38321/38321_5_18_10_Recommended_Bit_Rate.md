### 5.18.10 Recommended Bit Rate

The recommended bit rate procedure is used to provide the MAC entity
with information about the bit rate which the gNB recommends. The bit
rate is the recommended bit rate of the physical layer. Averaging window
of default value 2000 ms will apply as specified in TS 26.114 \[13\].

The gNB may transmit the Recommended bit rate MAC CE to the MAC entity
to indicate the recommended bit rate for the UE for a specific logical
channel and a specific direction (either uplink or downlink). Upon
reception of a Recommended bit rate MAC CE the MAC entity shall:

\- indicate to upper layers the recommended bit rate for the indicated
logical channel and direction.

The MAC entity may request the gNB to indicate the recommended bit rate
for a specific logical channel and a specific direction. If the MAC
entity is requested by upper layers to query the gNB for the recommended
bit rate for a logical channel and for a direction (i.e. for uplink or
downlink), the MAC entity shall:

1\> if a Recommended bit rate query for this logical channel and this
direction has not been triggered:

2\> trigger a Recommended bit rate query for this logical channel,
direction, and desired bit rate.

If the MAC entity has UL resources allocated for new transmission the
MAC entity shall:

1\> for each Recommended bit rate query that the Recommended Bit Rate
procedure determines has been triggered and not cancelled:

2\> if *bitRateQueryProhibitTimer* for the logical channel and the
direction of this Recommended bit rate query is configured, and it is
not running; and

2\> if the MAC entity has UL resources allocated for new transmission
and the allocated UL resources can accommodate a Recommended bit rate
MAC CE plus its subheader as a result of LCP as defined in clause
5.4.3.1:

3\> instruct the Multiplexing and Assembly procedure to generate the
Recommended bit rate MAC CE for the logical channel and the direction of
this Recommended bit rate query;

3\> start the *bitRateQueryProhibitTimer* for the logical channel and
the direction of this Recommended bit rate query;

3\> cancel this Recommended bit rate query.