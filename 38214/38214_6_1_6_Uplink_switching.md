### 6.1.6 Uplink switching

The UE may omit uplink transmission during the uplink switching gap
$N_{\text{Tx1-Tx2}}$ if the conditions defined in this clause are met
and the UE is configured with *uplinkTxSwitching* or
*uplinkTxSwitchingMoreBands*. The switching gap $N_{\text{Tx1-Tx2}}$ is
indicated by UE capability *uplinkTxSwitchingPeriod2T2T* if
*uplinkTxSwitching-2T-Mode* is configured, and *uplinkTxSwitchingPeriod*
otherwise in clauses 6.1.6.1, 6.1.6.2.0, 6.1.6.3, and is determined
based on higher layer parameter *switchingPeriodConfigForBandPair* in
clause 6.1.6.2.2 for uplink switching configured with 2, 3 or 4 uplink
bands if *uplinkTxSwitchingMoreBands* is configured:

\- If a UE indicated a capability for uplink switching with
*BandCombination-UplinkTxSwitch* for a band combination, and if it is
for that band combination

\- Configured with a MCG using E-UTRA radio access and with a SCG using
NR radio access (EN-DC), or

\- Configured with uplink carrier aggregation, or

\- Configured in a serving cell with two uplink carriers with higher
layer parameter *supplementaryUplink*.

The conditions under which the switching gap may be present are defined
for each of the cases in clauses 6.1.6.1, 6.1.6.2, and 6.1.6.3
respectively.

If an uplink switching is triggered for an uplink transmission starting
at *T~0~*, after *T~0~-T~offset~*, the UE is not expected to cancel the
uplink switching, or to trigger any other new uplink switching occurring
before *T~0~* for any other uplink transmission that is scheduled after
*T~0~-T~offset~*, where *T~offset~* is the UE processing procedure time
defined for the uplink transmission(s) triggering the switch given in
clause 5.3, clause 5.4, clause 6.1, clause 6.2.1, clause 6.4 and in
clause 9 of \[6, TS 38.213\].

The UE does not expect to perform more than one uplink switching in a
slot with *µ~UL\ ~*= max(*µ~UL,\ 1,~ µ~UL,\ 2~*), where the *µ~UL,\ 1~*
corresponds to the subcarrier spacing of the active UL BWP of one uplink
carrier before the switching gap and the *µ~UL,\ 2~* corresponds to the
subcarrier spacing of the active UL BWP of the other uplink carrier
after the switching gap.

For uplink switching configured with 3 or 4 uplink bands

\- If two contiguous intra-band uplink carriers are configured to a UE,
the UE may assume that the active UL BWPs of the two carriers are
configured with the same subcarrier spacing.

\- The UE does not expect to perform more than one uplink switching in a
reference slot with *µ~UL~*, where the *µ~UL~* corresponds to the
maximum subcarrier spacing of the active UL BWPs of all the configured
uplink carriers.

\- If 500 µs is determined by the UE capability
*uplinkTxSwitchingMinimumSeparationTime*, when within any two
consecutive reference slots corresponding to numerology *µ~UL~*,

\- the UE first performs one uplink switch and later performs another
uplink switch and

\- at least three bands are involved in the transmissions before the
first switch, between the first switch and the second switch, and after
the second switch,

> the separation time between the start of all transmission(s) after the
> first switch and the start of all transmission(s) after the second
> switch is not expected to be less than 500 µs. If other than 500 µs is
> determined by the UE capability
> *uplinkTxSwitchingMinimumSeparationTime*, no additional restrictions
> apply.

\- If an uplink switching is triggered for uplink transmission(s) with a
gap between the start of the first uplink transmission(s) and the end of
the last preceding uplink transmission(s) that is smaller than the
determined switching gap $N_{\text{Tx1-Tx2}}$, the UE determines the
band of the switching period location, defined in \[8, TS 38.101-1\]
based on the priority of the bands configured by
*uplinkTxSwitchingBandList*. Among the bands either in switch-from or
switch-to bands but not both, the switch is located on either,

\- the switch-from band(s) if the highest priority band is a switch-to
band, or

\- the switch-to band(s) if the highest priority band is a switch-from
band.