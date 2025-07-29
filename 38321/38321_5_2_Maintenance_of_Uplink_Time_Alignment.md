## 5.2 Maintenance of Uplink Time Alignment

RRC configures the following parameters for the maintenance of UL time
alignment:

\- *timeAlignmentTimer* (per TAG) which controls how long the MAC entity
considers the Serving Cells to the associated TAG to be uplink time
aligned for the TAG;

\- *inactivePosSRS-TimeAlignmentTimer* which controls how long the MAC
entity considers the Positioning SRS transmission in RRC_INACTIVE in
clause 5.26 to be uplink time aligned;

\- *cg-SDT-TimeAlignmentTimer* which controls how long the MAC entity
considers the uplink transmission for CG-SDT to be uplink time aligned;

> \- *inactivePosSRS-ValidityAreaTAT* which controls how long the MAC
> entity considers Positioning SRS transmission in RRC_INACTIVE in
> clause 5.26 to be uplink time aligned when SRS positioning validity
> area is configured.

The MAC entity shall:

1\> when a Timing Advance Command MAC CE is received, and if an N~TA~
(as defined in TS 38.211 \[8\]) has been maintained with the indicated
TAG:

2\> apply the Timing Advance Command for the indicated TAG;

2\> if there is ongoing Positioning SRS Transmission in RRC_INACTIVE as
in clause 5.26:

3\> if SRS positioning validity area is configured:

4\> start or restart the *inactivePosSRS-ValidityAreaTAT* associated
with the indicated TAG.

3\> else:

4\> start or restart the *inactivePosSRS-TimeAlignmentTimer* associated
with the indicated TAG.

2\> if CG-SDT procedure triggered as in clause 5.27 is ongoing:

3\> start or restart the *cg-SDT-TimeAlignmentTimer* associated with the
indicated TAG.

2\> else:

3\> start or restart the *timeAlignmentTimer* associated with the
indicated TAG.

1\> when a Timing Advance Command is received in a Random Access
Response message for a Serving Cell configured with two TAGs or in a
MSGB for an SpCell configured with two TAGs:

2\> if the Random Access Preamble was not selected by the MAC entity
among the contention-based Random Access Preamble:

3\> apply the Timing Advance Command for the TAG indicated in the
received Random Access Response message or MSGB;

3\> start or restart the *timeAlignmentTimer* associated with TAG
indicated in the received Random Access Response message or MSGB.

2\> else if the *timeAlignmentTimer* associated with the TAG indicated
in the received Random Access Response message or MSGB is not running:

3\> apply the Timing Advance Command for this TAG;

3\> start the *timeAlignmentTimer* associated with this TAG;

3\> when the Contention Resolution is considered not successful as
described in clause 5.1.5:

4\> stop the *timeAlignmentTimer* associated with this TAG.

2\> else:

3\> ignore the received Timing Advance Command.

1\> when a Timing Advance Command is received in a Random Access
Response message for a Serving Cell not configured with two TAGs or in a
MSGB for an SpCell not configured with two TAGs:

2\> if the Random Access Preamble was not selected by the MAC entity
among the contention-based Random Access Preamble:

3\> apply the Timing Advance Command for this TAG;

3\> start or restart the *timeAlignmentTimer* associated with this TAG.

2\> else if the *timeAlignmentTimer* associated with this TAG is not
running:

3\> apply the Timing Advance Command for this TAG;

3\> start the *timeAlignmentTimer* associated with this TAG;

3\> when the Contention Resolution is considered not successful as
described in clause 5.1.5; or

3\> when the Contention Resolution is considered successful for SI
request as described in clause 5.1.5, after transmitting HARQ feedback
for MAC PDU including UE Contention Resolution Identity MAC CE:

4\> stop *timeAlignmentTimer* associated with this TAG.

3\> when the Contention Resolution is considered not successful as
described in clause 5.1.5:

4\> if CG-SDT procedure triggered as in clause 5.27 is ongoing; or

4\> if SRS transmission in RRC_INACTIVE as in clause 5.26 is ongoing:

5\> set the N~TA~ value to the value before applying the received Timing
Advance Command as in TS 38.211 \[8\].

3\> when the Contention Resolution is considered successful for Random
Access procedure while the CG-SDT procedure is ongoing:

4\> stop *timeAlignmentTimer* associated with this TAG;

4\> start or restart the *cg-SDT-TimeAlignmentTimer* associated with
this TAG.

