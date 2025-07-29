### 5.4.4 Scheduling Request

The Scheduling Request (SR) is used for requesting UL-SCH resources for
new transmission.

The MAC entity may be configured with zero, one, or more SR
configurations. An SR configuration consists of a set of PUCCH resources
for SR across different BWPs and cells. For a logical channel or for
SCell beam failure recovery (see clause 5.17) and for consistent LBT
failure recovery (see clause 5.21), at most one PUCCH resource for SR is
configured per BWP. For a logical channel serving a radio bearer
configured with SDT, PUCCH resource for SR is not configured for SDT.
For beam failure recovery of BFD-RS set(s) of Serving Cell, up to two
PUCCH resources for SR are configured per BWP. For positioning
measurement gap activation/deactivation request, a dedicated SR
configuration is configured.

Each SR configuration corresponds to one or more logical channels and/or
to SCell beam failure recovery and/or to consistent LBT failure recovery
and/or to beam failure recovery of a BFD-RS set and/or to positioning
measurement gap activation/deactivation request. Each logical channel,
SCell beam failure recovery, beam failure recovery of a BFD-RS set and
consistent LBT failure recovery, may be mapped to zero or one SR
configuration, which is configured by RRC. The SR configuration of the
logical channel that triggered a BSR (clause 5.4.5) or a DSR (clause
5.4.9) or the SCell beam failure recovery or the beam failure recovery
of a BFD-RS set or the consistent LBT failure recovery (clause 5.21) (if
such a configuration exists) or positioning measurement gap
activation/deactivation request (clause 5.25) is considered as
corresponding SR configuration for the triggered SR. Any SR
configuration may be used for an SR triggered by Pre-emptive BSR (clause
5.4.7) or Timing Advance reporting (clause 5.4.8).

RRC configures the following parameters for the scheduling request
procedure:

\- *sr-ProhibitTimer* (per SR configuration);

\- *sr-TransMax* (per SR configuration).

The following UE variables are used for the scheduling request
procedure:

\- *SR_COUNTER* (per SR configuration).

If an SR is triggered and there are no other SRs pending corresponding
to the same SR configuration, the MAC entity shall set the *SR_COUNTER*
of the corresponding SR configuration to 0.

When an SR is triggered, it shall be considered as pending until it is
cancelled.

All pending SR(s) for BSR triggered according to the BSR procedure
(clause 5.4.5) prior to the MAC PDU assembly shall be cancelled and each
respective *sr-ProhibitTimer* shall be stopped when the MAC PDU is
transmitted and this PDU includes a Long, Refined Long or Short BSR MAC
CE which contains buffer status up to (and including) the last event
that triggered a BSR (see clause 5.4.5) prior to the MAC PDU assembly.
All pending SR(s) for BSR triggered according to the BSR procedure
(clause 5.4.5) shall be cancelled and each respective *sr-ProhibitTimer*
shall be stopped when the UL grant(s) can accommodate all pending data
available for transmission.

The MAC entity shall for each pending SR not triggered according to the
BSR procedure (clause 5.4.5) for a Serving Cell:

1\> if this SR was triggered by Pre-emptive BSR procedure (see clause
5.4.7) prior to the MAC PDU assembly and a MAC PDU containing the
relevant Pre-emptive BSR MAC CE is transmitted; or

1\> if this SR was triggered by beam failure recovery (see clause 5.17)
of an SCell and a MAC PDU is transmitted and this PDU includes a MAC CE
for BFR which contains beam failure recovery information for this SCell;
or

1\> if this SR was triggered by beam failure recovery (see clause 5.17)
for a BFD-RS set of a Serving Cell and a MAC PDU is transmitted and this
PDU includes an Enhanced BFR MAC CE or a Truncated Enhanced BFR MAC CE
which contains beam failure recovery information for this BFD-RS set of
the Serving Cell; or

1\> if this SR was triggered by beam failure recovery (see clause 5.17)
of an SCell and this SCell is deactivated (see clause 5.9); or

1\> if this SR was triggered by beam failure recovery (see clause 5.17)
for a BFD-RS set of an SCell and this SCell is deactivated (see clause
5.9); or

