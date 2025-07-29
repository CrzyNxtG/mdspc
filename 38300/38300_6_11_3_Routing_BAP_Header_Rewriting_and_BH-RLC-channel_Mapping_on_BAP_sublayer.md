### 6.11.3 Routing, BAP Header Rewriting and BH-RLC-channel Mapping on BAP sublayer

![](media/image33.emf)

Figure 6.11.3-1: Routing and BH RLC channel selection on BAP sublayer

Routing on BAP sublayer uses the BAP routing ID, which is configured by
the IAB-donor-CU. The BAP routing ID consists of BAP address and BAP
path ID. The BAP address is used for the following purposes:

> 1\. Determination if a packet has reached the destination node, i.e.
> IAB-node or IAB-donor-DU, on BAP sublayer. This is the case if the BAP
> address in the packet\'s BAP header matches the BAP address configured
> via RRC on the IAB-node, or via F1AP on the IAB-donor-DU. For a
> dual-connected boundary IAB-node that is configured with two BAP
> addresses, the BAP address in the packet\'s BAP header is matched with
> the BAP address configured by the CU of the IAB topology, where the
> packet has been received.
>
> 2\. Determination of the next-hop node for packets that have not
> reached their destination. This applies to packets arriving from a
> prior hop on BAP sublayer or that have been received from IP layer.

For packets arriving from a prior hop or from upper layers, the
determination of the next-hop node is based on a routing configuration
provided by the IAB-donor-CU via F1AP signalling or a default
configuration provided by the IAB-donor-CU via RRC signalling. This F1AP
configuration contains the mapping between the BAP routing ID carried in
the packet\'s BAP header and the next-hop node\'s BAP address.

Table 6.11.3-1: Routing configuration

  -----------------------------------------------------------------------
  BAP routing ID                        Next-hop BAP address
  ------------------------------------- ---------------------------------
  Derived from BAP packet\'s BAP header Egress BH link to forward packet

  -----------------------------------------------------------------------

The IAB-node resolves the next-hop BAP address to a physical backhaul
link. For this purpose, the IAB-donor-CU provides the
IAB-node/IAB-donor-DU with its child-node\'s BAP address via F1AP, and
it provides the IAB-node with its parent-node\'s BAP address via RRC.
For a boundary IAB-node, the routing configuration also indicates the
IAB topology it applies to. The BH link to the next-hop node and the
next-hop BAP address belong to the IAB topology of the CU that provided
the RRC configuration of the BH link to that next-hop node.

The IAB-node can receive multiple routing configurations with the same
destination BAP address but different BAP path IDs. These routing
configurations may resolve to the same or different egress BH links.

In case the BH link resolved from the routing entry is considered
*unavailable* for this packet, the IAB-node may perform local rerouting
as defined in TS 38.340 \[31\], i.e., select another BH link by
considering only the packet\'s BAP address or, in some cases, by header
rewriting. In this manner, the packet can be delivered via an
alternative path as defined in TS 38.340 \[31\].

A BH link may be considered *unavailable* in case the BH link has RLF. A
parent link may be considered *unavailable* after a BH RLF detection
indication has been received on this parent link and before a subsequent
BH RLF recovery indication has been received on the same parent link.
For DL traffic, a BH link may be considered *unavailable* for BAP PDUs
carrying a certain BAP routing ID due to congestion derived from
flow-control feedback information related to this BAP routing ID, as
defined in TS 38.340 \[31\].

For a boundary IAB-node, the routing configuration may carry information
on the IAB topology the configuration applies to.

The IAB-node may rewrite the BAP routing ID in the packet\'s BAP header
under the following circumstances:

\- A packet is routed between two IAB topologies via a boundary IAB-node
as defined in TS 38.401\[31\]. In this case, the BAP routing ID carried
by the received BAP PDU is allocated by the IAB-donor-CU of the ingress
IAB topology, while the BAP routing ID carried by the BAP PDU after
header rewriting is allocated by the IAB-donor-CU of the egress IAB
topology.

\- An upstream packet is locally re-routed to a different IAB-donor-DU
than indicated by the BAP address in the BAP header of the received
packet. The rewritten BAP header carries the BAP address of the
alternative IAB-donor-DU and the BAP path ID for a path to this
alternative IAB-donor-DU. BAP header rewriting for upstream
inter-IAB-donor-DU local rerouting is only applied if neither routing
nor local re-routing without header rewriting resolve to an available
egress BH link.

For packets that are routed between two IAB topologies via a boundary
node, the BAP header rewriting configuration is provided via F1AP, and
it includes the ingress BAP routing ID, the egress BAP routing ID, and
it indicates the egress IAB topology:

Table 6.11.3-2a: BAP header rewriting configuration

  -----------------------------------------------------------------------
  Ingress BAP routing ID    Egress BAP routing ID   Egress topology
                                                    indicator
  ------------------------- ----------------------- ---------------------
  BAP routing ID carried in BAP routing ID carried  Indicates the egress
  the BAP header of the     in the BAP header of    IAB topology.
  received BAP PDU          the transmitted BAP PDU 

  -----------------------------------------------------------------------

For upstream packets that are locally re-routed to a different
IAB-donor-DU, the BAP header is rewritten with a BAP routing ID
contained in the routing entry that was selected for re-routing.

Details of BAP header rewriting are defined in TS 38.340 \[31\].

When routing a packet from an ingress to an egress BH link, the IAB-node
derives the egress BH RLC channel on the egress BH link through an
F1AP-configured mapping from the BH RLC channel used on the ingress BH
link. The BH RLC channel IDs used for ingress and egress BH RLC channels
are generated by the IAB-donor-CU. Since the BH RLC channel ID only has
link-local scope, the mapping configurations also include the BAP
addresses of prior and next hop:

Table 6.11.3-2: BH RLC channel mapping configuration

  -------------------------------------------------------------------------
  Next-hop BAP      Prior-hop BAP      Ingress RLC        Egress RLC
  address           address            channel ID         channel ID
  ----------------- ------------------ ------------------ -----------------
  Derived from      Derived from       Derived from       BH RLC channel on
  routing           packet\'s ingress  packet\'s ingress  egress BH link to
  configuration     BH link            BH RLC channel     forward packet

  -------------------------------------------------------------------------

For a boundary IAB-node, the BH RLC channel mapping configuration may
also include indicators for the IAB topology of the ingress and of the
egress BH link.

The IAB-node resolves the BH RLC channel IDs from logical channel IDs
based on the configuration by the IAB-donor-CU. The IAB-MT obtains the
BH RLC channel ID in the RRC configuration of the corresponding logical
channel. The IAB-DU obtains the BH RLC channel ID in the F1AP
configuration of the BH RLC channel.