# A.1 EHC principle

The Ethernet header compression (EHC) protocol compresses Ethernet
header as shown in Figure A.1-1 \[15\]. The fields that are compressed
(i.e. removed from the Ethernet header) by the EHC protocol are:
DESTINATION ADDRESS, SOURCE ADDRESS, 802.1Q TAG, and LENGTH/TYPE. The
fields PREAMBLE, SFD, and FCS are not transmitted in 3GPP system, and
thus not considered in EHC protocol. There may be more than one 802.1Q
TAG fields in the Ethernet header, and all are compressed by the EHC
protocol. The padding (PAD) is not compressed by the EHC protocol.

![](media/image23.emf)

Figure A.1-1: Ethernet packet format \[15\]

The EHC compressor and the EHC decompressor store original header field
information as a \"EHC context\". Each EHC context is identified by a
unique identifier, called Context ID (CID). The EHC context must be
synchronized between the EHC compressor and the EHC decompressor;
otherwise, the EHC decompressor erroneously decompresses the
\"Compressed Header (CH)\" packets.

For an Ethernet packet stream, the EHC compressor establishes the EHC
context and associates it with the CID. Then, the EHC compressor
transmits the \"Full Header (FH)\" packet to the EHC decompressor
including the associated CID. The EHC compressor keeps transmitting the
FH packets until the EHC feedback is received from the EHC decompressor.

NOTE: If the maximum number of EHC contexts are already established for
the compressed flows and a new Ethernet flow does not match any
established EHC context, the compressor should associate the new
Ethernet flow with one of the EHC CIDs allocated for the existing
compressed flows or send PDCP SDUs belonging to the Ethernet flow as
uncompressed packet.

When the EHC decompressor receives the FH packet, the EHC decompressor
establishes the EHC context identified by the CID, and transmits the EHC
feedback to the EHC compressor to indicate that the EHC context
associated with the CID is successfully established in the EHC
decompressor.

After receiving the EHC feedback, the EHC compressor starts to transmit
the CH packets to the EHC decompressor including the associated CID. The
CH packet includes only the header fields not stored in the EHC context.

When the EHC decompressor receives the CH packet, the EHC decompressor
restores original header fields based on the stored EHC context
identified by the associated CID.

Figure A.1-2 represents a conceptual view of EHC operation.

![](media/image24.emf)

Figure A.1-2: EHC operation