1\> if the SR is triggered by positioning measurement gap
activation/deactivation request (see clause 5.25) and the Positioning
Measurement Gap Activation/Deactivation Request MAC CE that triggers the
SR has already been cancelled; or

1\> if this SR was triggered by consistent LBT failure recovery (see
clause 5.21) of an SCell and a MAC PDU is transmitted and the MAC PDU
includes an LBT failure MAC CE that indicates consistent LBT failure for
this SCell; or

1\> if this SR was triggered by consistent LBT failure recovery (see
clause 5.21) of an SCell and all the triggered consistent LBT failure(s)
for this SCell are cancelled; or

1\> if this SR was triggered by Timing Advance reporting (see clause
5.4.8) and all the triggered Timing Advance reports are cancelled; or

1\> if this SR was triggered by DSR procedure (see clause 5.4.9) and the
DSR that triggered the SR has been cancelled:

2\> cancel the pending SR and stop the corresponding *sr-ProhibitTimer*,
if running.

Only PUCCH resources on a BWP which is active at the time of SR
transmission occasion are considered valid.

As long as at least one SR is pending, the MAC entity shall for each
pending SR:

1\> if the MAC entity has no valid PUCCH resource configured for the
pending SR; and

1\> if there is no ongoing RACH-less LTM cell switch; and

1\> if *rach-LessHO* is not configured:

2\> initiate a Random Access procedure (see clause 5.1) on the SpCell
and cancel the pending SR.

1\> else, for the SR configuration corresponding to the pending SR:

2\> when the MAC entity has an SR transmission occasion on the valid
PUCCH resource for SR configured; and

2\> if *sr-ProhibitTimer* is not running at the time of the SR
transmission occasion; and

2\> if the PUCCH resource for the SR transmission occasion does not
overlap with a measurement gap:

3\> if the PUCCH resource for the SR transmission occasion does not
overlap with any of a UL-SCH resource whose simultaneous transmission
with the SR is not allowed by configuration of *simultaneousPUCCH-PUSCH*
or *simultaneousPUCCH-PUSCH-SecondaryPUCCHgroup* or
*simultaneousSR-PUSCH-diffPUCCH-Groups* or
*simultaneousPUCCH-PUSCH-SamePriority* or
*simultaneousPUCCH-PUSCH-SamePriority-SecondaryPUCCHgroup*, an SL-SCH
resource, or an SL-PRS resource; or

3\> if the MAC entity is able to perform this SR transmission
simultaneously with the transmission of the SL-SCH resource; or

3\> if the MAC entity is configured with *lch-basedPrioritization*, and
the PUCCH resource for the SR transmission occasion does not overlap
with the PUSCH duration of an uplink grant received in a Random Access
Response or with the PUSCH duration of an uplink grant addressed to
Temporary C-RNTI or with the PUSCH duration of a MSGA payload, and the
PUCCH resource for the SR transmission occasion for the pending SR
triggered as specified in clause 5.4.5 overlaps with any other UL-SCH
resource(s), and the physical layer can signal the SR on one valid PUCCH
resource for SR, and the priority of the logical channel that triggered
SR is higher than the priority of the uplink grant(s) for any UL-SCH
resource(s) where the uplink grant was not already de-prioritized and
its simultaneous transmission with the SR is not allowed by
configuration of *simultaneousPUCCH-PUSCH* or
*simultaneousPUCCH-PUSCH-SecondaryPUCCHgroup* or
*simultaneousSR-PUSCH-diffPUCCHgroups* or
*simultaneousPUCCH-PUSCH-SamePriority* or
*simultaneousPUCCH-PUSCH-SamePriority-SecondaryPUCCHgroup*, and the
priority of the uplink grant is determined as specified in clause 5.4.1;
or

3\> if both *sl-PrioritizationThres* and *ul-PrioritizationThres* are
configured and the PUCCH resource for the SR transmission occasion for
the pending SR triggered as specified in clause 5.22.1.5 overlaps with
any UL-SCH resource(s) carrying a MAC PDU, and the value of the priority
of the triggered SR determined as specified in clause 5.22.1.5 is lower
than *sl-PrioritizationThres* and the value of the highest priority of
the logical channel(s) in the MAC PDU is higher than or equal to
*ul-PrioritizationThres* and any MAC CE prioritized as described in
clause 5.4.3.1.3 is not included in the MAC PDU and the MAC PDU is not
prioritized by upper layer according to TS 23.287 \[19\]; or

