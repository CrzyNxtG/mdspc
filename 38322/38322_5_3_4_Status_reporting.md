### 5.3.4 Status reporting

An AM RLC entity sends STATUS PDUs to its peer AM RLC entity in order to
provide positive and/or negative acknowledgements of RLC SDUs (or
portions of them).

Triggers to initiate STATUS reporting include:

\- Polling from its peer AM RLC entity:

\- When an AMD PDU with SN = x and the P field set to \"1\" is received
from lower layer, the receiving side of an AM RLC entity shall:

\- if the AMD PDU is to be discarded as specified in clause 5.2.3.2.2;
or

\- if x \< RX_Highest_Status or x \>= RX_Next + AM_Window_Size:

\- trigger a STATUS report.

\- else:

\- delay triggering the STATUS report until x \< RX_Highest_Status or x
\>= RX_Next + AM_Window_Size.

NOTE 1: This ensures that the RLC Status report is transmitted after
HARQ reordering.

\- Detection of reception failure of an AMD PDU

\- The receiving side of an AM RLC entity shall trigger a STATUS report
when *t-Reassembly* expires.

NOTE 2: The expiry of *t-Reassembly* triggers both RX_Highest_Status to
be updated and a STATUS report to be triggered, but the STATUS report
shall be triggered after RX_Highest_Status is updated.

When STATUS reporting has been triggered, the receiving side of an AM
RLC entity shall:

\- if *t-StatusProhibit* is not running:

\- at the first transmission opportunity indicated by lower layer,
construct a STATUS PDU and submit it to lower layer.

\- else:

\- at the first transmission opportunity indicated by lower layer after
*t-StatusProhibit* expires, construct a single STATUS PDU even if status
reporting was triggered several times while *t-StatusProhibit* was
running and submit it to lower layer.

When a STATUS PDU has been submitted to lower layer, the receiving side
of an AM RLC entity shall:

\- start *t-StatusProhibit*.

When constructing a STATUS PDU, the AM RLC entity shall:

\- for the RLC SDUs with SN such that RX_Next \<= SN \<
RX_Highest_Status that has not been completely received yet, in
increasing SN order of RLC SDUs and increasing byte segment order within
RLC SDUs, starting with SN = RX_Next up to the point where the resulting
STATUS PDU still fits to the total size of RLC PDU(s) indicated by lower
layer:

\- for an RLC SDU for which no byte segments have been received yet:

\- include in the STATUS PDU a NACK_SN which is set to the SN of the RLC
SDU.

\- for a continuous sequence of byte segments of a partly received RLC
SDU that have not been received yet:

\- include in the STATUS PDU a set of NACK_SN, SOstart and SOend.

\- for a continuous sequence of RLC SDUs that have not been received
yet:

\- include in the STATUS PDU a set of NACK_SN and NACK range;

\- include in the STATUS PDU, if required, a pair of SOstart and SOend.

\- set the ACK_SN to the SN of the next not received RLC SDU which is
not indicated as missing in the resulting STATUS PDU.