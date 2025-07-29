## 9.2 UCI reporting in physical uplink control channel

UCI types reported in a PUCCH include HARQ-ACK information, SR, LRR, and
CSI. UCI bits include HARQ-ACK information bits, if any, SR information
bits, if any, LRR information bit, if any, and CSI bits, if any. The
HARQ-ACK information bits correspond to a HARQ-ACK codebook as described
in clause 9.1. For the remaining of this clause, any reference to SR is
applicable for SR and/or for LRR.

A UE may transmit one or two PUCCHs on a serving cell in different
symbols within a slot. When the UE transmits two PUCCHs in a slot and
the UE is not provided *ackNackFeedbackMode* = *separate*, at least one
of the two PUCCHs uses PUCCH format 0 or PUCCH format 2.

If a UE is provided *ackNackFeedbackMode* = *separate*, the UE may
transmit up to two PUCCHs with HARQ-ACK information in different symbols
within a slot.

In clauses 9.2.3, 9.2.5.1, 9.2.5.2 and 9.2.5.3, a UE assumes 11 CRC bits
if a number of respective UCI bits is larger than or equal to 360;
otherwise, the UE determines a number of CRC bits based on the number of
respective UCI bits as described in \[5, TS 38.212\].