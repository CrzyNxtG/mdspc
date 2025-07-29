### 4.2.4 PDCP Parameters

+-----------------------------------------------------+-----+-----+---------+
| Definitions for parameters                          | Per | M   | FDD-TDD |
|                                                     |     |     | DIFF    |
+=====================================================+:===:+:===:+:=======:+
| ***continueEHC-Context-r16***                       | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates that the UE supports EHC context          |     |     |         |
| continuation operation where the UE keeps the       |     |     |         |
| established EHC context(s) upon PDCP                |     |     |         |
| re-establishment, as specified in TS 38.323 \[16\]. |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***continueROHC-Context***                          | UE  | No  | No      |
|                                                     |     |     |         |
| Defines whether the UE supports ROHC context        |     |     |         |
| continuation operation where the UE does not reset  |     |     |         |
| the current ROHC context upon PDCP                  |     |     |         |
| re-establishment, as specified in TS 38.323 \[16\]. |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***ehc-r16***                                       | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates that the UE supports Ethernet header      |     |     |         |
| compression and decompression using EHC protocol,   |     |     |         |
| as specified in TS 38.323 \[16\]. The UE indicating |     |     |         |
| this capability and indicating support for at least |     |     |         |
| one ROHC profile, shall support simultaneous        |     |     |         |
| configuration of EHC and ROHC on different          |     |     |         |
| DRBs/multicast MRBs.                                |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***extendedDiscardTimer-r16***                      | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates whether the UE supports the additional    |     |     |         |
| values of PDCP discard timer. The supported         |     |     |         |
| additional values are 0.5ms, 1ms, 2ms, 4ms, 6ms and |     |     |         |
| 8ms, as specified in TS 38.331 \[9\].               |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***jointEHC-ROHC-Config-r16***                      | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates whether the UE supports simultaneous      |     |     |         |
| configuration of EHC and ROHC protocols for the     |     |     |         |
| same DRB/multicast MRB.                             |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***maxNumberROHC-ContextSessions***                 | UE  | No  | No      |
|                                                     |     |     |         |
| Defines the maximum number of ROHC header           |     |     |         |
| compression context sessions supported by the UE    |     |     |         |
| across all DRBs and multicast MRBs, excluding       |     |     |         |
| context sessions that leave all headers             |     |     |         |
| uncompressed.                                       |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***maxNumberEHC-Contexts-r16***                     | UE  | No  | No      |
|                                                     |     |     |         |
| Defines the maximum number of Ethernet header       |     |     |         |
| compression contexts supported by the UE across all |     |     |         |
| DRBs and multicast MRBs and across UE\'s EHC        |     |     |         |
| compressor and EHC decompressor. The indicated      |     |     |         |
| number defines the number of contexts in addition   |     |     |         |
| to CID = \"all zeros\" as specified in TS 38.323    |     |     |         |
| \[16\].                                             |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***outOfOrderDelivery***                            | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates whether UE supports out of order delivery |     |     |         |
| of data to upper layers by PDCP.                    |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***pdcp-DuplicationMCG-OrSCG-DRB***                 | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates whether the UE supports CA-based PDCP     |     |     |         |
| duplication over MCG or SCG DRB as specified in TS  |     |     |         |
| 38.323 \[16\].                                      |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***pdcp-DuplicationMoreThanTwoRLC-r16***            | UE  | No  | No      |
|                                                     |     |     |         |
| Defines whether the UE supports PDCP duplication    |     |     |         |
| with more than two RLC entities as specified in TS  |     |     |         |
| 38.323 \[16\]. The UE supporting this feature       |     |     |         |
| supports secondary RLC entity(ies) activation and   |     |     |         |
| deactivation based on duplication RLC               |     |     |         |
| Activation/Deactivation MAC CE as specified in TS   |     |     |         |
| 38.321 \[8\]. A UE supporting this feature shall    |     |     |         |
| also support *pdcp-DuplicationMCG-OrSCG-DRB*,       |     |     |         |
| *pdcp-DuplicationSplitDRB*,                         |     |     |         |
| *pdcp-DuplicationSplitSRB* and                      |     |     |         |
| *pdcp-DuplicationSRB*.                              |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***pdcp-DuplicationSplitDRB***                      | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates whether the UE supports PDCP duplication  |     |     |         |
| over split DRB as specified in TS 38.323 \[16\].    |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***pdcp-DuplicationSplitSRB***                      | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates whether the UE supports PDCP duplication  |     |     |         |
| over split SRB1/2 as specified in TS 38.323 \[16\]. |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***pdcp-DuplicationSRB***                           | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates whether the UE supports CA-based PDCP     |     |     |         |
| duplication over SRB1/2 and/or, if (NG)EN-DC or     |     |     |         |
| NR-DC is supported, SRB3 as specified in TS 38.323  |     |     |         |
| \[16\].                                             |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***psi-BasedDiscard-r18***                          | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates whether the UEs supports PSI based        |     |     |         |
| discard (i.e. *discardTimerForLowImportance-r18*    |     |     |         |
| configuration, as specified in TS 38.331 \[9\]).    |     |     |         |
|                                                     |     |     |         |
| UE supporting *psi-BasedDiscard-r18* shall also     |     |     |         |
| support the ability to identify PDU sets and PSI    |     |     |         |
| for UL XR traffic.                                  |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***shortSN***                                       | UE  | Yes | No      |
|                                                     |     |     |         |
| Indicates whether the UE supports 12 bit length of  |     |     |         |
| PDCP sequence number.                               |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***supportedROHC-Profiles***                        | UE  | No  | No      |
|                                                     |     |     |         |
| Defines which ROHC profiles from the list below are |     |     |         |
| supported by the UE:                                |     |     |         |
|                                                     |     |     |         |
| > \- 0x0000 ROHC No compression (RFC 5795)          |     |     |         |
| >                                                   |     |     |         |
| > \- 0x0001 ROHC RTP/UDP/IP (RFC 3095, RFC 4815)    |     |     |         |
| >                                                   |     |     |         |
| > \- 0x0002 ROHC UDP/IP (RFC 3095, RFC 4815)        |     |     |         |
| >                                                   |     |     |         |
| > \- 0x0003 ROHC ESP/IP (RFC 3095, RFC 4815)        |     |     |         |
| >                                                   |     |     |         |
| > \- 0x0004 ROHC IP (RFC 3843, RFC 4815)            |     |     |         |
| >                                                   |     |     |         |
| > \- 0x0006 ROHC TCP/IP (RFC 6846)                  |     |     |         |
| >                                                   |     |     |         |
| > \- 0x0101 ROHC RTP/UDP/IP (RFC 5225)              |     |     |         |
| >                                                   |     |     |         |
| > \- 0x0102 ROHC UDP/IP (RFC 5225)                  |     |     |         |
| >                                                   |     |     |         |
| > \- 0x0103 ROHC ESP/IP (RFC 5225)                  |     |     |         |
| >                                                   |     |     |         |
| > \- 0x0104 ROHC IP (RFC 5225)                      |     |     |         |
|                                                     |     |     |         |
| A UE that supports one or more of the listed ROHC   |     |     |         |
| profiles shall support ROHC profile 0x0000 ROHC     |     |     |         |
| uncompressed (RFC 5795).                            |     |     |         |
|                                                     |     |     |         |
| An IMS voice capable UE shall indicate support of   |     |     |         |
| ROHC profiles 0x0000, 0x0001, 0x0002 and be able to |     |     |         |
| compress and decompress headers of PDCP SDUs at a   |     |     |         |
| PDCP SDU rate corresponding to supported IMS voice  |     |     |         |
| codecs.                                             |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***supportOfPDU-SetDiscard-r18***                   | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates whether the UE supports PDU set based     |     |     |         |
| discard operation (i.e. *pdu-SetDiscard-r18*        |     |     |         |
| configuration, as specified in TS 38.331 \[9\]).    |     |     |         |
|                                                     |     |     |         |
| UE supporting this feature shall also support the   |     |     |         |
| ability to identify PDU sets for UL XR traffic.     |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***supportOfSN-GapReport-r18***                     | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates whether the UE supports PDCP SN gap       |     |     |         |
| reporting as specified in TS 38.323 \[16\] and TS   |     |     |         |
| 38.331 \[9\].                                       |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***udc-r17***                                       | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates whether the UE supports the uplink data   |     |     |         |
| compression operation as specified in TS 38.323     |     |     |         |
| \[16\]. The capability signalling comprises of the  |     |     |         |
| following parameters:                               |     |     |         |
|                                                     |     |     |         |
| \- *standardDictionary-r17* indicates whether the   |     |     |         |
| UE supports UL data compression with SIP static     |     |     |         |
| dictionary as defined in TS 38.323 \[16\].          |     |     |         |
|                                                     |     |     |         |
| \- *operatorDictionary-r17* indicates whether the   |     |     |         |
| UE supports UL data compression with operator       |     |     |         |
| defined dictionary. In this release, the UE can     |     |     |         |
| only support one operator defined dictionary. If    |     |     |         |
| the UE supports operator defined dictionary, the UE |     |     |         |
| shall report *versionOfDictionary-r17* and          |     |     |         |
| *associatedPLMN-ID-r17* of the stored operator      |     |     |         |
| defined dictionary as defined in TS 38.331 \[9\].   |     |     |         |
| This parameter is not required to be present if the |     |     |         |
| UE is in VPLMN. The *associatedPLMN-ID-r17* is only |     |     |         |
| associated to the operator defined dictionary which |     |     |         |
| has no relationship with UE\'s HPLMN ID.            |     |     |         |
|                                                     |     |     |         |
| \- *continueUDC-r17* indicates whether the UE       |     |     |         |
| supports continuation of uplink data compression    |     |     |         |
| protocol operation where the UE does not reset the  |     |     |         |
| buffer upon PDCP re-establishment, as specified in  |     |     |         |
| TS 38.323 \[16\].                                   |     |     |         |
|                                                     |     |     |         |
| \- *supportOfBufferSize-r17* indicates which        |     |     |         |
| compression buffer size the UE supports as          |     |     |         |
| specified in TS 38.323 \[16\]. Value kbyte4 means   |     |     |         |
| the UE supports 4096 bytes for compression buffer   |     |     |         |
| per UDC DRB. Value kbyte8 means the UE supports     |     |     |         |
| 8192 bytes for compression buffer per UDC DRB.      |     |     |         |
|                                                     |     |     |         |
| A UE that supports the uplink data compression      |     |     |         |
| operation shall support 2048 bytes for compression  |     |     |         |
| buffer per UDC DRB and support up to 2 UDC DRBs.    |     |     |         |
+-----------------------------------------------------+-----+-----+---------+
| ***uplinkOnlyROHC-Profiles***                       | UE  | No  | No      |
|                                                     |     |     |         |
| Indicates the ROHC profile(s) that are supported in |     |     |         |
| uplink-only ROHC operation by the UE.               |     |     |         |
|                                                     |     |     |         |
| \- 0x0006 ROHC TCP (RFC 6846)                       |     |     |         |
|                                                     |     |     |         |
| A UE that supports uplink-only ROHC profile(s)      |     |     |         |
| shall support ROHC profile 0x0000 ROHC uncompressed |     |     |         |
| (RFC 5795).                                         |     |     |         |
+-----------------------------------------------------+-----+-----+---------+