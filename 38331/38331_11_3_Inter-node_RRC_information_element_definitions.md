## 11.3 Inter-node RRC information element definitions

#### *--* *L1-MeasConfigNRDC*

The IE *L1-MeasConfigNRDC* is used to indicate or request a maximum
value that can be used by the SN in NR-DC to configure L1 measurement
related to LTM at the SCG. Each value is equal to or lower than the
value of the corresponding field in the UE capability, as reported by
the UE, unless specified otherwise. The value indicated by each field is
applicable to all BCs within the field *allowedBC-ListMRDC*.

*L1-MeasConfigNRDC* information element

\-- ASN1START

\-- TAG-L1-MEASCONFIGNRDC-START

L1-MeasConfigNRDC-r18 ::= SEQUENCE {

maxL1-MeasNoGapSCG-r18 INTEGER(0..maxNrofL1-MeasNoGap-r18) OPTIONAL,

maxL1-MeasWithGapSCG-r18 INTEGER(0..maxNrofL1-MeasWithGap-r18) OPTIONAL,

maxCellsL1-MeasNoGapSCG-r18 INTEGER(0..maxNrofCellsL1-MeasNoGap-r18)
OPTIONAL,

maxCellsL1-MeasWithGapSCG-r18 INTEGER(0..maxNrofCellsL1-MeasWithGap-r18)
OPTIONAL,

maxTotalCellsL1-MeasNoGapSCG-r18
INTEGER(0..maxNrofTotalCellsL1-MeasNoGap-r18) OPTIONAL,

maxSSBsL1-MeasNoGapSCG-r18 INTEGER(0..maxNrofSSBsL1-MeasNoGap-r18)
OPTIONAL,

maxSSBsL1-MeasWithGapSCG-r18 INTEGER(0..maxNrofSSBsL1-MeasWithGap-r18)
OPTIONAL,

maxTotalSSBsL1-MeasNoGapSCG-r18
INTEGER(0..maxNrofTotalSSBsL1-MeasNoGap-r18) OPTIONAL,

maxCellsL1-MeasIntraFreqSCG-r18
INTEGER(0..maxNrofSSBsL1-MeasIntraFreq-r18) OPTIONAL,

maxCellsL1-MeasInterFreqSCG-r18
INTEGER(0..maxNrofSSBsL1-MeasInterFreq-r18) OPTIONAL,

maxReportConfigsAperiodic-r18
INTEGER(0..maxNrofReportConfigsAperiodic-r18) OPTIONAL,

maxReportConfigsPeriodic-r18
INTEGER(0..maxNrofReportConfigsPeriodic-r18) OPTIONAL,

maxReportConfigsSemiPersistent-r18
INTEGER(0..maxNrofReportConfigsSemiPersistent-r18) OPTIONAL,

\...,

\[\[

maxSSBsL1-MeasNoGapSCGExt-r18 INTEGER(0..maxNrofSSBsL1-MeasNoGapExt-r18)
OPTIONAL

\]\]

}

