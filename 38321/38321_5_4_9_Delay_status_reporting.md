### 5.4.9 Delay status reporting

The Delay Status Reporting (DSR) procedure is used to provide the
serving gNB with delay status of LCGs. This delay status for an LCG
includes remaining time, which is the smallest remaining value of the
running PDCP *discardTimer*s among PDCP SDUs that are buffered for the
LCG but have not been transmitted in any MAC PDU as specified in clause
7.3 in TS 38.323 \[4\], and the total amount of delay-critical UL data
for the LCG according to the data volume calculation procedure specified
in clause 5.5 in TS 38.322 \[3\] and clause 5.15 in TS 38.323 \[4\] for
the associated RLC and PDCP entities, respectively.

RRC controls the DSR procedure by configuring the following parameter:

\- *remainingTimeThreshold* (per LCG): the threshold on remaining time
for triggering a DSR for a logical channel within an LCG.

If an LCG is configured for delay status reporting, the MAC entity shall
for each logical channel within the LCG:

1\> if the smallest remaining value of the running PDCP *discardTimer*s
among all the PDCP SDUs buffered for the logical channel that have not
been transmitted in any MAC PDU and have not been reported as data
volume in a DSR MAC CE becomes below *remainingTimeThreshold* of the
LCG; and

1\> if there is no DSR pending for the logical channel:

2\> trigger a DSR for the logical channel.

If there is at least one DSR pending, the MAC entity shall:

1\> if UL-SCH resources are available for a new transmission and the
UL-SCH resources can accommodate the DSR MAC CE plus its subheader as a
result of logical channel prioritization:

2\> instruct the Multiplexing and Assembly procedure to generate the DSR
MAC CE as specified in clause 6.1.3.72.

1\> else if there is no pending SR already triggered by the DSR
procedure for the same logical channel as of this DSR:

2\> trigger a Scheduling Request.

NOTE 1: The availability of UL-SCH resources for the transmission of the
DSR MAC CE follows the same critieria specified in clause 5.4.5.

A PDCP SDU is considered to be associated with a DSR if it has not been
transmitted in any MAC PDU and is a delay-critical PDCP SDU (as defined
in TS 38.323 \[4\]) associated with the logical channel which triggered
the DSR.

A MAC PDU shall contain at most one DSR MAC CE. A MAC PDU shall not
contain a DSR MAC CE if it includes all PDCP SDUs associated with all
the pending DSRs.

After a DSR is triggered, it is considered as pending until it is
cancelled. The MAC entity shall cancel a pending DSR, when all the PDCP
SDUs associated with the DSR have been discarded, or when a MAC PDU is
transmitted and this MAC PDU includes a DSR MAC CE that contains the
delay information of all the PDCP SDUs associated with the DSR (as
described in the clause 6.1.3.72), or when a MAC PDU is transmitted and
this MAC PDU includes all the PDCP SDUs associated with the DSR.

NOTE 2: It is up to UE implementation whether the MAC entity includes a
DSR MAC CE in a MAC PDU if the MAC PDU can accommodate all PDCP SDUs
associated with all the pending DSRs but is not sufficient to
additionally accommodate the DSR MAC CE plus its subheader.