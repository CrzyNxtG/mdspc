### 4.2.2 General parameters

+------------------------------------------------------+-----+-----+---------+-------------+
| Definitions for parameters                           | Per | M   | FDD-TDD | **FR1-FR2** |
|                                                      |     |     | DIFF    |             |
|                                                      |     |     |         | DIFF        |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***accessStratumRelease***                           | UE  | Yes | No      | No          |
|                                                      |     |     |         |             |
| Indicates the access stratum release the UE supports |     |     |         |             |
| as specified in TS 38.331 \[9\].                     |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***airToGroundNetwork-r18***                         | UE  | No  | No      | FR1 only    |
|                                                      |     |     |         |             |
| Indicates whether the UE supports air to ground      |     |     |         |             |
| network access. If the UE indicates this capability  |     |     |         |             |
| the UE shall support the following ATG essential     |     |     |         |             |
| features, e.g., acquiring ATG cell specific SIB22    |     |     |         |             |
| and ATG cell specific P-Max.                         |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***crossCarrierSchedulingConfigurationRelease-r17*** | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports using              |     |     |         |             |
| *crossCarrierSchedulingConfigRelease* to release the |     |     |         |             |
| configurations configured by                         |     |     |         |             |
| *crossCarrierSchedulingConfig*.                      |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***delayBudgetReporting***                           | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports delay budget       |     |     |         |             |
| reporting as specified in TS 38.331 \[9\].           |     |     |         |             |
+======================================================+:===:+:===:+:=======:+:===========:+
| ***dl-DedicatedMessageSegmentation-r16***            | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports reception of       |     |     |         |             |
| segmented DL RRC messages.                           |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***drx-Preference-r16***                             | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports providing its      |     |     |         |             |
| preference of a cell group on DRX parameters for     |     |     |         |             |
| power saving in RRC_CONNECTED, as specified in TS    |     |     |         |             |
| 38.331 \[9\].                                        |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***gNB-SideRTT-BasedPDC-r17***                       | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports gNB-side RTT-based |     |     |         |             |
| PDC, as specified in TS 38.300 \[28\]. A UE          |     |     |         |             |
| supporting this feature shall also support           |     |     |         |             |
| *rtt-BasedPDC-CSI-RS-ForTracking-r17* and/or         |     |     |         |             |
| *rtt-BasedPDC-PRS-r17*.                              |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***hardSatelliteSwitchResyncNTN-r18***               | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether UE supports hard satellite switch  |     |     |         |             |
| with re-sync, as specified in TS 38.331 \[9\].       |     |     |         |             |
|                                                      |     |     |         |             |
| A UE supporting this feature shall also indicate the |     |     |         |             |
| support of *nonTerrestrialNetwork-r17*.              |     |     |         |             |
|                                                      |     |     |         |             |
| When UE supports this feature and does not support   |     |     |         |             |
| *softSatelliteSwitchResyncNTN-r18*, this UE is able  |     |     |         |             |
| to perform hard satellite switch with re-sync in a   |     |     |         |             |
| network supporting soft satellite switch with        |     |     |         |             |
| re-sync, as specified in TS 38.331 \[9\].            |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***inactiveState***                                  | UE  | Yes | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports RRC_INACTIVE as    |     |     |         |             |
| specified in TS 38.331 \[9\]. This capability is not |     |     |         |             |
| applicable to NCR-MT.                                |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***inactiveStateNTN-r17***                           | UE  | CY  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports RRC_INACTIVE in    |     |     |         |             |
| NTN as specified in TS 38.331 \[9\]. It is mandated  |     |     |         |             |
| if the UE indicates the support of                   |     |     |         |             |
| *nonTerrestrialNetwork-r17*.                         |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***inactiveStatePO-Determination-r17***              | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports to use the same    |     |     |         |             |
| i_s to determine PO in RRC_INACTIVE state as in      |     |     |         |             |
| RRC_IDLE state.                                      |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***inDeviceCoexInd-r16***                            | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports reporting of       |     |     |         |             |
| affected NR carrier frequencies in IDC assistance    |     |     |         |             |
| information as specified in TS 38.331 \[9\].         |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***inDeviceCoexIndAutonomousDenial-r18***            | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports IDC autonomous     |     |     |         |             |
| denial as specified in TS 38.331 \[9\]. A UE         |     |     |         |             |
| supporting this feature shall also support           |     |     |         |             |
| *inDeviceCoexInd-r16*.                               |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***inDeviceCoexIndFDM-r18***                         | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports reporting of       |     |     |         |             |
| affected NR carrier frequency ranges in IDC          |     |     |         |             |
| assistance information as specified in TS 38.331     |     |     |         |             |
| \[9\]. A UE supporting this feature shall also       |     |     |         |             |
| support *inDeviceCoexInd-r16*.                       |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***inDeviceCoexIndTDM-r18***                         | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports reporting of IDC   |     |     |         |             |
| TDM assistance information as specified in TS 38.331 |     |     |         |             |
| \[9\]. A UE supporting this feature shall also       |     |     |         |             |
| support *inDeviceCoexInd-r16*.                       |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***maxBW-Preference-r16, maxBW-Preference-r17***     | UE  | No  | No      | Yes         |
|                                                      |     |     |         |             |
| Indicates whether the UE supports providing its      |     |     |         | (Incl FR2-2 |
| preference of a cell group on the maximum aggregated |     |     |         | DIFF)       |
| bandwidth for power saving in RRC_CONNECTED, as      |     |     |         |             |
| specified in TS 38.331 \[9\].                        |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***maxCC-Preference-r16***                           | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports providing its      |     |     |         |             |
| preference of a cell group on the maximum number of  |     |     |         |             |
| secondary component carriers for power saving in     |     |     |         |             |
| RRC_CONNECTED, as specified in TS 38.331 \[9\].      |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***maxMIMO-LayerPreference-r16,                      | UE  | No  | No      | Yes         |
| maxMIMO-LayerPreference-r17***                       |     |     |         |             |
|                                                      |     |     |         | (Incl FR2-2 |
| Indicates whether the UE supports providing its      |     |     |         | DIFF)       |
| preference of a cell group on the maximum number of  |     |     |         |             |
| MIMO layers for power saving in RRC_CONNECTED, as    |     |     |         |             |
| specified in TS 38.331 \[9\].                        |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***maxMRB-Add-r17***                                 | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates the additional maximum number of MRBs that |     |     |         |             |
| the UE supports for MBS multicast reception in       |     |     |         |             |
| RRC_CONNECTED as specified in TS 38.331 \[9\].       |     |     |         |             |
|                                                      |     |     |         |             |
| For the UE indicating support of                     |     |     |         |             |
| *multicastInactive-r18*, this capability is also     |     |     |         |             |
| applicable to multicast reception in RRC_INACTIVE,   |     |     |         |             |
| as specified in TS 38.331 \[9\].                     |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***mcgRLF-RecoveryViaSCG-r16***                      | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports recovery from MCG  |     |     |         |             |
| RLF via split SRB1 (if supported) and via SRB3 (if   |     |     |         |             |
| supported) as specified in TS 38.331\[9\].           |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***minSchedulingOffsetPreference-r16***              | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports providing its      |     |     |         |             |
| preference on the minimum scheduling offset for      |     |     |         |             |
| cross-slot scheduling of the cell group for power    |     |     |         |             |
| saving in RRC_CONNECTED, as specified in TS 38.331   |     |     |         |             |
| \[9\].                                               |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***mpsPriorityIndication-r16***                      | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports                    |     |     |         |             |
| *mpsPriorityIndication* on RRC release with redirect |     |     |         |             |
| as defined in TS 38.331 \[9\].                       |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***mt-SDT-r18***                                     | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports initiating MT-SDT  |     |     |         |             |
| procedure via random access procedure with 4-step RA |     |     |         |             |
| type and if UE supports *twoStepRACH-r16*, with      |     |     |         |             |
| 2-step RA type, in response to the reception of      |     |     |         |             |
| MT-SDT indication in paging message, as specified in |     |     |         |             |
| TS 38.331 \[9\].                                     |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***mt-SDT-NTN-r18***                                 | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports initiating MT-SDT  |     |     |         |             |
| procedure in NTN via random access procedure with    |     |     |         |             |
| 4-step RA type and if UE supports *twoStepRACH-r16*  |     |     |         |             |
| for NTN, with 2-step RA type, in response to the     |     |     |         |             |
| reception of MT-SDT indication in paging message, as |     |     |         |             |
| specified in TS 38.331 \[9\]. A UE supporting this   |     |     |         |             |
| feature shall also indicate the support of           |     |     |         |             |
| *nonTerrestrialNetwork-r17*.                         |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***musim-CapabilityRestriction-r18***                | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports providing MUSIM    |     |     |         |             |
| assistance information with temporary capability     |     |     |         |             |
| restriction and capability restriction indication    |     |     |         |             |
| (i.e., *musim-CapRestrictionInd*), as defined in TS  |     |     |         |             |
| 38.331 \[9\]. For a UE supporting                    |     |     |         |             |
| *nr-NeedForGap-Reporting-r16*, this field also       |     |     |         |             |
| indicates UE supports providing                      |     |     |         |             |
| *musim-NeedForGapsInfoNR-r18* with temporary         |     |     |         |             |
| capability restriction as defined in TS 38.331       |     |     |         |             |
| \[9\].                                               |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***musim-GapPreference-r17***                        | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports providing MUSIM    |     |     |         |             |
| assistance information with MUSIM gap preference and |     |     |         |             |
| related MUSIM gap configuration, as defined in       |     |     |         |             |
| TS 38.331 \[9\]. UE supporting this feature supports |     |     |         |             |
| 3 periodic gaps and 1 aperiodic gap.                 |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***musim-GapPriorityPreference-r18***                | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports providing MUSIM    |     |     |         |             |
| assistance information with periodic MUSIM gap       |     |     |         |             |
| priority preference and related periodic MUSIM gap   |     |     |         |             |
| priority configuration, and its preference of        |     |     |         |             |
| keeping all collided MUSIM gaps, as defined in TS    |     |     |         |             |
| 38.331 \[9\]. A UE supporting this feature shall     |     |     |         |             |
| support *musim-GapPreference-r17.*                   |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***musimLeaveConnected-r17***                        | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports providing MUSIM    |     |     |         |             |
| assistance information with indication of leaving    |     |     |         |             |
| RRC_CONNECTED state as defined in TS 38.331 \[9\].   |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***nonTerrestrialNetwork-r17***                      | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports NR NTN access. If  |     |     |         |             |
| the UE indicates this capability the UE shall        |     |     |         |             |
| support the following NTN essential features, e.g.,  |     |     |         |             |
| timer extension in MAC/RLC/PDCP layers and RACH      |     |     |         |             |
| adaptation to handle long RTT, acquiring NTN         |     |     |         |             |
| specific SIB and more than one TAC per PLMN          |     |     |         |             |
| broadcast in one cell.                               |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***ntn-CHO-OnlyLocationTimeTrigger-r18***            | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports conditional        |     |     |         |             |
| handover with only a location-based or a time-based  |     |     |         |             |
| trigger event, i.e. *condEventD1, condEventD2* or    |     |     |         |             |
| *condEventT1*, as specified in TS 38.331 \[9\].      |     |     |         |             |
|                                                      |     |     |         |             |
| A UE supporting this feature shall also indicate the |     |     |         |             |
| support of at least one of                           |     |     |         |             |
| *locationBasedCondHandover-r17* or                   |     |     |         |             |
| *timeBasedCondHandover-r17* or                       |     |     |         |             |
| *locationBasedCondHandoverEMC-r18*.                  |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***ntn-ScenarioSupport-r17***                        | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports the NTN features   |     |     |         |             |
| in GSO scenario or NGSO scenario. If a UE does not   |     |     |         |             |
| include this field but includes                      |     |     |         |             |
| *nonTerrestrialNetwork-r17*, the UE supports the NTN |     |     |         |             |
| features for both GSO and NGSO scenarios, and also   |     |     |         |             |
| supports mobility between GSO and NGSO scenarios.    |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***ntn-VSAT-AntennaType-r18***                       | UE  | No  | No      | FR2 only    |
|                                                      |     |     |         |             |
| Indicates whether a VSAT UE uses electronic or       |     |     |         |             |
| mechanical steering antenna. A UE supporting this    |     |     |         |             |
| feature shall also indicate the support of           |     |     |         |             |
| *nonTerrestrialNetwork-r17*.                         |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***ntn-VSAT-MobilityType-r18***                      | UE  | No  | No      | FR2 only    |
|                                                      |     |     |         |             |
| Indicates whether a VSAT UE is a mobile or fixed     |     |     |         |             |
| VSAT. A UE supporting this feature shall also        |     |     |         |             |
| indicate the support of *nonTerrestrialNetwork-r17*. |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***onDemandSIB-Connected-r16***                      | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports the on-demand      |     |     |         |             |
| request procedure of SIB(s) or posSIB(s) while in    |     |     |         |             |
| RRC_CONNECTED, as specified in TS 38.331 \[9\].      |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***overheatingInd***                                 | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports overheating        |     |     |         |             |
| assistance information.                              |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***pei-SubgroupingSupportBandList-r17***             | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports receiving paging   |     |     |         |             |
| early indication in DCI format 2_7 as specified in   |     |     |         |             |
| TS 38.304 \[21\] for a list of frequency band. The   |     |     |         |             |
| UE shall support UEID based subgrouping for a        |     |     |         |             |
| frequency band if it indicates supporting of paging  |     |     |         |             |
| early indication reception for the frequency band.   |     |     |         |             |
| The set of OFDM symbols within a slot where UE can   |     |     |         |             |
| monitor the PEI PDCCH in Type 2A CSS is the same as  |     |     |         |             |
| the requirement for paging PDCCH in Type 2 CSS for   |     |     |         |             |
| IDLE and INACTIVE mode UEs.                          |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***partialFR2-FallbackRX-Req***                      | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE meets only a partial set of |     |     |         |             |
| the UE minimum receiver requirements for the         |     |     |         |             |
| eligible FR2 fallback band combinations as defined   |     |     |         |             |
| in Clause 4.2 of TS 38.101-2 \[3\] and Clause 4.2 of |     |     |         |             |
| TS 38.101-3 \[4\]. If not indicated, the UE shall    |     |     |         |             |
| meet all the UE minimum receiver requirements for    |     |     |         |             |
| all the FR2 fallback combinations in TS 38.101-2     |     |     |         |             |
| \[3\] and TS 38.101-3 \[4\]. The UE shall support    |     |     |         |             |
| configuration of any of the FR2 fallback band        |     |     |         |             |
| combinations regardless of the presence or the       |     |     |         |             |
| absence of this field.                               |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***ra-InsteadCG-SDT-r18***                           | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports the selection of   |     |     |         |             |
| RACH resources instead of configured grant type 1    |     |     |         |             |
| resource when triggering resume for MO-SDT or MT-SDT |     |     |         |             |
| and next configured grant type 1 resource is too     |     |     |         |             |
| far, as specified in TS 38.331 \[9\].                |     |     |         |             |
|                                                      |     |     |         |             |
| A UE supporting this feature shall also indicate the |     |     |         |             |
| support of *cg-SDT-r17,* or *mt-CG-SDT-r18.*         |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***ra-SDT-r17***                                     | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports initiating MO-SDT  |     |     |         |             |
| procedure (i.e., transmission of data and/or         |     |     |         |             |
| signalling over allowed radio bearers in             |     |     |         |             |
| RRC_INACTIVE state) via Random Access procedure      |     |     |         |             |
| (i.e., RA-SDT) with 4-step RA type and if UE         |     |     |         |             |
| supports *twoStepRACH-r16,* with 2-step RA type, as  |     |     |         |             |
| specified in TS 38.331 \[9\].                        |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***ra-SDT-NTN-r17***                                 | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports initiating MO-SDT  |     |     |         |             |
| procedure (i.e., transmission of data and/or         |     |     |         |             |
| signalling over allowed radio bearers in             |     |     |         |             |
| RRC_INACTIVE state) in NTN via Random Access         |     |     |         |             |
| procedure (i.e., RA-SDT) with 4-step RA type and if  |     |     |         |             |
| UE supports *twoStepRACH-r16* for NTN*,* with 2-step |     |     |         |             |
| RA type, as specified in TS 38.331 \[9\]. A UE       |     |     |         |             |
| supporting this feature shall also indicate the      |     |     |         |             |
| support of *nonTerrestrialNetwork-r17*.              |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***redirectAtResumeByNAS-r16***                      | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports reception of       |     |     |         |             |
| *redirectedCarrierInfo* in an *RRCRelease* message   |     |     |         |             |
| in response to an *RRCResumeRequest* or              |     |     |         |             |
| *RRCResumeRequest1* which is triggered by the NAS    |     |     |         |             |
| layer, as specified in TS 38.331 \[9\].              |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***reducedCP-Latency***                              | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports reduced control    |     |     |         |             |
| plane latency as defined in TS 38.331 \[9\]          |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***referenceTimeProvision-r16***                     | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports provision of       |     |     |         |             |
| referenceTimeInfo in *DLInformationTransfer* message |     |     |         |             |
| and in SIB9 and reference time information           |     |     |         |             |
| preference indication via assistance information, as |     |     |         |             |
| specified in TS 38.331 \[9\].                        |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***releasePreference-r16***                          | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports providing its      |     |     |         |             |
| preference assistance information to transition out  |     |     |         |             |
| of RRC_CONNECTED for power saving, as specified in   |     |     |         |             |
| TS 38.331 \[9\].                                     |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***requirementTypeIndication-r18***                  | UE  | No  | No      | FR1 only    |
|                                                      |     |     |         |             |
| Indicates whether the UE supports network controlled |     |     |         |             |
| indication of the MTTD/MRTD and RF requirements by   |     |     |         |             |
| *nonCollocatedTypeMRDC-r18* for TDD-TDD inter-band   |     |     |         |             |
| EN-DC with overlapping or partially overlapping      |     |     |         |             |
| bands as specified in TS 38.331 \[9\]. This field is |     |     |         |             |
| only applicable to the UE indicating                 |     |     |         |             |
| *interBandMRDC-WithOverlapDL-Bands-r16*.             |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***resumeAfterSDT-Release-r18***                     | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports immediate RRC      |     |     |         |             |
| connection resume procedure triggering after         |     |     |         |             |
| receiving *RRCRelease* message with a                |     |     |         |             |
| *resumeIndication* included during an ongoing SDT    |     |     |         |             |
| procedure, as specified in TS 38.331 \[9\].          |     |     |         |             |
|                                                      |     |     |         |             |
| The UE indicating support of this feature shall also |     |     |         |             |
| support any of *ra-SDT-r17*, *ra-SDT-NTN-r17*,       |     |     |         |             |
| *cg-SDT-r17*, *mt-SDT-r18, mt-SDT-NTN-r18* or        |     |     |         |             |
| *mt-CG-SDT-r18*.                                     |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***resumeWithStoredMCG-SCells-r16***                 | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports not deleting the   |     |     |         |             |
| stored MCG SCell configuration when initiating the   |     |     |         |             |
| resume procedure.                                    |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***resumeWithStoredSCG-r16***                        | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports not deleting the   |     |     |         |             |
| stored SCG configuration when initiating resume. The |     |     |         |             |
| UE which indicates support for                       |     |     |         |             |
| *resumeWithStoredSCG-r16* shall also indicate        |     |     |         |             |
| support for *resumeWithSCG-Config-r16*.              |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***resumeWithSCG-Config-r16***                       | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports (re-)configuration |     |     |         |             |
| of an SCG during the resume procedure.               |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***sib19-Support-r18***                              | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE in RRC_CONNECTED in a TN    |     |     |         |             |
| cell supports reception of SIB19 to acquire          |     |     |         |             |
| satellite assistance information for NTN access. A   |     |     |         |             |
| UE supporting this feature shall also indicate the   |     |     |         |             |
| support of *nonTerrestrialNetwork-r17*.              |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***sliceInfoforCellReselection-r17***                | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports slice-based cell   |     |     |         |             |
| reselection information in SIB and on RRC release    |     |     |         |             |
| for slice-based cell reselection in RRC \_IDLE and   |     |     |         |             |
| RRC INACTIVE as defined in TS 38.304 \[21\].         |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***splitSRB-WithOneUL-Path***                        | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports UL transmission    |     |     |         |             |
| via MCG path and DL reception via either MCG path or |     |     |         |             |
| SCG path, as specified for the split SRB in TS       |     |     |         |             |
| 37.340 \[7\]. The UE shall not set the FDD/TDD       |     |     |         |             |
| specific fields for this capability (i.e. it shall   |     |     |         |             |
| not include this field in                            |     |     |         |             |
| *UE-MRDC-CapabilityAddXDD-Mode*).                    |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***softSatelliteSwitchResyncNTN-r18***               | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether UE supports soft satellite switch  |     |     |         |             |
| with re-sync, as specified in TS 38.331 \[9\].       |     |     |         |             |
|                                                      |     |     |         |             |
| A UE supporting this feature shall also indicate     |     |     |         |             |
| support of *hardSatelliteSwitchResyncNTN-r18.*       |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***splitDRB-withUL-Both-MCG-SCG***                   | UE  | Yes | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports UL transmission    |     |     |         |             |
| via both MCG path and SCG path for the split DRB as  |     |     |         |             |
| specified in TS 37.340 \[7\]. The UE shall not set   |     |     |         |             |
| the FDD/TDD specific fields for this capability      |     |     |         |             |
| (i.e. it shall not include this field in             |     |     |         |             |
| *UE-MRDC-CapabilityAddXDD-Mode*).                    |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***srb3***                                           | UE  | Yes | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports SRB3 which is a    |     |     |         |             |
| direct SRB between the SN and the UE as specified in |     |     |         |             |
| TS 37.340 \[7\]. The UE shall not set the FDD/TDD    |     |     |         |             |
| specific fields for this capability (i.e. it shall   |     |     |         |             |
| not include this field in                            |     |     |         |             |
| *UE-MRDC-CapabilityAddXDD-Mode*). This field is not  |     |     |         |             |
| applied to NE-DC.                                    |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***srb-SDT-NTN-r17***                                | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports the usage of       |     |     |         |             |
| signalling radio bearer SRB2 for MO-SDT (over RA-SDT |     |     |         |             |
| or CG-SDT) or MT-SDT (over RA or CG-SDT) in NTN, as  |     |     |         |             |
| specified in TS 38.331 \[9\].                        |     |     |         |             |
|                                                      |     |     |         |             |
| A UE supporting this feature shall also indicate     |     |     |         |             |
| support of *ra-SDT-NTN-r17*, *cg-SDT-r17*,           |     |     |         |             |
| *mt-SDT-NTN-r18* or *mt-CG-SDT-r18* in NTN bands. A  |     |     |         |             |
| UE supporting this feature shall also indicate the   |     |     |         |             |
| support of *nonTerrestrialNetwork-r17*.              |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***srb-SDT-r17***                                    | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports the usage of       |     |     |         |             |
| signalling radio bearer SRB2 for MO-SDT (over RA-SDT |     |     |         |             |
| or CG-SDT) or MT-SDT (over RA or CG-SDT), as         |     |     |         |             |
| specified in TS 38.331 \[9\].                        |     |     |         |             |
|                                                      |     |     |         |             |
| A UE supporting this feature shall also indicate     |     |     |         |             |
| support of *ra-SDT-r17 cg-SDT-r17*, *mt-SDT-r18* or  |     |     |         |             |
| *mt-CG-SDT-r18*.                                     |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***ul-GapFR2-Pattern-r17***                          | UE  | CY  | No      | FR2 only    |
|                                                      |     |     |         |             |
| Indicates FR2 UL gap pattern(s) supported by the UE  |     |     |         |             |
| for NR SA, for NR-DC without FR2-FR2 band            |     |     |         |             |
| combination, for NE-DC, and for (NG)EN-DC, if UE     |     |     |         |             |
| supports a band in FR2. The leading / leftmost bit   |     |     |         |             |
| (bit 0) corresponds to the FR2 UL gap pattern 0, the |     |     |         |             |
| next bit corresponds to the FR2 UL gap pattern 1, as |     |     |         |             |
| specified in TS 38.133 \[5\] and so on. The UE shall |     |     |         |             |
| set at least one of the bits to 1 for FR2 UL gap     |     |     |         |             |
| pattern 1 and 3, if the UE indicates support for     |     |     |         |             |
| *ul-GapFR2-r17* in an FR2 band.                      |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***ul-RRC-MaxCapaSegments-r17***                     | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports uplink RRC         |     |     |         |             |
| segmentation of *UECapabilityInformation* according  |     |     |         |             |
| to the network indication *rrc-MaxCapaSegAllowed* as |     |     |         |             |
| specified in TS 38.331 \[9\].                        |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***ul-RRC-Segmentation-r16***                        | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether the UE supports uplink RRC         |     |     |         |             |
| segmentation of *UECapabilityInformation* according  |     |     |         |             |
| to the network indication *rrc-SegAllowed* as        |     |     |         |             |
| specified in TS 38.331 \[9\].                        |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+
| ***ul-TrafficInfo-r18***                             | UE  | No  | No      | No          |
|                                                      |     |     |         |             |
| Indicates whether UE supports sending UE assistance  |     |     |         |             |
| information with UL traffic information, including   |     |     |         |             |
| at least one of jitter range, burst arrival time,    |     |     |         |             |
| data burst periodicity and PDU Set and PSI           |     |     |         |             |
| identification, as specified in TS 38.331 \[9\].     |     |     |         |             |
+------------------------------------------------------+-----+-----+---------+-------------+