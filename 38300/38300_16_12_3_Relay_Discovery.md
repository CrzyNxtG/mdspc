### 16.12.3 Relay Discovery

Model A and Model B discovery models as defined in TS 23.304 \[48\] are
supported for U2N/U2U Relay discovery. The protocol stack used for
discovery is illustrated in Figure 16.12.3-1.

![](media/image88.emf)

Figure 16.12.3-1: Protocol Stack of Discovery Message for
UE-to-Network/UE-to-UE Relay

The U2N Remote UE can perform Relay discovery message (i.e., as
specified in TS 23.304 \[48\]) transmission and may monitor the sidelink
for Relay discovery message while in RRC_IDLE, RRC_INACTIVE or
RRC_CONNECTED. The network may broadcast or configure via dedicated RRC
signalling a Uu RSRP threshold, which is used by the U2N Remote UE to
determine if it can transmit Relay discovery messages to U2N Relay
UE(s).

The U2N Relay UE can perform Relay discovery message (i.e., as specified
in TS 23.304 \[48\]) transmission and may monitor the sidelink for Relay
discovery message while in RRC_IDLE, RRC_INACTIVE or RRC_CONNECTED. The
network may broadcast or configure via dedicated RRC signalling a
maximum Uu RSRP threshold, a minimum Uu RSRP threshold, or both, which
are used by the U2N Relay UE to determine if it can transmit Relay
discovery messages to U2N Remote UE(s).

The U2U Remote UE and U2U Relay UE can perform Relay discovery message
transmission or DCR/DCA message with integrated discovery transmission
and may monitor for Relay discovery message or DCR/DCA message with
integrated discovery while in coverage (i.e. RRC_IDLE, RRC_INACTIVE, or
RRC_CONNECTED) or out-of-coverage.

The network may provide the Relay discovery configuration using
broadcast or dedicated signalling. In addition, the U2N/U2U Remote UE,
L3 U2N Relay UE and U2U Relay UE may use pre-configuration for Relay
discovery.

The resource pool(s) used for NR sidelink communication can be used for
Relay discovery or the network may configure resource pool(s) dedicated
for Relay discovery. Resource pool(s) dedicated for Relay discovery can
be configured simultaneously with resource pool(s) for NR sidelink
communication in system information, dedicated signalling and/or
pre-configuration. Whether dedicated resource pool(s) for Relay
discovery are configured is based on network implementation. If resource
pool(s) dedicated for Relay discovery are configured, only those
resource pool(s) dedicated for Relay discovery shall be used for Relay
discovery. If only resource pool(s) for NR sidelink communication are
configured, all the configured resource pool(s) can be used for Relay
discovery and NR sidelink communication. Only the resource pool for NR
sidelink communication is used for the DCR/DCA message with integrated
discovery.

For U2N Remote UE (including both in-coverage and out of coverage cases)
that has been connected to the network via a U2N Relay UE, only resource
allocation mode 2 is used for Relay discovery message transmission.

For in-coverage U2N Relay UE, and for both in-coverage and out of
coverage U2N Remote UEs, NR sidelink resource allocation principles are
applied for Relay discovery message transmission.

For U2U Remote UE and U2U Relay UE, NR sidelink resource allocation
principles, both mode 1 and mode 2, can be applied for Relay discovery
message transmission.

The sidelink power control for the transmission of Relay discovery
messages is same as for NR sidelink communication.

No ciphering or integrity protection in PDCP layer is applied for the
Relay discovery messages.

The U2N/U2U Remote UE and U2N/U2U Relay UE can determine from SIB12
whether the gNB supports Relay discovery, or Non-Relay discovery, or
both.