3\> if an SL-SCH resource overlaps with the PUCCH resource for the SR
transmission occasion for the pending SR triggered as specified in
clause 5.4.5, and the MAC entity is not able to perform this SR
transmission simultaneously with the transmission of the SL-SCH
resource, and either transmission on the SL-SCH resource is not
prioritized as described in clause 5.22.1.3.1a or the priority value of
the logical channel that triggered SR is lower than
*ul-PrioritizationThres*, if configured; or

3\> if an SL-SCH resource overlaps with the PUCCH resource for the SR
transmission occasion for the pending SR triggered as specified in
clause 5.22.1.5, and the MAC entity is not able to perform this SR
transmission simultaneously with the transmission of the SL-SCH
resource, and the priority of the triggered SR determined as specified
in clause 5.22.1.5 is higher than the priority of the MAC PDU determined
as specified in clause 5.22.1.3.1a for the SL-SCH resource; or

3\> if an SL-PRS resource overlaps with the PUCCH resource for the SR
transmission occasion for the pending SR triggered as specified in
clause 5.4.5, and the MAC entity is not able to perform this SR
transmission simultaneously with the transmission of the SL-PRS
resource, and either transmission on the SL-PRS resource is not
prioritized as described in clause 5.22.1.3.1a or in the clause
5.22.1.3.5, or the priority value of the logical channel that triggered
SR is lower than *ul-PrioritizationThres*, if configured; or

3\> if an SL-PRS resource overlaps with the PUCCH resource for the SR
transmission occasion for the pending SR triggered as specified in
clause 5.22.1.5, and the MAC entity is not able to perform this SR
transmission simultaneously with the transmission of the SL-PRS
resource, and the priority of the triggered SR determined as specified
in clause 5.22.1.5 is higher than the priority of the MAC PDU and
SL-PRS, if available, determined as specified in clause 5.22.1.3.1a or
the SL-PRS resource in clause 5.22.1.3.5:

4\> consider the SR transmission as a prioritized SR transmission.

4\> consider the other overlapping uplink grant(s), if any, as a
de-prioritized uplink grant(s), except for the overlapping uplink
grant(s) whose simultaneous transmission is allowed by configuration of
*simultaneousPUCCH-PUSCH* or
*simultaneousPUCCH-PUSCH-SecondaryPUCCHgroup* or
*simultaneousSR-PUSCH-diffPUCCH-Groups* or
*simultaneousPUCCH-PUSCH-SamePriority* or
*simultaneousPUCCH-PUSCH-SamePriority-SecondaryPUCCHgroup*;

4\> if the de-prioritized uplink grant(s) is a configured uplink grant
configured with *autonomousTx* whose PUSCH has already started:

5\> stop the *configuredGrantTimer* for the corresponding HARQ process
of the de-prioritized uplink grant(s);

5\> stop the *cg-RetransmissionTimer* for the corresponding HARQ process
of the de-prioritized uplink grant(s).

4\> if *SR_COUNTER* \< *sr-TransMax*:

5\> instruct the physical layer to signal the SR on one valid PUCCH
resource for SR;

5\> if LBT failure indication is not received from lower layers:

6\> increment *SR_COUNTER* by 1;

6\> start the *sr-ProhibitTimer*.

5\> else if *lbt-FailureRecoveryConfig* is not configured:

6\> increment *SR_COUNTER* by 1.

4\> else:

5\> notify RRC to release PUCCH for all Serving Cells;

5\> notify RRC to release SRS for all Serving Cells;

5\> clear any configured downlink assignments and uplink grants;

5\> clear any PUSCH resources for semi-persistent CSI reporting;

5\> if *rach-LessHO* is not configured and if there is no ongoing
RACH-less LTM cell switch:

6\> initiate a Random Access procedure (see clause 5.1) on the SpCell
and cancel all pending SRs.

3\> else:

4\> consider the SR transmission as a de-prioritized SR transmission.

