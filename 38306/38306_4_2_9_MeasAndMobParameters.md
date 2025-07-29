### 4.2.9 *MeasAndMobParameters*

+------------------------------------------------------+-----+-----+---------+---------+
| Definitions for parameters                           | Per | M   | FDD-TDD | FR1-FR2 |
|                                                      |     |     | DIFF    | DIFF    |
+======================================================+:===:+:===:+:=======:+:=======:+
| ***bestCellChangeReport-r18***                       | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports the sending of the |     |     |         |         |
| measurement report if the measured first best cell   |     |     |         |         |
| changed as specified in TS 38.331 \[9\].             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***cellIndividualOffsetPerMeasEvent-r18***           | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports the configuration  |     |     |         |         |
| of a cell individual offset per measurement event    |     |     |         |         |
| within *reportConfigNR* or *reportConfigInterRAT* as |     |     |         |         |
| specified in TS 38.331 \[9\].                        |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***cli-RSSI-Meas-r16***                              | UE  | No  | TDD     | Yes     |
|                                                      |     |     | only    |         |
| Indicates whether the UE can perform CLI RSSI        |     |     |         |         |
| measurements as specified in TS 38.215 \[13\] and    |     |     |         |         |
| supports periodical reporting and measurement event  |     |     |         |         |
| triggering as specified in TS 38.331 \[9\]. If the   |     |     |         |         |
| UE supports this feature, the UE needs to report     |     |     |         |         |
| *maxNumberCLI-RSSI-r16*. If this parameter is        |     |     |         |         |
| indicated for FR1 and FR2 differently, each          |     |     |         |         |
| indication corresponds to the frequency range of     |     |     |         |         |
| measurement resources to be measured.                |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***cli-SRS-RSRP-Meas-r16***                          | UE  | No  | TDD     | Yes     |
|                                                      |     |     | only    |         |
| Indicates whether the UE can perform SRS RSRP        |     |     |         |         |
| measurements as specified in TS 38.215 \[13\] and    |     |     |         |         |
| supports periodical reporting and measurement event  |     |     |         |         |
| triggering based on SRS-RSRP as specified in TS      |     |     |         |         |
| 38.331 \[9\]. If the UE supports this feature, the   |     |     |         |         |
| UE needs to report *maxNumberCLI-SRS-RSRP-r16* and   |     |     |         |         |
| *maxNumberPerSlotCLI-SRS-RSRP-r16*. If this          |     |     |         |         |
| parameter is indicated for FR1 and FR2 differently,  |     |     |         |         |
| each indication corresponds to the frequency range   |     |     |         |         |
| of measurement resources to be measured.             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***concurrentMeasCRS-InsideBWP-EUTRA-r18***          | UE  | No  | No      | FR1     |
|                                                      |     |     |         | only    |
| Indicates whether the UE supports concurrent         |     |     |         |         |
| inter-RAT measurement on EUTRAN cell in non-DSS and  |     |     |         |         |
| PDCCH or PDSCH reception from the serving cell with  |     |     |         |         |
| a different numerology.                              |     |     |         |         |
|                                                      |     |     |         |         |
| A UE supporting this feature shall also indicate     |     |     |         |         |
| support of *eutra-NoGapMeasurementInsideBWP-r18* or  |     |     |         |         |
| *eutra-NoGapMeasurementOutsideBWP-r18*.              |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***concurrentMeasGap-r17***                          | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports the concurrent     |     |     |         |         |
| measurements gaps as specified in TS 38.133 \[5\].   |     |     |         |         |
| The capability signalling comprises the following    |     |     |         |         |
| parameters:                                          |     |     |         |         |
|                                                      |     |     |         |         |
| \- *concurrentPerUE-OnlyMeasGap-r17* indicates       |     |     |         |         |
| whether the UE supports more than 1 per-UE           |     |     |         |         |
| measurement gap configurations (i.e. gap combination |     |     |         |         |
| configuration id = 2 as specified in TS 38.133       |     |     |         |         |
| \[5\]), or                                           |     |     |         |         |
|                                                      |     |     |         |         |
| *-* *concurrentPerUE-PerFRCombMeasGap-r17* indicates |     |     |         |         |
| whether the UE supports all concurrent gap           |     |     |         |         |
| combination configurations as specified in TS 38.133 |     |     |         |         |
| \[5\] including support of more than 1 per-UE        |     |     |         |         |
| measurement gap configurations. For UE capable of    |     |     |         |         |
| Rel-15 per-FR gap (*independentGapConfig*), this     |     |     |         |         |
| field indicates whether the UE supports more than 1  |     |     |         |         |
| per-FR gap measurement gap configurations in an FR,  |     |     |         |         |
| or simultaneous 1 per UE measurement gap plus 1      |     |     |         |         |
| per-FR measurement gap configurations in an FR, or   |     |     |         |         |
| more than 1 per-UE measurement gap configurations    |     |     |         |         |
| (i.e. gap combination configuration id = 2 as        |     |     |         |         |
| specified in TS 38.133 \[5\]).                       |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***concurrentMeasGapEUTRA-r17***                     | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE support the configurations  |     |     |         |         |
| of E-UTRAN measurement objectives associated with    |     |     |         |         |
| more than 1 concurrent measurement gaps as specified |     |     |         |         |
| in TS 38.133 \[5\]. The UE indicating support of     |     |     |         |         |
| this feature shall also indicate support of          |     |     |         |         |
| *concurrentMeasGap-r17*.                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***concurrentMeasGapsNCSG-r18***                     | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports multiple per-UE    |     |     |         |         |
| (or per-FR) measurement gap patterns with at least   |     |     |         |         |
| one per-UE (or per-FR) NCSG as specified in TS       |     |     |         |         |
| 38.133 \[5\].                                        |     |     |         |         |
|                                                      |     |     |         |         |
| A UE supporting this feature shall also indicate     |     |     |         |         |
| support of *nr-NeedForGapNCSG-Reporting-r17* and     |     |     |         |         |
| *concurrentMeasGap-r17.*                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***concurrentMeasGapsPreMG-r18***                    | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports multiple per-UE    |     |     |         |         |
| (or per-FR) measurement gap patterns with at least   |     |     |         |         |
| one per-UE (or per-FR) Pre-MG as specified in TS     |     |     |         |         |
| 38.133 \[5\].                                        |     |     |         |         |
|                                                      |     |     |         |         |
| A UE supporting this feature shall also indicate     |     |     |         |         |
| support of *concurrentMeasGap-r17* and one of        |     |     |         |         |
| *preconfiguredNW-ControlledMeasGap-r17* and          |     |     |         |         |
| *preconfiguredUE-AutonomousMeasGap-r17*.             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***condHandoverFDD-TDD-r16***                        | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports conditional        |     |     |         |         |
| handover between FDD and TDD cells. The parameter    |     |     |         |         |
| can only be set if *condHandover-r16* is set for     |     |     |         |         |
| both FDD and TDD. The UE that indicates support of   |     |     |         |         |
| this feature shall also indicate support of          |     |     |         |         |
| *handoverFDD-TDD*.                                   |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***condHandoverFR1-FR2-r16***                        | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports conditional        |     |     |         |         |
| handover HO between FR1 and FR2. The parameter can   |     |     |         |         |
| only be set if *condHandover-r16* is set for both    |     |     |         |         |
| FR1 and FR2. The UE that indicates support of this   |     |     |         |         |
| feature shall also indicate support of               |     |     |         |         |
| *handoverFR1-FR2*.                                   |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***condHandoverWithSCG-NRDC-r17***                   | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports conditional        |     |     |         |         |
| handover with NR SCG configuration for NR-DC. The UE |     |     |         |         |
| indicating support of this feature shall also        |     |     |         |         |
| indicate the support of *condHandover-r16* and       |     |     |         |         |
| support of at least one NR-DC band combination.      |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***csi-RS-RLM***                                     | UE  | Yes | No      | Yes     |
|                                                      |     |     |         |         |
| Indicates whether the UE can perform radio link      |     |     |         |         |
| monitoring procedure based on measurement of CSI-RS  |     |     |         |         |
| as specified in TS 38.213 \[11\] and TS 38.133       |     |     |         |         |
| \[5\]. If the UE supports this feature, the UE needs |     |     |         |         |
| to report *maxNumberResource-CSI-RS-RLM*. This       |     |     |         |         |
| applies only to non-shared spectrum channel access.  |     |     |         |         |
| For shared spectrum channel access, *csi-RS-RLM-r16* |     |     |         |         |
| applies.                                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***csi-RSRP-AndRSRQ-MeasWithSSB***                   | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Indicates whether the UE can perform CSI-RSRP and    |     |     |         |         |
| CSI-RSRQ measurement as specified in TS 38.215       |     |     |         |         |
| \[13\], where CSI-RS resource is configured with an  |     |     |         |         |
| associated SS/PBCH. If this parameter is indicated   |     |     |         |         |
| for FR1 and FR2 differently, each indication         |     |     |         |         |
| corresponds to the frequency range of measured       |     |     |         |         |
| target cell. If the UE supports this feature, the UE |     |     |         |         |
| needs to report *maxNumberCSI-RS-RRM-RS-SINR*. This  |     |     |         |         |
| applies only to non-shared spectrum channel access.  |     |     |         |         |
| For shared spectrum channel access, *csi-RS-RLM-r16* |     |     |         |         |
| applies.                                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***csi-RSRP-AndRSRQ-MeasWithoutSSB***                | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Indicates whether the UE can perform CSI-RSRP and    |     |     |         |         |
| CSI-RSRQ measurement as specified in TS 38.215       |     |     |         |         |
| \[13\], where CSI-RS resource is configured for a    |     |     |         |         |
| cell that transmits SS/PBCH block and without an     |     |     |         |         |
| associated SS/PBCH block. If this parameter is       |     |     |         |         |
| indicated for FR1 and FR2 differently, each          |     |     |         |         |
| indication corresponds to the frequency range of     |     |     |         |         |
| measured target cell. If the UE supports this        |     |     |         |         |
| feature, the UE needs to report                      |     |     |         |         |
| *maxNumberCSI-RS-RRM-RS-SINR*. This applies only to  |     |     |         |         |
| non-shared spectrum channel access. For shared       |     |     |         |         |
| spectrum channel access,                             |     |     |         |         |
| *csi-RSRP-AndRSRQ-MeasWithoutSSB-r16* applies.       |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***csi-SINR-Meas***                                  | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Indicates whether the UE can perform CSI-SINR        |     |     |         |         |
| measurements based on configured CSI-RS resources as |     |     |         |         |
| specified in TS 38.215 \[13\]. If this parameter is  |     |     |         |         |
| indicated for FR1 and FR2 differently, each          |     |     |         |         |
| indication corresponding to the frequency range of   |     |     |         |         |
| measured target cell. If the UE supports this        |     |     |         |         |
| feature, the UE needs to report                      |     |     |         |         |
| *maxNumberCSI-RS-RRM-RS-SINR*. This applies only to  |     |     |         |         |
| non-shared spectrum channel access. For shared       |     |     |         |         |
| spectrum channel access, *csi-SINR-Meas-r16*         |     |     |         |         |
| applies.                                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***deriveSSB-IndexFromCellInterNon-NCSG-r17***       | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports configuration of   |     |     |         |         |
| *deriveSSB-IndexFromCellInter-r17* in                |     |     |         |         |
| *MeasObjectNR*. This field applies to NR SA, MN      |     |     |         |         |
| configured measurements when NR-DC or NE-DC is       |     |     |         |         |
| configured, and SN configured measurements when      |     |     |         |         |
| NR-DC or (NG)EN-DC is configured. UE supporting this |     |     |         |         |
| feature is required to meet the measurement          |     |     |         |         |
| requirements in TS 38.133 \[5\]. This field applies  |     |     |         |         |
| only to non-NCSG capable UEs (i.e. UEs not           |     |     |         |         |
| supporting *ncsg-MeasGapNR-Patterns-r17*).           |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***dynamicCollision-r18***                           | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports RRM requirements   |     |     |         |         |
| for handling dynamic collisions between a Pre-MG and |     |     |         |         |
| another measurement gap or Pre-MG.                   |     |     |         |         |
|                                                      |     |     |         |         |
| A UE supporting this feature shall also indicate     |     |     |         |         |
| support of *concurrentMeasGapsPreMG-r18*.            |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***enterAndLeaveCellReport-r18***                    | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports the report of      |     |     |         |         |
| cell(s) that meet the event leaving condition and    |     |     |         |         |
| the report of cell(s) that meet the event entering   |     |     |         |         |
| condition as defined in TS 38.331 \[9\] clause       |     |     |         |         |
| 5.5.4.2.                                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eutra-AutonomousGaps-r16***                       | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Defines whether the UE supports, upon configuration  |     |     |         |         |
| of *useAutonomousGaps* by the network, acquisition   |     |     |         |         |
| of relevant information from a neighbouring E-UTRA   |     |     |         |         |
| cell by reading the SI of the neighbouring cell      |     |     |         |         |
| using autonomous gap and reporting the acquired      |     |     |         |         |
| information to the network as specified in TS 38.331 |     |     |         |         |
| \[9\] when MR-DC is not configured.                  |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eutra-AutonomousGaps-NEDC-r16***                  | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Defines whether the UE supports, upon configuration  |     |     |         |         |
| of *useAutonomousGaps* by the network, acquisition   |     |     |         |         |
| of relevant information from a neighbouring E-UTRA   |     |     |         |         |
| cell by reading the SI of the neighbouring cell      |     |     |         |         |
| using autonomous gap and reporting the acquired      |     |     |         |         |
| information to the network as specified in TS 38.331 |     |     |         |         |
| \[9\] when NE-DC is configured.                      |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eutra-AutonomousGaps-NRDC-r16***                  | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Defines whether the UE supports, upon configuration  |     |     |         |         |
| of *useAutonomousGaps* by the network, acquisition   |     |     |         |         |
| of relevant information from a neighbouring E-UTRA   |     |     |         |         |
| cell by reading the SI of the neighbouring cell      |     |     |         |         |
| using autonomous gap and reporting the acquired      |     |     |         |         |
| information to the network as specified in TS 38.331 |     |     |         |         |
| \[9\] when NR-DC is configured.                      |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eutra-CGI-Reporting***                            | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Defines whether the UE supports acquisition of       |     |     |         |         |
| relevant CGI-information from a neighbouring E-UTRA  |     |     |         |         |
| cell by reading the SI of the neighbouring cell and  |     |     |         |         |
| reporting the acquired information to the network as |     |     |         |         |
| specified in TS 38.331 \[9\] when the (NG)EN-DC and  |     |     |         |         |
| NE-DC are not configured or, when consistent DRX is  |     |     |         |         |
| configured in NR-DC. The consistent DRX              |     |     |         |         |
| configuration implies that MN and SN have the same   |     |     |         |         |
| DRX cycle and on-duration configured by MN           |     |     |         |         |
| completely contains on-duration configured by SN. It |     |     |         |         |
| is mandated if the UE supports EUTRA. It is optional |     |     |         |         |
| for (e)RedCap UEs.                                   |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eutra-CGI-Reporting-NEDC***                       | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Defines whether the UE supports acquisition of       |     |     |         |         |
| relevant information from a neighbouring E-UTRA cell |     |     |         |         |
| by reading the SI of the neighbouring cell and       |     |     |         |         |
| reporting the acquired information to the network as |     |     |         |         |
| specified in TS 38.331 \[9\] when the NE-DC is       |     |     |         |         |
| configured.                                          |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eutra-CGI-Reporting-NRDC***                       | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Defines whether the UE supports acquisition of       |     |     |         |         |
| relevant information from a neighbouring E-UTRA cell |     |     |         |         |
| by reading the SI of the neighbouring cell and       |     |     |         |         |
| reporting the acquired information to the network as |     |     |         |         |
| specified in TS 38.331 \[9\] when the NR-DC is       |     |     |         |         |
| configured wherein MN and SN have different DRX      |     |     |         |         |
| cycles, or on-duration configured by MN does not     |     |     |         |         |
| contain on-duration configured by SN if the DRX      |     |     |         |         |
| cycles are the same.                                 |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eutra-MeasEMW-r18***                              | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports configuration of   |     |     |         |         |
| effective measurement window for inter-RAT EUTRAN    |     |     |         |         |
| measurements, including offset, duration and         |     |     |         |         |
| periodicity.                                         |     |     |         |         |
|                                                      |     |     |         |         |
| The leftmost bit in the bitmap corresponds to EMW    |     |     |         |         |
| pattern #0 and the right most bit in the bitmap      |     |     |         |         |
| corresponds to EMW pattern #5. The bitmap for EMW    |     |     |         |         |
| patterns are defined in TS 38.133 \[5\].             |     |     |         |         |
|                                                      |     |     |         |         |
| EMW patterns #0 and #1 are mandatory (i.e. the       |     |     |         |         |
| corresponding bits in the bitmap is set to 1) if UE  |     |     |         |         |
| supports EMW feature. Other patterns are optional.   |     |     |         |         |
|                                                      |     |     |         |         |
| A UE supporting this feature shall also indicate     |     |     |         |         |
| support of *eutra-NoGapMeasurementOutsideBWP-r18* or |     |     |         |         |
| *eutra-NoGapMeasurementInsideBWP-r18*.               |     |     |         |         |
|                                                      |     |     |         |         |
| If a UE does not support this feature, a UE is not   |     |     |         |         |
| allowed to cause scheduling restriction defined in   |     |     |         |         |
| TS 38.133 \[5\] for                                  |     |     |         |         |
| *eutra-NoGapMeasurementOutsideBWP-r18* or            |     |     |         |         |
| *eutra-NoGapMeasurementInsideBWP-r18*.               |     |     |         |         |
|                                                      |     |     |         |         |
| NOTE: If UE supports                                 |     |     |         |         |
| *eutra-NoGapMeasurementOutsideBWP-r18* or            |     |     |         |         |
| *eutra-NoGapMeasurementInsideBWP-r18* and UE         |     |     |         |         |
| requires scheduling restriction, UE should support   |     |     |         |         |
| this feature.                                        |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eutra-NeedForGapNCSG-Reporting-r17***             | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports reporting of the   |     |     |         |         |
| NCSG and measurement gap requirement information for |     |     |         |         |
| E-UTRA target bands in the UE response to a network  |     |     |         |         |
| configuration RRC message as specified in TS 38.331  |     |     |         |         |
| \[9\].                                               |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eutra-NoGapMeasurementInsideBWP-r18***            | UE  | No  | No      | FR1     |
|                                                      |     |     |         | only    |
| Indicates whether the UE supports inter-RAT EUTRAN   |     |     |         |         |
| measurements without gap when CRS is completely      |     |     |         |         |
| contained within UE\'s active DL BWP.                |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eutra-NoGapMeasurementOutsideBWP-r18***           | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports inter-RAT EUTRAN   |     |     |         |         |
| measurements outside active DL BWP for nogap-noncsg. |     |     |         |         |
|                                                      |     |     |         |         |
| A UE supporting this feature shall also indicate     |     |     |         |         |
| support of *eutra-NeedForGapNCSG-Reporting-r17*.     |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eventA-MeasAndReport***                           | UE  | Yes | Yes     | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports NR measurements    |     |     |         |         |
| and events A triggered reporting as specified in TS  |     |     |         |         |
| 38.331 \[9\]. This field only applies to SN          |     |     |         |         |
| configured measurement when (NG)EN-DC is configured. |     |     |         |         |
| For NR SA, MN and SN configured measurement when     |     |     |         |         |
| NR-DC is configured, and MN configured measurement   |     |     |         |         |
| when NE-DC is configured, this feature is mandatory  |     |     |         |         |
| supported.                                           |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eventB-MeasAndReport***                           | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports EUTRA measurement  |     |     |         |         |
| and event B triggered reporting as specified in TS   |     |     |         |         |
| 38.331 \[9\]. It is mandated if the UE supports      |     |     |         |         |
| EUTRA.                                               |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eventD1-MeasReportTrigger-r17***                  | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports location-based     |     |     |         |         |
| triggered measurement reporting (i.e., event D1) as  |     |     |         |         |
| specified in TS 38.331 \[9\]. It is mandated if the  |     |     |         |         |
| UE supports *locationBasedCondHandover-r17* in any   |     |     |         |         |
| NTN band. It is mandated if the UE supports          |     |     |         |         |
| *locationBasedCondHandoverATG-r18* in any ATG band.  |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***eventD2-MeasReportTrigger-r18***                  | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports location-based     |     |     |         |         |
| triggered measurement reporting for an NTN           |     |     |         |         |
| Earth-moving cell (i.e., event D2) as specified in   |     |     |         |         |
| TS 38.331 \[9\]. It is mandated if the UE supports   |     |     |         |         |
| *locationBasedCondHandoverEMC-r18* in any NTN band.  |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***gNB-ID-LengthReporting-r17***                     | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports acquisition and    |     |     |         |         |
| reporting of gNB ID length from a neighbouring       |     |     |         |         |
| intra-frequency or inter-frequency NR cell by        |     |     |         |         |
| reading the SI of the neighbouring cell and          |     |     |         |         |
| reporting the acquired gNB ID length to the network  |     |     |         |         |
| as specified in TS 38.331 \[9\] when (NG)EN-DC and   |     |     |         |         |
| NE-DC are not configured or, when consistent DRX is  |     |     |         |         |
| configured in NR-DC. The consistent DRX              |     |     |         |         |
| configuration implies that MN and SN have the same   |     |     |         |         |
| DRX cycle and on-duration configured by MN           |     |     |         |         |
| completely contains on-duration configured by SN. It |     |     |         |         |
| is mandated if UE supports NR CGI reporting          |     |     |         |         |
| (NG)EN-DC and NE-DC are not configured or, when      |     |     |         |         |
| consistent DRX is configured in NR-DC.               |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***gNB-ID-LengthReporting-ENDC-r17***                | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports acquisition and    |     |     |         |         |
| reporting of gNB ID length from a neighbouring       |     |     |         |         |
| intra-frequency or inter-frequency NR cell by        |     |     |         |         |
| reading the SI of the neighbouring cell and          |     |     |         |         |
| reporting the acquired gNB ID length to the network  |     |     |         |         |
| as specified in TS 38.331 \[9\] when the (NG)EN-DC   |     |     |         |         |
| is configured. It is mandated if UE supports NR CGI  |     |     |         |         |
| reporting when (NG)EN-DC is configured.              |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***gNB-ID-LengthReporting-NEDC-r17***                | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports acquisition and    |     |     |         |         |
| reporting of gNB ID length from a neighbouring       |     |     |         |         |
| intra-frequency or inter-frequency NR cell by        |     |     |         |         |
| reading the SI of the neighbouring cell and          |     |     |         |         |
| reporting the acquired gNB ID length to the network  |     |     |         |         |
| as specified in TS 38.331 \[9\] when the NE-DC is    |     |     |         |         |
| configured. It is mandated if UE supports NR CGI     |     |     |         |         |
| reporting when NE-DC is configured.                  |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***gNB-ID-LengthReporting-NRDC-r17***                | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports acquisition and    |     |     |         |         |
| reporting of gNB ID length from a neighbouring       |     |     |         |         |
| intra-frequency or inter-frequency NR cell by        |     |     |         |         |
| reading the SI of the neighbouring cell and          |     |     |         |         |
| reporting the acquired gNB ID length to the network  |     |     |         |         |
| as specified in TS 38.331 \[9\] when the NR-DC is    |     |     |         |         |
| configured wherein MN and SN have different DRX      |     |     |         |         |
| cycles, or on-duration configured by MN does not     |     |     |         |         |
| contain on-duration configured by SN if the DRX      |     |     |         |         |
| cycles are the same. It is mandated if UE supports   |     |     |         |         |
| NR CGI reporting when NR-DC is configured.           |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***gNB-ID-LengthReporting-NPN-r17***                 | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports acquisition of     |     |     |         |         |
| NPN-relevant gNB ID length from a neighbouring       |     |     |         |         |
| intra-frequency or inter-frequency NR NPN cell by    |     |     |         |         |
| reading the SI of the neighbouring cell and          |     |     |         |         |
| reporting the acquired gNB ID length to the network  |     |     |         |         |
| as specified in TS 38.331 \[9\]. It is mandated if   |     |     |         |         |
| UE supports NPN CGI reporting.                       |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***handoverLTE-5GC, handoverLTE-5GC-r17***           | UE  | CY  | Yes     | Yes     |
|                                                      |     |     |         |         |
| Indicates whether the UE supports HO to EUTRA        |     |     |         | (Incl   |
| connected to 5GC. It is mandated if the UE supports  |     |     |         | FR2-2   |
| EUTRA connected to 5GC.                              |     |     |         | DIFF)   |
+------------------------------------------------------+-----+-----+---------+---------+
| ***handoverFDD-TDD***                                | UE  | Yes | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports HO between FDD and |     |     |         |         |
| TDD. It is mandated if the UE supports both FDD and  |     |     |         |         |
| TDD. This field only applies to NR SA/NR-DC/NE-DC    |     |     |         |         |
| (e.g. PCell handover). For PSCell change when        |     |     |         |         |
| (NG)EN-DC/NR-DC is configured, this feature is       |     |     |         |         |
| mandatory supported. UEs supporting this shall       |     |     |         |         |
| indicate support of *handoverInterF* for both FDD    |     |     |         |         |
| and TDD.                                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***handoverFR1-FR2***                                | UE  | Yes | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports HO between FR1 and |     |     |         |         |
| FR2. Support is mandatory for the UE supporting both |     |     |         |         |
| FR1 and FR2. This field only applies to NR           |     |     |         |         |
| SA/NR-DC/NE-DC (e.g. PCell handover). For PSCell     |     |     |         |         |
| change when (NG)EN-DC/NR-DC is configured, this      |     |     |         |         |
| feature is mandatory supported. UEs supporting this  |     |     |         |         |
| shall indicate support of *handoverInterF* for both  |     |     |         |         |
| FR1 and FR2.                                         |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***handoverFR1-FR2-2-r17***                          | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports HO between FR1 and |     |     |         |         |
| FR2-2. This field only applies to NR SA/NR-DC/NE-DC  |     |     |         |         |
| (e.g. PCell handover) and PSCell change when         |     |     |         |         |
| (NG)EN-DC/NR-DC is configured. UEs supporting this   |     |     |         |         |
| shall indicate support of *handoverInterF* for both  |     |     |         |         |
| FR1 and FR2-2.                                       |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***handoverFR2-1-FR2-2-r17***                        | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports HO between FR2-1   |     |     |         |         |
| and FR2-2. This field only applies to NR             |     |     |         |         |
| SA/NR-DC/NE-DC (e.g. PCell handover) and PSCell      |     |     |         |         |
| change when (NG)EN-DC/NR-DC is configured. UEs       |     |     |         |         |
| supporting this shall indicate support of            |     |     |         |         |
| *handoverInterF* for both FR2-1 and FR2-2.           |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***handoverInterF, handoverInterF-r17***             | UE  | Yes | Yes     | Yes     |
|                                                      |     |     |         |         |
| Indicates whether the UE supports inter-frequency    |     |     |         | (Incl   |
| HO. It indicates the support for inter-frequency HO  |     |     |         | FR2-2   |
| from the corresponding duplex mode and from          |     |     |         | DIFF)   |
| frequency range indicated to be supported as         |     |     |         |         |
| described in Annex B. This field only applies to NR  |     |     |         |         |
| SA/NR-DC/NE-DC (e.g. PCell handover). For PSCell     |     |     |         |         |
| change when (NG)EN-DC/NR-DC is configured, this      |     |     |         |         |
| feature is mandatory supported.                      |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***handoverLTE-EPC, handoverLTE-EPC-r17***           | UE  | CY  | Yes     | Yes     |
|                                                      |     |     |         |         |
| Indicates whether the UE supports HO to EUTRA        |     |     |         | (Incl   |
| connected to EPC. It is mandated if the UE supports  |     |     |         | FR2-2   |
| EUTRA connected to EPC.                              |     |     |         | DIFF)   |
+------------------------------------------------------+-----+-----+---------+---------+
| ***idleInactiveNR-MeasReport-r16,                    | UE  | No  | No      | Yes     |
| idleInactiveNR-MeasReport-r17***                     |     |     |         |         |
|                                                      |     |     |         | (Incl   |
| Indicates whether the UE supports configuration of   |     |     |         | FR2-2   |
| NR SSB measurements in RRC_IDLE/RRC_INACTIVE and     |     |     |         | DIFF)   |
| reporting of the corresponding results upon network  |     |     |         |         |
| request as specified in TS 38.331 \[9\]. If this     |     |     |         |         |
| parameter is indicated for FR1 and FR2 differently,  |     |     |         |         |
| each indication corresponds to the frequency range   |     |     |         |         |
| of measured target cell.                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***idleInactiveNR-MeasBeamReport-r16***              | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Indicates whether the UE supports beam level         |     |     |         |         |
| measurements in RRC_IDLE/RRC_INACTIVE and reporting  |     |     |         |         |
| of the corresponding beam measurement results upon   |     |     |         |         |
| network request as specified in TS 38.331 \[9\]. A   |     |     |         |         |
| UE supports this feature shall also support          |     |     |         |         |
| *idleInactiveNR-MeasReport-r16*. If this parameter   |     |     |         |         |
| is indicated for FR1 and FR2 differently, each       |     |     |         |         |
| indication corresponds to the frequency range of     |     |     |         |         |
| measured target cell.                                |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***idleInactiveEUTRA-MeasReport-r16***               | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports configuration of   |     |     |         |         |
| E-UTRA measurements in RRC_IDLE/RRC_INACTIVE and     |     |     |         |         |
| reporting of the corresponding results upon network  |     |     |         |         |
| request as specified in TS 38.331 \[9\].             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***idleInactive-ValidityArea-r16***                  | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports configuration of a |     |     |         |         |
| validity area for NR measurements in                 |     |     |         |         |
| RRC_IDLE/RRC_INACTIVE as specified in TS 38.331      |     |     |         |         |
| \[9\].                                               |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***increasedNumberofCSIRSPerMO-r16***                | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Indicates support of up to 192 CSI-RS resource for   |     |     |         |         |
| L3 mobility configuration per measurement object     |     |     |         |         |
| configured with *associatedSSB*. If this parameter   |     |     |         |         |
| is indicated for FR1 and FR2 differently, each       |     |     |         |         |
| indication corresponds to the frequency range of the |     |     |         |         |
| cells to be measured within *MeasObjectNR*.          |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***independentGapConfig***                           | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| This field indicates whether the UE supports two     |     |     |         |         |
| independent measurement gap configurations for FR1   |     |     |         |         |
| and FR2 specified in clause 9.1.2 of TS 38.133       |     |     |         |         |
| \[5\]. The field also indicates whether the UE       |     |     |         |         |
| supports the FR2 inter-RAT measurement without gaps  |     |     |         |         |
| when (NG)EN-DC is not configured.                    |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***independentGapConfig-maxCC-r17***                 | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| This field indicates whether the UE supports two     |     |     |         |         |
| independent measurement gap configurations for FR1   |     |     |         |         |
| and FR2 as specified in clause 9.1.2 of TS 38.133    |     |     |         |         |
| \[5\] while the number of configured serving cells   |     |     |         |         |
| is less than or equal to the indicated number.       |     |     |         |         |
|                                                      |     |     |         |         |
| The capability signalling includes the following     |     |     |         |         |
| parameters:                                          |     |     |         |         |
|                                                      |     |     |         |         |
| > \- *fr1-Only-r17* indicates the maximum number of  |     |     |         |         |
| > configured serving cells when only NR FR1 serving  |     |     |         |         |
| > cells are configured                               |     |     |         |         |
| >                                                    |     |     |         |         |
| > \- *fr2-Only-r17* indicates the maximum number of  |     |     |         |         |
| > configured serving cells when only NR FR2 serving  |     |     |         |         |
| > cells are configured                               |     |     |         |         |
| >                                                    |     |     |         |         |
| > \- *fr1-AndFR2-r17* indicates the maximum number   |     |     |         |         |
| > of configured serving cells when both NR FR1 and   |     |     |         |         |
| > NR FR2 serving cells are configured                |     |     |         |         |
|                                                      |     |     |         |         |
| The absence of the *fr1-Only-r17* or *fr2-Only-r17*  |     |     |         |         |
| field indicates that per-FR gap is not supported     |     |     |         |         |
| when only FR1 or FR2 serving cells are configured.   |     |     |         |         |
| Absence of the *fr1-AndFR2* field indicates that     |     |     |         |         |
| per-FR-gap is not supported when both FR1 and FR2    |     |     |         |         |
| serving cells are configured. Value \"1\" for        |     |     |         |         |
| *fr1-Only-r17* or *fr2-Only-r17* indicates support   |     |     |         |         |
| of the per-FR gap when only PCell is configured (no  |     |     |         |         |
| additional CC). Value \"2\" for *fr1-Only-r17* or    |     |     |         |         |
| *fr2-Only-r17* indicates support of the per-FR gap   |     |     |         |         |
| when PCell and 1 additional CC are configured, and   |     |     |         |         |
| so on. Value \"1\" or \"2\" for *fr1-AndFR2-r17*     |     |     |         |         |
| indicates the support of per-FR gap when PCell and   |     |     |         |         |
| \"1\" additional CC are configured.                  |     |     |         |         |
|                                                      |     |     |         |         |
| UE indicating support of this feature in             |     |     |         |         |
| *UE-NR-Capability* shall not indicate support of     |     |     |         |         |
| *independentGapConfig* in *UE-NR-Capability*.        |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***independentGapConfigPRS-r17***                    | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports two independent    |     |     |         |         |
| measurement gap configurations for FR1 and FR2 for   |     |     |         |         |
| PRS measurement, as specified in clause 9.1.2 of TS  |     |     |         |         |
| 38.133 \[5\].                                        |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***intraAndInterF-MeasAndReport***                   | UE  | Yes | Yes     | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports NR intra-frequency |     |     |         |         |
| and inter-frequency measurements and at least        |     |     |         |         |
| periodical reporting. This field only applies to SN  |     |     |         |         |
| configured measurement when (NG)EN-DC is configured. |     |     |         |         |
| For NR SA, MN and SN configured measurement when     |     |     |         |         |
| NR-DC is configured, and MN configured measurement   |     |     |         |         |
| when NE-DC is configured, this feature is mandatory  |     |     |         |         |
| supported.                                           |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***intraF-NeighMeasForSCellWithoutSSB***             | UE  | No  | No      | FR1     |
|                                                      |     |     |         | only    |
| Indicates whether the UE supports the configuration  |     |     |         |         |
| of *servingCellMO* for SCell that does not transmit  |     |     |         |         |
| SS/PBCH block. A UE supporting this feature shall    |     |     |         |         |
| also support NR intra-frequency measurements on      |     |     |         |         |
| neighbour cells based on *servingCellMO* associated  |     |     |         |         |
| with SCell that does not transmit SS/PBCH block.     |     |     |         |         |
|                                                      |     |     |         |         |
| A UE supporting this feature shall also indicate     |     |     |         |         |
| support of *scellWithoutSSB* or                      |     |     |         |         |
| *scellWithoutSSB-InterBandCA-r18* or both.           |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***interFrequencyMeas-NoGap-r16***                   | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Indicates whether the UE can perform inter-frequency |     |     |         |         |
| SSB based measurements without measurement gaps if   |     |     |         |         |
| the SSB is completely contained in the active BWP of |     |     |         |         |
| the UE as specified in TS 38.133 \[5\]. If this      |     |     |         |         |
| parameter is indicated for FR1 and FR2 differently,  |     |     |         |         |
| each indication corresponds to the frequency range   |     |     |         |         |
| of cells to be measured.                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***interSatMeas-r17***                               | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports inter-satellite    |     |     |         |         |
| measurement as specified in TS 38.331 \[9\]. It is   |     |     |         |         |
| mandatory if the UE supports                         |     |     |         |         |
| *nonTerrestrialNetwork-r17*.                         |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***l3-MeasUnknownSCellActivation-r18***              | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports reporting valid L3 |     |     |         |         |
| measurement results triggered by the unknown SCell   |     |     |         |         |
| activation command                                   |     |     |         |         |
|                                                      |     |     |         |         |
| UE is required to meet the shortened SCell           |     |     |         |         |
| activation delay requirement in TS 38.133 \[5\] if   |     |     |         |         |
| the feature is supported, including single SCell     |     |     |         |         |
| activation, single PUCCH SCell activation, and       |     |     |         |         |
| multiple SCell activation with/without PUCCH SCell.  |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ltm-FastUE-Processing-r18***                      | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates the reduced T~LTM_processing~ delay of the |     |     |         |         |
| UE during cell switch.                               |     |     |         |         |
|                                                      |     |     |         |         |
| The capability signalling includes the following     |     |     |         |         |
| parameters:                                          |     |     |         |         |
|                                                      |     |     |         |         |
| > \- *fr1-r18* indicates the reduced                 |     |     |         |         |
| > T~LTM_processing~ for cell switch from FR1 to FR1. |     |     |         |         |
| >                                                    |     |     |         |         |
| > \- *fr2-r18* indicates the reduced                 |     |     |         |         |
| > T~LTM_processing~ for cell switch from FR2 to FR2. |     |     |         |         |
| >                                                    |     |     |         |         |
| > \- *fr1-AndFR2-r18* indicates the reduced          |     |     |         |         |
| > T~LTM_processing~ for cell switch from FR1/FR2 to  |     |     |         |         |
| > FR2/FR1.                                           |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ltm-InterFreq-r18***                              | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates UE supports inter-frequency MCG LTM on all |     |     |         |         |
| the bands where the UE indicates support of          |     |     |         |         |
| *ltm-MCG-IntraFreq-r18* or inter-frequency SCG LTM   |     |     |         |         |
| on all the bands where the UE indicates support of   |     |     |         |         |
| *ltm-SCG-IntraFreq-r18* respectively.                |     |     |         |         |
|                                                      |     |     |         |         |
| A UE supporting this feature shall also indicate     |     |     |         |         |
| support of *ltm-MCG-IntraFreq-r18* or                |     |     |         |         |
| *ltm-SCG-IntraFreq-r18.*                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ltm-interFreqL1-OnlyInBC-r18***                   | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| When included, for each BC in which the UE indicates |     |     |         |         |
| support of *interFreqL1-MeasConfig-r18*, the UE only |     |     |         |         |
| supports inter-frequency L1-RSRP measurement and     |     |     |         |         |
| reporting based on SSB(s) of LTM candidate cell(s)   |     |     |         |         |
| that are inside the BC. When not included, the       |     |     |         |         |
| description in *interFreqL1-MeasConfig-r18* is       |     |     |         |         |
| applicable.                                          |     |     |         |         |
|                                                      |     |     |         |         |
| A UE supporting this feature shall also indicate     |     |     |         |         |
| support of *interFreqL1-MeasConfig-r18*.             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ltm-InterFreqMeasGap-r18***                       | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports SSB based          |     |     |         |         |
| inter-frequency L1-RSRP measurements with            |     |     |         |         |
| measurement gaps for LTM.                            |     |     |         |         |
|                                                      |     |     |         |         |
| A UE supporting this feature shall also indicate     |     |     |         |         |
| support of *interFreqL1-MeasConfig-r18*.             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ltm-MCG-NRDC-r18***                               | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports LTM for MCG with   |     |     |         |         |
| RACH with NR-DC configured as defined in TS 38.331   |     |     |         |         |
| \[9\] and TS 38.321 \[8\]. UE indicating support for |     |     |         |         |
| this feature shall also indicate support of          |     |     |         |         |
| *ltm-MCG-IntraFreq-r18.*                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ltm-MCG-NRDC-Release-r18***                       | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports LTM for MCG with   |     |     |         |         |
| the release of NR-DC configuration as part of LTM    |     |     |         |         |
| execution when LTM cell switch command MAC CE is     |     |     |         |         |
| received. UE indicating support for this feature     |     |     |         |         |
| shall also indicate support of                       |     |     |         |         |
| *ltm-MCG-IntraFreq-r18.*                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ltm-RACH-LessCG-r18***                            | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports RACH-less LTM with |     |     |         |         |
| configured grant for MCG LTM if the UE indicates     |     |     |         |         |
| support of *ltm-MCG-IntraFreq-r18* or for SCG LTM if |     |     |         |         |
| the UE indicates support of *ltm-SCG-IntraFreq-r18*  |     |     |         |         |
| respectively.                                        |     |     |         |         |
|                                                      |     |     |         |         |
| UE indicating support for this feature shall also    |     |     |         |         |
| indicate support of either                           |     |     |         |         |
| *ltm-BeamIndicationJointTCI-r18* or                  |     |     |         |         |
| *ltm-BeamIndicationSeparateTCI-r18* for at least one |     |     |         |         |
| band and either *ta-IndicationCellSwitch-r18* or     |     |     |         |         |
| *ue-TA-Measurement-r18*.                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ltm-RACH-LessDG-r18***                            | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports RACH-Less LTM with |     |     |         |         |
| dynamic grant, for MCG LTM if the UE indicates       |     |     |         |         |
| support of *ltm-MCG-IntraFreq-r18* or for SCG LTM if |     |     |         |         |
| the UE indicates support of *ltm-SCG-IntraFreq-r18*  |     |     |         |         |
| respectively.                                        |     |     |         |         |
|                                                      |     |     |         |         |
| UE indicating support for this feature shall also    |     |     |         |         |
| indicate support of either                           |     |     |         |         |
| *ltm-BeamIndicationJointTCI-r18* or                  |     |     |         |         |
| *ltm-BeamIndicationSeparateTCI-r18* for at least one |     |     |         |         |
| band and TA indication in                            |     |     |         |         |
| *ta-IndicationCellSwitch-r18* or                     |     |     |         |         |
| *ue-TA-Measurement-r18*.                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ltm-Recovery-r18***                               | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports recovery procedure |     |     |         |         |
| for MCG LTM execution when the selected cell in RRC  |     |     |         |         |
| re-establishment procedure is a LTM candidate as     |     |     |         |         |
| specified in TS 38.331 \[9\].                        |     |     |         |         |
|                                                      |     |     |         |         |
| UE indicating support for this feature shall also    |     |     |         |         |
| indicate support of *ltm-MCG-IntraFreq-r18* for at   |     |     |         |         |
| least one band.                                      |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ltm-ReferenceConfig-r18***                        | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether UE supports a reference            |     |     |         |         |
| configuration for LTM.                               |     |     |         |         |
|                                                      |     |     |         |         |
| UE indicating support for this feature shall also    |     |     |         |         |
| indicate support of either *ltm-MCG-IntraFreq-r18*   |     |     |         |         |
| or *ltm-SCG-IntraFreq-r18* for at least one band.    |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***maxNumberCLI-RSSI-r16***                          | UE  | CY  | TDD     | No      |
|                                                      |     |     | only    |         |
| Defines the maximum number of CLI-RSSI measurement   |     |     |         |         |
| resources for CLI RSSI measurement. If the UE        |     |     |         |         |
| supports *cli-RSSI-Meas-r16*, the UE shall report    |     |     |         |         |
| this capability.                                     |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***maxNumberCLI-SRS-RSRP-r16***                      | UE  | CY  | TDD     | No      |
|                                                      |     |     | only    |         |
| Defines the maximum number of SRS-RSRP measurement   |     |     |         |         |
| resources for SRS-RSRP measurement. If the UE        |     |     |         |         |
| supports *cli-SRS-RSRP-Meas-r16*, the UE shall       |     |     |         |         |
| report this capability.                              |     |     |         |         |
|                                                      |     |     |         |         |
| NOTE 1: A slot is based on minimum SCS among active  |     |     |         |         |
| BWPs across all CCs configured for SRS-RSRP          |     |     |         |         |
| measurement.                                         |     |     |         |         |
|                                                      |     |     |         |         |
| NOTE 2: A SRS resource occasion that overlaps with   |     |     |         |         |
| the slot is counted as one measurement resource in   |     |     |         |         |
| the slot.                                            |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***maxNumberCSI-RS-RRM-RS-SINR***                    | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Defines the maximum number of CSI-RS resources for   |     |     |         |         |
| RRM and RS-SINR measurement across all measurement   |     |     |         |         |
| frequencies per slot. UE indicating support of this  |     |     |         |         |
| feature shall also indicate support of               |     |     |         |         |
| *csi-RSRP-AndRSRQ-MeasWithSSB*,                      |     |     |         |         |
| *csi-RSRP-AndRSRQ-MeasWithoutSSB* or                 |     |     |         |         |
| *csi-SINR-Meas*. If UE supports any of               |     |     |         |         |
| *csi-RSRP-AndRSRQ-MeasWithSSB*,                      |     |     |         |         |
| *csi-RSRP-AndRSRQ-MeasWithoutSSB*, and               |     |     |         |         |
| *csi-SINR-Meas*, UE shall report this capability.    |     |     |         |         |
|                                                      |     |     |         |         |
| NOTE: A slot is based on minimum SCS among all       |     |     |         |         |
| measurement frequencies configured for RRM and       |     |     |         |         |
| RS-SINR measurement.                                 |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***maxNumberPerSlotCLI-SRS-RSRP-r16***               | UE  | CY  | TDD     | No      |
|                                                      |     |     | only    |         |
| Defines the maximum number of SRS-RSRP measurement   |     |     |         |         |
| resources per slot for SRS-RSRP measurement. If the  |     |     |         |         |
| UE supports *cli-SRS-RSRP-Meas-r16*, the UE shall    |     |     |         |         |
| report this capability.                              |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***maxNumberResource-CSI-RS-RLM***                   | UE  | CY  | No      | Yes     |
|                                                      |     |     |         |         |
| Defines the maximum number of CSI-RS resources       |     |     |         |         |
| within a slot per spCell for CSI-RS based RLM. UE    |     |     |         |         |
| indicating support of this feature shall also        |     |     |         |         |
| indicate support of *csi-RS-RLM* or                  |     |     |         |         |
| *ssb-AndCSI-RS-RLM*, If UE supports any of           |     |     |         |         |
| *csi-RS-RLM* and *ssb-AndCSI-RS-RLM*, UE shall       |     |     |         |         |
| report this capability.                              |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***measSequenceConfig-r18***                         | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports configuration of   |     |     |         |         |
| *measSequence-r18* in *MeasObjectNR* and             |     |     |         |         |
| *MeasObjectEUTRA* for recommended sequence for       |     |     |         |         |
| intra/inter-RAT intra/inter-frequency measurement.   |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ncsg-MeasGapNR-Patterns-r17***                    | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports NR-only NCSG       |     |     |         |         |
| patterns. The left most bit in the bitmap            |     |     |         |         |
| corresponds to NCSG pattern #0 and the right most    |     |     |         |         |
| bit in the bitmap corresponds to NCSG pattern #23. A |     |     |         |         |
| bit in the bitmap is set to 1 if the corresponding   |     |     |         |         |
| pattern is supported by the UE. NCSG patterns #0 to  |     |     |         |         |
| #23 are as specified in TS 38.133 \[5\].             |     |     |         |         |
|                                                      |     |     |         |         |
| NCSG patterns #2 and #3 are mandatory (i.e. the      |     |     |         |         |
| corresponding bits in the bitmap is set to 1) if the |     |     |         |         |
| UE includes this field. NCSG patterns #17 and #18    |     |     |         |         |
| are mandatory (i.e. the corresponding bits in the    |     |     |         |         |
| bitmap is set to 1) if UE includes this field and    |     |     |         |         |
| supports a FR2 band. UEs supporting this shall       |     |     |         |         |
| indicate support of                                  |     |     |         |         |
| *nr-NeedForGapNCSG-Reporting-r17*.                   |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ncsg-MeasGapPatterns-r17***                       | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports NCSG patterns. The |     |     |         |         |
| left most bit in the bitmap corresponds to NCSG      |     |     |         |         |
| pattern #0 and the right most bit in the bitmap      |     |     |         |         |
| corresponds to NCSG pattern #23. A bit in the bitmap |     |     |         |         |
| is set to 1 if the corresponding pattern is          |     |     |         |         |
| supported by the UE. NCSG patterns #0 to #23 are as  |     |     |         |         |
| specified in TS 38.133 \[5\].                        |     |     |         |         |
|                                                      |     |     |         |         |
| NCSG patterns #0 and #1 are mandatory (i.e. the      |     |     |         |         |
| corresponding bits in the bitmap is set to 1) if the |     |     |         |         |
| UE includes this field. NCSG patterns #13 and #14    |     |     |         |         |
| are mandatory (i.e. the corresponding bits in the    |     |     |         |         |
| bitmap is set to 1) if UE supports                   |     |     |         |         |
| *ncsg-MeasGapPerFR-r17* or if the UE is NCSG capable |     |     |         |         |
| and supports FR2 band in standalone mode. UEs        |     |     |         |         |
| supporting this shall indicate support of            |     |     |         |         |
| *nr-NeedForGapNCSG-Reporting-r17* or                 |     |     |         |         |
| *eutra-NeedForGapNCSG-Reporting-r17*.                |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ncsg-MeasGapPerFR-r17***                          | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports per-FR NCSG. UEs   |     |     |         |         |
| supporting this shall indicate support of            |     |     |         |         |
| *nr-NeedForGapNCSG-Reporting-r17*.                   |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ncsg-SymbolLevelScheduleRestrictionInter-r17***   | UE  | No  | No      | FR2     |
|                                                      |     |     |         | only    |
| Indicates whether the UE supports performing         |     |     |         |         |
| measurement with NCSG based on flag                  |     |     |         |         |
| *deriveSSB-IndexFromCell-inter* and meeting the      |     |     |         |         |
| following requirements that the scheduling           |     |     |         |         |
| restriction in FR2 serving cell during NCSG ML is on |     |     |         |         |
| SSB symbol level. UEs supporting this shall indicate |     |     |         |         |
| support of *nr-NeedForGapNCSG-Reporting-r17*.        |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***nr-AutonomousGaps-r16***                          | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Defines whether the UE supports, upon configuration  |     |     |         |         |
| of *useAutonomousGaps* by the network, acquisition   |     |     |         |         |
| of relevant information from a neighbouring NR cell  |     |     |         |         |
| by reading the SI of the neighbouring cell using     |     |     |         |         |
| autonomous gap and reporting the acquired            |     |     |         |         |
| information to the network as specified in TS 38.331 |     |     |         |         |
| \[9\] when MR-DC is not configured. If this          |     |     |         |         |
| parameter is indicated for FR1 and FR2 differently,  |     |     |         |         |
| each indication corresponds to the frequency range   |     |     |         |         |
| of measured target cell.                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***nr-AutonomousGaps-ENDC-r16***                     | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Defines whether the UE supports, upon configuration  |     |     |         |         |
| of *useAutonomousGaps* by the network, acquisition   |     |     |         |         |
| of relevant information from a neighbouring NR cell  |     |     |         |         |
| by reading the SI of the neighbouring cell using     |     |     |         |         |
| autonomous gap and reporting the acquired            |     |     |         |         |
| information to the network as specified in TS 38.331 |     |     |         |         |
| \[9\] when (NG)EN-DC is configured. If this          |     |     |         |         |
| parameter is indicated for FR1 and FR2 differently,  |     |     |         |         |
| each indication corresponds to the frequency range   |     |     |         |         |
| of measured target cell.                             |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***nr-AutonomousGaps-NEDC-r16***                     | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Defines whether the UE supports, upon configuration  |     |     |         |         |
| of *useAutonomousGaps* by the network, acquisition   |     |     |         |         |
| of relevant information from a neighbouring NR cell  |     |     |         |         |
| by reading the SI of the neighbouring cell using     |     |     |         |         |
| autonomous gap and reporting the acquired            |     |     |         |         |
| information to the network as specified in TS 38.331 |     |     |         |         |
| \[9\] when NE-DC is configured. If this parameter is |     |     |         |         |
| indicated for FR1 and FR2 differently, each          |     |     |         |         |
| indication corresponds to the frequency range of     |     |     |         |         |
| measured target cell.                                |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***nr-AutonomousGaps-NRDC-r16***                     | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Defines whether the UE supports, upon configuration  |     |     |         |         |
| of *useAutonomousGaps* by the network, acquisition   |     |     |         |         |
| of relevant information from a neighbouring NR cell  |     |     |         |         |
| by reading the SI of the neighbouring cell using     |     |     |         |         |
| autonomous gap and reporting the acquired            |     |     |         |         |
| information to the network as specified in TS 38.331 |     |     |         |         |
| \[9\] when NR-DC is configured. If this parameter is |     |     |         |         |
| indicated for FR1 and FR2 differently, each          |     |     |         |         |
| indication corresponds to the frequency range of     |     |     |         |         |
| measured target cell.                                |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***nr-CGI-Reporting***                               | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Defines whether the UE supports acquisition of       |     |     |         |         |
| relevant CGI-information from a neighbouring         |     |     |         |         |
| intra-frequency or inter-frequency NR cell by        |     |     |         |         |
| reading the SI of the neighbouring cell and          |     |     |         |         |
| reporting the acquired information to the network as |     |     |         |         |
| specified in TS 38.331 \[9\] when (NG)EN-DC and      |     |     |         |         |
| NE-DC are not configured or, when consistent DRX is  |     |     |         |         |
| configured in NR-DC. The consistent DRX              |     |     |         |         |
| configuration implies that MN and SN have the same   |     |     |         |         |
| DRX cycle and on-duration configured by MN           |     |     |         |         |
| completely contains on-duration configured by SN. It |     |     |         |         |
| is optional for (e)RedCap UEs.                       |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***nr-CGI-Reporting-ENDC***                          | UE  | Yes | No      | No      |
|                                                      |     |     |         |         |
| Defines whether the UE supports acquisition of       |     |     |         |         |
| relevant CGI-information from a neighbouring         |     |     |         |         |
| intra-frequency or inter-frequency NR cell by        |     |     |         |         |
| reading the SI of the neighbouring cell and          |     |     |         |         |
| reporting the acquired information to the network as |     |     |         |         |
| specified in TS 38.331 \[9\] when the (NG)EN-DC is   |     |     |         |         |
| configured.                                          |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***nr-CGI-Reporting-NEDC***                          | UE  | Yes | No      | No      |
|                                                      |     |     |         |         |
| Defines whether the UE supports acquisition of       |     |     |         |         |
| relevant information from a neighbouring             |     |     |         |         |
| intra-frequency or inter-frequency NR cell by        |     |     |         |         |
| reading the SI of the neighbouring cell and          |     |     |         |         |
| reporting the acquired information to the network as |     |     |         |         |
| specified in TS 38.331 \[9\] when the NE-DC is       |     |     |         |         |
| configured.                                          |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***nr-CGI-Reporting-NPN-r16***                       | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Defines whether the UE supports acquisition of       |     |     |         |         |
| NPN-relevant CGI-information from a neighbouring     |     |     |         |         |
| intra-frequency or inter-frequency NR NPN cell by    |     |     |         |         |
| reading the SI of the neighbouring cell and          |     |     |         |         |
| reporting the acquired information to the network as |     |     |         |         |
| specified in TS 38.331 \[9\]. If UE supports NPN, UE |     |     |         |         |
| shall report this capability. It is optional for     |     |     |         |         |
| (e)RedCap UEs.                                       |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***nr-CGI-Reporting-NRDC***                          | UE  | Yes | No      | No      |
|                                                      |     |     |         |         |
| Defines whether the UE supports acquisition of       |     |     |         |         |
| relevant information from a neighbouring             |     |     |         |         |
| intra-frequency or inter-frequency NR cell by        |     |     |         |         |
| reading the SI of the neighbouring cell and          |     |     |         |         |
| reporting the acquired information to the network as |     |     |         |         |
| specified in TS 38.331 \[9\] when the NR-DC is       |     |     |         |         |
| configured wherein MN and SN have different DRX      |     |     |         |         |
| cycles, or on-duration configured by MN does not     |     |     |         |         |
| contain on-duration configured by SN if the DRX      |     |     |         |         |
| cycles are the same.                                 |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***nr-NeedForGapNCSG-Reporting-r17***                | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports reporting of the   |     |     |         |         |
| NCSG and measurement gap requirement information for |     |     |         |         |
| SSB based measurement in the UE response to a        |     |     |         |         |
| network configuration RRC message as specified in TS |     |     |         |         |
| 38.331 \[9\].                                        |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***nr-NeedForGap-Reporting-r16***                    | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports reporting the      |     |     |         |         |
| measurement gap requirement information for NR       |     |     |         |         |
| target in the UE response to a network configuration |     |     |         |         |
| RRC message.                                         |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***nr-NeedForInterruptionReport-r18***               | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports reporting the      |     |     |         |         |
| interruption requirement information for SSB based   |     |     |         |         |
| measurement towards NR target without gap in the UE  |     |     |         |         |
| response to a network configuration RRC message. The |     |     |         |         |
| UE supporting this feature shall also indicate       |     |     |         |         |
| support of *nr-NeedForGap-Reporting-r16*.            |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ntn-NeighbourCellInfoSupport-r18***               | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports configuration of   |     |     |         |         |
| *ntn-NeighbourCellInfo-r18* in *MeasObjectNR* for    |     |     |         |         |
| dedicated ephemeris. A UE supporting this feature    |     |     |         |         |
| shall also indicate the support of                   |     |     |         |         |
| *nonTerrestrialNetwork-r17*.                         |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***parallelMeasurementGap-r17***                     | UE  | No  | FDD     | FR1     |
|                                                      |     |     | only    | only    |
| Indicates whether the UE supports 2 parallel         |     |     |         |         |
| measurement gaps for NTN SSB based RRM measurements. |     |     |         |         |
| If a UE does not include this field but includes     |     |     |         |         |
| *nonTerrestrialNetwork-r17*, the UE supports 1       |     |     |         |         |
| measurement gap for NTN SSB based RRM measurements.  |     |     |         |         |
| If this parameter is indicated, a UE shall also      |     |     |         |         |
| support that two parallel measurement gaps with the  |     |     |         |         |
| same gap type can be associated to one frequency     |     |     |         |         |
| layer. A UE supporting this feature shall also       |     |     |         |         |
| indicate the support of *nonTerrestrialNetwork-r17*. |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***parallelSMTC-r17***                               | UE  | No  | FDD     | FR1     |
|                                                      |     |     | only    | only    |
| Indicates whether the UE supports NTN SSB based RRM  |     |     |         |         |
| measurements on target cells belonging to 4 SMTC-s   |     |     |         |         |
| on a single frequency carrier. If a UE does not      |     |     |         |         |
| include this field but includes                      |     |     |         |         |
| *nonTerrestrialNetwork-r17*, the UE supports NTN SSB |     |     |         |         |
| based RRM measurements on target cells belonging to  |     |     |         |         |
| 2 SMTC-s on a single frequency carrier.              |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***periodicEUTRA-MeasAndReport***                    | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports periodic EUTRA     |     |     |         |         |
| measurement and reporting. It is mandated if the UE  |     |     |         |         |
| supports EUTRA.                                      |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***pcellT312-r16***                                  | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports T312 based fast    |     |     |         |         |
| failure recovery for PCell.                          |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***preconfiguredUE-AutonomousMeasGap-r17\***         | UE  | No  | No      | No      |
| Indicates whether the UE supports the preconfigured  |     |     |         |         |
| measurement gap with UE-autonomous mechanism for     |     |     |         |         |
| activation and deactivation as specified in TS       |     |     |         |         |
| 38.133 \[5\].                                        |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***preconfiguredNW-ControlledMeasGap-r17\***         | UE  | No  | No      | No      |
| Indicates whether the UE supports the preconfigured  |     |     |         |         |
| measurement gap with network-controlled mechanism    |     |     |         |         |
| for activation and deactivation as specified in TS   |     |     |         |         |
| 38.133 \[5\].                                        |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***rach-LessHandoverInterFreq-r18***                 | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports inter-frequency    |     |     |         |         |
| RACH-less handover. The UE supports inter-frequency  |     |     |         |         |
| RACH-less handover on all the bands where the UE     |     |     |         |         |
| indicates support for *rach-LessHandoverCG-r18* or   |     |     |         |         |
| *rach-LessHandoverDG-r18*.                           |     |     |         |         |
|                                                      |     |     |         |         |
| If the UE does not support                           |     |     |         |         |
| *rach-LessHandoverInterFreq-r18*                     |     |     |         |         |
|                                                      |     |     |         |         |
| but indicates support of *rach-LessHandoverCG-r18 or |     |     |         |         |
| rach-LessHandoverDG-r18*, the UE only supports       |     |     |         |         |
| intra-frequency RACH-less handover with configured   |     |     |         |         |
| grant or dynamic grant, respectively, on the         |     |     |         |         |
| corresponding bands.                                 |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***reportAddNeighMeasForPeriodic-r16***              | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Defines whether the UE supports periodic reporting   |     |     |         |         |
| of best neighbour cells per serving frequency, as    |     |     |         |         |
| defined in TS 38.331 \[9\]. It is optional for       |     |     |         |         |
| (e)RedCap UEs.                                       |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***secondBestCellChangeReport-r18***                 | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports the sending of the |     |     |         |         |
| measurement report if more than one of two best      |     |     |         |         |
| cells changed as specified in TS 38.331 \[9\].       |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***serviceLinkPropDelayDiffReporting-r17***          | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports the reporting of   |     |     |         |         |
| service link propagation delay difference between    |     |     |         |         |
| serving cell and neighbour cell(s). A UE supporting  |     |     |         |         |
| this feature shall also indicate the support of      |     |     |         |         |
| *nonTerrestrialNetwork-r17*.                         |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***sftd-MeasPSCell***                                | UE  | No  | Yes     | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports SFTD measurements  |     |     |         |         |
| between the PCell and a configured PSCell. If this   |     |     |         |         |
| capability is included in UE-MRDC-Capability, it     |     |     |         |         |
| indicates that the UE supports SFTD measurement      |     |     |         |         |
| between PCell and PSCell in (NG)EN-DC. If this       |     |     |         |         |
| capability is included in UE-NR-Capability, it       |     |     |         |         |
| indicates that the UE supports SFTD measurement      |     |     |         |         |
| between PCell and PSCell in NR-DC.                   |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***sftd-MeasPSCell-NEDC***                           | UE  | No  | Yes     | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports SFTD measurement   |     |     |         |         |
| between the NR PCell and a configured E-UTRA PSCell  |     |     |         |         |
| in NE-DC.                                            |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***sftd-MeasNR-Cell***                               | UE  | No  | Yes     | No      |
|                                                      |     |     |         |         |
| Indicates whether the SFTD measurement with and      |     |     |         |         |
| without measurement gaps between the EUTRA PCell and |     |     |         |         |
| the NR cells is supported by the UE which is capable |     |     |         |         |
| of EN-DC/NGEN-DC when EN-DC/NGEN-DC is not           |     |     |         |         |
| configured. The SFTD measurement without gaps can be |     |     |         |         |
| used when the UE supports at least one EN-DC band    |     |     |         |         |
| combination consisting of the set of the current     |     |     |         |         |
| E-UTRA serving frequencies and the NR frequency      |     |     |         |         |
| where SFTD measurement is configured. In             |     |     |         |         |
| UE-NR-Capability, this field is not used, and UE     |     |     |         |         |
| does not include the field.                          |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***sftd-MeasNR-Neigh***                              | UE  | No  | Yes     | No      |
|                                                      |     |     |         |         |
| Indicates whether the inter-frequency SFTD           |     |     |         |         |
| measurement with and without measurement gaps        |     |     |         |         |
| between the NR PCell and inter-frequency NR          |     |     |         |         |
| neighbour cells is supported by the UE when MR-DC is |     |     |         |         |
| not configured. The SFTD measurement without gaps    |     |     |         |         |
| can be used when the UE supports at least one DC or  |     |     |         |         |
| CA band combination consisting of the set of the     |     |     |         |         |
| current NR serving frequencies and the NR frequency  |     |     |         |         |
| where SFTD measurement is configured.                |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***sftd-MeasNR-Neigh-DRX***                          | UE  | No  | Yes     | No      |
|                                                      |     |     |         |         |
| Indicates whether the inter-frequency SFTD           |     |     |         |         |
| measurement using DRX off period between the NR      |     |     |         |         |
| PCell and the inter-frequency NR neighbour cells is  |     |     |         |         |
| supported by the UE when MR-DC is not configured.    |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***shortMeasInterval-r18***                          | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports using SSB          |     |     |         |         |
| periodicity instead of SMTC periodicity for the      |     |     |         |         |
| measurement interval during unknown SCell activation |     |     |         |         |
| when the SMTC is only configured in measurement      |     |     |         |         |
| object for enhanced unknown SCell activation         |     |     |         |         |
| requirement and performing L1-RSRP measurement in    |     |     |         |         |
| non-DRX mode even DRX is configured during unknown   |     |     |         |         |
| SCell activation.                                    |     |     |         |         |
|                                                      |     |     |         |         |
| UE is required to meet the shortened SCell           |     |     |         |         |
| activation delay requirement in TS 38.133 \[5\] if   |     |     |         |         |
| the feature is supported.                            |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***simultaneousRxDataSSB-DiffNumerology***           | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Indicates whether the UE supports concurrent         |     |     |         |         |
| intra-frequency measurement on serving cell or       |     |     |         |         |
| neighbouring cell and PDCCH or PDSCH reception from  |     |     |         |         |
| the serving cell with a different numerology as      |     |     |         |         |
| defined in clause 8 and 9 of TS 38.133 \[5\].        |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***simultaneousRxDataSSB-DiffNumerology-Inter-r16*** | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Indicates whether the UE supports concurrent SSB     |     |     |         |         |
| based inter-frequency measurement without            |     |     |         |         |
| measurement gap on neighbouring cell and PDCCH or    |     |     |         |         |
| PDSCH reception from the serving cell with a         |     |     |         |         |
| different numerology as defined in clause 8 and 9 of |     |     |         |         |
| TS 38.133 \[5\]. UE indicates support of this        |     |     |         |         |
| indicates support of *interFrequencyMeas-NoGap-r16*. |     |     |         |         |
| If this parameter is indicated for FR1 and FR2       |     |     |         |         |
| differently, each indication corresponds to the      |     |     |         |         |
| frequency range where the SSB and PDCCH/PDSCH are    |     |     |         |         |
| received.                                            |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ssb-RLM***                                        | UE  | Yes | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE can perform radio link      |     |     |         |         |
| monitoring procedure based on measurement of SS/PBCH |     |     |         |         |
| block as specified in TS 38.213 \[11\] and TS 38.133 |     |     |         |         |
| \[5\]. This field shall be set to *supported*. This  |     |     |         |         |
| applies only to non-shared spectrum channel access.  |     |     |         |         |
| For shared spectrum channel access,                  |     |     |         |         |
| *ssb-RLM-DynamicChAccess-r16* or                     |     |     |         |         |
| *ssb-RLM-Semi-StaticChAccess-r16* applies.           |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ssb-AndCSI-RS-RLM***                              | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE can perform radio link      |     |     |         |         |
| monitoring procedure based on measurement of SS/PBCH |     |     |         |         |
| block and CSI-RS as specified in TS 38.213 \[11\]    |     |     |         |         |
| and TS 38.133 \[5\]. UE indicating support of this   |     |     |         |         |
| feature shall also indicate support of *ssb-RLM* and |     |     |         |         |
| *csi-RS-RLM*. If the UE supports this feature, the   |     |     |         |         |
| UE needs to report *maxNumberResource-CSI-RS-RLM*.   |     |     |         |         |
| This applies only to non-shared spectrum channel     |     |     |         |         |
| access. For shared spectrum channel access,          |     |     |         |         |
| *ssb-AndCSI-RS-RLM-r16* applies.                     |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***ss-SINR-Meas***                                   | UE  | No  | No      | Yes     |
|                                                      |     |     |         |         |
| Indicates whether the UE can perform SS-SINR         |     |     |         |         |
| measurement as specified in TS 38.215 \[13\]. If     |     |     |         |         |
| this parameter is indicated for FR1 and FR2          |     |     |         |         |
| differently, each indication corresponds to the      |     |     |         |         |
| frequency range of measured target cell. This        |     |     |         |         |
| applies only to non-shared spectrum channel access.  |     |     |         |         |
| For shared spectrum channel access,                  |     |     |         |         |
| *ss-SINR-Meas-r16* applies.                          |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***supportedGapPattern***                            | UE  | CY  | No      | No      |
|                                                      |     |     |         |         |
| Indicates measurement gap pattern(s) optionally      |     |     |         |         |
| supported by the UE for NR SA, for NR-DC, for NE-DC  |     |     |         |         |
| and for independent measurement gap configuration on |     |     |         |         |
| FR2 in (NG)EN-DC. The leading / leftmost bit (bit 0) |     |     |         |         |
| corresponds to the gap pattern 2, the next bit       |     |     |         |         |
| corresponds to the gap pattern 3, as specified in TS |     |     |         |         |
| 38.133 \[5\] and so on. The UE shall set the bits    |     |     |         |         |
| corresponding to the measurement gap pattern 13, 14, |     |     |         |         |
| 17, 18 and 19 to 1 if the UE is an NR standalone     |     |     |         |         |
| capable UE that supports a band in FR2 or if the UE  |     |     |         |         |
| is an (NG)EN-DC capable UE that supports             |     |     |         |         |
| *independentGapConfig* and supports a band in FR2.   |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***supportedGapPattern-r16***                        | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates measurement gap pattern(s) optionally      |     |     |         |         |
| supported by the UE for NR SA, for NR-DC for PRS     |     |     |         |         |
| measurement and NR/E-UTRA RRM measurement. The       |     |     |         |         |
| leading / leftmost bit (bit 0) corresponds to the    |     |     |         |         |
| gap pattern 24, the next bit corresponds to the gap  |     |     |         |         |
| pattern 25, as specified in TS 38.133 \[5\]. The     |     |     |         |         |
| applicability of the gap patterns 24 and 25 is       |     |     |         |         |
| defined in clause 9.1.2 of TS 38.133 \[5\]. A UE     |     |     |         |         |
| that indicates support of this capability shall      |     |     |         |         |
| indicate support of                                  |     |     |         |         |
| *NR-DL-PRS-ProcessingCapability-r16* defined in TS   |     |     |         |         |
| 37.355 \[22\].                                       |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***supportedGapPattern-NRonly-r16***                 | UE  | FD  | No      | No      |
|                                                      |     |     |         |         |
| Indicates measurement gap pattern(s) optionally      |     |     |         |         |
| supported by the UE for NR SA and NR-DC when the     |     |     |         |         |
| frequencies to be measured within this measurement   |     |     |         |         |
| gap are all NR frequencies. The leading / leftmost   |     |     |         |         |
| bit (bit 0) corresponds to the gap pattern 2, the    |     |     |         |         |
| next bit corresponds to the gap pattern 3 and so on. |     |     |         |         |
| The UE shall set the bits corresponding to the       |     |     |         |         |
| measurement gap pattern 2, 3 and 11 to 1.            |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+
| ***supportedGapPattern-NRonly-NEDC-r16***            | UE  | No  | No      | No      |
|                                                      |     |     |         |         |
| Indicates whether the UE supports gap patterns 2, 3  |     |     |         |         |
| and 11 in NE-DC when the frequencies to be measured  |     |     |         |         |
| within this measurement gap are all NR frequencies.  |     |     |         |         |
+------------------------------------------------------+-----+-----+---------+---------+