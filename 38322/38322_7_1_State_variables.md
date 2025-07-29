## 7.1 State variables

This clause describes the state variables used in AM and UM entities in
order to specify the RLC protocol. The state variables defined in this
clause are normative.

All state variables and all counters are non-negative integers.

All state variables related to AM data transfer can take values from 0
to 4095 for 12 bit SN or from 0 to 262143 for 18 bit SN. All arithmetic
operations contained in the present document on state variables related
to AM data transfer are affected by the AM modulus (i.e. final value =
\[value from arithmetic operation\] modulo 4096 for 12 bit SN and 262144
for 18 bit SN).

All state variables related to UM data transfer can take values from 0
to 63 for 6 bit SN or from 0 to 4095 for 12 bit SN. All arithmetic
operations contained in the present document on state variables related
to UM data transfer are affected by the UM modulus (i.e. final value =
\[value from arithmetic operation\] modulo 64 for 6 bit SN and 4096 for
12 bit SN).

When performing arithmetic comparisons of state variables or SN values,
a modulus base shall be used.

TX_Next_Ack and RX_Next shall be assumed as the modulus base at the
transmitting side and receiving side of an AM RLC entity, respectively.
This modulus base is subtracted from all the values involved, and then
an absolute comparison is performed (e.g. RX_Next \<= SN \< RX_Next +
AM_Window_Size is evaluated as \[RX_Next -- RX_Next\] modulo
2^\[*sn-FieldLength*\]^ \<= \[SN -- RX_Next\] modulo
2^\[*sn-FieldLength*\]^ \< \[RX_Next + AM_Window_Size -- RX_Next\]
modulo 2^\[*sn-FieldLength*\]^), where *sn-FieldLength* is 12 or 18 for
12 bit SN and 18 bit SN, respectively.

RX_Next_Highest-- UM_Window_Size shall be assumed as the modulus base at
the receiving UM RLC entity. This modulus base is subtracted from all
the values involved, and then an absolute comparison is performed (e.g.
(RX_Next_Highest-- UM_Window_Size) \<= SN \< RX_Next_Highest is
evaluated as \[(RX_Next_Highest-- UM_Window_Size) -- (RX_Next_Highest--
UM_Window_Size)\] modulo 2^\[*sn-FieldLength*\]^ \<= \[SN --
(RX_Next_Highest-- UM_Window_Size)\] modulo 2^\[*sn-FieldLength*\]^ \<
\[RX_Next_Highest-- (RX_Next_Highest-- UM_Window_Size)\] modulo
2^\[*sn-FieldLength*\]^), where *sn-FieldLength* is 6 or 12 for 6 bit SN
and 12 bit SN, respectively.

The transmitting side of each AM RLC entity shall maintain the following
state variables:

a\) TX_Next_Ack -- Acknowledgement state variable

This state variable holds the value of the SN of the next RLC SDU for
which a positive acknowledgment is to be received in-sequence, and it
serves as the lower edge of the transmitting window. It is initially set
to 0, and is updated whenever the AM RLC entity receives a positive
acknowledgment for an RLC SDU with SN = TX_Next_Ack.

b\) TX_Next -- Send state variable

This state variable holds the value of the SN to be assigned for the
next newly generated AMD PDU. It is initially set to 0, and is updated
whenever the AM RLC entity constructs an AMD PDU with SN = TX_Next and
contains an RLC SDU or the last segment of a RLC SDU.

c\) POLL_SN -- Poll send state variable

This state variable holds the value of the highest SN of the AMD PDU
among the AMD PDUs submitted to lower layer when POLL_SN is set
according to clause 5.3.3.2. It is initially set to 0.

The transmitting side of each AM RLC entity shall maintain the following
counters:

a\) PDU_WITHOUT_POLL -- Counter

This counter is initially set to 0. It counts the number of AMD PDUs
sent since the most recent poll bit was transmitted.

b\) BYTE_WITHOUT_POLL -- Counter

This counter is initially set to 0. It counts the number of data bytes
sent since the most recent poll bit was transmitted.

c\) RETX_COUNT -- Counter

This counter counts the number of retransmissions of an RLC SDU or RLC
SDU segment (see clause 5.3.2). There is one RETX_COUNT counter
maintained per RLC SDU. This counter is reset to zero for each RLC SDU
when indicated by upper layer.

The receiving side of each AM RLC entity shall maintain the following
state variables:

a\) RX_Next -- Receive state variable

This state variable holds the value of the SN following the last
in-sequence completely received RLC SDU, and it serves as the lower edge
of the receiving window. It is initially set to 0, and is updated
whenever the AM RLC entity receives an RLC SDU with SN = RX_Next.

b\) RX_Next_Status_Trigger -- *t-Reassembly* state variable

This state variable holds the value of the SN following the SN of the
RLC SDU which triggered *t-Reassembly*.

c\) RX_Highest_Status -- Maximum STATUS transmit state variable

This state variable holds the highest possible value of the SN which can
be indicated by \"ACK_SN\" when a STATUS PDU needs to be constructed. It
is initially set to 0.

d\) RX_Next_Highest -- Highest received state variable

This state variable holds the value of the SN following the SN of the
RLC SDU with the highest SN among received RLC SDUs. It is initially set
to 0.

Each transmitting UM RLC entity shall maintain the following state
variables:

a\) TX_Next -- UM send state variable

This state variable holds the value of the SN to be assigned for the
next newly generated UMD PDU with segment. It is initially set to 0, and
is updated after the UM RLC entity submits a UMD PDU including the last
segment of an RLC SDU to lower layers.

Each receiving UM RLC entity shall maintain the following state
variables:

a\) RX_Next_Reassembly -- UM receive state variable

This state variable holds the value of the earliest SN that is still
considered for reassembly. It is initially set to 0. For groupcast and
broadcast of NR sidelink communication or for SL-SRB4 of NR sidelink
discovery, it is initially set to the SN of the first received UMD PDU
containing an SN. For the receiving UM RLC entity configured for MCCH or
MTCH, it is up to UE implementation to set the initial value of
RX_Next_Reassembly to a value before RX_Next_Highest.

b\) RX_Timer_Trigger -- UM *t-Reassembly* state variable

This state variable holds the value of the SN following the SN which
triggered *t-Reassembly*.

c\) RX_Next_Highest-- UM receive state variable

This state variable holds the value of the SN following the SN of the
UMD PDU with the highest SN among received UMD PDUs. It serves as the
higher edge of the reassembly window. It is initially set to 0. For
groupcast and broadcast of NR sidelink communication or for SL-SRB4 of
NR sidelink discovery, it is initially set to the SN of the first
received UMD PDU containing an SN. For the receiving UM RLC entity
configured for MCCH or MTCH, it is initially set to the SN of the first
received UMD PDU containing an SN.