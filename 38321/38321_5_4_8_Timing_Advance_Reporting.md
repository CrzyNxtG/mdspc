### 5.4.8 Timing Advance Reporting

The Timing Advance reporting procedure is used in a non-terrestrial
network or an air to ground network to provide the gNB with an estimate
of the UE\'s Timing Advance value (i.e., *T*~TA~ as defined in the UE\'s
TA formula, see TS 38.211 \[8\] clause 4.3.1).

RRC controls Timing Advance reporting by configuring the following
parameters:

*- offsetThresholdTA*;

*- timingAdvanceSR*.

A Timing Advance report (TAR) shall be triggered if any of the following
events occur:

\- upon indication from upper layers to trigger a Timing Advance report;

\- upon configuration of *offsetThresholdTA* by upper layers, if the UE
has not previously reported Timing Advance value to current Serving
Cell;

\- if the variation between the current estimate of the Timing Advance
value and the last reported Timing Advance value is equal to or larger
than *offsetThresholdTA*, if configured.

The MAC entity shall:

1\> if the Timing Advance reporting procedure determines that at least
one TAR has been triggered and not cancelled:

2\> if UL-SCH resources are available for a new transmission and the
UL-SCH resources can accommodate the Timing Advance Report MAC CE plus
its subheader as a result of logical channel prioritization:

3\> instruct the Multiplexing and Assembly procedure to generate the
Timing Advance Report MAC CE as defined in clause 6.1.3.56.

2\> else

3\> if *timingAdvanceSR* is configured with value *enabled*:

4\> trigger a Scheduling Request.

NOTE: UL-SCH resources are considered available if the MAC entity has
been configured with, receives, or determines an uplink grant. If the
MAC entity has determined at a given point in time that UL-SCH resources
are available, this need not imply that UL-SCH resources are available
for use at that point in time.

A MAC PDU shall contain at most one Timing Advance Report MAC CE, even
when multiple events have triggered a Timing Advance report. The Timing
Advance Report MAC CE shall be generated based on the latest available
estimate of the UE\'s Timing Advance value prior to the MAC PDU
assembly.

All triggered Timing Advance reports shall be cancelled when a MAC PDU
is transmitted and this PDU includes a Timing Advance Report MAC CE.