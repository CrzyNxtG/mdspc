### 9.1.3 Type-2 HARQ-ACK codebook determination

This clause applies if the UE is configured with
*pdsch-HARQ-ACK-Codebook = dynamic* or with
*pdsch-HARQ-ACK-Codebook-r16*. Unless stated otherwise, a
PDSCH-to-HARQ_feedback timing indicator field provides an applicable
value. In clauses 9.1.3, 9.1.3.1, 9.1.3.2 and 9.1.3.3, if the UE is
provided for only one of *pdsch-HARQ-ACK-Codebook = dynamic* or
*pdsch-HARQ-ACK-Codebook-r16* for unicast HARQ-ACK-ACK codebook, or
*pdsch-HARQ-ACK-Codebook = dynamic* for multicast HARQ-ACK codebook, the
Type-2 HARQ-ACK codebook is generated considering only one of respective
unicast or multicast configurations for PDSCH receptions or for PDCCH
monitoring for detection of DCI formats.

A UE does not expect to multiplex in a Type-2 HARQ-ACK codebook HARQ-ACK
information that is in response to a detection of a DCI format that does
not include a counter DAI field.

If a UE is provided *downlinkHARQ-FeedbackDisabled* indicating disabled
HARQ-ACK information for a HARQ process associated with a transport
block for PDCCH monitoring occasion $m$ or for SPS PDSCH receptions on
serving cell $c$, the UE does not multiplex a HARQ-ACK information bit
corresponding to the transport block in a Type-2 HARQ-ACK codebook and
does not consider the transport block as received in the determination
of $N_{m,c}^{received}$ or of $N_{\text{SPS,c}}$ in clause 9.1.3.1. If
the UE is also provided *PDSCH-CodeBlockGroupTransmission*, the UE does
not multiplex HARQ-ACK information bits corresponding to CBGs of the
transport block in the Type-2 HARQ-ACK codebook and does not consider
the CBGs as received in the determination of $N_{m,c}^{received,CBG}$ in
clause 9.1.3.1. If the UE is also provided
*harq-feedbackEnablingforSPSactive* = \'*enabled\'*, the UE considers a
HARQ process associated with a transport block in a first SPS PDSCH
reception, after an activation of SPS PDSCH receptions, to have enabled
HARQ-ACK information and the UE provides a HARQ-ACK information bit
according to a decoding outcome for the transport block in the first SPS
PDSCH reception.

If a UE is indicated to not provide multicast HARQ-ACK information, as
described in clause 18, associated with PDCCH monitoring occasion $m$ or
for SPS PDSCH receptions on serving cell $c$, the UE does not multiplex
corresponding HARQ-ACK information bits in a Type-2 HARQ-ACK codebook
and does not consider any transport blocks as received in the
determination of $N_{m,c}^{received}$ or of $N_{\text{SPS,c}}$ in clause
9.1.3.1.

If a UE receives a first DCI format that the UE detects in a first PDCCH
monitoring occasion and includes a PDSCH-to-HARQ_feedback timing
indicator field providing an inapplicable value from
*dl-DataToUL-ACK-r16* or *dl-DataToUL-ACK-r17*,

\- if the UE detects a second DCI format, the UE multiplexes the
corresponding HARQ-ACK information in a PUCCH or PUSCH transmission in a
slot that is indicated by a value of a PDSCH-to-HARQ_feedback timing
indicator field in the second DCI format, where

\- if the UE is not provided *pdsch-HARQ-ACK-Codebook-r16*, the UE
detects the second DCI format in any PDCCH monitoring occasion after the
first one, and where the slot indicated by the value of the
PDSCH-to-HARQ_feedback timing indicator field in the second DCI format
is no later than a slot for HARQ-ACK information in response to a SPS
PDSCH reception, if any, received after the PDSCHs scheduled by the
first DCI format.

\- if the UE is provided *pdsch-HARQ-ACK-Codebook-r16*, the UE detects
the second DCI format in any PDCCH monitoring occasion after the first
one, and the second DCI format indicates a HARQ-ACK information report
for a same PDSCH group index as indicated by the first DCI format as
described in clause 9.1.3.3, and where the slot indicated by the value
of the PDSCH-to-HARQ_feedback timing indicator field in the second DCI
format is no later than a slot for HARQ-ACK information in response to a
SPS PDSCH reception, if any, received after the PDSCHs scheduled by the
first DCI format.

\- if the UE is provided *pdsch-HARQ-ACK-Codebook-r16*, the UE receives
the second DCI format later than the slot for HARQ-ACK information in
response to a SPS PDSCH reception received after the PDSCHs scheduled by
the first DCI format, and the second DCI format indicates a HARQ-ACK
information report for a same PDSCH group index as indicated by the
first DCI format as described in clause 9.1.3.3.

\- if the UE is provided *pdsch-HARQ-ACK-OneShotFeedback*, the first DCI
format does not have associated HARQ-ACK information without scheduling
a PDSCH reception or TCI state update, the UE detects the second DCI
format in any PDCCH monitoring occasion after the first one, and the
second DCI format includes a One-shot HARQ-ACK request field with value
1, the UE includes the HARQ-ACK information in a Type-3 HARQ-ACK
codebook, as described in clause 9.1.4, and where the slot indicated by
the value of the PDSCH-to-HARQ_feedback timing indicator field in the
second DCI format is no later than a slot for HARQ-ACK information in
response to a SPS PDSCH reception, if any, received after the PDSCHs
scheduled by the first DCI format.

\- if the UE is provided *pdsch-HARQ-ACK-OneShotFeedback-r16*, the first
DCI format does not have associated HARQ-ACK information without
scheduling a PDSCH reception or TCI state update, and the UE receives
the second DCI format later than the slot for HARQ-ACK information in
response to a SPS PDSCH reception received after the PDSCHs scheduled by
the first DCI format, and the second DCI format includes a One-shot
HARQ-ACK request field with value 1, the UE includes the HARQ-ACK
information in a Type-3 HARQ-ACK codebook, as described in clause 9.1.4.

\- otherwise, the UE does not multiplex the corresponding HARQ-ACK
information in a PUCCH or PUSCH transmission.