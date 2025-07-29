## 5.15 Data volume calculation for delay status reporting

For the purpose of MAC delay status reporting, the transmitting PDCP
entity shall consider the following as delay-critical PDCP data volume:

\- the delay-critical PDCP SDUs for which no PDCP Data PDUs have been
constructed;

\- the PDCP Data PDUs that contain the delay-critical PDCP SDUs and have
not been submitted to lower layers;

\- the PDCP Control PDUs;

\- for AM DRBs, the PDCP SDUs to be retransmitted according to clause
5.1.2 and clause 5.13;

\- for AM DRBs, the PDCP Data PDUs to be retransmitted according to
clause 5.5.

The transmitting PDCP entity provides a delay-critical indication for
the PDCP Data PDU to lower layers when:

\- the PDCP Data PDU has already been submitted to lower layers and the
corresponding PDCP SDU becomes a delay-critical PDCP SDU; or

\- the PDCP Data PDU is submitted to lower layers and the corresponding
PDCP SDU is already a delay-critical PDCP SDU.

If the transmitting PDCP entity is associated with at least two RLC
entities, when indicating the delay-critical PDCP data volume to a MAC
entity for DSR triggering and Buffer Size calculation (as specified in
TS 38.321 \[4\]), the transmitting PDCP entity shall:

\- if the PDCP duplication is activated for the RB:

\- indicate the delay-critical PDCP data volume to the MAC entity
associated with the primary RLC entity;

\- indicate the delay-critical PDCP data volume excluding the PDCP
Control PDU to the MAC entity associated with the RLC entity other than
the primary RLC entity activated for PDCP duplication;

\- indicate the delay-critical PDCP data volume as 0 to the MAC entity
associated with RLC entity deactivated for PDCP duplication;

\- else (i.e. the PDCP duplication is deactivated for the RB):

\- if the split secondary RLC entity is configured; and

\- if the total amount of PDCP data volume and RLC data volume pending
for initial transmission (as specified in TS 38.322 \[5\]) in the
primary RLC entity and the split secondary RLC entity is equal to or
larger than *ul-DataSplitThreshold*:

\- indicate the delay-critical PDCP data volume to both the MAC entity
associated with the primary RLC entity and the MAC entity associated
with the split secondary RLC entity;

\- indicate the delay-critical PDCP data volume as 0 to the MAC entity
associated with RLC entity other than the primary RLC entity and the
split secondary RLC entity;

\- else:

\- indicate the delay-critical PDCP data volume to the MAC entity
associated with the primary RLC entity;

\- indicate the delay-critical PDCP data volume as 0 to the MAC entity
associated with the RLC entity other than the primary RLC entity.