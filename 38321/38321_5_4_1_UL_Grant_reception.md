### 5.4.1 UL Grant reception

Uplink grant is either received dynamically on the PDCCH, in a Random
Access Response, configured semi-persistently by RRC or determined to be
associated with the PUSCH resource of MSGA as specified in clause
5.1.2a. The MAC entity shall have an uplink grant to transmit on the
UL-SCH. To perform the requested transmissions, the MAC layer receives
HARQ information from lower layers. For uplink spatial multiplexing, the
MAC layer can receive up to two uplink grants (one per HARQ process) on
the PDCCH that schedules two TBs as specified in TS 38.212 \[9\]. An
uplink grant addressed to CS-RNTI with NDI = 0 is considered as a
configured uplink grant. An uplink grant addressed to CS-RNTI with NDI =
1 is considered as a dynamic uplink grant.

For a BWP configured with *sTx-2Panel,* the MAC entity considers the
PUSCH duration of one uplink grant overlaps with the PUSCH duration of
another uplink grant if they are overlapping in time and associated with
an *srs-ResourceSetId* corresponding to the same *coresetPoolIndex*.

If the MAC entity has a C-RNTI, a Temporary C-RNTI, or CS-RNTI, the MAC
entity shall for each PDCCH occasion and for each Serving Cell belonging
to a TAG that has a running *timeAlignmentTimer* or a running
*cg-SDT-TimeAlignmentTimer* and for each grant received for this PDCCH
occasion:

1\> if an uplink grant for this Serving Cell has been received on the
PDCCH for the MAC entity\'s C-RNTI or Temporary C-RNTI; or

1\> if an uplink grant has been received in a Random Access Response:

2\> if the uplink grant is for MAC entity\'s C-RNTI and if the previous
uplink grant delivered to the HARQ entity for the same HARQ process was
either an uplink grant received for the MAC entity\'s CS-RNTI or a
configured uplink grant:

3\> consider the NDI to have been toggled for the corresponding HARQ
process regardless of the value of the NDI.

2\> if the uplink grant is for MAC entity\'s C-RNTI, and the identified
HARQ process is configured for a configured uplink grant:

3\> start or restart the *configuredGrantTimer* for the corresponding
HARQ process, if configured;

3\> stop the *cg-RetransmissionTimer* for the corresponding HARQ
process, if running.

2\> stop the *cg-SDT-RetransmissionTimer* for the corresponding HARQ
process, if running.

2\> stop the *cg-RRC-RetransmissionTimer* for the corresponding HARQ
process, if running.

2\> if the uplink grant has been received on the PDCCH for the MAC
entity\'s C-RNTI after the first PUSCH transmission to the Serving Cell;
and

2\> if the uplink grant is for a new transmission on the same HARQ
process used for the first PUSCH transmission to the Serving Cell:

3\> if there is an ongoing RACH-less handover procedure:

4\> consider the RACH-less handover to be successfully completed and
indicate to upper layers.

3\> else if there is an ongoing RACH-less LTM cell switch:

4\> consider the LTM cell switch to be successfully completed and
indicate it to upper layers.

2\> deliver the uplink grant and the associated HARQ information to the
HARQ entity.

1\> else if an uplink grant for this PDCCH occasion has been received
for this Serving Cell on the PDCCH for the MAC entity\'s CS-RNTI:

2\> if the NDI in the received HARQ information is 1:

3\> consider the NDI for the corresponding HARQ process not to have been
toggled;

3\> start or restart the *configuredGrantTimer* for the corresponding
HARQ process, if configured;

3\> stop the *cg-RetransmissionTimer* for the corresponding HARQ
process, if running;

3\> stop the *cg-SDT-RetransmissionTimer* for the corresponding HARQ
process, if running;

3\> stop the *cg-RRC-RetransmissionTimer* for the corresponding HARQ
process, if running;

3\> deliver the uplink grant and the associated HARQ information to the
HARQ entity;

3\> if a logical channel associated with a DRB configured with
*survivalTimeStateSupport* is multiplexed in the MAC PDU stored in the
HARQ buffer for the corresponding HARQ process:

4\> trigger activation of PDCP duplication for all configured RLC
entities of the DRB.

2\> else if the NDI in the received HARQ information is 0:

3\> if PDCCH contents indicate configured grant Type 2 deactivation:

4\> trigger configured uplink grant confirmation.

3\> else if PDCCH contents indicate configured grant Type 2 activation:

4\> trigger configured uplink grant confirmation;

4\> store the uplink grant for this Serving Cell and the associated HARQ
information as configured uplink grant;

