### 9.2.6 PUCCH repetition procedure

A UE that does not have dedicated PUCCH resource configuration and
indicates a capability to transmit with repetitions a PUCCH with
HARQ-ACK information \[11, TS 38.321\], determines a number of
$N_{\text{PUCCH}}^{\text{repeat}}$ slots for repetitions of a PUCCH
transmission with HARQ-ACK information based on an indication by
*numberOfMsg4HARQ-ACK-Repetitions*. If
*numberOfMsg4HARQ-ACK-Repetitions* provides more than one values, the
DAI field in a DCI format 1_0 with CRC scrambled by a TC-RNTI scheduling
a PDSCH reception that includes a UE contention resolution identity
indicates $N_{\text{PUCCH}}^{\text{repeat}}$ from the more than one
values. The UE transmits any PUCCH with repetitions over
$N_{\text{PUCCH}}^{\text{repeat}}$ slots before dedicated PUCCH resource
configuration is provided. The UE transmits each repetition of the PUCCH
using frequency hopping as described in Clause 9.2.1.

In the remaining of this clause, a UE without dedicated PUCCH resource
configuration determines a value of a parameter, if applicable,
according to Table 9.2.1-1 and/or as specified above in this clause for
a PUCCH transmission with repetitions from the UE.

A UE can be indicated to transmit a PUCCH over
$N_{\text{PUCCH}}^{\text{repeat}}$ slots using a PUCCH resource, where

\- if the PUCCH resource is indicated by a DCI format and includes
*pucch-RepetitionNrofSlots*, $N_{\text{PUCCH}}^{\text{repeat}}$ is
provided by *pucch-RepetitionNrofSlots*

\- otherwise, $N_{\text{PUCCH}}^{\text{repeat}}$ is provided by
*nrofSlots*

If the UE is provided *subslotLengthForPUCCH*, a slot for a PUCCH
transmission with repetitions over
$N_{\text{PUCCH}}^{\text{repeat}} > 1$ slots includes a number of
symbols indicated by *subslotLengthForPUCCH*.

For $N_{\text{PUCCH}}^{\text{repeat}} > 1$,

\- the UE repeats the PUCCH transmission with the UCI over
$N_{\text{PUCCH}}^{\text{repeat}}$ slots

\- if the UE is provided *multipanelSFN-Scheme* and
*applyIndicatedTCI-State* = \'both\', a repetition of the PUCCH
transmission simultaneously uses first and second spatial domain filters
corresponding to first and second *TCI-State* or *TCI-UL-State*

\- a repetition of the PUCCH transmission in each of the
$N_{\text{PUCCH}}^{\text{repeat}}$ slots has a same number of
consecutive symbols, as provided by *nrofSymbols*

\- a repetition of the PUCCH transmission in each of the
$N_{\text{PUCCH}}^{\text{repeat}}$ slots has a same first symbol, as
provided by *startingSymbolIndex* if *subslotLengthForPUCCH* is not
provided; otherwise mod(*startingSymbolIndex*, *subslotLengthForPUCCH*)

\- the UE is configured by *interslotFrequencyHopping* whether or not to
perform frequency hopping for repetitions of the PUCCH transmission in
different slots

\- if the UE is configured to perform frequency hopping for repetitions
of a PUCCH transmission across slots and the UE is not provided
*pucch-DMRS-Bundling* = \'enabled\'

\- the UE performs frequency hopping per slot

\- the UE transmits the PUCCH starting from a first PRB, provided by
*startingPRB*, in slots with even number and starting from a second PRB,
provided by *secondHopPRB*, in slots with odd number. The slot indicated
to the UE for the first repetition of the PUCCH transmission has number
0 and each subsequent slot until the UE transmits the PUCCH in
$N_{\text{PUCCH}}^{\text{repeat}}$ slots is counted regardless of
whether or not the UE transmits the PUCCH in the slot

\- the UE does not expect to be configured to perform frequency hopping
for a repetition of the PUCCH transmission within a slot

\- if the UE is configured to perform frequency hopping for repetitions
of a PUCCH transmission across slots and the UE is provided
*pucch-DMRS-Bundling* = \'enabled\'

