### 16.10.4 Group Scheduling

The following logical channels are used for MBS delivery:

\- MTCH: A PTM downlink channel for transmitting MBS data of either
multicast session or broadcast session from the network to the UE;

\- DTCH: A PTP channel defined in clause 6.2.2 for transmitting MBS data
of a multicast session from the network to the UE;

\- MCCH: A PTM downlink channel used for transmitting MBS broadcast or
MBS multicast control information associated to one or several MTCH(s)
from the network to the UE. Broadcast MCCH and multicast MCCH are
independent channels. The multicast MCCH is used only for multicast
reception in RRC_INACTIVE state.

The following connections between logical channels and transport
channels for PTM transmission exist:

\- MCCH can be mapped to DL-SCH;

\- MTCH can be mapped to DL-SCH.

The following depicts the usage of RNTI for PTM transmission:

\- A UE can receive different services using same or different G-RNTIs;

\- A UE can receive different services using same or different
G-CS-RNTIs.