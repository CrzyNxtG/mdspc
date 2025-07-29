### 5.4.7 Pre-emptive Buffer Status Reporting

The Pre-emptive Buffer Status reporting (Pre-emptive BSR) procedure is
used by an IAB-MT to provide its parent IAB-DU(s) or IAB-donor-DU(s)
with the information about the amount of the data expected to arrive at
the IAB-MT from its child node(s) and/or UE(s) connected to it.

If configured, Pre-emptive BSR may be triggered for the specific case of
an IAB-MT if any of the following events occur:

\- UL grant is provided to child IAB node or UE;

\- BSR is received from child IAB node or UE.

IAB-MT may report Extended Pre-emptive BSR (as defined in clause
6.1.3.1) if the MAC entity of the IAB-MT is configured with
*logicalChannelGroupIAB-Ext* by upper layers. Otherwise IAB-MT may
report Pre-emptive BSR (as defined in clause 6.1.3.1).

The MAC entity shall:

1\> if the Pre-emptive Buffer Status reporting procedure determines that
at least one Pre-emptive BSR has been triggered and not cancelled:

2\> if UL-SCH resources are available for a new transmission and the
UL-SCH resources can accommodate the Extended Pre-emptive BSR or
Pre-emptive BSR MAC CE plus its subheader as a result of logical channel
prioritization:

3\> instruct the Multiplexing and Assembly procedure to generate the
Extended Pre-emptive BSR or Pre-emptive BSR MAC CE as defined in clause
6.1.3.1.

2\> else:

3\> trigger a Scheduling Request.

A MAC PDU shall contain at most one Pre-emptive BSR MAC CE or Extended
Pre-emptive BSR MAC CE, even when multiple events have triggered a
Pre-emptive BSR.

All triggered Pre-emptive BSR(s) shall be cancelled when a MAC PDU is
transmitted and this PDU includes the corresponding Pre-emptive BSR MAC
CE or Extended Pre-emptive BSR MAC CE.

NOTE: Pre-emptive BSR may be used for the case of dual-connected IAB
node. It is up to network implementation to work out the associated MAC
entity or entities which report the Pre-emptive BSR, and the associated
expected amount of data reported by any such entity or entities. For the
case of dual-connected IAB node, if two ingress BH RLC channels
belonging to the same ingress LCG are mapped to two different egress
Cell Groups (corresponding to different parent nodes), there may be
ambiguity in Pre-emptive BSR calculations and interpretation by the
receiving parent node(s) and the IAB node reporting pre-emptive BSR.