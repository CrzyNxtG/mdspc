## 5.4 SDU discard procedures

When indicated from upper layer (e.g. PDCP) to discard a particular RLC
SDU, the transmitting side of an AM RLC entity or the transmitting UM
RLC entity shall discard the indicated RLC SDU, if neither the RLC SDU
nor a segment thereof has been submitted to the lower layers. The
transmitting side of an AM RLC entity shall not introduce an RLC SN gap
when discarding an RLC SDU.