\-- TAG-L1-MEASCONFIGNRDC-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *L1-MeasConfigNRDC* field descriptions                                |
+=======================================================================+
| ***maxCellsL1-MeasInterFreqSCG***                                     |
|                                                                       |
| Indicates the maximum number of RRC configured LTM candidate cells    |
| for intra- and inter-frequency L1 measurement.                        |
+-----------------------------------------------------------------------+
| ***maxCellsL1-MeasIntraFreqSCG***                                     |
|                                                                       |
| Indicates the maximum number of RRC configured LTM candidate cells    |
| for intra-frequency L1 measurement.                                   |
+-----------------------------------------------------------------------+
| ***maxCellsL1-MeasNoGapSCG***                                         |
|                                                                       |
| Indicates the maximum number of neighbour cells UE can measure per    |
| frequency layer for intra-frequency or inter-frequency L1             |
| measurements without measurement gaps.                                |
+-----------------------------------------------------------------------+
| ***maxCellsL1-MeasWithGapSCG***                                       |
|                                                                       |
| Indicates the maximum number of neighbour cells UE can measure per    |
| frequency layer for inter-frequency L1 measurements with measurement  |
| gaps.                                                                 |
+-----------------------------------------------------------------------+
| ***maxL1-MeasNoGapSCG***                                              |
|                                                                       |
| Indicates the maximum number of frequency layers UE can measure for   |
| intra- and inter-frequency L1 measurements without measurement gaps.  |
+-----------------------------------------------------------------------+
| ***maxL1-MeasWithGapSCG***                                            |
|                                                                       |
| Indicates the maximum number of frequency layers UE can measure for   |
| inter-frequency L1 measurements with measurement gaps.                |
+-----------------------------------------------------------------------+
| ***maxReportConfigsAperiodic***                                       |
|                                                                       |
| Indicates the maximum number of aperiodic LTM CSI report              |
| configurations.                                                       |
+-----------------------------------------------------------------------+
| ***maxReportConfigsPeriodic***                                        |
|                                                                       |
| Indicates the maximum number of periodic LTM CSI report               |
| configurations.                                                       |
+-----------------------------------------------------------------------+
| ***maxReportConfigsSemiPersistent***                                  |
|                                                                       |
| Indicates the maximum number of semi-persistent LTM CSI report        |
| configurations.                                                       |
+-----------------------------------------------------------------------+
| ***maxSSBsL1-MeasNoGapSCG, maxSSBsL1-MeasNoGapSCGExt***               |
|                                                                       |
| Indicates the maximum number of SSB resources UE can measure per      |
| frequency layer for intra-frequency or inter-frequency L1             |
| measurements without measurement gaps. If the field                   |
| *maxSSBsL1-MeasNoGapSCGExt* is included, the field                    |
| *maxSSBsL1-MeasNoGapSCG* is not present.                              |
+-----------------------------------------------------------------------+
| ***maxSSBsL1-MeasWithGapSCG***                                        |
|                                                                       |
| Indicates the maximum number of SSB resources UE can measure per      |
| frequency layer for inter-frequency L1 measurements with measurement  |
| gaps.                                                                 |
+-----------------------------------------------------------------------+
| ***maxTotalCellsL1-MeasNoGapSCG***                                    |
|                                                                       |
| Indicates the maximum total number of cells, including serving cells  |
| and neighboring cells, across all frequency layers of intra-frequency |
| and inter-frequency L1 measurements, UE can measure without           |
| measurement gaps.                                                     |
+-----------------------------------------------------------------------+
| ***maxTotalSSBsL1-MeasNoGapSCG***                                     |
|                                                                       |
| Indicates the maximum total number of SSB resources, including        |
| serving cells and neighboring cells, across all frequency layers of   |
| intra-frequency and inter-frequency L1 measurements, UE can measure   |
| without measurement gaps.                                             |
+-----------------------------------------------------------------------+

#### *--* *LTM-ResourceConfigNRDC*

The IE *LTM-ResourceConfigNRDC* is used to indicate or request a maximum
value that can be used by the SN in NR-DC to configure LTM related
configuration at the SCG e.g., number of TCI states to be configured and
activated, and number of LTM candidates on which to trigger the early UL
synchronization. Each value is equal to or lower than the value of the
corresponding field in the UE capability, as reported by the UE, unless
specified otherwise. The value indicated by each field is applicable to
all BCs within the field *allowedBC-ListMRDC*.

*LTM-ResourceConfigNRDC* information element

\-- ASN1START

\-- TAG-LTM-RESOURCECONFIGNRDC-START

LTM-ResourceConfigNRDC-r18 ::= SEQUENCE {

maxCellsTA-Meas-r18 INTEGER(0..maxNrofCellsTA-Meas-r18) OPTIONAL,

maxConfigJointTCI-States-r18
INTEGER(0..maxNrofConfigJointTCI-States-r18) OPTIONAL,

maxCellsJointTCI-r18 INTEGER(0..maxNrofCellsTCI-r18) OPTIONAL,

maxConfigDL-TCI-States-r18 INTEGER(0..maxNrofConfigDL-TCI-States-r18)
OPTIONAL,

maxConfigUL-TCI-States-r18 INTEGER(0..maxNrofConfigUL-TCI-States-r18)
OPTIONAL,

maxCellsTCI-r18 INTEGER(0..maxNrofCellsTCI-r18) OPTIONAL,

maxStoredConfigCells-r18 INTEGER(0..maxNrofStoredConfigCells-r18)
OPTIONAL,

maxConfigCells-r18 INTEGER(0..maxNrofConfigCells-r18) OPTIONAL,

maxActivatedJointTCI-States-r18
INTEGER(0..maxNrofActivatedJointTCI-States-r18) OPTIONAL,

maxActivatedDL-TCI-States-r18
INTEGER(0..maxNrofActivatedDL-TCI-States-r18) OPTIONAL,

maxActivatedUL-TCI-States-r18
INTEGER(0..maxNrofActivatedUL-TCI-States-r18) OPTIONAL,

\...

}