4\> initialise or re-initialise the configured uplink grant for this
Serving Cell to start in the associated PUSCH duration and to recur
according to rules in clause 5.8.2;

4\> stop the *configuredGrantTimer* for the corresponding HARQ process,
if running;

4\> stop the *cg-RetransmissionTimer* for the corresponding HARQ
process, if running.

For each Serving Cell and each configured uplink grant, if configured
and activated and available for use as specified in clause 5.8.2, the
MAC entity shall:

1\> if the MAC entity is configured with *lch-basedPrioritization*, and
the PUSCH duration of the configured uplink grant does not overlap with
the PUSCH duration of an uplink grant received in a Random Access
Response or with the PUSCH duration of an uplink grant addressed to
Temporary C-RNTI or the PUSCH duration of a MSGA payload for this
Serving Cell; or

1\> if the MAC entity is not configured with *lch-basedPrioritization*,
and the PUSCH duration of the configured uplink grant does not overlap
with the PUSCH duration of an uplink grant received on the PDCCH or in a
Random Access Response or the PUSCH duration of a MSGA payload for this
Serving Cell:

2\> set the HARQ Process ID to the HARQ Process ID associated with this
PUSCH duration;

2\> if, for the corresponding HARQ process, the *configuredGrantTimer*
is not running and *cg-RetransmissionTimer* is not configured and
*cg-SDT-RetransmissionTimer* is not configured, and
*cg-RRC-RetransmissionTimer* is not configured (i.e. new transmission):

3\> if the configured uplink grant is for the initial transmission for
the CG-SDT with CCCH message; or

3\> if there is an ongoing CG-SDT procedure and PDCCH addressed to the
MAC entity\'s C-RNTI has been received; or

3\> if the configured uplink grant is for the first PUSCH transmission
during an ongoing RACH-less LTM cell switch; or

3\> if the configured uplink grant is for the first PUSCH transmission
during an ongoing RACH-less handover procedure; or

3\> if there is no ongoing CG-SDT nor ongoing RACH-less LTM cell switch
nor ongoing RACH-less handover procedure:

4\> consider the NDI bit for the corresponding HARQ process to have been
toggled;

4\> deliver the configured uplink grant and the associated HARQ
information to the HARQ entity.

2\> else if the *cg-RetransmissionTimer* for the corresponding HARQ
process is configured and not running, then for the corresponding HARQ
process:

3\> if the *configuredGrantTimer* is not running, and the HARQ process
is not pending (i.e. new transmission):

4\> consider the NDI bit to have been toggled;

4\> deliver the configured uplink grant and the associated HARQ
information to the HARQ entity.

3\> else if the previous uplink grant delivered to the HARQ entity for
the same HARQ process was a configured uplink grant (i.e. retransmission
on configured grant):

4\> deliver the configured uplink grant and the associated HARQ
information to the HARQ entity.

2\> else if the *cg-SDT-RetransmissionTimer* is configured and not
running for the corresponding HARQ process; or

2\> if the *cg-RRC-RetransmissionTimer* is configured and not running
for the corresponding HARQ process:

3\> if the configured uplink grant is for the first PUSCH transmission
at RACH-less LTM cell switch (i.e., initial new transmission); or

3\> if the configured uplink grant is for the first PUSCH transmission
of RACH-less handover (i.e., initial new transmission); or

3\> if the configured uplink grant is for the initial transmission for
the CG-SDT with CCCH message (i.e., initial new transmission); or

3\> if the *configuredGrantTimer* is not running or not configured, and
PDCCH addressed to the MAC entity\'s C-RNTI has been received after the
initial transmission of the CG-SDT with CCCH message (i.e., subsequent
new transmission):

4\> consider the NDI bit to have been toggled;

4\> deliver the configured uplink grant and the associated HARQ
information to the HARQ entity.

3\> if PDCCH addressed to the MAC entity\'s C-RNTI has not been received
and if the previous uplink grant delivered to the HARQ entity for the
same HARQ process was a configured uplink grant for initial transmission
of CG-SDT with CCCH message or for its retransmission (i.e.,
retransmission for initial CG-SDT transmission); or

3\> if RACH-less handover is not successfully completed and if the
previous uplink grant delivered to the HARQ entity for the same HARQ
process was a configured uplink grant for the first PUSCH transmission
of RACH-less handover or for its retransmission (i.e., retransmission
for the first PUSCH transmission for RACH-less handover); or

3\> if RACH-less LTM cell switch is ongoing and if the previous uplink
grant delivered to the HARQ entity for the same HARQ process was a
configured uplink grant for first PUSCH transmission at RACH-less LTM
cell switch or for its retransmission (i.e., retransmission for the
first PUSCH transmission at RACH-less LTM cell switch):

