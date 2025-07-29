### 6.11.2 Traffic Mapping from Upper Layers to Layer-2

In upstream direction, the IAB-donor-CU configures the IAB-node with
mappings between upstream F1 and non-F1 traffic originated at the
IAB-node, and the appropriate BAP routing ID, next-hop BAP address and
BH RLC channel. A specific mapping is configured:

> \- for each F1-U GTP-U tunnel;
>
> \- for non-UE associated F1AP messages;
>
> \- for UE-associated F1AP messages;
>
> \- for non-F1 traffic.

Multiple mappings can contain the same BH RLC channel and/or next-hop
BAP address and/or BAP routing ID. In case the IAB-MT is
NR-dual-connected (SA mode only), the mapping may include two separate
BH RLC channels, where the two BH RLC channels are established toward
different parent nodes.

In case the IAB-node is configured with multiple IP addresses for F1-C
on the NR leg, multiple mappings can be configured for non-UE-associated
F1AP messages or UE-associated F1AP messages. The appropriate mapping is
selected based on the IAB-node\'s implementation.

These traffic mapping configurations are performed via F1AP. For a
boundary IAB-node, the traffic mapping configuration includes
information that allows the boundary IAB-node to determine the IAB
topology the mapping applies to.

During IAB-node integration, a default BH RLC channel and a default BAP
routing ID may be configured via RRC, which can be used for non-F1-U
traffic. These default configurations may be updated during topology
adaptation scenarios as discussed in TS 38.401 \[4\].

In downstream direction, traffic mapping occurs internal to the
IAB-donor. Transport for IAB-donors that use split-gNB architecture is
handled in TS 38.401 \[4\].