\- the UE performs frequency hopping per interval of
$N_{\text{PUCCH}}^{\text{interval}}$ consecutive slots, that start from
a slot indicated to the UE and where the UE would transmit a first
repetition of the PUCCH, where $N_{\text{PUCCH}}^{\text{interval}}$ is
the value of *pucch-FrequencyHoppingInterval*, if provided; otherwise,
$N_{\text{PUCCH}}^{\text{interval}}$ is the value of
*pucch-TimeDomainWindowLength*

\- the UE transmits the PUCCH over intervals until the UE transmits the
PUCCH in $N_{\text{PUCCH}}^{\text{repeat}}$ slots, where the first
interval has number 0 and each subsequent interval is counted regardless
of whether or not the UE transmits the PUCCH in a slot

\- the UE transmits the PUCCH starting from a first PRB, provided by
*startingPRB*, in intervals with even number and starting from a second
PRB, provided by *secondHopPRB*, in intervals of frequency hopping
intervals with odd number

\- the UE does not expect to be configured to perform frequency hopping
for a repetition of the PUCCH transmission within a slot

\- if the UE is not configured to perform frequency hopping for
repetitions of a PUCCH transmission across slots and the UE is
configured to perform frequency hopping for a repetition of the PUCCH
transmission within a slot, the frequency hopping pattern between the
first PRB and the second PRB is same within each slot

If the UE determines that, for a repetition of a PUCCH transmission in a
slot, the number of symbols available for the PUCCH transmission is
smaller than the value provided by *nrofSymbols* for the corresponding
PUCCH format, the UE does not transmit the PUCCH repetition in the slot.

A SS/PBCH block symbol is a symbol of an SS/PBCH block with candidate
SS/PBCH block index corresponding to the SS/PBCH block index indicated
to a UE by *ssb-PositionsInBurst* in *SIB1* or *ssb-PositionsInBurst* in
*ServingCellConfigCommon* or, if the UE is not provided
*dl-OrJointTCI-StateList*, by *ssb-PositionsInBurst* in
*SSB-MTCAdditionalPCI* associated to physical cell ID with active TCI
states for PDCCH or PDSCH, or for a set of symbols of a slot
corresponding to SS/PBCH blocks configured for L1 beam
measurement/reporting.

For unpaired spectrum, the UE determines the
$N_{\text{PUCCH}}^{\text{repeat}}$ slots for a PUCCH transmission
starting from a slot indicated to the UE as described in clause 9.2.3
for HARQ-ACK reporting, or a slot determined as described in clause
9.2.4 for SR reporting or in clause 5.2.1.4 of \[6, TS 38.214\] for CSI
reporting and having

\- an UL symbol, as described in clause 11.1, or flexible symbol that is
not SS/PBCH block symbol provided by *startingSymbolIndex* as a first
symbol, and

\- consecutive UL symbols, as described in clause 11.1, or flexible
symbols that are not SS/PBCH block symbols, starting from the first
symbol, equal to or larger than a number of symbols provided by
*nrofsymbols*

For paired spectrum or supplementary uplink band, the UE determines the
$N_{\text{PUCCH}}^{\text{repeat}}$ slots for a PUCCH transmission as the
$N_{\text{PUCCH}}^{\text{repeat}}$ consecutive slots starting from a
slot indicated to the UE as described in clause 9.2.3 for HARQ-ACK
reporting, or a slot determined as described in clause 9.2.4 for SR
reporting or in clause 5.2.1.4 of \[6, TS 38.214\] for CSI reporting.

If a UE would transmit a PUCCH over a first number
$N_{\text{PUCCH}}^{\text{repeat}} > 1$ of slots and the UE would
transmit a PUSCH with repetition Type A or with TB processing over
multiple slots over a second number of slots, and the PUCCH transmission
would overlap with the PUSCH transmission in one or more slots, and the
conditions in clause 9.2.5 for multiplexing the UCI in the PUSCH are
satisfied in the overlapping slots, the UE transmits the PUCCH and does
not transmit the PUSCH in the overlapping slots.

