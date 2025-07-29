## 6.5 Short Message

Short Messages can be transmitted on PDCCH using P-RNTI with or without
associated *Paging* message using Short Message field in DCI format 1_0
(see TS 38.212 \[17\], clause 7.3.1.2.1).

Table 6.5-1 defines Short Messages. Bit 1 is the most significant bit.

Table 6.5-1: Short Messages

+-------+--------------------------------------------------------------+
| Bit   | Short Message                                                |
+=======+==============================================================+
| 1     | ***systemInfoModification***                                 |
|       |                                                              |
|       | If set to 1: indication of a BCCH modification other than    |
|       | *SIB6*, *SIB7*, *SIB8* and *posSIBs*.                        |
+-------+--------------------------------------------------------------+
| 2     | ***etwsAndCmasIndication***                                  |
|       |                                                              |
|       | If set to 1: indication of an ETWS primary notification      |
|       | and/or an ETWS secondary notification and/or a CMAS          |
|       | notification.                                                |
+-------+--------------------------------------------------------------+
| 3     | ***stopPagingMonitoring***                                   |
|       |                                                              |
|       | This bit can be used for only operation with shared spectrum |
|       | channel access and if                                        |
|       | *nrofPDCCH-MonitoringOccasionPerSSB-InPO* is present.        |
|       |                                                              |
|       | If set to 1: indication that the UE may stop monitoring      |
|       | PDCCH occasion(s) for paging in this Paging Occasion as      |
|       | specified in TS 38.304 \[20\], clause 7.1.                   |
+-------+--------------------------------------------------------------+
| 4     | ***systemInfoModification-eDRX***                            |
|       |                                                              |
|       | If set to 1: indication of a BCCH modification other than    |
|       | *SIB6*, *SIB7*, *SIB8* and *posSIB*s. This indication        |
|       | applies only to UEs using IDLE eDRX cycle longer than the    |
|       | BCCH modification period.                                    |
+-------+--------------------------------------------------------------+
| 5 --  | Not used in this release of the specification, and shall be  |
| 8     | ignored by UE if received.                                   |
+-------+--------------------------------------------------------------+