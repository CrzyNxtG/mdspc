### 5.14.4 Uplink data compression

The UDC protocol generates UDC packets, each associated with one PDCP
SDU.

A UDC packet is associated with the same PDCP SN and COUNT values as the
related PDCP SDU. The uplink data compression is not applicable to the
SDAP header and the SDAP Control PDU if included in the PDCP Data PDU.