If a UE would transmit a PUCCH over a first number
$N_{\text{PUCCH}}^{\text{repeat}} > 1$ of slots and the UE would
transmit a PUSCH with repetition Type B over a second number of slots,
and the PUCCH transmission would overlap with actual PUSCH repetitions
in one or more slots, and the conditions in clause 9.2.5 for
multiplexing the UCI in the PUSCH are satisfied for the overlapping
actual PUSCH repetitions, the UE transmits the PUCCH and does not
transmit the overlapping actual PUSCH repetitions.

A UE does not multiplex different UCI types in a PUCCH transmission with
repetitions over $N_{\text{PUCCH}}^{\text{repeat}} > 1$ slots. If a UE
would transmit a first PUCCH over more than one slot and at least a
second PUCCH over one or more slots, and the transmissions of the first
PUCCH and the second PUCCH would overlap in a number of slots then, for
each slot of the number of slots and with UCI type priority of HARQ-ACK
\> SR \> CSI with higher priority \> CSI with lower priority, the UE
determines an earliest first PUCCH in a slot with the order of earliest
starting symbol followed by longest duration and the second PUCCHs
overlapping with the earliest first PUCCH, and then performs the
following

\- the UE does not expect more than one PUCCH from the first PUCCH and
the second PUCCHs to start at a same slot and include a UCI type with
same priority

\- if more than one PUCCH from the first PUCCH and the second PUCCHs
include a UCI type with the same highest priority, the UE transmits the
PUCCH with the highest priority starting at an earliest slot and does
not transmit the other PUCCHs, otherwise,

\- the UE transmits the PUCCH that includes the UCI type with the
highest priority and does not transmit the PUCCHs that include the UCI
type with lower priority

The UE repeats the above procedure until there is no PUCCH overlapping
with any PUCCH with repetitions in the slot.

When a PUCCH resource used for repetitions of a PUCCH transmission by a
UE includes

\- first and second spatial settings, or first and second sets of power
control parameters, as described in \[11, TS 38.321\] and in clauses 7
and 7.2.1, or

\- first and second *TCI-State* or *TCI-UL-State* and
*applyIndicatedTCI-State* = \'both\', and the PUCCH resource does not
include *multipanelSFN-Scheme*

the UE

\- uses the first and second spatial settings or the first and second
indicated *TCI-State* or *TCI-UL-State*, or the first and second sets of
power control parameters, for first and second repetitions of the PUCCH
transmission, respectively, when $N_{\text{PUCCH}}^{\text{repeat}} = 2$,

\- alternates between the first and second spatial settings or between
the first and second indicated *TCI-State* or *TCI-UL-State*, or between
the first and second sets of power control parameters, respectively, per
$N_{\text{PUCCH}}^{\text{switch}}$ repetitions of the PUCCH
transmission, where $N_{\text{PUCCH}}^{\text{switch}} = 1$ if
*mappingPattern* = \'cyclicMapping\'; else,
$N_{\text{PUCCH}}^{\text{switch}} = 2$.

A UE does not expect a PUCCH that is in response to a DCI format
detection to overlap with any other PUCCH that does not satisfy the
corresponding timing conditions in clause 9.2.5.

If a UE would transmit a PUCCH over $N_{\text{PUCCH}}^{\text{repeat}}$
slots and the UE does not transmit the PUCCH in a slot from the
$N_{\text{PUCCH}}^{\text{repeat}}$ slots due to overlapping with another
PUCCH transmission in the slot, the UE counts the slot in the number of
$N_{\text{PUCCH}}^{\text{repeat}}$ slots.

For DAPS operation, if a UE would transmit a PUCCH over
$N_{\text{PUCCH}}^{\text{repeat}}$ slots on the source MCG and the UE
does not transmit the PUCCH in a slot from the
$N_{\text{PUCCH}}^{\text{repeat}}$ slots due to overlapping in time with
UE transmission on the target MCG in the slot, the UE counts the slot in
the number of $N_{\text{PUCCH}}^{\text{repeat}}$ slots.