NOTE 1: Except for the cases specified in NOTE 3 below, the selection of
which valid PUCCH resource for SR to signal SR on when the MAC entity
has more than one overlapping valid PUCCH resource for the SR
transmission occasion is left to UE implementation.

NOTE 2: If more than one individual SR triggers an instruction from the
MAC entity to the PHY layer to signal the SR on the same valid PUCCH
resource, the *SR_COUNTER* for the relevant SR configuration is
incremented only once.

NOTE 3: When the MAC entity has pending SR for SCell beam failure
recovery and the MAC entity has one or more PUCCH resources (other than
PUCCH resources of pending SR for beam failure recovery of a BFD-RS set)
overlapping with PUCCH resource for SCell beam failure recovery for the
SR transmission occasion, the MAC entity considers only the PUCCH
resource for SCell beam failure recovery as valid. When the MAC entity
has pending SR for beam failure recovery of a BFD-RS set of Serving Cell
and the MAC entity has one or more PUCCH resources (other than PUCCH
resources of pending SR for beam failure recovery) overlapping with
PUCCH resource for beam failure recovery of that BFD-RS set for the SR
transmission occasion, the MAC entity considers only the PUCCH resource
for beam failure recovery of that BFD-RS set as valid.

NOTE 4: For a UE operating in a semi-static channel access mode as
described in TS 37.213 \[18\], PUCCH resources overlapping with the set
of consecutive symbols where the UE does not transmit before the start
of a next channel occupancy time are not considered valid.

NOTE 5: If the MAC entity is configured with *lch-basedPrioritization*,
the MAC entity does not take UCI multiplexing according to the procedure
specified in TS 38.213 \[6\] into account when determining whether the
valid PUCCH resource for the SR transmission can be signalled by the
physical layer and the SR transmission occasion overlaps with the PUSCH
duration of an uplink grant of a MSGA payload.

NOTE 6: When the MAC entity has PUCCH resource for pending SR for SCell
beam failure recovery overlapping with PUCCH resource for pending SR for
beam failure recovery of a BFD-RS set for the SR transmission occasion,
it is up to UE implementation to select PUCCH resource for SCell beam
failure recovery or PUCCH resource for beam failure recovery of a BFD-RS
set.

NOTE 7: If an SL-SCH resource overlaps with the PUCCH resource for the
SR transmission occasion for the pending SR triggered by Uu MAC CEs
except BSR/SL-BSR MAC CE, and the MAC entity is not able to perform this
SR transmission simultaneously with the transmission of the SL-SCH
resource, it is left to UE implementation to determine whether this SR
transmission is prioritized over the SL transmission.

The MAC entity may stop, if any, ongoing Random Access procedure due to
a pending SR for BSR, which was initiated by the MAC entity prior to the
MAC PDU assembly and which has no valid PUCCH resources configured, if:

\- a MAC PDU is transmitted using a UL grant other than a UL grant
provided by Random Access Response or a UL grant determined as specified
in clause 5.1.2a for the transmission of the MSGA payload, and this PDU
includes a BSR MAC CE which contains buffer status up to (and including)
the last event that triggered a BSR (see clause 5.4.5) prior to the MAC
PDU assembly; or

\- the UL grant(s) can accommodate all pending data available for
transmission.

The MAC entity may stop, if any, ongoing Random Access procedure due to
a pending SR for SL-BSR, which has no valid PUCCH resources configured,
if:

\- a MAC PDU is transmitted using a UL grant other than a UL grant
provided by Random Access Response or a UL grant determined as specified
in clause 5.1.2a for the transmission of the MSGA payload, and the
ongoing Random Access procedure was initiated by the MAC entity prior to
the MAC PDU assembly, and this PDU includes an SL-BSR MAC CE which
contains buffer status up to (and including) the last event that
triggered an SL-BSR (see clause 5.22.1.6) prior to the MAC PDU assembly;
or

\- the SL grant(s) can accommodate all pending data available for
transmission, and the ongoing Random Access procedure was initiated by
the MAC entity prior to the sidelink MAC PDU assembly.

The MAC entity may stop, if any, ongoing Random Access procedure due to
a pending SR for SL-CSI reporting, which has no valid PUCCH resources
configured, if:

\- the SL grant can accommodate SL-CSI reporting MAC CE for
transmission.

