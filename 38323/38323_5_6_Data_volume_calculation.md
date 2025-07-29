## 5.6 Data volume calculation

For the purpose of MAC buffer status reporting, the transmitting PDCP
entity shall consider the following as PDCP data volume:

\- the PDCP SDUs for which no PDCP Data PDUs have been constructed;

\- the PDCP Data PDUs that have not been submitted to lower layers;

\- the PDCP Control PDUs;

\- for AM DRBs, the PDCP SDUs to be retransmitted according to clause
5.1.2 and clause 5.13;

\- for AM DRBs, the PDCP Data PDUs to be retransmitted according to
clause 5.5.

If the transmitting PDCP entity is associated with at least two RLC
entities, or with one or more RLC entities and either an SRAP entity or
the N3C, when indicating the PDCP data volume to a MAC entity for BSR
triggering and Buffer Size calculation (as specified in TS 38.321 \[4\]
and TS 36.321 \[12\]), the transmitting PDCP entity shall:

\- if the PDCP duplication is activated for the RB:

\- indicate the PDCP data volume to the MAC entity associated with the
primary RLC entity, or the MAC entity associated with the SRAP entity if
the MP primary path is the indirect path;

\- indicate the PDCP data volume excluding the PDCP Control PDU to the
MAC entity associated with the RLC entity other than the primary RLC
entity, or the MAC entity associated with any Uu RLC entity, when the MP
secondary path is the direct path, activated for PDCP duplication;

\- indicate the PDCP data volume as 0 to the MAC entity associated with
RLC entity deactivated for PDCP duplication;

\- else (i.e. the PDCP duplication is deactivated for the RB or the RB
is a DAPS bearer):

\- if the split secondary RLC entity is configured; and

\- if the total amount of PDCP data volume and RLC data volume pending
for initial transmission (as specified in TS 38.322 \[5\]) in the
primary RLC entity and the split secondary RLC entity is equal to or
larger than *ul-DataSplitThreshold*:

\- indicate the PDCP data volume to both the MAC entity associated with
the primary RLC entity and the MAC entity associated with the split
secondary RLC entity;

\- indicate the PDCP data volume as 0 to the MAC entity associated with
RLC entity other than the primary RLC entity and the split secondary RLC
entity;

\- else, if the total amount of PDCP data volume, RLC data volume
pending for initial transmission (as specified in TS 38.322 \[5\]) in
either the primary RLC entity (when the MP primary path is the direct
path) or the split secondary RLC entity on the direct path (when the MP
primary path is the indirect path), and data volume pending for initial
transmission in the N3C (if available), or mapped SL RLC entity
associated with the SRAP entity, is equal to or larger than
*ul-DataSplitThreshold*:

\- indicate the PDCP data volume to both the MAC entity associated with
the Uu RLC entity (i.e., either primary RLC entity or split secondary
RLC entity) and the MAC entity associated with the SRAP entity;

\- indicate the PDCP data volume as 0 to the MAC entity associated with
Uu RLC entity other than the primary RLC entity or the split secondary
RLC entity;

\- else, if the transmitting PDCP entity is associated with the DAPS
bearer:

\- if the uplink data switching has not been requested:

\- indicate the PDCP data volume to the MAC entity associated with the
source cell;

\- else:

\- indicate the PDCP data volume excluding the PDCP Control PDU for
interspersed ROHC feedback associated with the source cell to the MAC
entity associated with the target cell;

\- indicate the PDCP data volume of PDCP Control PDU for interspersed
ROHC feedback associated with the source cell to the MAC entity
associated with the source cell;

\- else:

\- if the transmitting PDCP entity is associated with one or more RLC
entities and, either one SRAP entity or the N3C; and

\- if the MP primary path is the indirect path:

\- indicate the PDCP data volume to the MAC entity associated with the
SRAP entity;

\- indicate the PDCP data volume as 0 to the MAC entities associated
with all Uu RLC entities on the direct path;

\- else:

\- indicate the PDCP data volume to the MAC entity associated with the
primary RLC entity;

\- indicate the PDCP data volume as 0 to the MAC entity associated with
the RLC entity other than the primary RLC entity.