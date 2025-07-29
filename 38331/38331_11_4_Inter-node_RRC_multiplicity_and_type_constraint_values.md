## 11.4 Inter-node RRC multiplicity and type constraint values

#### -- Multiplicity and type constraints definitions

\-- ASN1START

\-- TAG-NR-MULTIPLICITY-AND-CONSTRAINTS-START

maxMeasFreqsMN INTEGER ::= 32 \-- Maximum number of MN-configured
measurement frequencies

maxMeasFreqsSN INTEGER ::= 32 \-- Maximum number of SN-configured
measurement frequencies

maxMeasIdentitiesMN INTEGER ::= 62 \-- Maximum number of measurement
identities that a UE can be configured with

maxCellPrep INTEGER ::= 32 \-- Maximum number of cells prepared for
handover

maxNrofL1-MeasNoGap-r18 INTEGER ::= 8 \-- Maximum number of frequencies
layers for L1 measurements UE can measure without gaps

maxNrofL1-MeasWithGap-r18 INTEGER ::= 8 \-- Maximum number of
frequencies layers for L1 measurements UE can measure with gaps

maxNrofCellsL1-MeasNoGap-r18 INTEGER ::= 8 \-- Maximum number of
neighboring cells for L1 measurements UE can measure without gaps

maxNrofCellsL1-MeasWithGap-r18 INTEGER ::= 8 \-- Maximum number of
neighboring cells for L1 measurements UE can measure with gaps

maxNrofTotalCellsL1-MeasNoGap-r18 INTEGER ::= 24 \-- Maximum total
number of cell across all frequencies layers UE can measure

maxNrofSSBsL1-MeasNoGap-r18 INTEGER ::= 8 \-- Maximum number of SSB
resources for L1 measurements without gaps

maxNrofSSBsL1-MeasNoGapExt-r18 INTEGER ::= 24 \-- Maximum number of SSB
resources for L1 measurements without gaps

maxNrofSSBsL1-MeasWithGap-r18 INTEGER ::= 8 \-- Maximum number of SSB
resources for L1 measurements with gaps

maxNrofTotalSSBsL1-MeasNoGap-r18 INTEGER ::= 64 \-- Maximum total number
of SSB resources for L1 measurements without gaps

maxNrofSSBsL1-MeasIntraFreq-r18 INTEGER ::= 8 \-- Maximum number of RRC
configured intra-frequency LTM candidate configurations

maxNrofSSBsL1-MeasInterFreq-r18 INTEGER ::= 8 \-- Maximum number of RRC
configured inter-frequency LTM candidate configurations

maxNrofReportConfigsAperiodic-r18 INTEGER ::= 4 \-- Maximum number of
aperiodic LTM CSI report configurations

maxNrofReportConfigsPeriodic-r18 INTEGER ::= 4 \-- Maximum number of
periodic LTM CSI report configurations

maxNrofReportConfigsSemiPersistent-r18 INTEGER ::= 4 \-- Maximum number
of semi-persistent LTM CSI report configurations

maxNrofCellsTA-Meas-r18 INTEGER ::= 8 \-- Maximum number of LTM
candidate cells for TA acquisition

maxNrofConfigJointTCI-States-r18 INTEGER ::= 128 \-- Maximum number of
joint LTM DL TCI states that can be configured

maxNrofConfigDL-TCI-States-r18 INTEGER ::= 128 \-- Maximum number of
separate LTM DL TCI states that can be configured

maxNrofConfigUL-TCI-States-r18 INTEGER ::= 64 \-- Maximum number of
separate LTM UL TCI states that can be configured

maxNrofCellsTCI-r18 INTEGER ::= 8 \-- Maximum number of configured joint
LTM TCI state(s) across candidate cells

maxNrofStoredConfigCells-r18 INTEGER ::= 16 \-- Maximum number cells
which can be stored by the UE

maxNrofConfigCells-r18 INTEGER ::= 4 \-- Maximum number LTM candidate
configurations on which UE can fast processing

maxNrofActivatedJointTCI-States-r18 INTEGER ::= 32 \-- Maximum number of
joint DL TCI states that can be activated via MAC CE

maxNrofActivatedDL-TCI-States-r18 INTEGER ::= 32 \-- Maximum number of
separate DL TCI states that can be activated via MAC CE

maxNrofActivatedUL-TCI-States-r18 INTEGER ::= 32 \-- Maximum number of
separate DL TCI states that can be activated via MAC CE

\-- TAG-NR-MULTIPLICITY-AND-CONSTRAINTS-STOP

\-- ASN1STOP

#### -- *End of NR-InterNodeDefinitions*

\-- ASN1START

\-- TAG-NR-INTER-NODE-DEFINITIONS-END-START

END

\-- TAG-NR-INTER-NODE-DEFINITIONS-END-STOP

\-- ASN1STOP