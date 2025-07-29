### 4.2.9a *MeasAndMobParametersMRDC*

+---------------------------------------------------------+-----+----+---------+---------+
| Definitions for parameters                              | Per | M  | FDD-TDD | FR1-FR2 |
|                                                         |     |    | DIFF    | DIFF    |
+=========================================================+=====+====+=========+=========+
| ***condHandoverWithCandSCG-Addition-r18***              | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports conditional handover  |     |    |         |         |
| with candidate NR PSCell addition.                      |     |    |         |         |
|                                                         |     |    |         |         |
| The UE indicating support of this feature shall also    |     |    |         |         |
| indicate the support of *condHandover-r16* and support  |     |    |         |         |
| of at least one NR-DC band combination.                 |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***condHandoverWithCandSCG-FDD-TDD-Change-r18***        | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports conditional handover  |     |    |         |         |
| with candidate SCG, where conditional NR PSCell change  |     |    |         |         |
| is supported between FDD and TDD. The parameter can     |     |    |         |         |
| only be set if *condHandoverWithCandSCG-change-r18* is  |     |    |         |         |
| set for both FDD and TDD.                               |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***condHandoverWithCandSCG-FR1-FR2-Change-r18***        | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports conditional handover  |     |    |         |         |
| with candidate SCG, where conditional NR PSCell change  |     |    |         |         |
| is supported between FR1 and FR2. The parameter can     |     |    |         |         |
| only be set if *condHandoverWithCandSCG-change-r18* is  |     |    |         |         |
| set for both FR1 and FR2.                               |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***condHandoverWithSCG-ENDC-r17***                      | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports conditional handover  |     |    |         |         |
| with NR SCG configuration for EN-DC. The UE indicating  |     |    |         |         |
| support of this feature shall also indicate the support |     |    |         |         |
| of *cho-r16* as specified in TS 36.306 \[15\] and at    |     |    |         |         |
| least one EN-DC band combination.                       |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***condHandoverWithSCG-NEDC-r17***                      | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports conditional handover  |     |    |         |         |
| with E-UTRA SCG configuration for NE-DC. The UE         |     |    |         |         |
| indicating support of this feature shall also indicate  |     |    |         |         |
| the support of *condHandover-r16* and at least one      |     |    |         |         |
| NE-DC band combination.                                 |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***condPSCellChangeFDD-TDD-r16***                       | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports conditional PSCell    |     |    |         |         |
| change between FDD and TDD cells. The parameter can     |     |    |         |         |
| only be set if *condPSCellChange-r16* is set for both   |     |    |         |         |
| FDD and TDD.                                            |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***condPSCellChangeFR1-FR2-r16***                       | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports conditional PSCell    |     |    |         |         |
| change between FR1 and FR2. The parameter can only be   |     |    |         |         |
| set if *condPSCellChange-r16* is set for both FR1 and   |     |    |         |         |
| FR2.                                                    |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***independentGapConfig-maxCC-r17***                    | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| This field indicates whether the UE supports two        |     |    |         |         |
| independent measurement gap configurations for FR1 and  |     |    |         |         |
| FR2 as specified in clause 9.1.2 of TS 38.133 \[5\]     |     |    |         |         |
| while the number of configured serving cells is less    |     |    |         |         |
| than or equal to the indicated number.                  |     |    |         |         |
|                                                         |     |    |         |         |
| The capability signalling includes the following        |     |    |         |         |
| parameters:                                             |     |    |         |         |
|                                                         |     |    |         |         |
| > \- *fr1-Only-r17* indicates the maximum number of     |     |    |         |         |
| > configured serving cells when E-UTRA and NR FR1       |     |    |         |         |
| > serving cells are configured                          |     |    |         |         |
| >                                                       |     |    |         |         |
| > \- *fr2-Only-r17* is not applicable when the field    |     |    |         |         |
| > *independentGapConfig-maxCC-r17* is included in       |     |    |         |         |
| > *UE-MRDC-Capability*.                                 |     |    |         |         |
| >                                                       |     |    |         |         |
| > \- *fr1-AndFR2-r17* indicates the maximum number of   |     |    |         |         |
| > configured serving cells when E-UTRA and NR FR2       |     |    |         |         |
| > serving cells are configured or when E-UTRA, NR FR1   |     |    |         |         |
| > and NR FR2 serving cells are configured.              |     |    |         |         |
|                                                         |     |    |         |         |
| The absence of the *fr1-Only-r17* field indicates that  |     |    |         |         |
| per-FR gap is not supported when E-UTRA and NR FR1      |     |    |         |         |
| serving cells are configured. Absence of the            |     |    |         |         |
| *fr1-AndFR2* field indicates that per-FR-gap is not     |     |    |         |         |
| supported when E-UTRA and NR FR2 serving cells are      |     |    |         |         |
| configured or when E-UTRA, NR FR1 and NR FR2 serving    |     |    |         |         |
| cells are configured. Value \"1\" or \"2\" for          |     |    |         |         |
| *fr1-Only-r17* or *fr1-AndFR2-r17* indicates the        |     |    |         |         |
| support of per-FR gap when PCell and \"1\" additional   |     |    |         |         |
| CC are configured.                                      |     |    |         |         |
|                                                         |     |    |         |         |
| UE indicating support of this feature in                |     |    |         |         |
| *UE-MRDC-Capability* shall not indicate support of      |     |    |         |         |
| *independentGapConfig* in *UE-MRDC-Capability*.         |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***inter-SN-condPSCellChangeFDD-TDD-ENDC-r17***         | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports inter SN conditional  |     |    |         |         |
| PSCell change between FDD and TDD cells in EN-DC.       |     |    |         |         |
|                                                         |     |    |         |         |
| The parameter can only be set                           |     |    |         |         |
|                                                         |     |    |         |         |
| \- if *mn-InitiatedCondPSCellChange-FR1FDD-ENDC-r17* is |     |    |         |         |
| supported and at least one of                           |     |    |         |         |
| *mn-InitiatedCondPSCellChange-FR1TDD-ENDC-r17* and      |     |    |         |         |
| *mn-InitiatedCondPSCellChange-FR2TDD-ENDC-r17* is       |     |    |         |         |
| supported; or                                           |     |    |         |         |
|                                                         |     |    |         |         |
| \- if *sn-InitiatedCondPSCellChange-FR1FDD-ENDC-r17* is |     |    |         |         |
| supported and at least one of                           |     |    |         |         |
| *sn-InitiatedCondPSCellChange-FR1TDD-ENDC-r17* and      |     |    |         |         |
| *sn-InitiatedCondPSCellChange-FR2TDD-ENDC-r17* is       |     |    |         |         |
| supported.                                              |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***inter-SN-condPSCellChangeFDD-TDD-NRDC-r17***         | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports inter SN conditional  |     |    |         |         |
| PSCell change between FDD and TDD cells in NR-DC. The   |     |    |         |         |
| parameter can only be set if                            |     |    |         |         |
| *mn-InitiatedCondPSCellChangeNRDC-r17* is set for FDD   |     |    |         |         |
| band(s) and TDD band(s), or                             |     |    |         |         |
| *sn-InitiatedCondPSCellChangeNRDC-r17* is set for FDD   |     |    |         |         |
| band(s) and TDD band(s).                                |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***inter-SN-condPSCellChangeFR1-FR2-ENDC-r17***         | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports inter SN conditional  |     |    |         |         |
| PSCell change between FR1 and FR2 cells in EN-DC.       |     |    |         |         |
|                                                         |     |    |         |         |
| The parameter can only be set:                          |     |    |         |         |
|                                                         |     |    |         |         |
| \- if *mn-InitiatedCondPSCellChange-FR2TDD-ENDC-r17* is |     |    |         |         |
| supported and at least one of                           |     |    |         |         |
| *mn-InitiatedCondPSCellChange-FR1TDD-ENDC-r17* and      |     |    |         |         |
| *mn-InitiatedCondPSCellChange-FR1FDD-ENDC-r17* is       |     |    |         |         |
| supported; or                                           |     |    |         |         |
|                                                         |     |    |         |         |
| \- if *sn-InitiatedCondPSCellChange-FR2TDD-ENDC-r17* is |     |    |         |         |
| supported and at least one of                           |     |    |         |         |
| *sn-InitiatedCondPSCellChange-FR1TDD-ENDC-r17* and      |     |    |         |         |
| *sn-InitiatedCondPSCellChange-FR1FDD-ENDC-r17* is       |     |    |         |         |
| supported.                                              |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***inter-SN-condPSCellChangeFR1-FR2-NRDC-r17***         | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports inter SN conditional  |     |    |         |         |
| PSCell change between FR1 and FR2 cells. The parameter  |     |    |         |         |
| can only be set if                                      |     |    |         |         |
| *mn-InitiatedCondPSCellChangeNRDC-r17* is set for FR1   |     |    |         |         |
| band(s) and FR2 band(s), or                             |     |    |         |         |
| *sn-InitiatedCondPSCellChangeNRDC-r17* is set for FR1   |     |    |         |         |
| band(s) and FR2 band(s).                                |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***mn-ConfiguredMN-TriggerSCPAC-r18***                  | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports Subsequent CPAC as    |     |    |         |         |
| defined in TS 38.331 \[9\] for MN initiated subsequent  |     |    |         |         |
| conditional PSCell change or addition in NR-DC, which   |     |    |         |         |
| is configured by NR *conditionalReconfiguration* using  |     |    |         |         |
| MN configured measurement as the initial triggering     |     |    |         |         |
| condition and using candidate SN configured measurement |     |    |         |         |
| as the following triggering condition.                  |     |    |         |         |
|                                                         |     |    |         |         |
| The parameter can only be set if                        |     |    |         |         |
| *sn-InitiatedCondPSCellChangeNRDC-r17,*                 |     |    |         |         |
| *mn-InitiatedCondPSCellChangeNRDC-r17* and              |     |    |         |         |
| *condPSCellAdditionNRDC-r17* are supported.             |     |    |         |         |
|                                                         |     |    |         |         |
| A UE indicating support for this feature and for        |     |    |         |         |
| inter-SN-condPSCellChangeFDD-TDD-NRDC-r17, and          |     |    |         |         |
| respectively for                                        |     |    |         |         |
| inter-SN-condPSCellChangeFR1-FR2-NRDC-r17, shall        |     |    |         |         |
| support this feature between FDD and TDD cells, and     |     |    |         |         |
| respectively between FR1 and FR2 cells, in NR-DC.       |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***mn-ConfiguredMN-TriggerSCPAC-afterSCG-release-r18*** | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports Subsequent CPAC as    |     |    |         |         |
| defined in TS 38.331 \[9\] for MN initiated subsequent  |     |    |         |         |
| conditional PSCell change or addition in NR-DC, which   |     |    |         |         |
| is configured by NR *conditionalReconfiguration* using  |     |    |         |         |
| MN configured measurement as the initial triggering     |     |    |         |         |
| condition and using candidate SN configured measurement |     |    |         |         |
| as the following triggering condition, after the SCG    |     |    |         |         |
| from a previous SCPAC configuration is released. UE     |     |    |         |         |
| indicating support for this feature shall indicate      |     |    |         |         |
| support of *mn-ConfiguredMN-TriggerSCPAC-r18*.          |     |    |         |         |
|                                                         |     |    |         |         |
| A UE indicating support for this feature and for        |     |    |         |         |
| *inter-SN-condPSCellChangeFDD-TDD-NRDC-r17*, and        |     |    |         |         |
| respectively for                                        |     |    |         |         |
| *inter-SN-condPSCellChangeFR1-FR2-NRDC-r17*, shall      |     |    |         |         |
| support this feature between FDD and TDD cells, and     |     |    |         |         |
| respectively between FR1 and FR2 cells, in NR-DC.       |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***mn-ConfiguredReferenceConfigSCPAC-r18***             | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports reference             |     |    |         |         |
| configuration for *mn-ConfiguredMN-TriggerSCPAC-r18*    |     |    |         |         |
| and *mn-ConfiguredSN-TriggerSCPAC-r18* as defined in TS |     |    |         |         |
| 38.331 \[9\].                                           |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***mn-ConfiguredSN-TriggerSCPAC-r18***                  | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports Subsequent CPAC as    |     |    |         |         |
| defined in TS 38.331 \[9\] for initial MN configured    |     |    |         |         |
| subsequent conditional PSCell change in NR-DC, which is |     |    |         |         |
| configured by NR *conditionalReconfiguration* using SN  |     |    |         |         |
| configured measurement as the initial triggering        |     |    |         |         |
| condition. The parameter can only be set if             |     |    |         |         |
| *sn-InitiatedCondPSCellChangeNRDC-r17* is supported.    |     |    |         |         |
|                                                         |     |    |         |         |
| A UE indicating support for this feature and for        |     |    |         |         |
| *inter-SN-condPSCellChangeFDD-TDD-NRDC-r17*, and        |     |    |         |         |
| respectively for                                        |     |    |         |         |
| *inter-SN-condPSCellChangeFR1-FR2-NRDC-r17*, shall      |     |    |         |         |
| support this feature between FDD and TDD cells, and     |     |    |         |         |
| respectively between FR1 and FR2 cells, in NR-DC.       |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***mn-InitiatedCondPSCellChange-FR1FDD-ENDC-r17***      | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports MN initiated          |     |    |         |         |
| conditional PSCell change within all supported FR1-FDD  |     |    |         |         |
| bands in EN-DC, which is configured by E-UTRA           |     |    |         |         |
| *conditionalReconfiguration* field using MN configured  |     |    |         |         |
| measurement as triggering condition. The UE supporting  |     |    |         |         |
| this feature shall also support 2 trigger events for    |     |    |         |         |
| same execution condition in MN initiated conditional    |     |    |         |         |
| PSCell change in EN-DC.                                 |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***mn-InitiatedCondPSCellChange-FR1TDD-ENDC-r17***      | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports MN initiated          |     |    |         |         |
| conditional PSCell change within all supported FR1-TDD  |     |    |         |         |
| bands in EN-DC, which is configured by E-UTRA           |     |    |         |         |
| *conditionalReconfiguration* field using MN configured  |     |    |         |         |
| measurement as triggering condition. The UE supporting  |     |    |         |         |
| this feature shall also support 2 trigger events for    |     |    |         |         |
| same execution condition in MN initiated conditional    |     |    |         |         |
| PSCell change in EN-DC.                                 |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***mn-InitiatedCondPSCellChange-FR2TDD-ENDC-r17***      | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports MN initiated          |     |    |         |         |
| conditional PSCell change within all supported FR2-TDD  |     |    |         |         |
| bands in EN-DC, which is configured by E-UTRA           |     |    |         |         |
| *conditionalReconfiguration* field using MN configured  |     |    |         |         |
| measurement as triggering condition. The UE supporting  |     |    |         |         |
| this feature shall also support 2 trigger events for    |     |    |         |         |
| same execution condition in MN initiated conditional    |     |    |         |         |
| PSCell change in EN-DC.                                 |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***pscellT312-r16***                                    | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports T312 based fast       |     |    |         |         |
| failure recovery for PSCell.                            |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***sn-ConfiguredReferenceConfigSCPAC-r18***             | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports reference             |     |    |         |         |
| configuration for *sn-Configured-SCPAC-r18* as defined  |     |    |         |         |
| in TS 38.331 \[9\].                                     |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***sn-ConfiguredSCPAC-r18***                            | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports Subsequent CPAC as    |     |    |         |         |
| defined in TS 38.331 \[9\] for SN configured subsequent |     |    |         |         |
| conditional PSCell change (intra-SN) in NR-DC.          |     |    |         |         |
|                                                         |     |    |         |         |
| The parameter can only be set if *condPSCellChange-r16* |     |    |         |         |
| is supported.                                           |     |    |         |         |
|                                                         |     |    |         |         |
| A UE indicating support for this feature and for        |     |    |         |         |
| *condPSCellChangeFDD-TDD-r16*, and respectively for     |     |    |         |         |
| *condPSCellChangeFR1-FR2-r16*, shall support this       |     |    |         |         |
| feature between FDD and TDD cells, and respectively     |     |    |         |         |
| between FR1 and FR2 cells, in NR-DC.                    |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***sn-InitiatedCondPSCellChange-FR1FDD-ENDC-r17***      | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports SN initiated inter-SN |     |    |         |         |
| conditional PSCell change within all supported FR1-FDD  |     |    |         |         |
| bands in EN-DC, which is configured by E-UTRA           |     |    |         |         |
| *conditionalReconfiguration* field using SN configured  |     |    |         |         |
| measurement as triggering condition. The UE supporting  |     |    |         |         |
| this feature shall also support 2 trigger events for    |     |    |         |         |
| same execution condition in SN initiated inter-SN       |     |    |         |         |
| conditional PSCell change in EN-DC.                     |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***sn-InitiatedCondPSCellChange-FR1TDD-ENDC-r17***      | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports SN initiated inter-SN |     |    |         |         |
| conditional PSCell change within all supported FR1-TDD  |     |    |         |         |
| bands in EN-DC, which is configured by E-UTRA           |     |    |         |         |
| *conditionalReconfiguration* field using SN configured  |     |    |         |         |
| measurement as triggering condition. The UE supporting  |     |    |         |         |
| this feature shall also support 2 trigger events for    |     |    |         |         |
| same execution condition in SN initiated inter-SN       |     |    |         |         |
| conditional PSCell change in EN-DC.                     |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+
| ***sn-InitiatedCondPSCellChange-FR2TDD-ENDC-r17***      | UE  | No | No      | No      |
|                                                         |     |    |         |         |
| Indicates whether the UE supports SN initiated inter-SN |     |    |         |         |
| conditional PSCell change within all supported FR2-TDD  |     |    |         |         |
| bands in EN-DC, which is configured by E-UTRA           |     |    |         |         |
| *conditionalReconfiguration* field using SN configured  |     |    |         |         |
| measurement as triggering condition. The UE supporting  |     |    |         |         |
| this feature shall also support 2 trigger events for    |     |    |         |         |
| same execution condition in SN initiated inter-SN       |     |    |         |         |
| conditional PSCell change in EN-DC.                     |     |    |         |         |
+---------------------------------------------------------+-----+----+---------+---------+