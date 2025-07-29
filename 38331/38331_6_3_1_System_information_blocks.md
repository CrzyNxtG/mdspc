### 6.3.1 System information blocks

#### -- *SIB2*

*SIB2* contains cell re-selection information common for
intra-frequency, inter-frequency and/or inter-RAT cell re-selection
(i.e. applicable for more than one type of cell re-selection but not
necessarily all) as well as intra-frequency cell re-selection
information other than neighbouring cell related.

*SIB2* information element

\-- ASN1START

\-- TAG-SIB2-START

SIB2 ::= SEQUENCE {

cellReselectionInfoCommon SEQUENCE {

nrofSS-BlocksToAverage INTEGER (2..maxNrofSS-BlocksToAverage) OPTIONAL,
\-- Need S

absThreshSS-BlocksConsolidation ThresholdNR OPTIONAL, \-- Need S

rangeToBestCell RangeToBestCell OPTIONAL, \-- Need R

q-Hyst ENUMERATED {

dB0, dB1, dB2, dB3, dB4, dB5, dB6, dB8, dB10,

dB12, dB14, dB16, dB18, dB20, dB22, dB24},

speedStateReselectionPars SEQUENCE {

mobilityStateParameters MobilityStateParameters,

q-HystSF SEQUENCE {

sf-Medium ENUMERATED {dB-6, dB-4, dB-2, dB0},

sf-High ENUMERATED {dB-6, dB-4, dB-2, dB0}

}

} OPTIONAL, \-- Need R

\...

},

cellReselectionServingFreqInfo SEQUENCE {

s-NonIntraSearchP ReselectionThreshold OPTIONAL, \-- Need S

s-NonIntraSearchQ ReselectionThresholdQ OPTIONAL, \-- Need S

threshServingLowP ReselectionThreshold,

threshServingLowQ ReselectionThresholdQ OPTIONAL, \-- Need R

cellReselectionPriority CellReselectionPriority,

cellReselectionSubPriority CellReselectionSubPriority OPTIONAL, \-- Need
R

\...

},

intraFreqCellReselectionInfo SEQUENCE {

q-RxLevMin Q-RxLevMin,

q-RxLevMinSUL Q-RxLevMin OPTIONAL, \-- Need R

q-QualMin Q-QualMin OPTIONAL, \-- Need S

s-IntraSearchP ReselectionThreshold,

s-IntraSearchQ ReselectionThresholdQ OPTIONAL, \-- Need S

t-ReselectionNR T-Reselection,

frequencyBandList MultiFrequencyBandListNR-SIB OPTIONAL, \-- Need S

frequencyBandListSUL MultiFrequencyBandListNR-SIB OPTIONAL, \-- Need R

p-Max P-Max OPTIONAL, \-- Need S

smtc SSB-MTC OPTIONAL, \-- Need S

ss-RSSI-Measurement SS-RSSI-Measurement OPTIONAL, \-- Need R

ssb-ToMeasure SSB-ToMeasure OPTIONAL, \-- Need S

deriveSSB-IndexFromCell BOOLEAN,

\...,

\[\[

t-ReselectionNR-SF SpeedStateScaleFactors OPTIONAL \-- Need R

\]\],

\[\[

smtc2-LP-r16 SSB-MTC2-LP-r16 OPTIONAL, \-- Need R

ssb-PositionQCL-Common-r16 SSB-PositionQCL-Relation-r16 OPTIONAL \--
Cond SharedSpectrum

\]\],

\[\[

ssb-PositionQCL-Common-r17 SSB-PositionQCL-Relation-r17 OPTIONAL \--
Cond SharedSpectrum2

\]\],

\[\[

smtc4list-r17 SSB-MTC4List-r17 OPTIONAL \-- Need R

\]\],

\[\[

frequencyBandList-v1760 MultiFrequencyBandListNR-SIB-v1760 OPTIONAL, \--
Need R

frequencyBandListSUL-v1760 MultiFrequencyBandListNR-SIB-v1760 OPTIONAL
\-- Need R

\]\],

\[\[

frequencyBandListAerial-r18 MultiFrequencyBandListNR-Aerial-SIB-r18
OPTIONAL \-- Need S

\]\]

},

\...,

\[\[

relaxedMeasurement-r16 SEQUENCE {

lowMobilityEvaluation-r16 SEQUENCE {

s-SearchDeltaP-r16 ENUMERATED {

dB3, dB6, dB9, dB12, dB15,

spare3, spare2, spare1},

t-SearchDeltaP-r16 ENUMERATED {

s5, s10, s20, s30, s60, s120, s180,

s240, s300, spare7, spare6, spare5,

spare4, spare3, spare2, spare1}

} OPTIONAL, \-- Need R

cellEdgeEvaluation-r16 SEQUENCE {

s-SearchThresholdP-r16 ReselectionThreshold,

s-SearchThresholdQ-r16 ReselectionThresholdQ OPTIONAL \-- Need R

} OPTIONAL, \-- Need R

combineRelaxedMeasCondition-r16 ENUMERATED {true} OPTIONAL, \-- Need R

highPriorityMeasRelax-r16 ENUMERATED {true} OPTIONAL \-- Need R

} OPTIONAL \-- Need R

\]\],

\[\[

cellEquivalentSize-r17 INTEGER(2..16) OPTIONAL, \-- Cond HSDN

relaxedMeasurement-r17 SEQUENCE {

stationaryMobilityEvaluation-r17 SEQUENCE {

s-SearchDeltaP-Stationary-r17 ENUMERATED {dB2, dB3, dB6, dB9, dB12,
dB15, spare2, spare1},

t-SearchDeltaP-Stationary-r17 ENUMERATED {s5, s10, s20, s30, s60, s120,
s180, s240, s300, spare7, spare6, spare5,

spare4, spare3, spare2, spare1}

},

cellEdgeEvaluationWhileStationary-r17 SEQUENCE {

s-SearchThresholdP2-r17 ReselectionThreshold,

s-SearchThresholdQ2-r17 ReselectionThresholdQ OPTIONAL \-- Need R

} OPTIONAL, \-- Need R

combineRelaxedMeasCondition2-r17 ENUMERATED {true} OPTIONAL \-- Need R

} OPTIONAL \-- Need R

\]\]

}

RangeToBestCell ::= Q-OffsetRange

\-- TAG-SIB2-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB2* field descriptions                                             |
+=======================================================================+
| ***absThreshSS-BlocksConsolidation***                                 |
|                                                                       |
| Threshold for consolidation of L1 measurements per RS index. If the   |
| field is absent, the UE uses the measurement quantity as specified in |
| TS 38.304 \[20\].                                                     |
+-----------------------------------------------------------------------+
| ***cellEdgeEvaluation***                                              |
|                                                                       |
| Indicates the criteria for a UE to detect that it is not at cell      |
| edge, in order to relax measurement requirements for cell reselection |
| (see TS 38.304 \[20\], clause 5.2.4.9.2).                             |
+-----------------------------------------------------------------------+
| ***cellEdgeEvaluationWhileStationary***                               |
|                                                                       |
| Indicates the criteria for a UE to detect that it is not at cell edge |
| while stationary, in order to relax measurement requirements for cell |
| reselection (see TS 38.304 \[20\], clause 5.2.4.9.4).                 |
+-----------------------------------------------------------------------+
| ***cellEquivalentSize***                                              |
|                                                                       |
| The number of cell count used for mobility state estimation for this  |
| cell as specified in TS 38.304 \[20\].                                |
+-----------------------------------------------------------------------+
| ***cellReselectionInfoCommon***                                       |
|                                                                       |
| Cell re-selection information common for intra-frequency,             |
| inter-frequency and/ or inter-RAT cell re-selection.                  |
+-----------------------------------------------------------------------+
| ***cellReselectionServingFreqInfo***                                  |
|                                                                       |
| Information common for non-intra-frequency cell re-selection i.e.     |
| cell re-selection to inter-frequency and inter-RAT cells.             |
+-----------------------------------------------------------------------+
| ***combineRelaxedMeasCondition***                                     |
|                                                                       |
| When both *lowMobilityEvaluation* and *cellEdgeEvaluation* criteria   |
| are present in SIB2, this parameter configures the UE to fulfil both  |
| criteria in order to relax measurement requirements for cell          |
| reselection. If the field is absent, the UE is allowed to relax       |
| measurement requirements for cell reselection when either or both of  |
| the criteria are met. (See TS 38.304 \[20\], clause 5.2.4.9.0)        |
+-----------------------------------------------------------------------+
| ***combineRelaxedMeasCondition2***                                    |
|                                                                       |
| When both *stationaryMobilityEvaluation* and                          |
| *cellEdgeEvaluationWhileStationary* criteria are present in SIB2,     |
| this parameter configures the UE to fulfil both criteria in order to  |
| relax measurement requirements for cell reselection. If the field is  |
| absent, the UE is allowed to relax measurement requirements for cell  |
| reselection when only the stationary criteria is met. (See TS 38.304  |
| \[20\], clause 5.2.4.9.0)                                             |
+-----------------------------------------------------------------------+
| ***deriveSSB-IndexFromCell***                                         |
|                                                                       |
| This field indicates whether the UE can utilize serving cell timing   |
| to derive the index of SS block transmitted by neighbour cell. If     |
| this field is set to *true*, the UE assumes SFN and frame boundary    |
| alignment across cells on the serving frequency as specified in TS    |
| 38.133 \[14\].                                                        |
+-----------------------------------------------------------------------+
| ***frequencyBandList***                                               |
|                                                                       |
| Indicates the list of frequency bands for which the NR cell           |
| reselection parameters apply. The UE behaviour in case the field is   |
| absent is described in clause 5.2.2.4.3.                              |
+-----------------------------------------------------------------------+
| ***frequencyBandListAerial***                                         |
|                                                                       |
| Indicates the list of frequency bands for aerial operation for which  |
| the NR cell reselection parameters apply. The UE behaviour in case    |
| the field is absent is described in clause 5.2.2.4.3.                 |
+-----------------------------------------------------------------------+
| ***highPriorityMeasRelax***                                           |
|                                                                       |
| Indicates whether measurements can be relaxed on high priority        |
| frequencies. If the field is absent, the UE shall not relax           |
| measurements on high priority frequencies beyond                      |
| \"T~higher_priority_search~\" unless both low mobility and not at     |
| cell edge criteria are fulfilled (see TS 38.133 \[14\], clauses       |
| 4.2.2.7, 4.2.2.10 and 4.2.2.11).                                      |
+-----------------------------------------------------------------------+
| ***intraFreqCellReselectionInfo***                                    |
|                                                                       |
| Cell re-selection information common for intra-frequency cells.       |
+-----------------------------------------------------------------------+
| ***lowMobilityEvaluation***                                           |
|                                                                       |
| Indicates the criteria for a UE to detect low mobility, in order to   |
| relax measurement requirements for cell reselection (see TS 38.304    |
| \[20\], clause 5.2.4.9.1).                                            |
+-----------------------------------------------------------------------+
| ***nrofSS-BlocksToAverage***                                          |
|                                                                       |
| Number of SS blocks to average for cell measurement derivation. If    |
| the field is absent the UE uses the measurement quantity as specified |
| in TS 38.304 \[20\].                                                  |
+-----------------------------------------------------------------------+
| ***p-Max***                                                           |
|                                                                       |
| Value in dBm applicable for the intra-frequency neighbouring NR       |
| cells. If absent the UE applies the maximum power according to TS     |
| 38.101-1 \[15\] in case of an FR1 cell, TS 38.101-2 \[39\] in case of |
| an FR2 cell or TS 38.101-5 \[75\] in case of an NTN cell. In this     |
| release of the specification, if *p-Max* is present on a carrier      |
| frequency in FR2, the UE shall ignore the field and applies the       |
| maximum power according to TS 38.101-2 \[39\] for FR2-1/2 or          |
| according to TS 38.101-5 \[75\] for FR2-NTN. This field is ignored by |
| IAB-MT and NCR-MT. The IAB-MT applies output power and emissions      |
| requirements, as specified in TS 38.174 \[63\]. The NCR-MT applies    |
| output power and emissions requirements as specified in TS 38.106     |
| \[79\].                                                               |
+-----------------------------------------------------------------------+
| ***q-Hyst***                                                          |
|                                                                       |
| Parameter \"*Q~hyst~*\" in TS 38.304 \[20\], Value in dB. Value *dB1* |
| corresponds to 1 dB, *dB2* corresponds to 2 dB and so on.             |
+-----------------------------------------------------------------------+
| ***q-HystSF***                                                        |
|                                                                       |
| Parameter \"Speed dependent ScalingFactor for Qhyst\" in TS 38.304    |
| \[20\]. The *sf-Medium* and *sf-High* concern the additional          |
| hysteresis to be applied, in Medium and High Mobility state           |
| respectively, to Qhyst as defined in TS 38.304 \[20\]. In dB. Value   |
| *dB-6* corresponds to -6dB, *dB-4* corresponds to -4dB and so on.     |
+-----------------------------------------------------------------------+
| ***q-QualMin***                                                       |
|                                                                       |
| Parameter \"Q~qualmin~\" in TS 38.304 \[20\], applicable for          |
| intra-frequency neighbour cells. If the field is absent, the UE       |
| applies the (default) value of negative infinity for Q~qualmin~.      |
+-----------------------------------------------------------------------+
| ***q-RxLevMin***                                                      |
|                                                                       |
| Parameter \"Q~rxlevmin~\" in TS 38.304 \[20\], applicable for         |
| intra-frequency neighbour cells.                                      |
+-----------------------------------------------------------------------+
| ***q-RxLevMinSUL***                                                   |
|                                                                       |
| Parameter \"Q~rxlevmin~\" in TS 38.304 \[20\], applicable for         |
| intra-frequency neighbour cells.                                      |
+-----------------------------------------------------------------------+
| ***rangeToBestCell***                                                 |
|                                                                       |
| Parameter \"rangeToBestCell\" in TS 38.304 \[20\]. The network        |
| configures only non-negative (in dB) values.                          |
+-----------------------------------------------------------------------+
| ***relaxedMeasurement***                                              |
|                                                                       |
| Configuration to allow relaxation of RRM measurement requirements for |
| cell reselection (see TS 38.304 \[20\], clause 5.2.4.9). In NTN, this |
| field is only applicable for GSO neighbour cells.                     |
+-----------------------------------------------------------------------+
| ***s-IntraSearchP***                                                  |
|                                                                       |
| Parameter \"S~IntraSearchP~\" in TS 38.304 \[20\].                    |
+-----------------------------------------------------------------------+
| ***s-IntraSearchQ***                                                  |
|                                                                       |
| Parameter \"S~IntraSearchQ~\" in TS 38.304 \[20\]. If the field is    |
| absent, the UE applies the (default) value of 0 dB for                |
| S~IntraSearchQ~.                                                      |
+-----------------------------------------------------------------------+
| ***s-NonIntraSearchP***                                               |
|                                                                       |
| Parameter \"S~nonIntraSearchP~\" in TS 38.304 \[20\]. If this field   |
| is absent, the UE applies the (default) value of infinity for         |
| S~nonIntraSearchP~.                                                   |
+-----------------------------------------------------------------------+
| ***s-NonIntraSearchQ***                                               |
|                                                                       |
| Parameter \"S~nonIntraSearchQ~\" in TS 38.304 \[20\]. If the field is |
| absent, the UE applies the (default) value of 0 dB for                |
| S~nonIntraSearchQ~.                                                   |
+-----------------------------------------------------------------------+
| ***s-SearchDeltaP***                                                  |
|                                                                       |
| Parameter \"S~SearchDeltaP~\" in TS 38.304 \[20\]. Value dB3          |
| corresponds to 3 dB, dB6 corresponds to 6 dB and so on.               |
+-----------------------------------------------------------------------+
| ***s-SearchDeltaP-Stationary***                                       |
|                                                                       |
| Parameter \"S~SearchDeltaP-Stationary~\" in TS 38.304 \[20\]. Value   |
| *dB2* corresponds to 2 dB, *dB3* corresponds to 3 dB and so on.       |
+-----------------------------------------------------------------------+
| ***s-SearchThresholdP, s-SearchThresholdP2***                         |
|                                                                       |
| Parameters \"S~SearchThresholdP~\" and \"S~SearchThresholdP2~\" in TS |
| 38.304 \[20\]. The network configures *s-SearchThresholdP* and        |
| *s-SearchThresholdP2* to be less than or equal to *s-IntraSearchP*    |
| and *s-NonIntraSearchP*.                                              |
+-----------------------------------------------------------------------+
| ***s-SearchThresholdQ, s-SearchThresholdQ2***                         |
|                                                                       |
| Parameters \"S~SearchThresholdQ~\" and \"S~SearchThresholdQ2~\" in TS |
| 38.304 \[20\]. The network configures *s-SearchThresholdQ* and        |
| *s-SearchThresholdQ2* to be less than or equal to *s-IntraSearchQ*    |
| and *s-NonIntraSearchQ*.                                              |
+-----------------------------------------------------------------------+
| ***smtc***                                                            |
|                                                                       |
| Measurement timing configuration for intra-frequency measurement. If  |
| this field is absent, the UE assumes that SSB periodicity is 5 ms for |
| the intra-frequency cells. If the field is broadcast by an NTN cell,  |
| the *offset* (derived from parameter *periodicityAndOffset*) is based |
| on the assumption that the gNB-UE propagation delay difference        |
| between the serving cell and neighbour cells equals to 0 ms, and UE   |
| can adjust the actual *offset* based on the actual propagation delay  |
| difference.                                                           |
+-----------------------------------------------------------------------+
| ***smtc2-LP***                                                        |
|                                                                       |
| Measurement timing configuration for intra-frequency neighbour cells  |
| with a Long Periodicity (LP) indicated by periodicity in *smtc2-LP*.  |
| The timing offset and duration are equal to the offset and duration   |
| indicated in *smtc* in *intraFreqCellReselectionInfo*. The            |
| periodicity in *smtc2-LP* can only be set to a value strictly larger  |
| than the periodicity in *smtc* in *intraFreqCellReselectionInfo*      |
| (e.g. if *smtc* indicates sf20 the Long Periodicity can only be set   |
| to sf40, sf80 or sf160, if *smtc* indicates sf160, *smtc2-LP* cannot  |
| be configured). The *pci-List*, if present, includes the physical     |
| cell identities of the intra-frequency neighbour cells with Long      |
| Periodicity. If *smtc2-LP* is absent, the UE assumes that there are   |
| no intra-frequency neighbour cells with a Long Periodicity. This      |
| field is not configured together with *smtc4list*.                    |
+-----------------------------------------------------------------------+
| ***smtc4list***                                                       |
|                                                                       |
| Measurement timing configuration list for NTN deployments. The offset |
| of each SSB-MTC4 in *smtc4list* is based on the assumption that the   |
| gNB-UE propagation delay difference between the serving cell and      |
| neighbour cells equals to 0 ms, and UE can adjust the actual *offset* |
| based on the actual propagation delay difference. For a UE that       |
| supports less SMTCs than what is included in this list, it is up to   |
| the UE to select which SMTCs to consider.                             |
+-----------------------------------------------------------------------+
| ***ssb-PositionQCL-Common***                                          |
|                                                                       |
| Indicates the QCL relation between SS/PBCH blocks for intra-frequency |
| neighbor cells as specified in TS 38.213 \[13\], clause 4.1.          |
+-----------------------------------------------------------------------+
| ***ssb-ToMeasure***                                                   |
|                                                                       |
| The set of SS blocks to be measured within the SMTC measurement       |
| duration (see TS 38.215 \[9\]). When the field is absent the UE       |
| measures on all SS-blocks.                                            |
+-----------------------------------------------------------------------+
| ***stationaryMobilityEvaluation***                                    |
|                                                                       |
| Indicates the criteria for a UE to detect stationary mobility, in     |
| order to relax measurement requirements for cell reselection (see TS  |
| 38.304 \[20\], clause 5.2.4.9.0).                                     |
+-----------------------------------------------------------------------+
| ***t-ReselectionNR***                                                 |
|                                                                       |
| Parameter \"Treselection~NR~\" in TS 38.304 \[20\].                   |
+-----------------------------------------------------------------------+
| ***t-ReselectionNR-SF***                                              |
|                                                                       |
| Parameter \"Speed dependent ScalingFactor for Treselection~NR~\" in   |
| TS 38.304 \[20\]. If the field is absent, the UE behaviour is         |
| specified in TS 38.304 \[20\].                                        |
+-----------------------------------------------------------------------+
| ***threshServingLowP***                                               |
|                                                                       |
| Parameter \"Thresh~Serving,\ LowP~\" in TS 38.304 \[20\].             |
+-----------------------------------------------------------------------+
| ***threshServingLowQ***                                               |
|                                                                       |
| Parameter \"Thresh~Serving,\ LowQ~\" in TS 38.304 \[20\].             |
+-----------------------------------------------------------------------+
| ***t-SearchDeltaP***                                                  |
|                                                                       |
| Parameter \"T~SearchDeltaP~\" in TS 38.304 \[20\]. Value in seconds.  |
| Value *s5* means 5 seconds, value *s10* means 10 seconds and so on.   |
+-----------------------------------------------------------------------+
| ***t-SearchDeltaP-Stationary***                                       |
|                                                                       |
| Parameter \"T~SearchDeltaP-Stationary~\" in TS 38.304 \[20\]. Value   |
| in seconds. Value *s5* means 5 seconds, value *s10* means 10 seconds  |
| and so on.                                                            |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *HSDN*               The field is optionally present, Need R, if
                       *speedStateReselectionPars* is present; otherwise
                       the field is not present.

  *SharedSpectrum*     This field is mandatory present if this
                       intra-frequency operates with shared spectrum
                       channel access in FR1. Otherwise, it is absent,
                       Need R.

  *SharedSpectrum2*    This field is optionally present if this
                       intra-frequency operates with shared spectrum
                       channel access in FR2-2, Need R. Otherwise, it is
                       absent, Need R.
  -----------------------------------------------------------------------

