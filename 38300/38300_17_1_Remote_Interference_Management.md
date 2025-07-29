## 17.1 Remote Interference Management

The atmospheric ducting phenomenon, caused by lower densities at higher
altitudes in the Earth\'s atmosphere, causes a reduced refractive index,
causing the signals to bend back towards the Earth. A signal trapped in
the atmospheric duct can reach distances far greater than normal. In TDD
networks with the same UL/DL slot configuration, and in the absence of
atmospheric ducting, a guard period is used to avoid the interference
between UL and DL transmissions in different cells. However, when the
atmospheric ducting phenomenon happens, radio signals can travel a
relatively long distance, and the propagation delay exceeds the guard
period. Consequently, the DL signals of an aggressor cell can interfere
with the UL signals of a victim cell that is far away from the
aggressor. Such interference is termed as remote interference. The
further the aggressor is to the victim, the more UL symbols of the
victim will be impacted.

A remote interference scenario may involve a number of victim and
aggressor cells, where the gNBs execute Remote Interference Management
(RIM) coordination on behalf of their respective cells. Aggressor and
victim gNBs can be grouped into semi-static sets, where each cell is
assigned a set ID, and is configured with a RIM Reference Signal
(RIM-RS) and the radio resources associated with the set ID. Each
aggressor gNB can be configured with multiple set IDs and each victim
gNB can be configured with multiple set IDs, whereas each cell can have
at most one victim set ID and one aggressor set ID. Consequently, each
gNB can be an aggressor and a victim at the same time.

To mitigate remote interference, the network enables RIM frameworks for
coordination between victim and aggressor gNBs. The coordination
communication in RIM frameworks can be wireless- or backhaul-based. The
backhaul-based RIM framework uses a combination of wireless and backhaul
communication, while in the wireless framework, the communication is
purely wireless.

In both frameworks, all gNBs in a victim set simultaneously transmit an
identical RIM reference signal carrying the victim set ID over the air.

In the wireless framework, upon reception of the RIM reference signal
from the victim set, aggressor gNBs undertake RIM measures, and send
back a RIM reference signal carrying the aggressor set ID. The RIM
reference signal sent by the aggressor is able to provide information
whether the atmospheric ducting phenomenon exists. The victim gNBs
realize the atmospheric ducting phenomenon have ceased upon not
receiving any reference signal sent from aggressors.

In the RIM backhaul framework, upon reception of the RIM reference
signal from the victim set, aggressor gNBs undertake RIM measures, and
establish backhaul coordination towards the victim gNB set. The backhaul
messages are sent from individual aggressor gNBs to individual victim
gNB, where the signalling is transparent to the core network. The RIM
backhaul messages from aggressor to victim gNBs carry the indication
about the detection or disappearance of RIM reference signal. Based on
the indication from the backhaul message, the victim gNBs realize
whether the atmospheric ducting and the consequent remote interference
have ceased.

In both frameworks, upon realizing that the atmospheric ducting has
disappeared, the victim gNBs stop transmitting the RIM reference signal.