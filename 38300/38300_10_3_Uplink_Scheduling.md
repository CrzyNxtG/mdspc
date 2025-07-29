## 10.3 Uplink Scheduling

In the uplink, the gNB can dynamically allocate resources to UEs via the
C-RNTI on PDCCH(s). A UE always monitors the PDCCH(s) in order to find
possible grants for uplink transmission when its downlink reception is
enabled (activity governed by DRX and cell DTX when configured). When CA
is configured, the same C-RNTI applies to all serving cells.

The gNB may cancel a PUSCH transmission, or a repetition of a PUSCH
transmission, or an SRS transmission of a UE for another UE with a
latency-critical transmission. The gNB can configure UEs to monitor
cancelled transmission indications using CI-RNTI on a PDCCH. If a UE
receives the cancelled transmission indication, the UE shall cancel the
PUSCH transmission from the earliest symbol overlapped with the resource
or the SRS transmission overlapped with the resource indicated by
cancellation (see clause 11.2A of TS 38.213 \[38\]).

In addition, with Configured Grants, the gNB can allocate uplink
resources for the initial HARQ transmissions and HARQ retransmissions to
UEs. Two types of configured uplink grants are defined:

\- With Type 1, RRC directly provides the configured uplink grant
(including the periodicity).

\- With Type 2, RRC defines the periodicity of the configured uplink
grant while PDCCH addressed to CS-RNTI can either signal and activate
the configured uplink grant, or deactivate it; i.e. a PDCCH addressed to
CS-RNTI indicates that the uplink grant can be implicitly reused
according to the periodicity defined by RRC, until deactivated.

If the UE is not configured with enhanced intra-UE overlapping resources
prioritization, the dynamically allocated uplink transmission overrides
the configured uplink grant in the same serving cell, if they overlap in
time. Otherwise an uplink transmission according to the configured
uplink grant is assumed, if activated.

If the UE is configured with enhanced intra-UE overlapping resources
prioritization, in case a configured uplink grant transmission overlaps
in time with dynamically allocated uplink transmission or with another
configured uplink grant transmission in the same serving cell, the UE
prioritizes the transmission based on the comparison between the highest
priority of the logical channels that have data to be transmitted and
which are multiplexed or can be multiplexed in MAC PDUs associated with
the overlapping resources. Similarly, in case a configured uplink grant
transmissions or a dynamically allocated uplink transmission overlaps in
time with a scheduling request transmission, the UE prioritizes the
transmission based on the comparison between the priority of the logical
channel which triggered the scheduling request and the highest priority
of the logical channels that have data to be transmitted and which are
multiplexed or can be multiplexed in MAC PDU associated with the
overlapping resource. In case the MAC PDU associated with a
deprioritized transmission has already been generated, the UE keeps it
stored to allow the gNB to schedule a retransmission. The UE may also be
configured by the gNB to transmit the stored MAC PDU as a new
transmission using a subsequent resource of the same configured uplink
grant configuration when an explicit retransmission grant is not
provided by the gNB.

Retransmissions other than repetitions are explicitly allocated via
PDCCH(s) or via configuration of a retransmission timer.

The UE may be configured with up to 12 active configured uplink grants
for a given BWP of a serving cell. When more than one is configured, the
network decides which of these configured uplink grants are active at a
time (including all of them). Each configured uplink grant can either be
of Type 1 or Type 2. For Type 2, activation and deactivation of
configured uplink grants are independent among the serving cells. When
more than one Type 2 configured grant is configured, each configured
grant is activated separately using a DCI command and deactivation of
Type 2 configured grants is done using a DCI command, which can either
deactivate a single configured grant configuration or multiple
configured grant configurations jointly.

When SUL is configured, the network should ensure that an active
configured uplink grant on SUL does not overlap in time with another
active configured uplink grant on the other UL configuration.

For both dynamic grant and configured grant, for a transport block, two
or more repetitions can be in one slot, or across slot boundary in
consecutive available slots with each repetition in one slot. For both
dynamic grant and configured grant Type 2, the number of repetitions can
be also dynamically indicated in the L1 signalling. The dynamically
indicated number of repetitions shall override the RRC configured number
of repetitions, if both are present.