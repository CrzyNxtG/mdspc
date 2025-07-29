### 6.3.6 MBS information elements

#### -- *CarrierFreqListMBS*

The IE *CarrierFreqListMBS* is used to inform network of the frequencies
on which the UE is receiving or interested to receive MBS broadcast
service via a broadcast MRB.

*CarrierFreqListMBS* information element

\-- ASN1START

\-- TAG-CARRIERFREQLISTMBS-START

CarrierFreqListMBS-r17 ::= SEQUENCE (SIZE (1..maxFreqMBS-r17)) OF
ARFCN-ValueNR

\-- TAG-CARRIERFREQLISTMBS-STOP

\-- ASN1STOP

#### -- *CFR-ConfigMCCH-MTCH*

The IE *CFR-ConfigMCCH-MTCH* is used to configure the common frequency
resource used for MCCH, multicast MCCH and MTCH reception.

*CFR-ConfigMCCH-MTCH* information element

\-- ASN1START

\-- TAG-CFR-CONFIGMCCH-MTCH-START

CFR-ConfigMCCH-MTCH-r17 ::= SEQUENCE {

locationAndBandwidthBroadcast-r17 LocationAndBandwidthBroadcast-r17
OPTIONAL, \-- Need S

pdsch-ConfigMCCH-r17 PDSCH-ConfigBroadcast-r17 OPTIONAL, \-- Need S

commonControlResourceSetExt-r17 ControlResourceSet OPTIONAL \-- Cond
NotSIB1CommonControlResource

}

LocationAndBandwidthBroadcast-r17 ::= CHOICE {

sameAsSib1ConfiguredLocationAndBW NULL,

locationAndBandwidth INTEGER (0..37949)

}