#### -- *SIB3*

*SIB3* contains neighbouring cell related information relevant only for
intra-frequency cell re-selection. The IE includes cells with specific
re-selection parameters as well as exclude-listed cells.

*SIB3* information element

\-- ASN1START

\-- TAG-SIB3-START

SIB3 ::= SEQUENCE {

intraFreqNeighCellList IntraFreqNeighCellList OPTIONAL, \-- Need R

intraFreqExcludedCellList IntraFreqExcludedCellList OPTIONAL, \-- Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...,

\[\[

intraFreqNeighCellList-v1610 IntraFreqNeighCellList-v1610 OPTIONAL, \--
Need R

intraFreqAllowedCellList-r16 IntraFreqAllowedCellList-r16 OPTIONAL, \--
Cond SharedSpectrum2

intraFreqCAG-CellList-r16 SEQUENCE (SIZE (1..maxPLMN)) OF
IntraFreqCAG-CellListPerPLMN-r16 OPTIONAL \-- Need R

\]\],

\[\[

intraFreqNeighHSDN-CellList-r17 IntraFreqNeighHSDN-CellList-r17
OPTIONAL, \-- Need R

intraFreqNeighCellList-v1710 IntraFreqNeighCellList-v1710 OPTIONAL \--
Need R

\]\],

\[\[

channelAccessMode2-r17 ENUMERATED {enabled} OPTIONAL \-- Need R

\]\]

}

IntraFreqNeighCellList ::= SEQUENCE (SIZE (1..maxCellIntra)) OF
IntraFreqNeighCellInfo

IntraFreqNeighCellList-v1610::= SEQUENCE (SIZE (1..maxCellIntra)) OF
IntraFreqNeighCellInfo-v1610

IntraFreqNeighCellList-v1710 ::= SEQUENCE (SIZE (1..maxCellIntra)) OF
IntraFreqNeighCellInfo-v1710

IntraFreqNeighCellInfo ::= SEQUENCE {

physCellId PhysCellId,

q-OffsetCell Q-OffsetRange,

q-RxLevMinOffsetCell INTEGER (1..8) OPTIONAL, \-- Need R

q-RxLevMinOffsetCellSUL INTEGER (1..8) OPTIONAL, \-- Need R

q-QualMinOffsetCell INTEGER (1..8) OPTIONAL, \-- Need R

\...

}

IntraFreqNeighCellInfo-v1610 ::= SEQUENCE {

ssb-PositionQCL-r16 SSB-PositionQCL-Relation-r16 OPTIONAL \-- Cond
SharedSpectrum2

}

IntraFreqNeighCellInfo-v1710 ::= SEQUENCE {

ssb-PositionQCL-r17 SSB-PositionQCL-Relation-r17 OPTIONAL \-- Cond
SharedSpectrum2

}

IntraFreqExcludedCellList ::= SEQUENCE (SIZE (1..maxCellExcluded)) OF
PCI-Range

IntraFreqAllowedCellList-r16 ::= SEQUENCE (SIZE (1..maxCellAllowed)) OF
PCI-Range

IntraFreqCAG-CellListPerPLMN-r16 ::= SEQUENCE {

plmn-IdentityIndex-r16 INTEGER (1..maxPLMN),

cag-CellList-r16 SEQUENCE (SIZE (1..maxCAG-Cell-r16)) OF PCI-Range

}

IntraFreqNeighHSDN-CellList-r17 ::= SEQUENCE (SIZE (1..maxCellIntra)) OF
PCI-Range

\-- TAG-SIB3-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB3* field descriptions                                             |
+=======================================================================+
| ***channelAccessMode2***                                              |
|                                                                       |
| If present, this field indicates that intra-frequency neighbor cells  |
| apply channel access mode procedures for operation with shared        |
| spectrum channel access in accordance with TS 37.213 \[48\], clause   |
| 4.4 for FR2-2. If absent, the intra-frequency neighbor cells do not   |
| apply any channel access procedure.                                   |
+-----------------------------------------------------------------------+
| ***intraFreqAllowedCellList***                                        |
|                                                                       |
| List of allow-listed intra-frequency neighbouring cells, see TS       |
| 38.304 \[20\], clause 5.2.4.                                          |
+-----------------------------------------------------------------------+
| ***intraFreqCAG-CellList***                                           |
|                                                                       |
| List of intra-frequency neighbouring CAG cells (as defined in TS      |
| 38.304 \[20\]) per PLMN.                                              |
+-----------------------------------------------------------------------+
| ***intraFreqExcludedCellList***                                       |
|                                                                       |
| List of exclude-listed intra-frequency neighbouring cells.            |
+-----------------------------------------------------------------------+
| ***intraFreqNeighCellList***                                          |
|                                                                       |
| List of intra-frequency neighbouring cells with specific cell         |
| re-selection parameters. If *intraFreqNeighCellList-v1610* is         |
| present, it shall contain the same number of entries, listed in the   |
| same order as in *intraFreqNeighCellList* (without suffix).           |
+-----------------------------------------------------------------------+
| ***intraFreqNeighHSDN-CellList***                                     |
|                                                                       |
| List of intra-frequency neighbouring HSDN cells as specified in TS    |
| 38.304 \[20\].                                                        |
+-----------------------------------------------------------------------+
| ***plmn-IdentityIndex***                                              |
|                                                                       |
| Index of the PLMN across the *plmn-IdentityInfoList* and              |
| *npn-IdentityInfoList* fields included in SIB1.                       |
+-----------------------------------------------------------------------+
| ***q-OffsetCell***                                                    |
|                                                                       |
| Parameter \"Qoffset~s,n~\" in TS 38.304 \[20\].                       |
+-----------------------------------------------------------------------+
| ***q-QualMinOffsetCell***                                             |
|                                                                       |
| Parameter \"Q~qualminoffsetcell~\" in TS 38.304 \[20\]. Actual value  |
| Q~qualminoffsetcell~ = field value \[dB\].                            |
+-----------------------------------------------------------------------+
| ***q-RxLevMinOffsetCell***                                            |
|                                                                       |
| Parameter \"Q~rxlevminoffsetcell~\" in TS 38.304 \[20\]. Actual value |
| Q~rxlevminoffsetcell~ = field value \* 2 \[dB\].                      |
+-----------------------------------------------------------------------+
| ***q-RxLevMinOffsetCellSUL***                                         |
|                                                                       |
| Parameter \"Q~rxlevminoffsetcellSUL~\" in TS 38.304 \[20\]. Actual    |
| value Q~rxlevminoffsetcellSUL~ = field value \* 2 \[dB\].             |
+-----------------------------------------------------------------------+
| ***ssb-PositionQCL***                                                 |
|                                                                       |
| Indicates the QCL relation between SS/PBCH blocks for a specific      |
| intra-frequency neighbor cell as specified in TS 38.213 \[13\],       |
| clause 4.1. If provided, the cell specific value overwrites the value |
| signalled by *ssb-PositionQCL-Common* in *SIB2* for the indicated     |
| cell.                                                                 |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *SharedSpectrum2*    The field is optional present, Need R, if this
                       intra-frequency or neighbor cell operates with
                       shared spectrum channel access. Otherwise, it is
                       absent, Need R.

  -----------------------------------------------------------------------

#### -- *SIB4*

*SIB4* contains information relevant for inter-frequency cell
re-selection (i.e. information about other NR frequencies and
inter-frequency neighbouring cells relevant for cell re-selection),
which can also be used for NR idle/inactive measurements. The IE
includes cell re-selection parameters common for a frequency as well as
cell specific re-selection parameters.

*SIB4* information element

\-- ASN1START

\-- TAG-SIB4-START

SIB4 ::= SEQUENCE {

interFreqCarrierFreqList InterFreqCarrierFreqList,

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...,

\[\[

interFreqCarrierFreqList-v1610 InterFreqCarrierFreqList-v1610 OPTIONAL
\-- Need R

\]\],

\[\[

interFreqCarrierFreqList-v1700 InterFreqCarrierFreqList-v1700 OPTIONAL
\-- Need R

\]\],

\[\[

interFreqCarrierFreqList-v1720 InterFreqCarrierFreqList-v1720 OPTIONAL
\-- Need R

\]\],

\[\[

interFreqCarrierFreqList-v1730 InterFreqCarrierFreqList-v1730 OPTIONAL
\-- Need R

\]\],

\[\[

interFreqCarrierFreqList-v1760 InterFreqCarrierFreqList-v1760 OPTIONAL
\-- Need R

\]\],

\[\[

interFreqCarrierFreqList-v1800 InterFreqCarrierFreqList-v1800 OPTIONAL
\-- Need R

\]\]

}

InterFreqCarrierFreqList ::= SEQUENCE (SIZE (1..maxFreq)) OF
InterFreqCarrierFreqInfo

InterFreqCarrierFreqList-v1610 ::= SEQUENCE (SIZE (1..maxFreq)) OF
InterFreqCarrierFreqInfo-v1610

InterFreqCarrierFreqList-v1700 ::= SEQUENCE (SIZE (1..maxFreq)) OF
InterFreqCarrierFreqInfo-v1700

InterFreqCarrierFreqList-v1720 ::= SEQUENCE (SIZE (1..maxFreq)) OF
InterFreqCarrierFreqInfo-v1720

InterFreqCarrierFreqList-v1730 ::= SEQUENCE (SIZE (1..maxFreq)) OF
InterFreqCarrierFreqInfo-v1730

InterFreqCarrierFreqList-v1760 ::= SEQUENCE (SIZE (1..maxFreq)) OF
InterFreqCarrierFreqInfo-v1760

InterFreqCarrierFreqList-v1800 ::= SEQUENCE (SIZE (1..maxFreq)) OF
InterFreqCarrierFreqInfo-v1800

InterFreqCarrierFreqInfo ::= SEQUENCE {

dl-CarrierFreq ARFCN-ValueNR,

frequencyBandList MultiFrequencyBandListNR-SIB OPTIONAL, \-- Cond
Mandatory

frequencyBandListSUL MultiFrequencyBandListNR-SIB OPTIONAL, \-- Need R

nrofSS-BlocksToAverage INTEGER (2..maxNrofSS-BlocksToAverage) OPTIONAL,
\-- Need S

absThreshSS-BlocksConsolidation ThresholdNR OPTIONAL, \-- Need S

smtc SSB-MTC OPTIONAL, \-- Need S

ssbSubcarrierSpacing SubcarrierSpacing,

ssb-ToMeasure SSB-ToMeasure OPTIONAL, \-- Need S

deriveSSB-IndexFromCell BOOLEAN,

ss-RSSI-Measurement SS-RSSI-Measurement OPTIONAL, \-- Need R

q-RxLevMin Q-RxLevMin,

q-RxLevMinSUL Q-RxLevMin OPTIONAL, \-- Need R

q-QualMin Q-QualMin OPTIONAL, \-- Need S

p-Max P-Max OPTIONAL, \-- Need S

t-ReselectionNR T-Reselection,

t-ReselectionNR-SF SpeedStateScaleFactors OPTIONAL, \-- Need S

threshX-HighP ReselectionThreshold,

threshX-LowP ReselectionThreshold,

threshX-Q SEQUENCE {

threshX-HighQ ReselectionThresholdQ,

threshX-LowQ ReselectionThresholdQ

} OPTIONAL, \-- Cond RSRQ

cellReselectionPriority CellReselectionPriority OPTIONAL, \-- Need R

cellReselectionSubPriority CellReselectionSubPriority OPTIONAL, \-- Need
R

q-OffsetFreq Q-OffsetRange DEFAULT dB0,

interFreqNeighCellList InterFreqNeighCellList OPTIONAL, \-- Need R

interFreqExcludedCellList InterFreqExcludedCellList OPTIONAL, \-- Need R

\...

}

InterFreqCarrierFreqInfo-v1610 ::= SEQUENCE {

interFreqNeighCellList-v1610 InterFreqNeighCellList-v1610 OPTIONAL, \--
Need R

smtc2-LP-r16 SSB-MTC2-LP-r16 OPTIONAL, \-- Need R

interFreqAllowedCellList-r16 InterFreqAllowedCellList-r16 OPTIONAL, \--
Cond SharedSpectrum2

ssb-PositionQCL-Common-r16 SSB-PositionQCL-Relation-r16 OPTIONAL, \--
Cond SharedSpectrum

interFreqCAG-CellList-r16 SEQUENCE (SIZE (1..maxPLMN)) OF
InterFreqCAG-CellListPerPLMN-r16 OPTIONAL \-- Need R

}

