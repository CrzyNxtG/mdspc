### 7.1.1 Timers (Informative)

+-----------+-----------------------------------+----------------------------------------+----------------------------+
| Timer     | Start                             | Stop                                   | At expiry                  |
+===========+===================================+========================================+============================+
| T300      | Upon transmission of              | Upon reception of *RRCSetup* or        | Perform the actions as     |
|           | *RRCSetupRequest.*                | *RRCReject* message, cell              | specified in 5.3.3.7.      |
|           |                                   | re-selection, relay (re)selection or   |                            |
|           |                                   | cell selection by a L2 U2N Remote UE,  |                            |
|           |                                   | and upon abortion of connection        |                            |
|           |                                   | establishment by upper layers.         |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T301      | Upon transmission of              | Upon reception of *RRCReestablishment* | Go to RRC_IDLE             |
|           | *RRCReestabilshmentRequest*       | or *RRCSetup* message as well as when  |                            |
|           |                                   | the selected cell becomes unsuitable   |                            |
|           |                                   | or the (re)selected L2 U2N Relay UE    |                            |
|           |                                   | becomes unsuitable, upon reception of  |                            |
|           |                                   | *NotificationMessageSidelink*          |                            |
|           |                                   | indicating *relayUE-HO* or             |                            |
|           |                                   | *relayUE-CellReselection*.             |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T302      | Upon reception of *RRCReject*     | Upon entering RRC_CONNECTED or         | Inform upper layers about  |
|           | while performing RRC connection   | RRC_IDLE, upon cell re-selection, upon | barring alleviation as     |
|           | establishment or resume, upon     | cell change due to relay (re)selection | specified in 5.3.14.4      |
|           | reception of *RRCRelease* with    | or cell selection by a L2 U2N Remote   |                            |
|           | *waitTime*.                       | UE, and upon reception of *RRCReject*  |                            |
|           |                                   | message.                               |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T304      | Upon reception of                 | Upon successful completion of random   | For T304 of MCG, in case   |
|           | *RRCReconfiguration* message      | access on the corresponding SpCell.    | of the handover from NR or |
|           | including                         |                                        | intra-NR handover, or path |
|           | *reconfigurationWithSync* for the | Upon receiving an indication from      | switch from a L2 U2N Relay |
|           | MCG which does not include        | lower layers of successful completion  | UE to a NR cell, or an LTM |
|           | *sl-PathSwitchConfig*, or upon    | of Rach-less handover, or upon         | cell switch procedure,     |
|           | reception of *RRCReconfiguration* | receiving an indication from lower     | initiate the RRC           |
|           | message including                 | layers of successful completion of an  | re-establishment           |
|           | *reconfigurationWithSync* for the | LTM RACH-less cell switch.             | procedure; In case of      |
|           | SCG not indicated as deactivated  |                                        | handover to NR, perform    |
|           | in the NR or E-UTRA message       | For T304 of SCG, upon SCG release.     | the actions defined in the |
|           | containing the                    |                                        | specifications applicable  |
|           | *RRCReconfiguration* message or   |                                        | for the source RAT. If any |
|           | upon conditional reconfiguration  |                                        | DAPS bearer is configured  |
|           | execution i.e. when applying a    |                                        | and if there is no RLF in  |
|           | stored *RRCReconfiguration*       |                                        | source PCell, initiate the |
|           | message including                 |                                        | failure information        |
|           | *reconfigurationWithSync*.        |                                        | procedure.                 |
|           |                                   |                                        |                            |
|           | Also, for the MCG and SCG upon an |                                        | For T304 of SCG, inform    |
|           | indication from lower layer that  |                                        | network about the          |
|           | an LTM cell switch procedure is   |                                        | reconfiguration with sync  |
|           | triggered and, for the MCG, upon  |                                        | failure by initiating the  |
|           | performing an LTM cell switch     |                                        | SCG failure information    |
|           | procedure following cell          |                                        | procedure as specified in  |
|           | selection performed while timer   |                                        | 5.7.3.                     |
|           | T311 is running.                  |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T310      | Upon detecting physical layer     | Upon receiving N311 consecutive        | If the T310 is kept in     |
|           | problems for the SpCell i.e. upon | in-sync indications from lower layers  | MCG: If AS security is not |
|           | receiving N310 consecutive        | for the SpCell, upon receiving         | activated: go to RRC_IDLE  |
|           | out-of-sync indications from      | RRCReconfiguration with                | else: initiate the MCG     |
|           | lower layers.                     | *reconfigurationWithSync* for that     | failure information        |
|           |                                   | cell group, upon reception of          | procedure as specified in  |
|           |                                   | *MobilityFromNRCommand*, upon the      | 5.7.3b or the connection   |
|           |                                   | reconfiguration of                     | re-establishment procedure |
|           |                                   | *rlf-TimersAndConstant,* upon          | as specified in 5.3.7 or   |
|           |                                   | initiating the connection              | the procedure as specified |
|           |                                   | re-establishment procedure, upon       | in 5.3.10.3 if any DAPS    |
|           |                                   | conditional reconfiguration execution  | bearer is configured.      |
|           |                                   | i.e. when applying a stored            |                            |
|           |                                   | RRCReconfiguration message including   | If the T310 is kept in     |
|           |                                   | *reconfigurationWithSync* for that     | SCG, Inform E-UTRAN/NR     |
|           |                                   | cell group, upon an indication from    | about the SCG radio link   |
|           |                                   | lower layers that an LTM cell switch   | failure by initiating the  |
|           |                                   | procedure is triggered, and upon       | SCG failure information    |
|           |                                   | initiating the MCG failure information | procedure as specified in  |
|           |                                   | procedure.                             | 5.7.3.                     |
|           |                                   |                                        |                            |
|           |                                   | Upon SCG release, if the T310 is kept  |                            |
|           |                                   | in SCG.                                |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T311      | Upon initiating the RRC           | Upon selection of a suitable NR cell,  | Enter RRC_IDLE             |
|           | connection re-establishment       | or upon selection of a suitable L2 U2N |                            |
|           | procedure                         | Relay UE, or a cell using another RAT. |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T312      | If T312 is configured in MCG:     | Upon receiving N311 consecutive        | If the T312 is kept in     |
|           | Upon triggering a measurement     | in-sync indications from lower layers  | MCG, initiate the MCG      |
|           | report for a measurement identity | for the SpCell, receiving              | failure information        |
|           | for which T312 has been           | *RRCReconfiguration* with              | procedure as specified in  |
|           | configured and *useT312* has been | *reconfigurationWithSync* for that     | 5.7.3b or the connection   |
|           | set to true, while T310 in PCell  | cell group, upon reception of          | re-establishment           |
|           | is running.                       | *MobilityFromNRCommand*, upon          | procedure.                 |
|           |                                   | initiating the connection              |                            |
|           | If T312 is configured in SCG and  | re-establishment procedure, upon the   | If the T312 is kept in     |
|           | *useT312* has been set to true:   | reconfiguration of                     | SCG, Inform E-UTRAN/NR     |
|           | Upon triggering a measurement     | *rlf-TimersAndConstant*, upon          | about the SCG radio link   |
|           | report for a measurement identity | initiating the MCG failure information | failure by initiating the  |
|           | for which T312 has been           | procedure, upon conditional            | SCG failure information    |
|           | configured, while T310 in PSCell  | reconfiguration execution i.e. when    | procedure.as specified in  |
|           | is running.                       | applying a stored RRCReconfiguration   | 5.7.3.                     |
|           |                                   | message including                      |                            |
|           |                                   | *reconfigurationWithSync* for that     |                            |
|           |                                   | cell group, upon an indication from    |                            |
|           |                                   | lower layers that an LTM cell switch   |                            |
|           |                                   | procedure is triggered, and upon the   |                            |
|           |                                   | expiry of T310 in corresponding        |                            |
|           |                                   | SpCell.                                |                            |
|           |                                   |                                        |                            |
|           |                                   | Upon SCG release, if the T312 is kept  |                            |
|           |                                   | in SCG                                 |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T316      | Upon transmission of the          | Upon receiving *RRCRelease*,           | Perform the actions as     |
|           | *MCGFailureInformation* message   | *RRCReconfiguration* with              | specified in 5.7.3b.5.     |
|           |                                   | *reconfigurationwithSync* for the      |                            |
|           |                                   | PCell, *MobilityFromNRCommand,* or     |                            |
|           |                                   | upon initiating the re-establishment   |                            |
|           |                                   | procedure                              |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T319      | Upon transmission of              | Upon reception of *RRCResume,*         | Perform the actions as     |
|           | *RRCResumeRequest* or             | *RRCSetup, RRCRelease, RRCRelease*     | specified in 5.3.13.5.     |
|           | *RRCResumeRequest1 when the       | with *suspendConfig* or *RRCReject*    |                            |
|           | resume procedure is not initiated | message, upon cell re-selection or     |                            |
|           | for SDT.*                         | upon relay (re)selection.              |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T319a     | Upon transmission of              | Upon reception of *RRCResume,*         | Perform the actions as     |
|           | *RRCResumeRequest* or             | *RRCSetup, RRCRelease,* *RRCReject*    | specified in 5.3.13.5.     |
|           | *RRCResumeRequest1* when the      | message or upon failure to resume RRC  |                            |
|           | resume procedure is initiated for | connection for SDT as specified in     |                            |
|           | SDT.                              | 5.3.13.5 or upon cell reselection.     |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T320      | Upon reception of *t320* or upon  | Upon entering RRC_CONNECTED, upon      | Discard the cell           |
|           | cell (re)selection to NR from     | reception of *RRCRelease*, when PLMN   | reselection priority       |
|           | another RAT with validity time    | selection or SNPN selection is         | information provided by    |
|           | configured for dedicated          | performed on request by NAS, when the  | dedicated signalling.      |
|           | priorities (in which case the     | UE enters RRC_IDLE from RRC_INACTIVE,  |                            |
|           | remaining validity time is        | or upon cell (re)selection to another  |                            |
|           | applied).                         | RAT (in which case the timer is        |                            |
|           |                                   | carried on to the other RAT).          |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T321      | Upon receiving *measConfig*       | Upon acquiring the information needed  | Initiate the measurement   |
|           | including a *reportConfig* with   | to set all fields of *cgi-info*, upon  | reporting procedure, stop  |
|           | the *reportType* set to           | receiving *measConfig* that includes   | performing the related     |
|           | *reportCGI*                       | removal of the *reportConfig* with the | measurements.              |
|           |                                   | *reportType* set to *reportCGI* and    |                            |
|           |                                   | upon detecting that a cell is not      |                            |
|           |                                   | broadcasting SIB1.                     |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T322      | Upon receiving *measConfig*       | Upon acquiring the SFTD measurement    | Initiate the measurement   |
|           | including *reportConfigNR* with   | results, upon receiving *measConfig*   | reporting procedure, stop  |
|           | the *reportType* set to           | that includes removal of the           | performing the related     |
|           | *reportSFTD* and                  | *reportConfig* with the *reportType*   | measurements*.*            |
|           | *drx-SFTD-NeighMeas* is set to    | set to *reportSFTD*.                   |                            |
|           | *true*.                           |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T325      | Upon reception of *RRCRelease*    | When PLMN selection or SNPN selection  | Stop deprioritisation of   |
|           | message with                      | is performed on request by NAS         | all frequencies or NR      |
|           | *deprioritisationTimer*.          | according to TS 38.304 \[20\].         | signalled by *RRCRelease*  |
|           |                                   |                                        | and discard the stored     |
|           |                                   |                                        | deprioritisation           |
|           |                                   |                                        | request(s)*.*              |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T330      | Upon receiving                    | Upon log volume exceeding the suitable | Perform the actions        |
|           | *LoggedMeasurementConfiguration*  | UE memory, upon initiating the release | specified in 5.5a.1.4      |
|           | message                           | of *LoggedMeasurementConfiguration*    |                            |
|           |                                   | procedure                              |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T331      | Upon receiving *RRCRelease*       | Upon receiving *RRCSetup, RRCResume*,  | Perform the actions as     |
|           | message with *measIdleDuration*   | *RRCRelease* with idle/inactive        | specified in 5.7.8.3.      |
|           |                                   | measurement configuration, upon cell   |                            |
|           |                                   | selection/reselection to a cell that   |                            |
|           |                                   | does not belong to the *validityArea*  |                            |
|           |                                   | (if configured)*,* or upon cell        |                            |
|           |                                   | re-selection to another RAT*.*         |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T342      | Upon transmitting                 | Upon releasing                         | No action.                 |
|           | *UEAssistanceInformation* message | *delayBudgetReportingConfig* during    |                            |
|           | with *DelayBudgetReport*.         | the connection re-establishment/resume |                            |
|           |                                   | procedures, and upon receiving         |                            |
|           |                                   | *delayBudgetReportingConfig* set to    |                            |
|           |                                   | *release.*                             |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T345      | Upon transmitting                 | Upon releasing                         | No action.                 |
|           | *UEAssistanceInformation* message | *overheatingAssistanceConfig* during   |                            |
|           | with *overheatingAssistance*      | the connection re-establishment        |                            |
|           |                                   | procedure, upon initiating the         |                            |
|           |                                   | connection resumption procedure, and   |                            |
|           |                                   | upon receiving                         |                            |
|           |                                   | *overheatingAssistanceConfig* set to   |                            |
|           |                                   | *release.*                             |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346a     | Upon transmitting                 | Upon releasing *drx-PreferenceConfig*  | No action.                 |
| (The UE   | *UEAssistanceInformation* message | during the connection                  |                            |
| maintains | with *drx-Preference*.            | re-establishment/resume procedures,    |                            |
| one       |                                   | upon receiving *drx-PreferenceConfig*  |                            |
| instance  |                                   | set to *release*, or upon performing   |                            |
| of this   |                                   | MR-DC release*.*                       |                            |
| timer per |                                   |                                        |                            |
| cell      |                                   |                                        |                            |
| group)    |                                   |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346b     | Upon transmitting                 | Upon releasing                         | No action.                 |
| (The UE   | *UEAssistanceInformation* message | *maxBW-PreferenceConfig* during the    |                            |
| maintains | with *maxBW-Preference*.          | connection re-establishment/resume     |                            |
| one       |                                   | procedures, upon receiving             |                            |
| instance  |                                   | *maxBW-PreferenceConfig* set to        |                            |
| of this   |                                   | *release*, or upon performing MR-DC    |                            |
| timer per |                                   | release*.*                             |                            |
| cell      |                                   |                                        |                            |
| group)    |                                   |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346c     | Upon transmitting                 | Upon releasing                         | No action.                 |
| (The UE   | *UEAssistanceInformation* message | *maxCC-PreferenceConfig* during the    |                            |
| maintains | with *maxCC-Preference*.          | connection re-establishment/resume     |                            |
| one       |                                   | procedures, upon receiving             |                            |
| instance  |                                   | *maxCC-PreferenceConfig* set to        |                            |
| of this   |                                   | *release*, or upon performing MR-DC    |                            |
| timer per |                                   | release*.*                             |                            |
| cell      |                                   |                                        |                            |
| group)    |                                   |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346d     | Upon transmitting                 | Upon releasing                         | No action.                 |
| (The UE   | *UEAssistanceInformation* message | *maxMIMO-LayerPreferenceConfig* during |                            |
| maintains | with *maxMIMO-LayerPreference*.   | the connection re-establishment/resume |                            |
| one       |                                   | procedures, upon receiving             |                            |
| instance  |                                   | *maxMIMO-LayerPreferenceConfig* set to |                            |
| of this   |                                   | *release*, or upon performing MR-DC    |                            |
| timer per |                                   | release*.*                             |                            |
| cell      |                                   |                                        |                            |
| group)    |                                   |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346e     | Upon transmitting                 | Upon releasing                         | No action.                 |
| (The UE   | *UEAssistanceInformation* message | *minSchedulingOffsetPreferenceConfig*  |                            |
| maintains | with                              | during the connection                  |                            |
| one       | *minSchedulingOffsetPreference*.  | re-establishment/resume procedures,    |                            |
| instance  |                                   | upon receiving                         |                            |
| of this   |                                   | *minSchedulingOffsetPreferenceConfig*  |                            |
| timer per |                                   | set to *release*, or upon performing   |                            |
| cell      |                                   | MR-DC release*.*                       |                            |
| group)    |                                   |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346f     | Upon transmitting                 | Upon releasing                         | No action.                 |
|           | *UEAssistanceInformation* message | *releasePreferenceConfig* during the   |                            |
|           | with *releasePreference*.         | connection re-establishment/resume     |                            |
|           |                                   | procedures, or upon receiving          |                            |
|           |                                   | *releasePreferenceConfig* set to       |                            |
|           |                                   | *release.*                             |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346g     | Upon transmitting                 | Upon receiving *RRCRelease*, or upon   | Perform the actions as     |
|           | *UEAssistanceInformation* message | receiving                              | specified in 5.3.8.6.      |
|           | with *musim-PreferredRRC-State*.  | *musim-LeaveAssistanceConfig* set to   |                            |
|           |                                   | *release*.                             |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346h     | Upon transmitting                 | Upon releasing                         | No action.                 |
|           | *UEAssistanceInformation* message | *musim-GapAssistanceConfig* during the |                            |
|           | with *musim-GapPreferenceList*    | connection re-establishment/resume     |                            |
|           | and/or                            | procedures, or upon receiving          |                            |
|           | *musim-GapPriorityPreferenceList* | *musim-GapAssistanceConfig* set to     |                            |
|           | and/or *musim-GapKeepPreference*  | *release*.                             |                            |
|           | Information.                      |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346i     | Upon transmitting                 | Upon releasing                         | No action.                 |
|           | *UEAssistanceInformation* message | *scg-DeactivationPreferenceConfig*     |                            |
|           | with *scg-DeactivationPreference* | during RRC connection                  |                            |
|           |                                   | re-establishment/resume or upon        |                            |
|           |                                   | receiving                              |                            |
|           |                                   | *scg-DeactivationPreferenceConfig* set |                            |
|           |                                   | to *release*.                          |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346j     | Upon transmitting                 | Upon releasing                         | No action.                 |
| (The UE   | *UEAssistanceInformation* message | *rlm-RelaxationReportingConfig* during |                            |
| maintains | with                              | the connection re-establishment/resume |                            |
| one       | *rlm-RelaxationReportingConfig*.  | procedures, upon receiving             |                            |
| instance  |                                   | *rlm-RelaxationReportingConfig* set to |                            |
| of this   |                                   | *release*, or upon performing MR-DC    |                            |
| timer per |                                   | release*.*                             |                            |
| cell      |                                   |                                        |                            |
| group)    |                                   |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346k     | Upon transmitting                 | Upon releasing                         | No action.                 |
| (The UE   | *UEAssistanceInformation* message | *bfd-RelaxationReportingConfig* during |                            |
| maintains | with                              | the connection re-establishment/resume |                            |
| one       | *bfd-RelaxationReportingConfig*.  | procedures, upon receiving             |                            |
| instance  |                                   | *bfd-RelaxationReportingConfig* set to |                            |
| of this   |                                   | *release*, or upon performing MR-DC    |                            |
| timer per |                                   | release*.*                             |                            |
| cell      |                                   |                                        |                            |
| group)    |                                   |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346l     | Upon transmitting                 | Upon releasing                         | No action.                 |
|           | *UEAssistanceInformation* message | *ul-TrafficInfoReportingConfig* during |                            |
| (The UE   | with *ul-TrafficInfo* for the     | the connection re-establishment/resume |                            |
| maintains | concerned QoS flow.               | procedures, or upon receiving          |                            |
| one       |                                   | *ul-TrafficInfoReportingConfig* set to |                            |
| instance  |                                   | *release.*                             |                            |
| of this   |                                   |                                        |                            |
| timer per |                                   |                                        |                            |
| QoS flow) |                                   |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346m     | Upon transmitting                 | Upon releasing                         | No action.                 |
|           | *UEAssistanceInformation* message | *multiRx-PreferenceReportingConfigFR2* |                            |
|           | with *multiRx-PreferenceFR2*.     | during the connection                  |                            |
|           |                                   | re-establishment/resume procedures,    |                            |
|           |                                   | upon receiving                         |                            |
|           |                                   | *multiRx-PreferenceReportingConfigFR2* |                            |
|           |                                   | set to release.                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T346n     | Upon transmission of MUSIM        | Upon releasing                         | No action.                 |
|           | temporary restriction of          | *musim-CapabilityRestrictionConfig*    |                            |
|           | *musim-CapRestriction* for        | during the connection                  |                            |
|           | affected bands or combination of  | re-establishment/resume procedures, or |                            |
|           | bands and/or avoided band(s) or   | upon receiving                         |                            |
|           | combination of bands.             | *musim-CapabilityRestrictionConfig*    |                            |
|           |                                   | set to *release.*                      |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T348      | Upon transmission of MUSIM        | Upon reception of *RRCReconfiguration* | UE may apply the temporary |
|           | temporary restriction of          | message that does not exceed UE        | UE capability restriction  |
|           | *musim-CapRestriction* for        | temporary capability restriction       | in accordance with the one |
|           | serving cell(s) with capabilities | indicated via *musim-CapRestriction*.  | indicated in the last      |
|           | restricted, release of SCell or   |                                        | transmission of the        |
|           | PSCell or release of SCG.         |                                        | *UEAssistanceInformation*  |
|           |                                   |                                        | message including          |
|           |                                   |                                        | *musim-CapRestriction*. UE |
|           |                                   |                                        | may apply the temporary    |
|           |                                   |                                        | capability restriction     |
|           |                                   |                                        | that SCG is not supported  |
|           |                                   |                                        | if *ServCellIndex* of      |
|           |                                   |                                        | PSCell was included in     |
|           |                                   |                                        | indicated                  |
|           |                                   |                                        | *MUSIM-CellToRelease-r18*. |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T350      | Upon transmitting                 | Upon acquiring the requested SIB(s) or | No action                  |
|           | *DedicatedSIBRequest* message     | posSIB(s), upon releasing              |                            |
|           | with *requestedSIB-List* and/or   | *onDemandSIB-Request* during the       |                            |
|           | *requestedPosSIB-List*.           | connection re-establishment            |                            |
|           |                                   | procedures, upon receiving             |                            |
|           |                                   | *onDemandSIB-Request* set to release,  |                            |
|           |                                   | upon reception of *RRCRelease* or upon |                            |
|           |                                   | successful change of PCell while in    |                            |
|           |                                   | RRC_CONNECTED.                         |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T380      | Upon reception of t380 in         | Upon reception of *RRCResume*,         | Perform the actions as     |
|           | *RRCRelease.*                     | *RRCSetup* or *RRCRelease*.            | specified in 5.3.13.       |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T390      | When access attempt is barred at  | Upon cell (re)selection, upon relay    | Perform the actions as     |
|           | access barring check for an       | (re)selection, upon entering           | specified in 5.3.14.4.     |
|           | Access Category. The UE maintains | RRC_CONNECTED, upon reception of       |                            |
|           | one instance of this timer per    | *RRCReconfiguration* including         |                            |
|           | Access Category.                  | *reconfigurationWithSync*, upon change |                            |
|           |                                   | of PCell while in RRC_CONNECTED, upon  |                            |
|           |                                   | reception of *MobilityFromNRCommand*,  |                            |
|           |                                   | or upon reception of *RRCRelease*.     |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T400      | Upon transmission of              | Upon reception of                      | Perform the Sidelink radio |
|           | RRCReconfigurationSidelink        | RRCReconfigurationFailureSidelink or   | link failure related       |
|           |                                   | RRCReconfigurationCompleteSidelink     | actions as specified in    |
|           |                                   |                                        | 5.8.9.3.                   |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T420      | Upon reception of the             | Upon successfully sending              | Perform the RRC            |
|           | *RRCReconfiguration* message      | *RRCReconfigurationComplete* message   | re-establishment procedure |
|           | including *sl-PathSwitchConfig*   | (i.e., PC5 RLC acknowledgement is      | as specified in 5.3.7.     |
|           | where *sl-IndirectPathMaintain*   | received from target L2 U2N Relay UE)  |                            |
|           | is not included in                |                                        |                            |
|           | *reconfigurationWithSync*         |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T421      | Upon reception of the             | Upon successfully sending              | Perform the Failure        |
|           | *RRCReconfiguration* message      | *RRCReconfigurationComplete* message   | Information Reporting as   |
|           | including                         | (i.e., PC5 RLC acknowledgement is      | specified in 5.7.3c.       |
|           | *sl-IndirectPathAddChange* where  | received from target L2 U2N Relay UE)  |                            |
|           | *sl-IndirectPathMaintain* is not  | if split SRB1 with duplication is      |                            |
|           | included in                       | configured, or upon reception of       |                            |
|           | *reconfigurationWithSync*         | *RRCReconfigurationCompleteSidelink*   |                            |
|           |                                   | if split SRB1 with duplication is not  |                            |
|           |                                   | configured, or upon initiation of      |                            |
|           |                                   | indirect path failure information      |                            |
|           |                                   | procedure.                             |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+
| T430      | Start or restart from the         | Stop T430, if it is running, for the   | Perform the actions as     |
|           | subframe indicated by *epochTime* | source cell upon reception of          | specified in 5.2.2.6.      |
|           | upon reception of *SIB19*, or     | *RRCReconfiguration* message including |                            |
|           | upon reception of                 | *reconfigurationWithSync*, or upon     |                            |
|           | *RRCReconfiguration* message for  | conditional reconfiguration execution  |                            |
|           | the target cell including         | i.e. when applying a stored            |                            |
|           | *reconfigurationWithSync*, or     | *RRCReconfiguration* message including |                            |
|           | upon conditional reconfiguration  | *reconfigurationWithSync,* or upon     |                            |
|           | execution i.e. when applying a    | satellite switch with                  |                            |
|           | stored *RRCReconfiguration*       | resynchronization*.*                   |                            |
|           | message for the target cell       |                                        |                            |
|           | including                         |                                        |                            |
|           | *reconfigurationWithSync,* or     |                                        |                            |
|           | upon satellite switch with        |                                        |                            |
|           | resynchronization*.*              |                                        |                            |
+-----------+-----------------------------------+----------------------------------------+----------------------------+