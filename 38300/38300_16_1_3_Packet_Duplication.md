### 16.1.3 Packet Duplication

When duplication is configured for a radio bearer by RRC, at least one
secondary RLC entity is added to the radio bearer to handle the
duplicated PDCP PDUs as depicted on Figure 16.1.3-1, where the logical
channel corresponding to the primary RLC entity is referred to as *the
primary logical channel*, and the logical channel corresponding to the
secondary RLC entity(ies), the *secondary logical channel(s)*. All RLC
entities have the same RLC mode. Duplication at PDCP therefore consists
in submitting the same PDCP PDUs multiple times: once to each activated
RLC entity for the radio bearer. With multiple independent transmission
paths, packet duplication therefore increases reliability and reduces
latency and is especially beneficial for URLLC services.

![](media/image66.emf)

Figure 16.1.3-1: Packet Duplication

NOTE: PDCP control PDUs are not duplicated and always submitted to the
primary RLC entity.

When configuring duplication for a DRB, RRC also sets the state of PDCP
duplication (either activated or deactivated) at the time of
(re-)configuration. After the configuration, the PDCP duplication state
can then be dynamically controlled by means of a MAC control element and
in DC, the UE applies the MAC CE commands regardless of their origin
(MCG or SCG). When duplication is configured for an SRB the state is
always active and cannot be dynamically controlled. When configuring
duplication for a DRB with more than one secondary RLC entity, RRC also
sets the state of each of them (i.e. either activated or deactivated).
Subsequently, a MAC CE can be used to dynamically control whether each
of the configured secondary RLC entities for a DRB should be activated
or deactivated, i.e. which of the RLC entities shall be used for
duplicate transmission. Primary RLC entity cannot be deactivated. When
duplication is deactivated for a DRB, all secondary RLC entities
associated to this DRB are deactivated. When a secondary RLC entity is
deactivated, it is not re-established, the HARQ buffers are not flushed,
and the transmitting PDCP entity should indicate to the secondary RLC
entity to discard all duplicated PDCP PDUs.

When activating duplication for a DRB, NG-RAN should ensure that at
least one serving cell is activated for each logical channel associated
with an activated RLC entity of the DRB; and when the deactivation of
SCells leaves no serving cells activated for a logical channel of the
DRB, NG-RAN should ensure that duplication is also deactivated for the
RLC entity associated with the logical channel.

When duplication is activated, the original PDCP PDU and the
corresponding duplicate(s) shall not be transmitted on the same carrier.
The logical channels of a radio bearer configured with duplication can
either belong to the same MAC entity (referred to as CA duplication) or
to different ones (referred to as DC duplication). CA duplication can
also be configured in either or both of the MAC entities together with
DC duplication when duplication over more than two RLC entities is
configured for the radio bearer. In CA duplication, logical channel
mapping restrictions are used in a MAC entity to ensure that the
different logical channels of a radio bearer in the MAC entity are not
sent on the same carrier. When CA duplication is configured for an SRB,
one of the logical channels associated to the SRB is mapped to SpCell.

When CA duplication is deactivated for a DRB in a MAC entity (i.e. none
or only one of RLC entities of the DRB in the MAC entity remains
activated), the logical channel mapping restrictions of the logical
channels of the DRB are lifted for as long as CA duplication remains
deactivated for the DRB in the MAC entity.

When an RLC entity acknowledges the transmission of a PDCP PDU, the PDCP
entity shall indicate to the other RLC entity(ies) to discard it. In
addition, in case of CA duplication, when an RLC entity restricted to
only SCell(s) reaches the maximum number of retransmissions for a PDCP
PDU, the UE informs the gNB but does not trigger RLF.