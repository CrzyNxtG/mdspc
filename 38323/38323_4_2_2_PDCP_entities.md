### 4.2.2 PDCP entities

The PDCP entities are located in the PDCP sublayer. Several PDCP
entities may be defined for a UE. Each PDCP entity is carrying the data
of one radio bearer. A PDCP entity is associated either to the control
plane or the user plane depending on which radio bearer it is carrying
data for.

Figure 4.2.2-1 represents the functional view of the PDCP entity for the
PDCP sublayer; it should not restrict implementation. The figure is
based on the radio interface protocol architecture defined in TS 38.300
\[2\].

For split bearers, MP split bearers, and DAPS bearers, routing is
performed in the transmitting PDCP entity.

A PDCP entity associated with DRB can be configured by upper layers TS
38.331 \[3\] to use header compression or uplink data compression (UDC).
A PDCP entity associated with MRB can be configured by upper layers TS
38.331 \[3\] to use header compression. In this version of the
specification, the robust header compression protocol (ROHC), the
Ethernet header compression protocol (EHC) and UDC are supported. Each
header compression protocol is independently configured for a DRB/MRB.

![](media/image6.emf)

Figure 4.2.2-1: PDCP layer, functional view

Figure 4.2.2-2 represents the functional view of the PDCP entity
associated with the DAPS bearer for the PDCP sublayer; it should not
restrict implementation. The figure is based on the radio interface
protocol architecture defined in TS 38.300 \[2\].

For DAPS bearers, the PDCP entity is configured with two sets of
security functions and keys and two sets of header compression
protocols.

![](media/image7.emf)

Figure 4.2.2-2: PDCP layer associated with DAPS bearer, functional view