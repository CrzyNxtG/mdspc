## 5.5 Transport Channels

The physical layer offers information transfer services to MAC and
higher layers. The physical layer transport services are described by
*how* and with what characteristics data are transferred over the radio
interface. An adequate term for this is \"Transport Channel\". This
should be clearly separated from the classification of *what* is
transported, which relates to the concept of logical channels at MAC
sublayer.

Downlink transport channel types are:

1\. **Broadcast Channel (BCH)** characterised by:

\- fixed, pre-defined transport format;

\- requirement to be broadcast in the entire coverage area of the cell,
either as a single message or by beamforming different BCH instances.

2\. **Downlink Shared Channel (DL-SCH)** characterised by:

\- support for HARQ;

\- support for dynamic link adaptation by varying the modulation, coding
and transmit power;

\- possibility to be broadcast in the entire cell;

\- possibility to use beamforming;

\- support for both dynamic and semi-static resource allocation;

\- support for UE discontinuous reception (DRX) to enable UE power
saving.

3\. **Paging Channel (PCH)** characterised by:

\- support for UE discontinuous reception (DRX) to enable UE power
saving (DRX cycle is indicated by the network to the UE);

\- requirement to be broadcast in the entire coverage area of the cell,
either as a single message or by beamforming different PCH instances;

\- mapped to physical resources which can be used dynamically also for
traffic/other control channels.

Uplink transport channel types are:

1\. **Uplink Shared Channel (UL-SCH)** characterised by:

\- possibility to use beamforming;

\- support for dynamic link adaptation by varying the transmit power and
potentially modulation and coding;

\- support for HARQ;

\- support for both dynamic and semi-static resource allocation.

2\. **Random Access Channel(s) (RACH)** characterised by:

\- limited control information;

\- collision risk.

Sidelink transport channel types are:

1\. **Sidelink broadcast channel (SL-BCH)** characterised by:

\- pre-defined transport format.

2\. **Sidelink shared channel (SL-SCH)** characterised by:

\- support for unicast transmission, groupcast transmission and
broadcast transmission;

\- support for both UE autonomous resource selection and scheduled
resource allocation by NG-RAN;

\- support for both dynamic and semi-static resource allocation when UE
is allocated resources by the NG-RAN;

\- support for HARQ;

\- support for dynamic link adaptation by varying the transmit power,
modulation and coding;

\- support for SL discontinuous reception (SL DRX) to enable UE power
saving.

Association of transport channels to physical channels is described in
TS 38.202 \[20\].