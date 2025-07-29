### 4.9.3 Signalling procedures

RRC signalling is utilized to configure the NCR-MT to receive side
control information from a gNB, which is used to control the
amplify-and-forward function of the NCR-Fwd. If the side control
configuration is removed, the NCR-Fwd ceases its
amplifying-and-forwarding function.

MAC CE indications can be used to configure the backhaul link and the
access link of the NCR-Fwd as specified in TS 38.321 \[6\].

When the NCR-MT is in RRC_CONNECTED state, the NCR-Fwd may
amplify-and-forward RF signals based on the side control information
received from the gNB. The NCR-MT does not support RRM measurements in
RRC_CONNECTED.

When the NCR-MT transitions from RRC_CONNECTED state to RRC_INACTIVE
state, the NCR-Fwd may continue to amplify-and-forward RF signals in
accordance with the last side control information received from the gNB.
When the NCR-MT is in RRC_INACTIVE state, the NCR-Fwd ceases to
amplify-and-forward RF signals if no suitable cell is detected, or if
the NCR-MT selects a different cell than the last serving cell on which
side control configuration was received.

When an NCR-MT in RRC_INACTIVE state determines degradation of the
NCR-Fwd backhaul link beam, then the NCR-Fwd should cease
amplifying-and-forwarding RF signals, and the NCR-MT should attempt to
resume its RRC connection (with cause value *mo-Signalling*). The
criteria to evaluate backhaul beam degradation are left to the NCR-node
implementation.

When the NCR-MT transitions from RRC_CONNECTED state to RRC_IDLE, the
NCR-Fwd ceases any amplifying-and-forwarding of RF signals. How an
NCR-MT transitions back from RRC_IDLE state to RRC_CONNECTED state is
left to NCR-node or network implementation.

An NCR-MT can detect RLF on the control link as specified in TS 38.331
clause 5.3.10 \[12\]. When RLF is detected, the NCR-MT performs the RRC
re-establishment procedure as specified in TS 38.331 \[12\]. During the
RRC re-establishment procedure, the NCR-Fwd ceases to
amplify-and-forward RF signals.

After successfully performing the RRC re-establishment procedure, the
NCR-MT waits for the new side control configuration for the NCR-Fwd to
resume the amplifying-and-forwarding of RF signals.

An NCR-MT can also perform Beam Failure Detection (BFD) and Beam Failure
Recovery (BFR) as described in clause 9.2.8. Once the NCR-MT detects
beam failure in the control link, the NCR-Fwd should cease
amplifying-and-forwarding RF signals until BFR is completed.