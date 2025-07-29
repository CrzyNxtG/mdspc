### 9.1.4 Type-3 HARQ-ACK codebook determination

If a UE is provided *pdsch-HARQ-ACK-OneShotFeedback* or
*pdsch-HARQ-ACK-EnhType3ToAddModList*, the UE determines
${\widetilde{o}}_{0}^{ACK},{\widetilde{o}}_{1}^{ACK},\ldots,{\widetilde{o}}_{O_{ACK} - 1}^{ACK}$
HARQ-ACK information bits, for a total number of $O_{ACK}$ HARQ-ACK
information bits, of a Type-3 HARQ-ACK codebook according to the
following procedure. If the UE is provided
*pdsch-HARQ-ACK-EnhType3ToAddModList* and a DCI format scheduling PDSCH
reception and triggering the Type-3 HARQ-ACK codebook includes an
enhanced Type 3 codebook indicator field that provides a value for
*pdsch-HARQ-ACK-EnhType3Index*, the UE determines a size of a set of
indicated serving cells $N_{cells}^{DL,ind}$ and a size of a set of
indicated HARQ process numbers $N_{HARQ,c}^{DL,ind}$ for each indicated
serving cell and each indicated HARQ process number from the entry in
*pdsch-HARQ-ACK-EnhType3ToAddModList* corresponding to the
*pdsch-HARQ-ACK-EnhType3Index* value. Each bit from MSB to LSB provided
by *perCC* corresponds to a serving cell in ascending order of serving
cell index, where value \'1\' or value \'0\' indicate HARQ-ACK for the
corresponding serving cell is included or not included in the Type 3
HARQ-ACK codebook, respectively. Each bit string provided by *perHARQ*
corresponds to a serving cell in ascending order of serving cell index,
and each bit from MSB to LSB within a bit string corresponds to a HARQ
process number on a corresponding serving cell in ascending order of
HARQ process number, where value \'1\' or value \'0\' indicate HARQ-ACK
for the corresponding HARQ process number on the corresponding serving
cell is included or not included in the Type 3 HARQ-ACK codebook,
respectively. If the DCI format does not include the enhanced Type 3
codebook indicator field, the *pdsch-HARQ-ACK-EnhType3Index* value is
zero.

Set $N_{cells}^{DL}$ to the number of configured serving cells or, when
applicable, to $N_{cells}^{DL,ind}$.

Set $N_{HARQ,c}^{DL}$ to the value of *nrofHARQ-ProcessesForPDSCH* or
*nrofHARQ-ProcessesForPDSCH-v1700* for serving cell $c$, if provided;
else, set $N_{HARQ,c}^{DL} = 8$ . When applicable, set $N_{HARQ,c}^{DL}$
to $N_{HARQ,c}^{DL,ind}$.

Set $N_{TB,c}^{DL}$ to the maximum value of
*maxNrofCodeWordsScheduledByDCI* in *PDSCH-config* and
*PDSCH-configMulticast* for serving cell $c$ if
*harq-ACK-SpatialBundlingPUCCH* is provided and ${NDI}_{HARQ} = 0$, or
if *harq-ACK-SpatialBundlingPUCCH* is not provided, or if
*maxCodeBlockGroupsPerTransportBlock* is provided for serving cell $c$;
else, set $N_{TB,c}^{DL} = 1$.

Set $N_{HARQ - ACK,c}^{CBG/TB,max}$ to the number of HARQ-ACK
information bits per TB for PDSCH receptions on serving cell $c$ as
described in clause 9.1.1 if *maxCodeBlockGroupsPerTransportBlock* is
provided for serving cell $c$ and *pdsch-HARQ-ACK-OneShotFeedbackCBG* or
*pdsch-HARQ-ACK-EnhType3CBG* corresponding to the
*pdsch-HARQ-ACK-EnhType3Index* value is provided; else, set
$N_{HARQ - ACK,c}^{CBG/TB,max} = 0$. A UE provided with
*pdsch-HARQ-ACK-OneShotFeedbackCBG* or *pdsch-HARQ-ACK-EnhType3CBG* does
not expect to be provided with different values of
*maxCodeBlockGroupsPerTransportBlock* for different priority indexes in
*pdsch-CodeBlockGroupTransmissionList* for serving cell *c.*

Set ${NDI}_{HARQ} = 0$ if *pdsch-HARQ-ACK-OneShotFeedbackNDI* or
*pdsch-HARQ-ACK-EnhType3NDI* is provided; else set ${NDI}_{HARQ} = 1$.

Set $c = 0$ -- serving cell index in the set of serving cells

