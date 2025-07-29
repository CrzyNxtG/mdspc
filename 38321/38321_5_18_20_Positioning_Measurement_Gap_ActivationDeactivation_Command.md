### 5.18.20 Positioning Measurement Gap Activation/Deactivation Command

If the UE is configured with pre-configured measurement gaps, the
network may send DL MAC CE for Positioning Measurement Gap
Activation/Deactivation Command to the UE as in clause 6.1.3.41. For the
activated measurement gap, the UE shall follow the specified UE
behaviour in clause 5.14.

Upon the reception of the MAC CE for Positioning Measurement Gap
Activation/Deactivation Command, the MAC entity shall:

1\> if the Positioning Measurement Gap Activation/Deactivation Command
MAC CE indicates the deactivation of a pre-configured positioning
measurement gap:

2\> deactivate the positioning measurement gap.

1\> else if the Positioning Measurement Gap Activation/Deactivation
Command MAC CE indicates the activation of a pre-configured measurement
gap:

2\> activate the positioning measurement gap and perform the procedure
specified in clause 5.14.