4\> consider the NDI bit to have not been toggled;

4\> deliver the configured uplink grant and the associated HARQ
information to the HARQ entity.

For configured uplink grants that are not part of a multi-PUSCH
configured grant and neither configured with *harq-ProcID-Offset2* nor
with *cg-RetransmissionTimer*, the HARQ Process ID associated with the
first symbol of a UL transmission is derived from the following
equation:

HARQ Process ID = \[floor(CURRENT_symbol/*periodicity*)\] modulo
*nrofHARQ-Processes*

For configured uplink grants that are not part of a multi-PUSCH
configured grant and configured with *harq-ProcID-Offset2*, the HARQ
Process ID associated with the first symbol of a UL transmission is
derived from the following equation:

HARQ Process ID = \[floor(CURRENT_symbol / *periodicity*)\] modulo
*nrofHARQ-Processes* + *harq-ProcID-Offset2*

For a multi-PUSCH configured grant (as specified in clause 5.8.2)
configured with neither *harq-ProcID-Offset2* nor
*cg-RetransmissionTimer*, the HARQ Process ID associated with the first
symbol of a UL transmission is derived from the following equation:

HARQ Process ID = \[*nrofSlotsInCG-Period*× floor (CURRENT_symbol /
*periodicity*) + ID_OFFSET\] modulo *nrofHARQ-Processes*

For a multi-PUSCH configured grant configured with
*harq-ProcID-Offset2*, the HARQ Process ID associated with the first
symbol of a UL transmission is derived from the following equation:

HARQ Process ID = \[*nrofSlotsInCG-Period* × floor (CURRENT_symbol /
*periodicity*) + ID_OFFSET\] modulo *nrofHARQ-Processes* +
*harq-ProcID-Offset2*

where, if *cg-SDT-PeriodicityExt* (as defined in TS 38.331 \[5\]) is not
configured,

CURRENT_symbol = (SFN × *numberOfSlotsPerFrame* ×
*numberOfSymbolsPerSlot* + slot number in the frame ×
*numberOfSymbolsPerSlot* + symbol number in the slot)

alternatively, if *cg-SDT-PeriodicityExt* (as defined in TS 38.331
\[5\]) is configured, *periodicity* equals to *cg-SDT-PeriodicityExt*,
and

CURRENT_symbol = ((H-SFN × *numberOfSFNperH-SFN* + SFN) ×
*numberOfSlotsPerFrame* × *numberOfSymbolsPerSlot* + slot number in the
frame × *numberOfSymbolsPerSlot* + symbol number in the slot).

*numberOfSFNperH-SFN*, *numberOfSlotsPerFrame* and
*numberOfSymbolsPerSlot* above refer to the number of consecutive frames
per H-SFN, the number of consecutive slots per frame and the number of
consecutive symbols per slot, respectively as specified in TS 38.211
\[8\].

For a multi-PUSCH configured grant, ID_OFFSET equals 0 for the first
configured uplink grant within a *periodicity* of the configuration and
K for the K^th^ (1 ≤ K \< *nrofSlotsInCG-Period*) valid configured
uplink grant after the first configured uplink grant within the same
*periodicity*. A configured uplink grant in a multi-PUSCH configured
grant is considered valid if it satisfies the conditions specified in
clause 6.1 in TS 38.214 \[7\].

For configured uplink grants configured with *cg-RetransmissionTimer*,
the UE implementation selects an HARQ Process ID among the HARQ process
IDs available for the configured grant configuration. If the MAC entity
is configured with *intraCG-Prioritization*, for HARQ Process ID
selection, the UE shall prioritize the HARQ Process ID with the highest
priority, where the priority of HARQ process is determined by the
highest priority among priorities of the logical channels that are
multiplexed (i.e. the MAC PDU to transmit is already stored in the HARQ
buffer) or have data available that can be multiplexed (i.e. the MAC PDU
to transmit is not stored in the HARQ buffer) in the MAC PDU, according
to the mapping restrictions as described in clause 5.4.3.1.2. If the MAC
entity is configured with *intraCG-Prioritization*, for HARQ Process ID
selection among initial transmission and retransmission with equal
priority, the UE shall prioritize retransmissions before initial
transmissions. The priority of a HARQ Process for which no data for
logical channels is multiplexed or can be multiplexed in the MAC PDU is
lower than the priority of a HARQ Process for which data for any logical
channels is multiplexed or can be multiplexed in the MAC PDU. If the MAC
entity is not configured with *intraCG-Prioritization*, for HARQ Process
ID selection, the UE shall prioritize retransmissions before initial
transmissions. The UE shall toggle the NDI in the CG-UCI for new
transmissions and not toggle the NDI in the CG-UCI in retransmissions.

NOTE 1: If a configured uplink grant is associated with a multi-PUSCH
configured grant, CURRENT_symbol refers to the symbol index of the first
transmission occasion in the first configured uplink grant within the
same periodicity. Otherwise, CURRENT_symbol refers to the symbol index
of the first transmission occasion of a bundle of configured uplink
grant.

NOTE 2: A HARQ process is configured for a configured uplink grant where
neither *harq-ProcID-Offset* nor *harq-ProcID-Offset2* is configured, if
the configured uplink grant is activated and the associated HARQ process
ID is less than *nrofHARQ-Processes*. A HARQ process is configured for a
configured uplink grant where *harq-ProcID-Offset2* is configured, if
the configured uplink grant is activated and the associated HARQ process
ID is greater than or equal to *harq-ProcID-Offset2* and less than sum
of *harq-ProcID-Offset2* and *nrofHARQ-Processes* for the configured
grant configuration.

NOTE 3: If the MAC entity receives a grant in a Random Access Response
(i.e. MAC RAR or fallbackRAR), or addressed to Temporary C-RNTI or
determines a grant as specified in clause 5.1.2a for MSGA payload and if
the MAC entity also receives an overlapping grant for its C-RNTI or
CS-RNTI, requiring concurrent transmissions on the SpCell, the MAC
entity may choose to continue with either the grant for its
RA-RNTI/Temporary C-RNTI/MSGB-RNTI/the MSGA payload transmission or the
grant for its C-RNTI or CS-RNTI.

NOTE 4: In case of unaligned SFN across carriers in a cell group, the
SFN of the concerned Serving Cell is used to calculate the HARQ Process
ID used for configured uplink grants.

> NOTE 5: If *cg-RetransmissionTimer* is not configured, a HARQ process
> is not shared between different configured grant configurations in the
> same BWP.

For the MAC entity configured with *lch-basedPrioritization*, priority
of an uplink grant is determined by the highest priority among
priorities of the logical channels that are multiplexed (i.e. the MAC
PDU to transmit is already stored in the HARQ buffer) or have data
available that can be multiplexed (i.e. the MAC PDU to transmit is not
stored in the HARQ buffer) in the MAC PDU, according to the mapping
restrictions as described in clause 5.4.3.1.2. The priority of an uplink
grant for which no data for logical channels is multiplexed or can be
multiplexed in the MAC PDU is lower than either the priority of an
uplink grant for which data for any logical channels is multiplexed or
can be multiplexed in the MAC PDU or the priority of the logical channel
triggering an SR.

For the MAC entity configured with *lch-basedPrioritization*, if the
corresponding PUSCH transmission of a configured uplink grant is
cancelled by CI-RNTI as specified in clause 11.2A of TS 38.213 \[6\] or
cancelled by a high PHY-priority PUCCH transmission as specified in
clause 9 of TS 38.213 \[6\], this configured uplink grant is considered
as a de-prioritized uplink grant. If this de-prioritized uplink grant is
configured with *autonomousTx*, the *configuredGrantTimer* for the
corresponding HARQ process of this de-prioritized uplink grant shall be
stopped if it is running. If this de-prioritized uplink grant is
configured with *autonomousTx*, the *cg-RetransmissionTimer* for the
corresponding HARQ process of this de-prioritized uplink grant shall be
stopped if it is running.

When the MAC entity is configured with *lch-basedPrioritization*, for
each uplink grant delivered to the HARQ entity and whose associated
PUSCH can be transmitted by lower layers, the MAC entity shall:

1\> if this uplink grant is received in a Random Access Response (i.e.
in a MAC RAR or fallback RAR), or addressed to Temporary C-RNTI, or is
determined as specified in clause 5.1.2a for the transmission of the
MSGA payload:

2\> consider this uplink grant as a prioritized uplink grant.

1\> else if this uplink grant is addressed to CS-RNTI with NDI = 1 or
C-RNTI:

2\> if there is no overlapping PUSCH duration of a configured uplink
grant which was not already de-prioritized, in the same BWP, whose
priority is higher than the priority of the uplink grant; and

2\> if there is no overlapping PUCCH resource with an SR transmission
which was not already de-prioritized and the simultaneous transmission
of the SR and the uplink grant is not allowed by configuration of
*simultaneousPUCCH-PUSCH* or
*simultaneousPUCCH-PUSCH-SecondaryPUCCHgroup* or
*simultaneousSR-PUSCH-diffPUCCH-Groups* or
*simultaneousPUCCH-PUSCH-SamePriority* or
*simultaneousPUCCH-PUSCH-SamePriority-SecondaryPUCCHgroup*, and the
priority of the logical channel that triggered the SR is higher than the
priority of the uplink grant:

3\> consider this uplink grant as a prioritized uplink grant;

3\> consider the other overlapping uplink grant(s), if any, as a
de-prioritized uplink grant(s);

3\> consider the other overlapping SR transmission(s), if any, as a
de-prioritized SR transmission(s), except for the SR transmission(s)
whose simultaneous transmission is allowed by configuration of
*simultaneousPUCCH-PUSCH* or
*simultaneousPUCCH-PUSCH-SecondaryPUCCHgroup* or
*simultaneousSR-PUSCH-diffPUCCH-Groups* or
*simultaneousPUCCH-PUSCH-SamePriority* or
*simultaneousPUCCH-PUSCH-SamePriority-SecondaryPUCCHgroup*;

3\> if the de-prioritized uplink grant(s) is a configured uplink grant
configured with *autonomousTx* whose PUSCH has already started:

4\> stop the *configuredGrantTimer* for the corresponding HARQ process
of the de-prioritized uplink grant(s);

4\> stop the *cg-RetransmissionTimer* for the corresponding HARQ process
of the de-prioritized uplink grant(s).

1\> else if this uplink grant is a configured uplink grant:

2\> if there is no overlapping PUSCH duration of another configured
uplink grant which was not already de-prioritized, in the same BWP,
whose priority is higher than the priority of the uplink grant; and

2\> if there is no overlapping PUSCH duration of an uplink grant
addressed to CS-RNTI with NDI = 1 or C-RNTI which was not already
de-prioritized, in the same BWP, whose priority is higher than or equal
to the priority of the uplink grant; and

2\> if there is no overlapping PUCCH resource with an SR transmission
which was not already de-prioritized and the simultaneous transmission
of the SR and the uplink grant is not allowed by configuration of
*simultaneousPUCCH-PUSCH* or
*simultaneousPUCCH-PUSCH-SecondaryPUCCHgroup* or
*simultaneousSR-PUSCH-diffPUCCH-Groups* or
*simultaneousPUCCH-PUSCH-SamePriority* or
*simultaneousPUCCH-PUSCH-SamePriority-SecondaryPUCCHgroup*, and the
priority of the logical channel that triggered the SR is higher than the
priority of the uplink grant:

3\> consider this uplink grant as a prioritized uplink grant;

3\> consider the other overlapping uplink grant(s), if any, as a
de-prioritized uplink grant(s);

3\> if the de-prioritized uplink grant(s) is a configured uplink grant
configured with *autonomousTx* whose PUSCH has already started:

4\> stop the *configuredGrantTimer* for the corresponding HARQ process
of the de-prioritized uplink grant(s);

4\> stop the *cg-RetransmissionTimer* for the corresponding HARQ process
of the de-prioritized uplink grant(s).

3\> consider the other overlapping SR transmission(s), if any, as a
de-prioritized SR transmission(s), except for the SR transmission(s)
whose simultaneous transmission is allowed by configuration of
*simultaneousPUCCH-PUSCH* or
*simultaneousPUCCH-PUSCH-SecondaryPUCCHgroup* or
*simultaneousSR-PUSCH-diffPUCCH-Groups* or
*simultaneousPUCCH-PUSCH-SamePriority* or
*simultaneousPUCCH-PUSCH-SamePriority-SecondaryPUCCHgroup*.

NOTE 6: If the MAC entity is configured with *lch-basedPrioritization*
and if there is overlapping PUSCH duration of at least two configured
uplink grants whose priorities are equal, the prioritized uplink grant
is determined by UE implementation.

NOTE 7: If the MAC entity is not configured with
*lch-basedPrioritization* and if there is overlapping PUSCH duration of
at least two configured uplink grants, it is up to UE implementation to
choose one of the configured uplink grants.

NOTE 8: If the MAC entity is configured with *lch-basedPrioritization*,
the MAC entity does not take UCI multiplexing according to the procedure
specified in TS 38.213 \[6\] into account when determining whether the
PUSCH duration of an uplink grant overlaps with the PUCCH resource for
an SR transmission.

NOTE 9: For uplink spatial multiplexing, for the MAC entity configured
with *lch-basedPrioritization*, the MAC entity considers the two uplink
grants received on the PDCCH that schedules two TBs are prioritized or
deprioritized together and the priority is determined by the highest
priority among priorities of the logical channels that are multiplexed
or have data available that can be multiplexed in the two MAC PDUs,
according to the mapping restrictions as described in clause 5.4.3.1.2.