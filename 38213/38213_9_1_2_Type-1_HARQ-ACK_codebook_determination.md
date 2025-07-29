### 9.1.2 Type-1 HARQ-ACK codebook determination

This clause applies if the UE is configured with
*pdsch-HARQ-ACK-Codebook = semi-static*. In clauses 9.1.2, 9.1.2.1, and
9.1.2.2, if the UE is configured with *pdsch-HARQ-ACK-Codebook =
semi-static* for only one of unicast or multicast HARQ-ACK codebook, the
Type-1 HARQ-ACK codebook is generated considering only one of respective
unicast or multicast configurations for PDSCH receptions or for PDCCH
monitoring for detection of DCI formats.

A UE does not provide a Type-1 HARQ-ACK codebook if the Type-1 HARQ-ACK
codebook would include only HARQ-ACK information for transport blocks
associated with HARQ processes with disabled HARQ-ACK information.

If a UE is provided *downlinkHARQ-FeedbackDisabled* indicating disabled
HARQ-ACK information for a HARQ process associated with a transport
block in PDSCH reception occasion $m$ on serving cell $c$, the UE
reports a NACK value for a HARQ-ACK information bit corresponding to the
transport block in a Type-1 HARQ-ACK codebook and does not consider the
transport block as received in the determination of $N_{m,c}^{received}$
in clause 9.1.2.1. If the UE is also provided
*PDSCH-CodeBlockGroupTransmission*, the UE reports NACK values for
HARQ-ACK information bits corresponding to CBGs of the transport block
in the Type-1 HARQ-ACK codebook and does not consider the CBGs as
received in the determination of $N_{m,c}^{received,CBG}$ in clause
9.1.2.1. If the UE is also provided *harq-feedbackEnablingforSPSactive*
= \'*enabled\'*, the UE considers a HARQ process associated with a
transport block in a first SPS PDSCH reception, after an activation of
SPS PDSCH receptions, to have enabled HARQ-ACK information and the UE
provides a HARQ-ACK information bit according to a decoding outcome for
the transport block in the first SPS PDSCH reception.

If a UE reports HARQ-ACK information associated with a G-RNTI for
multicast or a G-CS-RNTI with disabled HARQ-ACK information, as
described in clause 18, a value of the HARQ-ACK information is a UE
implementation choice.

A UE reports HARQ-ACK information for a corresponding PDSCH reception or
SPS PDSCH release or TCI state update only in a HARQ-ACK codebook that
the UE transmits in a slot indicated by a value of a
PDSCH-to-HARQ_feedback timing indicator field in a corresponding DCI
format or provided by *dl-DataToUL-ACK* or *dl-DataToUL-ACK-r16* or
*dl-DataToUL-ACK-DCI-1-2* or *dl-DataToUL-ACK-r17* or
*dl-DataToUL-ACK-v1700* or *dl-DataToUL-ACK-DCI-1-2-r17* if the
PDSCH-to-HARQ_feedback timing indicator field is not present in the DCI
format as described in clause 9.2.3. The UE reports NACK value(s) for
HARQ-ACK information bit(s) in a HARQ-ACK codebook that the UE transmits
in a slot not indicated by a value of a PDSCH-to-HARQ_feedback timing
indicator field in a corresponding DCI format.

If a UE is not provided *pdsch-HARQ-ACK-OneShotFeedback*, the UE does
not expect to receive a PDSCH scheduled by a DCI format that the UE
detects in any PDCCH monitoring occasion and includes a
PDSCH-to-HARQ_feedback timing indicator field providing an inapplicable
value from *dl-DataToUL-ACK-r16* or *dl-DataToUL-ACK-r17*.

If the UE is provided *pdsch-AggregationFactor-r16* in *SPS-Config*, or
*pdsch-AggregationFactor* in *PDSCH-Config* and no entry in
*pdsch-TimeDomainAllocationList* and
*pdsch-TimeDomainAllocationListDCI-1-2* includes *repetitionNumber* in
*PDSCH-TimeDomainResourceAllocation-r16*, $N_{PDSCH}^{repeat,max}$ is a
maximum value of *pdsch-AggregationFactor-r16* in *SPS-Config*, or
*pdsch-AggregationFactor* in *PDSCH-Config*; otherwise
$N_{PDSCH}^{repeat,max} = 1$. The UE reports HARQ-ACK information for a
PDSCH reception

\- from DL slot ${n_{D} - N}_{PDSCH}^{repeat} + 1$ to DL slot $n_{D}$,
if $N_{PDSCH}^{repeat}$ is provided by *pdsch-AggregationFactor* or
*pdsch-AggregationFactor-r16* \[6, TS 38.214\], or

\- from DL slot $\ n_{D} - repetitionNumber + 1$ to DL slot $n_{D}$, if
the time domain resource assignment field in the DCI format scheduling
the PDSCH reception indicates an entry containing *repetitionNumber,* or

\- in DL slot $n_{D}$, otherwise

only in a HARQ-ACK codebook that the UE includes in a PUCCH or PUSCH
transmission in slot $n + k$, where $n$ is

\- an UL slot overlapping with the end of the PDSCH reception in DL slot
$n_{D}$ if the UE is provided *subslotLengthForPUCCH* for the HARQ-ACK
codebook

\- the UL slot is on the primary cell if the UE is provided
*pucch-sSCellPattern*; otherwise, the UL slot is on the serving cell of
the PUCCH transmission