Set $h = 0$ -- HARQ process number index in the set of numbers of HARQ
processes

Set $t = 0$ -- TB index

Set $g = 0$ -- CBG index

Set $j = 0$

while ${c < N}_{cells}^{DL}$

while $h < N_{HARQ,c}^{DL}$

if *downlinkHARQ-FeedbackDisabled* is not provided, or is provided and
indicates enabled HARQ-ACK information for $h$, or
*harq-feedbackEnablingforSPSactive* is provided and enabled and $h$
corresponds to a transport block in a first SPS PDSCH reception after an
activation of SPS PDSCH receptions

if ${NDI}_{HARQ} = 0$

if $N_{HARQ - ACK,c}^{CBG/TB,max} > 0$

while $t < N_{TB,c}^{DL}$

> while $g < N_{HARQ - ACK,c}^{CBG/TB,max}$
>
> ${\widetilde{o}}_{j}^{ACK}$= HARQ-ACK information bit for CBG $g$ of
> TB $t$ for HARQ process number index $h$ in the set of numbers of HARQ
> processes of serving cell $c$, if any; else,
> ${\widetilde{o}}_{j}^{ACK} = 0$
>
> $j = j + 1$
>
> $g = g + 1$
>
> end while
>
> ${\widetilde{o}}_{j}^{ACK}$= NDI value indicated in the DCI format
> corresponding to the HARQ-ACK information bit(s) for TB $t$ for HARQ
> process number index $h$ in the set of numbers of HARQ processes on
> serving cell $c$, if any; else, ${\widetilde{o}}_{j}^{ACK} = 0$
>
> $g = 0$
>
> $j = j + 1$
>
> $t = t + 1$
>
> end while

else

> while $t < N_{TB,c}^{DL}$
>
> ${\widetilde{o}}_{j}^{ACK}$= HARQ-ACK information bit for TB $t$ for
> HARQ process index $h$ in the set of numbers of HARQ processes of
> serving cell $c$, if any; else, ${\widetilde{o}}_{j}^{ACK} = 0$
>
> $j = j + 1$
>
> ${\widetilde{o}}_{j}^{ACK}$= NDI value indicated in the DCI format
> corresponding to the HARQ-ACK information bit(s) for TB $t$ for HARQ
> process number index $h$ in the set of numbers of HARQ processes on
> serving cell $c$, if any; else, ${\widetilde{o}}_{j}^{ACK} = 0$
>
> $j = j + 1$
>
> $t = t + 1$
>
> end while

end if

$t = 0$

else

if $N_{HARQ - ACK,c}^{CBG/TB,max} > 0$

> while $t < N_{TB,c}^{DL}$
>
> if UE has obtained HARQ-ACK information for TB $t$ for HARQ process
> number index $h$ in the set of numbers of HARQ processes on serving
> cell $c$ corresponding to a PDSCH reception and has not reported the
> HARQ-ACK information corresponding to the PDSCH reception
>
> while $g < N_{HARQ - ACK,c}^{CBG/TB,max}$
>
> ${\widetilde{o}}_{j}^{ACK}$= HARQ-ACK information bit for CBG $g$ of
> TB $t$ for HARQ process number index $h$ in the set of numbers of HARQ
> processes of serving cell $c$
>
> $j = j + 1$
>
> $g = g + 1$
>
> end while
>
> else
>
> while $g < N_{HARQ - ACK,c}^{CBG/TB,max}$
>
> ${\widetilde{o}}_{j}^{ACK} = NACK$
>
> $j = j + 1$
>
> $g = g + 1$
>
> end while
>
> end if
>
> $g = 0$
>
> $t = t + 1$
>
> end while

else

> while $t < N_{TB,c}^{DL}$
>
> if UE has obtained HARQ-ACK information for TB $t$ for HARQ process
> number index $h$ in the set of numbers of HARQ processes on serving
> cell $c$ corresponding to a PDSCH reception and has not reported the
> HARQ-ACK information corresponding to the PDSCH reception
>
> if *harq-ACK-SpatialBundlingPUCCH* is not provided
>
> ${\widetilde{o}}_{j}^{ACK}$= HARQ-ACK information bit for TB $t$ for
> HARQ process number index $h$ in the set of numbers of HARQ processes
> of serving cell $c$
>
> else
>
> ${\widetilde{o}}_{j}^{ACK}$= binary AND operation of the HARQ-ACK
> information bits corresponding to first and second transport blocks
> for HARQ process number index $h$ in the set of numbers of HARQ
> processes of serving cell $c$. If the UE receives one transport block,
> the UE assumes ACK for the second transport block
>
> end if
>
> $j = j + 1$
>
> $t = t + 1$
>
> else
>
> ${\widetilde{o}}_{j}^{ACK} = NACK$
>
> $j = j + 1$
>
> $t = t + 1$
>
> end if
>
> end while

