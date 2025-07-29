## 8.4 NR sidelink communication, V2X sidelink communication and Ranging/Sidelink positioning related identities

The following identities are used for NR sidelink communication and
SL-PRS transmission on shared SL-PRS resource pool:

\- Source Layer-2 ID: Identifies the sender of the data in NR sidelink
communication and/or SL-PRS transmission. The Source Layer-2 ID is 24
bits long and is split in the MAC layer into two bit strings:

\- One bit string is the LSB part (8 bits) of Source Layer-2 ID and
forwarded to physical layer of the sender. This identifies the source of
the intended data and/or SL-PRS in sidelink control information and is
used for filtering of packets at the physical layer of the receiver;

\- Second bit string is the MSB part (16 bits) of the Source Layer-2 ID
and is carried within the MAC header. This is used for filtering of
packets at the MAC layer of the receiver.

\- Destination Layer-2 ID: Identifies the target of the data in NR
sidelink communication and/or SL-PRS transmission. For NR sidelink
communication and SL-PRS transmission on shared SL-PRS resource pool,
the Destination Layer-2 ID is 24 bits long and is split in the MAC layer
into two bit strings:

\- One bit string is the LSB part (16 bits) of Destination Layer-2 ID
and forwarded to physical layer of the sender. This identifies the
target of the intended data and/or SL-PRS in sidelink control
information and is used for filtering of packets at the physical layer
of the receiver;

\- Second bit string is the MSB part (8 bits) of the Destination Layer-2
ID and is carried within the MAC header. This is used for filtering of
packets at the MAC layer of the receiver.

\- PC5 Link Identifier: Uniquely identifies the PC5 unicast link in a UE
for the lifetime of the PC5 unicast link as specified in TS 23.287
\[40\]. The PC5 Link Identifier is used to indicate to upper layers the
PC5 unicast link in which sidelink RLF was declared and corresponding
PC5-RRC connection was released.

V2X sidelink communication related identities are specified in clause
8.3 of TS 36.300 \[2\].

The following identities are used for SL-PRS transmission on dedicated
SL-PRS resource pool:

\- Source ID: Identifies the sender of the SL-PRS transmission. The
length of the identifier is either 12 or 24 bits, which is indicated in
the RRC configuration. The source ID identifies the source of the
intended SL-PRS in sidelink control information and is used for
filtering at the MAC layer of the receiver;

\- Destination ID: Identifies the target of the SL-PRS transmission. The
length of the identifier is 24 bits. The Destination ID identifies the
target of the intended SL-PRS in sidelink control information and is
used for filtering at the MAC layer of the receiver.