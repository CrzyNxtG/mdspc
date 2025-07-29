### 5.11.2 Duplicate PDU discard

For the PDCP entity configured with *pdcp-Duplication* or for the PDCP
entity associated with two RLC entities for an SLRB, the transmitting
PDCP entity shall:

\- if the successful delivery of a PDCP Data PDU is confirmed by one of
the associated AM RLC entities and the AM RLC entity is not associated
with an SRAP entity:

\- indicate to the other AM RLC entities to discard the duplicated PDCP
Data PDU;

\- if the deactivation of PDCP duplication is indicated for the DRB:

\- if the transmitting PDCP entity is associated with one or more RLC
entities and, either one SRAP entity or the N3C; and

\- if the MP primary path is on the indirect path:

\- indicate to the RLC entities on the MP secondary path to discard all
duplicated PDCP Data PDUs;

\- else:

\- indicate to the RLC entities other than the primary RLC entity to
discard all duplicated PDCP Data PDUs;

\- if the deactivation of PDCP duplication is indicated for at least one
associated RLC entities:

\- indicate to the RLC entities deactivated for PDCP duplication to
discard all duplicated PDCP Data PDUs.