\-- TAG-LTM-RSOURCECONFIGNRDC-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *LTM-ResourceConfigNRDC* field descriptions                           |
+=======================================================================+
| ***maxActivatedDL-TCI-States***                                       |
|                                                                       |
| Indicates the maximum number of MAC CE activated LTM DL TCI states.   |
+-----------------------------------------------------------------------+
| ***maxActivatedJointTCI-States***                                     |
|                                                                       |
| Indicates the maximum number of MAC CE activated joint LTM TCI        |
| states.                                                               |
+-----------------------------------------------------------------------+
| ***maxActivatedUL-TCI-States***                                       |
|                                                                       |
| Indicates the maximum number of MAC CE activated LTM UL TCI states.   |
+-----------------------------------------------------------------------+
| ***maxCellsJointTCI***                                                |
|                                                                       |
| Indicates the maximum number of configured cells for joint LTM TCI    |
| state(s).                                                             |
+-----------------------------------------------------------------------+
| ***maxCellsTA-Meas***                                                 |
|                                                                       |
| Indicates the maximum number of candidate cells for TA acquisition    |
| based on PDCCH ordered CFRA procedure before receiving cell switch    |
| command MAC-CE.                                                       |
+-----------------------------------------------------------------------+
| ***maxCellsTCI***                                                     |
|                                                                       |
| Indicates the maximum number of configured cells for separate DL/UL   |
| LTM TCI state(s).                                                     |
+-----------------------------------------------------------------------+
| ***maxConfigCells***                                                  |
|                                                                       |
| Indicates the maximum number of LTM candidate configuration(s) for    |
| which the UE can perform early ASN.1 decoding and validity check.     |
+-----------------------------------------------------------------------+
| ***maxConfigDL-TCI-States***                                          |
|                                                                       |
| Indicates the maximum number of configured separate DL LTM TCI        |
| state(s).                                                             |
+-----------------------------------------------------------------------+
| ***maxConfigJointTCI-States***                                        |
|                                                                       |
| Indicates the maximum number of configured joint LTM TCI state(s).    |
+-----------------------------------------------------------------------+
| ***maxConfigUL-TCI-States***                                          |
|                                                                       |
| Indicates the maximum number of configured separate UL LTM TCI        |
| state(s).                                                             |
+-----------------------------------------------------------------------+
| ***maxStoredConfigCells***                                            |
|                                                                       |
| Indicates the maximum number of serving cell(s) and candidate         |
| cell(s), including serving SpCell(s), serving SCell(s) in SCG, SpCell |
| in LTM candidate configurations and SCell(s) in LTM candidate         |
| configurations for SCG.                                               |
+-----------------------------------------------------------------------+

#### -- *ResourceConfigNRDC*

The IE is used to indicate or request the maximum values that can be
used by the SCG in NR-DC, with each value equal to or lower than the
value of the corresponding field in the UE capability, as reported by
the UE, unless specified otherwise.

*ResourceConfigNRDC* information element

\-- ASN1START

\-- TAG-RESOURCECONFIGNRDC-START

ResourceConfigNRDC-r17 ::= SEQUENCE {

fr1-ResourceConfig-r17 ResourceConfigPerFR-r17 OPTIONAL,

fr2-ResourceConfig-r17 ResourceConfigPerFR-r17 OPTIONAL,

maxNumberResAcrossCC-AcrossFR-r17 INTEGER (0..256) OPTIONAL,

\...

}

