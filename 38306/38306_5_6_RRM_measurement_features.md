## 5.6 RRM measurement features

+-----------------------------------------------------------------------+
| Definitions for feature                                               |
+-----------------------------------------------------------------------+
| **Cell reselection from TN to NTN**                                   |
|                                                                       |
| It is optional for the UE in RRC_IDLE or in RRC_INACTIVE in a TN cell |
| to support the measurement of NTN neighbour cells for cell            |
| reselection based on the information acquired in SIB19 as specified   |
| in TS 38.304 \[21\] and* *in TS 38.133 \[5\]. This feature is only    |
| applicable if the UE supports *nonTerrestrialNetwork-r17*.            |
+-----------------------------------------------------------------------+
| **Enhanced inter-frequency IDLE/INACTIVE measurements for HST FR2**   |
|                                                                       |
| It is optional for UE to support RRM requirement for inter-frequency  |
| measurements in idle and inactive mode to support FR2 high speed up   |
| to 350 km/h, as specified in TS 38.133 \[5\].                         |
|                                                                       |
| A UE supporting this feature shall also indicate support of PC6 in    |
| *ue-PowerClass-v1700*.                                                |
+-----------------------------------------------------------------------+
| **Enhanced RRM requirements for measurements in IDLE and INACTIVE     |
| modes**                                                               |
|                                                                       |
| It is optional for UE to support enhanced RRM requirements for        |
| measurements for NTN bands (FR1 only and FDD only) in                 |
| RRC_IDLE/RRC_INACTIVE as specified in TS 38.133 \[5\]. If UE does not |
| support this feature, other NTN measurement requirements (as          |
| specified in TS 38.133 \[5\], clause 4.2C.2 for RRC_IDLE and clause   |
| 5.1C.2 for RRC_INACTIVE) are applied.                                 |
+-----------------------------------------------------------------------+
| **Enhanced RRM requirements for measurements in IDLE and INACTIVE     |
| modes for ATG**                                                       |
|                                                                       |
| It is optional for the UE in RRC_IDLE/RRC_INACTIVE to support the     |
| enhanced inter-frequency cell re-selection requirements for ATG (as   |
| specified in TS 38.133 \[5\], Table 4.2D.2.4-2). If UE does not       |
| support this feature, other measurement requirements as specified in  |
| TS 38.133 \[5\], Table 4.2D.2.4-1 are applied.                        |
+-----------------------------------------------------------------------+
| **Enhanced RRM requirements for measurements in IDLE and INACTIVE     |
| modes for FR2-NTN**                                                   |
|                                                                       |
| It is optional for UE to support enhanced RRM requirements for        |
| measurements for FDD FR2-NTN bands in RRC_IDLE/RRC_INACTIVE as        |
| specified in TS 38.133 \[5\]. If UE does not support this feature,    |
| other NTN measurement requirements (as specified in TS 38.133 \[5\],  |
| clause 4.2C.2 for RRC_IDLE and clause 5.1C.2 for RRC_INACTIVE) are    |
| applied.                                                              |
+-----------------------------------------------------------------------+
| **High speed inter-frequency IDLE/INACTIVE measurements**             |
|                                                                       |
| It is optional for UE to support high speed inter-frequency           |
| measurements in RRC_IDLE/RRC_INACTIVE as specified in TS 38.133       |
| \[5\].                                                                |
+-----------------------------------------------------------------------+
| **Location-based measurement initiation**                             |
|                                                                       |
| It is optional for the UE in RRC_IDLE/RRC_INACTIVE to support         |
| location based RRM measurements of neighbour cells in NTN             |
| (quasi-)Earth fixed cell as specified in TS 38.304 \[21\].            |
+-----------------------------------------------------------------------+
| **Location-based measurement initiation for NTN Earth-moving cell**   |
|                                                                       |
| It is optional for the UE in RRC_IDLE/RRC_INACTIVE to support         |
| location based RRM measurements of neighbour cells in NTN             |
| Earth-moving cell as specified in TS 38.304 \[21\].                   |
+-----------------------------------------------------------------------+
| **Relaxed measurement**                                               |
|                                                                       |
| It is optional for UE to support relaxed RRM measurements of          |
| neighbour cells in RRC_IDLE/RRC_INACTIVE as specified in TS 38.304    |
| \[21\].                                                               |
+-----------------------------------------------------------------------+
| **Rel-17 relaxed measurement for RRC_IDLE/RRC_INACTIVE**              |
|                                                                       |
| It is optional for (e)RedCap UE to support Rel-17 relaxed RRM         |
| measurements of neighbour cells in RRC_IDLE/RRC_INACTIVE as specified |
| in TS 38.304 \[21\].                                                  |
+-----------------------------------------------------------------------+
| **Skipping TN measurements**                                          |
|                                                                       |
| It is optional for the UE in RRC_IDLE/RRC_INACTIVE to support         |
| skipping the neighbour cell measurements for TN neighbour cells in an |
| area where there is no TN network coverage as specified in TS 38.304  |
| \[21\].                                                               |
+-----------------------------------------------------------------------+
| **SMTC adjustment for RRC_IDLE/RRC_INACTIVE**                         |
|                                                                       |
| It is optional for the UE in RRC_IDLE/RRC_INACTIVE to support SMTC    |
| adjustment based on propagation delay difference between serving and  |
| neighbour cells.                                                      |
+-----------------------------------------------------------------------+
| **Time-based measurement initiation**                                 |
|                                                                       |
| It is optional for the UE in RRC_IDLE/RRC_INACTIVE to support time    |
| based RRM measurements of neighbour cells in NTN quasi-Earth fixed    |
| cell as specified in TS 38.304 \[21\].                                |
+-----------------------------------------------------------------------+
| **Time-based measurement initiation for NTN Earth-moving cell**       |
|                                                                       |
| It is optional for the UE in RRC_IDLE/RRC_INACTIVE to support time    |
| based RRM measurements of neighbour cells in NTN Earth-moving cell as |
| specified in TS 38.304 \[21\].                                        |
+=======================================================================+