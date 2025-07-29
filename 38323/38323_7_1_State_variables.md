## 7.1 State variables

This clause describes the state variables used in PDCP entities in order
to specify the PDCP protocol. The state variables defined in this clause
are normative.

All state variables are non-negative integers, and take values from 0 to
\[2^32^ -- 1\].

PDCP Data PDUs are numbered integer sequence numbers (SN) cycling
through the field: 0 to \[2^\[*pdcp-SN-SizeUL*\]^ -- 1\] or 0 to
\[2^\[*pdcp-SN-SizeDL*\]^ -- 1\] or 0 to \[2^\[*sl-PDCP-SN-Size*\]^ --
1\].

The transmitting PDCP entity shall maintain the following state
variables:

a\) TX_NEXT

This state variable indicates the COUNT value of the next PDCP SDU to be
transmitted. The initial value is 0, except for SRBs configured with
state variables continuation. For target SRB configured with state
variables continuation, the initial value is the value stored in PDCP
entity for the corresponding source SRB. For source SRB configured with
state variables continuation, the initial value is the value stored in
PDCP entity for the corresponding target SRB.

The receiving PDCP entity shall maintain the following state variables:

a\) RX_NEXT

This state variable indicates the COUNT value of the next PDCP SDU
expected to be received. The initial value is 0, except for sidelink
broadcast and groupcast, for SRBs configured with state variables
continuation, for multicast MRBs whose PDCP COUNT is not synchronized as
indicated by upper layer, and for broadcast MRBs. For NR sidelink
communication for broadcast and groupcast or sidelink SRB4 for NR
sidelink discovery, the initial value of the SN part of RX_NEXT is (x
+1) modulo (2^\[*sl-PDCP-SN-Size*\]^), where x is the SN of the first
received PDCP Data PDU. For multicast MRBs whose PDCP COUNT is not
synchronized as indicated by upper layer, and for broadcast MRBs, the
initial value of the SN part of RX_NEXT is (x +1) modulo
(2^\[*PDCP-SN-SizeDL*\]^), where x is the SN of the first received PDCP
Data PDU. For target SRB configured with state variables continuation,
the initial value is the value stored in PDCP entity for the
corresponding source SRB. For source SRB configured with state variables
continuation, the initial value is the value stored in PDCP entity for
the corresponding target SRB.

NOTE 1: For NR sidelink communication for broadcast and groupcast or
sidelink SRB4 for NR sidelink discovery, it is up to UE implementation
to select the HFN part for RX_NEXT such that initial value of RX_DELIV
should be a positive value.

NOTE 2: For multicast MRBs whose PDCP COUNT is not synchronized as
indicated by upper layer, and for broadcast MRBs, the initial value of
the HFN part of RX_NEXT is set by UE implementation.

b\) RX_DELIV

This state variable indicates the COUNT value of the first PDCP SDU not
delivered to the upper layers, but still waited for. The initial value
is 0, except for sidelink broadcast and groupcast, for SRBs configured
with state variables continuation, and for MRBs. For NR sidelink
communication for broadcast and groupcast or sidelink SRB4 for NR
sidelink discovery, the initial value of the SN part of RX_DELIV is (x
-- 0.5 × 2^\[*sl-PDCP-SN-Size*--1\]^) modulo (2^\[*sl-PDCP-SN-Size*\]^),
where x is the SN of the first received PDCP Data PDU. For multicast
MRBs whose PDCP COUNT is not synchronized as indicated by upper layer,
and for broadcast MRBs, the initial value of the SN part of RX_DELIV is
set to (x -- 0.5 × 2^\[*PDCP-SN-SizeDL*--1\]^) modulo
(2^\[*PDCP-SN-SizeDL*\]^), where x is the SN of the first received PDCP
Data PDU. For multicast MRBs, the initial value of RX_DELIV is set, if
provided, by *initialRX-DELIV* in TS 38.331 \[3\]. For target SRB
configured with state variables continuation, the initial value is the
value stored in PDCP entity for the corresponding source SRB. For source
SRB configured with state variables continuation, the initial value is
the value stored in PDCP entity for the corresponding target SRB.

NOTE 3: For multicast MRBs whose PDCP COUNT is not synchronized as
indicated by upper layer, and for broadcast MRBs, the initial value of
the HFN part of RX_DELIV is set by UE implementation.

c\) RX_REORD

This state variable indicates the COUNT value following the COUNT value
associated with the PDCP Data PDU which triggered *t-Reordering*. For
target SRB configured with state variables continuation, the initial
value is the value stored in PDCP entity for the corresponding source
SRB. For source SRB configured with state variables continuation, the
initial value is the value stored in PDCP entity for the corresponding
target SRB.