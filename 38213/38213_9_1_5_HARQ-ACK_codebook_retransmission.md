### 9.1.5 HARQ-ACK codebook retransmission

With reference to slots of PUCCH transmissions on the primary cell and
for Type-1 or Type-2 HARQ-ACK codebooks, a UE that transmitted or would
transmit a PUCCH or a PUSCH with a first HARQ-ACK codebook in slot $m$
can be indicated by a DCI format with CRC scrambled by a C-RNTI or a
MCS-C-RNTI that does not schedule a PDSCH reception \[4, TS 38.212\] on
one or more serving cells and is received in a PDCCH ending in slot $n$,
to transmit a PUCCH with the first HARQ-ACK codebook in slot $n + k$,
where slot $n + k$ is after slot $m$. The UE determines $k$ and a
resource for the PUCCH transmission as described in clauses 9.2.3 and
9.2.5. If the UE is provided a periodic cell switching pattern for PUCCH
transmissions by *pucch-sSCellPattern*, the UE further determines a
corresponding cell based on the periodic cell switching pattern as
described in clause 9.A.

If the HARQ-ACK retransmission indicator field value in a DCI format is
\'1\', the UE determines slot $m$ as $m = n - l$ where $l$ is determined
by a one-to-one mapping in ascending order among the values from -7 to
24 and the values of

\- the MCS field for transport block 1 if the DCI format is DCI format
1_1

\- the MCS field if the DCI format is DCI format 1_2

\- the MCS field for transport block 1 for a serving cell if the DCI
format is DCI format 1_3, where the serving cell is the one with
smallest index that has

\- *resourceAllocation* = *resourceAllocationType0* and all bits of the
corresponding block of the frequency domain resource assignment field
equal to 0, or

\- *resourceAllocation* = *resourceAllocationType1* and all bits of the
corresponding block of the frequency domain resource assignment field
equal to 1, or

\- *resourceAllocation = dynamicSwitch* and all bits of the
corresponding block of the frequency domain resource assignment field
equal to 0 or 1

If the DCI format includes a priority indicator field having a value, a
priority value of first HARQ-ACK information in the first HARQ-ACK
codebook is same as the value of the priority indicator field;
otherwise, the priority value of the first HARQ-ACK information is zero.

If a UE

\- is not provided *coresetPoolIndex* or is provided *coresetPoolIndex*
with a value of 0 for first CORESETs on active DL BWPs of serving cells,
and

\- is provided *coresetPoolIndex* with a value of 1 for second CORESETs
on active DL BWPs of the serving cells, and

\- is provided *ackNackFeedbackMode* = *separate*

the first HARQ-ACK codebook is associated with the first CORESETs or
with the second CORESETs, as described in clause 9, when the UE receives
the PDCCH providing the DCI format in a CORESET from the first CORESETs
or from the second CORESETs, respectively.

If the UE would also multiplex in the PUCCH transmission in slot $n + k$
a second HARQ-ACK codebook with second HARQ-ACK information of same
priority value as for the first HARQ-ACK information in the first
HARQ-ACK codebook, the UE appends the first HARQ-ACK codebook to the
second HARQ-ACK codebook. The UE determines to multiplex the second
HARQ-ACK information in the PUCCH transmission in slot $n + k$ as
described in clause 9.2.3. $O_{ACK}$ is the total number of the first
HARQ-ACK information bits and the second HARQ-ACK information bits if
any.

If the UE performs a procedure for deferring third HARQ-ACK information
for SPS PDSCH receptions to slot $n + k$, as described in clause
9.2.5.4, and the third HARQ-ACK information has same priority value as a
priority value indicated by the DCI format triggering the PUCCH
transmission in slot $n + k$, the UE multiplexes in the PUCCH
transmission in slot $n + k$ the first HARQ-ACK information with the
priority value that results in slot $n + k$ according to the procedure
in this clause, by appending the third HARQ-ACK information to the first
HARQ-ACK information. If the UE would also multiplex in the PUCCH
transmission in slot $n + k$ the second HARQ-ACK information with the
priority value, the UE appends the first HARQ-ACK information followed
by the third HARQ-ACK information to the second HARQ-ACK information.
$O_{ACK}$ is the total number of the first HARQ-ACK information bits,
the second HARQ-ACK information bits if any and the third HARQ-ACK
information bits if any.

If in slot $m$ the UE would transmit a first PUCCH with first HARQ-ACK
information over more than one slot and a second PUCCH with second
HARQ-ACK information over one or more slots, where the first and second
HARQ-ACK information have same priority value, the UE multiplexes in the
PUCCH transmission in slot $n + k$ one of

\- the first HARQ-ACK information if the first PUCCH starts at an
earlier slot than the second PUCCH, or

\- the second HARQ-ACK information if the second PUCCH starts at an
earlier slot than the first PUCCH.

If $O_{ACK} + O_{SR} + O_{CSI} \leq 11$, the UE determines a number of
HARQ-ACK information bits for obtaining a transmission power for a
PUCCH, as described in clause 7.2.1, as
$n_{HARQ - ACK} = \ n_{HARQ - ACK,0} + n_{HARQ - ACK,1} + n_{HARQ - ACK,2}$
where

\- $n_{HARQ - ACK,0}$ is the number of HARQ-ACK information bits that
the UE determines as described in clause 9.1.2.1 or 9.1.3.1 for the
first HARQ-ACK information bits,

\- $n_{HARQ - ACK,1}$ is the number of HARQ-ACK information bits, if
any, that the UE determines as described in clause 9.1.2.1 or 9.1.3.1
for the second HARQ-ACK information bits,

\- $n_{HARQ - ACK,2}$ is determined as described in clause 9.1.2.1 or
9.1.3.1 for the third HARQ-ACK information bits for SPS PDSCH receptions
deferred to slot $n + k$, if any.