3\> when the Contention Resolution is considered successful for Random
Access procedure while Positioning SRS transmission in RRC_INACTIVE is
ongoing as in clause 5.26:

> 4\> if SRS positioning validity area is configured:

5\> start or restart the *inactivePosSRS-ValidityAreaTAT* associated
with the indicated TAG.

4\> else:

5\> start or restart the *inactivePosSRS-TimeAlignmentTimer* associated
with this TAG.

2\> else:

3\> ignore the received Timing Advance Command.

1\> when an Absolute Timing Advance Command is received in response to a
MSGA transmission including C-RNTI MAC CE, as specified in clause
5.1.4a, for an SpCell configured with two TAGs:

2\> apply the Timing Advance Command for the PTAG indicated in the
Absolute Timing Advance Command MAC CE;

2\> start or restart the *timeAlignmentTimer* associated with this PTAG.

1\> when an Absolute Timing Advance Command is received in response to a
MSGA transmission including C-RNTI MAC CE, as specified in clause
5.1.4a, for an SpCell not configured with two TAGs:

2\> apply the Timing Advance Command for PTAG;

2\> if there is ongoing Positioning SRS Transmission in RRC_INACTIVE as
in clause 5.26:

3\> if SRS positioning validity area is configured:

4\> start or restart the *inactivePosSRS-ValidityAreaTAT* associated
with the indicated TAG.

3\> else:

4\> start or restart the *inactivePosSRS-TimeAlignmentTimer* associated
with the indicated TAG.

2\> if CG-SDT procedure is ongoing:

3\> start or restart the *cg-SDT-TimeAlignmentTimer* associated with
PTAG.

2\> else:

3\> start or restart the *timeAlignmentTimer* associated with PTAG.

1\> when the MAC entity is configured with *rach-LessHO*:

2\> set the N~TA~ value (as defined in TS 38.211 \[8\]) to the value
indicated by *targetNTA* in *rach-LessHO* for PTAG;

2\> start the *timeAlignmentTimer* associated with PTAG.

1\> when the indication is received from upper layer for stopping the
*inactivePosSRS-TimeAlignmentTimer*:

2\> stop the *inactivePosSRS-TimeAlignmentTimer*.

1\> when the indication is received from upper layer for starting the
*inactivePosSRS-TimeAlignmentTimer*:

2\> start or restart the *inactivePosSRS-TimeAlignmentTimer*.

1\> when instruction from the upper layer has been received for starting
the *cg-SDT-TimeAlignmentTimer*:

2\> start the *cg-SDT-TimeAlignmentTimer*.

1\> when instruction from the upper layer has been received for stopping
the *cg-SDT-TimeAlignmentTimer*:

2\> consider the *cg-SDT-TimeAlignmentTimer* as expired.

1\> when the indication is received from upper layer for starting the
*inactivePosSRS-ValidityAreaTAT*:

2\> start or restart the *inactivePosSRS-ValidityAreaTAT*.

1\> when the indication is received from upper layer for stopping the
*inactivePosSRS-ValidityAreaTAT*:

2\> stop the *inactivePosSRS-ValidityAreaTAT*.

1\> when instruction from the upper layer has been received for starting
the *TimeAlignmentTimer* associated with PTAG:

2\> start the *TimeAlignmentTimer* associated with the indicated PTAG.

1\> when an LTM Cell Switch Command MAC CE is received and the Timing
Advance Command is not set as FFF:

2\> apply the Timing Advance Command for the PTAG as specified in clause
6.1.3.75;

2\> start or restart the *timeAlignmentTimer* associated with the PTAG
as specified in clause 6.1.3.75.

1\> when an LTM Cell Switch Command MAC CE is received, and the Timing
Advance Command is set as FFF, and the UE has successfully measured the
Timing Advance as in clause 5.18.35:

2\> apply the measured Timing Advance for the PTAG;

2\> start or restart the *timeAlignmentTimer* associated with the PTAG.

1\> when a *timeAlignmentTimer* expires:

2\> if the *timeAlignmentTimer* is associated with a PTAG and the SpCell
is not configured with two PTAGs; or

2\> if the *timeAlignmentTimer* is associated with a PTAG, the SpCell is
configured with two PTAGs, and the *timeAlignmentTimer* associated with
the other PTAG is not running:

3\> flush all HARQ buffers for all Serving Cells;

3\> notify RRC to release PUCCH for all Serving Cells, if configured;

3\> notify RRC to release SRS for all Serving Cells, if configured;

3\> clear any configured downlink assignments and configured uplink
grants;

