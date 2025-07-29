### 4.2.10 Inter-RAT parameters

+------------------------------------------------------+-----+-----+---------+
| Definitions for parameters                           | Per | M   | FDD-TDD |
|                                                      |     |     | DIFF    |
+------------------------------------------------------+-----+-----+---------+
| ***mfbi-EUTRA***                                     | UE  | Yes | No      |
|                                                      |     |     |         |
| Indicates whether the UE supports the mechanisms     |     |     |         |
| defined for cells broadcasting multi band            |     |     |         |
| information i.e. comprehending *multiBandInfoList*   |     |     |         |
| defined in TS 36.331 \[17\].                         |     |     |         |
+------------------------------------------------------+-----+-----+---------+
| ***modifiedMPR-BehaviorEUTRA***                      | UE  | No  | No      |
|                                                      |     |     |         |
| *modifiedMPR-Behavior* in 4.3.5.10, TS 36.306        |     |     |         |
| \[15\].                                              |     |     |         |
+------------------------------------------------------+-----+-----+---------+
| ***multiNS-Pmax-EUTRA***                             | UE  | No  | No      |
|                                                      |     |     |         |
| *multiNS-Pmax* defined in 4.3.5.16, TS 36.306        |     |     |         |
| \[15\].                                              |     |     |         |
+------------------------------------------------------+-----+-----+---------+
| ***ne-DC***                                          | UE  | No  | No      |
|                                                      |     |     |         |
| Indicates whether the UE supports NE-DC as specified |     |     |         |
| in TS 37.340 \[7\].                                  |     |     |         |
+------------------------------------------------------+-----+-----+---------+
| ***nr-HO-ToEN-DC-r16***                              | UE  | CY  | No      |
|                                                      |     |     |         |
| Indicates whether the UE supports inter-RAT handover |     |     |         |
| from NR to EN-DC while NR-DC or NE-DC is not         |     |     |         |
| configured as defined in TS 36.306 \[15\]. It is     |     |     |         |
| mandated if the UE supports EN-DC.                   |     |     |         |
+------------------------------------------------------+-----+-----+---------+
| ***rs-SINR-MeasEUTRA***                              | UE  | No  | No      |
|                                                      |     |     |         |
| *rs-SINR-Meas* in 4.3.6.13, TS 36.306 \[15\].        |     |     |         |
+------------------------------------------------------+-----+-----+---------+
| ***rsrqMeasWidebandEUTRA***                          | UE  | No  | Yes     |
|                                                      |     |     |         |
| *rsrqMeasWideband* in 4.3.6.2, TS 36.306 \[15\]. If  |     |     |         |
| this parameter is indicated for FDD and TDD          |     |     |         |
| differently, each indication corresponds to the      |     |     |         |
| duplex mode of measured target cell.                 |     |     |         |
+------------------------------------------------------+-----+-----+---------+
| ***supportedBandListEUTRA***                         | UE  | No  | No      |
|                                                      |     |     |         |
| *supportedBandListEUTRA* defined in 4.3.5.1, TS      |     |     |         |
| 36.306 \[15\].                                       |     |     |         |
+------------------------------------------------------+-----+-----+---------+
| ***supportedBandListUTRA-FDD-r16***                  | UE  | No  | No      |
|                                                      |     |     |         |
| *Radio frequency bands* defined in 4.5.7, TS 25.306  |     |     |         |
| \[20\].                                              |     |     |         |
+======================================================+=====+=====+=========+