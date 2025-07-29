## 9.1 HARQ-ACK codebook determination

If a UE is provided *pdsch-HARQ-ACK-CodebookList*, the UE can be
indicated by *pdsch-HARQ-ACK-CodebookList* to generate one or two
HARQ-ACK codebooks. If the UE is indicated to generate one HARQ-ACK
codebook, the HARQ-ACK codebook is associated with a PUCCH of priority
index 0. If a UE is provided *pdsch-HARQ-ACK-CodebookList*, the UE
multiplexes in a same HARQ-ACK codebook only HARQ-ACK information
associated with a same priority index. If the UE is indicated to
generate two HARQ-ACK codebooks

> \- a first HARQ-ACK codebook is associated with a PUCCH of priority
> index 0 and a second HARQ-ACK codebook is associated with a PUCCH of
> priority index 1
>
> \- the UE is provided first and second for each of {*PUCCH-Config*,
> *UCI-OnPUSCH*, *PDSCH*-*codeBlockGroupTransmission*} by
> {*PUCCH-ConfigurationList*, *UCI-OnPUSCH-ListDCI-0-1*,
> *PDSCH-CodeBlockGroupTransmissionList*} or {*PUCCH-ConfigurationList*,
> *UCI-OnPUSCH-ListDCI-0-2*, *PDSCH-CodeBlockGroupTransmissionList*},
> respectively, for use with the first and second HARQ-ACK codebooks,
> respectively

If a UE receives a PDSCH without receiving a corresponding PDCCH, or if
the UE receives a PDCCH indicating a SPS PDSCH release, the UE generates
one corresponding HARQ-ACK information bit. If the UE generates two
HARQ-ACK codebooks, the UE is indicated by *harq-CodebookID*, per SPS
PDSCH configuration, a HARQ-ACK codebook index for multiplexing the
corresponding HARQ-ACK information bit.

If a UE is provided *pdsch-HARQ-ACK-OneShotFeedback* and the UE detects
a DCI format in any PDCCH monitoring occasion that includes a One-shot
HARQ-ACK request field with value 1

\- the UE includes the HARQ-ACK information in a Type-3 HARQ-ACK
codebook, as described in clause 9.1.4

\- the UE does not expect that the PDSCH-to-HARQ_feedback timing
indicator field of the DCI format provides an inapplicable value from
*dl-DataToUL-ACK-r16* or *dl-DataToUL-ACK-r17*

In the remaining of this clause, reference is to one HARQ-ACK codebook
and to DCI formats that schedule PDSCH reception, or have associated
HARQ-ACK information without scheduling a PDSCH reception and are
associated with the HARQ-ACK codebook.

If a UE is required to receive SPS PDSCHs in a slot according to Clause
5.1 of \[6\] and Clause 11.1 for SPS configurations that are indicated
to be released by a DCI format, the UE is not expected to receive the
DCI format in the slot if the end of the last symbol of the PDCCH
reception is after the end of a last symbol of any of the SPS PDSCH
receptions. For a SPS configuration subject to *pdsch-AggregationFactor*
or *pdsch-AggregationFactor-r16*, the UE is not expected to receive the
DCI format in a slot containing a SPS PDSCH transmission occasion other
than the first transmission occasion required to be received by the UE
for a TB.

If a UE is configured to receive SPS PDSCHs in a slot for SPS
configurations that are indicated to be released by a DCI format, and if
the UE receives the PDCCH providing the DCI format in the slot, and if
HARQ-ACK information for the SPS PDSCH release and the SPS PDSCH
receptions would be multiplexed in a same PUCCH, the UE does not expect
to receive the SPS PDSCHs, does not generate HARQ-ACK information for
the SPS PDSCH receptions, and generates a HARQ-ACK information bit for
the SPS PDSCH release.

If a UE is configured to receive SPS PDSCH(s) in a slot for SPS
configuration(s), the UE does not expect to receive a PDCCH providing a
DCI format in the slot to indicate SPS PDSCH release of these SPS
configuration(s), if HARQ-ACK information for the SPS PDSCH release and
the SPS PDSCH reception(s) would map to different PUCCHs.

If a UE detects a DCI format 1_1 or a DCI format 1_3 indicating

\- SCell dormancy without scheduling a PDSCH reception, as described in
clause 10.3, and

\- is provided *pdsch-HARQ-ACK-Codebook = dynamic* or
*pdsch-HARQ-ACK-Codebook-r16*

the UE generates a HARQ-ACK information bit as described in clause 9.1.3
for a DCI format 1_1 or a DCI format 1_3 indicating SCell dormancy
without scheduling a PDSCH reception and the HARQ-ACK information bit
value is ACK.

If a UE is not provided *PDSCH-CodeBlockGroupTransmission*, the UE
generates one HARQ-ACK information bit per transport block.

For a HARQ-ACK information bit, a UE generates a positive
acknowledgement (ACK) if the UE detects a DCI format that provides a SPS
PDSCH release or detects a DCI format that does not schedule PDSCH
reception and indicates a TCI state update or correctly decodes a
transport block, and generates a negative acknowledgement (NACK) if the
UE does not correctly decode the transport block. A HARQ-ACK information
bit value of 0 represents a NACK while a HARQ-ACK information bit value
of 1 represents an ACK.

In the following, the CRC for a DCI format is scrambled with a C-RNTI,
an MCS-C-RNTI, or a CS-RNTI, or a G-RNTI for multicast, or a G-CS-RNTI.

In the following, if the value of *maxNrofCodeWordsScheduledByDCI* is
not provided, the value of *maxNrofCodeWordsScheduledByDCI* equals one.