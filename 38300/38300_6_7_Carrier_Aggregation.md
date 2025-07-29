## 6.7 Carrier Aggregation

In case of CA, the multi-carrier nature of the physical layer is only
exposed to the MAC layer for which one HARQ entity is required per
serving cell as depicted on Figures 6.7-1 and 6.7-2 below:

\- In both uplink and downlink, there is one independent hybrid-ARQ
entity per serving cell and one transport block is generated per
assignment/grant per serving cell in the absence of spatial
multiplexing. Each transport block and its potential HARQ
retransmissions are mapped to a single serving cell.

![](media/image30.emf)

Figure 6.7-1: Layer 2 Structure for DL with CA configured

![](media/image31.emf)

Figure 6.7-2: Layer 2 Structure for UL with CA configured