InterFreqCarrierFreqInfo-v1700 ::= SEQUENCE {

interFreqNeighHSDN-CellList-r17 InterFreqNeighHSDN-CellList-r17
OPTIONAL, \-- Need R

highSpeedMeasInterFreq-r17 ENUMERATED {true} OPTIONAL, \-- Need R

redCapAccessAllowed-r17 ENUMERATED {true} OPTIONAL, \-- Need R

ssb-PositionQCL-Common-r17 SSB-PositionQCL-Relation-r17 OPTIONAL, \--
Cond SharedSpectrum

interFreqNeighCellList-v1710 InterFreqNeighCellList-v1710 OPTIONAL \--
Cond SharedSpectrum2

}

InterFreqCarrierFreqInfo-v1720 ::= SEQUENCE {

smtc4list-r17 SSB-MTC4List-r17 OPTIONAL \-- Need R

}

InterFreqCarrierFreqInfo-v1730 ::= SEQUENCE {

channelAccessMode2-r17 ENUMERATED {enabled} OPTIONAL \-- Need R

}

InterFreqCarrierFreqInfo-v1760 ::= SEQUENCE {

frequencyBandList-v1760 MultiFrequencyBandListNR-SIB-v1760 OPTIONAL, \--
Need R

frequencyBandListSUL-v1760 MultiFrequencyBandListNR-SIB-v1760 OPTIONAL
\-- Need R

}

InterFreqCarrierFreqInfo-v1800 ::= SEQUENCE {

dl-CarrierFreq-r18 ARFCN-ValueNR OPTIONAL, \-- Cond LessThan5MHz

frequencyBandList-r18 MultiFrequencyBandListNR-SIB OPTIONAL, \-- Cond
LessThan5MHz

frequencyBandListAerial-r18 MultiFrequencyBandListNR-Aerial-SIB-r18
OPTIONAL, \-- Need S

mobileIAB-CellList-r18 PCI-Range OPTIONAL, \-- Need R

mobileIAB-Freq-r18 ENUMERATED {true} OPTIONAL, \-- Need R

eRedCapAccessAllowed-r18 ENUMERATED {true} OPTIONAL, \-- Need R

tn-AreaIdList-r18 SEQUENCE (SIZE (1..maxTN-AreaInfo-r18)) OF
TN-AreaId-r18 OPTIONAL, \-- Need R

accessAllowed2RxXR-r18 ENUMERATED {true} OPTIONAL \-- Need R

}

InterFreqNeighHSDN-CellList-r17 ::= SEQUENCE (SIZE (1..maxCellInter)) OF
PCI-Range

InterFreqNeighCellList ::= SEQUENCE (SIZE (1..maxCellInter)) OF
InterFreqNeighCellInfo

InterFreqNeighCellList-v1610 ::= SEQUENCE (SIZE (1..maxCellInter)) OF
InterFreqNeighCellInfo-v1610

InterFreqNeighCellList-v1710 ::= SEQUENCE (SIZE (1..maxCellInter)) OF
InterFreqNeighCellInfo-v1710

InterFreqNeighCellInfo ::= SEQUENCE {

physCellId PhysCellId,

q-OffsetCell Q-OffsetRange,

q-RxLevMinOffsetCell INTEGER (1..8) OPTIONAL, \-- Need R

q-RxLevMinOffsetCellSUL INTEGER (1..8) OPTIONAL, \-- Need R

q-QualMinOffsetCell INTEGER (1..8) OPTIONAL, \-- Need R

\...

}

InterFreqNeighCellInfo-v1610 ::= SEQUENCE {

ssb-PositionQCL-r16 SSB-PositionQCL-Relation-r16 OPTIONAL \-- Cond
SharedSpectrum2

}

InterFreqNeighCellInfo-v1710 ::= SEQUENCE {

ssb-PositionQCL-r17 SSB-PositionQCL-Relation-r17 OPTIONAL \-- Cond
SharedSpectrum2

}

InterFreqExcludedCellList ::= SEQUENCE (SIZE (1..maxCellExcluded)) OF
PCI-Range

InterFreqAllowedCellList-r16 ::= SEQUENCE (SIZE (1..maxCellAllowed)) OF
PCI-Range

InterFreqCAG-CellListPerPLMN-r16 ::= SEQUENCE {

plmn-IdentityIndex-r16 INTEGER (1..maxPLMN),

cag-CellList-r16 SEQUENCE (SIZE (1..maxCAG-Cell-r16)) OF PCI-Range

}

