## 5.25 Positioning Measurement Gap Activation/Deactivation Request

If the UE is configured with pre-configured positioning measurement gap
and the request of the activation/deactivation of the positioning
measurement gap by UL MAC CE, the UE may request the network to activate
or deactivate the Positioning measurement gap with UL MAC CE for
Positioning Measurement Gap Activation/Deactivation Request in clause
6.1.3.40.

The MAC entity shall, when triggered by the upper layer to send
Positioning Measurement Gap Activation/Deactivation Request, cancel the
triggered Positioning Measurement Gap Activation/Deactivation Request,
if any and trigger another Positioning Measurement Gap
Activation/Deactivation Request according to the upper layer\'s request.

The MAC entity shall,

1\>if Positioning Measurement Gap Activation/Deactivation Request MAC CE
has been triggered, and not cancelled:

2\> if indication from upper layer has been received that the triggered
Positioning Measurement Gap Activation/Deactivation Request MAC CE
should be cancelled; or

2\> if the pre-configured measurement gap indicated in the Positioning
Measurement Gap Activation/Deactivation Request MAC CE has already been
activated/deactivated according to clause 5.18.20:

3\> cancel the triggered Positioning Measurement Gap
Activation/Deactivation Request MAC CE.

2\> if UL-SCH resources are available for a new transmission and these
UL-SCH resources can accommodate the Positioning Measurement Gap
Activation/Deactivation Request MAC CE plus its subheader as a result of
logical channel prioritization:

3\> instruct the Multiplexing and Assembly procedure to generate the
Positioning Measurement Gap Activation/Deactivation Request MAC CE
according to the upper layer\'s request;

3\> cancel triggered Positioning Measurement Gap Activation/Deactivation
Request MAC CE.

2\> else:

3\> trigger a Scheduling Request for Positioning Measurement Gap
Activation/Deactivation Request MAC CE as specified in clause 5.4.4.