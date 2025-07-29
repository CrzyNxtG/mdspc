### 5.12.7 Simultaneous configuration of ROHC and EHC

If both ROHC and EHC are configured for a DRB/MRB, the ROHC header shall
be located after the EHC header. Figure 5.12.7-1 shows the location of
the ROHC header and the EHC header in a PDCP Data PDU.

![](media/image8.emf)

Figure 5.12.7-1: Location of ROHC header and EHC header in a PDCP Data
PDU

If a PDCP SDU including non-IP Ethernet packet is received from upper
layers, the EHC compressor shall bypass the ROHC compressor and submit
the EHC compressed non-IP Ethernet packet to lower layers according to
clause 5.2.1.

If a PDCP Data PDU including non-IP Ethernet packet is received from
lower layers, the EHC decompressor shall bypass the ROHC decompressor
and deliver the EHC decompressed non-IP Ethernet packet to upper layers
according to clause 5.2.2.