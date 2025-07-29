## 17.1A Second procedures for RedCap UE

In this clause, the term \'UE\' refers to a RedCap UE that indicates
*supportOfERedCap*.

A UE that has not indicated *eRedCapNotReducedBB-BW* does not expect to
transmit a PUSCH over a bandwidth that is larger than 25 PRBs for 15 kHz
SCS, or larger than 12 PRBs for 30 kHz SCS, per hop in a slot.

A UE that has not indicated *eRedCapNotReducedBB-BW* does not expect to
process a PDSCH reception that is scheduled by a DCI format with CRC
scrambled by a C-RNTI, CS-RNTI, MCS-C-RNTI, G-RNTI for multicast, or
G-CS-RNTI, or is associated with a SPS PDSCH configuration activated by
a DCI format with CRC scrambled by CS-RNTI or G-CS-RNTI, over a number
of PRBs that is larger than 25 PRBs for 15 kHz SCS, or larger than 12
PRBs for 30 kHz SCS, in a slot.

A UE that has not indicated *eRedCapNotReducedBB-BW* is not required to
process a PDSCH reception in slot $n$ that is scheduled by a DCI format
with CRC scrambled by a G-RNTI for broadcast or a MCCH-RNTI over a
number of PRBs that is larger than 25 PRBs for 15 kHz SCS, or larger
than 12 PRBs for 30 kHz SCS, when the PDSCH reception is with
repetitions or when the UE receives another PDSCH in slot $n + 1$.

A UE that has not indicated *eRedCapNotReducedBB-BW* is not required to
process a PDSCH reception that is scheduled by a DCI format with CRC
scrambled by Multicast MCCH-RNTI or G-RNTI for multicast in RRC_INACTIVE
state over a number of PRBs that is larger than 25 PRBs for 15 kHz SCS,
or larger than 12 PRBs for 30 kHz SCS, in a slot.

A UE is not required to process a PDSCH reception that is scheduled by a
DCI format with CRC scrambled by a TC-RNTI over a number of PRBs that is
larger than 25 PRBs for 15 kHz SCS, or larger than 12 PRBs for 30 kHz
SCS, in a slot.

A UE does not expect to transmit a PUSCH over a bandwidth that is larger
than 25 PRBs for 15 kHz SCS, or larger than 12 PRBs for 30 kHz SCS, per
hop in a slot, where the PUSCH is scheduled by RAR UL grant or by a DCI
scrambled by a TC-RNTI, or is configured for a Type-2 random access
procedure.

When

\- a UE receives a PDSCH scheduled by a DCI format with CRC scrambled by
a RA-RNTI or a MsgB-RNTI over a number of PRBs that is larger than 25
PRBs for 15 kHz SCS or larger than 12 PRBs for 30 kHz SCS, and

\- the PDSCH includes a RAR message with an RAR UL grant scheduling a
Msg3 PUSCH transmission from the UE, as described in Clauses 8.2 and
8.2A

the UE transmits the Msg3 PUSCH if a time between the last symbol of a
PDSCH reception conveying the RAR message and the first symbol of the
Msg3 PUSCH transmission is not smaller than $N_{T,1} + N_{T,2} + 1.5$
msec for 15 kHz SCS or $N_{T,1} + N_{T,2} + 1.0$ msec for 30 kHz SCS
where $N_{T,1}$ and $N_{T,2}$ are defined in clause 8.3; otherwise, the
UE behaviour is based on UE implementation.

When

\- a UE receives a PDSCH scheduled by a DCI format with CRC scrambled by
a RA-RNTI or a MsgB-RNTI over a number of PRBs that is larger than 25
PRBs for 15 kHz SCS or larger than 12 PRBs for 30 kHz SCS, and

\- the UE does not correctly receive the transport block provided by the
PDSCH, or if the higher layers at the UE do not identify a RAPID
associated with a corresponding PRACH transmission from the UE

if requested by higher layers, the UE shall be ready to transmit a PRACH
no later than $N_{T,1} + 1.75$ msec for 15 kHz SCS, or no later than
$N_{T,1} + 1.25$ msec for 30 kHz SCS, after the last symbol of the PDSCH
reception, or after the last symbol of the window as described in
Clauses 8.2 and 8.2A.

When

\- a UE receives a PDSCH scheduled by a DCI format with CRC scrambled by
MsgB-RNTI over a number of PRBs that is larger than 25 PRBs for 15 kHz
SCS or larger than 12 PRBs for 30 kHz SCS, and

\- the PDSCH includes a RAR message that is for successRAR for the UE as
described in Clause 8.2A

the UE transmits a PUCCH with HARQ-ACK information if a time between the
last symbol of the PDSCH reception conveying the RAR message and the
first symbol of the PUCCH transmission is not smaller than
$N_{T,1} + 1.5$ msec for 15 kHz SCS or $N_{T,1} + 1.0$ msec for 30 kHz
SCS; otherwise, the UE behaviour is based on UE implementation.