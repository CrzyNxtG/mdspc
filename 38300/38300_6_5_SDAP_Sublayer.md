## 6.5 SDAP Sublayer

The main services and functions of SDAP include:

\- Mapping between a QoS flow and a data radio bearer;

NOTE: When remapping an XR QoS flow carrying PDU sets (see clause 16.15)
from one DRB to another (as exemplified in Annex A), all SDAP SDUs
belonging to a PDU Set should be mapped to the same DRB.

\- Marking QoS flow ID (QFI) in both DL and UL packets.

A single protocol entity of SDAP is configured for each individual PDU
session.