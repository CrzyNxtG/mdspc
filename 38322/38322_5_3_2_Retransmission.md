### 5.3.2 Retransmission

The transmitting side of an AM RLC entity can receive a negative
acknowledgement (notification of reception failure by its peer AM RLC
entity) for an RLC SDU or an RLC SDU segment by the following:

\- STATUS PDU from its peer AM RLC entity.

When receiving a negative acknowledgement for an RLC SDU or an RLC SDU
segment by a STATUS PDU from its peer AM RLC entity, the transmitting
side of the AM RLC entity shall:

\- if the SN of the corresponding RLC SDU falls within the range
TX_Next_Ack \<= SN \< = the highest SN of the AMD PDU among the AMD PDUs
submitted to lower layer:

\- consider the RLC SDU or the RLC SDU segment for which a negative
acknowledgement was received for retransmission.

When an RLC SDU or an RLC SDU segment is considered for retransmission,
the transmitting side of the AM RLC entity shall:

\- if the RLC SDU or RLC SDU segment is considered for retransmission
for the first time:

\- set the RETX_COUNT associated with the RLC SDU to zero.

\- else, if it (the RLC SDU or the RLC SDU segment that is considered
for retransmission) is not pending for retransmission already and the
RETX_COUNT associated with the RLC SDU has not been incremented due to
another negative acknowledgment in the same STATUS PDU:

\- increment the RETX_COUNT.

\- if RETX_COUNT = *maxRetxThreshold*:

\- indicate to upper layers that max retransmission has been reached.

When retransmitting an RLC SDU or an RLC SDU segment, the transmitting
side of an AM RLC entity shall:

\- if needed, segment the RLC SDU or the RLC SDU segment;

\- form a new AMD PDU which will fit within the total size of AMD PDU(s)
indicated by lower layer at the particular transmission opportunity;

\- submit the new AMD PDU to lower layer.

When forming a new AMD PDU, the transmitting side of an AM RLC entity
shall:

\- only map the original RLC SDU or RLC SDU segment to the Data field of
the new AMD PDU;

\- modify the header of the new AMD PDU in accordance with the
description in clause 6.2.2.4;

\- set the P field according to clause 5.3.3.