\-- TAG-SIB4-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB4* field descriptions                                             |
+=======================================================================+
| ***absThreshSS-BlocksConsolidation***                                 |
|                                                                       |
| Threshold for consolidation of L1 measurements per RS index. If the   |
| field is absent, the UE uses the measurement quantity as specified in |
| TS 38.304 \[20\].                                                     |
+-----------------------------------------------------------------------+
| ***accessAllowed2RxXR***                                              |
|                                                                       |
| Indicates if the cells on the frequency support 2Rx XR UEs. If        |
| present, 2Rx XR UEs shall consider only these NR frequencies in cell  |
| reselection evaluation.                                               |
+-----------------------------------------------------------------------+
| ***channelAccessMode2***                                              |
|                                                                       |
| If present, this field indicates that the neighbor cells on the       |
| inter-frequency apply channel access mode procedures for operation    |
| with shared spectrum channel access in accordance with TS 37.213      |
| \[48\], clause 4.4 for FR2-2. If absent, the neighbor cells on the    |
| inter-frequency do not apply any channel access procedure.            |
+-----------------------------------------------------------------------+
| ***deriveSSB-IndexFromCell***                                         |
|                                                                       |
| This field indicates whether the UE may use the timing of any         |
| detected cell on that frequency to derive the SSB index of all        |
| neighbour cells on that frequency. If this field is set to *true*,    |
| the UE assumes SFN and frame boundary alignment across cells on the   |
| neighbor frequency as specified in TS 38.133 \[14\].                  |
+-----------------------------------------------------------------------+
| ***dl-CarrierFreq***                                                  |
|                                                                       |
| This field indicates center frequency of the SS block of the          |
| neighbour cells, where the frequency corresponds to a GSCN value as   |
| specified in TS 38.101-1 \[15\] or TS 38.101-5 \[75\].                |
|                                                                       |
| For a neighbouring carrier frequency when *dl-CarrierFreq-r18* is     |
| included, the network sets the corresponding value of                 |
| *dl-CarrierFreq* (without suffix) to 250, and the UE applies          |
| *dl-CarrierFreq-r18* instead of *dl-CarrierFreq* (without suffix). In |
| such case, if the UE does not support the GSCN value corresponding to |
| the *dl-CarrierFreq-r18*, it ignores the corresponding neighbour      |
| cell.                                                                 |
+-----------------------------------------------------------------------+
| ***eRedCapAccessAllowed***                                            |
|                                                                       |
| Indicates whether eRedCap UEs are allowed to access cells on the      |
| frequency.                                                            |
+-----------------------------------------------------------------------+
| ***frequencyBandList***                                               |
|                                                                       |
| Indicates the list of frequency bands for which the NR cell           |
| reselection parameters apply. For a neighbouring carrier frequency    |
| when *frequencyBandList-r18* is included, the network sets the        |
| corresponding value of *freqBandIndicatorNR* in *frequencyBandList*   |
| (without suffix) to 200, and the UE applies *frequencyBandList-r18*   |
| instead of *frequencyBandList* (without suffix).                      |
+-----------------------------------------------------------------------+
| ***frequencyBandListAerial***                                         |
|                                                                       |
| Indicates the list of frequency bands for aerial operation for which  |
| the NR cell reselection parameters apply. The UE behaviour in case    |
| the field is absent is described in clause 5.2.2.4.5.                 |
+-----------------------------------------------------------------------+
| ***highSpeedMeasInterFreq***                                          |
|                                                                       |
| If the field is set to *true* and UE supports high speed              |
| inter-frequency IDLE/INACTIVE measurements, the UE shall apply the    |
| enhanced inter-frequency RRM requirements on the inter-frequency      |
| carrier to support high speed up to 500 km/h in RRC_IDLE/RRC_INACTIVE |
| as specified in TS 38.133 \[14\].                                     |
+-----------------------------------------------------------------------+
| ***interFreqAllowedCellList***                                        |
|                                                                       |
| List of allow-listed inter-frequency neighbouring cells, see TS       |
| 38.304 \[20\], clause 5.2.4.                                          |
+-----------------------------------------------------------------------+
| ***interFreqCAG-CellList***                                           |
|                                                                       |
| List of inter-frequency neighbouring CAG cells (as defined in TS      |
| 38.304 \[20\] per PLMN.                                               |
+-----------------------------------------------------------------------+
| ***interFreqCarrierFreqList***                                        |
|                                                                       |
| List of neighbouring carrier frequencies and frequency specific cell  |
| re-selection information. If *interFreqCarrierFreqList-v1610,         |
| interFreqCarrierFreqList-v1700, interFreqCarrierFreqList-v1720*,      |
| *interFreqCarrierFreqList-v1730,* *interFreqCarrierFreqList-v1760* or |
| *interFreqCarrierFreqInfo-v1800* are present, they shall contain the  |
| same number of entries, listed in the same order as in                |
| *interFreqCarrierFreqList* (without suffix).                          |
+-----------------------------------------------------------------------+
| ***interFreqExcludedCellList***                                       |
|                                                                       |
| List of exclude-listed inter-frequency neighbouring cells.            |
+-----------------------------------------------------------------------+
| ***interFreqNeighCellList***                                          |
|                                                                       |
| List of inter-frequency neighbouring cells with specific cell         |
| re-selection parameters. If *interFreqNeighCellList-v1610* is         |
| present, it shall contain the same number of entries, listed in the   |
| same order as in *interFreqNeighCellList* (without suffix).           |
+-----------------------------------------------------------------------+
| ***interFreqNeighHSDN-CellList***                                     |
|                                                                       |
| List of inter-frequency neighbouring HSDN cells as specified in TS    |
| 38.304 \[20\].                                                        |
+-----------------------------------------------------------------------+
| ***mobileIAB-CellList***                                              |
|                                                                       |
| Contains a PCI range on which mobile IAB cells may be deployed.       |
+-----------------------------------------------------------------------+
| ***mobileIAB-Freq***                                                  |
|                                                                       |
| If present, it indicates that a mobile IAB node may be deployed on    |
| the inter-frequency carrier.                                          |
+-----------------------------------------------------------------------+
| ***nrofSS-BlocksToAverage***                                          |
|                                                                       |
| Number of SS blocks to average for cell measurement derivation. If    |
| the field is absent, the UE uses the measurement quantity as          |
| specified in TS 38.304 \[20\].                                        |
+-----------------------------------------------------------------------+
| ***plmn-IdentityIndex***                                              |
|                                                                       |
| Index of the PLMN across the *plmn-IdentityInfoList* and              |
| *npn-IdentityInfoList* fields included in SIB1.                       |
+-----------------------------------------------------------------------+
| ***p-Max***                                                           |
|                                                                       |
| Value in dBm applicable for the neighbouring NR cells on this carrier |
| frequency. If absent the UE applies the maximum power according to TS |
| 38.101-1 \[15\] in case of an FR1 cell, TS 38.101-2 \[39\] in case of |
| an FR2 cell or TS 38.101-5 \[75\] in case of an NTN cell. In this     |
| release of the specification, if *p-Max* is present on a carrier      |
| frequency in FR2, the UE shall ignore the field and applies the       |
| maximum power according to TS 38.101-2 \[39\] for FR2-1/2 or          |
| according to TS 38.101-5 \[75\] for FR2-NTN. This field is ignored by |
| IAB-MT and NCR-MT. The IAB-MT applies output power and emissions      |
| requirements, as specified in TS 38.174 \[63\]. The NCR-MT applies    |
| output power and emissions requirements as specified in TS 38.106     |
| \[79\].                                                               |
+-----------------------------------------------------------------------+
| ***q-OffsetCell***                                                    |
|                                                                       |
| Parameter \"Qoffset~s,n~\" in TS 38.304 \[20\].                       |
+-----------------------------------------------------------------------+
| ***q-OffsetFreq***                                                    |
|                                                                       |
| Parameter \"Qoffset~frequency~\" in TS 38.304 \[20\].                 |
+-----------------------------------------------------------------------+
| ***q-QualMin***                                                       |
|                                                                       |
| Parameter \"Q~qualmin~\" in TS 38.304 \[20\]. If the field is absent, |
| the UE applies the (default) value of negative infinity for           |
| Q~qualmin~.                                                           |
+-----------------------------------------------------------------------+
| ***q-QualMinOffsetCell***                                             |
|                                                                       |
| Parameter \"Q~qualminoffsetcell~\" in TS 38.304 \[20\]. Actual value  |
| Q~qualminoffsetcell~ = field value \[dB\].                            |
+-----------------------------------------------------------------------+
| ***q-RxLevMin***                                                      |
|                                                                       |
| Parameter \"Q~rxlevmin~\" in TS 38.304 \[20\].                        |
+-----------------------------------------------------------------------+
| ***q-RxLevMinOffsetCell***                                            |
|                                                                       |
| Parameter \"Q~rxlevminoffsetcell~\" in TS 38.304 \[20\]. Actual value |
| Q~rxlevminoffsetcell~ = field value \* 2 \[dB\].                      |
+-----------------------------------------------------------------------+
| ***q-RxLevMinOffsetCellSUL***                                         |
|                                                                       |
| Parameter \"Q~rxlevminoffsetcellSUL~\" in TS 38.304 \[20\]. Actual    |
| value Q~rxlevminoffsetcellSUL~ = field value \* 2 \[dB\].             |
+-----------------------------------------------------------------------+
| ***q-RxLevMinSUL***                                                   |
|                                                                       |
| Parameter \"Q~rxlevmin~\" in TS 38.304 \[20\].                        |
+-----------------------------------------------------------------------+
| ***redCapAccessAllowed***                                             |
|                                                                       |
| Indicates whether RedCap UEs are allowed to access cells on the       |
| frequency.                                                            |
+-----------------------------------------------------------------------+
| ***smtc***                                                            |
|                                                                       |
| Measurement timing configuration for inter-frequency measurement. If  |
| this field is absent, the UE assumes that SSB periodicity is 5 ms in  |
| this frequency. If the field is broadcast by an NTN cell, the         |
| o*ffset* (derived from parameter *periodicityAndOffset*) is based on  |
| the assumption that the gNB-UE propagation delay difference between   |
| the serving cell and neighbour cells equals to 0 ms, and UE can       |
| adjust the actual o*ffset* based on the actual propagation delay      |
| difference.                                                           |
+-----------------------------------------------------------------------+
| ***smtc2-LP***                                                        |
|                                                                       |
| Measurement timing configuration for inter-frequency neighbour cells  |
| with a Long Periodicity (LP) indicated by periodicity in *smtc2-LP*.  |
| The timing offset and duration are equal to the offset and duration   |
| indicated in *smtc* in *InterFreqCarrierFreqInfo*. The periodicity in |
| *smtc2-LP* can only be set to a value strictly larger than the        |
| periodicity in *smtc* in *InterFreqCarrierFreqInfo* (e.g. if *smtc*   |
| indicates sf20 the Long Periodicity can only be set to sf40, sf80 or  |
| sf160, if *smtc* indicates sf160, *smtc2-LP* cannot be configured).   |
| The *pci-List*, if present, includes the physical cell identities of  |
| the inter-frequency neighbour cells with Long Periodicity. If         |
| *smtc2-LP* is absent, the UE assumes that there are no                |
| inter-frequency neighbour cells with a Long Periodicity. This field   |
| is not configured together with *smtc4list*.                          |
+-----------------------------------------------------------------------+
| ***smtc4list***                                                       |
|                                                                       |
| Measurement timing configuration list for NTN deployments. The offset |
| of each SSB-MTC4 in *smtc4list* is based on the assumption that the   |
| gNB-UE propagation delay difference between the serving cell and      |
| neighbour cells equals to 0 ms, and UE can adjust the actual *offset* |
| based on the actual propagation delay difference. For a UE that       |
| supports less SMTCs than what is included in this list, it is up to   |
| the UE to select which SMTCs to consider.                             |
+-----------------------------------------------------------------------+
| ***ssb-PositionQCL***                                                 |
|                                                                       |
| Indicates the QCL relation between SS/PBCH blocks for a specific      |
| neighbor cell as specified in TS 38.213 \[13\], clause 4.1. If        |
| provided, the cell specific value overwrites the common value         |
| signalled by *ssb-PositionQCL-Common* in *SIB4* for the indicated     |
| cell.                                                                 |
+-----------------------------------------------------------------------+
| ***ssb-PositionQCL-Common***                                          |
|                                                                       |
| Indicates the QCL relation between SS/PBCH blocks for inter-frequency |
| neighbor cells as specified in TS 38.213 \[13\], clause 4.1.          |
+-----------------------------------------------------------------------+
| ***ssb-ToMeasure***                                                   |
|                                                                       |
| The set of SS blocks to be measured within the SMTC measurement       |
| duration (see TS 38.215 \[9\]). When the field is absent the UE       |
| measures on all SS-blocks.                                            |
+-----------------------------------------------------------------------+
| ***ssbSubcarrierSpacing***                                            |
|                                                                       |
| Subcarrier spacing of SSB.                                            |
|                                                                       |
| Only the following values are applicable depending on the used        |
| frequency:                                                            |
|                                                                       |
| FR1: 15 or 30 kHz                                                     |
|                                                                       |
| FR2-1/FR2-NTN: 120 or 240 kHz                                         |
|                                                                       |
| FR2-2: 120, 480, or 960 kHz                                           |
+-----------------------------------------------------------------------+
| ***threshX-HighP***                                                   |
|                                                                       |
| Parameter \"Thresh~X,\ HighP~\" in TS 38.304 \[20\].                  |
+-----------------------------------------------------------------------+
| ***threshX-HighQ***                                                   |
|                                                                       |
| Parameter \"Thresh~X,\ HighQ~\" in TS 38.304 \[20\].                  |
+-----------------------------------------------------------------------+
| ***threshX-LowP***                                                    |
|                                                                       |
| Parameter \"Thresh~X,\ LowP~\" in TS 38.304 \[20\].                   |
+-----------------------------------------------------------------------+
| ***threshX-LowQ***                                                    |
|                                                                       |
| Parameter \"Thresh~X,\ LowQ~\" in TS 38.304 \[20\].                   |
+-----------------------------------------------------------------------+
| ***tn-AreaIdList***                                                   |
|                                                                       |
| List of TN area identifiers. The associated coverage information is   |
| provided in *SIB25*.                                                  |
+-----------------------------------------------------------------------+
| ***t-ReselectionNR***                                                 |
|                                                                       |
| Parameter \"Treselection~NR~\" in TS 38.304 \[20\].                   |
+-----------------------------------------------------------------------+
| ***t-ReselectionNR-SF***                                              |
|                                                                       |
| Parameter \"Speed dependent ScalingFactor for Treselection~NR~\" in   |
| TS 38.304 \[20\]. If the field is absent, the UE behaviour is         |
| specified in TS 38.304 \[20\].                                        |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *LessThan5MHz*       The field is mandatory present if the
                       *carrierBandwidth* in SIB1 indicates UL or DL
                       transmission bandwidth other than 15 PRB and the
                       corresponding neighbour cell(s) support(s) 12 PRB,
                       15 PRB or 20 PRB transmission bandwidth
                       configuration as defined in TS 38.101-1 \[15\], TS
                       38.211 \[16\] and TS 38.213 \[13\]. Otherwise, the
                       field is optional, Need R.

  *Mandatory*          The field is mandatory present in SIB4.

  *RSRQ*               The field is mandatory present if
                       *threshServingLowQ* is present in *SIB2*;
                       otherwise it is absent.

  *SharedSpectrum*     This field is mandatory present if this
                       inter-frequency operates with shared spectrum
                       channel access. Otherwise, it is absent, Need R.

  *SharedSpectrum2*    The field is optional present, Need R, if this
                       inter-frequency or neighbor cell operates with
                       shared spectrum channel access. Otherwise, it is
                       absent, Need R.
  -----------------------------------------------------------------------

#### -- *SIB5*

*SIB5* contains information relevant only for inter-RAT cell
re-selection i.e. information about E-UTRA frequencies and E-UTRAs
neighbouring cells relevant for cell re-selection. The IE includes cell
re-selection parameters common for a frequency.

*SIB5* information element

\-- ASN1START

\-- TAG-SIB5-START

SIB5 ::= SEQUENCE {

carrierFreqListEUTRA CarrierFreqListEUTRA OPTIONAL, \-- Need R

t-ReselectionEUTRA T-Reselection,

t-ReselectionEUTRA-SF SpeedStateScaleFactors OPTIONAL, \-- Need S

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...,

\[\[

carrierFreqListEUTRA-v1610 CarrierFreqListEUTRA-v1610 OPTIONAL \-- Need
R

\]\],

\[\[

carrierFreqListEUTRA-v1700 CarrierFreqListEUTRA-v1700 OPTIONAL, \-- Need
R

idleModeMeasVoiceFallback-r17 ENUMERATED{true} OPTIONAL \-- Need R

\]\],

\[\[

carrierFreqListEUTRA-v1800 CarrierFreqListEUTRA-v1800 OPTIONAL \-- Need
R

\]\]

}

CarrierFreqListEUTRA ::= SEQUENCE (SIZE (1..maxEUTRA-Carrier)) OF
CarrierFreqEUTRA

CarrierFreqListEUTRA-v1610 ::= SEQUENCE (SIZE (1..maxEUTRA-Carrier)) OF
CarrierFreqEUTRA-v1610

CarrierFreqListEUTRA-v1700 ::= SEQUENCE (SIZE (1..maxEUTRA-Carrier)) OF
CarrierFreqEUTRA-v1700

CarrierFreqListEUTRA-v1800 ::= SEQUENCE (SIZE (1..maxEUTRA-Carrier)) OF
CarrierFreqEUTRA-v1800

CarrierFreqEUTRA ::= SEQUENCE {

carrierFreq ARFCN-ValueEUTRA,

eutra-multiBandInfoList EUTRA-MultiBandInfoList OPTIONAL, \-- Need R

eutra-FreqNeighCellList EUTRA-FreqNeighCellList OPTIONAL, \-- Need R

eutra-ExcludedCellList EUTRA-FreqExcludedCellList OPTIONAL, \-- Need R

allowedMeasBandwidth EUTRA-AllowedMeasBandwidth,

presenceAntennaPort1 EUTRA-PresenceAntennaPort1,

cellReselectionPriority CellReselectionPriority OPTIONAL, \-- Need R

cellReselectionSubPriority CellReselectionSubPriority OPTIONAL, \-- Need
R

threshX-High ReselectionThreshold,

threshX-Low ReselectionThreshold,

q-RxLevMin INTEGER (-70..-22),

q-QualMin INTEGER (-34..-3),

p-MaxEUTRA INTEGER (-30..33),

threshX-Q SEQUENCE {

threshX-HighQ ReselectionThresholdQ,

threshX-LowQ ReselectionThresholdQ

} OPTIONAL \-- Cond RSRQ

}

CarrierFreqEUTRA-v1610 ::= SEQUENCE {

highSpeedEUTRACarrier-r16 ENUMERATED {true} OPTIONAL \-- Need R

}

CarrierFreqEUTRA-v1700 ::= SEQUENCE {

eutra-FreqNeighHSDN-CellList-r17 EUTRA-FreqNeighHSDN-CellList-r17
OPTIONAL \-- Need R

}

CarrierFreqEUTRA-v1800 ::= SEQUENCE {

eutra-MultiBandInfoListAerial-r18 EUTRA-MultiBandInfoListAerial-r18
OPTIONAL, \-- Need R

tn-AreaIdList-r18 SEQUENCE (SIZE (1..maxTN-AreaInfo-r18)) OF
TN-AreaId-r18 OPTIONAL \-- Need R

}

EUTRA-FreqNeighHSDN-CellList-r17 ::= SEQUENCE (SIZE (1..maxCellEUTRA))
OF EUTRA-PhysCellIdRange

EUTRA-FreqExcludedCellList ::= SEQUENCE (SIZE
(1..maxEUTRA-CellExcluded)) OF EUTRA-PhysCellIdRange

EUTRA-FreqNeighCellList ::= SEQUENCE (SIZE (1..maxCellEUTRA)) OF
EUTRA-FreqNeighCellInfo

EUTRA-FreqNeighCellInfo ::= SEQUENCE {

physCellId EUTRA-PhysCellId,

dummy EUTRA-Q-OffsetRange,

q-RxLevMinOffsetCell INTEGER (1..8) OPTIONAL, \-- Need R

q-QualMinOffsetCell INTEGER (1..8) OPTIONAL \-- Need R

}

\-- TAG-SIB5-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB5* field descriptions                                             |
+=======================================================================+
| ***carrierFreqListEUTRA***                                            |
|                                                                       |
| List of carrier frequencies of E-UTRA. If the                         |
| *carrierFreqListEUTRA-v1610/ carrierFreqListEUTRA-v1700/              |
| carrierFreqListEUTRA-v1800* is present, it shall contain the same     |
| number of entries, listed in the same order as in the                 |
| *carrierFreqListEUTRA* (without suffix).                              |
+-----------------------------------------------------------------------+
| ***dummy***                                                           |
|                                                                       |
| This field is not used in the specification. If received it shall be  |
| ignored by the UE.                                                    |
+-----------------------------------------------------------------------+
| ***eutra-ExcludedCellList***                                          |
|                                                                       |
| List of exclude-listed E-UTRA neighbouring cells.                     |
+-----------------------------------------------------------------------+
| ***eutra-FreqNeighHSDN-CellList***                                    |
|                                                                       |
| List of neighbouring EUTRA HSDN cells as specified in TS 36.304       |
| \[27\].                                                               |
+-----------------------------------------------------------------------+
| ***eutra-multiBandInfoList***                                         |
|                                                                       |
| Indicates the list of frequency bands in addition to the band         |
| represented by *carrierFreq* for which cell reselection parameters    |
| are common, and a list of *additionalPmax* and                        |
| *additionalSpectrumEmission* values, as defined in TS 36.101 \[22\],  |
| table 6.2.4-1, for the frequency bands in *eutra-multiBandInfoList*   |
+-----------------------------------------------------------------------+
| ***highSpeedEUTRACarrier***                                           |
|                                                                       |
| If the field is present, the UE shall apply the enhanced NR-EUTRA     |
| inter-RAT measurement requirements to support high speed up to 500    |
| km/h as specified in TS 38.133 \[14\] to the E-UTRA carrier.          |
+-----------------------------------------------------------------------+
| ***idleModeMeasVoiceFallback***                                       |
|                                                                       |
| Indicates whether E-UTRA idle/inactive measurements and reporting for |
| EPS fallback can be used.                                             |
+-----------------------------------------------------------------------+
| ***p-MaxEUTRA***                                                      |
|                                                                       |
| The maximum allowed transmission power in dBm on the (uplink) carrier |
| frequency, see TS 36.304 \[27\].                                      |
+-----------------------------------------------------------------------+
| ***q-QualMin***                                                       |
|                                                                       |
| Parameter \"Q*~qualmin~*\" in TS 36.304 \[27\]. Actual value          |
| Q~qualmin~ = field value \[dB\].                                      |
+-----------------------------------------------------------------------+
| ***q-QualMinOffsetCell***                                             |
|                                                                       |
| Parameter \"*Q~qualminoffsetcell~*\" in TS 36.304 \[27\]. Actual      |
| value Q~qualminoffsetcell~ = field value \[dB\].                      |
+-----------------------------------------------------------------------+
| ***q-RxLevMin***                                                      |
|                                                                       |
| Parameter \"Q*~rxlevmin~*\" in TS 36.304 \[27\]. Actual value         |
| Q~rxlevmin~ = field value \* 2 \[dBm\].                               |
+-----------------------------------------------------------------------+
| ***q-RxLevMinOffsetCell***                                            |
|                                                                       |
| Parameter \"*Q~rxlevminoffsetcell~*\" in TS 36.304 \[27\]. Actual     |
| value Q~rxlevminoffsetcell~ = field value \* 2 \[dB\].                |
+-----------------------------------------------------------------------+
| ***t-ReselectionEUTRA***                                              |
|                                                                       |
| Parameter \"Treselection~EUTRA~\" in TS 38.304 \[20\].                |
+-----------------------------------------------------------------------+
| ***threshX-High***                                                    |
|                                                                       |
| Parameter \"Thresh~X,\ HighP~\" in TS 38.304 \[20\].                  |
+-----------------------------------------------------------------------+
| ***threshX-HighQ***                                                   |
|                                                                       |
| Parameter \"Thresh~X,\ HighQ~\" in TS 38.304 \[20\].                  |
+-----------------------------------------------------------------------+
| ***threshX-Low***                                                     |
|                                                                       |
| Parameter \"Thresh~X,\ LowP~\" in TS 38.304 \[20\].                   |
+-----------------------------------------------------------------------+
| ***threshX-LowQ***                                                    |
|                                                                       |
| Parameter \"Thresh~X,\ LowQ~\" in TS 38.304 \[20\].                   |
+-----------------------------------------------------------------------+
| ***tn-AreaIdList***                                                   |
|                                                                       |
| List of TN area identifiers. The associated coverage information is   |
| provided in *SIB25*.                                                  |
+-----------------------------------------------------------------------+
| ***t-ReselectionEUTRA-SF***                                           |
|                                                                       |
| Parameter \"Speed dependent ScalingFactor for Treselection~EUTRA~\"   |
| in TS 38.304 \[20\]. If the field is absent, the UE behaviour is      |
| specified in TS 38.304 \[20\].                                        |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *RSRQ*               The field is mandatory present if the
                       *threshServingLowQ* is present in *SIB2*;
                       otherwise it is absent.

  -----------------------------------------------------------------------

#### *-- SIB6*

*SIB6* contains an ETWS primary notification.

*SIB6* information element

\-- ASN1START

\-- TAG-SIB6-START

SIB6 ::= SEQUENCE {

messageIdentifier BIT STRING (SIZE (16)),

serialNumber BIT STRING (SIZE (16)),

warningType OCTET STRING (SIZE (2)),

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

\-- TAG-SIB6-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB6* field descriptions                                             |
+=======================================================================+
| ***messageIdentifier***                                               |
|                                                                       |
| Identifies the source and type of ETWS notification.                  |
+-----------------------------------------------------------------------+
| ***serialNumber***                                                    |
|                                                                       |
| Identifies variations of an ETWS notification.                        |
+-----------------------------------------------------------------------+
| ***warningType***                                                     |
|                                                                       |
| Identifies the warning type of the ETWS primary notification and      |
| provides information on emergency user alert and UE popup.            |
+-----------------------------------------------------------------------+

#### *-- SIB7*

*SIB7* contains an ETWS secondary notification.

*SIB7* information element

\-- ASN1START

\-- TAG-SIB7-START

SIB7 ::= SEQUENCE {

messageIdentifier BIT STRING (SIZE (16)),

serialNumber BIT STRING (SIZE (16)),

warningMessageSegmentType ENUMERATED {notLastSegment, lastSegment},

warningMessageSegmentNumber INTEGER (0..63),

warningMessageSegment OCTET STRING,

dataCodingScheme OCTET STRING (SIZE (1)) OPTIONAL, \-- Cond Segment1

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

\-- TAG-SIB7-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB7* field descriptions                                             |
+=======================================================================+
| ***dataCodingScheme***                                                |
|                                                                       |
| Identifies the alphabet/coding and the language applied variations of |
| an ETWS notification.                                                 |
+-----------------------------------------------------------------------+
| ***messageIdentifier***                                               |
|                                                                       |
| Identifies the source and type of ETWS notification.                  |
+-----------------------------------------------------------------------+
| ***serialNumber***                                                    |
|                                                                       |
| Identifies variations of an ETWS notification.                        |
+-----------------------------------------------------------------------+
| ***warningMessageSegment***                                           |
|                                                                       |
| Carries a segment of the Warning Message Contents IE.                 |
+-----------------------------------------------------------------------+
| ***warningMessageSegmentNumber***                                     |
|                                                                       |
| Segment number of the ETWS warning message segment contained in the   |
| SIB. A segment number of zero corresponds to the first segment, A     |
| segment number of one corresponds to the second segment, and so on.   |
+-----------------------------------------------------------------------+
| ***warningMessageSegmentType***                                       |
|                                                                       |
| Indicates whether the included ETWS warning message segment is the    |
| last segment or not.                                                  |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *Segment1*           The field is mandatory present in the first
                       segment of *SIB7*, otherwise it is absent.

  -----------------------------------------------------------------------

#### *-- SIB8*

*SIB8* contains a CMAS notification.

*SIB8* information element

\-- ASN1START

\-- TAG-SIB8-START

SIB8 ::= SEQUENCE {

messageIdentifier BIT STRING (SIZE (16)),

serialNumber BIT STRING (SIZE (16)),

warningMessageSegmentType ENUMERATED {notLastSegment, lastSegment},

warningMessageSegmentNumber INTEGER (0..63),

warningMessageSegment OCTET STRING,

dataCodingScheme OCTET STRING (SIZE (1)) OPTIONAL, \-- Cond Segment1

warningAreaCoordinatesSegment OCTET STRING OPTIONAL, \-- Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

\-- TAG-SIB8-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB8* field descriptions                                             |
+=======================================================================+
| ***dataCodingScheme***                                                |
|                                                                       |
| Identifies the alphabet/coding and the language applied variations of |
| a CMAS notification.                                                  |
+-----------------------------------------------------------------------+
| ***messageIdentifier***                                               |
|                                                                       |
| Identifies the source and type of CMAS notification.                  |
+-----------------------------------------------------------------------+
| ***serialNumber***                                                    |
|                                                                       |
| Identifies variations of a CMAS notification.                         |
+-----------------------------------------------------------------------+
| ***warningAreaCoordinatesSegment***                                   |
|                                                                       |
| If present, carries a segment, with one or more octets, of the        |
| geographical area where the CMAS warning message is valid as defined  |
| in \[28\]. The first octet of the first                               |
| *warningAreaCoordinatesSegment* is equivalent to the first octet of   |
| Warning Area Coordinates IE defined in and encoded according to TS    |
| 23.041 \[29\] and so on.                                              |
+-----------------------------------------------------------------------+
| ***warningMessageSegment***                                           |
|                                                                       |
| Carries a segment, with one or more octets, of the *Warning Message   |
| Contents* IE defined in TS 38.413 \[42\]. The first octet of the      |
| *Warning Message Contents* IE is equivalent to the first octet of the |
| *CB data* IE defined in and encoded according to TS 23.041 \[29\],    |
| clause 9.4.2.2.5, and so on.                                          |
+-----------------------------------------------------------------------+
| ***warningMessageSegmentNumber***                                     |
|                                                                       |
| Segment number of the CMAS warning message segment contained in the   |
| SIB. A segment number of zero corresponds to the first segment, one   |
| corresponds to the second segment, and so on. If warning area         |
| coordinates are provided for the warning message, then this field     |
| applies to both warning message segment and warning area coordinates  |
| segment.                                                              |
+-----------------------------------------------------------------------+
| ***warningMessageSegmentType***                                       |
|                                                                       |
| Indicates whether the included CMAS warning message segment is the    |
| last segment or not. If warning area coordinates are provided for the |
| warning message, then this field applies to both warning message      |
| segment and warning area coordinates segment.                         |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *Segment1*           The field is mandatory present in the first
                       segment of *SIB8*, otherwise it is absent.

  -----------------------------------------------------------------------

#### -- *SIB9*

*SIB9* contains information related to GPS time and Coordinated
Universal Time (UTC). The UE may use the parameters provided in this
system information block to obtain the UTC, the GPS and the local time.

NOTE: The UE may use the time information for numerous purposes,
possibly involving upper layers e.g. to assist GPS initialisation, to
synchronise the UE clock.

*SIB9* information element

\-- ASN1START

\-- TAG-SIB9-START

SIB9 ::= SEQUENCE {

timeInfo SEQUENCE {

timeInfoUTC INTEGER (0..549755813887),

dayLightSavingTime BIT STRING (SIZE (2)) OPTIONAL, \-- Need R

leapSeconds INTEGER (-127..128) OPTIONAL, \-- Need R

localTimeOffset INTEGER (-63..64) OPTIONAL \-- Need R

} OPTIONAL, \-- Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...,

\[\[

referenceTimeInfo-r16 ReferenceTimeInfo-r16 OPTIONAL \-- Need R

\]\],

\[\[

eventID-TSS-r18 INTEGER (0..63) OPTIONAL \-- Need R

\]\]

}

\-- TAG-SIB9-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB9* field descriptions                                             |
+=======================================================================+
| ***dayLightSavingTime***                                              |
|                                                                       |
| Indicates if and how daylight-saving time (DST) is applied to obtain  |
| the local time. The semantics are the same as the semantics of the    |
| *Daylight Saving Time* IE in TS 24.501 \[23\] and TS 24.008 \[38\].   |
| The first/leftmost bit of the bit string contains the b2 of octet 3   |
| and the second bit of the bit string contains b1 of octet 3 in the    |
| value part of the *Daylight Saving Time* IE in TS 24.008 \[38\].      |
+-----------------------------------------------------------------------+
| ***eventID-TSS***                                                     |
|                                                                       |
| This field indicates the status of the 5G access stratum time         |
| distribution parameter Clock Quality Reporting Control Information as |
| defined in TS 23.501 \[32\].                                          |
+-----------------------------------------------------------------------+
| ***leapSeconds***                                                     |
|                                                                       |
| Number of leap seconds offset between GPS Time and UTC. UTC and GPS   |
| time are related i.e. GPS time -leapSeconds = UTC time.               |
+-----------------------------------------------------------------------+
| ***localTimeOffset***                                                 |
|                                                                       |
| Offset between UTC and local time in units of 15 minutes. Actual      |
| value = field value \* 15 minutes. Local time of the day is           |
| calculated as UTC time + localTimeOffset.                             |
+-----------------------------------------------------------------------+
| ***timeInfoUTC***                                                     |
|                                                                       |
| Coordinated Universal Time corresponding to the SFN boundary at or    |
| immediately after the ending boundary of the SI-window in which SIB9  |
| is transmitted. In an NTN cell, the indicated time is referenced at   |
| the uplink time synchronization reference point (RP), i.e., UE should |
| take into account the propagation delay between UE and RP when        |
| determining the UTC time at the UE. The field counts the number of    |
| UTC seconds in 10 ms units since 00:00:00 on Gregorian calendar date  |
| 1 January, 1900 (midnight between Sunday, December 31, 1899 and       |
| Monday, January 1, 1900). See NOTE 1. This field is excluded when     |
| determining changes in system information, i.e. changes of            |
| *timeInfoUTC* should neither result in system information change      |
| notifications nor in a modification of *valueTag* in *SIB1*.          |
+-----------------------------------------------------------------------+

NOTE 1: The UE may use this field together with the *leapSeconds* field
to obtain GPS time as follows: GPS Time (in seconds) = timeInfoUTC (in
seconds) - 2,524,953,600 (seconds) + leapSeconds, where 2,524,953,600 is
the number of seconds between 00:00:00 on Gregorian calendar date 1
January, 1900 and 00:00:00 on Gregorian calendar date 6 January, 1980
(start of GPS time).

#### -- *SIB10*

*SIB10* contains the HRNNs of the NPNs listed in SIB1.

***SIB10* information element**

\-- ASN1START

\-- TAG-SIB10-START

SIB10-r16 ::= SEQUENCE {

hrnn-List-r16 HRNN-List-r16 OPTIONAL, \-- Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

HRNN-List-r16 ::= SEQUENCE (SIZE (1..maxNPN-r16)) OF HRNN-r16

HRNN-r16 ::= SEQUENCE {

hrnn-r16 OCTET STRING (SIZE(1.. maxHRNN-Len-r16)) OPTIONAL \-- Need R

}

\-- TAG-SIB10-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB10* field descriptions                                            |
+=======================================================================+
| ***HRNN-List***                                                       |
|                                                                       |
| The same amount of HRNN (see TS 23.003 \[21\]) elements as the number |
| of NPNs in SIB 1 are included. The n-th entry of *HRNN-List* contains |
| the human readable network name of the n-th NPN of SIB1. The *hrnn*   |
| in the corresponding entry in *HRNN-List* is absent if there is no    |
| HRNN associated with the given NPN.                                   |
+-----------------------------------------------------------------------+

#### -- *SIB11*

*SIB11* contains information related to idle/inactive measurements.

*SIB11* information element

\-- ASN1START

\-- TAG-SIB11-START

SIB11-r16 ::= SEQUENCE {

measIdleConfigSIB-r16 MeasIdleConfigSIB-r16 OPTIONAL, \-- Need S

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

\-- TAG-SIB11-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB11* field descriptions                                            |
+=======================================================================+
| ***measIdleConfigSIB***                                               |
|                                                                       |
| Indicates measurement configuration to be stored and used by the UE   |
| while in RRC_IDLE or RRC_INACTIVE.                                    |
+-----------------------------------------------------------------------+

#### -- *SIB12*

SIB12 contains NR sidelink communication/discovery configuration.

*SIB12* information element

\-- ASN1START

\-- TAG-SIB12-START

SIB12-r16 ::= SEQUENCE {

segmentNumber-r16 INTEGER (0..63),

segmentType-r16 ENUMERATED {notLastSegment, lastSegment},

segmentContainer-r16 OCTET STRING

}

SIB12-IEs-r16 ::= SEQUENCE {

sl-ConfigCommonNR-r16 SL-ConfigCommonNR-r16,

lateNonCriticalExtension OCTET STRING (CONTAINING SIB12-IEs-v16k0)
OPTIONAL,

\...,

\[\[

sl-DRX-ConfigCommonGC-BC-r17 SL-DRX-ConfigGC-BC-r17 OPTIONAL, \-- Need R

sl-DiscConfigCommon-r17 SL-DiscConfigCommon-r17 OPTIONAL, \-- Need R

sl-L2U2N-Relay-r17 ENUMERATED {enabled} OPTIONAL, \-- Need R

sl-NonRelayDiscovery-r17 ENUMERATED {enabled} OPTIONAL, \-- Need R

sl-L3U2N-RelayDiscovery-r17 ENUMERATED {enabled} OPTIONAL, \-- Need R

sl-TimersAndConstantsRemoteUE-r17 UE-TimersAndConstantsRemoteUE-r17
OPTIONAL \-- Need R

\]\],

\[\[

sl-FreqInfoListSizeExt-v1800 SEQUENCE (SIZE (1..maxNrofFreqSL-1-r18)) OF
SL-FreqConfigCommon-r16 OPTIONAL, \-- Need R

sl-RLC-BearerConfigListSizeExt-v1800 SEQUENCE (SIZE (1..maxSL-LCID-r16))
OF SL-RLC-BearerConfig-r16 OPTIONAL, \-- Need R

sl-SyncFreqList-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-Freq-Id-r16 OPTIONAL, \-- Need R

sl-SyncTxMultiFreq-r18 ENUMERATED {true} OPTIONAL, \-- Need S

sl-MaxTransPowerCA-r18 P-Max OPTIONAL, \-- Need R

sl-DiscConfigCommon-v1800 SL-DiscConfigCommon-v1800 OPTIONAL, \-- Need R

sl-L2-U2U-Relay-r18 ENUMERATED {enabled} OPTIONAL, \-- Need R

sl-L3-U2U-RelayDiscovery-r18 ENUMERATED {enabled} OPTIONAL, \-- Need R

t400-U2U-r18 ENUMERATED {ms200, ms400, ms600, ms800, ms1200, ms2000,
ms3000, ms4000} OPTIONAL \-- Need R

\]\],

\[\[

sl-DiscConfigCommon-v1840 SL-DiscConfigCommon-v1840 OPTIONAL \-- Need R

\]\]

}

\-- Late non-critical Rel-16 extensions:

SIB12-IEs-v16k0 ::= SEQUENCE {

sl-ConfigCommonNR-v16k0 SL-ConfigCommonNR-v16k0 OPTIONAL, \-- Need R

nonCriticalExtension SEQUENCE{} OPTIONAL

}

SL-ConfigCommonNR-r16 ::= SEQUENCE {

sl-FreqInfoList-r16 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-FreqConfigCommon-r16 OPTIONAL, \-- Need R

sl-UE-SelectedConfig-r16 SL-UE-SelectedConfig-r16 OPTIONAL, \-- Need R

sl-NR-AnchorCarrierFreqList-r16 SL-NR-AnchorCarrierFreqList-r16
OPTIONAL, \-- Need R

sl-EUTRA-AnchorCarrierFreqList-r16 SL-EUTRA-AnchorCarrierFreqList-r16
OPTIONAL, \-- Need R

sl-RadioBearerConfigList-r16 SEQUENCE (SIZE (1..maxNrofSLRB-r16)) OF
SL-RadioBearerConfig-r16 OPTIONAL, \-- Need R

sl-RLC-BearerConfigList-r16 SEQUENCE (SIZE (1..maxSL-LCID-r16)) OF
SL-RLC-BearerConfig-r16 OPTIONAL, \-- Need R

sl-MeasConfigCommon-r16 SL-MeasConfigCommon-r16 OPTIONAL, \-- Need R

sl-CSI-Acquisition-r16 ENUMERATED {enabled} OPTIONAL, \-- Need R

sl-OffsetDFN-r16 INTEGER (1..1000) OPTIONAL, \-- Need R

t400-r16 ENUMERATED {ms100, ms200, ms300, ms400, ms600, ms1000, ms1500,
ms2000} OPTIONAL, \-- Need R

sl-MaxNumConsecutiveDTX-r16 ENUMERATED {n1, n2, n3, n4, n6, n8, n16,
n32} OPTIONAL, \-- Need R

sl-SSB-PriorityNR-r16 INTEGER (1..8) OPTIONAL \-- Need R

}

SL-ConfigCommonNR-v16k0 ::= SEQUENCE {

sl-FreqInfoListExt-v16k0 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-FreqConfigCommonExt-v16k0 OPTIONAL \-- Need R

}

SL-NR-AnchorCarrierFreqList-r16 ::= SEQUENCE (SIZE
(1..maxFreqSL-NR-r16)) OF ARFCN-ValueNR

SL-EUTRA-AnchorCarrierFreqList-r16 ::= SEQUENCE (SIZE
(1..maxFreqSL-EUTRA-r16)) OF ARFCN-ValueEUTRA

SL-DiscConfigCommon-r17 ::= SEQUENCE {

sl-RelayUE-ConfigCommon-r17 SL-RelayUE-Config-r17,

sl-RemoteUE-ConfigCommon-r17 SL-RemoteUE-Config-r17

}

SL-DiscConfigCommon-v1800 ::= SEQUENCE {

sl-RelayUE-ConfigCommonU2U-r18 SL-RelayUE-ConfigU2U-r18,

sl-RemoteUE-ConfigCommonU2U-r18 SL-RemoteUE-ConfigU2U-r18

}

SL-DiscConfigCommon-v1840 ::= SEQUENCE {

sl-RelayUE-ConfigCommonU2U-v1840 SL-RelayUE-ConfigU2U-v1840,

sl-RemoteUE-ConfigCommonU2U-v1840 SL-RemoteUE-ConfigU2U-v1830

}

\-- TAG-SIB12-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB12* field descriptions                                            |
+-----------------------------------------------------------------------+
| ***segmentContainer***                                                |
|                                                                       |
| This field includes a segment of the encoded *SIB12-IEs*. The size of |
| the included segment in this container should be small enough that    |
| the SIB message size is less than or equal to the maximum size of a   |
| NR SI, i.e. 2976 bits when SIB12 is broadcast.                        |
+-----------------------------------------------------------------------+
| ***segmentNumber***                                                   |
|                                                                       |
| This field identifies the sequence number of a segment of             |
| *SIB12-IEs*. A segment number of zero corresponds to the first        |
| segment, A segment number of one corresponds to the second segment,   |
| and so on.                                                            |
+-----------------------------------------------------------------------+
| ***segmentType***                                                     |
|                                                                       |
| This field indicates whether the included segment is the last segment |
| or not.                                                               |
+-----------------------------------------------------------------------+
| ***sl-CSI-Acquisition***                                              |
|                                                                       |
| This field indicates whether CSI reporting is enabled in sidelink     |
| unicast. If not set, SL CSI reporting is disabled.                    |
+=======================================================================+
| ***sl-DRX-ConfigCommonGC-BC***                                        |
|                                                                       |
| This field indicates the sidelink DRX configuration for groupcast and |
| broadcast communication, as specified in TS 38.321 \[3\]. This field, |
| if present, also indicates the gNB is capable of sidelink DRX.        |
+-----------------------------------------------------------------------+
| ***sl-EUTRA-AnchorCarrierFreqList***                                  |
|                                                                       |
| This field indicates the EUTRA anchor carrier frequency list, which   |
| can provide the NR sidelink communication configurations.             |
+-----------------------------------------------------------------------+
| ***sl-FreqInfoList, sl-FreqInfoListSizeExt, sl-FreqInfoListExt***     |
|                                                                       |
| This field indicates the NR sidelink communication/discovery          |
| configuration on some carrier frequency (ies). In this release, only  |
| one entry can be configured in *sl-FreqInfoList*. More entries can be |
| configured in *sl-FreqInfoListSizeExt*. If network includes           |
| *sl-FreqInfoListExt*, it includes the same number of entries, and     |
| listed in the same order, as in *sl-FreqInfoList* together with       |
| *sl-FreqInfoListSizeExt*. The first entry corresponds to the          |
| AdditionalSpectrumEmission of the frequency of first entry in         |
| *sl-FreqInfoList* broadcast in *SIB12*, the second entry corresponds  |
| to the AdditionalSpectrumEmission of the frequency of first entry in  |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12*, the third entry        |
| corresponds to the AdditionalSpectrumEmission of the frequency of     |
| second entry in *sl-FreqInfoListSizeExt* broadcast in *SIB12* and so  |
| on.                                                                   |
+-----------------------------------------------------------------------+
| ***sl-L2U2N-Relay***                                                  |
|                                                                       |
| This field indicates the support of NR sidelink Layer-2 U2N relay     |
| operation.                                                            |
+-----------------------------------------------------------------------+
| ***sl-L2-U2U-Relay***                                                 |
|                                                                       |
| This field indicates the support of NR sidelink Layer-2 U2U relay     |
| operation.                                                            |
+-----------------------------------------------------------------------+
| ***sl-L3U2N-RelayDiscovery***                                         |
|                                                                       |
| This field indicates the support of L3 U2N relay AS-layer capability, |
| i.e. NR sidelink L3 U2N relay discovery.                              |
+-----------------------------------------------------------------------+
| ***sl-L3-U2U-RelayDiscovery***                                        |
|                                                                       |
| This field indicates the support of L3 U2U relay AS-layer capability, |
| i.e. NR sidelink L3 U2U relay discovery.                              |
+-----------------------------------------------------------------------+
| ***sl-MaxNumConsecutiveDTX***                                         |
|                                                                       |
| This field indicates the maximum number of consecutive HARQ DTX       |
| before triggering sidelink RLF. Value n1 corresponds to 1, value n2   |
| corresponds to 2, and so on.                                          |
+-----------------------------------------------------------------------+
| ***sl-MaxTransPowerCA***                                              |
|                                                                       |
| The maximum total transmit power to be used by the UE across all      |
| sidelink carriers.                                                    |
+-----------------------------------------------------------------------+
| ***sl-MeasConfigCommon***                                             |
|                                                                       |
| This field indicates the measurement configurations (e.g. RSRP) for   |
| NR sidelink communication.                                            |
+-----------------------------------------------------------------------+
| ***sl-NonRelayDiscovery***                                            |
|                                                                       |
| This field indicates the support of NR sidelink non-relay discovery.  |
+-----------------------------------------------------------------------+
| ***sl-NR-AnchorCarrierFreqList***                                     |
|                                                                       |
| This field indicates the NR anchor carrier frequency list, which can  |
| provide the NR sidelink communication/discovery configurations.       |
+-----------------------------------------------------------------------+
| ***sl-OffsetDFN***                                                    |
|                                                                       |
| Indicates the timing offset for the UE to determine DFN timing when   |
| GNSS is used for timing reference. Value 1 corresponds to 0.001       |
| milliseconds, value 2 corresponds to 0.002 milliseconds, and so on.   |
+-----------------------------------------------------------------------+
| ***sl-RadioBearerConfigList***                                        |
|                                                                       |
| This field indicates one or multiple sidelink radio bearer            |
| configurations.                                                       |
+-----------------------------------------------------------------------+
| ***sl-RLC-BearerConfigList, sl-RLC-BearerConfigListSizeExt***         |
|                                                                       |
| This field indicates one or multiple sidelink RLC bearer              |
| configurations. For L2 U2U operation, *sl-RLC-BearerConfigList* also  |
| indicates the PC5 Relay RLC Channel configurations.                   |
+-----------------------------------------------------------------------+
| ***sl-SSB-PriorityNR***                                               |
|                                                                       |
| This field indicates the priority of NR sidelink SSB transmission and |
| reception.                                                            |
+-----------------------------------------------------------------------+
| ***sl-SyncFreqList***                                                 |
|                                                                       |
| Indicates a list of candidate carrier frequencies that can be used    |
| for the synchronisation of NR sidelink communication. For             |
| *SL-Freq-Id-r16*, the value 1 corresponds to the frequency of first   |
| entry in *sl-FreqInfoList* broadcast in *SIB12*, the value 2          |
| corresponds to the frequency of first entry in                        |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12*, the value 3            |
| corresponds to the frequency of second entry in                       |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12* and so on.              |
+-----------------------------------------------------------------------+
| ***sl-SyncTxMultiFreq***                                              |
|                                                                       |
| Indicates that the UE transmits S-SSB on multiple carrier frequencies |
| for NR sidelink communication. If this field is absent, the UE        |
| transmits S-SSB only on the synchronisation carrier frequency.        |
+-----------------------------------------------------------------------+
| ***t400***                                                            |
|                                                                       |
| Indicates the value for timer T400 as described in clause 7.1. Value  |
| *ms100* corresponds to 100 ms, value *ms200* corresponds to 200 ms    |
| and so on.                                                            |
+-----------------------------------------------------------------------+
| ***t400-U2U***                                                        |
|                                                                       |
| Indicates the value for timer T400 to be applied for end-to-end PC5   |
| connection in sidelink U2U relay operation as described in clause     |
| 7.1. Value *ms200* corresponds to 200 ms, value *ms400* corresponds   |
| to 400 ms and so on.                                                  |
+-----------------------------------------------------------------------+

#### -- *SIB13*

SIB13 contains configurations of V2X sidelink communication defined in
TS 36.331 \[10\].

*SIB13* information element

\-- ASN1START

\-- TAG-SIB13-START

SIB13-r16 ::= SEQUENCE {

sl-V2X-ConfigCommon-r16 OCTET STRING,

dummy OCTET STRING,

tdd-Config-r16 OCTET STRING,

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

\-- TAG-SIB13-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB13* field descriptions                                            |
+-----------------------------------------------------------------------+
| ***dummy***                                                           |
|                                                                       |
| This field is not used in the specification and the UE ignores the    |
| received value.                                                       |
+=======================================================================+
| ***sl-V2X-ConfigCommon***                                             |
|                                                                       |
| This field includes the E-UTRA *SystemInformationBlockType21* message |
| as specified in TS 36.331 \[10\].                                     |
+-----------------------------------------------------------------------+
| ***tdd-Config***                                                      |
|                                                                       |
| This field includes the *tdd-Config* in E-UTRA                        |
| *SystemInformationBlockType1* message as specified in TS 36.331       |
| \[10\].                                                               |
+-----------------------------------------------------------------------+

#### -- *SIB14*

SIB14 contains configurations of V2X sidelink communication defined in
TS 36.331 \[10\], which can be used jointly with that included in
*SIB13*.

*SIB14* information element

\-- ASN1START

\-- TAG-SIB14-START

SIB14-r16 ::= SEQUENCE {

sl-V2X-ConfigCommonExt-r16 OCTET STRING,

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

\-- TAG-SIB14-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB14* field descriptions                                            |
+=======================================================================+
| ***sl-V2X-ConfigCommonExt***                                          |
|                                                                       |
| This field includes the E-UTRA *SystemInformationBlockType26* message |
| as specified in TS 36.331 \[10\].                                     |
+-----------------------------------------------------------------------+

#### -- *SIB15*

*SIB15* contains configurations of disaster roaming information.

*SIB15* information element

\-- ASN1START

\-- TAG-SIB15-START

SIB15-r17 ::= SEQUENCE {

commonPLMNsWithDisasterCondition-r17 SEQUENCE (SIZE (1..maxPLMN)) OF
PLMN-Identity OPTIONAL, \-- Need R

applicableDisasterInfoList-r17 SEQUENCE (SIZE (1..maxPLMN)) OF
ApplicableDisasterInfo-r17 OPTIONAL, \-- Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

ApplicableDisasterInfo-r17 ::= CHOICE {

noDisasterRoaming-r17 NULL,

disasterRelatedIndication-r17 NULL,

commonPLMNs-r17 NULL,

dedicatedPLMNs-r17 SEQUENCE (SIZE (1..maxPLMN)) OF PLMN-Identity

}

\-- TAG-SIB15-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB15* field descriptions                                            |
+=======================================================================+
| ***commonPLMNsWithDisasterCondition***                                |
|                                                                       |
| A list of PLMN(s) for which disaster condition applies and that       |
| disaster inbound roaming is accepted, which can be commonly           |
| applicable to the PLMNs sharing the cell.                             |
+-----------------------------------------------------------------------+
| ***applicableDisasterInfoList***                                      |
|                                                                       |
| A list indicating the applicable disaster roaming information for the |
| networks indicated in *plmn-IdentityInfoList* and                     |
| *npn-IdentityInfoList-r16*. The network indicates in this list one    |
| entry for each entry of *plmn-IdentityInfoList*, followed by one      |
| entry for each entry of *npn-IdentityInfoList-r16*, meaning that this |
| list will have as many entries as the number of entries of the        |
| combination of *plmn-IdentityInfoList* and                            |
| *npn-IdentityInfoList-r16*. The first entry in this list indicates    |
| the disaster roaming information applicable for the network(s) in the |
| first entry of *plmn-IdentityInfoList*/*npn-IdentityInfoList-r16*,    |
| the second entry in this list indicates the disaster roaming          |
| information applicable for the network(s) in the second entry of      |
| *plmn-IdentityInfoList*/*npn-IdentityInfoList-r16*, and so on. Each   |
| entry in this list can either be having the value                     |
| *noDisasterRoaming*, *disasterRelatedIndication*, *commonPLMNs*, or   |
| *dedicatedPLMNs*. If an entry in this list takes the value            |
| *noDisasterRoaming*, disaster inbound roaming is not allowed in this  |
| network(s). If an entry in this list takes the value                  |
| *disasterRelatedIndication*, the meaning of this field for this       |
| network(s) is as specified for \"disaster related indication\" in TS  |
| 23.122 \[74\], clause 4.4.3.1.1. If an entry in this list takes the   |
| value *commonPLMNs*, the PLMN(s) with disaster conditions indicated   |
| in the field *commonPLMNsWithDisasterCondition* apply for this        |
| network(s). If an entry in this list contains the value               |
| *dedicatedPLMNs*, the listed PLMN(s) are the PLMN(s) with disaster    |
| conditions that the network(s) corresponding to this entry accepts    |
| disaster inbound roamers from. For SNPNs, the network indicates the   |
| value *noDisasterRoaming*.                                            |
+-----------------------------------------------------------------------+

#### -- *SIB16*

SIB16 contains configurations of slice-based cell reselection
information.

*SIB16* information element

\-- ASN1START

\-- TAG-SIB16-START

SIB16-r17 ::= SEQUENCE {

freqPriorityListSlicing-r17 FreqPriorityListSlicing-r17 OPTIONAL, \--
Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

\-- TAG-SIB16-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB16* field descriptions                                            |
+=======================================================================+
| ***freqPriorityListSlicing***                                         |
|                                                                       |
| This field indicates cell reselection priorities for slicing.         |
+-----------------------------------------------------------------------+

#### -- *SIB17*

SIB17 contains configurations of TRS resources for idle/inactive UEs.

*SIB17* information element

\-- ASN1START

\-- TAG-SIB17-START

SIB17-r17 ::= SEQUENCE {

segmentNumber-r17 INTEGER (0..63),

segmentType-r17 ENUMERATED {notLastSegment, lastSegment},

segmentContainer-r17 OCTET STRING

}

SIB17-IEs-r17 ::= SEQUENCE {

trs-ResourceSetConfig-r17 SEQUENCE (SIZE
(1..maxNrofTRS-ResourceSets-r17)) OF TRS-ResourceSet-r17,

validityDuration-r17 ENUMERATED {t1, t2, t4, t8, t16, t32, t64, t128,
t256, t512, infinity, spare5, spare4, spare3, spare2,

spare1} OPTIONAL, \-- Need S

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

TRS-ResourceSet-r17 ::= SEQUENCE {

powerControlOffsetSS-r17 ENUMERATED {db-3, db0, db3, db6},

scramblingID-Info-r17 CHOICE {

scramblingIDforCommon-r17 ScramblingId,

scramblingIDperResourceListWith2-r17 SEQUENCE (SIZE (2)) OF
ScramblingId,

scramblingIDperResourceListWith4-r17 SEQUENCE (SIZE (4)) OF
ScramblingId,

\...

},

firstOFDMSymbolInTimeDomain-r17 INTEGER (0..9),

startingRB-r17 INTEGER (0..maxNrofPhysicalResourceBlocks-1),

nrofRBs-r17 INTEGER (24..maxNrofPhysicalResourceBlocksPlus1),

ssb-Index-r17 SSB-Index,

periodicityAndOffset-r17 CHOICE {

slots10 INTEGER (0..9),

slots20 INTEGER (0..19),

slots40 INTEGER (0..39),

slots80 INTEGER (0..79)

},

frequencyDomainAllocation-r17 BIT STRING (SIZE (4)),

indBitID-r17 INTEGER (0..5),

nrofResources-r17 ENUMERATED {n2, n4}

}

\-- TAG-SIB17-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB17* field descriptions                                            |
+-----------------------------------------------------------------------+
| ***segmentContainer***                                                |
|                                                                       |
| This field includes a segment of the encoded *SIB17-IEs*. The size of |
| the included segment in this container should be small enough that    |
| the SIB message size is less than or equal to the maximum size of a   |
| NR SI, i.e. 2976 bits when *SIB17* is broadcast.                      |
+-----------------------------------------------------------------------+
| ***segmentNumber***                                                   |
|                                                                       |
| This field identifies the sequence number of a segment of             |
| *SIB17-IEs*. A segment number of zero corresponds to the first        |
| segment, a segment number of one corresponds to the second segment,   |
| and so on.                                                            |
+-----------------------------------------------------------------------+
| ***segmentType***                                                     |
|                                                                       |
| This field indicates whether the included segment is the last segment |
| or not.                                                               |
+=======================================================================+
| ***trs-ResourceSetConfig***                                           |
|                                                                       |
| RS configuration of TRS occasion(s) for idle/inactive UE(s), in terms |
| of a list of N\>=1 NZP TRS resource set(s). The maximum number of TRS |
| resource sets configured by higher layer is 64. If a TRS resource is  |
| configured, the L1 based availability indication is always enabled    |
| based on that configuration. A UE which acquired *SIB17* with a TRS   |
| configuration but did not yet receive an associated L1-based          |
| availability indication considers the configured TRS as unavailable.  |
| If SIB scheduling indicates that *SIB17* has changed, the UE          |
| considers its configured TRS(s) as unavailable until it receives the  |
| associated L1-based availability indication(s).                       |
+-----------------------------------------------------------------------+
| ***validityDuration***                                                |
|                                                                       |
| The valid time duration for L1 availability indication, time unit is  |
| one default paging cycle. When the field is absent, UE assumes a      |
| default time duration to be 2 default paging cycles. The field is     |
| only valid while the UE has a valid *SIB17*.                          |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *TRS-ResourceSet* field descriptions                                  |
+=======================================================================+
| ***firstOFDMSymbolInTimeDomain***                                     |
|                                                                       |
| The index of the first OFDM symbol in the PRB used for TRS in a slot. |
| The field indicates the first symbol in a slot for the first TRS      |
| resource within the slot, and the symbol for the second TRS resource  |
| in the same slot can be derived implicitly with symbol index as       |
| *firstOFDMSymbolInTimeDomain*+4.                                      |
+-----------------------------------------------------------------------+
| ***frequencyDomainAllocation***                                       |
|                                                                       |
| Indicates the offset of the first RE to RE#0 in a RB in row1 in table |
| 7.4.1.5.3-1 for frequency domain allocation within a physical         |
| resource block (TS 38.211 \[16\], clause 7.4.1.5.3).                  |
+-----------------------------------------------------------------------+
| ***indBitID***                                                        |
|                                                                       |
| The index of the associated bit in TRS availability indication field  |
| in DCI. Each TRS resource set is configured with an ID i for the      |
| association with (i+1)-th indication bit in TRS availability          |
| indication field in DCI.                                              |
+-----------------------------------------------------------------------+
| ***nrofRBs***                                                         |
|                                                                       |
| Number of PRBs across which corresponding TRS resource spans.         |
+-----------------------------------------------------------------------+
| ***nrofResources***                                                   |
|                                                                       |
| The number of TRS resources for a TRS resource set.                   |
+-----------------------------------------------------------------------+
| ***periodicityAndOffset***                                            |
|                                                                       |
| The periodicity and slot offset (slot) for periodic TRS. It is used   |
| to determine the location of the first slot of TRS resource set. The  |
| periodicity value *slots10* corresponds to 10 slots, value *slots20*  |
| corresponds to 20 slots, and so on. Only the following values of the  |
| periodicity are used: 10 slots (SCS 15 kHz), 20 slots (SCS 15 and 30  |
| kHz) and 40 slots (SCS 15, 30 and 60 kHz) and 80 slots (SCS 15, 30,   |
| 60, 120 kHz).                                                         |
+-----------------------------------------------------------------------+
| ***powerControlOffsetSS***                                            |
|                                                                       |
| Power offset (dB) of NZP CSI-RS RE to SSS RE.                         |
+-----------------------------------------------------------------------+
| ***scramblingID-Info***                                               |
|                                                                       |
| One or more scrambling IDs are configured for a TRS resource set. If  |
| a common scrambling ID is configured, it applies to all the TRS       |
| resources within the TRS resource set. Otherwise, each TRS resource   |
| within the TRS resource set is provided with a scrambling ID. If the  |
| number of TRS resources for the TRS resource set is 2,                |
| *scramblingIDperResourceListWith2-r17* is configured, while           |
| *scramblingIDperResourceListWith4-r17* is configured for the case     |
| that the number of TRS resources for the TRS resource set is 4.       |
+-----------------------------------------------------------------------+
| ***ssb-Index***                                                       |
|                                                                       |
| The index of reference SSB with which quasi-collocation information   |
| is provided as specified in TS 38.214 \[19\] clause 5.1.5.            |
+-----------------------------------------------------------------------+
| ***startingRB***                                                      |
|                                                                       |
| The PRB index where corresponding TRS resource starts in relation to  |
| common resource block #0 (CRB#0) on the common resource block grid.   |
+-----------------------------------------------------------------------+

#### -- *SIB17bis*

*SIB17bis* contains configurations of TRS resources for idle/inactive
UEs. *SIB17bis* is optionally scheduled if *SIB17* is not scheduled.

*SIB17bis* information element

\-- ASN1START

\-- TAG-SIB17bis-START

SIB17bis-r18 ::= SEQUENCE {

segmentNumber-r18 INTEGER (0..63),

segmentType-r18 ENUMERATED {notLastSegment, lastSegment},

segmentContainer-r18 OCTET STRING

}

SIB17bis-IEs-r18 ::= SEQUENCE {

trs-ResourceSetConfig-r18 SEQUENCE (SIZE
(1..maxNrofTRS-ResourceSets-r17)) OF TRS-ResourceSet-r18 OPTIONAL, \--
Need R

validityDuration-r18 ENUMERATED {t1, t2, t4, t8, t16, t32, t64, t128,
t256, t512, infinity, spare5, spare4, spare3, spare2,

spare1} OPTIONAL, \-- Need S

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

TRS-ResourceSet-r18 ::= SEQUENCE {

powerControlOffsetSS-r18 ENUMERATED {db-3, db0, db3, db6},

scramblingID-Info-r18 CHOICE {

scramblingIDforCommon-r18 ScramblingId,

scramblingIDperResourceListWith2-r18 SEQUENCE (SIZE (2)) OF
ScramblingId,

scramblingIDperResourceListWith4-r18 SEQUENCE (SIZE (4)) OF
ScramblingId,

\...

},

firstOFDMSymbolInTimeDomain-r18 INTEGER (0..9),

startingRB-r18 INTEGER (0..maxNrofPhysicalResourceBlocks-1),

nrofRBs-r18 INTEGER (24..maxNrofPhysicalResourceBlocksPlus1),

ssb-Index-r18 SSB-Index,

periodicityAndOffset-r18 CHOICE {

slots10 INTEGER (0..9),

slots20 INTEGER (0..19),

slots40 INTEGER (0..39),

slots80 INTEGER (0..79),

slots160 INTEGER (0..159),

slots320 INTEGER (0..319),

slots640 INTEGER (0..639)

},

frequencyDomainAllocation-r18 BIT STRING (SIZE (4)),

indBitID-r18 INTEGER (0..5),

nrofResources-r18 ENUMERATED {n2, n4}

}

\-- TAG-SIB17bis-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB17bis* field descriptions                                         |
+-----------------------------------------------------------------------+
| ***segmentContainer***                                                |
|                                                                       |
| This field includes a segment of the encoded *SIB17bis-IEs*. The size |
| of the included segment in this container should be small enough that |
| the SIB message size is less than or equal to the maximum size of a   |
| NR SI, i.e. 2976 bits when *SIB17bis* is broadcast.                   |
+-----------------------------------------------------------------------+
| ***segmentNumber***                                                   |
|                                                                       |
| This field identifies the sequence number of a segment of             |
| *SIB17bis-IEs*. A segment number of zero corresponds to the first     |
| segment, a segment number of one corresponds to the second segment,   |
| and so on.                                                            |
+-----------------------------------------------------------------------+
| ***segmentType***                                                     |
|                                                                       |
| This field indicates whether the included segment is the last segment |
| or not.                                                               |
+=======================================================================+
| ***trs-ResourceSetConfig***                                           |
|                                                                       |
| RS configuration of TRS occasion(s) for idle/inactive UE(s), in terms |
| of a list of N\>=1 NZP TRS resource set(s). The maximum number of TRS |
| resource sets configured by higher layer is 64. If a TRS resource is  |
| configured, the L1 based availability indication is always enabled    |
| based on that configuration. A UE which acquired *SIB17bis* with a    |
| TRS configuration but did not yet receive an associated L1-based      |
| availability indication considers the configured TRS as unavailable.  |
| If SIB scheduling indicates that *SIB17bis* has changed, the UE       |
| considers its configured TRS(s) from *SIB17bis* as unavailable until  |
| it receives the associated L1-based availability indication(s).       |
+-----------------------------------------------------------------------+
| ***validityDuration***                                                |
|                                                                       |
| The valid time duration for L1 availability indication, time unit is  |
| one default paging cycle. When the field is absent, UE assumes a      |
| default time duration to be 2 default paging cycles. The field is     |
| only valid while the UE has a valid *SIB17bis*.                       |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *TRS-ResourceSet* field descriptions                                  |
+=======================================================================+
| ***firstOFDMSymbolInTimeDomain***                                     |
|                                                                       |
| The index of the first OFDM symbol in the PRB used for TRS in a slot. |
| The field indicates the first symbol in a slot for the first TRS      |
| resource within the slot, and the symbol for the second TRS resource  |
| in the same slot can be derived implicitly with symbol index as       |
| *firstOFDMSymbolInTimeDomain*+4.                                      |
+-----------------------------------------------------------------------+
| ***frequencyDomainAllocation***                                       |
|                                                                       |
| Indicates the offset of the first RE to RE#0 in a RB in row1 in table |
| 7.4.1.5.3-1 for frequency domain allocation within a physical         |
| resource block (TS 38.211 \[16\], clause 7.4.1.5.3).                  |
+-----------------------------------------------------------------------+
| ***indBitID***                                                        |
|                                                                       |
| The index of the associated bit in TRS availability indication field  |
| in DCI. Each TRS resource set is configured with an ID i for the      |
| association with (i+1)-th indication bit in TRS availability          |
| indication field in DCI.                                              |
+-----------------------------------------------------------------------+
| ***nrofRBs***                                                         |
|                                                                       |
| Number of PRBs across which corresponding TRS resource spans.         |
+-----------------------------------------------------------------------+
| ***nrofResources***                                                   |
|                                                                       |
| The number of TRS resources for a TRS resource set.                   |
+-----------------------------------------------------------------------+
| ***periodicityAndOffset***                                            |
|                                                                       |
| The periodicity and slot offset (slot) for periodic TRS. It is used   |
| to determine the location of the first slot of TRS resource set. The  |
| periodicity value *slots10* corresponds to 10 slots, value *slots20*  |
| corresponds to 20 slots, and so on. Only the following values of the  |
| periodicity are used: 10 slots (SCS 15 kHz), 20 slots (SCS 15 and 30  |
| kHz), 40 slots (SCS 15, 30 and 60 kHz), 80 slots (SCS 15, 30, 60 and  |
| 120 kHz), 160 slots (SCS 30, 60 and 120 kHz), 320 slots (SCS 60 and   |
| 120 kHz), and 640 slots (SCS 120 kHz).                                |
+-----------------------------------------------------------------------+
| ***powerControlOffsetSS***                                            |
|                                                                       |
| Power offset (dB) of NZP CSI-RS RE to SSS RE.                         |
+-----------------------------------------------------------------------+
| ***scramblingID-Info***                                               |
|                                                                       |
| One or more scrambling IDs are configured for a TRS resource set. If  |
| a common scrambling ID is configured, it applies to all the TRS       |
| resources within the TRS resource set. Otherwise, each TRS resource   |
| within the TRS resource set is provided with a scrambling ID. If the  |
| number of TRS resources for the TRS resource set is 2,                |
| *scramblingIDperResourceListWith2-r18* is configured, while           |
| *scramblingIDperResourceListWith4-r18* is configured for the case     |
| that the number of TRS resources for the TRS resource set is 4.       |
+-----------------------------------------------------------------------+
| ***ssb-Index***                                                       |
|                                                                       |
| The index of reference SSB with which quasi-collocation information   |
| is provided as specified in TS 38.214 \[19\] clause 5.1.5.            |
+-----------------------------------------------------------------------+
| ***startingRB***                                                      |
|                                                                       |
| The PRB index where corresponding TRS resource starts in relation to  |
| common resource block #0 (CRB#0) on the common resource block grid.   |
+-----------------------------------------------------------------------+

#### -- *SIB18*

*SIB18* contains Group IDs for Network selection (GINs) to support
access using credentials from a Credentials Holder or to support UE
onboarding.

***SIB18* information element**

\-- ASN1START

\-- TAG-SIB18-START

SIB18-r17 ::= SEQUENCE {

gin-ElementList-r17 SEQUENCE (SIZE (1..maxGIN-r17)) OF GIN-Element-r17
OPTIONAL, \-- Need R

gins-PerSNPN-List-r17 SEQUENCE (SIZE (1..maxNPN-r16)) OF
GINs-PerSNPN-r17 OPTIONAL, \-- Need S

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

GIN-Element-r17 ::= SEQUENCE {

plmn-Identity-r17 PLMN-Identity,

nid-List-r17 SEQUENCE (SIZE (1..maxGIN-r17)) OF NID-r16

}

GINs-PerSNPN-r17 ::= SEQUENCE {

supportedGINs-r17 BIT STRING (SIZE (1..maxGIN-r17)) OPTIONAL \-- Need R

}

\-- TAG-SIB18-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB18* field descriptions                                            |
+=======================================================================+
| ***gin-ElementList***                                                 |
|                                                                       |
| The *gin-ElementList* contains one or more GIN elements. Each GIN     |
| element contains either one GIN, which is identified by a PLMN ID and |
| a NID, or multiple GINs that share the same PLMN ID. The total number |
| of GINs indicated does not exceed maxGIN-r17. The GIN index *m* is    |
| defined as d1+d2+...+d(n-1)+i for the GIN included in the *n*-th      |
| entry of the *gin-ElementList* and the *i*-th entry of its            |
| corresponding *GIN-Element*, where *d(k)* is the number of GIN index  |
| values used in the *k*-th *gin-ElementList* entry.                    |
+-----------------------------------------------------------------------+
| ***gins-PerSNPN-List***                                               |
|                                                                       |
| Indicates the supported GINs for each SNPN. The network includes the  |
| same number of entries as the number of SNPNs in                      |
| *snpn-AccessInfoList* in provided in SIB1, and the n-th entry in this |
| list corresponds to the n-th SNPN listed in *snpn-AccessInfoList*     |
| provided in SIB1. The network configures this field only if the cell  |
| broadcasts more than one SNPN in *SIB1*. If this field is absent, as  |
| in case of a single SNPN broadcasted in *SIB1*, the UE shall          |
| associate all GINs in *gin-ElementList* to that SNPN.                 |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *GINs-PerSNPN* field descriptions                                     |
+=======================================================================+
| ***supportedGINs***                                                   |
|                                                                       |
| Indicates the GINs which are supported by the given SNPN. The         |
| first/leftmost bit corresponds to the GIN with GIN index 1, the       |
| second bit corresponds to the GIN with GIN index 2 and so on. A bit   |
| set to 1 indicates that the GIN is supported by the SNPN. If the      |
| field is not present, then the corresponding SNPN does not support    |
| any GINs.                                                             |
+-----------------------------------------------------------------------+

#### *-- SIB19*

*SIB19* contains satellite assistance information for NTN access.

***SIB19* information element**

\-- ASN1START

\-- TAG-SIB19-START

SIB19-r17 ::= SEQUENCE {

ntn-Config-r17 NTN-Config-r17 OPTIONAL, \-- Need R

t-Service-r17 INTEGER (0..549755813887) OPTIONAL, \-- Need R

referenceLocation-r17 ReferenceLocation-r17 OPTIONAL, \-- Need R

distanceThresh-r17 INTEGER(0..65525) OPTIONAL, \-- Need R

ntn-NeighCellConfigList-r17 NTN-NeighCellConfigList-r17 OPTIONAL, \--
Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...,

\[\[

ntn-NeighCellConfigListExt-v1720 NTN-NeighCellConfigList-r17 OPTIONAL
\-- Need R

\]\],

\[\[

movingReferenceLocation-r18 ReferenceLocation-r17 OPTIONAL, \-- Need R

ntn-CovEnh-r18 NTN-CovEnh-r18 OPTIONAL, \-- Need R

satSwitchWithReSync-r18 SatSwitchWithReSync-r18 OPTIONAL \-- Need R

\]\]

}

NTN-NeighCellConfigList-r17 ::= SEQUENCE (SIZE(1..maxCellNTN-r17)) OF
NTN-NeighCellConfig-r17

NTN-NeighCellConfig-r17 ::= SEQUENCE {

ntn-Config-r17 NTN-Config-r17 OPTIONAL, \-- Need R

carrierFreq-r17 ARFCN-ValueNR OPTIONAL, \-- Need R

physCellId-r17 PhysCellId OPTIONAL \-- Need R

}

NTN-CovEnh-r18 ::= SEQUENCE {

numberOfMsg4HARQ-ACK-Repetitions-r18 BIT STRING (SIZE(4)),

rsrp-ThresholdMsg4HARQ-ACK-r18 RSRP-Range OPTIONAL \-- Need R

}

SatSwitchWithReSync-r18 ::= SEQUENCE {

ntn-Config-r18 NTN-Config-r17,

t-ServiceStart-r18 INTEGER (0..549755813887) OPTIONAL, \-- Need R

ssb-TimeOffset-r18 INTEGER (0..159) OPTIONAL \-- Need R

}

\-- TAG-SIB19-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| ***SIB19* field descriptions**                                        |
+-----------------------------------------------------------------------+
| ***distanceThresh***                                                  |
|                                                                       |
| Distance from the serving cell reference location and is used in      |
| location-based measurement initiation in RRC_IDLE and RRC_INACTIVE,   |
| as defined in TS 38.304 \[20\]. Each step represents 50m. This field  |
| is only present in an NTN cell.                                       |
+-----------------------------------------------------------------------+
| ***movingReferenceLocation***                                         |
|                                                                       |
| Reference location of the serving cell of an NTN Earth-moving cell at |
| a time reference. It is used in the evaluation of *eventD2* and       |
| *condEventD2* criteria for the serving cell in RRC_CONNECTED, and     |
| location-based measurement initiation in RRC_IDLE and RRC_INACTIVE    |
| when *distanceThresh* is also configured, as defined in TS 38.304     |
| \[20\]. The time reference of this field is indicated by *epochTime*  |
| in *ntn-Config* of the serving cell. This field is excluded when      |
| determining changes in system information, i.e., changes to           |
| *movingReferenceLocation* should neither result in system information |
| change notifications nor in a modification of *valueTag* in *SIB1*.   |
| This field is only present in an NTN cell.                            |
+=======================================================================+
| ***ntn-Config***                                                      |
|                                                                       |
| Provides parameters needed for the UE to access NR via NTN access     |
| such as Ephemeris data, common TA parameters, k_offset, validity      |
| duration for UL sync information and epoch time. In a TN cell, this   |
| field is only present in *ntn-NeighCellConfigList* and                |
| *ntn-NeighCellConfigListExt*.                                         |
+-----------------------------------------------------------------------+
| ***ntn-NeighCellConfigList, ntn-NeighCellConfigListExt***             |
|                                                                       |
| Provides a list of NTN neighbour cells including their *ntn-Config*,  |
| carrier frequency and *PhysCellId*. This set includes all elements of |
| *ntn-NeighCellConfigList* and all elements of                         |
| *ntn-NeighCellConfigListExt*. If *ntn-Config* is absent for an entry  |
| in *ntn-NeighCellConfigListExt*, the *ntn-Config* provided in the     |
| entry at the same position in *ntn-NeighCellConfigList* applies.      |
| Network provides *ntn-Config* for the first entry of                  |
| *ntn-NeighCellConfigList.* If the *ntn-Config* is absent for any      |
| other entry in *ntn-NeighCellConfigList*, the *ntn-Config* provided   |
| in the previous entry in *ntn-NeighCellConfigList* applies.           |
+-----------------------------------------------------------------------+
| ***referenceLocation***                                               |
|                                                                       |
| Reference location of the serving cell provided via NTN (quasi-)Earth |
| fixed cell and is used in location-based measurement initiation in    |
| RRC_IDLE and RRC_INACTIVE, as defined in TS 38.304 \[20\]. This field |
| is only present in an NTN cell.                                       |
+-----------------------------------------------------------------------+
| ***satSwitchWithReSync***                                             |
|                                                                       |
| Provides parameters for the target satellite required to perform      |
| satellite switch with resynchronization. This field is only present   |
| in an NTN cell and its presence indicates that satellite switch       |
| without PCI change is supported in the cell.                          |
+-----------------------------------------------------------------------+
| ***t-Service***                                                       |
|                                                                       |
| Indicates the time information on when a cell provided via NTN is     |
| going to stop serving the area it is currently covering. This field   |
| applies for both service link switches in NTN quasi-Earth fixed cell  |
| and feeder link switches for both NTN quasi-Earth fixed and           |
| Earth-moving cell. The field indicates a time in multiples of 10 ms   |
| after 00:00:00 on Gregorian calendar date 1 January, 1900 (midnight   |
| between Sunday, December 31, 1899 and Monday, January 1, 1900). The   |
| exact stop time is between the time indicated by the value of this    |
| field minus 1 and the time indicated by the value of this field. The  |
| reference point for *t-Service* is the uplink time synchronization    |
| reference point of the cell. This field is only present in an NTN     |
| cell.                                                                 |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *NTN-CovEnh* field descriptions                                       |
+=======================================================================+
| ***numberOfMsg4HARQ-ACK-Repetitions***                                |
|                                                                       |
| The number of repetition slots for PUCCH transmission with HARQ-ACK   |
| information for Msg4, see clause 9.2.6 in TS 38.213 \[13\]. The       |
| first/leftmost bit corresponds to the repetition factor 1, the second |
| bit corresponds to the repetition factor 2, the third bit corresponds |
| to the repetition factor 4, and the last/rightmost bit corresponds to |
| the repetition factor 8. The repetition factor 1 shall be indicated   |
| together with at least one other repetition factor.                   |
+-----------------------------------------------------------------------+
| ***rsrp-ThresholdMsg4HARQ-ACK***                                      |
|                                                                       |
| This threshold is used by the UE for determining the configuration of |
| the MAC entity for PUCCH repetition for Msg4 HARQ-ACK, as specified   |
| in clause 6.2.1 in TS 38.321 \[3\].                                   |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SatSwitchWithReSync* field descriptions                              |
+-----------------------------------------------------------------------+
| ***ssb-TimeOffset***                                                  |
|                                                                       |
| Indicates the time offset of the SSB from target satellite at its     |
| uplink time synchronization reference point with respect to the SSB   |
| from source satellite at its uplink time synchronization reference    |
| point. The starting boundaries of SFN0 of the source satellite and    |
| the target satellite are aligned at the uplink time synchronization   |
| reference point. The value is given in number of subframes and can    |
| only be configured as 5 subframes or multiples of 5 subframes.        |
+-----------------------------------------------------------------------+
| ***t-ServiceStart***                                                  |
|                                                                       |
| Indicates the time information on when the target satellite is going  |
| to start serving the area currently covered by the serving satellite. |
| The field indicates a time in multiples of 10 ms after 00:00:00 on    |
| Gregorian calendar date 1^st^ January 1900 (midnight between Sunday,  |
| December 31, 1899, and Monday, January 1, 1900). The exact start time |
| is between the time indicated by the value of this field minus 1 and  |
| the time indicated by the value of this field. The reference point    |
| for *t-ServiceStart* is the uplink time synchronization reference     |
| point of the serving satellite.                                       |
+=======================================================================+

#### -- *SIB20*

*SIB20* contains the information required to acquire the MCCH/MTCH
configuration for MBS broadcast.

*SIB20* information element

\-- ASN1START

\-- TAG-SIB20-START

SIB20-r17 ::= SEQUENCE {

mcch-Config-r17 MCCH-Config-r17,

cfr-ConfigMCCH-MTCH-r17 CFR-ConfigMCCH-MTCH-r17 OPTIONAL, \-- Need S

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...,

\[\[

cfr-ConfigMCCH-MTCH-RedCap-r18 CFR-ConfigMCCH-MTCH-r17 OPTIONAL, \--
Need S

mcch-ConfigRedCap-r18 MCCH-Config-r17 OPTIONAL \-- Need S

\]\]

}

MCCH-Config-r17 ::= SEQUENCE {

mcch-RepetitionPeriodAndOffset-r17 MCCH-RepetitionPeriodAndOffset-r17,

mcch-WindowStartSlot-r17 INTEGER (0..79),

mcch-WindowDuration-r17 ENUMERATED {sl2, sl4, sl8, sl10, sl20,
sl40,sl80, sl160} OPTIONAL, \-- Need S

mcch-ModificationPeriod-r17 ENUMERATED {rf2, rf4, rf8, rf16, rf32, rf64,
rf128, rf256,

rf512, rf1024, rf2048, rf4096, rf8192, rf16384, rf32768, rf65536}

}

MCCH-RepetitionPeriodAndOffset-r17 ::= CHOICE {

rf1-r17 INTEGER(0),

rf2-r17 INTEGER(0..1),

rf4-r17 INTEGER(0..3),

rf8-r17 INTEGER(0..7),

rf16-r17 INTEGER(0..15),

rf32-r17 INTEGER(0..31),

rf64-r17 INTEGER(0..63),

rf128-r17 INTEGER(0..127),

rf256-r17 INTEGER(0..255)

}

\-- TAG-SIB20-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB20* field descriptions                                            |
+-----------------------------------------------------------------------+
| ***cfr-ConfigMCCH-MTCH***                                             |
|                                                                       |
| Common frequency resource used for MCCH and MTCH reception. If the    |
| field is absent, the CFR for broadcast has the same location and size |
| as CORESET#0 and PDSCH configuration of MCCH is the same as PDSCH     |
| configuration provided in *initialDownlinkBWP* in *SIB1*.             |
+-----------------------------------------------------------------------+
| ***cfr-ConfigMCCH-MTCH-RedCap***                                      |
|                                                                       |
| Common frequency resource used for MCCH and MTCH reception for        |
| (e)RedCap UEs. If the field is absent, the (e)RedCap UE can use       |
| *cfr-ConfigMCCH-MTCH* if the UE supports the configured bandwidth.    |
+-----------------------------------------------------------------------+
| ***mcch-ConfigRedcap***                                               |
|                                                                       |
| Indicates MBS broadcast MCCH configuration for (e)Redcap UEs. If the  |
| field is absent, the (e)RedCap UE can use *mcch-Config* if the UE     |
| supports the bandwidth configured by *cfr-ConfigMCCH-MTCH*.           |
+=======================================================================+
| ***mcch-ModificationPeriod***                                         |
|                                                                       |
| Defines periodically appearing boundaries, i.e. radio frames for      |
| which SFN mod *mcch-ModificationPeriod* = 0. The contents of          |
| different transmissions of MCCH information can only be different if  |
| there is at least one such boundary in-between them. Value rf2        |
| corresponds to two radio frames, value rf4 corresponds to four radio  |
| frames and so on.                                                     |
+-----------------------------------------------------------------------+
| ***mcch-RepetitionPeriodAndOffset***                                  |
|                                                                       |
| Defines the length and the offset of the MCCH repetition period. rf1  |
| corresponds to a repetition period length of one radio frame, rf2     |
| corresponds to a repetition period length of two radio frames and so  |
| on. The corresponding integer value indicates the offset of the       |
| repetition period in the number of radio frames. MCCH is scheduled in |
| the MCCH transmission window starting from each radio frame for       |
| which: SFN mod repetition period length = offset of the repetition    |
| period.                                                               |
+-----------------------------------------------------------------------+
| ***mcch-WindowDuration***                                             |
|                                                                       |
| Indicates, starting from the slot indicated by                        |
| *mcch-WindowStartSlot*, the duration in slots during which MCCH may   |
| be scheduled. Absence of this field means that MCCH is only scheduled |
| in the slot indicated by *mcch-WindowStartSlot*. The network always   |
| configures *mcch-WindowDuration* to be shorter or equal to the length |
| of MCCH repetition period.                                            |
+-----------------------------------------------------------------------+
| ***mcch-WindowStartSlot***                                            |
|                                                                       |
| Indicates the slot in which MCCH transmission window starts.          |
+-----------------------------------------------------------------------+

#### -- *SIB21*

*SIB21* contains the mapping between the current and/or neighbouring
carrier frequencies and MBS Frequency Selection Area Identities (FSAI).

*SIB21* information element

\-- ASN1START

\-- TAG-SIB21-START

SIB21-r17 ::= SEQUENCE {

mbs-FSAI-IntraFreq-r17 MBS-FSAI-List-r17 OPTIONAL, \-- Need R

mbs-FSAI-InterFreqList-r17 MBS-FSAI-InterFreqList-r17 OPTIONAL, \-- Need
R

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

MBS-FSAI-List-r17 ::= SEQUENCE (SIZE (1..maxFSAI-MBS-r17)) OF
MBS-FSAI-r17

MBS-FSAI-InterFreqList-r17 ::= SEQUENCE (SIZE (1..maxFreq)) OF
MBS-FSAI-InterFreq-r17

MBS-FSAI-InterFreq-r17 ::= SEQUENCE {

dl-CarrierFreq-r17 ARFCN-ValueNR,

mbs-FSAI-List-r17 MBS-FSAI-List-r17

}

MBS-FSAI-r17 ::= OCTET STRING (SIZE (3))

\-- TAG-SIB21-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB21* field descriptions                                            |
+-----------------------------------------------------------------------+
| ***mbs-FSAI-InterFreqList***                                          |
|                                                                       |
| Contains a list of neighboring frequencies including additional       |
| bands, if any, that provide MBS services and the corresponding MBS    |
| FSAIs.                                                                |
+-----------------------------------------------------------------------+
| ***mbs-FSAI-IntraFreq***                                              |
|                                                                       |
| Contains the list of MBS FSAIs for the current frequency. For MBS     |
| service continuity, the UE shall use all MBS FSAIs listed in          |
| *mbs-FSAI-IntraFreq* to derive the MBS frequencies of interest.       |
+=======================================================================+

#### -- *SIB22*

*SIB22* contains ATG assistance information for ATG access.

*SIB22* information element

\-- ASN1START

\-- TAG-SIB22-START

SIB22-r18 ::= SEQUENCE {

atg-Config-r18 ATG-Config-r18 OPTIONAL, \-- Need R

hs-ATG-CellReselectionSet-r18 ENUMERATED {true} OPTIONAL, \-- Need R

atg-NeighCellConfigList-r18 ATG-NeighCellConfigList-r18 OPTIONAL, \--
Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

ATG-NeighCellConfigList-r18 ::= SEQUENCE (SIZE(1..maxCellATG-r18)) OF
ATG-NeighCellConfig-r18

ATG-NeighCellConfig-r18 ::= SEQUENCE {

atg-gNB-Location-r18 ReferenceLocation-r17 OPTIONAL, \-- Need R

height-gNB-r18 INTEGER (-16384..16383) OPTIONAL, \-- Need R

carrierFreq-r18 ARFCN-ValueNR OPTIONAL, \-- Need R

physCellId-r18 PhysCellId OPTIONAL \-- Need R

}

\-- TAG-SIB22-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB22* field descriptions                                            |
+-----------------------------------------------------------------------+
| ***atg-Config***                                                      |
|                                                                       |
| Provides parameters needed for ATG access such as ATG gNB location    |
| information, cell Specific Koffset, TA Report indication.             |
+-----------------------------------------------------------------------+
| ***atg-NeighCellConfigList***                                         |
|                                                                       |
| Provides ATG assistance information of ATG neighbour cells.           |
+-----------------------------------------------------------------------+
| ***hs-ATG-CellReselectionSet***                                       |
|                                                                       |
| Indicates whether the UE applies high speed inter-frequency           |
| measurements requirements for inter-frequency cell reselection in     |
| RRC_IDLE and RRC_INACTIVE states as specified in TS 38.133 \[14\]. If |
| the field is absent UE applies only the NR cell reselection           |
| requirements as specified in TS 38.133 \[14\].                        |
+=======================================================================+

#### -- *SIB23*

*SIB23* contains NR sidelink Positioning configuration for dedicated
SL-PRS resource pool.

*SIB23* information element

\-- ASN1START

\-- TAG-SIB23-START

SIB23-r18 ::= SEQUENCE {

segmentNumber-r18 INTEGER (0..63),

segmentType-r18 ENUMERATED {notLastSegment, lastSegment},

segmentContainer-r18 OCTET STRING

}

SIB23-IEs-r18 ::= SEQUENCE {

sl-PosConfigCommonNR-r18 SL-PosConfigCommonNR-r18,

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

SL-PosConfigCommonNR-r18 ::= SEQUENCE {

sl-PosFreqInfoList-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-FreqConfigCommon-r16 OPTIONAL, \-- Need R

sl-PosUE-SelectedConfig-r18 SL-UE-SelectedConfig-r16 OPTIONAL, \-- Need
R

sl-PosNR-AnchorCarrierFreqList-r18 SL-NR-AnchorCarrierFreqList-r16
OPTIONAL, \-- Need R

sl-PosMeasConfigCommon-r18 SL-MeasConfigCommon-r16 OPTIONAL, \-- Need R

sl-PosOffsetDFN-r18 INTEGER (1..1000) OPTIONAL, \-- Need R

sl-PosSSB-PriorityNR-r18 INTEGER (1..8) OPTIONAL, \-- Need R

\...

}

\-- TAG-SIB23-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB23* field descriptions                                            |
+-----------------------------------------------------------------------+
| ***segmentContainer***                                                |
|                                                                       |
| This field includes a segment of the encoded *SIB23-IEs*. The size of |
| the included segment in this container should be small enough that    |
| the SI message size is less than or equal to the maximum size of a NR |
| SI, i.e. 2976 bits when SIB23 is broadcast.                           |
+-----------------------------------------------------------------------+
| ***segmentNumber***                                                   |
|                                                                       |
| This field identifies the sequence number of a segment of             |
| *SIB23-IEs*. A segment number of zero corresponds to the first        |
| segment, a segment number of one corresponds to the second segment,   |
| and so on.                                                            |
+-----------------------------------------------------------------------+
| ***segmentType***                                                     |
|                                                                       |
| This field indicates whether the included segment is the last segment |
| or not.                                                               |
+=======================================================================+
| ***sl-PosConfigCommonNR***                                            |
|                                                                       |
| This field indicates the NR sidelink positioning configuration.       |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SL-PosConfigCommonNR* field descriptions                             |
+-----------------------------------------------------------------------+
| ***sl-PosFreqInfoList***                                              |
|                                                                       |
| This field indicates the NR sidelink positioning carrier frequencies  |
| for SL-PRS transmission and reception. In this release, only one      |
| entry of *SL-FreqConfigCommon* is included in the list.               |
+=======================================================================+
| ***sl-PosMeasConfigCommon***                                          |
|                                                                       |
| This field indicates the measurement configurations (e.g. RSRP) for   |
| NR sidelink positioning.                                              |
+-----------------------------------------------------------------------+
| ***sl-PosNR-AnchorCarrierFreqList***                                  |
|                                                                       |
| This field indicates the NR anchor carrier frequency list, which can  |
| provide the NR sidelink positioning configurations.                   |
+-----------------------------------------------------------------------+
| ***sl-PosOffsetDFN***                                                 |
|                                                                       |
| Indicates the timing offset for the UE to determine DFN timing when   |
| GNSS is used for timing reference. Value 1 corresponds to 0.001       |
| milliseconds, value 2 corresponds to 0.002 milliseconds, and so on.   |
+-----------------------------------------------------------------------+
| ***sl-PosSSB-PriorityNR***                                            |
|                                                                       |
| This field indicates the priority of NR sidelink SSB transmission and |
| reception.                                                            |
+-----------------------------------------------------------------------+
| ***sl-PosUE-SelectedConfig***                                         |
|                                                                       |
| Indicates the configuration used for UE autonomous resource           |
| selection.                                                            |
+-----------------------------------------------------------------------+

#### -- *SIB24*

*SIB24* contains the information required to acquire the multicast
MCCH/MTCH configuration for MBS multicast reception in RRC_INACTIVE.

*SIB24* information element

\-- ASN1START

\-- TAG-SIB24-START

SIB24-r18 ::= SEQUENCE {

multicastMCCH-Config-r18 MCCH-Config-r17 OPTIONAL, \-- Need S

cfr-ConfigMCCH-MTCH-r18 CFR-ConfigMCCH-MTCH-r17 OPTIONAL, \-- Need S

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

\-- TAG-SIB24-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB24* field descriptions                                            |
+-----------------------------------------------------------------------+
| ***cfr-ConfigMCCH-MTCH***                                             |
|                                                                       |
| Common frequency resource used for multicast MCCH and/or multicast    |
| MTCH reception. If the field is absent, the CFR for multicast has the |
| same location and size as CORESET#0 and PDSCH configuration of        |
| multicast MCCH, if present, is the same as PDSCH configuration        |
| provided in *initialDownlinkBWP* in *SIB1*.                           |
+-----------------------------------------------------------------------+
| ***multicastMCCH-Config***                                            |
|                                                                       |
| Indicates MCCH configuration for MBS multicast reception in           |
| RRC_INACTIVE. This field is always included if it is provided via     |
| broadcast signalling in *SIB24*.                                      |
+=======================================================================+

#### -- *SIB25*

*SIB25* contains TN coverage information to assist neighbour cell
measurements for the UEs in an NTN cell.

*SIB25* information element

\-- ASN1START

\-- TAG-SIB25-START

SIB25-r18 ::= SEQUENCE {

coverageAreaInfoList-r18 CoverageAreaInfoList-r18 OPTIONAL, \-- Need R

lateNonCriticalExtension OCTET STRING OPTIONAL,

\...

}

CoverageAreaInfoList-r18 ::= SEQUENCE (SIZE (1..maxTN-AreaInfo-r18)) OF
CoverageAreaInfo-r18

CoverageAreaInfo-r18 ::= SEQUENCE {

tn-AreaId-r18 TN-AreaId-r18,

tn-ReferenceLocation-r18 ReferenceLocation-r17,

tn-DistanceRadius-r18 INTEGER(0..65535)

}

\-- TAG-SIB25-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SIB25* field descriptions                                            |
+-----------------------------------------------------------------------+
| ***coverageAreaInfoList***                                            |
|                                                                       |
| Contains a list of TN coverage area\'s information to assist skipping |
| TN measurements for NTN UEs in RRC_IDLE and RRC_INACTIVE, as defined  |
| in TS 38.304 \[20\].                                                  |
+-----------------------------------------------------------------------+
| ***tn-DistanceRadius***                                               |
|                                                                       |
| Distance from the TN coverage area reference location. It is used for |
| skipping TN measurements in RRC_IDLE and RRC_INACTIVE, as defined in  |
| TS 38.304 \[20\]. Each step represents 1m.                            |
+=======================================================================+