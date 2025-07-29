### 5.2.1 Transmit operation

At reception of a PDCP SDU from upper layers, the transmitting PDCP
entity shall:

\- if *discardTimerForLowImportance* is configured and PSI based SDU
discard is activated, and the PDCP SDU belongs to a low importance PDU
Set:

\- start the *discardTimerForLowImportance* associated with this PDCP
SDU;

\- else:

\- start the *discardTimer* associated with this PDCP SDU (if
configured).

NOTE 0: Identification of PSI of a PDU Set and determination of low
importance PDU Set are left up to UE implementation.

For a PDCP SDU received from upper layers, the transmitting PDCP entity
shall:

\- associate the COUNT value corresponding to TX_NEXT to this PDCP SDU;

NOTE 1: Associating more than half of the PDCP SN space of contiguous
PDCP SDUs with PDCP SNs, when e.g., the PDCP SDUs are discarded or
transmitted without acknowledgement, may cause HFN desynchronization
problem. How to prevent HFN desynchronization problem is left up to UE
implementation.

\- perform header compression of the PDCP SDU using ROHC as specified in
the clause 5.7.4 and/or using EHC as specified in the clause 5.12.4;

\- perform uplink data compression of the PDCP SDU as specified in
clause 5.14.4;

\- perform integrity protection, and ciphering using the TX_NEXT as
specified in the clause 5.9 and 5.8, respectively;

\- set the PDCP SN of the PDCP Data PDU to TX_NEXT modulo
2^\[*pdcp-SN-SizeUL*\]^;

\- increment TX_NEXT by one;

\- submit the resulting PDCP Data PDU to lower layer as specified below.

When submitting a PDCP PDU to lower layer, the transmitting PDCP entity
shall:

\- if the transmitting PDCP entity is associated with one SRAP entity:

\- submit the PDCP PDU to the associated SRAP entity;

\- else, if the transmitting PDCP entity is associated with one RLC
entity:

\- submit the PDCP PDU to the associated RLC entity;

\- else, if the transmitting PDCP entity is associated with one or more
RLC entities and, either one SRAP entity or the N3C:

\- if PDCP duplication is activated for the RB:

\- if the PDCP PDU is a PDCP Data PDU:

\- duplicate the PDCP Data PDU and submit the PDCP Data PDU to each of
the MP primary path and MP secondary path which is activated for PDCP
duplication, including any associated Uu RLC entities activated for PDCP
duplication;

\- else:

\- if the MP primary path is the direct path:

\- submit the PDCP Control PDU to the primary RLC entity;

\- else:

\- submit the PDCP Control PDU to the SRAP entity or N3C;

\- else (i.e., PDCP duplication is deactivated for the RB):

\- if the total amount of PDCP data volume, RLC data volume pending for
initial transmission (as specified in TS 38.322 \[5\]) in either the
primary RLC entity (when the MP primary path is the direct path) or the
split secondary RLC entity on the direct path (when the MP primary path
is the indirect path), and data volume pending for initial transmission
in the N3C (if available) or mapped SL RLC entity associated with the
SRAP entity, is equal to or larger than *ul-DataSplitThreshold*:

\- submit the PDCP PDU to either the Uu RLC entity (i.e., either the
primary RLC entity or the split secondary RLC entity) or SRAP
entity/N3C;

\- else:

\- if the MP primary path is the direct path:

\- submit the PDCP PDU to the primary RLC entity;

\- else:

\- submit the PDCP PDU to the SRAP entity or N3C;

\- else, if the transmitting PDCP entity is associated with at least two
RLC entities:

\- if the PDCP duplication is activated for the RB:

\- if the PDCP PDU is a PDCP Data PDU:

\- duplicate the PDCP Data PDU and submit the PDCP Data PDU to the
associated RLC entities activated for PDCP duplication;

\- else:

\- submit the PDCP Control PDU to the primary RLC entity;

\- else (i.e. the PDCP duplication is deactivated for the RB or the RB
is a DAPS bearer):

\- if the split secondary RLC entity is configured; and

\- if the total amount of PDCP data volume and RLC data volume pending
for initial transmission (as specified in TS 38.322 \[5\]) in the
primary RLC entity and the split secondary RLC entity is equal to or
larger than *ul-DataSplitThreshold*:

\- submit the PDCP PDU to either the primary RLC entity or the split
secondary RLC entity;

\- else, if the transmitting PDCP entity is associated with the DAPS
bearer:

\- if the uplink data switching has not been requested:

\- submit the PDCP PDU to the RLC entity associated with the source
cell;

\- else:

\- if the PDCP PDU is a PDCP Data PDU:

\- submit the PDCP Data PDU to the RLC entity associated with the target
cell;

\- else:

\- if the PDCP Control PDU is associated with source cell:

\- submit the PDCP Control PDU to the RLC entity associated with the
source cell;

\- else:

\- submit the PDCP Control PDU to the RLC entity associated with the
target cell;

\- else:

\- submit the PDCP PDU to the primary RLC entity.

NOTE 2: If the transmitting PDCP entity is associated with two RLC
entities, or with one or more RLC entities and either an SRAP entity or
the N3C, the UE should minimize the amount of PDCP PDUs submitted to
lower layers before receiving request from lower layers and minimize the
PDCP SN gap between PDCP PDUs submitted to two associated RLC entities,
or to the one or more RLC entities and either the SRAP entity or the
N3C, to minimize PDCP reordering delay in the receiving PDCP entity.