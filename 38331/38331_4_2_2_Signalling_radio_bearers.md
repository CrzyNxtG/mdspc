### 4.2.2 Signalling radio bearers

\"Signalling Radio Bearers\" (SRBs) are defined as Radio Bearers (RBs)
that are used only for the transmission of RRC and NAS messages. More
specifically, the following SRBs are defined:

\- SRB0 is for RRC messages using the CCCH logical channel (except SRB0
of L2 U2N Remote UE);

\- SRB1 is for RRC messages (which may include a piggybacked NAS
message) as well as for NAS messages prior to the establishment of SRB2,
all using DCCH logical channel (except SRB1 of L2 U2N Remote UE);

\- SRB2 is for NAS messages and for RRC messages which include logged
measurement information, all using DCCH logical channel (except SRB2 of
L2 U2N Remote UE). SRB2 has a lower priority than SRB1 and may be
configured by the network after AS security activation;

\- SRB3 is for specific RRC messages when UE is in (NG)EN-DC or NR-DC,
all using DCCH logical channel;

\- SRB4 is for RRC messages which include application layer measurement
report information, all using DCCH logical channel. SRB4 has a lower
priority than SRB1 and can only be configured by the network after AS
security activation.

\- SRB5 is for RRC messages which include application layer measurement
report information, all using DCCH logical channel. SRB5 has a lower
priority than SRB1 and SRB3 and can only be configured by the SN serving
the SCG when the UE is in NR-DC, after AS security activation.

In downlink, piggybacking of NAS messages is used only for one dependant
(i.e. with joint success/failure) procedure: bearer
establishment/modification/release. In uplink piggybacking of NAS
message is used only for transferring the initial NAS message during
connection setup and connection resume.

NOTE 1: The NAS messages transferred via SRB2 are also contained in RRC
messages, which however do not include any RRC protocol control
information.

Once AS security is activated, all RRC messages on SRB1, SRB2, SRB3,
SRB4 and SRB5, including those containing NAS messages, are integrity
protected and ciphered by PDCP. NAS independently applies integrity
protection and ciphering to the NAS messages, see TS 24.501 \[23\].

Split SRB is supported for all the MR-DC options as well as MP in both
SRB1 and SRB2 (split SRB is not supported for SRB0, SRB3, SRB4 and
SRB5).

For operation with shared spectrum channel access in FR1, SRB0, SRB1 and
SRB3 are assigned with the highest priority Channel Access Priority
Class (CAPC), (i.e. CAPC = 1) while CAPC for SRB2 is configurable.

For the NR sidelink L2 U2N relay operations not involved in MP, SRB0,
SRB1, SRB2 of a L2 U2N Remote UE are not using Uu CCCH/DCCH logical
channels. The SRB0, SRB1, SRB2 of a L2 U2N Remote UE are transmitted via
the PC5 Relay RLC channels over PC5 and Uu Relay RLC channels over Uu.