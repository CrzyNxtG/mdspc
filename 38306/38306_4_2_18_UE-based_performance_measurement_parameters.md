### 4.2.18 UE-based performance measurement parameters

+---------------------------------------------------+-----+----+---------+---------+
| Definitions for parameters                        | Per | M  | FDD-TDD | FR1-FR2 |
|                                                   |     |    | DIFF    | DIFF    |
+---------------------------------------------------+-----+----+---------+---------+
| ***barometerMeasReport-r16***                     | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports uncompensated   |     |    |         |         |
| barometeric pressure measurement reporting upon   |     |    |         |         |
| request from the network.                         |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***earlyMeasLog-r17***                            | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports the storage of  |     |    |         |         |
| Early Measurement Logging in logged measurements  |     |    |         |         |
| and the reporting upon request from the network   |     |    |         |         |
| as specified in TS 38.331 \[9\].                  |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***excessPacketDelay-r17***                       | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports the UL PDCP     |     |    |         |         |
| excess packet delay measurement per DRB as        |     |    |         |         |
| specified in TS 38.314 \[26\]. A UE that supports |     |    |         |         |
| the UL PDCP excess packet delay measurement shall |     |    |         |         |
| also support the measurement configuration and    |     |    |         |         |
| reporting as specified in TS 38.331 \[9\].        |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***gnss-Location-r16***                           | UE  | CY | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE is equipped with a GNSS  |     |    |         |         |
| or A-GNSS receiver that may be used to provide    |     |    |         |         |
| detailed location information along with SON,     |     |    |         |         |
| MDT, and NTN related measurements in              |     |    |         |         |
| RRC_CONNECTED, RRC_IDLE and RRC_INACTIVE state. A |     |    |         |         |
| UE shall set this field to *supported* if it      |     |    |         |         |
| indicates the support of                          |     |    |         |         |
| *nonTerrestrialNetwork-r17*.                      |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***immMeasBT-r16***                               | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports Bluetooth       |     |    |         |         |
| measurements in RRC_CONNECTED state.              |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***immMeasWLAN-r16***                             | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports WLAN            |     |    |         |         |
| measurements in RRC_CONNECTED state.              |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***loggedMDT-PNI-NPN-r18***                       | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports Logged MDT for  |     |    |         |         |
| PNI-NPN(s).                                       |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***loggedMDT-SNPN-r18***                          | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports Logged MDT for  |     |    |         |         |
| SNPN(s).                                          |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***loggedMeasBT-r16***                            | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports Bluetooth       |     |    |         |         |
| measurements in RRC_IDLE and RRC_INACTIVE state.  |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***loggedMeasurements-r16***                      | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports logged          |     |    |         |         |
| measurements in RRC_IDLE and RRC_INACTIVE state.  |     |    |         |         |
| A UE that supports logged measurements shall      |     |    |         |         |
| support both periodical logging and               |     |    |         |         |
| event-triggered logging. The minimum memory size  |     |    |         |         |
| of MDT logged measurements is 64KB. For eRedCap   |     |    |         |         |
| UE supporting this feature, the minimum memory    |     |    |         |         |
| size of MDT logged measurements is 16KB.          |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***loggedMeasWLAN-r16***                          | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports WLAN            |     |    |         |         |
| measurements in RRC_IDLE and RRC_INACTIVE state.  |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***multipleCEF-Report-r17***                      | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports the storage and |     |    |         |         |
| delivery of multiple CEF reports upon request     |     |    |         |         |
| from the network as specified in TS 38.331 \[9\]. |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***orientationMeasReport-r16***                   | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports orientation     |     |    |         |         |
| information reporting upon request from the       |     |    |         |         |
| network.                                          |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***sigBasedLogMDT-OverrideProtect-r17***          | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports the override    |     |    |         |         |
| protection of the signalling based logged         |     |    |         |         |
| measurements configured in NR.                    |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***speedMeasReport-r16***                         | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports speed           |     |    |         |         |
| information reporting upon request from the       |     |    |         |         |
| network.                                          |     |    |         |         |
+---------------------------------------------------+-----+----+---------+---------+
| ***ulPDCP-Delay-r16***                            | UE  | No | No      | No      |
|                                                   |     |    |         |         |
| Indicates whether the UE supports UL PDCP Packet  |     |    |         |         |
| Average Delay measurement (as specified in TS     |     |    |         |         |
| 38.314 \[26\]) and reporting in RRC_CONNECTED     |     |    |         |         |
| state.                                            |     |    |         |         |
+===================================================+=====+====+=========+=========+