## 8.2 Structure of encoded RRC messages

An RRC PDU, which is the bit string that is exchanged between peer
entities/across the radio interface contains the basic production as
defined in X.691.

RRC PDUs shall be mapped to and from PDCP SDUs (in case of DCCH) or RLC
SDUs (in case of PCCH, BCCH or CCCH) upon transmission and reception as
follows:

\- when delivering an RRC PDU as an PDCP SDU to the PDCP layer for
transmission, the first bit of the RRC PDU shall be represented as the
first bit in the PDCP SDU and onwards; and

\- when delivering an RRC PDU as an RLC SDU to the RLC layer for
transmission, the first bit of the RRC PDU shall be represented as the
first bit in the RLC SDU and onwards; and

\- upon reception of an PDCP SDU from the PDCP layer, the first bit of
the PDCP SDU shall represent the first bit of the RRC PDU and onwards;
and

\- upon reception of an RLC SDU from the RLC layer, the first bit of the
RLC SDU shall represent the first bit of the RRC PDU and onwards.