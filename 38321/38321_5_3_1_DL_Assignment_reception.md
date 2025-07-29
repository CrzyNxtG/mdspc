### 5.3.1 DL Assignment reception

Downlink assignments received on the PDCCH both indicate that there is a
transmission on a DL-SCH for a particular MAC entity and provide the
relevant HARQ information.

When the MAC entity has a C-RNTI, Temporary C-RNTI, CS-RNTI, G-RNTI or
G-CS-RNTI, the MAC entity shall for each PDCCH occasion during which it
monitors PDCCH and for each Serving Cell:

1\> if a downlink assignment for this PDCCH occasion and this Serving
Cell has been received on the PDCCH for the MAC entity\'s C-RNTI, or
Temporary C‑RNTI, or G-RNTI configured for multicast MTCH:

2\> if this is the first downlink assignment for this Temporary C-RNTI:

3\> consider the NDI to have been toggled.

2\> if the downlink assignment is for the MAC entity\'s C-RNTI, and if
the previous downlink assignment indicated to the HARQ entity of the
same HARQ process was either a downlink assignment received for the MAC
entity\'s CS-RNTI or G-CS-RNTI, or a configured downlink assignment for
unicast or MBS multicast; or

2\> if the downlink assignment is for the MAC entity\'s G-RNTI
configured for multicast MTCH, and if the previous downlink assignment
indicated to the HARQ entity of the same HARQ process was either a
downlink assignment received for the MAC entity\'s CS-RNTI or G-CS-RNTI,
or other G-RNTI, or C-RNTI, or a configured downlink assignment for
unicast or MBS multicast:

3\> consider the NDI to have been toggled regardless of the value of the
NDI.

2\> stop the *cg-SDT-RetransmissionTimer*, if it is running, for the
corresponding HARQ process for initial transmission with CCCH message;

2\> stop the *cg-RRC-RetransmissionTimer*, if it is running, for the
corresponding HARQ process for the first PUSCH transmission of RACH-less
handover or RACH-less LTM cell switch;

2\> stop the *configuredGrantTimer*, if it is running, for the
corresponding HARQ process for initial transmission with CCCH message;

2\> if the downlink assignment has been received on the PDCCH for the
MAC entity\'s C-RNTI after the first PUSCH transmission to the Serving
Cell:

3\> if there is an ongoing RACH-less handover procedure:

4\> consider the RACH-less handover to be successfully completed and
indicate it to upper layers.

3\> else if RACH-less LTM cell switch is ongoing:

4\> consider the LTM cell switch to be successfully completed and
indicate it to upper layers.

2\> indicate the presence of a downlink assignment and deliver the
associated HARQ information to the HARQ entity.

1\> else if a downlink assignment for this PDCCH occasion has been
received for this Serving Cell on the PDCCH for the MAC entity\'s
CS-RNTI or G-CS-RNTI:

2\> if the NDI in the received HARQ information is 1:

3\> consider the NDI for the corresponding HARQ process not to have been
toggled;

3\> indicate the presence of a downlink assignment for this Serving Cell
and deliver the associated HARQ information to the HARQ entity.

2\> if the NDI in the received HARQ information is 0:

3\> if PDCCH contents indicate SPS deactivation:

4\> clear the configured downlink assignment for this Serving Cell (if
any);

4\> if the *timeAlignmentTimer*, associated with the TAG containing the
Serving Cell on which the HARQ feedback is to be transmitted, is
running, and the Serving Cell is not configured with two TAGs; or

4\> if the Serving Cell on which the HARQ feedback is to be transmitted
is configured with two TAGs and if the *timeAlignmentTimer* of the TAG,
associated with the TCI state(s) used for transmitting the HARQ
feedback, is running:

5\> indicate a positive acknowledgement for the SPS deactivation to the
physical layer.

3\> else if PDCCH content indicates SPS activation:

4\> store the downlink assignment for this Serving Cell and the
associated HARQ information as configured downlink assignment;

4\> initialise or re-initialise the configured downlink assignment for
this Serving Cell to start in the associated PDSCH duration and to recur
according to rules in clause 5.8.1 or in clause 5.8.1a;

For each Serving Cell and each configured downlink assignment, if
configured and activated, the MAC entity shall:

1\> if the PDSCH duration of the configured downlink assignment does not
overlap with the PDSCH duration of a downlink assignment received on the
PDCCH for this Serving Cell:

2\> instruct the physical layer to receive, in this PDSCH duration,
transport block on the DL-SCH according to the configured downlink
assignment and to deliver it to the HARQ entity;

2\> set the HARQ Process ID to the HARQ Process ID associated with this
PDSCH duration;

2\> consider the NDI bit for the corresponding HARQ process to have been
toggled;

2\> indicate the presence of a configured downlink assignment and
deliver the stored HARQ information to the HARQ entity.

For configured downlink assignments without *harq-ProcID-Offset*, the
HARQ Process ID associated with the slot where the DL transmission
starts is derived from the following equation:

HARQ Process ID = \[floor (CURRENT_slot × 10 / (*numberOfSlotsPerFrame*
× *periodicity*))\]\
modulo *nrofHARQ-Processes*

where CURRENT_slot = \[(SFN × *numberOfSlotsPerFrame*) + slot number in
the frame\] and *numberOfSlotsPerFrame* refers to the number of
consecutive slots per frame as specified in TS 38.211 \[8\].

For configured downlink assignments with *harq-ProcID-Offset*, the HARQ
Process ID associated with the slot where the DL transmission starts is
derived from the following equation:

HARQ Process ID = \[floor (CURRENT_slot × 10 / (*numberOfSlotsPerFrame*
× *periodicity*))\]\
modulo *nrofHARQ-Processes* + *harq-ProcID-Offset*

where CURRENT_slot = \[(SFN × *numberOfSlotsPerFrame*) + slot number in
the frame\] and *numberOfSlotsPerFrame* refers to the number of
consecutive slots per frame as specified in TS 38.211 \[8\].

NOTE 1: In case of unaligned SFN across carriers in a cell group, the
SFN of the concerned Serving Cell is used to calculate the HARQ Process
ID used for configured downlink assignments.

NOTE 2: CURRENT_slot refers to the slot index of the first transmission
occasion of a bundle of configured downlink assignment.

When the MAC entity needs to read BCCH, the MAC entity may, based on the
scheduling information from RRC:

1\> if a downlink assignment for this PDCCH occasion has been received
on the PDCCH for the SI-RNTI;

2\> indicate a downlink assignment and redundancy version for the
dedicated broadcast HARQ process to the HARQ entity.

When the MAC entity needs to read MCCH, the MAC entity may, based on the
scheduling information from RRC:

1\> if a downlink assignment for this PDCCH occasion has been received
on the PDCCH for the MCCH-RNTI or Multicast MCCH-RNTI:

2\> indicate a downlink assignment and redundancy version for the
selected HARQ process to the HARQ entity.

When the MAC entity needs to read broadcast MTCH, the MAC entity may,
based on the scheduling information from RRC and DCI:

1\> if a downlink assignment for this PDCCH occasion has been received
on the PDCCH for the G-RNTI configured for broadcast MTCH:

2\> indicate the presence of a downlink assignment and deliver the
associated HARQ information for the selected HARQ process to the HARQ
entity.