\- the last UL slot for PUCCH transmission overlapping with DL slot
$n_{D}$ if the UE is not provided *subslotLengthForPUCCH* for the
HARQ-ACK codebook

\- the last UL slot is on the primary cell if the UE is provided
*pucch-sSCellPattern*; otherwise, the last UL slot is on the serving
cell of the PUCCH transmission

and $k$ is a number of slots indicated by the PDSCH-to-HARQ_feedback
timing indicator field in a corresponding DCI format, or provided by
*dl-DataToUL-ACK* or *dl-DataToUL-ACK-r16* or *dl-DataToUL-ACK-DCI-1-2*
or *dl-DataToUL-ACK-r17* or *dl-DataToUL-ACK-v1700* or
*dl-DataToUL-ACK-DCI-1-2-r17* if the PDSCH-to-HARQ_feedback timing
indicator field is not present in the DCI format. If the UE reports
HARQ-ACK information for the PDSCH reception in a slot other than slot
$n + k$, the UE sets a value for each corresponding HARQ-ACK information
bit to NACK.

If a UE is provided *pdsch-HARQ-ACK-Codebook = \'semi-static\'* for
unicast or multicast HARQ-ACK information, the UE reports HARQ-ACK
information in a PUCCH only for one of

\- a SPS PDSCH release indicated by DCI format 1_0 or by DCI format 4_1,
with counter DAI field value of 1, or

\- a PDSCH reception providing a transport block having enabled HARQ-ACK
information report and scheduled by DCI format 1_0 or by DCI format 4_1,
with counter DAI field value of 1 on the PCell, or

\- SPS PDSCH receptions with transport blocks having enabled HARQ-ACK
information reports,

in the $M_{\text{A,c}}$ occasions for candidate PDSCH receptions as
determined in clause 9.1.2.1, in which case the UE generates a HARQ-ACK
information only for the SPS PDSCH release, or only for the PDSCH
reception, or only for SPS PDSCH receptions according to corresponding
$M_{\text{A,c}}$ occasions on respective serving cells, where the value
of counter DAI in DCI format 1_0 or in DCI format 4_1 is according to
Table 9.1.3-1 and HARQ-ACK information bits in response to more than one
SPS PDSCH receptions that the UE is configured to receive are ordered
according to the following pseudo-code; otherwise, the procedures in
clause 9.1.2.1 and clause 9.1.2.2 for a HARQ-ACK codebook determination
apply.

In the following pseudo-code, SPS PDSCH receptions associated with a SPS
PDSCH configuration are activated by a DCI format with CRC scrambled by
a CS-RNTI or by a DCI format with CRC scrambled by a G-CS-RNTI.

Set $N_{cells}^{DL}$ to the number of serving cells configured to the UE

Set $N_{c}^{SPS}$ to the number of SPS PDSCH configurations configured
to the UE for serving cell $c$

Set $N_{c}^{DL}$ to the number of DL slots for SPS PDSCH receptions on
serving cell $c$ with HARQ-ACK information multiplexed on the PUCCH

Set $j = 0$ -- HARQ-ACK information bit index

Set $c = 0$ -- serving cell index: lower indexes correspond to lower RRC
indexes of corresponding cell

while $c < N_{cells}^{DL}$

Set $s = 0$ -- SPS PDSCH configuration index: lower indexes correspond
to lower RRC indexes of corresponding SPS configurations

while $s < N_{c}^{SPS}$

Set $n_{D} = 0$ -- slot index

while $n_{D} < N_{c}^{DL}$

if {

a UE is configured to receive SPS PDSCHs from slot
$n_{D} - N_{PDSCH}^{repeat} + 1$ to slot $n_{D}$ for SPS PDSCH
configuration $s$ on serving cell $c$, excluding SPS PDSCHs that are not
required to be received in any slot among overlapping SPS PDSCHs, if any
according to \[6, TS 38.214\], or based on a UE capability for a number
of PDSCH receptions in a slot according to \[6, TS 38.214\], or due to
overlapping with a set of symbols

> \- indicated as uplink by tdd-UL-DL-ConfigurationCommon or by
> tdd-UL-DL-ConfigurationDedicated, and/or
>
> \- determined as non-active period of cell DTX \[11, TS 38.321\]

where, for unicast SPS PDSCHs, $N_{PDSCH}^{repeat}$ is provided by
*pdsch-AggregationFactor-r16* in *SPS-Config* or, if
*pdsch-AggregationFactor-r16* is not included in *SPS-Config*, by
*pdsch-AggregationFactor* in *PDSCH-config* and, for multicast SPS
PDSCHs, $N_{PDSCH}^{repeat}$ is provided by $repetitionNumber$ if
contained in an entry indicated by the time domain resource assignment
field in the DCI format scheduling the PDSCH repetition, or provided by
*pdsch-AggregationFactor-r16* if included in *SPS-Config* or, otherwise,
$N_{PDSCH}^{repeat} = 1$, and

> HARQ-ACK information for the SPS PDSCH is associated with the PUCCH
>
> }

${\widetilde{o}}_{j}^{ACK}$ = HARQ-ACK information bit for this SPS
PDSCH reception

$j = j + 1$;

end if

$n_{D} = n_{D} + 1$;

end while

$s = s + 1$;

end while

$c = c + 1$;

end while