end if

$t = 0$

end if

end if

$h = h + 1$

end while

$h = 0$

$c = c + 1$

end while

If $N_{TB,c}^{DL} > 1$, when a UE receives a PDSCH with one transport
block, the HARQ-ACK information is associated with the first transport
block.

If a UE receives a SPS PDSCH, or a PDSCH that is scheduled by a DCI
format that does not support CBG-based PDSCH receptions for a serving
cell $c$, and if *maxCodeBlockGroupsPerTransportBlock* is provided for
serving cell $c$, and *pdsch-HARQ-ACK-OneShotFeedbackCBG* or
*pdsch-HARQ-ACK-EnhType3CBG* corresponding to the
*pdsch-HARQ-ACK-EnhType3Index* value is provided, the UE repeats
$N_{HARQ - ACK,c}^{CBG/TB,max}$ times the HARQ-ACK information for the
transport block, if any, in the PDSCH.

If a UE detects a DCI format that includes a One-shot HARQ-ACK request
field with value 1, the UE determines a PUCCH or a PUSCH to multiplex a
Type-3 HARQ-ACK codebook for transmission in a slot as described in
clauses 9.2.3 and 9.2.5. If the UE is provided a periodic cell switching
pattern for PUCCH transmissions by *pucch-sSCellPattern*, the UE
determines the slot and a corresponding cell based on the periodic cell
switching pattern as described in clause 9.A. The UE multiplexes only
the Type-3 HARQ-ACK codebook in the PUCCH or the PUSCH for transmission
in the slot. If the UE is provided
*pdsch-HARQ-ACK-EnhType3ToAddModList*, the UE expects that HARQ-ACK
information in a Type-1 or Type-2 HARQ-ACK codebook in a slot is
associated with HARQ process(es) of the Type-3 HARQ-ACK codebook in the
slot.

If

\- a UE detects a DCI format that includes a One-shot HARQ-ACK request
field with value 1, and

\- the CRC of the DCI is scrambled by a C-RNTI or an MCS-C-RNTI, and

if for one or more serving cells

\- *resourceAllocation* = *resourceAllocationType0* and all bits of the
frequency domain resource assignment field in the DCI format are equal
to 0, or

\- *resourceAllocation* = *resourceAllocationType1* and all bits of the
frequency domain resource assignment field in the DCI format are equal
to 1, or

\- *resourceAllocation = dynamicSwitch* and all bits of the frequency
domain resource assignment field in the DCI format are equal to 0 or 1

the DCI format provides a request for a Type-3 HARQ-ACK codebook report
and does not schedule a PDSCH reception on the one or more serving
cells. If the UE is provided *pdsch-HARQ-ACK-EnhType3ToAddModList* and
the DCI format includes an enhanced Type 3 codebook indicator field that
provides a value for *pdsch-HARQ-ACK-EnhType3Index*, the UE determines a
size of a set of indicated serving cells $N_{cells}^{DL,ind}$ and a size
of a set of indicated HARQ process numbers $N_{HARQ,c}^{DL,ind}$ for
each indicated serving cell
$and\ each\ indicated\ HARQ\ process\ number$ from the entry in
*pdsch-HARQ-ACK-EnhType3ToAddModList* corresponding to the
*pdsch-HARQ-ACK-EnhType3Index* value. If the DCI format does not include
the enhanced Type 3 codebook indicator field, the
*pdsch-HARQ-ACK-EnhType3Index* value is provided by the value of

\- the MCS field for transport block 1 if the DCI format is DCI format
1_1,

\- the MCS field if the DCI format is DCI format 1_2,

\- the MCS field for transport block 1 of a serving cell with smallest
index among the one or more serving cells if the DCI format is DCI
format 1_3.

The UE is expected to provide HARQ-ACK information in response to the
request for the Type-3 HARQ-ACK codebook after $N$ symbols from the last
symbol of a PDCCH providing the DCI format without scheduling any PDSCH
reception, where the value of $N$ is provided in clause 10.2 by
replacing \"SPS PDSCH release\" with \"DCI format\".

If a UE multiplexes HARQ-ACK information in a PUSCH transmission, the UE
generates the HARQ-ACK codebook as described in this clause except that
*harq-ACK-SpatialBundlingPUCCH* is replaced by
*harq-ACK-SpatialBundlingPUSCH*.