\-- TAG-CFR-CONFIGMCCH-MTCH-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *CFR-ConfigMCCH-MTCH* field descriptions                              |
+-----------------------------------------------------------------------+
| ***commonControlResourceSetExt***                                     |
|                                                                       |
| An additional common control resource set which may be configured and |
| used for *searchSpaceMCCH*/*searchSpaceMTCH* or UE-specific search    |
| space in the BWP where *searchSpaceMCCH* is configured. It is         |
| contained in the bandwidth of the CFR for broadcast and larger than   |
| CORESET#0.                                                            |
+=======================================================================+
| ***locationAndBandwidthBroadcast***                                   |
|                                                                       |
| Indicates starting PRB and the number of PRBs of CFR used for MCCH,   |
| multicast MCCH and MTCH reception.                                    |
|                                                                       |
| Value *sameAsSib1ConfiguredLocationAndBW* means the CFR for broadcast |
| or multicast has the same location and size as the                    |
| *locationAndBandwidth* for initial BWP (for (e)RedCap UEs:            |
| *initialDownlinkBWP-RedCap* if it is configured and includes CD-SSB   |
| and the entire CORESET#0) configured in *SIB1*.                       |
|                                                                       |
| Value *locationAndBandwidth* is used to configure CFR with bandwidth  |
| that is larger than and fully contains the bandwidth for the initial  |
| DL BWP (for (e)RedCap UEs: *initialDownlinkBWP-RedCap* if it is       |
| configured and includes CD-SSB and the entire CORESET#0) configured   |
| in *SIB1* and CORESET#0. The value of the field shall be interpreted  |
| as defined in TS 38.214 \[19\] with assumptions as described in TS    |
| 38.213 \[13\].                                                        |
|                                                                       |
| This field is not included in *cfr-ConfigMCCH-MTCH-RedCap* if         |
| *initialDownlinkBWP-RedCap* in *SIB1* is configured but does not      |
| include CD-SSB and the entire CORESET#0.                              |
|                                                                       |
| If the field is absent, the CFR for broadcast or multicast has the    |
| same location and size as CORESET#0.                                  |
+-----------------------------------------------------------------------+
| ***pdsch-ConfigMCCH***                                                |
|                                                                       |
| Indicates PDSCH parameters used for MCCH or multicast MCCH            |
| transmission. If the field is absent, PDSCH parameters used for MCCH  |
| or multicast MCCH are the same as those of PDSCH configuration        |
| provided in *initialDownlinkBWP* in *SIB1*.                           |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------------------
  Conditional Presence             Explanation
  -------------------------------- --------------------------------------------------
  *NotSIB1CommonControlResource*   The field is optional present in case
                                   *commonControlResourceSet* is not configured in
                                   SIB1, Need R, otherwise it is absent.

  -----------------------------------------------------------------------------------

#### -- *DRX-ConfigPTM*

The IE *DRX-ConfigPTM* is used to configure DRX related parameters for
PTM transmission as specified in TS 38.321 \[3\].

*DRX-ConfigPTM* information element

\-- ASN1START

\-- TAG-DRX-CONFIGPTM-START

DRX-ConfigPTM-r17 ::= SEQUENCE {

drx-onDurationTimerPTM-r17 CHOICE {

subMilliSeconds INTEGER (1..31),

milliSeconds ENUMERATED {

ms1, ms2, ms3, ms4, ms5, ms6, ms8, ms10, ms20, ms30, ms40, ms50, ms60,

ms80, ms100, ms200, ms300, ms400, ms500, ms600, ms800, ms1000, ms1200,

ms1600, spare8, spare7, spare6, spare5, spare4, spare3, spare2, spare1

}

},

drx-InactivityTimerPTM-r17 ENUMERATED {

ms0, ms1, ms2, ms3, ms4, ms5, ms6, ms8, ms10, ms20, ms30, ms40, ms50,
ms60, ms80,

ms100, ms200, ms300, ms500, ms750, ms1280, ms1920, ms2560, spare9,
spare8,

spare7, spare6, spare5, spare4, spare3, spare2, spare1

},

drx-HARQ-RTT-TimerDL-PTM-r17 INTEGER (0..56) OPTIONAL, \-- Cond
HARQFeedback

drx-RetransmissionTimerDL-PTM-r17 ENUMERATED {

sl0, sl1, sl2, sl4, sl6, sl8, sl16, sl24, sl33, sl40, sl64, sl80, sl96,
sl112, sl128,

sl160, sl320, spare15, spare14, spare13, spare12, spare11, spare10,
spare9,

spare8, spare7, spare6, spare5, spare4, spare3, spare2, spare1

} OPTIONAL, \-- Cond HARQFeedback

drx-LongCycleStartOffsetPTM-r17 CHOICE {

ms10 INTEGER(0..9),

ms20 INTEGER(0..19),

ms32 INTEGER(0..31),

ms40 INTEGER(0..39),

ms60 INTEGER(0..59),

ms64 INTEGER(0..63),

ms70 INTEGER(0..69),

ms80 INTEGER(0..79),

ms128 INTEGER(0..127),

ms160 INTEGER(0..159),

ms256 INTEGER(0..255),

ms320 INTEGER(0..319),

ms512 INTEGER(0..511),

ms640 INTEGER(0..639),

ms1024 INTEGER(0..1023),

ms1280 INTEGER(0..1279),

ms2048 INTEGER(0..2047),

ms2560 INTEGER(0..2559),

ms5120 INTEGER(0..5119),

ms10240 INTEGER(0..10239)

},

drx-SlotOffsetPTM-r17 INTEGER (0..31)

}

\-- TAG-DRX-CONFIGPTM-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *DRX-ConfigPTM* field descriptions                                    |
+=======================================================================+
| ***drx-HARQ-RTT-TimerDL-PTM***                                        |
|                                                                       |
| Value in number of symbols of the CFR where the transport block was   |
| received.                                                             |
+-----------------------------------------------------------------------+
| ***drx-InactivityTimerPTM***                                          |
|                                                                       |
| Value in multiple integers of 1 ms. *ms0* corresponds to 0, *ms1*     |
| corresponds to 1 ms, *ms2* corresponds to 2 ms, and so on.            |
+-----------------------------------------------------------------------+
| ***drx-LongCycleStartOffsetPTM***                                     |
|                                                                       |
| *drx-LongCycle-PTM* in ms and *drx-StartOffset-PTM* in multiples of 1 |
| ms.                                                                   |
+-----------------------------------------------------------------------+
| ***drx-onDurationTimerPTM***                                          |
|                                                                       |
| Value in multiples of 1/32 ms (subMilliSeconds) or in ms              |
| (milliSecond). For the latter, value *ms1* corresponds to 1 ms, value |
| *ms2* corresponds to 2 ms, and so on.                                 |
+-----------------------------------------------------------------------+
| ***drx-RetransmissionTimerDL-PTM***                                   |
|                                                                       |
| Value in number of slot lengths of the CFR where the transport block  |
| was received. value *sl0* corresponds to 0 slots, *sl1* corresponds   |
| to 1 slot, *sl2* corresponds to 2 slots, and so on.                   |
+-----------------------------------------------------------------------+
| ***drx-SlotOffsetPTM***                                               |
|                                                                       |
| Value in 1/32 ms. Value 0 corresponds to 0 ms, value 1 corresponds to |
| 1/32 ms, value 2 corresponds to 2/32 ms, and so on.                   |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *HARQFeedback*       The field is mandatory present if HARQ feedback is
                       enabled for a G-RNTI/G-CS-RNTI associated with
                       this DRX configuration. It is optionally present.
                       Need R, otherwise.

  -----------------------------------------------------------------------

#### -- *MBS-NeighbourCellList*

The IE *MBS-NeighbourCellList* indicates a list of neighbour cells where
ongoing MBS sessions provided via broadcast/multicast MRB in the current
cell may also be provided, as indicated in the *mtch-NeighbourCell*.

*MBS-NeighbourCellList* information element

\-- ASN1START

\-- TAG-MBS-NEIGHBOURCELLLIST-START

MBS-NeighbourCellList-r17 ::= SEQUENCE (SIZE (0..maxNeighCellMBS-r17))
OF MBS-NeighbourCell-r17

MBS-NeighbourCell-r17 ::= SEQUENCE {

physCellId-r17 PhysCellId,

carrierFreq-r17 ARFCN-ValueNR OPTIONAL \-- Need S

}

\-- TAG-MBS-NEIGHBOURCELLLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MBS-NeighbourCellList* field descriptions                            |
+=======================================================================+
| ***carrierFreq***                                                     |
|                                                                       |
| Indicates the frequency of the neighbour cell indicated by            |
| *physCellId*. Absence of the IE means that the neighbour cell is on   |
| the same frequency as the current cell.                               |
+-----------------------------------------------------------------------+

#### -- *MBS-NonServingInfoList*

The IE *MBS-NonServingInfoList* is used to inform network of the
frequencies, CFR information and subcarrier spacing for MBS broadcast
reception on the non-serving cell.

*MBS-NonServingInfoList* information element

\-- ASN1START

\-- TAG-MBS-NONSERVINGINFOLIST-START

MBS-NonServingInfoList-r18 ::= SEQUENCE (SIZE (1..maxFreqMBS-r17)) OF
NonServingInfo-r18

NonServingInfo-r18 ::= SEQUENCE {

freqInfoMBS-r18 FreqInfoMBS-r18 OPTIONAL,

cfr-InfoMBS-r18 CHOICE {

cfr-Bandwidth-r18 INTEGER (1..maxNrofPhysicalResourceBlocks),

cfr-LocationAndBW-r18 CFR-LocationAndBW-r18

} OPTIONAL,

subcarrierSpacing-r18 SubcarrierSpacing OPTIONAL

}

FreqInfoMBS-r18 ::= SEQUENCE {

carrierFreqMBS-r18 ARFCN-ValueNR,

freqBandIndicatorMBS-r18 FreqBandIndicatorNR

}

CFR-LocationAndBW-r18 ::= SEQUENCE {

locationAndBandwidthMBS-r18 INTEGER (0..37949) OPTIONAL,

absoluteFrequencyPointA-MBS-r18 ARFCN-ValueNR OPTIONAL,

offsetToCarrierMBS-r18 INTEGER (0..2199) OPTIONAL

}

\-- TAG-MBS-NONSERVINGINFOLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MBS-NonServingInfoList* field descriptions                           |
+-----------------------------------------------------------------------+
| ***freqInfoMBS***                                                     |
|                                                                       |
| Indicates MBS frequency of interest and the frequency band of the     |
| non-serving cell for MBS broadcast reception as specified in clause   |
| 5.9.4.3.                                                              |
+-----------------------------------------------------------------------+
| ***cfr-infoMBS***                                                     |
|                                                                       |
| Indicates the CFR information of the non-serving cell for MBS         |
| broadcast reception. It is up to UE implementation to choose          |
| *cfr-Bandwidth* or *cfr-LocationAndBW* as the reported CFR            |
| information.                                                          |
+-----------------------------------------------------------------------+
| ***cfr-Bandwidth***                                                   |
|                                                                       |
| Indicates the CFR bandwidth of the non-serving cell for MBS broadcast |
| reception.                                                            |
+-----------------------------------------------------------------------+
| ***cfr-LocationAndBW***                                               |
|                                                                       |
| Indicates the CFR location and bandwidth of the non-serving cell for  |
| MBS broadcast reception.                                              |
+-----------------------------------------------------------------------+
| ***subcarrierSpacing***                                               |
|                                                                       |
| Indicates the subcarrier spacing of the CORESET#0 of the non-serving  |
| cell for MBS broadcast reception.                                     |
+=======================================================================+

+-----------------------------------------------------------------------+
| *CFR-LocationAndBW* field descriptions                                |
+-----------------------------------------------------------------------+
| ***locationAndBandwidthMBS***                                         |
|                                                                       |
| Indicates the starting PRB and the number of PRBs of CFR used for MBS |
| broadcast reception from non-serving cell. The value of the field     |
| shall be interpreted as resource indicator value (RIV) as defined in  |
| TS 38.214 \[19\] with assumptions as described in TS 38.213 \[13\].   |
| The first PRB is a PRB determined by *subcarrierSpacing*,             |
| *offsetToCarrierMBS* and *absoluteFrequencyPointA-MBS* of the         |
| non-serving cell.                                                     |
+-----------------------------------------------------------------------+
| ***absoluteFrequencyPointA-MBS***                                     |
|                                                                       |
| Indicates the absolute frequency position of the reference resource   |
| block (common RB 0) of the non-serving cell for MBS broadcast         |
| reception. Its lowest subcarrier is also known as Point A (see TS     |
| 38.211 \[16\], clause 4.4.4.2).                                       |
+-----------------------------------------------------------------------+
| ***offsetToCarrierMBS***                                              |
|                                                                       |
| Indicates the offset in frequency domain between Point A (lowest      |
| subcarrier of common RB 0) and the lowest usable subcarrier on this   |
| carrier in number of PRBs (using the *subcarrierSpacing* indicated    |
| for the non-serving cell).                                            |
+=======================================================================+

#### -- *MBS-ServiceList*

The IE *MBS-* *ServiceList* is used to inform the network of the MBS
services that the UE is receiving or interested to receive.

*MBS-ServiceList* information element

\-- ASN1START

\-- TAG-MBS-SERVICELIST-START

MBS-ServiceList-r17 ::= SEQUENCE (SIZE
(1..maxNrofMBS-ServiceListPerUE-r17)) OF MBS-ServiceInfo-r17

MBS-ServiceInfo-r17 ::= SEQUENCE {

tmgi-r17 TMGI-r17

}

\-- TAG-MBS-SERVICELIST-STOP

\-- ASN1STOP

#### -- *MBS-SessionInfoList*

The IE *MBS-SessionInfoList* provides the list of ongoing MBS broadcast
sessions transmitted via broadcast MRB and, for each MBS broadcast
session, the associated G-RNTI and scheduling information.

*MBS-SessionInfoList* information element

\-- ASN1START

\-- TAG-MBS-SESSIONINFOLIST-START

MBS-SessionInfoList-r17 ::= SEQUENCE (SIZE (1..maxNrofMBS-Session-r17))
OF MBS-SessionInfo-r17

MBS-SessionInfo-r17 ::= SEQUENCE {

mbs-SessionId-r17 TMGI-r17,

g-RNTI-r17 RNTI-Value,

mrb-ListBroadcast-r17 MRB-ListBroadcast-r17,

mtch-SchedulingInfo-r17 DRX-ConfigPTM-Index-r17 OPTIONAL, \-- Need S

mtch-NeighbourCell-r17 BIT STRING (SIZE(maxNeighCellMBS-r17)) OPTIONAL,
\-- Need S

pdsch-ConfigIndex-r17 PDSCH-ConfigIndex-r17 OPTIONAL, \-- Need S

mtch-SSB-MappingWindowIndex-r17 MTCH-SSB-MappingWindowIndex-r17 OPTIONAL
\-- Cond MTCH-Mapping

}

DRX-ConfigPTM-Index-r17 ::= INTEGER (0..maxNrofDRX-ConfigPTM-1-r17)

PDSCH-ConfigIndex-r17 ::= INTEGER (0..maxNrofPDSCH-ConfigPTM-1-r17)

MTCH-SSB-MappingWindowIndex-r17 ::= INTEGER
(0..maxNrofMTCH-SSB-MappingWindow-1-r17)

MRB-ListBroadcast-r17 ::= SEQUENCE (SIZE (1..maxNrofMRB-Broadcast-r17))
OF MRB-InfoBroadcast-r17

MRB-InfoBroadcast-r17 ::= SEQUENCE {

pdcp-Config-r17 MRB-PDCP-ConfigBroadcast-r17,

rlc-Config-r17 MRB-RLC-ConfigBroadcast-r17,

\...

}

MRB-PDCP-ConfigBroadcast-r17 ::= SEQUENCE {

pdcp-SN-SizeDL-r17 ENUMERATED {len12bits} OPTIONAL, \-- Need S

headerCompression-r17 CHOICE {

notUsed NULL,

rohc SEQUENCE {

maxCID-r17 INTEGER (1..16) DEFAULT 15,

profiles-r17 SEQUENCE {

profile0x0000-r17 BOOLEAN,

profile0x0001-r17 BOOLEAN,

profile0x0002-r17 BOOLEAN

}

}

},

t-Reordering-r17 ENUMERATED {ms1, ms10, ms40, ms160, ms500, ms1000,
ms1250, ms2750} OPTIONAL \-- Need S

}

MRB-RLC-ConfigBroadcast-r17 ::= SEQUENCE {

logicalChannelIdentity-r17 LogicalChannelIdentity,

sn-FieldLength-r17 ENUMERATED {size6} OPTIONAL, \-- Need S

t-Reassembly-r17 T-Reassembly OPTIONAL \-- Need S

}

\-- TAG-MBS-SESSIONINFOLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MBS-SessionInfoList* field descriptions                              |
+=======================================================================+
| ***g-RNTI***                                                          |
|                                                                       |
| G-RNTI used to scramble the scheduling and transmission of MTCH.      |
+-----------------------------------------------------------------------+
| ***headerCompression***                                               |
|                                                                       |
| If *rohc* is configured, the UE shall apply the configured ROHC       |
| profile(s) in downlink.                                               |
+-----------------------------------------------------------------------+
| ***mbs-SessionId***                                                   |
|                                                                       |
| Indicates an identifier of the MBS session provided by the MTCH.      |
+-----------------------------------------------------------------------+
| ***mrb-listBroadcast***                                               |
|                                                                       |
| A list of broadcast MRBs to which the associated broadcast MBS        |
| session is mapped to.                                                 |
+-----------------------------------------------------------------------+
| ***mtch-neighbourCell***                                              |
|                                                                       |
| Indicates neighbour cells which provide this service on MTCH. The     |
| first bit is set to 1 if the service is provided on MTCH in the first |
| cell in *mbs-NeighbourCellList*, otherwise it is set to 0. The second |
| bit is set to 1 if the service is provided on MTCH in the second cell |
| in *mbs-NeighbourCellList*, and so on. If the service is not          |
| available in any neighbouring cell and *mbs-NeighbourCellList* is     |
| signalled, the network sets all bits in this field to 0. The field is |
| absent when *mbs-NeighbourCellList* is absent or an empty             |
| *mbs-NeighbourCellList* is signalled. If this field is absent when    |
| *mbs-NeighbourCellList* is absent or a non-empty                      |
| *mbs-NeighbourCellList* is signalled, the related service may or may  |
| not be available in any neighbouring cell, i.e. the UE cannot         |
| determine the presence or absence of an MBS service in neighbouring   |
| cells based on the absence of this field. If this field is absent and |
| an empty *mbs-NeighbourCellList* is signalled, then the UE shall      |
| assume that MBS broadcast services signalled in *mbs-SessionInfoList* |
| in the *MBSBroadcastConfiguration* message are not provided in any    |
| neighbour cell.                                                       |
+-----------------------------------------------------------------------+
| ***mtch-schedulingInfo***                                             |
|                                                                       |
| Indicates the index of DRX configuration entry in                     |
| *drx-ConfigPTM-List* that is used for scheduling the MTCH. The value  |
| 0 corresponds to the first entry in *drx-ConfigPTM-List*, the value 1 |
| corresponds to the second entry in *drx-ConfigPTM-List* and so on. In |
| case *mtch-schedulingInfo* is absent for a G-RNTI (i.e. no PTM DRX),  |
| the UE shall monitor for PDCCH scrambled with G-RNTI in any slot      |
| according to the search space configured for MTCH \[see TS 38.213     |
| \[13\], clause 10.1\].                                                |
+-----------------------------------------------------------------------+
| ***mtch-SSB-MappingWindowIndex***                                     |
|                                                                       |
| Indicates the index of *MTCH-SSB-MappingWindowCycleOffset*            |
| configuration entry in *MTCH-SSB-MappingWindowList*. The value 0      |
| corresponds to the first entry in *MTCH-SSB-MappingWindowList*, the   |
| value 1 corresponds to the second entry in                            |
| *MTCH-SSB-MappingWindowList* and so on. This field is set to the same |
| value for all MBS sessions mapped to the same G-RNTI.                 |
+-----------------------------------------------------------------------+
| ***pdcp-SN-SizeDL***                                                  |
|                                                                       |
| Indicates that PDCP sequence number size of 12 bits is used, as       |
| specified in TS 38.323 \[5\]. When the field is absent the UE applies |
| the value as specified in 9.1.1.7.                                    |
+-----------------------------------------------------------------------+
| ***pdschConfigIndex***                                                |
|                                                                       |
| Indicates the index of PDSCH configuration entry in *pdschConfigList* |
| for MTCH. Value 0 corresponds to the first entry in                   |
| *pdschConfigList*, the value 1 corresponds to the second entry in     |
| *pdschConfigList* and so on. When the field is absent the UE applies  |
| the first entry in pdschConfigList for MTCH.                          |
+-----------------------------------------------------------------------+
| ***sn-FieldLength***                                                  |
|                                                                       |
| Indicates that the RLC SN field size of 6 bits is used, see TS 38.322 |
| \[4\]. When the field is absent the UE applies the value as specified |
| in 9.1.1.7.                                                           |
+-----------------------------------------------------------------------+
| ***t-Reassembly***                                                    |
|                                                                       |
| Timer for reassembly in TS 38.322 \[4\], in milliseconds. Value ms0   |
| means 0 ms, value ms5 means 5 ms and so on. When the field is absent  |
| the UE applies the value in specified in 9.1.1.7.                     |
+-----------------------------------------------------------------------+
| ***t-Reordering***                                                    |
|                                                                       |
| Value in ms of t-Reordering specified in TS 38.323 \[5\]. Value ms1   |
| corresponds to 1 ms, value ms10 corresponds to 10 ms, and so on. When |
| the field is absent the UE applies the value as specified in 9.1.1.7. |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *MTCH-Mapping*       The field is mandatory present if the number of
                       actual transmitted SSBs determined according to
                       *ssb-PositionsInBurst* in SIB1 is more than 1, and
                       *searchspaceMTCH* is not set to zero (including
                       the case where *searchSpaceMTCH* is absent and
                       *searchSpaceMCCH* is not set to zero). Otherwise,
                       it is absent, Need R.

  -----------------------------------------------------------------------

#### -- *MBS-SessionInfoListMulticast*

The IE *MBS-SessionInfoListMulticast* provides a list of MBS multicast
sessions transmitted via multicast MRB for RRC_INACTIVE UEs and, for
each MBS multicast session, the associated G-RNTI and scheduling
information.

*MBS-SessionInfoListMulticast* information element

\-- ASN1START

\-- TAG-MBS-SESSIONINFOLISTMULTICAST-START

MBS-SessionInfoListMulticast-r18 ::= SEQUENCE (SIZE
(1..maxNrofMBS-Session-r17)) OF MBS-SessionInfoMulticast-r18

MBS-SessionInfoMulticast-r18 ::= SEQUENCE {

mbs-SessionId-r18 TMGI-r17,

g-RNTI-r18 RNTI-Value OPTIONAL, \-- Need R

mrb-ListMulticast-r18 MRB-ListMulticast-r18 OPTIONAL, \-- Need R

mtch-SchedulingInfo-r18 DRX-ConfigPTM-Index-r17 OPTIONAL, \-- Need S

mtch-NeighbourCell-r18 BIT STRING (SIZE(maxNeighCellMBS-r17)) OPTIONAL,
\-- Need S

pdsch-ConfigIndex-r18 PDSCH-ConfigIndex-r17 OPTIONAL, \-- Need S

mtch-SSB-MappingWindowIndex-r18 MTCH-SSB-MappingWindowIndex-r17
OPTIONAL, \-- Cond MTCH-Mapping

thresholdIndex-r18 INTEGER (0..maxNrofThresholdMBS-1-r18) OPTIONAL, \--
Need R

pdcp-SyncIndicator-r18 ENUMERATED {true} OPTIONAL, \-- Cond RRCRelease

stopMonitoringRNTI-r18 ENUMERATED {true} OPTIONAL, \-- Cond G-RNTI

\...

}

MRB-ListMulticast-r18 ::= SEQUENCE (SIZE (1.. maxMRB-r17)) OF
MRB-InfoMulticast-r18

MRB-InfoMulticast-r18 ::= SEQUENCE {

pdcp-Config-r18 MRB-PDCP-ConfigMulticast-r18,

rlc-Config-r18 MRB-RLC-ConfigMulticast-r18,

\...

}

MRB-PDCP-ConfigMulticast-r18 ::= SEQUENCE {

pdcp-SN-SizeDL-r18 ENUMERATED {len12bits, len18bits},

headerCompression-r18 CHOICE {

notUsed NULL,

rohc SEQUENCE {

maxCID-r18 INTEGER (1..16) DEFAULT 15,

profiles-r18 SEQUENCE {

profile0x0000-r18 BOOLEAN,

profile0x0001-r18 BOOLEAN,

profile0x0002-r18 BOOLEAN

}

}

},

t-Reordering-r17 ENUMERATED {ms1, ms10, ms40, ms160, ms500, ms1000,
ms1250, ms2750} OPTIONAL \-- Need R

}

MRB-RLC-ConfigMulticast-r18 ::= SEQUENCE {

logicalChannelIdentity-r18 CHOICE {

logicalChannelIdentitymulticast-r18 LogicalChannelIdentity,

logicalChannelIdentityExt-r18 LogicalChannelIdentityExt-r17

},

sn-FieldLength-r18 ENUMERATED {size6, size12},

t-Reassembly-r18 T-Reassembly OPTIONAL \-- Need R

}

\-- TAG-MBS-SESSIONINFOLISTMULTICAST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MBS-SessionInfoListMulticast* field descriptions                     |
+=======================================================================+
| ***g-RNTI***                                                          |
|                                                                       |
| G-RNTI used to scramble the scheduling and transmission of multicast  |
| MTCH.                                                                 |
+-----------------------------------------------------------------------+
| ***mbs-SessionId***                                                   |
|                                                                       |
| Indicates an identifier of the MBS session to be received by the UE   |
| in RRC_INACTIVE.                                                      |
+-----------------------------------------------------------------------+
| ***mrb-ListMulticast***                                               |
|                                                                       |
| A list of multicast MRBs to which the associated MBS multicast        |
| session is mapped to.                                                 |
+-----------------------------------------------------------------------+
| ***mtch-NeighbourCell***                                              |
|                                                                       |
| Indicates neighbour cells which provide this service on MTCH for      |
| RRC_INACTIVE. The first bit is set to 1 if the service is provided on |
| MTCH in the first cell in *mbs-NeighbourCellList*, otherwise it is    |
| set to 0. The second bit is set to 1 if the service is provided on    |
| MTCH in the second cell in *mbs-NeighbourCellList*, and so on. If the |
| service is not available in any neighbouring cell and                 |
| *mbs-NeighbourCellList* is signalled, the network sets all bits in    |
| this field to 0. The field is absent when *mbs-NeighbourCellList* is  |
| absent or an empty *mbs-NeighbourCellList* is signalled. If this      |
| field is absent when *mbs-NeighbourCellList* is absent or a non-empty |
| *mbs-NeighbourCellList* is signalled, the related service may or may  |
| not be available in any neighbouring cell, i.e. the UE cannot         |
| determine the presence or absence of an MBS service in neighbouring   |
| cells based on the absence of this field. If this field is absent and |
| an empty *mbs-NeighbourCellList* is signalled, then the UE shall      |
| assume that MBS multicast services signalled in                       |
| *mbs-SessionInfoListMulticast* in the *MBSMulticastConfiguration*     |
| message are not provided in any neighbour cell.                       |
+-----------------------------------------------------------------------+
| ***mtch-SchedulingInfo***                                             |
|                                                                       |
| Indicates the index of DRX configuration entry in                     |
| *drx-ConfigPTM-List* that is used for scheduling the MTCH. The value  |
| 0 corresponds to the first entry in *drx-ConfigPTM-List*, the value 1 |
| corresponds to the second entry in *drx-ConfigPTM-List* and so on. In |
| case *mtch-schedulingInfo* is absent for a G-RNTI (i.e. no PTM DRX),  |
| the UE shall monitor for PDCCH scrambled with G-RNTI in any slot      |
| according to the search space configured for MTCH.                    |
+-----------------------------------------------------------------------+
| ***mtch-SSB-MappingWindowIndex***                                     |
|                                                                       |
| Indicates the index of *MTCH-SSB-MappingWindowCycleOffset*            |
| configuration entry in *MTCH-SSB-MappingWindowList*. The value 0      |
| corresponds to the first entry in *MTCH-SSB-MappingWindowList*, the   |
| value 1 corresponds to the second entry in                            |
| *MTCH-SSB-MappingWindowList* and so on. This field is set to the same |
| value for all MBS sessions mapped to the same G-RNTI.                 |
+-----------------------------------------------------------------------+
| ***pdcp-SN-SizeDL***                                                  |
|                                                                       |
| Indicates PDCP sequence number size of 12 or 18 bits, as specified in |
| TS 38.323 \[5\].                                                      |
+-----------------------------------------------------------------------+
| ***pdsch-ConfigIndex***                                               |
|                                                                       |
| Indicates the index of PDSCH configuration entry in                   |
| *pdsch-ConfigList* for MTCH. Value 0 corresponds to the first entry   |
| in *pdsch-ConfigList*, the value 1 corresponds to the second entry in |
| *pdsch-ConfigList* and so on. When the field is absent the UE applies |
| the first entry in *pdsch-ConfigList* for MTCH.                       |
+-----------------------------------------------------------------------+
| ***pdcp-SyncIndicator***                                              |
|                                                                       |
| Indicates the PDCP COUNT of the corresponding multicast session is    |
| synchronized in the RNA, i.e. the cells in the RNA follow a common    |
| QoS flow to MRB mapping rule and at the same time PDCP COUNT is set   |
| according to the MBS QoS Flow SN.                                     |
+-----------------------------------------------------------------------+
| ***sn-FieldLength***                                                  |
|                                                                       |
| Indicates RLC SN field size of 6 or12 bits, as specified in TS 38.322 |
| \[4\].                                                                |
+-----------------------------------------------------------------------+
| ***stopMonitoringRNTI***                                              |
|                                                                       |
| Indicates the UE to stop monitoring the G-RNTI for the corresponding  |
| multicast session.                                                    |
+-----------------------------------------------------------------------+
| ***t-Reassembly***                                                    |
|                                                                       |
| Timer for reassembly in TS 38.322 \[4\], in milliseconds. Value ms0   |
| means 0 ms, value ms5 means 5 ms and so on.                           |
+-----------------------------------------------------------------------+
| ***t-Reordering***                                                    |
|                                                                       |
| Value in ms of *t-Reordering* specified in TS 38.323 \[5\]. Value ms1 |
| corresponds to 1 ms, value ms10 corresponds to 10 ms, and so on.      |
+-----------------------------------------------------------------------+
| ***thresholdIndex***                                                  |
|                                                                       |
| Indicates the index of *thresholdMBS* entry in *thresholdMBS-List*    |
| that is used for RRC connection resume for a UE receiving the         |
| corresponding multicast session in RRC_INACTIVE. Value 0 corresponds  |
| to the first entry in *thresholdMBS-List*, the value 1 corresponds to |
| the second entry in *thresholdMBS-List* and so on.                    |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *G-RNTI*             The field is optionally present, Need R, if
                       *g-RNTI* is included. Otherwise, it is absent.

  *MTCH-Mapping*       The field is mandatory present if the number of
                       actual transmitted SSBs determined according to
                       *ssb-PositionsInBurst* in SIB1 is more than 1, and
                       *searchSpaceMulticastMTCH* is not set to zero
                       (including the case where
                       *searchSpaceMulticastMTCH* is absent and
                       *searchSpaceMulticastMCCH* is not set to zero).
                       Otherwise, it is absent, Need R.

  *RRCRelease*         The field is optionally present, Need R, if
                       *mbs-SessionInfoListMulticast* is included in
                       *RRCRelease* message. Otherwise, it is absent.
  -----------------------------------------------------------------------

#### -- *MTCH-SSB-MappingWindowList*

The IE *MTCH-SSB-MappingWindowList* is used to configure MTCH PDCCH
ocassions to SSB mapping window related periodic and offset parameters.

*MTCH-SSB-MappingWindowList* information element

\-- ASN1START

\-- TAG-MTCH-SSB-MAPPINGWINDOWLIST-START

MTCH-SSB-MappingWindowList-r17 ::= SEQUENCE (SIZE
(1..maxNrofMTCH-SSB-MappingWindow-r17)) OF
MTCH-SSB-MappingWindowCycleOffset-r17

MTCH-SSB-MappingWindowCycleOffset-r17 ::= CHOICE {

ms10 INTEGER(0..9),

ms20 INTEGER(0..19),

ms32 INTEGER(0..31),

ms64 INTEGER(0..63),

ms128 INTEGER(0..127),

ms256 INTEGER(0..255)

}

\-- TAG-MTCH-SSB-MAPPINGWINDOWLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MTCH-SSB-MappingWindowList* field descriptions                       |
+=======================================================================+
| ***MTCH-SSB-MappingWindowCycleOffset***                               |
|                                                                       |
| Indicates the *cycle* and *offset* for MTCH PDCCH ocassions to SSB    |
| mapping. Values in unit of ms. *ms10* corresponds to cycle of 10 ms   |
| with corresponding offset between 0 and 9 ms, value *ms20*            |
| corresponds to cycle of 20 ms with corresponding offset between 0 and |
| 19 ms, and so on. The mapping window starts at a subframe in a SFN    |
| where \[(SFN number × 10) + subframe number\] modulo (*cycle*) =      |
| *offset.*                                                             |
|                                                                       |
| PDCCH monitoring occasions for MTCH in a mapping window which are not |
| overlapping with UL symbols (determined according to                  |
| *tdd-UL-DL-ConfigurationCommon*) are sequentially numbered starting   |
| from 1 in the maping window. The \[x×N+K\]^th^ PDCCH monitoring       |
| occasion for MTCH in this mapping window corresponds to the K^th^     |
| transmitted SSB, where x = 0, 1, \...X-1, K = 1, 2, ...N, N is the    |
| number of actual transmitted SSBs determined according to             |
| *ssb-PositionsInBurst* in *SIB1* and X is equal to CEIL(number of     |
| PDCCH monitoring occasions in MTCH to SSB mapping transmission        |
| window/N). The actual transmitted SSBs are sequentially numbered from |
| one in ascending order of their SSB indexes.                          |
+-----------------------------------------------------------------------+

#### -- *PDSCH-ConfigBroadcast*

The IE *PDSCH-ConfigBroadcast* is used to configure parameters for
acquiring the PDSCH for MCCH, multicast MCCH and MTCH.

*PDSCH-ConfigBroadcast* information element

\-- ASN1START

\-- TAG-PDSCH-CONFIGBROADCAST-START

PDSCH-ConfigBroadcast-r17 ::= SEQUENCE {

pdschConfigList-r17 SEQUENCE (SIZE (1..maxNrofPDSCH-ConfigPTM-r17) ) OF
PDSCH-ConfigPTM-r17,

pdsch-TimeDomainAllocationList-r17
PDSCH-TimeDomainResourceAllocationList-r16 OPTIONAL, \-- Need R

rateMatchPatternToAddModList-r17 SEQUENCE (SIZE
(1..maxNrofRateMatchPatterns)) OF RateMatchPattern OPTIONAL, \-- Need R

lte-CRS-ToMatchAround-r17 RateMatchPatternLTE-CRS OPTIONAL, \-- Need R

mcs-Table-r17 ENUMERATED {qam256, qam64LowSE} OPTIONAL, \-- Need S

xOverhead-r17 ENUMERATED {xOh6, xOh12, xOh18} OPTIONAL \-- Need S

}

PDSCH-ConfigPTM-r17 ::= SEQUENCE {

dataScramblingIdentityPDSCH-r17 INTEGER (0..1023) OPTIONAL, \-- Need S

dmrs-ScramblingID0-r17 INTEGER (0..65535) OPTIONAL, \-- Need S

pdsch-AggregationFactor-r17 ENUMERATED {n2, n4, n8} OPTIONAL \-- Need S

}

\-- TAG-PDSCH-CONFIGBROADCAST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *PDSCH-ConfigBroadcast* field descriptions                            |
+=======================================================================+
| ***lte-CRS-ToMatchAround***                                           |
|                                                                       |
| Parameters to determine an LTE CRS pattern that the UE shall rate     |
| match around.                                                         |
+-----------------------------------------------------------------------+
| ***pdschConfigList***                                                 |
|                                                                       |
| List of PDSCH parameters which can be configured per G-RNTI. Only one |
| entry is allowed to be configured if included in *SIB20* or *SIB24*.  |
+-----------------------------------------------------------------------+
| ***pdsch-TimeDomainAllocationList***                                  |
|                                                                       |
| List of time-domain configurations for timing of DL assignment to DL  |
| data.                                                                 |
|                                                                       |
| The field *pdsch-TimeDomainAllocationList* applies to DCI format 4_0  |
| (see table 5.1.2.1.1-1 in TS 38.214 \[19\]). When the field is        |
| absent, the UE follows PDSCH time domain resource allocation          |
| determination rule as specified in TS 38.214 \[19\], clause           |
| 5.1.2.1.1.                                                            |
+-----------------------------------------------------------------------+
| ***rateMatchPatternToAddModList***                                    |
|                                                                       |
| Resources patterns which the UE should rate match PDSCH around. The   |
| UE rate matches around the union of all resources indicated in the    |
| rate match patterns (see TS 38.214 \[19\], clause 5.1.4.1).           |
+-----------------------------------------------------------------------+
| ***mcs-Table***                                                       |
|                                                                       |
| Indicates which MCS table the UE shall use for PDSCH. If the field is |
| absent the UE applies the value 64QAM. The field *mcs-Table* applies  |
| to DCI format 4_0 with CRC scrambled by MCCH-RNTI/G-RNTI for MBS      |
| broadcast or by Multicast MCCH-RNTI for MBS multicast in              |
| RRC_INACTIVE, and applies to DCI format 4_1 with CRC scrambled by     |
| G-RNTI for MBS multicast in RRC_INACTIVE (see TS 38.214 \[19\],       |
| clause 5.1.3.1).                                                      |
+-----------------------------------------------------------------------+
| ***xOverhead***                                                       |
|                                                                       |
| Accounts for an overhead from CSI-RS, CORESET, etc. If the field is   |
| absent, the UE applies value xOh0 (see TS 38.214 \[19\], clause       |
| 5.1.3.2).                                                             |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *PDSCH-ConfigPTM* field descriptions                                  |
+=======================================================================+
| ***dataScramblingIdentityPDSCH***                                     |
|                                                                       |
| Identifier(s) used to initialize data scrambling (c_init) for PDSCH   |
| as specified in TS 38.211 \[16\], clause 7.3.1.1. When the field is   |
| absent the UE applies the value physCellId configured for this        |
| serving cell.                                                         |
+-----------------------------------------------------------------------+
| ***dmrs-ScramblingID0***                                              |
|                                                                       |
| DL DMRS scrambling initialization (see TS 38.211 \[16\], clause       |
| 7.4.1.1.1). When the field is absent the UE applies the value         |
| *physCellId* configured for this serving cell.                        |
+-----------------------------------------------------------------------+
| ***pdsch-AggregationFactor***                                         |
|                                                                       |
| Number of repetitions for dynamic scheduling of MBS broadcast data    |
| for MTCH PDSCH (see TS 38.214 \[19\], clause 5.1.2.1). When the field |
| is absent the UE applies the value 1.                                 |
+-----------------------------------------------------------------------+

#### -- *TMGI*

The IE *TMGI* is used to identify the MBS session.

*TMGI* information element

\-- ASN1START

\-- TAG-TMGI-START

TMGI-r17 ::= SEQUENCE {

plmn-Id-r17 CHOICE {

plmn-Index INTEGER (1..maxPLMN),

explicitValue PLMN-Identity

},

serviceId-r17 OCTET STRING (SIZE (3))

}

\-- TAG-TMGI-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *TMGI* field descriptions                                             |
+=======================================================================+
| ***plmn-Index***                                                      |
|                                                                       |
| PLMN index or NPN index according to the *plmn-IdentityInfoList* and  |
| *npn-IdentityInfoList* fields included in *SIB1*. If this field is    |
| included in the *MRB-ToAddMod-r17*, the UE translates the             |
| *plmn-Index* into the PLMN Identity or SNPN Identity based on the     |
| configuration in *SIB1* (which is the *SIB1* of the target cell in    |
| case of handover). The *explicitValue* is not used for MBS service(s) |
| of an SNPN.                                                           |
+-----------------------------------------------------------------------+
| ***serviceId***                                                       |
|                                                                       |
| Uniquely identifies the identity of an MBS service within a PLMN. The |
| field contains octet 3- 5 of the IE Temporary Mobile Group Identity   |
| (TMGI) as defined in TS 24.008 \[38\]. The first octet contains the   |
| third octet of the TMGI, the second octet contains the fourth octet   |
| of the TMGI and so on.                                                |
+-----------------------------------------------------------------------+