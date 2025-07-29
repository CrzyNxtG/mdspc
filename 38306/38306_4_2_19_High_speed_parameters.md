### 4.2.19 High speed parameters

+----------------------------------------------------+-----+----+---------+---------+
| Definitions for parameters                         | Per | M  | FDD-TDD | FR1-FR2 |
|                                                    |     |    |         |         |
|                                                    |     |    | DIFF    | DIFF    |
+----------------------------------------------------+-----+----+---------+---------+
| ***demodulationEnhancement-r16***                  | UE  | No | No      | FR1     |
|                                                    |     |    |         | only    |
| Indicates whether the UE supports the enhanced     |     |    |         |         |
| demodulation processing for HST-SFN joint          |     |    |         |         |
| transmission scheme with velocity up to 500km/h as |     |    |         |         |
| specified in TS 38.101-4 \[18\]. This field        |     |    |         |         |
| applies to MN configured demodulation enhancement  |     |    |         |         |
| when MR-DC is not configured and SN configured     |     |    |         |         |
| demodulation enhancement when (NG)EN-DC is         |     |    |         |         |
| configured.                                        |     |    |         |         |
+----------------------------------------------------+-----+----+---------+---------+
| ***intraNR-MeasurementEnhancement-r16***           | UE  | No | No      | FR1     |
|                                                    |     |    |         | only    |
| Indicates whether the UE supports the enhanced     |     |    |         |         |
| intra-NR RRM requirements to support high speed up |     |    |         |         |
| to 500 km/h as specified in TS 38.133 \[5\]. This  |     |    |         |         |
| field applies to MN configured measurement         |     |    |         |         |
| enhancement when MR-DC is not configured and SN    |     |    |         |         |
| configured measurement enhancement when (NG)EN-DC  |     |    |         |         |
| is configured.                                     |     |    |         |         |
|                                                    |     |    |         |         |
| The UE can include this field only if the UE does  |     |    |         |         |
| not indicate the support of                        |     |    |         |         |
| *measurementEnhancement-r16* and                   |     |    |         |         |
| *interRAT-MeasurementEnhancement-r16*. Otherwise,  |     |    |         |         |
| the UE does not include this field.                |     |    |         |         |
+----------------------------------------------------+-----+----+---------+---------+
| ***interRAT-MeasurementEnhancement-r16***          | UE  | No | No      | FR1     |
|                                                    |     |    |         | only    |
| Indicates whether the UE supports the enhanced     |     |    |         |         |
| inter-RAT E-UTRAN RRM requirements to support high |     |    |         |         |
| speed up to 500 km/h as specified in TS 38.133     |     |    |         |         |
| \[5\]. This field applies to MN configured         |     |    |         |         |
| measurement enhancement.                           |     |    |         |         |
|                                                    |     |    |         |         |
| The UE can include this field only if the UE does  |     |    |         |         |
| not indicate the support of                        |     |    |         |         |
| *measurementEnhancement-r16* and                   |     |    |         |         |
| *intraNR-MeasurementEnhancement-r16*. Otherwise,   |     |    |         |         |
| the UE does not include this field.                |     |    |         |         |
+----------------------------------------------------+-----+----+---------+---------+
| ***measurementEnhancement-r16***                   | UE  | No | No      | FR1     |
|                                                    |     |    |         | only    |
| Indicates whether the UE supports the enhanced     |     |    |         |         |
| intra-NR and inter-RAT E-UTRAN RRM requirements    |     |    |         |         |
| for MN configured measurement enhancement when     |     |    |         |         |
| MR-DC is not configured, and the enhanced intra-NR |     |    |         |         |
| RRM requirements for SN configured measurement     |     |    |         |         |
| enhancement when (NG)EN-DC is configured, to       |     |    |         |         |
| support high speed up to 500 km/h as specified in  |     |    |         |         |
| TS 38.133 \[5\].                                   |     |    |         |         |
+----------------------------------------------------+-----+----+---------+---------+
| ***measurementEnhancementCA-r17***                 | UE  | No | No      | FR1     |
|                                                    |     |    |         | only    |
| Indicates whether the UE supports the enhanced RRM |     |    |         |         |
| requirements for carrier aggregation to support    |     |    |         |         |
| high speed up to 500 km/h as specified in TS       |     |    |         |         |
| 38.133 \[5\].                                      |     |    |         |         |
|                                                    |     |    |         |         |
| UE indicating support of this feature shall        |     |    |         |         |
| indicate support of *measurementEnhancement-r16*   |     |    |         |         |
| or *intraNR-MeasurementEnhancement-r16*.           |     |    |         |         |
+----------------------------------------------------+-----+----+---------+---------+
| ***measurementEnhancementInterFreq-r17***          | UE  | No | No      | FR1     |
|                                                    |     |    |         | only    |
| Indicates whether the UE supports the enhanced RRM |     |    |         |         |
| requirements for inter-frequency measurements in   |     |    |         |         |
| connected mode to support high speed up to 500     |     |    |         |         |
| km/h as specified in TS 38.133 \[5\].              |     |    |         |         |
|                                                    |     |    |         |         |
| UE indicating support of this feature shall        |     |    |         |         |
| indicate support of *measurementEnhancement-r16*   |     |    |         |         |
| or *intraNR-MeasurementEnhancement-r16*.           |     |    |         |         |
+====================================================+=====+====+=========+=========+