### 4.2.20 Application layer measurement parameters

+--------------------------------------------------+-----+----+---------+---------+
| Definitions for parameters                       | Per | M  | FDD-TDD | FR1-FR2 |
|                                                  |     |    | DIFF    | DIFF    |
+--------------------------------------------------+-----+----+---------+---------+
| ***qoe-AdditionalMemoryMeasReport-r18***         | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates the minimum AS layer memory size the   |     |    |         |         |
| UE supports for QoE measurement in RRC_IDLE and  |     |    |         |         |
| RRC_INACTIVE in addition to the \"AS layer       |     |    |         |         |
| memory size for QoE paused measurement           |     |    |         |         |
| reports\". Value kB128 means the UE supports at  |     |    |         |         |
| least 128 kilobytes for this purpose, and so on. |     |    |         |         |
| A UE supporting this feature shall also support  |     |    |         |         |
| *qoe-IdleInactiveMeasReport-r18*.                |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***qoe-IdleInactiveMeasReport-r18***             | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports NR QoE         |     |    |         |         |
| Measurement Collection in RRC_IDLE and           |     |    |         |         |
| RRC_INACTIVE states for the services indicated   |     |    |         |         |
| with                                             |     |    |         |         |
|                                                  |     |    |         |         |
| *qoe-Streaming-MeasReport-r17* or                |     |    |         |         |
| *qoe-MTSI-MeasReport-r17* or                     |     |    |         |         |
| *qoe-VR-MeasReport-r17*.                         |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***qoe-MTSI-MeasReport-r17***                    | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports NR QoE         |     |    |         |         |
| Measurement Collection for MTSI services, see TS |     |    |         |         |
| 26.114 \[30\].                                   |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***qoe-NRDC-MeasReport-r18***                    | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports to receive QoE |     |    |         |         |
| configuration(s) via SRB1 and/or SRB3 (if        |     |    |         |         |
| supported) from SN, and send the corresponding   |     |    |         |         |
| QoE report(s) via SRB4 and/or SRB5 (if the UE    |     |    |         |         |
| supports srb5). A UE supporting this feature     |     |    |         |         |
| shall also support                               |     |    |         |         |
| *qoe-Streaming-MeasReport-r17* or                |     |    |         |         |
| *qoe-MTSI-MeasReport-r17* or                     |     |    |         |         |
| *qoe-VR-MeasReport-r17*.                         |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***qoe-PriorityBasedDiscarding-r18***            | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports to discard QoE |     |    |         |         |
| report(s) stored during QoE pause for UE in      |     |    |         |         |
| RRC_CONNECTED and stored in                      |     |    |         |         |
| RRC_IDLE/RRC_INACTIVE based on the priority      |     |    |         |         |
| information gNB provides. A UE supporting this   |     |    |         |         |
| feature shall also support                       |     |    |         |         |
| *qoe-Streaming-MeasReport-r17* or                |     |    |         |         |
| *qoe-MTSI-MeasReport-r17* or                     |     |    |         |         |
| *qoe-VR-MeasReport-r17*, and conditionally       |     |    |         |         |
| support *qoe-IdleInactiveMeasReport-r18* for QoE |     |    |         |         |
| measurement reports in RRC_IDLE/RRC_INACTIVE.    |     |    |         |         |
+==================================================+:===:+:==:+:=======:+:=======:+
| ***qoe-Streaming-MeasReport-r17***               | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports NR QoE         |     |    |         |         |
| Measurement Collection for streaming services,   |     |    |         |         |
| see TS 26.247 \[29\].                            |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***qoe-MTSI-MeasReport-r17***                    | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports NR QoE         |     |    |         |         |
| Measurement Collection for MTSI services, see TS |     |    |         |         |
| 26.114 \[30\].                                   |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***qoe-VR-MeasReport-r17***                      | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports NR QoE         |     |    |         |         |
| Measurement Collection for VR services, see TS   |     |    |         |         |
| 26.118 \[31\].                                   |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***ran-VisibleQoE-Streaming-MeasReport-r17***    | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports RAN visible    |     |    |         |         |
| QoE Measurement Collection for streaming         |     |    |         |         |
| services. A UE supporting this feature shall     |     |    |         |         |
| also support *qoe-Streaming-MeasReport-r17.*     |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***ran-VisibleQoE-VR-MeasReport-r17***           | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports RAN visible    |     |    |         |         |
| QoE Measurement Collection for VR services. A UE |     |    |         |         |
| supporting this feature shall also support       |     |    |         |         |
| *qoe-VR-MeasReport-r17.*                         |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***srb5-r18***                                   | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports SRB5 which is  |     |    |         |         |
| a direct SRB between the SN and the UE as        |     |    |         |         |
| specified in TS 37.340 \[7\]. A UE supporting    |     |    |         |         |
| this feature shall also indicate support of      |     |    |         |         |
| *qoe-NRDC-MeasReport-r18*.                       |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***ul-MeasurementReportAppLayer-Seg-r17***       | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports RRC            |     |    |         |         |
| segmentation of the MeasurementReportAppLayer    |     |    |         |         |
| message in UL over SRB4 and SRB5 (if supported), |     |    |         |         |
| as specified in TS 38.331 \[9\].                 |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+