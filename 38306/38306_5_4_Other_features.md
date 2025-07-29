## 5.4 Other features

+-----------------------------------------------------------------------+
| Definitions for feature                                               |
+-----------------------------------------------------------------------+
| **Access Category 1 selection assistance information enhancement**    |
|                                                                       |
| It is optional for UE that is configured for delay tolerant service   |
| to support Access Category 1 selection assistance information         |
| enhancement, according to *uac-AC1-SelectAssistInfo-r16* as specified |
| in TS 38.331 \[9\].                                                   |
+-----------------------------------------------------------------------+
| **Barring exemption for emergency call**                              |
|                                                                       |
| It is optional for UE to support the barring exemption for emergency  |
| call, as specified in TS 38.331 \[9\] and in TS 38.304 \[21\].        |
+-----------------------------------------------------------------------+
| **Beam Failure recovery for SDT**                                     |
|                                                                       |
| It is optional for UE to support Beam failure recovery for RA-SDT     |
| initiated for MO-SDT and MT-SDT as specified in TS 38.321 \[8\] and   |
| TS 38.331 \[9\].                                                      |
+-----------------------------------------------------------------------+
| **eCall over IMS**                                                    |
|                                                                       |
| It is optional for UE to support eCall over IMS as specified in TS    |
| 38.331 \[9\].                                                         |
+-----------------------------------------------------------------------+
| **Equivalent SNPNs for cell (re)selection**                           |
|                                                                       |
| It is optional for UE in SNPN access mode to support cell             |
| (re)selection for equivalent SNPNs as specified in TS 38.304 \[21\].  |
+-----------------------------------------------------------------------+
| **HSDN cell reselection**                                             |
|                                                                       |
| It is optional for UE to support HSDN cell reselection priority       |
| handling in RRC_IDLE/RRC_INACTIVE as specified in TS 38.304 \[21\]    |
| and TS 38.331 \[9\].                                                  |
+-----------------------------------------------------------------------+
| **Minimization of service interruption**                              |
|                                                                       |
| It is optional for UE to support minimization of service interruption |
| including reporting to NAS of disaster roaming information for        |
| available PLMNs and Access Barring check for Access Identity 3, as    |
| specified in TS 38.331 \[9\].                                         |
+-----------------------------------------------------------------------+
| **Mobile IAB cell reselection**                                       |
|                                                                       |
| It is optional for UE to support mobile IAB cell reselection priority |
| handling in RRC_IDLE/RRC_INACTIVE, as specified in TS 38.304 \[21\]   |
| and TS 38.331 \[9\].                                                  |
+-----------------------------------------------------------------------+
| **PUCCH repetition on common PUCCH resource**                         |
|                                                                       |
| It is optional for UE to support repetition transmission of PUCCH for |
| Msg4 HARQ-ACK on common PUCCH resource (i.e., PUCCH resource before   |
| dedicated configuration is provided). The UE supports receiving       |
| repetition factor in system information, receiving repetition factor  |
| in DCI format 1_0 with CRC scrambled by TC-RNTI scheduling Msg4       |
| PDSCH, Msg3 to report capability for PUCCH Msg4 HARQ-ACK repetition,  |
| extension of the repetition transmission of PUCCH before dedicated    |
| PUCCH resource configuration and RSRP threshold for Msg4 HARQ-ACK     |
| repetition on common PUCCH resources.                                 |
|                                                                       |
| A UE that includes LCID codepoint = one of {2, 3, 4, 5, 6, 7} for UL  |
| CCCH when the LX field is set to 1 must support this feature.         |
|                                                                       |
| NOTE: This capability is applicable only for bands in Tables 5.2.2-1  |
| and 5.2.3-1 in TS 38.101-5 \[34\] and HAPS operation bands in Clause  |
| 5.2 of TS 38.104 \[35\].                                              |
+-----------------------------------------------------------------------+
| **Random access prioritization for MPS and MCS**                      |
|                                                                       |
| It is optional for UE that is configured for MPS or MCS to support    |
| random access prioritization for Access Identity 1 or 2 as specified  |
| in TS 38.321 \[8\].                                                   |
+-----------------------------------------------------------------------+
| **Random access prioritisation for Slicing**                          |
|                                                                       |
| It is optional for UE to support slice-based prioritisation for       |
| random access as specified in TS 38.321 \[8\].                        |
+-----------------------------------------------------------------------+
| **Random access partitioning for Slicing**                            |
|                                                                       |
| It is optional for UE to support slice-based RACH partitioning as     |
| specified in TS 38.321 \[8\].                                         |
+-----------------------------------------------------------------------+
| **Relaxed cell reselection on GSO**                                   |
|                                                                       |
| It is optional for UE to support the relaxed cell reselection on GSO. |
+-----------------------------------------------------------------------+
| **Support of polarization signalling in NR NTN**                      |
|                                                                       |
| It is optional for UE to support the polarization signalling in NR    |
| NTN comprised of the following functional components:                 |
|                                                                       |
| \- Support polarization indication reception in SIB indicating DL     |
| and/or UL polarization information using respective polarization type |
| parameters to indicate: RHCP or LHCP or linear;                       |
|                                                                       |
| \- Support polarization signalling for target serving cell in         |
| handover command message;                                             |
|                                                                       |
| \- Support polarization signalling for non-serving cell in RRM        |
| measurement configuration.                                            |
+-----------------------------------------------------------------------+
| **TRS occasions from SIB17 for idle mode and RRC_INACTIVE UEs**       |
|                                                                       |
| It is optional for UE to support reading TRS configuration from SIB17 |
| and receiving L1 indication for TRS availability.                     |
|                                                                       |
| NOTE: Receiving L1 indication via DCI format 2_7 is supported only if |
| the UE supports receiving DCI format 2_7.                             |
+-----------------------------------------------------------------------+
| **TRS occasions from SIB17bis for idle mode and RRC_INACTIVE UEs**    |
|                                                                       |
| It is optional for UE to support reading TRS configuration from       |
| SIB17bis and receiving L1 indication for TRS availability.            |
|                                                                       |
| NOTE: Receiving L1 indication via DCI format 2_7 is supported only if |
| the UE supports receiving DCI format 2_7.                             |
+=======================================================================+