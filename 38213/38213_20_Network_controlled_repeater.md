# 20 Network controlled repeater

An NCR includes an NCR-MT entity and an NCR-Fwd entity \[19, TS
38.300\].

Throughout this specification, unless otherwise noted, statements using
the term \"UE\" in Clauses 4 through 13 are equally applicable to the
NCR-MT.

A procedure for the NCR-MT to perform cell search, system information
acquisition, random access procedure, UCI reporting, or PDCCH monitoring
is same as a corresponding one for a UE. A procedure for the NCR-MT to
perform PDSCH reception, CSI-RS measurements and CSI determination,
PUSCH transmission, or SRS transmission is same as a corresponding one
for a UE as described in \[6, TS 38.214\].

The NCR-Fwd transmits or receives only after the NCR-MT receives on the
control link an indication for one or more beams \[20, TS 38.106\] for
the NCR-Fwd to use for transmissions or receptions over corresponding
one or more time resources on the access link.

The timing for transmission and reception by the NCR-Fwd on the backhaul
link follows the frame timing for transmission and reception,
respectively, by the NCR-MT.

When the NCR-MT performs a link recovery procedure as described in
Clause 6, the NCR-Fwd does not transmit or receive until the link
recovery procedure is complete \[11, TS 38.321\].

The NCR can be provided, through the NCR-MT,
*tdd-UL-DL-ConfigurationCommon* and can be additionally provided
*tdd-UL-DL-ConfigurationDedicated*. The NCR-Fwd receives on the backhaul
link or transmits on the access link only in symbols indicated as
downlink by *tdd-UL-DL-ConfigurationCommon* and, if provided,
*tdd-UL-DL-ConfigurationDedicated*. The NCR-Fwd receives on the access
link or transmits on the backhaul link only in symbols indicated as
uplink by *tdd-UL-DL-ConfigurationCommon* and, if provided,
*tdd-UL-DL-ConfigurationDedicated*.

If the NCR does not support simultaneous transmissions on control link
and the backhaul link, the NCR-Fwd does not transmit over a time
resource if the NCR-MT transmits over the time resource.

When the NCR simultaneously receives via both the control link and the
backhaul link in a set of symbols, a TCI state for receptions on the
backhaul link is same as a TCI state for receptions on the control link
in the set of symbols. When the NCR simultaneously transmits via both
the control link and the backhaul link in a set of symbols, a spatial
filter for transmissions on the backhaul link is same as a spatial
filter for transmissions on the control link in the set of symbols.

When the NCR does not simultaneously receive on the control link and the
backhaul link

\- if the NCR does not support determination of a TCI state for
receptions on the backhaul link based on an indication of a TCI state by
the serving cell, or if the NCR does not receive an indication of a TCI
state, for receptions on the backhaul link \[11, TS 38.321\]

\- if the NCR does not receive an indication of a unified TCI state for
receptions by the NCR-MT, receptions on the backhaul link use same QCL
parameters as the ones for PDCCH receptions in a CORESET with the lowest
*controlResourceSetId* in the active DL BWP

\- else, receptions on the backhaul link use the QCL parameters provided
by an indicated unified TCI state for receptions by the NCR-MT

\- else receptions on the backhaul link use QCL parameters provided by a
TCI state in NCR Downlink Backhaul Link Beam Indication MAC CE \[11, TS
38.321\].

When the NCR does not simultaneously transmit on the control link and
the backhaul link

\- if the NCR does not support determination of a spatial filter for
transmissions on the backhaul link based on an indication of a unified
TCI state or of an SRI by the serving cell, or if the NCR-MT does not
receive an indication of a unified TCI state or of an SRI for
determining a spatial filter, for transmissions on the backhaul link

\- if the NCR does not receive an indication of a unified TCI state for
transmissions by the NCR-MT, transmissions on the backhaul link use a
same spatial filter as the one associated with the PUCCH resource with
the smallest *pucch-ResourceId* in *PUCCH-ResourceSet* in the active UL
BWP

\- else, transmissions on the backhaul link use a spatial filter
corresponding to the indicated unified TCI state for transmissions by
the NCR-MT.

\- else transmissions on the backhaul link use a spatial filter
corresponding to a unified TCI state or an SRI provided in NCR Uplink
Backhaul Link Beam Indication MAC CE \[11, TS 38.321\].

If the NCR receives an indication of a TCI state for receptions on the
backhaul link in a MAC CE command, or an indication of a unified TCI
state or of an SRI for determining a spatial filter for transmissions on
the backhaul link in a MAC CE command, the NCR applies the MAC CE
command from the first slot that is after slot
$k + 3 \bullet N_{slot}^{subframe,\mu}$ where $k$ is the slot where the
NCR-MT would transmit a PUCCH with HARQ-ACK information associated with
the PDSCH providing the MAC CE command, $N_{slot}^{subframe,\mu}$ is a
number of slots per subframe for the SCS configuration $\mu$ of the
PUCCH transmission.

The NCR-Fwd uses a same beam for transmissions and receptions on the
access link during respective time resources associated with a same beam
index.

