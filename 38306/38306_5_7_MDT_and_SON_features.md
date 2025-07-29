## 5.7 MDT and SON features

+-----------------------------------------------------------------------+
| Definitions for feature                                               |
+-----------------------------------------------------------------------+
| **Cross RAT RLF Report**                                              |
|                                                                       |
| It is optional for UE to support the delivery of EUTRA RLF report to  |
| an NR node upon request from the network.                             |
+-----------------------------------------------------------------------+
| **Mobility history information storage**                              |
|                                                                       |
| It is optional for UE to support the storage of PCell mobility        |
| history information and the reporting in *UEInformationResponse*      |
| message as specified in TS 38.331 \[9\].                              |
+-----------------------------------------------------------------------+
| **Radio Link Failure Report for inter-RAT MRO EUTRA**                 |
|                                                                       |
| It is optional for UE to support:                                     |
|                                                                       |
| \- Inclusion of EUTRA CGI and associated TAC, if available, and       |
| otherwise to include the physical cell identity and carrier frequency |
| of the target PCell of the failed handover as *failedPCellId* in      |
| *RLF-Report* upon request from the network as specified in TS 38.331  |
| \[9\].                                                                |
|                                                                       |
| \- Inclusion of EUTRA CGI and associated TAC as *previousPCellId* in  |
| *RLF-Report* as specified in TS 38.331 \[9\].                         |
|                                                                       |
| \- Inclusion of *eutraReconnectCellId* in *reconnectCellId* in the    |
| *RLF-Report* as specified in TS 38.331 \[9\] upon UE has radio link   |
| failure or handover failure and successfully re-connected to an       |
| E-UTRA cell.                                                          |
+-----------------------------------------------------------------------+
| **RACH Partitioning Information**                                     |
|                                                                       |
| It is optional for UE to support the delivery of RACH partitioning    |
| related information via RACH report procedure, upon request from the  |
| network.                                                              |
+-----------------------------------------------------------------------+
| **RLF report after successful fast MCG recovery**                     |
|                                                                       |
| It is optional for UE to support logging *previousPCellId*,           |
| *lastHO-Type*, and *timeConnFailure* when T316 was not running before |
| entering the PCell in which the radio link failure was detected.      |
+-----------------------------------------------------------------------+
| **RLF Report for Fast MCG Recovery**                                  |
|                                                                       |
| It is optional for UE to support the delivery of the Fast MCG         |
| recovery related information in the RLF-Report.                       |
+-----------------------------------------------------------------------+
| **RLF Report for Inter-system HO for Voice Fallback**                 |
|                                                                       |
| It is optional for UE to support the delivery of an explicit          |
| indication in the RLF-report when mobility from NR due to voice       |
| fallback fails.                                                       |
+-----------------------------------------------------------------------+
| **SCG Failure Report for CPAC**                                       |
|                                                                       |
| It is optional for UE to support the delivery of the CPAC related     |
| parameters for MRO in *SCGFailureInformation* message to the network. |
+-----------------------------------------------------------------------+
| **SCG Failure Report for MRO**                                        |
|                                                                       |
| It is optional for UE to support the delivery of the SCG failure      |
| related parameters for MRO in *SCGFailureInformation* message to the  |
| network.                                                              |
+-----------------------------------------------------------------------+
| **SON enhancements for NR-U**                                         |
|                                                                       |
| It is optional for UE to support the delivery of NR-U related         |
| information (FR1 only) in RA-report/SHR/RLF/SPR/SCGFailureInformation |
| report, upon request from the network.                                |
+-----------------------------------------------------------------------+
| **SON Report in SNPN**                                                |
|                                                                       |
| It is optional for UE to support collection and delivery of SON       |
| reports in SNPN. UE is not required to support all SON reports if it  |
| supports collection and delivery of the SON reports in SNPN, it may   |
| support one or more SON report for SNPN.                              |
+-----------------------------------------------------------------------+
| **SpCell ID indication**                                              |
|                                                                       |
| It is optional for UE to support the delivery of the *spCellID-r17*   |
| in the RA-Report, if the RA procedure is performed in a SCell of the  |
| MCG/SCG.                                                              |
+-----------------------------------------------------------------------+
| **Uplink PDCP delay measurements upon MO update**                     |
|                                                                       |
| It is optional for UE to support not resetting the UL PDCP Packet     |
| Average Delay measurement or UL PDCP excess packet delay measurement  |
| when the associated measurement object is modified. A UE supporting   |
| this feature shall also indicate the support of at least one of       |
| *ulPDCP-Delay-r16* and *excessPacketDelay-r17*.                       |
+=======================================================================+