The MAC entity may stop, if any, ongoing Random Access procedure due to
a pending SR for SL-DRX command indication, which has no valid PUCCH
resources configured, if:

\- the SL grant can accommodate SL-DRX command indication for
transmission.

The MAC entity may stop, if any, ongoing Random Access procedure due to
a pending SR for BFR of an SCell, which has no valid PUCCH resources
configured, if:

\- a MAC PDU is transmitted using a UL grant other than a UL grant
provided by Random Access Response or a UL grant determined as specified
in clause 5.1.2a for the transmission of the MSGA payload, and this PDU
contains a MAC CE for BFR which includes beam failure recovery
information of that SCell; or

\- the SCell is deactivated (as specified in clause 5.9) and all
triggered BFRs for SCells are cancelled.

The MAC entity may stop, if any, ongoing Random Access procedure due to
a pending SR for BFR of a BFD-RS set of a Serving Cell, which has no
valid PUCCH resources configured, if:

\- a MAC PDU is transmitted using a UL grant other than a UL grant
provided by Random Access Response or a UL grant determined as specified
in clause 5.1.2a for the transmission of the MSGA payload, and this PDU
contains an Enhanced BFR MAC CE or a Truncated Enhanced BFR MAC CE which
includes beam failure recovery information of that BFD-RS set of the
Serving Cell.

The MAC entity may stop, if any, ongoing Random Access procedure due to
a pending SR for consistent LBT failure recovery, which has no valid
PUCCH resources configured, if:

\- a MAC PDU is transmitted using a UL grant other than a UL grant
provided by Random Access Response or a UL grant determined as specified
in clause 5.1.2a for the transmission of the MSGA payload, and this PDU
includes an LBT failure MAC CE that indicates consistent LBT failure for
all the SCells that triggered consistent LBT failure; or

\- all the SCells that triggered consistent LBT failure recovery are
deactivated (see clause 5.9).

The MAC entity may stop, if any, ongoing Random Access procedure due to
a pending SR for Sidelink consistent LBT failure recovery, which has no
valid PUCCH resources configured, if one of the following conditions is
met:

\- a MAC PDU is transmitted using a UL grant other than a UL grant
provided by Random Access Response or a UL grant determined as specified
in clause 5.1.2a for the transmission of the MSGA payload, and this PDU
includes an SL LBT failure MAC CE that indicates Sidelink consistent LBT
failure; or

\- all the triggered Sidelink consistent LBT failure recovery are
cancelled (see clause 5.31.2).

The MAC entity may stop, if any, ongoing Random Access procedure due to
a pending SR for positioning measurement gap activation/deactivation
request, which has no valid PUCCH resources configured, if:

\- the Positioning Measurement Gap Activation/Deactivation Request MAC
CE that triggers the SR corresponding to the Random Access procedure has
already been cancelled.

The MAC entity may stop, if any, ongoing Random Access procedure due to
a pending SR for Timing Advance report, which has no valid PUCCH
resources configured, if:

\- a MAC PDU is transmitted using a UL grant other than a UL grant
provided by Random Access Response or a UL grant determined as specified
in clause 5.1.2a for the transmission of the MSGA payload, and this PDU
includes a Timing Advance Report MAC CE (see clause 5.4.8).

The MAC entity may stop, if any, ongoing Random Access procedure due to
a pending SR for DSR, which has no valid PUCCH resources configured, if:

\- a MAC PDU is transmitted using a UL grant other than a UL grant
provided by Random Access Response or a UL grant determined as specified
in clause 5.1.2a for the transmission of the MSGA payload, and this PDU
includes either a DSR MAC CE or all the PDCP SDUs associated with the
DSR (see clause 5.4.9); or

\- all the PDCP SDUs associated with the DSR have been discarded (see
clause 5.4.9).

The MAC entity may stop, if any, ongoing Random Access procedure due to
a pending SR for SL-PRS Resource Request, which has no valid PUCCH
resources configured, if:

\- a MAC PDU is transmitted using a UL grant other than a UL grant
provided by Random Access Response or a UL grant determined as specified
in clause 5.1.2a for the transmission of the MSGA payload, and this PDU
includes a SL-PRS Resource Request MAC CE (see clause 5.22.1.12).