The NCR can be provided by *periodicFwdRsrcSetToAddModList* a list of
sets of resources for transmissions or receptions on the access link. A
set of resources, from the list of sets of resources, is provided by
*NCR-PeriodicFwdResourceSet* and occurs with a periodicity provided by
*periodicityAndOffset-r18*. A resource from the set of resources is
provided by *NCR-PeriodicFwdResource* and includes a pair of a time
resource provided by *periodicTimeRsrc* and a beam \[20, TS 38.106\]
with an index provided by *beamIndex*. The time resource starts at a
slot that is offset by a number of slots provided by
*periodicityAndOffset-r18* from the start of the period for the set of
resources and at a symbol that is offset by *symbolOffset* from the
start of the slot, and has a duration provided by *durationInSymbols*
for a SCS provided by *referenceSCS* and the *cyclicPrefix* of the
active DL BWP.

The NCR can be provided by *semiPersistentFwdRsrcSetToAddModList* a list
of sets of resources for transmissions or receptions on the access link
and the NCR Access Link Beam Indication MAC CE command can indicate a
set of resources for the NCR to use or to stop using based on a
corresponding identity provided by *semiPersistentFwdRsrcSetId* \[11, TS
38.321\]. The NCR uses or stops using the set of resources starting from
the first slot that is after slot $k + 3N_{slot}^{subframe,\mu}$ where
$k$ is the slot where the NCR-MT would transmit a PUCCH with HARQ-ACK
information associated with the PDSCH providing the MAC CE command and
$\mu$ is the SCS configuration for the PUCCH transmission. The set of
resources is provided by *NCR-SemiPersistentFwdResourceSet* and occurs
with a periodicity provided by *periodicityAndOffset-r18*. A resource
from the set of resources is provided by *NCR-SemiPersistentFwdResource*
and includes a pair of a time resource provided by
*semiPersistentTimeRsrc* and a beam with an index provided by
*beamIndex*, where *beamIndex* can be updated by the NCR Access Link
Beam Indication MAC CE command. The time resource starts at a slot that
is offset by a number of slots provided by *periodicityAndOffset-r18*
from the start of the period for the set of resources and at a symbol
that is offset by *symbolOffset* from the start of the slot, and has a
duration provided by *durationInSymbols* for a SCS provided by
*referenceSCS* and the *cyclicPrefix* of the active DL BWP.

The NCR-MT can be configured to monitor PDCCH according to USS sets for
detection of a DCI format 2_8 with CRC scrambled by an NCR-RNTI. A time
resource and a corresponding beam index for transmissions or receptions
on the access link are indicated by corresponding fields in DCI format
2_8 \[4, TS 38.212\]. When the NCR detects more than one DCI formats 2_8
that indicate beam indexes for time resources overlapping in a set of
symbols, the NCR uses for the set of symbols a beam index that is
indicated by a DCI format 2_8 that the NCR-MT detects in a most recent
PDCCH monitoring occasion. If the NCR detects a DCI format 2_8
indicating more than one time resources that overlap in a set of
symbols, the NCR expects that beam indexes associated with the more than
one time resources have a same value. The time resource starts at a slot
that is offset by *slotOffsetAperiodic* slots from a reference slot and
at a symbol that is offset by *symbolOffset* from the start of the slot,
and has a duration provided by *durationInSymbols* for a SCS provided by
*referenceSCS* and the *cyclicPrefix* of the active DL BWP. The
reference slot is the first slot with the SCS provided
by *referenceSCS* that starts no earlier than the start of a slot that
is after a slot of a PDCCH reception that provides the DCI format 2_8 by
a number of slots indicated by *ncr-AperiodicBeamInd-AccessLink* \[18,
TS 38.306\] with the SCS of PDCCH reception.

If

\- a first time resource provided by *NCR-SemiPersistentFwdResourceSet*
is indicated by the NCR Access Link Beam Indication MAC CE command and
is associated with a first beam index, and

\- a second time resource is provided by *NCR-PeriodicFwdResourceSet*
and is associated with a second beam index, and

\- the first time resource overlaps with the second time resource in a
set of symbols,

the NCR applies, for transmissions or receptions on the access link in
the set of symbols, the second beam index if only
*NCR-PeriodicFwdResourceSet* includes *priorityFlag*, and the first beam
index otherwise.

If

\- a first time resource is provided by *NCR-PeriodicFwdResourceSet*, or
provided by *NCR-SemiPersistentFwdResourceSet* and indicated by the NCR
Access Link Beam Indication MAC CE command, and is associated with a
first beam index, and

\- a second time resource is indicated by DCI format 2_8 and is
associated with a second beam index provided by the DCI format 2_8, and

\- the first time resource overlaps with the second time resource in a
set of symbols,

the NCR applies, for transmissions or receptions on the access link in
the set of symbols,

\- the first beam index if *NCR-PeriodicFwdResourceSet* or
*NCR-SemiPersistentFwdResourceSet* includes *priorityFlag*, and

\- the second beam index if *NCR-PeriodicFwdResourceSet* or
*NCR-SemiPersistentFwdResourceSet* does not include *priorityFlag*.

The NCR does not expect overlapping time resources provided by either
*NCR-PeriodicFwdResourceSet* or *NCR-SemiPersistentFwdResourceSet* to be
associated with different beam indexes.