## 5.3 SDU discard

When the successful delivery of a PDCP SDU is confirmed by PDCP status
report, the transmitting PDCP entity shall discard the PDCP SDU along
with the corresponding PDCP Data PDU.

When the *discardTimer* or *discardTimerForLowImportance* expires for a
PDCP SDU, the transmitting PDCP entity shall:

\- if *pdu-SetDiscard* is configured:

\- discard all PDCP SDUs belonging to the PDU Set to which the PDCP SDU
belongs along with the corresponding PDCP Data PDUs;

NOTE 1: PDCP SDUs subsequently received from upper layers are also
discarded if they belong to the PDU Set.

\- else:

\- discard the PDCP SDU along with the corresponding PDCP Data PDU.

If the corresponding PDCP Data PDU has already been submitted to lower
layers, the discard is indicated to lower layers.

For SRBs, when upper layers request a PDCP SDU discard, the PDCP entity
shall discard all stored PDCP SDUs and PDCP PDUs.

NOTE 2: Discarding a PDCP SDU already associated with a PDCP SN causes a
SN gap in the transmitted PDCP Data PDUs, which increases PDCP
reordering delay in the receiving PDCP entity. It is up to UE
implementation how to minimize SN gap after SDU discard.