ResourceConfigPerFR-r17 ::= SEQUENCE {

bm-MaxNumberCSI-RS-Resource-r17 INTEGER (0..64) OPTIONAL,

bm-MaxNumberAperiodicCSI-RS-Resource-r17 INTEGER (0..64) OPTIONAL,

cg-MaxNumberConfigsAllCC-r17 INTEGER (0..32) OPTIONAL,

maxNumberCSI-RS-BFD-r17 INTEGER (0..64) OPTIONAL,

maxNumberCSI-RS-SSB-CBD-r17 INTEGER (0..256) OPTIONAL,

maxNumberSSB-BFD-r17 INTEGER (0..64) OPTIONAL,

sps-MaxNumberConfigsAllCC-r17 INTEGER (0..32) OPTIONAL,

trs-MaxConfResourceSetsAllCC-r17 INTEGER (0..256) OPTIONAL,

\...

}

\-- TAG-RESOURCECONFIGNRDC-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *ResourceConfigNRDC* field descriptions                               |
+=======================================================================+
| ***fr1-ResourceConfig, fr2-ResourceConfig***                          |
|                                                                       |
| Indicates the maximum number of resources that SCG is allowed to      |
| configure for FR1/FR2, respectively.                                  |
+-----------------------------------------------------------------------+
| ***maxNumberResAcrossCC-AcrossFR***                                   |
|                                                                       |
| Indicates the maximum number of configured CSI-RS resources.          |
| Corresponds to the UE capability *maxNumberResAcrossCC-AcrossFR-r16*  |
| in *maxTotalResourcesForAcrossFreqRanges-r16*.                        |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *ResourceConfigPerFR* field descriptions                              |
+=======================================================================+
| ***bm-MaxNumberAperiodicCSI-RS-Resource***                            |
|                                                                       |
| Indicates the maximum number of aperiodic CSI-RS resources that the   |
| SCG is allowed to configure for the UE to measure L1-RSRP.            |
| Corresponds to the UE capability *maxNumberAperiodicCSI-RS-Resource*  |
| in *beamManagementSSB-CSI-RS*.                                        |
+-----------------------------------------------------------------------+
| ***bm-MaxNumberCSI-RS-Resource***                                     |
|                                                                       |
| Indicates the maximum total number of NZP-CSI-RS resources that can   |
| be configured for the UE to measure L1-RSRP. Corresponds to the UE    |
| capability *maxNumberCSI-RS-Resource* in *beamManagementSSB-CSI-RS*.  |
+-----------------------------------------------------------------------+
| ***cg-MaxNumberConfigsAllCC***                                        |
|                                                                       |
| Indicates the maximum number of active configured grant               |
| configurations. Corresponds to the UE capability                      |
| *maxNumberConfigsAllCC-r16* in *activeConfiguredGrant-r16*.           |
+-----------------------------------------------------------------------+
| ***maxNumberCSI-RS-BFD***                                             |
|                                                                       |
| Indicates the maximal number of different CSI-RS resources for the UE |
| to monitor PDCCH quality. Corresponds to the UE capability            |
| *maxNumberCSI-RS-BFD*.                                                |
+-----------------------------------------------------------------------+
| ***maxNumberCSI-RS-SSB-CBD***                                         |
|                                                                       |
| Indicates the maximal number of different CSI-RS (and/or SSB)         |
| resources for new beam identifications. Corresponds to the UE         |
| capability *maxNumberCSI-RS-SSB-CBD*.                                 |
+-----------------------------------------------------------------------+
| ***maxNumberSSB-BFD***                                                |
|                                                                       |
| Indicates the maximal number of different SSBs for the UE to monitor  |
| PDCCH quality. Corresponds to the UE capability *maxNumberSSB-BFD*.   |
+-----------------------------------------------------------------------+
| ***sps-MaxNumberConfigsAllCC***                                       |
|                                                                       |
| Indicates the maximum number of SPS configurations. Corresponds to    |
| the UE capability *maxNumberConfigsAllCC-r16* in *sps-r16*.           |
+-----------------------------------------------------------------------+
| ***trs-MaxConfResourceSetsAllCC***                                    |
|                                                                       |
| Indicates the maximum configured CSI-RS for tracking (i.e. TRS)       |
| resource sets. Corresponds to the UE capability                       |
| *maxConfiguredResourceSetsAllCC* in *csi-RS-ForTracking*.             |
+-----------------------------------------------------------------------+