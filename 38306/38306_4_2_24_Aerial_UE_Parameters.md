### 4.2.24 Aerial UE Parameters

+--------------------------------------------------+-----+----+---------+---------+
| Definitions for parameters                       | Per | M  | FDD-TDD | FR1-FR2 |
|                                                  |     |    | DIFF    | DIFF    |
+==================================================+:===:+:==:+:=======:+:=======:+
| ***aerialUE-Capability-r18***                    | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports aerial UE      |     |    |         |         |
| communication as described in TS 38.300 \[28\]   |     |    |         |         |
| clause 16.18.                                    |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***altitudeMeas-r18***                           | UE  | CY | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports altitude based |     |    |         |         |
| measurement reporting as specified in TS 38.331  |     |    |         |         |
| \[9\]. It is mandatory if the UE supports        |     |    |         |         |
| *aerialUE-Capability-r18*.                       |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***altitudeBasedSSB-ToMeasure-r18***             | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports altitude based |     |    |         |         |
| *ssb-ToMeasure* as specified in TS 38.331 \[9\]. |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***eventAxHy-r18***                              | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports events A3H1,   |     |    |         |         |
| A3H2, A4H1, A4H2, A5H1, and A5H2 as specified in |     |    |         |         |
| TS 38.331 \[9\]. If the UE indicates support of  |     |    |         |         |
| *eventAxHy-r18*, then the UE additionally        |     |    |         |         |
| supports *multipleCellsMeasExtension-r18* for    |     |    |         |         |
| eventA3H1, eventA3H2, eventA4H1, eventA4H2,      |     |    |         |         |
| eventA5H1, and eventA5H2 as specified in TS      |     |    |         |         |
| 38.331 \[9\].                                    |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***flightPathReporting-r18***                    | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports reporting of   |     |    |         |         |
| the flight path plan through the procedure       |     |    |         |         |
| defined in TS 38.331 \[9\].                      |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***flightPathAvailabilityIndicationUAI-r18***    | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports indication of  |     |    |         |         |
| the flight path availability through the UAI     |     |    |         |         |
| message as defined in TS 38.331 \[9\]. If a UE   |     |    |         |         |
| supports this capability, the UE shall also      |     |    |         |         |
| support *flightPathReporting-r18.*               |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***multipleCellsMeasExtension-r18***             | UE  | CY | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports measurement    |     |    |         |         |
| reporting triggered based on a number of cells   |     |    |         |         |
| for eventA3, eventA4, and eventA5 as specified   |     |    |         |         |
| in TS 38.331 \[9\]. It is mandatory if the UE    |     |    |         |         |
| supports *aerialUE-Capability-r18*.              |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***nr-NS-PmaxListAerial-r18***                   | UE  | CY | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports the mechanisms |     |    |         |         |
| defined for cells broadcasting                   |     |    |         |         |
| *nr-NS-PmaxListAerial* and                       |     |    |         |         |
| *frequencyBandListAerial* as specified in TS     |     |    |         |         |
| 38.331 \[9\]. It is mandatory if the UE supports |     |    |         |         |
| *aerialUE-Capability-r18*.                       |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***simulMultiTriggerSingleMeasReport-r18***      | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports, for all the   |     |    |         |         |
| events of the same type for which the            |     |    |         |         |
| measurement reporting was triggered, measurement |     |    |         |         |
| reporting considering only the configuration of  |     |    |         |         |
| the event with the smallest value between the    |     |    |         |         |
| altitude of the UE and the corresponding         |     |    |         |         |
| altitude threshold, as specified in TS 38.331    |     |    |         |         |
| \[9\].                                           |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+
| ***sl-A2X-Service-r18***                         | UE  | No | No      | No      |
|                                                  |     |    |         |         |
| Indicates whether the UE supports A2X service(s) |     |    |         |         |
| which include BRID, DAA or both using A2X        |     |    |         |         |
| communication as specified in TS 38.331 \[9\].   |     |    |         |         |
| This field also indicates whether the UE         |     |    |         |         |
| supports the dedicated resource pools as         |     |    |         |         |
| specified in TS 38.331 for the corresponding A2X |     |    |         |         |
| service(s). A UE supporting this feature shall   |     |    |         |         |
| also support NR sidelink in at least one         |     |    |         |         |
| sidelink band.                                   |     |    |         |         |
+--------------------------------------------------+-----+----+---------+---------+