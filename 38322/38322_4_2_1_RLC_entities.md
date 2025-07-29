### 4.2.1 RLC entities

The description in this clause is a model and does not specify or
restrict implementations.

RRC is generally in control of the RLC configuration.

Functions of the RLC sub layer are performed by RLC entities. For an RLC
entity configured at the gNB, there is a peer RLC entity configured at
the UE and vice versa. In NR sidelink communication, in NR sidelink
discovery, for an RLC entity configured at the transmitting UE, there is
a peer RLC entity configured at each receiving UE.

An RLC entity receives/delivers RLC SDUs from/to upper layer or N3C and
sends/receives RLC PDUs to/from its peer RLC entity via lower layers.

An RLC PDU can either be an RLC data PDU or an RLC control PDU. If an
RLC entity receives RLC SDUs from upper layer, it receives them through
a single RLC channel between RLC and upper layer, and after forming RLC
data PDUs from the received RLC SDUs, the RLC entity submits the RLC
data PDUs to lower layer through a single logical channel. If an RLC
entity receives RLC data PDUs from lower layer, it receives them through
a single logical channel, and after forming RLC SDUs from the received
RLC data PDUs, the RLC entity delivers the RLC SDUs to upper layer
through a single RLC channel between RLC and upper layer. If an RLC
entity submits/receives RLC control PDUs to/from lower layer, it
submits/receives them through the same logical channel it
submits/receives the RLC data PDUs through.

NOTE 1: In case the upper layer is BAP as defined in TS 38.340 \[7\], an
RLC channel refers to a Backhaul RLC channel.

NOTE 2: In case the upper layer is SRAP as defined in TS 38.351 \[9\],
an RLC channel refers to either a PC5 Relay RLC channel or a Uu Relay
RLC channel.

An RLC entity can be configured to perform data transfer in one of the
following three modes: Transparent Mode (TM), Unacknowledged Mode (UM)
or Acknowledged Mode (AM). Consequently, an RLC entity is categorized as
a TM RLC entity, an UM RLC entity or an AM RLC entity depending on the
mode of data transfer that the RLC entity is configured to provide.

A TM RLC entity is configured either as a transmitting TM RLC entity or
a receiving TM RLC entity. The transmitting TM RLC entity receives RLC
SDUs from upper layer and sends RLC PDUs to its peer receiving TM RLC
entity via lower layers. The receiving TM RLC entity delivers RLC SDUs
to upper layer and receives RLC PDUs from its peer transmitting TM RLC
entity via lower layers.

An UM RLC entity is configured either as a transmitting UM RLC entity or
a receiving UM RLC entity. The transmitting UM RLC entity receives RLC
SDUs from upper layer and sends RLC PDUs to its peer receiving UM RLC
entity via lower layers. The receiving UM RLC entity delivers RLC SDUs
to upper layer and receives RLC PDUs from its peer transmitting UM RLC
entity via lower layers.

An AM RLC entity consists of a transmitting side and a receiving side.
The transmitting side of an AM RLC entity receives RLC SDUs from upper
layer and sends RLC PDUs to its peer AM RLC entity via lower layers. The
receiving side of an AM RLC entity delivers RLC SDUs to upper layer and
receives RLC PDUs from its peer AM RLC entity via lower layers.

Figure 4.2.1-1 illustrates the overview model of the RLC sub layer.

![](media/image3.emf)

Figure 4.2.1-1: Overview model of the RLC sub layer

RLC SDUs of variable sizes which are byte aligned (i.e. multiple of 8
bits) are supported for all RLC entity types (i.e. TM, UM and AM RLC
entity).

Each RLC SDU is used to construct an RLC PDU without waiting for
notification from the lower layer (i.e., by MAC) of a transmission
opportunity. In the case of UM and AM RLC entities, an RLC SDU may be
segmented and transported using two or more RLC PDUs based on the
notification(s) from the lower layer.

RLC PDUs are submitted to lower layer only when a transmission
opportunity has been notified by lower layer (i.e. by MAC).

NOTE 3: The UE should aim to prevent excessive non-consecutive RLC PDUs
in a MAC PDU when the UE is requested to generate more than one MAC PDU.

Description of different RLC entity types are provided below.