3\> clear any PUSCH resource for semi-persistent CSI reporting;

3\> consider all running *timeAlignmentTimer*s as expired;

3\> maintain N~TA~ (defined in TS 38.211 \[8\]) of all TAGs.

2\> else:

3\> if the *timeAlignmentTimer* is associated with a TAG for an SCell
configured with only this TAG; or

3\> if the *timeAlignmentTimer* is associated with a TAG for an SCell,
and if the SCell is configured with two TAGs and *the
timeAlignmentTimer* associated with the other TAG is not running:

4\> flush all HARQ buffers for all such SCells;

4\> notify RRC to release PUCCH, if configured for all such SCells;

4\> notify RRC to release SRS, if configured for all such SCells;

4\> clear any configured downlink assignments and configured uplink
grants for all such SCells;

4\> clear any PUSCH resource for semi-persistent CSI reporting for all
such SCells;

4\> maintain N~TA~ (defined in TS 38.211 \[8\]) of this TAG.

3\> else if the *timeAlignmentTimer* is associated with a TAG for a
Serving Cell configured with two TAGs, and if the *timeAlignmentTimer*
associated with the other TAG is running, for all such Serving Cells:

4\> clear any configured downlink assignment, if the activated TCI
state(s) for all PUCCH resources configured for the configured downlink
assignment is associated with the TAG of the expired
*timeAlignmentTimer*;

4\> clear any configured uplink grant, if the activated TCI state(s) for
the configured uplink grant is associated with the TAG of the expired
*timeAlignmentTimer*;

4\> clear any PUSCH resource for semi-persistent CSI reporting, if the
activated TCI state(s) for the PUSCH resource is associated with the TAG
of the expired *timeAlignmentTimer*;

4\> maintain N~TA~ (defined in TS 38.211 \[8\]) of this TAG.

1\> when the *inactivePosSRS-TimeAlignmentTimer* expires:

2\> notify RRC to release Positioning SRS for RRC_INACTIVE
configuration(s).

1\> when the *cg-SDT-TimeAlignmentTimer* expires:

2\> clear any configured uplink grants;

2\> if a PDCCH addressed to the MAC entity\'s C-RNTI after initial
transmission for the CG-SDT with CCCH message has not been received:

3\> consider ongoing CG-SDT procedure as terminated;

3\> indicate the expiry of *cg-SDT-TimeAlignmentTimer* to the upper
layer.

2\> flush all HARQ buffers;

2\> maintain N~TA~ (defined in TS 38.211 \[8\]) of this TAG.

When the MAC entity stops uplink transmissions for an SCell not
configured with two TAGs due to the fact that the maximum uplink
transmission timing difference between TAGs of the MAC entity or the
maximum uplink transmission timing difference between TAGs of any MAC
entity of the UE is exceeded, the MAC entity considers the
*timeAlignmentTimer* associated with the SCell as expired.

When the MAC entity stops uplink transmissions associated to a STAG for
an SCell configured with two TAGs due to the fact that the maximum
uplink transmission timing difference between TAGs of the MAC entity or
the maximum uplink transmission timing difference between TAGs of any
MAC entity of the UE is exceeded, the MAC entity considers the
*timeAlignmentTimer* associated with the STAG as expired.

The MAC entity shall not perform any uplink transmission on a Serving
Cell except the Random Access Preamble and MSGA transmission when the
*timeAlignmentTimer*(s) associated with all TAG(s) to which this Serving
Cell belongs is not running, CG-SDT procedure is not ongoing and
Positioning SRS transmission in RRC_INACTIVE as in clause 5.26 is not
ongoing. Furthermore, when the *timeAlignmentTimer*(s) associated with
all PTAG(s) is not running, CG-SDT procedure is not ongoing and
Positioning SRS transmission in RRC_INACTIVE as in clause 5.26 is not
ongoing, the MAC entity shall not perform any uplink transmission on any
Serving Cell except the Random Access Preamble and MSGA transmission on
the SpCell. The MAC entity shall not perform any uplink transmission
except the Random Access Preamble and MSGA transmission when the
*cg-SDT-TimeAlignmentTimer* is not running during the ongoing CG-SDT
procedure as triggered in clause 5.27 and the
*inactivePosSRS-TimeAlignmentTimer* or *inactivePosSRS-ValidityAreaTAT*
is not running. The MAC entity shall not perform any uplink transmission
except the Random Access Preamble and MSGA transmission on a Serving
Cell using TCI state(s) associated with a TAG for which the
*timeAlignmentTimer* is not running.