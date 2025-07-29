## 7.8 Bandwidth Adaptation

To enable BA on the SpCell, the gNB configures the UE with UL and DL
BWP(s). To enable BA on SCells in case of CA, the gNB configures the UE
with DL BWP(s) at least (i.e. there may be none in the UL). For the
PCell, the BWP used for initial access is configured via system
information. For the SCell(s), the BWP used after initial activation is
configured via dedicated RRC signalling.

In paired spectrum, DL and UL can switch BWP independently. In unpaired
spectrum, DL and UL switch BWP simultaneously. Switching between
configured BWPs happens by means of RRC signalling, DCI, inactivity
timer or upon initiation of random access. When an inactivity timer is
configured for a serving cell, the expiry of the inactivity timer
associated to that cell switches the active BWP to a default BWP
configured by the network. There can be at most one active BWP per cell,
except when the serving cell is configured with SUL, in which case there
can be at most one on each UL carrier.