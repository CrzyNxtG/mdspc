#  Contents {#contents .TT}

Foreword [27](#foreword)

1 Scope [28](#scope)

2 References [28](#references)

3 Definitions, symbols and abbreviations
[31](#definitions-symbols-and-abbreviations)

3.1 Definitions [31](#definitions)

3.2 Abbreviations [34](#abbreviations)

4 General [37](#general)

4.1 Introduction [37](#introduction)

4.2 Architecture [38](#architecture)

4.2.1 UE states and state transitions including inter RAT
[38](#ue-states-and-state-transitions-including-inter-rat)

4.2.2 Signalling radio bearers [41](#signalling-radio-bearers)

4.3 Services [42](#services)

4.3.1 Services provided to upper layers
[42](#services-provided-to-upper-layers)

4.3.2 Services expected from lower layers
[42](#services-expected-from-lower-layers)

4.4 Functions [42](#functions)

5 Procedures [43](#procedures)

5.1 General [43](#general-1)

5.1.1 Introduction [43](#introduction-1)

5.1.2 General requirements [43](#general-requirements)

5.1.3 Requirements for UE in MR-DC [44](#requirements-for-ue-in-mr-dc)

5.2 System information [44](#system-information)

5.2.1 Introduction [44](#introduction-2)

5.2.2 System information acquisition
[45](#system-information-acquisition)

5.2.2.1 General UE requirements [45](#general-ue-requirements)

5.2.2.2 SIB validity and need to (re)-acquire SIB
[46](#sib-validity-and-need-to-re-acquire-sib)

5.2.2.2.1 SIB validity [46](#sib-validity)

5.2.2.2.2 SI change indication and PWS notification
[47](#si-change-indication-and-pws-notification)

5.2.2.3 Acquisition of System Information
[49](#acquisition-of-system-information)

5.2.2.3.1 Acquisition of *MIB* and *SIB1*
[49](#acquisition-of-mib-and-sib1)

5.2.2.3.2 Acquisition of an SI message
[50](#acquisition-of-an-si-message)

5.2.2.3.3 Request for on demand system information
[51](#request-for-on-demand-system-information)

5.2.2.3.3a Request for on demand positioning system information
[53](#a-request-for-on-demand-positioning-system-information)

5.2.2.3.4 Actions related to transmission of *RRCSystemInfoRequest*
message
[55](#actions-related-to-transmission-of-rrcsysteminforequest-message)

5.2.2.3.5 Acquisition of SIB(s) or posSIB(s) in RRC_CONNECTED
[55](#acquisition-of-sibs-or-possibs-in-rrc_connected)

5.2.2.3.6 Actions related to transmission of *DedicatedSIBRequest*
message
[56](#actions-related-to-transmission-of-dedicatedsibrequest-message)

5.2.2.4 Actions upon receipt of System Information
[57](#actions-upon-receipt-of-system-information)

5.2.2.4.1 Actions upon reception of the *MIB*
[57](#actions-upon-reception-of-the-mib)

5.2.2.4.2 Actions upon reception of the *SIB1*
[57](#actions-upon-reception-of-the-sib1)

5.2.2.4.3 Actions upon reception of *SIB2*
[64](#actions-upon-reception-of-sib2)

5.2.2.4.4 Actions upon reception of *SIB3*
[65](#actions-upon-reception-of-sib3)

5.2.2.4.5 Actions upon reception of *SIB4*
[65](#actions-upon-reception-of-sib4)

5.2.2.4.6 Actions upon reception of *SIB5*
[67](#actions-upon-reception-of-sib5)

5.2.2.4.7 Actions upon reception of *SIB6*
[67](#actions-upon-reception-of-sib6)

5.2.2.4.8 Actions upon reception of *SIB7*
[67](#actions-upon-reception-of-sib7)

5.2.2.4.9 Actions upon reception of *SIB8*
[67](#actions-upon-reception-of-sib8)

5.2.2.4.10 Actions upon reception of *SIB9*
[68](#actions-upon-reception-of-sib9)

5.2.2.4.11 Actions upon reception of *SIB10*
[69](#actions-upon-reception-of-sib10)

5.2.2.4.12 Actions upon reception of *SIB11*
[69](#actions-upon-reception-of-sib11)

5.2.2.4.13 Actions upon reception of *SIB12*
[69](#actions-upon-reception-of-sib12)

5.2.2.4.14 Actions upon reception of *SIB13*
[71](#actions-upon-reception-of-sib13)

5.2.2.4.15 Actions upon reception of *SIB14*
[71](#actions-upon-reception-of-sib14)

5.2.2.4.16 Actions upon reception of *SIBpos*
[71](#actions-upon-reception-of-sibpos)

5.2.2.4.17 Actions upon reception of *SIB15*
[71](#actions-upon-reception-of-sib15)

5.2.2.4.18 Actions upon reception of *SIB16*
[71](#actions-upon-reception-of-sib16)

5.2.2.4.19 Actions upon reception of *SIB17*
[71](#actions-upon-reception-of-sib17)

5.2.2.4.19a Actions upon reception of *SIB17bis*
[71](#a-actions-upon-reception-of-sib17bis)

5.2.2.4.20 Actions upon reception of *SIB18*
[72](#actions-upon-reception-of-sib18)

5.2.2.4.21 Actions upon reception of *SIB19*
[72](#actions-upon-reception-of-sib19)

5.2.2.4.22 Actions upon reception of *SIB20*
[72](#actions-upon-reception-of-sib20)

5.2.2.4.23 Actions upon reception of *SIB21*
[72](#actions-upon-reception-of-sib21)

5.2.2.4.24 Actions upon reception of *SIB22*
[72](#actions-upon-reception-of-sib22)

5.2.2.4.25 Actions upon reception of *SIB23* [72](#_Toc193462511)

5.2.2.4.26 Actions upon reception of *SIB24*
[73](#actions-upon-reception-of-sib24)

5.2.2.4.27 Actions upon reception of *SIB25*
[73](#actions-upon-reception-of-sib25)

5.2.2.5 Essential system information missing
[73](#essential-system-information-missing)

5.2.2.6 T430 expiry [73](#t430-expiry)

5.3 Connection control [73](#connection-control)

5.3.1 Introduction [73](#introduction-3)

5.3.1.1 RRC connection control [73](#rrc-connection-control)

5.3.1.2 AS Security [74](#as-security)

5.3.2 Paging [75](#paging)

5.3.2.1 General [75](#general-2)

5.3.2.2 Initiation [76](#initiation)

5.3.2.3 Reception of the *Paging* *message* by the UE or *PagingRecord*
by the L2 U2N Remote UE
[76](#reception-of-the-paging-message-by-the-ue-or-pagingrecord-by-the-l2-u2n-remote-ue)

5.3.3 RRC connection establishment [78](#rrc-connection-establishment)

5.3.3.1 General [78](#general-3)

5.3.3.1a Conditions for establishing RRC Connection for NR sidelink
communication/discovery/V2X sidelink communication/MP operation
[79](#a-conditions-for-establishing-rrc-connection-for-nr-sidelink-communicationdiscoveryv2x-sidelink-communicationmp-operation)

5.3.3.1b Void [80](#b-void)

5.3.3.2 Initiation [80](#initiation-1)

5.3.3.3 Actions related to transmission of *RRCSetupRequest* message
[80](#actions-related-to-transmission-of-rrcsetuprequest-message)

5.3.3.4 Reception of the *RRCSetup* by the UE
[81](#reception-of-the-rrcsetup-by-the-ue)

5.3.3.5 Reception of the *RRCReject* by the UE
[86](#reception-of-the-rrcreject-by-the-ue)

5.3.3.6 Cell re-selection or cell selection or relay (re)selection while
T390, T300 or T302 is running (UE in RRC_IDLE)
[86](#cell-re-selection-or-cell-selection-or-relay-reselection-while-t390-t300-or-t302-is-running-ue-in-rrc_idle)

5.3.3.7 T300 expiry [87](#t300-expiry)

5.3.3.8 Abortion of RRC connection establishment
[89](#abortion-of-rrc-connection-establishment)

5.3.4 Initial AS security activation
[89](#initial-as-security-activation)

5.3.4.1 General [89](#general-4)

5.3.4.2 Initiation [89](#initiation-2)

5.3.4.3 Reception of the *SecurityModeCommand* by the UE
[89](#reception-of-the-securitymodecommand-by-the-ue)

5.3.5 RRC reconfiguration [90](#rrc-reconfiguration)

5.3.5.1 General [90](#general-5)

5.3.5.2 Initiation [92](#initiation-3)

5.3.5.3 Reception of an *RRCReconfiguration* by the UE
[92](#reception-of-an-rrcreconfiguration-by-the-ue)

5.3.5.4 Secondary cell group release
[109](#secondary-cell-group-release)

5.3.5.5 Cell Group configuration [110](#cell-group-configuration)

5.3.5.5.1 General [110](#general-6)

5.3.5.5.2 Reconfiguration with sync [111](#reconfiguration-with-sync)

5.3.5.5.3 RLC bearer release [113](#rlc-bearer-release)

5.3.5.5.4 RLC bearer addition/modification
[114](#rlc-bearer-additionmodification)

5.3.5.5.5 MAC entity configuration [115](#mac-entity-configuration)

5.3.5.5.6 RLF Timers & Constants configuration
[115](#rlf-timers-constants-configuration)

5.3.5.5.7 SpCell Configuration [116](#spcell-configuration)

5.3.5.5.8 SCell Release [117](#scell-release)

5.3.5.5.9 SCell Addition/Modification [117](#scell-additionmodification)

5.3.5.5.10 BH RLC channel release [118](#bh-rlc-channel-release)

5.3.5.5.11 BH RLC channel addition/modification
[118](#bh-rlc-channel-additionmodification)

5.3.5.5.12 Uu Relay RLC channel release
[118](#uu-relay-rlc-channel-release)

5.3.5.5.13 Uu Relay RLC channel addition/modification
[118](#uu-relay-rlc-channel-additionmodification)

5.3.5.5.14 NCR-Fwd configuration [119](#ncr-fwd-configuration)

5.3.5.6 Radio Bearer configuration [119](#radio-bearer-configuration)

5.3.5.6.1 General [119](#general-7)

5.3.5.6.2 SRB release [120](#srb-release)

5.3.5.6.3 SRB addition/modification [120](#srb-additionmodification)

5.3.5.6.4 DRB release [122](#drb-release)

5.3.5.6.5 DRB addition/modification [122](#drb-additionmodification)

5.3.5.6.6 Multicast MRB release [125](#multicast-mrb-release)

5.3.5.6.7 Multicast MRB addition/modification
[125](#multicast-mrb-additionmodification)

5.3.5.7 AS Security key update [126](#as-security-key-update)

5.3.5.8 Reconfiguration failure [127](#reconfiguration-failure)

5.3.5.8.1 Void [127](#void)

5.3.5.8.2 Inability to comply with *RRCReconfiguration*
[127](#inability-to-comply-with-rrcreconfiguration)

5.3.5.8.3 T304 expiry (Reconfiguration with sync Failure) or T420 expiry
(Path switch failure)
[130](#t304-expiry-reconfiguration-with-sync-failure-or-t420-expiry-path-switch-failure)

5.3.5.9 Other configuration [131](#other-configuration)

5.3.5.9a MUSIM gap configuration [136](#a-musim-gap-configuration)

5.3.5.10 MR-DC release [137](#mr-dc-release)

5.3.5.11 Full configuration [138](#full-configuration)

5.3.5.12 BAP configuration [140](#bap-configuration)

5.3.5.12a IAB Other Configuration [140](#a-iab-other-configuration)

5.3.5.12a.1 IP address management [140](#a.1-ip-address-management)

5.3.5.12a.1.1 IP Address Release [140](#a.1.1-ip-address-release)

5.3.5.12a.1.2 IP Address Addition/Modification
[140](#a.1.2-ip-address-additionmodification)

5.3.5.13 Conditional Reconfiguration [142](#conditional-reconfiguration)

5.3.5.13.1 General [142](#general-8)

5.3.5.13.2 Conditional reconfiguration removal
[143](#conditional-reconfiguration-removal)

5.3.5.13.3 Conditional reconfiguration addition/modification
[143](#conditional-reconfiguration-additionmodification)

5.3.5.13.4 Conditional reconfiguration evaluation
[144](#conditional-reconfiguration-evaluation)

5.3.5.13.4a Conditional reconfiguration evaluation of SN initiated
inter-SN CPC for EN-DC
[147](#a-conditional-reconfiguration-evaluation-of-sn-initiated-inter-sn-cpc-for-en-dc)

5.3.5.13.5 Conditional reconfiguration execution
[147](#conditional-reconfiguration-execution)

5.3.5.13.6 Subsequent CPAC reference configuration addition/removal
[148](#subsequent-cpac-reference-configuration-additionremoval)

5.3.5.13.7 sk-Counter configuration addition/modification/removal
[148](#sk-counter-configuration-additionmodificationremoval)

5.3.5.13.8 Subsequent CPAC execution [148](#subsequent-cpac-execution)

5.3.5.13a SCG activation [151](#a-scg-activation)

5.3.5.13b SCG deactivation [152](#b-scg-deactivation)

5.3.5.13b1 SCG activation without SN message
[152](#b1-scg-activation-without-sn-message)

5.3.5.13c FR2 UL gap configuration [153](#c-fr2-ul-gap-configuration)

5.3.5.13d Application layer measurement configuration
[153](#d-application-layer-measurement-configuration)

5.3.5.14 Sidelink dedicated configuration
[155](#sidelink-dedicated-configuration)

5.3.5.15 L2 U2N or U2U Relay UE configuration
[157](#l2-u2n-or-u2u-relay-ue-configuration)

5.3.5.15.1 General [157](#general-9)

5.3.5.15.2 L2 U2N or U2U Remote UE Release
[158](#l2-u2n-or-u2u-remote-ue-release)

5.3.5.15.3 L2 U2N or U2U Remote UE Addition/Modification
[158](#l2-u2n-or-u2u-remote-ue-additionmodification)

5.3.5.16 L2 U2N or U2U Remote UE configuration
[159](#l2-u2n-or-u2u-remote-ue-configuration)

5.3.5.16.1 L2 U2U Relay UE Release [160](#l2-u2u-relay-ue-release)

5.3.5.16.2 L2 U2U Relay UE Addition/Modification
[160](#l2-u2u-relay-ue-additionmodification)

5.3.5.17 MP configuration [160](#mp-configuration)

5.3.5.17.1 Introduction [160](#introduction-4)

5.3.5.17.2 Configuration of SL indirect path
[161](#configuration-of-sl-indirect-path)

5.3.5.17.2.1 General [161](#general-10)

5.3.5.17.2.2 SL indirect path specific configuration
[161](#sl-indirect-path-specific-configuration)

5.3.5.17.2.3 T421 expiry (Indirect path addition/change failure)
[161](#t421-expiry-indirect-path-additionchange-failure)

5.3.5.17.3 Configuration of N3C indirect path
[162](#configuration-of-n3c-indirect-path)

5.3.5.17.3.1 General [162](#general-11)

5.3.5.17.3.2 N3C remote UE configuration
[162](#n3c-remote-ue-configuration)

5.3.5.17.3.2a N3C Indirect path addition/change failure
[162](#a-n3c-indirect-path-additionchange-failure)

5.3.5.17.3.3 N3C relay UE configuration
[162](#n3c-relay-ue-configuration)

5.3.5.17.3.4 Bearer mapping management on N3C indirect path
[163](#bearer-mapping-management-on-n3c-indirect-path)

5.3.5.17.3.4.1 Bearer mapping release [163](#bearer-mapping-release)

5.3.5.17.3.4.2 Bearer mapping addition and modification
[163](#bearer-mapping-addition-and-modification)

5.3.5.18 LTM configuration and execution
[163](#ltm-configuration-and-execution)

5.3.5.18.1 LTM configuration [163](#ltm-configuration)

5.3.5.18.2 LTM candidate configuration release
[164](#ltm-candidate-configuration-release)

5.3.5.18.3 LTM candidate configuration addition/modification
[164](#ltm-candidate-configuration-additionmodification)

5.3.5.18.4 Void [165](#void-1)

5.3.5.18.5 Void [165](#void-2)

5.3.5.18.6 LTM cell switch execution [165](#ltm-cell-switch-execution)

5.3.5.18.7 LTM configuration release [168](#ltm-configuration-release)

5.3.5.19 T348 expiry [168](#t348-expiry)

5.3.6 Counter check [168](#counter-check)

5.3.6.1 General [168](#general-12)

5.3.6.2 Initiation [168](#initiation-4)

5.3.6.3 Reception of the *CounterCheck* message by the UE
[168](#reception-of-the-countercheck-message-by-the-ue)

5.3.7 RRC connection re-establishment
[169](#rrc-connection-re-establishment)

5.3.7.1 General [169](#general-13)

5.3.7.2 Initiation [170](#initiation-5)

5.3.7.3 Actions following cell selection while T311 is running
[174](#actions-following-cell-selection-while-t311-is-running)

5.3.7.3a Actions following relay selection while T311 is running
[176](#a-actions-following-relay-selection-while-t311-is-running)

5.3.7.4 Actions related to transmission of *RRCReestablishmentRequest*
message
[177](#actions-related-to-transmission-of-rrcreestablishmentrequest-message)

5.3.7.5 Reception of the *RRCReestablishment* by the UE
[178](#reception-of-the-rrcreestablishment-by-the-ue)

5.3.7.6 T311 expiry [180](#t311-expiry)

5.3.7.7 T301 expiry or selected cell/L2 U2N Relay UE no longer suitable
[180](#t301-expiry-or-selected-celll2-u2n-relay-ue-no-longer-suitable)

5.3.7.8 Reception of the *RRCSetup* by the UE
[181](#reception-of-the-rrcsetup-by-the-ue-1)

5.3.8 RRC connection release [181](#rrc-connection-release)

5.3.8.1 General [181](#general-14)

5.3.8.2 Initiation [181](#initiation-6)

5.3.8.3 Reception of the *RRCRelease* by the UE
[181](#reception-of-the-rrcrelease-by-the-ue)

5.3.8.4 T320 expiry [187](#t320-expiry)

5.3.8.5 UE actions upon the expiry of *DataInactivityTimer*
[187](#ue-actions-upon-the-expiry-of-datainactivitytimer)

5.3.8.6 T346g expiry [187](#t346g-expiry)

5.3.9 RRC connection release requested by upper layers
[187](#rrc-connection-release-requested-by-upper-layers)

5.3.9.1 General [187](#general-15)

5.3.9.2 Initiation [187](#initiation-7)

5.3.10 Radio link failure related actions
[188](#radio-link-failure-related-actions)

5.3.10.1 Detection of physical layer problems in RRC_CONNECTED
[188](#detection-of-physical-layer-problems-in-rrc_connected)

5.3.10.2 Recovery of physical layer problems
[188](#recovery-of-physical-layer-problems)

5.3.10.3 Detection of radio link failure
[188](#detection-of-radio-link-failure)

5.3.10.4 RLF cause determination [191](#rlf-cause-determination)

5.3.10.5 RLF report content determination
[191](#rlf-report-content-determination)

5.3.11 UE actions upon going to RRC_IDLE
[196](#ue-actions-upon-going-to-rrc_idle)

5.3.12 UE actions upon PUCCH/SRS release request
[198](#ue-actions-upon-pucchsrs-release-request)

5.3.13 RRC connection resume [199](#rrc-connection-resume)

5.3.13.1 General [199](#general-16)

5.3.13.1a Conditions for resuming RRC Connection for NR sidelink
communication/positioning/discovery/V2X sidelink communication
[200](#a-conditions-for-resuming-rrc-connection-for-nr-sidelink-communicationpositioningdiscoveryv2x-sidelink-communication)

5.3.13.1b Conditions for initiating SDT
[201](#b-conditions-for-initiating-sdt)

5.3.13.1c Void [201](#c-void)

5.3.13.1d Conditions for resuming RRC connection for multicast reception
[201](#d-conditions-for-resuming-rrc-connection-for-multicast-reception)

5.3.13.2 Initiation [202](#initiation-8)

5.3.13.3 Actions related to transmission of *RRCResumeRequest* or
*RRCResumeRequest1* message
[206](#actions-related-to-transmission-of-rrcresumerequest-or-rrcresumerequest1-message)

5.3.13.4 Reception of the *RRCResume* by the UE
[208](#reception-of-the-rrcresume-by-the-ue)

5.3.13.5 Handling of failure to resume RRC Connection
[216](#handling-of-failure-to-resume-rrc-connection)

5.3.13.6 Cell re-selection or cell selection or L2 U2N relay
(re)selection while T390, T319 or T302 is running or SDT procedure is
ongoing (UE in RRC_INACTIVE) or SRS transmission in RRC_INACTIVE is
configured
[217](#cell-re-selection-or-cell-selection-or-l2-u2n-relay-reselection-while-t390-t319-or-t302-is-running-or-sdt-procedure-is-ongoing-ue-in-rrc_inactive-or-srs-transmission-in-rrc_inactive-is-configured)

5.3.13.7 Reception of the *RRCSetup* by the UE
[218](#reception-of-the-rrcsetup-by-the-ue-2)

5.3.13.8 RNA update [218](#rna-update)

5.3.13.9 Reception of the *RRCRelease* by the UE
[219](#reception-of-the-rrcrelease-by-the-ue-1)

5.3.13.10 Reception of the *RRCReject* by the UE
[219](#reception-of-the-rrcreject-by-the-ue-1)

5.3.13.11 Inability to comply with *RRCResume*
[219](#inability-to-comply-with-rrcresume)

5.3.13.12 Inter RAT cell reselection [219](#inter-rat-cell-reselection)

5.3.14 Unified Access Control [219](#unified-access-control)

5.3.14.1 General [219](#general-17)

5.3.14.2 Initiation [219](#initiation-9)

5.3.14.3 Void [221](#void-3)

5.3.14.4 T302, T390 expiry or stop (Barring alleviation)
[221](#t302-t390-expiry-or-stop-barring-alleviation)

5.3.14.5 Access barring check [222](#access-barring-check)

5.3.15 RRC connection reject [223](#rrc-connection-reject)

5.3.15.1 Initiation [223](#initiation-10)

5.3.15.2 Reception of the *RRCReject* by the UE
[223](#reception-of-the-rrcreject-by-the-ue-2)

5.4 Inter-RAT mobility [224](#inter-rat-mobility)

5.4.1 Introduction [224](#introduction-5)

5.4.2 Handover to NR [224](#handover-to-nr)

5.4.2.1 General [224](#general-18)

5.4.2.2 Initiation [224](#initiation-11)

5.4.2.3 Reception of the *RRCReconfiguration* by the UE
[224](#reception-of-the-rrcreconfiguration-by-the-ue)

5.4.3 Mobility from NR [225](#mobility-from-nr)

5.4.3.1 General [225](#general-19)

5.4.3.2 Initiation [225](#initiation-12)

5.4.3.3 Reception of the *MobilityFromNRCommand* by the UE
[225](#reception-of-the-mobilityfromnrcommand-by-the-ue)

5.4.3.4 Successful completion of the mobility from NR
[226](#successful-completion-of-the-mobility-from-nr)

5.4.3.5 Mobility from NR failure [227](#mobility-from-nr-failure)

5.5 Measurements [228](#measurements)

5.5.1 Introduction [228](#introduction-6)

5.5.2 Measurement configuration [230](#measurement-configuration)

5.5.2.1 General [230](#general-20)

5.5.2.2 Measurement identity removal
[232](#measurement-identity-removal)

5.5.2.3 Measurement identity addition/modification
[232](#measurement-identity-additionmodification)

5.5.2.4 Measurement object removal [234](#measurement-object-removal)

5.5.2.5 Measurement object addition/modification
[234](#measurement-object-additionmodification)

5.5.2.6 Reporting configuration removal
[236](#reporting-configuration-removal)

5.5.2.7 Reporting configuration addition/modification
[236](#reporting-configuration-additionmodification)

5.5.2.8 Quantity configuration [237](#quantity-configuration)

5.5.2.9 Measurement gap configuration
[237](#measurement-gap-configuration)

5.5.2.10 Reference signal measurement timing configuration
[239](#reference-signal-measurement-timing-configuration)

5.5.2.10a RSSI measurement timing configuration
[240](#a-rssi-measurement-timing-configuration)

5.5.2.11 Measurement gap sharing configuration
[240](#measurement-gap-sharing-configuration)

5.5.2.12 Effective measurement window configuration
[241](#effective-measurement-window-configuration)

5.5.3 Performing measurements [241](#performing-measurements)

5.5.3.1 General [241](#general-21)

5.5.3.2 Layer 3 filtering [247](#layer-3-filtering)

5.5.3.3 Derivation of cell measurement results
[248](#derivation-of-cell-measurement-results)

5.5.3.3a Derivation of layer 3 beam filtered measurement
[249](#a-derivation-of-layer-3-beam-filtered-measurement)

5.5.3.4 Derivation of L2 U2N Relay UE measurement results
[249](#derivation-of-l2-u2n-relay-ue-measurement-results)

5.5.4 Measurement report triggering
[249](#measurement-report-triggering)

5.5.4.1 General [249](#general-22)

5.5.4.2 Event A1 (Serving becomes better than threshold)
[257](#event-a1-serving-becomes-better-than-threshold)

5.5.4.3 Event A2 (Serving becomes worse than threshold)
[258](#event-a2-serving-becomes-worse-than-threshold)

5.5.4.4 Event A3 (Neighbour becomes offset better than SpCell)
[258](#event-a3-neighbour-becomes-offset-better-than-spcell)

5.5.4.5 Event A4 (Neighbour becomes better than threshold)
[259](#event-a4-neighbour-becomes-better-than-threshold)

5.5.4.6 Event A5 (SpCell becomes worse than threshold1 and neighbour
becomes better than threshold2)
[260](#event-a5-spcell-becomes-worse-than-threshold1-and-neighbour-becomes-better-than-threshold2)

5.5.4.7 Event A6 (Neighbour becomes offset better than SCell)
[261](#event-a6-neighbour-becomes-offset-better-than-scell)

5.5.4.8 Event B1 (Inter RAT neighbour becomes better than threshold)
[261](#event-b1-inter-rat-neighbour-becomes-better-than-threshold)

5.5.4.9 Event B2 (PCell becomes worse than threshold1 and inter RAT
neighbour becomes better than threshold2)
[262](#event-b2-pcell-becomes-worse-than-threshold1-and-inter-rat-neighbour-becomes-better-than-threshold2)

5.5.4.10 Event I1 (Interference becomes higher than threshold)
[263](#event-i1-interference-becomes-higher-than-threshold)

5.5.4.11 Event C1 (The NR sidelink channel busy ratio is above a
threshold)
[263](#event-c1-the-nr-sidelink-channel-busy-ratio-is-above-a-threshold)

5.5.4.12 Event C2 (The NR sidelink channel busy ratio is below a
threshold)
[264](#event-c2-the-nr-sidelink-channel-busy-ratio-is-below-a-threshold)

5.5.4.13 Void [264](#void-4)

5.5.4.14 Void [264](#void-5)

5.5.4.15 Event D1 (Distance between UE and referenceLocation1 is above
threshold1 and distance between UE and referenceLocation2 is below
threshold2)
[264](#event-d1-distance-between-ue-and-referencelocation1-is-above-threshold1-and-distance-between-ue-and-referencelocation2-is-below-threshold2)

5.5.4.15a Event D2 (Distance between UE and the serving cell moving
reference location is above threshold1 and distance between UE and a
moving reference location is below threshold2)
[265](#a-event-d2-distance-between-ue-and-the-serving-cell-moving-reference-location-is-above-threshold1-and-distance-between-ue-and-a-moving-reference-location-is-below-threshold2)

5.5.4.16 CondEvent T1 (Time measured at UE is within a duration from
threshold)
[266](#condevent-t1-time-measured-at-ue-is-within-a-duration-from-threshold)

5.5.4.17 Event X1 (Serving L2 U2N Relay UE becomes worse than threshold1
and NR Cell becomes better than threshold2)
[266](#event-x1-serving-l2-u2n-relay-ue-becomes-worse-than-threshold1-and-nr-cell-becomes-better-than-threshold2)

5.5.4.18 Event X2 (Serving L2 U2N Relay UE becomes worse than threshold)
[267](#event-x2-serving-l2-u2n-relay-ue-becomes-worse-than-threshold)

5.5.4.19 Event Y1 (PCell becomes worse than threshold1 and candidate L2
U2N Relay UE becomes better than threshold2)
[268](#event-y1-pcell-becomes-worse-than-threshold1-and-candidate-l2-u2n-relay-ue-becomes-better-than-threshold2)

5.5.4.20 Event Y2 (Candidate L2 U2N Relay UE becomes better than
threshold)
[268](#event-y2-candidate-l2-u2n-relay-ue-becomes-better-than-threshold)

5.5.4.20b Event Z1 (Serving L2 U2N Relay UE becomes worse than
threshold1 and Candidate L2 U2N Relay UE becomes better than threshold2)
[269](#b-event-z1-serving-l2-u2n-relay-ue-becomes-worse-than-threshold1-and-candidate-l2-u2n-relay-ue-becomes-better-than-threshold2)

5.5.4.21 Event H1 (The Aerial UE altitude becomes higher than a
threshold)
[270](#event-h1-the-aerial-ue-altitude-becomes-higher-than-a-threshold)

5.5.4.22 Event H2 (The Aerial UE altitude becomes lower than a
threshold)
[270](#event-h2-the-aerial-ue-altitude-becomes-lower-than-a-threshold)

5.5.4.23 Event A3H1 (Neighbour becomes offset better than SpCell and the
Aerial UE altitude becomes higher than a threshold)
[270](#event-a3h1-neighbour-becomes-offset-better-than-spcell-and-the-aerial-ue-altitude-becomes-higher-than-a-threshold)

5.5.4.24 Event A3H2 (Neighbour becomes offset better than SpCell and the
Aerial UE altitude becomes lower than a threshold)
[271](#event-a3h2-neighbour-becomes-offset-better-than-spcell-and-the-aerial-ue-altitude-becomes-lower-than-a-threshold)

5.5.4.25 Event A4H1 (Neighbour becomes better than threshold1 and the
Aerial UE altitude becomes higher than a threshold2)
[272](#event-a4h1-neighbour-becomes-better-than-threshold1-and-the-aerial-ue-altitude-becomes-higher-than-a-threshold2)

5.5.4.26 Event A4H2 (Neighbour becomes better than threshold1 and the
Aerial UE altitude becomes lower than a threshold2)
[273](#event-a4h2-neighbour-becomes-better-than-threshold1-and-the-aerial-ue-altitude-becomes-lower-than-a-threshold2)

5.5.4.27 Event A5H1 (SpCell becomes worse than threshold1 and neighbour
becomes better than threshold2 and the Aerial UE altitude becomes higher
than a threshold3)
[274](#event-a5h1-spcell-becomes-worse-than-threshold1-and-neighbour-becomes-better-than-threshold2-and-the-aerial-ue-altitude-becomes-higher-than-a-threshold3)

5.5.4.28 Event A5H2 (SpCell becomes worse than threshold1 and neighbour
becomes better than threshold2 and the Aerial UE altitude becomes lower
than a threshold3)
[275](#event-a5h2-spcell-becomes-worse-than-threshold1-and-neighbour-becomes-better-than-threshold2-and-the-aerial-ue-altitude-becomes-lower-than-a-threshold3)

5.5.5 Measurement reporting [277](#measurement-reporting)

5.5.5.1 General [277](#general-23)

5.5.5.2 Reporting of beam measurement information
[286](#reporting-of-beam-measurement-information)

5.5.5.3 Sorting of cell measurement results
[287](#sorting-of-cell-measurement-results)

5.5.6 Location measurement indication
[288](#location-measurement-indication)

5.5.6.1 General [288](#general-24)

5.5.6.2 Initiation [288](#initiation-13)

5.5.6.3 Actions related to transmission of
*LocationMeasurementIndication* message
[289](#actions-related-to-transmission-of-locationmeasurementindication-message)

5.5a Logged Measurements [289](#a-logged-measurements)

5.5a.1 Logged Measurement Configuration
[289](#a.1-logged-measurement-configuration)

5.5a.1.1 General [289](#a.1.1-general)

5.5a.1.2 Initiation [290](#a.1.2-initiation)

5.5a.1.3 Reception of the *LoggedMeasurementConfiguration* by the UE
[290](#a.1.3-reception-of-the-loggedmeasurementconfiguration-by-the-ue)

5.5a.1.4 T330 expiry [290](#a.1.4-t330-expiry)

5.5a.2 Release of Logged Measurement Configuration
[290](#a.2-release-of-logged-measurement-configuration)

5.5a.2.1 General [290](#a.2.1-general)

5.5a.2.2 Initiation [291](#a.2.2-initiation)

5.5a.3 Measurements logging [291](#a.3-measurements-logging)

5.5a.3.1 General [291](#a.3.1-general)

5.5a.3.2 Initiation [291](#a.3.2-initiation)

5.5b Application Layer Measurements in RRC_IDLE/RRC_INACTIVE
[294](#b-application-layer-measurements-in-rrc_idlerrc_inactive)

5.5b.1 Handling of Application Layer Measurements in
RRC_IDLE/RRC_INACTIVE
[294](#b.1-handling-of-application-layer-measurements-in-rrc_idlerrc_inactive)

5.5b.1.1 General [294](#b.1.1-general)

5.5b.1.2 Initiation [294](#b.1.2-initiation)

5.6 UE capabilities [295](#ue-capabilities)

5.6.1 UE capability transfer [295](#ue-capability-transfer)

5.6.1.1 General [295](#general-25)

5.6.1.2 Initiation [295](#initiation-14)

5.6.1.3 Reception of the *UECapabilityEnquiry* by the UE
[295](#reception-of-the-uecapabilityenquiry-by-the-ue)

5.6.1.4 Setting band combinations, feature set combinations and feature
sets supported by the UE
[296](#setting-band-combinations-feature-set-combinations-and-feature-sets-supported-by-the-ue)

5.6.1.5 Void [300](#void-6)

5.7 Other [300](#other)

5.7.1 DL information transfer [300](#dl-information-transfer)

5.7.1.1 General [300](#general-26)

5.7.1.2 Initiation [300](#initiation-15)

5.7.1.3 Reception of the *DLInformationTransfer* by the UE
[300](#reception-of-the-dlinformationtransfer-by-the-ue)

5.7.1a DL information transfer for MR-DC
[301](#a-dl-information-transfer-for-mr-dc)

5.7.1a.1 General [301](#a.1-general)

5.7.1a.2 Initiation [301](#a.2-initiation)

5.7.1a.3 Actions related to reception of *DLInformationTransferMRDC*
message
[301](#a.3-actions-related-to-reception-of-dlinformationtransfermrdc-message)

5.7.2 UL information transfer [302](#ul-information-transfer)

5.7.2.1 General [302](#general-27)

5.7.2.2 Initiation [302](#initiation-16)

5.7.2.3 Actions related to transmission of *ULInformationTransfer*
message
[302](#actions-related-to-transmission-of-ulinformationtransfer-message)

5.7.2.4 Failure to deliver *ULInformationTransfer* message
[302](#failure-to-deliver-ulinformationtransfer-message)

5.7.2a UL information transfer for MR-DC
[303](#a-ul-information-transfer-for-mr-dc)

5.7.2a.1 General [303](#a.1-general-1)

5.7.2a.2 Initiation [303](#a.2-initiation-1)

5.7.2a.3 Actions related to transmission of *ULInformationTransferMRDC*
message
[303](#a.3-actions-related-to-transmission-of-ulinformationtransfermrdc-message)

5.7.2b UL transfer of IRAT information
[303](#b-ul-transfer-of-irat-information)

5.7.2b.1 General [303](#b.1-general)

5.7.2b.2 Initiation [304](#b.2-initiation)

5.7.2b.3 Actions related to transmission of *ULInformationTransferIRAT*
message
[304](#b.3-actions-related-to-transmission-of-ulinformationtransferirat-message)

5.7.3 SCG failure information [304](#scg-failure-information)

5.7.3.1 General [304](#general-28)

5.7.3.2 Initiation [304](#initiation-17)

5.7.3.3 Failure type determination for (NG)EN-DC
[305](#failure-type-determination-for-ngen-dc)

5.7.3.4 Setting the contents of *MeasResultSCG-Failure*
[306](#setting-the-contents-of-measresultscg-failure)

5.7.3.5 Actions related to transmission of *SCGFailureInformation*
message
[307](#actions-related-to-transmission-of-scgfailureinformation-message)

5.7.3a EUTRA SCG failure information
[309](#a-eutra-scg-failure-information)

5.7.3a.1 General [309](#a.1-general-2)

5.7.3a.2 Initiation [310](#a.2-initiation-2)

5.7.3a.3 Actions related to transmission of *SCGFailureInformationEUTRA*
message
[310](#a.3-actions-related-to-transmission-of-scgfailureinformationeutra-message)

5.7.3b MCG failure information [310](#b-mcg-failure-information)

5.7.3b.1 General [310](#b.1-general-1)

5.7.3b.2 Initiation [310](#b.2-initiation-1)

5.7.3b.3 Failure type determination
[311](#b.3-failure-type-determination)

5.7.3b.4 Actions related to transmission of *MCGFailureInformation*
message
[311](#b.4-actions-related-to-transmission-of-mcgfailureinformation-message)

5.7.3b.5 T316 expiry [313](#b.5-t316-expiry)

5.7.3c Indirect path failure information
[313](#c-indirect-path-failure-information)

5.7.3c.1 General [313](#c.1-general)

5.7.3c.2 Initiation [314](#c.2-initiation)

5.7.3c.3 Failure type determination
[314](#c.3-failure-type-determination)

5.7.3c.4 Actions related to transmission of
*IndirectPathFailureInformation* message
[315](#c.4-actions-related-to-transmission-of-indirectpathfailureinformation-message)

5.7.4 UE Assistance Information [315](#ue-assistance-information)

5.7.4.1 General [315](#general-29)

5.7.4.2 Initiation [316](#initiation-18)

5.7.4.3 Actions related to transmission of *UEAssistanceInformation*
message
[325](#actions-related-to-transmission-of-ueassistanceinformation-message)

5.7.4.3a Setting the contents of *OverheatingAssistance* IE
[337](#a-setting-the-contents-of-overheatingassistance-ie)

5.7.4.4 Relaxed measurement criterion for a stationary (e)RedCap UE
[338](#relaxed-measurement-criterion-for-a-stationary-eredcap-ue)

5.7.4a Void [339](#a-void)

5.7.5 Failure information [339](#failure-information)

5.7.5.1 General [339](#general-30)

5.7.5.2 Initiation [339](#initiation-19)

5.7.5.3 Actions related to transmission of *FailureInformation* message
[339](#actions-related-to-transmission-of-failureinformation-message)

5.7.6 DL message segment transfer [340](#dl-message-segment-transfer)

5.7.6.1 General [340](#general-31)

5.7.6.2 Initiation [340](#initiation-20)

5.7.6.3 Reception of *DLDedicatedMessageSegment* by the UE
[340](#reception-of-dldedicatedmessagesegment-by-the-ue)

5.7.7 UL message segment transfer [340](#ul-message-segment-transfer)

5.7.7.1 General [340](#general-32)

5.7.7.2 Initiation [340](#initiation-21)

5.7.7.3 Actions related to transmission of *ULDedicatedMessageSegment*
message
[341](#actions-related-to-transmission-of-uldedicatedmessagesegment-message)

5.7.8 Idle/inactive Measurements [341](#idleinactive-measurements)

5.7.8.1 General [341](#general-33)

5.7.8.1a Measurement configuration [341](#a-measurement-configuration)

5.7.8.1b Measurement configuration (reselection measurements)
[342](#b-measurement-configuration-reselection-measurements)

5.7.8.2 Void [343](#void-7)

5.7.8.2a Performing measurements [343](#a-performing-measurements)

5.7.8.3 T331 expiry or stop [346](#t331-expiry-or-stop)

5.7.8.4 Cell re-selection or cell selection while T331 is running
[346](#cell-re-selection-or-cell-selection-while-t331-is-running)

5.7.9 Mobility history information [346](#mobility-history-information)

5.7.9.1 General [346](#general-34)

5.7.9.2 Initiation [346](#initiation-22)

5.7.9.3 Release of Mobility History Information
[350](#release-of-mobility-history-information)

5.7.10 UE Information [350](#ue-information)

5.7.10.1 General [350](#general-35)

5.7.10.2 Initiation [350](#initiation-23)

5.7.10.3 Reception of the *UEInformationRequest* message
[350](#reception-of-the-ueinformationrequest-message)

5.7.10.4 Actions for the Random Access report determination
[355](#actions-for-the-random-access-report-determination)

5.7.10.5 RA information determination
[357](#ra-information-determination)

5.7.10.6 Actions for the successful handover report determination
[361](#actions-for-the-successful-handover-report-determination)

5.7.10.7 Actions for the successful PSCell change or addition report
determination
[365](#actions-for-the-successful-pscell-change-or-addition-report-determination)

5.7.11 Void [368](#void-8)

5.7.12 IAB Other Information [368](#iab-other-information)

5.7.12.1 General [368](#general-36)

5.7.12.2 Initiation [368](#initiation-24)

5.7.12.3 Actions related to transmission of *IABOtherInformation*
message
[368](#actions-related-to-transmission-of-iabotherinformation-message)

5.7.13 RLM/BFD relaxation [370](#rlmbfd-relaxation)

5.7.13.0 General [370](#general-37)

5.7.13.1 Relaxed measurement criterion for low mobility
[370](#relaxed-measurement-criterion-for-low-mobility)

5.7.13.2 Relaxed measurement criterion for good serving cell quality
[370](#relaxed-measurement-criterion-for-good-serving-cell-quality)

5.7.14 UE Positioning Assistance Information
[371](#ue-positioning-assistance-information)

5.7.14.1 General [371](#general-38)

5.7.14.2 Initiation [371](#initiation-25)

5.7.14.3 Actions related to transmission of
*UEPositioningAssistanceInfo* message
[371](#actions-related-to-transmission-of-uepositioningassistanceinfo-message)

5.7.15 Void [372](#void-9)

5.7.16 Application layer measurement reporting [372](#_Toc46480779)

5.7.16.1 General [372](#_Toc20487057)

5.7.16.2 Initiation [372](#_Toc20487058)

5.7.17 Derivation of pathloss reference for TA validation of SRS for
Positioning transmission and CG-SDT in RRC_INACTIVE
[374](#derivation-of-pathloss-reference-for-ta-validation-of-srs-for-positioning-transmission-and-cg-sdt-in-rrc_inactive)

5.7.18 Void [375](#void-10)

5.7.19 Satellite switch with resynchronization
[375](#satellite-switch-with-resynchronization)

5.7.20 Actions related to Transmission of SRS for Positioning in a
validity area in RRC_INACTIVE
[375](#actions-related-to-transmission-of-srs-for-positioning-in-a-validity-area-in-rrc_inactive)

5.8 Sidelink [376](#sidelink)

5.8.1 General [376](#general-39)

5.8.2 Conditions for NR sidelink communication/discovery/positioning
operation
[376](#conditions-for-nr-sidelink-communicationdiscoverypositioning-operation)

5.8.3 Sidelink UE information for NR sidelink
communication/discovery/positioning
[377](#sidelink-ue-information-for-nr-sidelink-communicationdiscoverypositioning)

5.8.3.1 General [377](#general-40)

5.8.3.2 Initiation [378](#initiation-26)

5.8.3.3 Actions related to transmission of *SidelinkUEInformationNR*
message
[384](#actions-related-to-transmission-of-sidelinkueinformationnr-message)

5.8.4 Void [391](#void-11)

5.8.5 Sidelink synchronisation information transmission for NR sidelink
communication/discovery/positioning
[391](#sidelink-synchronisation-information-transmission-for-nr-sidelink-communicationdiscoverypositioning)

5.8.5.1 General [391](#general-41)

5.8.5.2 Initiation [392](#initiation-27)

5.8.5.3 Transmission of SLSS [393](#transmission-of-slss)

5.8.5a Sidelink synchronisation information transmission for V2X
sidelink communication
[394](#a-sidelink-synchronisation-information-transmission-for-v2x-sidelink-communication)

5.8.5a.1 General [394](#a.1-general-3)

5.8.5a.2 Initiation [394](#a.2-initiation-3)

5.8.6 Sidelink synchronisation reference
[395](#sidelink-synchronisation-reference)

5.8.6.1 General [395](#general-42)

5.8.6.2 Selection and reselection of synchronisation reference
[395](#selection-and-reselection-of-synchronisation-reference)

5.8.6.2a Sidelink synchronization reference priority group order
[396](#a-sidelink-synchronization-reference-priority-group-order)

5.8.6.2b Sidelink synchronization reference search
[397](#b-sidelink-synchronization-reference-search)

5.8.6.3 Sidelink communication transmission reference cell selection
[398](#sidelink-communication-transmission-reference-cell-selection)

5.8.7 Sidelink communication reception
[398](#sidelink-communication-reception)

5.8.8 Sidelink communication transmission
[399](#sidelink-communication-transmission)

5.8.9 Sidelink RRC procedure [402](#sidelink-rrc-procedure)

5.8.9.1 Sidelink RRC reconfiguration
[402](#sidelink-rrc-reconfiguration)

5.8.9.1.1 General [402](#general-43)

5.8.9.1.2 Actions related to transmission of
*RRCReconfigurationSidelink* message
[403](#actions-related-to-transmission-of-rrcreconfigurationsidelink-message)

5.8.9.1.3 Reception of an *RRCReconfigurationSidelink* by the UE
[406](#reception-of-an-rrcreconfigurationsidelink-by-the-ue)

5.8.9.1.4 Void [409](#void-12)

5.8.9.1.5 Void [409](#void-13)

5.8.9.1.6 Void [409](#void-14)

5.8.9.1.7 Void [409](#void-15)

5.8.9.1.8 Reception of an *RRCReconfigurationFailureSidelink* by the UE
[409](#reception-of-an-rrcreconfigurationfailuresidelink-by-the-ue)

5.8.9.1.9 Reception of an *RRCReconfigurationCompleteSidelink* by the UE
[409](#reception-of-an-rrcreconfigurationcompletesidelink-by-the-ue)

5.8.9.1.10 Sidelink reset configuration [409](#_Toc193462918)

5.8.9.1a Sidelink radio bearer management
[409](#a-sidelink-radio-bearer-management)

5.8.9.1a.1 Sidelink DRB release [409](#a.1-sidelink-drb-release)

5.8.9.1a.2 Sidelink DRB addition/modification
[411](#a.2-sidelink-drb-additionmodification)

5.8.9.1a.3 Sidelink SRB release [413](#a.3-sidelink-srb-release)

5.8.9.1a.4 Sidelink SRB addition [413](#a.4-sidelink-srb-addition)

5.8.9.1a.5 Additional Sidelink RLC Bearer release
[414](#a.5-additional-sidelink-rlc-bearer-release)

5.8.9.1a.5.1 Additional Sidelink RLC Bearer release conditions
[414](#a.5.1-additional-sidelink-rlc-bearer-release-conditions)

5.8.9.1a.5.2 Additional Sidelink RLC Bearer release operation
[414](#a.5.2-additional-sidelink-rlc-bearer-release-operation)

5.8.9.1a.6 Additional Sidelink RLC Bearer addition/modification
[415](#a.6-additional-sidelink-rlc-bearer-additionmodification)

5.8.9.1a.6.1 Additional Sidelink RLC Bearer addition/modification
conditions
[415](#a.6.1-additional-sidelink-rlc-bearer-additionmodification-conditions)

5.8.9.1a.6.2 Additional Sidelink RLC Bearer addition/modification
operation
[415](#a.6.2-additional-sidelink-rlc-bearer-additionmodification-operation)

5.8.9.1b Sidelink Carrier Configuration
[417](#b-sidelink-carrier-configuration)

5.8.9.1b.1 Sidelink Carrier Release [417](#b.1-sidelink-carrier-release)

5.8.9.1b.1.1 Sidelink Carrier Release Condition
[417](#b.1.1-sidelink-carrier-release-condition)

5.8.9.1b.2 Sidelink Carrier Addition
[417](#b.2-sidelink-carrier-addition)

5.8.9.1b.2.1 Sidelink Carrier Addition Condition
[417](#b.2.1-sidelink-carrier-addition-condition)

5.8.9.2 Sidelink UE capability transfer
[418](#sidelink-ue-capability-transfer)

5.8.9.2.1 General [418](#general-44)

5.8.9.2.2 Initiation [418](#initiation-28)

5.8.9.2.3 Actions related to transmission of the
*UECapabilityEnquirySidelink* by the UE
[418](#actions-related-to-transmission-of-the-uecapabilityenquirysidelink-by-the-ue)

5.8.9.2.4 Actions related to reception of the
*UECapabilityEnquirySidelink* by the UE
[419](#actions-related-to-reception-of-the-uecapabilityenquirysidelink-by-the-ue)

5.8.9.3 Sidelink radio link failure related actions
[419](#sidelink-radio-link-failure-related-actions)

5.8.9.3a End-to-end PC5 connection failure related actions performed by
L2 U2U Remote UE
[420](#a-end-to-end-pc5-connection-failure-related-actions-performed-by-l2-u2u-remote-ue)

5.8.9.3b End-to-end PC5 connection failure/release related actions
performed by L2 U2U Relay UE
[421](#b-end-to-end-pc5-connection-failurerelease-related-actions-performed-by-l2-u2u-relay-ue)

5.8.9.4 Sidelink common control information
[421](#sidelink-common-control-information)

5.8.9.4.1 General [421](#general-45)

5.8.9.4.2 Actions related to reception of
*MasterInformationBlockSidelink* message
[421](#actions-related-to-reception-of-masterinformationblocksidelink-message)

5.8.9.4.3 Transmission of *MasterInformationBlockSidelink* message
[421](#transmission-of-masterinformationblocksidelink-message)

5.8.9.5 Actions related to PC5-RRC connection release requested by upper
layers
[423](#actions-related-to-pc5-rrc-connection-release-requested-by-upper-layers)

5.8.9.5a Actions related to end-to-end PC5-RRC connection release
performed by L2 U2U Remote UE
[423](#a-actions-related-to-end-to-end-pc5-rrc-connection-release-performed-by-l2-u2u-remote-ue)

5.8.9.6 Sidelink UE assistance information
[424](#sidelink-ue-assistance-information)

5.8.9.6.1 General [424](#general-46)

5.8.9.6.2 Initiation [424](#initiation-29)

5.8.9.6.3 Actions related to reception of
*UEAssistanceInformationSidelink* message
[424](#actions-related-to-reception-of-ueassistanceinformationsidelink-message)

5.8.9.7 PC5 Relay RLC channel management for L2 U2N or U2U relay
[424](#pc5-relay-rlc-channel-management-for-l2-u2n-or-u2u-relay)

5.8.9.7.0 Deriviation of PC5 Relay RLC channel configuration
[424](#deriviation-of-pc5-relay-rlc-channel-configuration)

5.8.9.7.1 PC5 Relay RLC channel release
[425](#pc5-relay-rlc-channel-release)

5.8.9.7.2 PC5 Relay RLC channel addition/modification
[425](#pc5-relay-rlc-channel-additionmodification)

5.8.9.8 Remote UE information [426](#remote-ue-information)

5.8.9.8.1 General [426](#general-47)

5.8.9.8.2 Actions related to transmission of
*RemoteUEInformationSidelink* message
[426](#actions-related-to-transmission-of-remoteueinformationsidelink-message)

5.8.9.8.3 Reception of *RemoteUEInformationSidelink* message by the L2
U2N/U2U Relay UE
[428](#reception-of-remoteueinformationsidelink-message-by-the-l2-u2nu2u-relay-ue)

5.8.9.9 Uu message transfer in sidelink
[429](#uu-message-transfer-in-sidelink)

5.8.9.9.1 General [429](#general-48)

5.8.9.9.2 Actions related to transmission of *UuMessageTransferSidelink*
message
[429](#actions-related-to-transmission-of-uumessagetransfersidelink-message)

5.8.9.9.3 Reception of the *UuMessageTransferSidelink*
[430](#reception-of-the-uumessagetransfersidelink)

5.8.9.10 Notification Message [430](#notification-message)

5.8.9.10.1 General [430](#general-49)

5.8.9.10.2 Initiation [430](#initiation-30)

5.8.9.10.3 Actions related to transmission of
*NotificationMessageSidelink* message
[431](#actions-related-to-transmission-of-notificationmessagesidelink-message)

5.8.9.10.4 Actions related to reception of *NotificationMessageSidelink*
message
[431](#actions-related-to-reception-of-notificationmessagesidelink-message)

5.8.9.11 UE information transfer on sidelink
[432](#ue-information-transfer-on-sidelink)

5.8.9.11.1 General [432](#general-50)

5.8.9.11.2 Actions related to transmission of the
*UEInformationRequestSidelink* by the UE
[432](#actions-related-to-transmission-of-the-ueinformationrequestsidelink-by-the-ue)

5.8.9.11.3 Actions related to reception of the
*UEInformationRequestSidelink* by the UE
[433](#actions-related-to-reception-of-the-ueinformationrequestsidelink-by-the-ue)

5.8.9.11.4 Actions related to reception of the
*UEInformationResponseSidelink* by the UE
[433](#actions-related-to-reception-of-the-ueinformationresponsesidelink-by-the-ue)

5.8.10 Sidelink measurement [434](#sidelink-measurement)

5.8.10.1 Introduction [434](#introduction-7)

5.8.10.2 Sidelink measurement configuration
[434](#sidelink-measurement-configuration)

5.8.10.2.1 General [434](#general-51)

5.8.10.2.2 Sidelink measurement identity removal
[435](#sidelink-measurement-identity-removal)

5.8.10.2.3 Sidelink measurement identity addition/modification
[435](#sidelink-measurement-identity-additionmodification)

5.8.10.2.4 Sidelink measurement object removal
[435](#sidelink-measurement-object-removal)

5.8.10.2.5 Sidelink measurement object addition/modification
[436](#sidelink-measurement-object-additionmodification)

5.8.10.2.6 Sidelink reporting configuration removal
[436](#sidelink-reporting-configuration-removal)

5.8.10.2.7 Sidelink reporting configuration addition/modification
[436](#sidelink-reporting-configuration-additionmodification)

5.8.10.2.8 Sidelink quantity configuration
[437](#sidelink-quantity-configuration)

5.8.10.3 Performing NR sidelink measurements
[437](#performing-nr-sidelink-measurements)

5.8.10.3.1 General [437](#general-52)

5.8.10.3.2 Derivation of NR sidelink measurement results
[437](#derivation-of-nr-sidelink-measurement-results)

5.8.10.4 Sidelink measurement report triggering
[438](#sidelink-measurement-report-triggering)

5.8.10.4.1 General [438](#general-53)

5.8.10.4.2 Event S1 (Serving becomes better than threshold)
[439](#event-s1-serving-becomes-better-than-threshold)

5.8.10.4.3 Event S2 (Serving becomes worse than threshold)
[439](#event-s2-serving-becomes-worse-than-threshold)

5.8.10.5 Sidelink measurement reporting
[440](#sidelink-measurement-reporting)

5.8.10.5.1 General [440](#general-54)

5.8.11 Zone identity calculation [440](#zone-identity-calculation)

5.8.12 DFN derivation from GNSS [441](#dfn-derivation-from-gnss)

5.8.13 NR sidelink discovery [441](#nr-sidelink-discovery)

5.8.13.1 General [441](#general-55)

5.8.13.2 NR sidelink discovery monitoring
[441](#nr-sidelink-discovery-monitoring)

5.8.13.3 NR sidelink discovery transmission
[442](#nr-sidelink-discovery-transmission)

5.8.14 NR sidelink U2N Relay UE operation
[446](#nr-sidelink-u2n-relay-ue-operation)

5.8.14.1 General [446](#general-56)

5.8.14.2 NR sidelink U2N Relay UE threshold conditions
[446](#_Toc193463003)

5.8.15 NR sidelink U2N Remote UE operation
[446](#nr-sidelink-u2n-remote-ue-operation)

5.8.15.1 General [446](#general-57)

5.8.15.2 NR Sidelink U2N Remote UE threshold conditions
[446](#nr-sidelink-u2n-remote-ue-threshold-conditions)

5.8.15.3 Selection and reselection of NR sidelink U2N Relay UE
[446](#selection-and-reselection-of-nr-sidelink-u2n-relay-ue)

5.8.16 NR sidelink U2U Relay UE operation
[448](#nr-sidelink-u2u-relay-ue-operation)

5.8.16.1 General [448](#general-58)

5.8.16.2 NR sidelink U2U Relay UE threshold conditions
[448](#nr-sidelink-u2u-relay-ue-threshold-conditions)

5.8.16.3 Neighbor UE(s) in proximity conditions
[448](#neighbor-ues-in-proximity-conditions)

5.8.17 NR sidelink U2U Remote UE operation
[449](#nr-sidelink-u2u-remote-ue-operation)

5.8.17.1 General [449](#general-59)

5.8.17.2 NR Sidelink U2U Remote UE threshold conditions
[449](#nr-sidelink-u2u-remote-ue-threshold-conditions)

5.8.17.3 Conditions for selection and reselection of NR sidelink U2U
Relay UE
[449](#conditions-for-selection-and-reselection-of-nr-sidelink-u2u-relay-ue)

5.8.17.4 Actions related to selection and reselection of NR sidelink U2U
Relay UE
[450](#actions-related-to-selection-and-reselection-of-nr-sidelink-u2u-relay-ue)

5.8.18 NR sidelink positioning [451](#nr-sidelink-positioning)

5.8.18.1 General [451](#general-60)

5.8.18.2 NR sidelink positioning measurement
[451](#nr-sidelink-positioning-measurement)

5.8.18.3 NR sidelink positioning transmission
[451](#nr-sidelink-positioning-transmission)

5.9 MBS Broadcast [453](#mbs-broadcast)

5.9.1 Introduction [453](#introduction-8)

5.9.1.1 General [453](#general-61)

5.9.1.2 MCCH scheduling [454](#mcch-scheduling)

5.9.1.3 MCCH information validity and notification of changes
[454](#mcch-information-validity-and-notification-of-changes)

5.9.2 MCCH information acquisition [454](#mcch-information-acquisition)

5.9.2.1 General [454](#general-62)

5.9.2.2 Initiation [455](#initiation-31)

5.9.2.3 MCCH information acquisition by the UE
[455](#mcch-information-acquisition-by-the-ue)

5.9.2.4 Actions upon reception of the *MBSBroadcastConfiguration*
message
[455](#actions-upon-reception-of-the-mbsbroadcastconfiguration-message)

5.9.3 Broadcast MRB configuration [455](#broadcast-mrb-configuration)

5.9.3.1 General [455](#general-63)

5.9.3.2 Initiation [455](#initiation-32)

5.9.3.3 Broadcast MRB establishment [456](#broadcast-mrb-establishment)

5.9.3.4 Broadcast MRB release [456](#broadcast-mrb-release)

5.9.4 MBS Interest Indication [456](#mbs-interest-indication)

5.9.4.1 General [456](#general-64)

5.9.4.2 Initiation [456](#initiation-33)

5.9.4.3 MBS frequencies of interest determination
[458](#mbs-frequencies-of-interest-determination)

5.9.4.4 MBS services of interest determination
[458](#mbs-services-of-interest-determination)

5.9.4.5 Setting of the contents of MBS Interest Indication
[458](#setting-of-the-contents-of-mbs-interest-indication)

5.10 MBS multicast reception in RRC_INACTIVE
[459](#mbs-multicast-reception-in-rrc_inactive)

5.10.1 Introduction [459](#introduction-9)

5.10.1.1 General [459](#general-65)

5.10.1.2 Multicast MCCH scheduling [459](#multicast-mcch-scheduling)

5.10.1.3 Multicast MCCH information validity and notification of changes
[460](#multicast-mcch-information-validity-and-notification-of-changes)

5.10.2 Multicast MCCH information acquisition
[460](#multicast-mcch-information-acquisition)

5.10.2.1 General [460](#general-66)

5.10.2.2 Initiation [460](#initiation-34)

5.10.2.3 Multicast MCCH information acquisition by the UE
[460](#multicast-mcch-information-acquisition-by-the-ue)

5.10.2.4 Actions upon reception of the *MBSMulticastConfiguration*
message
[461](#actions-upon-reception-of-the-mbsmulticastconfiguration-message)

5.10.3 MRB configuration [461](#mrb-configuration)

5.10.3.1 General [461](#general-67)

5.10.3.2 Multicast MRB establishment [461](#multicast-mrb-establishment)

5.10.3.3 Multicast MRB release [462](#multicast-mrb-release-1)

6 Protocol data units, formats and parameters (ASN.1)
[463](#protocol-data-units-formats-and-parameters-asn.1)

6.1 General [463](#general-68)

6.1.1 Introduction [463](#introduction-10)

6.1.2 Need codes and conditions for optional fields
[463](#need-codes-and-conditions-for-optional-fields)

6.1.3 General rules [466](#general-rules)

6.2 RRC messages [466](#rrc-messages)

6.2.1 General message structure [466](#general-message-structure)

*--* *NR-RRC-Definitions* [466](#nr-rrc-definitions)

*--* *BCCH-BCH-Message* [466](#bcch-bch-message)

*--* *BCCH-DL-SCH-Message* [467](#bcch-dl-sch-message)

-- *DL-CCCH-Message* [467](#dl-ccch-message)

*--* *DL-DCCH-Message* [468](#dl-dcch-message)

*--* *MCCH-Message* [468](#mcch-message)

*--* *MulticastMCCH-Message* [469](#multicastmcch-message)

*--* *PCCH-Message* [469](#pcch-message)

-- *UL-CCCH-Message* [470](#ul-ccch-message)

*--* *UL-CCCH1-Message* [470](#ul-ccch1-message)

*--* *UL-DCCH-Message* [471](#ul-dcch-message)

6.2.2 Message definitions [473](#message-definitions)

-- *CounterCheck* [473](#countercheck)

-- *CounterCheckResponse* [474](#countercheckresponse)

-- *DedicatedSIBRequest* [475](#dedicatedsibrequest)

-- *DLDedicatedMessageSegment* [476](#dldedicatedmessagesegment)

-- *DLInformationTransfer* [477](#dlinformationtransfer)

*--* *DLInformationTransferMRDC* [479](#dlinformationtransfermrdc)

-- *FailureInformation* [480](#failureinformation)

-- *IABOtherInformation* [481](#iabotherinformation)

*--* *IndirectPathFailureInformation*
[484](#indirectpathfailureinformation)

-- *LocationMeasurementIndication* [485](#locationmeasurementindication)

-- *LoggedMeasurementConfiguration*
[486](#loggedmeasurementconfiguration)

*--* *MBSBroadcastConfiguration* [488](#mbsbroadcastconfiguration)

*--* *MBSInterestIndication* [490](#mbsinterestindication)

*--* *MBSMulticastConfiguration* [491](#mbsmulticastconfiguration)

*--* *MCGFailureInformation* [492](#mcgfailureinformation)

-- *MeasurementReport* [494](#measurementreport)

-- *MeasurementReportAppLayer* [494](#measurementreportapplayer)

-- *MIB* [496](#mib)

-- *MobilityFromNRCommand* [498](#mobilityfromnrcommand)

-- *Paging* [500](#paging-1)

-- *RRCReestablishment* [502](#rrcreestablishment)

-- *RRCReestablishmentComplete* [503](#rrcreestablishmentcomplete)

-- *RRCReestablishmentRequest* [504](#rrcreestablishmentrequest)

-- *RRCReconfiguration* [505](#rrcreconfiguration)

*--* *RRCReconfigurationComplete* [514](#rrcreconfigurationcomplete)

-- *RRCReject* [516](#rrcreject)

-- *RRCRelease* [517](#rrcrelease)

-- *RRCResume* [530](#rrcresume)

-- *RRCResumeComplete* [533](#rrcresumecomplete)

-- *RRCResumeRequest* [535](#rrcresumerequest)

-- *RRCResumeRequest1* [536](#rrcresumerequest1)

-- *RRCSetup* [537](#rrcsetup)

-- *RRCSetupComplete* [538](#rrcsetupcomplete)

*--* *RRCSetupRequest* [541](#rrcsetuprequest)

-- *RRCSystemInfoRequest* [543](#rrcsysteminforequest)

*--* *SCGFailureInformation* [544](#scgfailureinformation)

*--* *SCGFailureInformationEUTRA* [546](#scgfailureinformationeutra)

-- *SecurityModeCommand* [547](#securitymodecommand)

-- *SecurityModeComplete* [548](#securitymodecomplete)

-- *SecurityModeFailure* [549](#securitymodefailure)

-- *SIB1* [549](#sib1)

-- *SidelinkUEInformationNR* [556](#sidelinkueinformationnr)

-- *SystemInformation* [567](#systeminformation)

-- *UEAssistanceInformation* [568](#ueassistanceinformation)

-- *UECapabilityEnquiry* [583](#uecapabilityenquiry)

-- *UECapabilityInformation* [584](#uecapabilityinformation)

-- *UEInformationRequest* [585](#ueinformationrequest)

-- *UEInformationResponse* [587](#ueinformationresponse)

-- *UEPositioningAssistanceInfo* [608](#uepositioningassistanceinfo)

-- *ULDedicatedMessageSegment* [610](#uldedicatedmessagesegment)

-- *ULInformationTransfer* [611](#ulinformationtransfer)

-- *ULInformationTransferIRAT* [612](#ulinformationtransferirat)

*--* *ULInformationTransferMRDC* [613](#ulinformationtransfermrdc)

6.3 RRC information elements [614](#rrc-information-elements)

6.3.0 Parameterized types [614](#parameterized-types)

-- *SetupRelease* [614](#setuprelease)

6.3.1 System information blocks [614](#system-information-blocks)

-- *SIB2* [614](#sib2)

-- *SIB3* [619](#sib3)

-- *SIB4* [621](#sib4)

-- *SIB5* [628](#sib5)

*--* *SIB6* [631](#sib6)

*--* *SIB7* [631](#sib7)

*--* *SIB8* [632](#sib8)

-- *SIB9* [633](#sib9)

-- *SIB10* [634](#sib10)

-- *SIB11* [635](#sib11)

-- *SIB12* [636](#sib12)

-- *SIB13* [639](#sib13)

-- *SIB14* [640](#sib14)

-- *SIB15* [640](#sib15)

-- *SIB16* [641](#sib16)

-- *SIB17* [642](#sib17)

-- *SIB17bis* [644](#sib17bis)

-- *SIB18* [647](#sib18)

*--* *SIB19* [648](#sib19)

-- *SIB20* [650](#sib20)

-- *SIB21* [651](#sib21)

-- *SIB22* [652](#sib22)

-- *SIB23* [653](#sib23)

-- *SIB24* [654](#sib24)

-- *SIB25* [655](#sib25)

6.3.1a Positioning System information blocks
[656](#a-positioning-system-information-blocks)

-- *PosSystemInformation-r16-IEs* [656](#possysteminformation-r16-ies)

-- *PosSI-SchedulingInfo* [657](#possi-schedulinginfo)

-- *SIBpos* [660](#sibpos)

6.3.2 Radio resource control information elements
[661](#radio-resource-control-information-elements)

-- *AdditionalPCIIndex* [661](#additionalpciindex)

-- *AdditionalSpectrumEmission* [661](#additionalspectrumemission)

-- *AdvancedReceiver-MU-MIMO* [661](#advancedreceiver-mu-mimo)

-- *Aerial-Config* [662](#aerial-config)

-- *Alpha* [663](#alpha)

-- *Altitude* [663](#altitude)

-- *AMF-Identifier* [664](#amf-identifier)

-- *ARFCN-ValueEUTRA* [664](#arfcn-valueeutra)

-- *ARFCN-ValueNR* [664](#arfcn-valuenr)

-- *ARFCN-ValueUTRA-FDD* [664](#arfcn-valueutra-fdd)

-- *ATG-Config* [665](#atg-config)

-- *AvailabilityCombinationsPerCell*
[666](#availabilitycombinationspercell)

-- *AvailabilityIndicator* [667](#availabilityindicator)

-- *BAP-RoutingID* [668](#bap-routingid)

*--* *BeamFailureRecoveryConfig* [668](#beamfailurerecoveryconfig)

*--* *BeamFailureRecoveryRSConfig* [671](#beamfailurerecoveryrsconfig)

-- *BetaOffsets* [672](#betaoffsets)

-- *BetaOffsetsCrossPri* [673](#betaoffsetscrosspri)

-- *BH-LogicalChannelIdentity* [673](#bh-logicalchannelidentity)

-- *BH-LogicalChannelIdentity-Ext* [674](#bh-logicalchannelidentity-ext)

-- *BH-RLC-ChannelConfig* [674](#bh-rlc-channelconfig)

-- *BH-RLC-ChannelID* [675](#bh-rlc-channelid)

-- *BSR-Config* [675](#bsr-config)

-- *BWP* [676](#bwp)

-- *BWP-Downlink* [677](#bwp-downlink)

-- *BWP-DownlinkCommon* [678](#bwp-downlinkcommon)

-- *BWP-DownlinkDedicated* [678](#bwp-downlinkdedicated)

-- *BWP-Id* [681](#bwp-id)

-- *BWP-Uplink* [682](#bwp-uplink)

-- *BWP-UplinkCommon* [682](#bwp-uplinkcommon)

-- *BWP-UplinkDedicated* [685](#bwp-uplinkdedicated)

*--* *CandidateBeamRS* [690](#candidatebeamrs)

-- *CandidateTCI-State* [690](#candidatetci-state)

-- *CandidateTCI-UL-State* [691](#candidatetci-ul-state)

-- *CellAccessRelatedInfo* [693](#cellaccessrelatedinfo)

*--* *CellAccessRelatedInfo-EUTRA-5GC*
[695](#cellaccessrelatedinfo-eutra-5gc)

*--* *CellAccessRelatedInfo-EUTRA-EPC*
[695](#cellaccessrelatedinfo-eutra-epc)

-- *CellDTX-DRX-Config* [696](#celldtx-drx-config)

-- *CellGroupConfig* [697](#cellgroupconfig)

-- *CellGroupId* [711](#cellgroupid)

-- *CellIdentity* [711](#cellidentity)

-- *CellReselectionPriority* [711](#cellreselectionpriority)

-- *CellReselectionSubPriority* [712](#cellreselectionsubpriority)

-- *CFR-ConfigMulticast* [712](#cfr-configmulticast)

*--* *CGI-InfoEUTRA* [713](#cgi-infoeutra)

*--* *CGI-InfoEUTRALogging* [713](#cgi-infoeutralogging)

*--* *CGI-InfoNR* [714](#cgi-infonr)

-- *CGI-Info-Logging* [715](#cgi-info-logging)

-- *CLI-RSSI-Range* [716](#cli-rssi-range)

-- *ClockQualityMetrics* [716](#clockqualitymetrics)

-- *CodebookConfig* [716](#codebookconfig)

-- *CommonLocationInfo* [724](#commonlocationinfo)

*--* *CondReconfigId* [725](#condreconfigid)

*--* *CondReconfigToAddModList* [726](#condreconfigtoaddmodlist)

*--* *ConditionalReconfiguration* [728](#conditionalreconfiguration)

-- *ConfiguredGrantConfig* [729](#configuredgrantconfig)

-- *ConfiguredGrantConfigIndex* [741](#configuredgrantconfigindex)

-- *ConfiguredGrantConfigIndexMAC* [741](#configuredgrantconfigindexmac)

-- *ConnEstFailureControl* [742](#connestfailurecontrol)

-- *ControlResourceSet* [742](#controlresourceset)

-- *ControlResourceSetId* [745](#controlresourcesetid)

-- *ControlResourceSetZero* [745](#controlresourcesetzero)

-- *CrossCarrierSchedulingConfig* [746](#crosscarrierschedulingconfig)

-- *CSI-AperiodicTriggerStateList* [747](#csi-aperiodictriggerstatelist)

-- *CSI-FrequencyOccupation* [751](#csi-frequencyoccupation)

-- *CSI-IM-Resource* [752](#csi-im-resource)

-- *CSI-IM-ResourceId* [753](#csi-im-resourceid)

-- *CSI-IM-ResourceSet* [753](#csi-im-resourceset)

-- *CSI-IM-ResourceSetId* [753](#csi-im-resourcesetid)

-- *CSI-MeasConfig* [754](#csi-measconfig)

-- *CSI-ReportConfig* [756](#csi-reportconfig)

-- *CSI-ReportConfigId* [765](#csi-reportconfigid)

-- *CSI-ReportPeriodicityAndOffset*
[765](#csi-reportperiodicityandoffset)

-- *CSI-ReportSubConfigId* [766](#csi-reportsubconfigid)

-- *CSI-ReportSubConfigTriggerList*
[766](#csi-reportsubconfigtriggerlist)

-- *CSI-ResourceConfig* [766](#csi-resourceconfig)

-- *CSI-ResourceConfigId* [767](#csi-resourceconfigid)

-- *CSI-ResourcePeriodicityAndOffset*
[768](#csi-resourceperiodicityandoffset)

-- *CSI-RS-ResourceConfigMobility* [768](#csi-rs-resourceconfigmobility)

-- *CSI-RS-ResourceMapping* [771](#csi-rs-resourcemapping)

-- *CSI-SemiPersistentOnPUSCH-TriggerStateList*
[772](#csi-semipersistentonpusch-triggerstatelist)

-- *CSI-SSB-ResourceSet* [773](#csi-ssb-resourceset)

-- *CSI-SSB-ResourceSetId* [774](#csi-ssb-resourcesetid)

-- *DedicatedNAS-Message* [774](#dedicatednas-message)

-- *DL-PPW-PreConfig* [775](#dl-ppw-preconfig)

-- *DMRS-BundlingPUCCH-Config* [777](#dmrs-bundlingpucch-config)

-- *DMRS-BundlingPUSCH-Config* [778](#dmrs-bundlingpusch-config)

-- *DMRS-DownlinkConfig* [779](#dmrs-downlinkconfig)

-- *DMRS-UplinkConfig* [780](#dmrs-uplinkconfig)

*--* *DownlinkConfigCommon* [782](#downlinkconfigcommon)

-- *DownlinkConfigCommonSIB* [783](#downlinkconfigcommonsib)

-- *DownlinkPreemption* [788](#downlinkpreemption)

-- *DRB-Identity* [789](#drb-identity)

-- *DRX-Config* [789](#drx-config)

-- *DRX-ConfigSecondaryGroup* [792](#drx-configsecondarygroup)

*--* *DRX-ConfigSL* [793](#drx-configsl)

-- *EarlyUL-SyncConfig* [794](#earlyul-syncconfig)

-- *EphemerisInfo* [795](#ephemerisinfo)

-- *EpochTime* [797](#epochtime)

-- *EUTRA-C-RNTI* [797](#eutra-c-rnti)

-- *FeatureCombination* [798](#featurecombination)

-- *FeatureCombinationPreambles* [799](#featurecombinationpreambles)

-- *FilterCoefficient* [801](#filtercoefficient)

-- *FreqBandIndicatorNR* [802](#freqbandindicatornr)

-- *FreqPriorityListDedicatedSlicing*
[802](#freqprioritylistdedicatedslicing)

-- *FreqPriorityListSlicing* [803](#freqprioritylistslicing)

-- *FrequencyInfoDL* [804](#frequencyinfodl)

*--* *FrequencyInfoDL-SIB* [805](#frequencyinfodl-sib)

-- *FrequencyInfoUL* [806](#frequencyinfoul)

*--* *FrequencyInfoUL-SIB* [808](#frequencyinfoul-sib)

-- *GapPriority* [809](#gappriority)

-- *HighSpeedConfig* [810](#highspeedconfig)

-- *Hysteresis* [812](#hysteresis)

-- *HysteresisAltitude* [812](#hysteresisaltitude)

-- *HysteresisLocation* [812](#hysteresislocation)

-- *InvalidSymbolPattern* [813](#invalidsymbolpattern)

-- *I-RNTI-Value* [814](#i-rnti-value)

-- *LBT-FailureRecoveryConfig* [814](#lbt-failurerecoveryconfig)

-- *LocationInfo* [815](#locationinfo)

-- *LocationMeasurementInfo* [815](#locationmeasurementinfo)

-- *LogicalChannelConfig* [817](#logicalchannelconfig)

-- *LogicalChannelIdentity* [819](#logicalchannelidentity)

-- *LTE-NeighCellsCRS-AssistInfoList*
[819](#lte-neighcellscrs-assistinfolist)

-- *LTM-CandidateId* [821](#ltm-candidateid)

-- *LTM-Candidate* [821](#ltm-candidate)

-- *LTM-Config* [823](#ltm-config)

-- *LTM-CSI-ReportConfig* [824](#ltm-csi-reportconfig)

-- *LTM-CSI-ReportConfigId* [825](#ltm-csi-reportconfigid)

-- *LTM-CSI-ResourceConfig* [825](#ltm-csi-resourceconfig)

-- *LTM-CSI-ResourceConfigId* [826](#ltm-csi-resourceconfigid)

-- *LTM-TCI-Info* [826](#ltm-tci-info)

-- *MAC-CellGroupConfig* [827](#mac-cellgroupconfig)

-- *MeasConfig* [832](#measconfig)

-- *MeasGapConfig* [833](#measgapconfig)

-- *MeasGapId* [838](#measgapid)

-- *MeasGapSharingConfig* [838](#measgapsharingconfig)

-- *MeasId* [839](#measid)

-- *MeasIdleConfig* [839](#measidleconfig)

-- *MeasIdToAddModList* [843](#measidtoaddmodlist)

*--* *MeasObjectCLI* [844](#measobjectcli)

*--* *MeasObjectEUTRA* [846](#measobjecteutra)

*--* *MeasObjectId* [848](#measobjectid)

*--* *MeasObjectNR* [849](#measobjectnr)

-- *MeasObjectNR-SL* [858](#measobjectnr-sl)

-- *MeasObjectRxTxDiff* [859](#measobjectrxtxdiff)

-- *MeasObjectToAddModList* [859](#measobjecttoaddmodlist)

-- *MeasObjectUTRA-FDD* [860](#measobjectutra-fdd)

*--* *MeasResultCellListSFTD-NR* [861](#measresultcelllistsftd-nr)

*--* *MeasResultCellListSFTD-EUTRA* [862](#measresultcelllistsftd-eutra)

-- *MeasResults* [862](#measresults)

*--* *MeasResult2EUTRA* [870](#measresult2eutra)

*--* *MeasResult2NR* [870](#measresult2nr)

-- *MeasResultIdleEUTRA* [871](#measresultidleeutra)

-- *MeasResultIdleNR* [872](#measresultidlenr)

-- *MeasResultRxTxTimeDiff* [873](#measresultrxtxtimediff)

*--* *MeasResultSCG-Failure* [874](#measresultscg-failure)

-- *MeasResultsSL* [874](#measresultssl)

-- *MeasSequence* [875](#meassequence)

-- *MeasTriggerQuantityEUTRA* [876](#meastriggerquantityeutra)

-- *MeasurementValidityDuration* [876](#measurementvalidityduration)

*--* *MeasWindowConfig* [877](#measwindowconfig)

-- *MobilityStateParameters* [877](#mobilitystateparameters)

-- *MRB-Identity* [878](#mrb-identity)

-- *MsgA-ConfigCommon* [878](#msga-configcommon)

-- *MsgA-PUSCH-Config* [879](#msga-pusch-config)

-- *MultiFrequencyBandListNR* [882](#multifrequencybandlistnr)

-- *MultiFrequencyBandListNR-SIB* [883](#multifrequencybandlistnr-sib)

-- *MUSIM-GapConfig* [884](#musim-gapconfig)

-- *MUSIM-GapId* [885](#musim-gapid)

-- *MUSIM-GapInfo* [886](#musim-gapinfo)

-- *N3C-IndirectPathConfigRelay* [887](#n3c-indirectpathconfigrelay)

-- *N3C-IndirectPathAddChange* [888](#n3c-indirectpathaddchange)

-- *N3C-RelayUE-Info* [888](#n3c-relayue-info)

-- *NCR-AperiodicFwdConfig* [889](#ncr-aperiodicfwdconfig)

-- *NCR-FwdConfig* [890](#ncr-fwdconfig)

-- *NCR-PeriodicityAndOffset* [891](#ncr-periodicityandoffset)

-- *NCR-PeriodicFwdResourceSet* [892](#ncr-periodicfwdresourceset)

-- *NCR-PeriodicFwdResourceSetId* [893](#ncr-periodicfwdresourcesetid)

-- *NCR-SemiPersistentFwdResourceSet* [894](#_Toc193463340)

-- *NCR-SemiPersistentFwdResourceSetId*
[895](#ncr-semipersistentfwdresourcesetid)

-- *NeedForGapsConfigNR* [895](#needforgapsconfignr)

-- *NeedForGapsInfoNR* [896](#_Toc193463343)

-- *NeedForGapNCSG-ConfigEUTRA* [897](#needforgapncsg-configeutra)

-- *NeedForGapNCSG-ConfigNR* [897](#needforgapncsg-confignr)

-- *NeedForGapNCSG-InfoEUTRA* [898](#needforgapncsg-infoeutra)

-- *NeedForGapNCSG-InfoNR* [899](#needforgapncsg-infonr)

-- *NeedForInterruptionInfoNR* [900](#needforinterruptioninfonr)

-- *NextHopChainingCount* [901](#nexthopchainingcount)

-- *NG-5G-S-TMSI* [901](#ng-5g-s-tmsi)

-- *NonCellDefiningSSB* [902](#noncelldefiningssb)

-- *NPN-Identity* [903](#npn-identity)

-- *NPN-IdentityInfoList* [903](#npn-identityinfolist)

-- *NR-DL-PRS-PDC-Info* [905](#nr-dl-prs-pdc-info)

-- *NR-NS-PmaxList* [909](#nr-ns-pmaxlist)

-- *NSAG-ID* [910](#nsag-id)

-- *NSAG-IdentityInfo* [910](#nsag-identityinfo)

-- *NTN-Config* [910](#ntn-config)

-- *NZP-CSI-RS-Resource* [913](#nzp-csi-rs-resource)

-- *NZP-CSI-RS-ResourceId* [914](#nzp-csi-rs-resourceid)

-- *NZP-CSI-RS-ResourceSet* [915](#nzp-csi-rs-resourceset)

-- *NZP-CSI-RS-ResourceSetId* [917](#nzp-csi-rs-resourcesetid)

-- *P-Max* [917](#p-max)

-- *PathlossReferenceRS* [917](#pathlossreferencers)

-- *PathlossReferenceRS-Id* [918](#pathlossreferencers-id)

-- *PCI-ARFCN-EUTRA* [918](#pci-arfcn-eutra)

-- *PCI-ARFCN-NR* [919](#pci-arfcn-nr)

-- *PCI-List* [919](#pci-list)

-- *PCI-Range* [919](#pci-range)

-- *PCI-RangeElement* [920](#pci-rangeelement)

-- *PCI-RangeIndex* [920](#pci-rangeindex)

-- *PCI-RangeIndexList* [921](#pci-rangeindexlist)

-- *PDCCH-Config* [921](#pdcch-config)

-- *PDCCH-ConfigCommon* [924](#pdcch-configcommon)

-- *PDCCH-ConfigSIB1* [928](#pdcch-configsib1)

-- *PDCCH-ServingCellConfig* [928](#pdcch-servingcellconfig)

-- *PDCP-Config* [929](#pdcp-config)

-- *PDSCH-Config* [937](#pdsch-config)

-- *PDSCH-ConfigCommon* [945](#pdsch-configcommon)

-- *PDSCH-ServingCellConfig* [946](#pdsch-servingcellconfig)

-- *PDSCH-TimeDomainResourceAllocationList*
[948](#pdsch-timedomainresourceallocationlist)

-- *PDU-SessionID* [950](#pdu-sessionid)

-- *PHR-Config* [950](#phr-config)

-- *PhysCellId* [952](#physcellid)

-- *PhysicalCellGroupConfig* [953](#physicalcellgroupconfig)

-- *PLMN-Identity* [962](#plmn-identity)

-- *PLMN-IdentityInfoList* [963](#plmn-identityinfolist)

-- *PLMN-IdentityList2* [964](#plmn-identitylist2)

-- *PRB-Id* [964](#prb-id)

-- *PTRS-DownlinkConfig* [965](#ptrs-downlinkconfig)

-- *PTRS-UplinkConfig* [966](#ptrs-uplinkconfig)

-- *PUCCH-Config* [967](#pucch-config)

-- *PUCCH-ConfigCommon* [976](#pucch-configcommon)

-- *PUCCH-ConfigurationList* [977](#pucch-configurationlist)

-- *PUCCH-CSI-Resource* [978](#pucch-csi-resource)

-- *PUCCH-PathlossReferenceRS-Id* [978](#pucch-pathlossreferencers-id)

-- *PUCCH-PowerControl* [979](#pucch-powercontrol)

-- *PUCCH-SpatialRelationInfo* [981](#pucch-spatialrelationinfo)

-- *PUCCH-SpatialRelationInfo-Id* [982](#pucch-spatialrelationinfo-id)

-- *PUCCH-TPC-CommandConfig* [983](#pucch-tpc-commandconfig)

-- *PUSCH-Config* [983](#pusch-config)

-- *PUSCH-ConfigCommon* [993](#pusch-configcommon)

-- *PUSCH-PowerControl* [994](#pusch-powercontrol)

-- *PUSCH-ServingCellConfig* [998](#pusch-servingcellconfig)

-- *PUSCH-TimeDomainResourceAllocationList*
[1000](#pusch-timedomainresourceallocationlist)

-- *PUSCH-TPC-CommandConfig* [1003](#pusch-tpc-commandconfig)

*--* *QFI* [1004](#qfi)

*--* *Q-OffsetRange* [1004](#q-offsetrange)

-- *Q-QualMin* [1005](#q-qualmin)

-- *Q-RxLevMin* [1005](#q-rxlevmin)

-- *QuantityConfig* [1005](#quantityconfig)

-- *RACH-ConfigCommon* [1007](#rach-configcommon)

-- *RACH-ConfigCommonTwoStepRA* [1010](#rach-configcommontwostepra)

-- *RACH-ConfigDedicated* [1015](#rach-configdedicated)

-- *RACH-ConfigGeneric* [1019](#rach-configgeneric)

-- *RACH-ConfigGenericTwoStepRA* [1020](#rach-configgenerictwostepra)

-- *RACH-ConfigTwoTA* [1023](#rach-configtwota)

-- *RA-Prioritization* [1024](#ra-prioritization)

-- *RA-PrioritizationForSlicing* [1025](#ra-prioritizationforslicing)

-- *RadioBearerConfig* [1025](#radiobearerconfig)

-- *RadioLinkMonitoringConfig* [1030](#radiolinkmonitoringconfig)

-- *RadioLinkMonitoringRS-Id* [1032](#radiolinkmonitoringrs-id)

-- *RAN-AreaCode* [1033](#ran-areacode)

-- *RateMatchPattern* [1033](#ratematchpattern)

-- *RateMatchPatternId* [1035](#ratematchpatternid)

-- *RateMatchPatternLTE-CRS* [1036](#ratematchpatternlte-crs)

-- *ReferenceConfiguration* [1037](#referenceconfiguration)

-- *ReferenceLocation* [1037](#referencelocation)

-- *ReferenceTimeInfo* [1037](#referencetimeinfo)

-- *RejectWaitTime* [1039](#rejectwaittime)

-- *RepetitionSchemeConfig* [1039](#repetitionschemeconfig)

-- *ReportConfigId* [1040](#reportconfigid)

*--* *ReportConfigInterRAT* [1040](#reportconfiginterrat)

-- *ReportConfigNR* [1046](#reportconfignr)

-- *ReportConfigNR-SL* [1060](#reportconfignr-sl)

-- *ReportConfigToAddModList* [1062](#reportconfigtoaddmodlist)

-- *ReportInterval* [1063](#reportinterval)

-- *ReselectionThreshold* [1063](#reselectionthreshold)

-- *ReselectionThresholdQ* [1063](#reselectionthresholdq)

-- *ResumeCause* [1064](#resumecause)

-- *RLC-BearerConfig* [1064](#rlc-bearerconfig)

-- *RLC-Config* [1066](#rlc-config)

-- *RLF-TimersAndConstants* [1069](#rlf-timersandconstants)

-- *RNTI-Value* [1070](#rnti-value)

-- *RSRP-Range* [1070](#rsrp-range)

-- *RSRQ-Range* [1070](#rsrq-range)

-- *RSSI-Range* [1071](#rssi-range)

-- *RxTxTimeDiff* [1071](#rxtxtimediff)

-- *SCellActivationRS-Config* [1072](#scellactivationrs-config)

-- *SCellActivationRS-ConfigId* [1072](#scellactivationrs-configid)

-- *SCellIndex* [1073](#scellindex)

-- *SchedulingRequestConfig* [1073](#schedulingrequestconfig)

-- *SchedulingRequestId* [1074](#schedulingrequestid)

-- *SchedulingRequestResourceConfig*
[1075](#schedulingrequestresourceconfig)

-- *SchedulingRequestResourceId* [1076](#schedulingrequestresourceid)

-- *ScramblingId* [1076](#scramblingid)

-- *SCS-SpecificCarrier* [1077](#scs-specificcarrier)

-- *SDAP-Config* [1078](#sdap-config)

-- *SearchSpace* [1079](#searchspace)

-- *SearchSpaceId* [1087](#searchspaceid)

-- *SearchSpaceZero* [1087](#searchspacezero)

-- *SecurityAlgorithmConfig* [1088](#securityalgorithmconfig)

-- *SelectedPSCellForCHO-WithSCG* [1089](#selectedpscellforcho-withscg)

-- *SemiStaticChannelAccessConfig*
[1089](#semistaticchannelaccessconfig)

-- *SemiStaticChannelAccessConfigUE*
[1089](#semistaticchannelaccessconfigue)

-- *Sensor-LocationInfo* [1090](#sensor-locationinfo)

*--* *ServingCellAndBWP-Id* [1091](#servingcellandbwp-id)

-- *ServCellIndex* [1091](#servcellindex)

-- *ServingCellConfig* [1091](#servingcellconfig)

-- *ServingCellConfigCommon* [1110](#servingcellconfigcommon)

-- *ServingCellConfigCommonSIB* [1113](#servingcellconfigcommonsib)

*--* *ShortI-RNTI-Value* [1116](#shorti-rnti-value)

*--* *ShortMAC-I* [1116](#shortmac-i)

-- *SINR-Range* [1116](#sinr-range)

-- *SI-RequestConfig* [1117](#si-requestconfig)

*--* *SI-RequestConfigRepetition* [1118](#si-requestconfigrepetition)

-- *SI-SchedulingInfo* [1120](#si-schedulinginfo)

*--* *SK-Counter* [1123](#sk-counter)

-- *SlotFormatCombinationsPerCell*
[1124](#slotformatcombinationspercell)

-- *SlotFormatIndicator* [1125](#slotformatindicator)

-- *S-NSSAI* [1128](#s-nssai)

-- *SpeedStateScaleFactors* [1129](#speedstatescalefactors)

-- *SPS-Config* [1129](#sps-config)

-- *SPS-ConfigIndex* [1132](#sps-configindex)

-- *SPS-PUCCH-AN* [1132](#sps-pucch-an)

-- *SPS-PUCCH-AN-List* [1133](#sps-pucch-an-list)

-- *SRB-Identity* [1133](#srb-identity)

-- *SRS-CarrierSwitching* [1133](#srs-carrierswitching)

-- *SRS-Config* [1135](#srs-config)

-- *SRS-PosTx-Hopping* [1152](#srs-postx-hopping)

-- *SRS-PosResourceSetLinkedForAggBW*
[1153](#srs-posresourcesetlinkedforaggbw)

-- *SRS-RSRP-Range* [1154](#srs-rsrp-range)

-- *SRS-TPC-CommandConfig* [1154](#srs-tpc-commandconfig)

-- *SSB-Index* [1155](#ssb-index)

-- *SSB-MTC* [1155](#ssb-mtc)

-- *SSB-PositionQCL-Relation* [1158](#ssb-positionqcl-relation)

-- *SSB-ToMeasure* [1158](#ssb-tomeasure)

-- *SS-RSSI-Measurement* [1159](#ss-rssi-measurement)

-- *SubcarrierSpacing* [1160](#subcarrierspacing)

-- *TAG-Config* [1160](#tag-config)

-- *TAR-Config* [1161](#tar-config)

-- *TCI-ActivatedConfig* [1162](#tci-activatedconfig)

-- *TCI-State* [1162](#tci-state)

-- *TCI-StateId* [1164](#tci-stateid)

-- *TCI-UL-State* [1165](#tci-ul-state)

-- *TCI-UL-StateId* [1166](#tci-ul-stateid)

-- *TDD-UL-DL-ConfigCommon* [1167](#tdd-ul-dl-configcommon)

-- *TDD-UL-DL-ConfigDedicated* [1168](#tdd-ul-dl-configdedicated)

-- *TrackingAreaCode* [1170](#trackingareacode)

-- *T-Reselection* [1170](#t-reselection)

-- *TimeAlignmentTimer* [1171](#timealignmenttimer)

-- *TimeToTrigger* [1171](#timetotrigger)

-- *TN-AreaId* [1171](#tn-areaid)

*--* *UAC-BarringInfoSetIndex* [1172](#uac-barringinfosetindex)

*--* *UAC-BarringInfoSetList* [1172](#uac-barringinfosetlist)

*--* *UAC-BarringPerCatList* [1173](#uac-barringpercatlist)

*--* *UAC-BarringPerPLMN-List* [1174](#uac-barringperplmn-list)

-- *UE-TimersAndConstants* [1174](#ue-timersandconstants)

-- *UE-TimersAndConstantsRemoteUE*
[1175](#ue-timersandconstantsremoteue)

-- *UL-DelayValueConfig* [1175](#ul-delayvalueconfig)

-- *UL-ExcessDelayConfig* [1176](#ul-excessdelayconfig)

-- *UL-GapFR2-Config* [1176](#ul-gapfr2-config)

-- *UplinkCancellation* [1177](#uplinkcancellation)

*--* *UplinkConfigCommon* [1179](#uplinkconfigcommon)

-- *UplinkConfigCommonSIB* [1180](#uplinkconfigcommonsib)

-- *Uplink-PowerControl* [1181](#uplink-powercontrol)

-- *Uu-RelayRLC-ChannelConfig* [1182](#uu-relayrlc-channelconfig)

-- *Uu-RelayRLC-ChannelID* [1183](#uu-relayrlc-channelid)

-- *UplinkTxDirectCurrentList* [1183](#uplinktxdirectcurrentlist)

*--* *UplinkTxDirectCurrentMoreCarrierList*
[1184](#uplinktxdirectcurrentmorecarrierlist)

-- *UplinkTxDirectCurrentTwoCarrierList*
[1186](#uplinktxdirectcurrenttwocarrierlist)

-- *ZP-CSI-RS-Resource* [1187](#zp-csi-rs-resource)

-- *ZP-CSI-RS-ResourceSet* [1188](#zp-csi-rs-resourceset)

-- *ZP-CSI-RS-ResourceSetId* [1189](#zp-csi-rs-resourcesetid)

6.3.3 UE capability information elements
[1189](#ue-capability-information-elements)

-- *AccessStratumRelease* [1189](#accessstratumrelease)

-- *AerialParameters* [1189](#aerialparameters)

-- *AppLayerMeasParameters* [1190](#applayermeasparameters)

-- *BandCombinationList* [1191](#bandcombinationlist)

-- *BandCombinationListSidelinkEUTRA-NR*
[1203](#bandcombinationlistsidelinkeutra-nr)

-- *BandCombinationListSL-Discovery*
[1205](#bandcombinationlistsl-discovery)

-- *CA-BandwidthClassEUTRA* [1206](#ca-bandwidthclasseutra)

-- *CA-BandwidthClassNR* [1206](#ca-bandwidthclassnr)

-- *CA-ParametersEUTRA* [1206](#ca-parameterseutra)

-- *CA-ParametersNR* [1207](#ca-parametersnr)

-- *CA-ParametersNRDC* [1222](#ca-parametersnrdc)

-- *CarrierAggregationVariant* [1224](#carrieraggregationvariant)

-- *CodebookParameters* [1225](#codebookparameters)

-- *DL-PRS-MeasurementWithRxFH-RRC-Connected*
[1236](#dl-prs-measurementwithrxfh-rrc-connected)

-- *ERedCapParameters* [1237](#eredcapparameters)

-- *FeatureSetCombination* [1237](#featuresetcombination)

-- *FeatureSetCombinationId* [1239](#featuresetcombinationid)

-- *FeatureSetDownlink* [1239](#featuresetdownlink)

-- *FeatureSetDownlinkId* [1247](#featuresetdownlinkid)

-- *FeatureSetDownlinkPerCC* [1247](#featuresetdownlinkpercc)

-- *FeatureSetDownlinkPerCC-Id* [1249](#featuresetdownlinkpercc-id)

-- *FeatureSetEUTRA-DownlinkId* [1250](#featureseteutra-downlinkid)

-- *FeatureSetEUTRA-UplinkId* [1250](#featureseteutra-uplinkid)

-- *FeatureSets* [1251](#featuresets)

-- *FeatureSetUplink* [1253](#featuresetuplink)

-- *FeatureSetUplinkId* [1261](#featuresetuplinkid)

-- *FeatureSetUplinkPerCC* [1262](#featuresetuplinkpercc)

-- *FeatureSetUplinkPerCC-Id* [1265](#featuresetuplinkpercc-id)

-- *FreqBandIndicatorEUTRA* [1265](#freqbandindicatoreutra)

-- *FreqBandList* [1265](#freqbandlist)

-- *FreqSeparationClass* [1266](#freqseparationclass)

*--* *FreqSeparationClassDL-Only* [1267](#freqseparationclassdl-only)

-- *FR2-2-AccessParamsPerBand* [1267](#fr2-2-accessparamsperband)

-- *HighSpeedParameters* [1268](#highspeedparameters)

-- *IMS-Parameters* [1269](#ims-parameters)

-- *InterRAT-Parameters* [1270](#interrat-parameters)

-- *MAC-Parameters* [1271](#mac-parameters)

-- *MeasAndMobParameters* [1274](#measandmobparameters)

-- *MeasAndMobParametersMRDC* [1279](#measandmobparametersmrdc)

-- *MIMO-Layers* [1281](#mimo-layers)

-- *MIMO-ParametersPerBand* [1281](#mimo-parametersperband)

-- *ModulationOrder* [1296](#modulationorder)

-- *MRDC-Parameters* [1296](#mrdc-parameters)

-- *NCR-Parameters* [1298](#ncr-parameters)

-- *NRDC-Parameters* [1299](#nrdc-parameters)

-- *NTN-Parameters* [1300](#ntn-parameters)

-- *OLPC-SRS-Pos* [1301](#olpc-srs-pos)

-- *PDCP-Parameters* [1301](#pdcp-parameters)

-- *PDCP-ParametersMRDC* [1303](#pdcp-parametersmrdc)

-- *Phy-Parameters* [1303](#phy-parameters)

-- *Phy-ParametersMRDC* [1312](#phy-parametersmrdc)

-- *Phy-ParametersSharedSpectrumChAccess*
[1313](#phy-parameterssharedspectrumchaccess)

-- *PosSRS-BWA-RRC-Inactive* [1314](#possrs-bwa-rrc-inactive)

-- *PosSRS-RRC-Inactive-OutsideInitialUL-BWP*
[1315](#possrs-rrc-inactive-outsideinitialul-bwp)

-- *PosSRS-TxFrequencyHoppingRRC-Connected*
[1316](#possrs-txfrequencyhoppingrrc-connected)

-- *PosSRS-TxFrequencyHoppingRRC-Inactive*
[1316](#possrs-txfrequencyhoppingrrc-inactive)

*--* *PowSav-Parameters* [1317](#powsav-parameters)

-- *ProcessingParameters* [1318](#processingparameters)

-- *PRS-ProcessingCapabilityOutsideMGinPPWperType*
[1318](#prs-processingcapabilityoutsidemginppwpertype)

-- *RAT-Type* [1319](#rat-type)

-- *RedCapParameters* [1319](#redcapparameters)

-- *RF-Parameters* [1320](#rf-parameters)

-- *RF-ParametersMRDC* [1338](#rf-parametersmrdc)

-- *RLC-Parameters* [1341](#rlc-parameters)

-- *SDAP-Parameters* [1342](#sdap-parameters)

-- *SharedSpectrumChAccessParamsPerBand*
[1342](#sharedspectrumchaccessparamsperband)

-- S*haredSpectrumChAccessParamsSidelinkPerBand*
[1345](#sharedspectrumchaccessparamssidelinkperband)

-- *SidelinkParameters* [1346](#sidelinkparameters)

-- *SimultaneousRxTxPerBandPair* [1352](#simultaneousrxtxperbandpair)

-- *SON-Parameters* [1352](#son-parameters)

-- *SpatialRelationsSRS-Pos* [1353](#spatialrelationssrs-pos)

-- *SRS-AllPosResourcesRRC-Inactive*
[1354](#srs-allposresourcesrrc-inactive)

-- *SRS-SwitchingTimeNR* [1354](#srs-switchingtimenr)

-- *SRS-SwitchingTimeEUTRA* [1355](#srs-switchingtimeeutra)

-- *SupportedAggBandwidth* [1355](#supportedaggbandwidth)

-- *SupportedBandwidth* [1355](#supportedbandwidth)

-- *UE-BasedPerfMeas-Parameters* [1356](#ue-basedperfmeas-parameters)

-- *UE-CapabilityRAT-ContainerList*
[1357](#ue-capabilityrat-containerlist)

-- *UE-CapabilityRAT-RequestList* [1357](#ue-capabilityrat-requestlist)

-- *UE-CapabilityRequestFilterCommon*
[1358](#ue-capabilityrequestfiltercommon)

-- *UE-CapabilityRequestFilterNR* [1361](#ue-capabilityrequestfilternr)

-- *UE-MRDC-Capability* [1361](#ue-mrdc-capability)

-- *UE-NR-Capability* [1363](#ue-nr-capability)

-- *UE-RadioPagingInfo* [1369](#ue-radiopaginginfo)

6.3.4 Other information elements [1370](#other-information-elements)

-- *AbsoluteTimeInfo* [1370](#absolutetimeinfo)

-- *AppLayerIdleInactiveConfig* [1370](#applayeridleinactiveconfig)

-- *AppLayerMeasConfig* [1371](#applayermeasconfig)

-- *AreaConfiguration* [1374](#areaconfiguration)

-- *BT-NameList* [1376](#bt-namelist)

-- *DedicatedInfoF1c* [1376](#dedicatedinfof1c)

-- *EUTRA-AllowedMeasBandwidth* [1377](#eutra-allowedmeasbandwidth)

-- *EUTRA-MBSFN-SubframeConfigList*
[1377](#eutra-mbsfn-subframeconfiglist)

-- *EUTRA-MultiBandInfoList* [1378](#eutra-multibandinfolist)

-- *EUTRA-MultiBandInfoListAerial*
[1378](#eutra-multibandinfolistaerial)

-- *EUTRA-NS-PmaxList* [1379](#eutra-ns-pmaxlist)

-- *EUTRA-PhysCellId* [1379](#eutra-physcellid)

-- *EUTRA-PhysCellIdRange* [1380](#eutra-physcellidrange)

-- *EUTRA-PresenceAntennaPort1* [1380](#eutra-presenceantennaport1)

-- *EUTRA-Q-OffsetRange* [1380](#eutra-q-offsetrange)

-- *IAB-IP-Address* [1381](#iab-ip-address)

-- *IAB-IP-AddressIndex* [1381](#iab-ip-addressindex)

-- *IAB-IP-Usage* [1382](#iab-ip-usage)

-- *LoggingDuration* [1382](#loggingduration)

-- *LoggingInterval* [1382](#logginginterval)

-- *LogMeasResultListBT* [1383](#logmeasresultlistbt)

-- *LogMeasResultListWLAN* [1383](#logmeasresultlistwlan)

-- *MeasConfigAppLayerId* [1385](#measconfigapplayerid)

-- *OtherConfig* [1385](#otherconfig)

-- *PhysCellIdUTRA-FDD* [1394](#physcellidutra-fdd)

-- *RRC-TransactionIdentifier* [1395](#rrc-transactionidentifier)

-- *Sensor-NameList* [1395](#sensor-namelist)

-- *TraceReference* [1396](#tracereference)

-- *UE-MeasurementsAvailable* [1396](#ue-measurementsavailable)

-- *UTRA-FDD-Q-OffsetRange* [1397](#utra-fdd-q-offsetrange)

-- *VisitedCellInfoList* [1397](#visitedcellinfolist)

-- *WLAN-NameList* [1398](#wlan-namelist)

6.3.5 Sidelink information elements
[1399](#sidelink-information-elements)

-- *SL-BWP-Config* [1399](#sl-bwp-config)

-- *SL-BWP-ConfigCommon* [1402](#sl-bwp-configcommon)

-- *SL-BWP-DiscPoolConfig* [1403](#sl-bwp-discpoolconfig)

-- *SL-BWP-DiscPoolConfigCommon* [1404](#sl-bwp-discpoolconfigcommon)

-- *SL-BWP-PoolConfig* [1404](#sl-bwp-poolconfig)

-- *SL-BWP-PoolConfigCommon* [1405](#sl-bwp-poolconfigcommon)

-- *SL-BWP-PRS-PoolConfig* [1406](#sl-bwp-prs-poolconfig)

-- *SL-BWP-PRS-PoolConfigCommon* [1407](#sl-bwp-prs-poolconfigcommon)

-- *SL-CBR-PriorityTxConfigList* [1408](#sl-cbr-prioritytxconfiglist)

-- *SL-CBR-CommonTxConfigList* [1409](#sl-cbr-commontxconfiglist)

-- *SL-CBR-CommonTxDedicatedSL-PRS-RP-List*
[1410](#sl-cbr-commontxdedicatedsl-prs-rp-list)

-- *SL-ConfigDedicatedNR* [1411](#sl-configdedicatednr)

-- *SL-ConfiguredGrantConfig* [1415](#sl-configuredgrantconfig)

-- *SL-ConfiguredGrantConfigDedicated-SL-PRS-RP*
[1418](#sl-configuredgrantconfigdedicated-sl-prs-rp)

-- *SL-DestinationIdentity* [1419](#sl-destinationidentity)

*--* *SL-DRX-Config* [1419](#sl-drx-config)

*--* *SL-DRX-ConfigGC-BC* [1420](#sl-drx-configgc-bc)

*--* *SL-DRX-ConfigUC* [1422](#sl-drx-configuc)

*--* *SL-DRX-ConfigUC-SemiStatic* [1424](#sl-drx-configuc-semistatic)

-- *SL-FreqConfig* [1425](#sl-freqconfig)

-- *SL-FreqConfigCommon* [1428](#sl-freqconfigcommon)

-- *SL-FreqSelectionConfig* [1431](#sl-freqselectionconfig)

*--* *SL-IndirectPathAddChange* [1432](#sl-indirectpathaddchange)

-- *SL-InterUE-CoordinationConfig*
[1432](#sl-interue-coordinationconfig)

-- *SL-LBT-FailureRecoveryConfig* [1436](#sl-lbt-failurerecoveryconfig)

-- *SL-LogicalChannelConfig* [1436](#sl-logicalchannelconfig)

-- *SL-L2RelayUE-Config* [1439](#sl-l2relayue-config)

-- *SL-L2RemoteUE-Config* [1440](#sl-l2remoteue-config)

-- *SL-MeasConfigCommon* [1441](#sl-measconfigcommon)

-- *SL-MeasConfigInfo* [1442](#sl-measconfiginfo)

-- *SL-MeasIdList* [1443](#sl-measidlist)

-- *SL-MeasObjectList* [1443](#sl-measobjectlist)

-- *SL-PagingIdentityRemoteUE* [1444](#sl-pagingidentityremoteue)

-- *SL-PBPS-CPS-Config* [1445](#sl-pbps-cps-config)

-- *SL-PDCP-Config* [1447](#sl-pdcp-config)

\- *SL-PosBWP-ConfigCommon* [1447](#sl-posbwp-configcommon)

-- *SL-PRS-ResourcePool* [1448](#sl-prs-resourcepool)

-- *SL-PSBCH-Config* [1452](#_Toc193463691)

-- *SL-PSSCH-TxConfigList* [1453](#sl-pssch-txconfiglist)

-- *SL-QoS-FlowIdentity* [1454](#sl-qos-flowidentity)

-- *SL-QoS-Profile* [1454](#sl-qos-profile)

-- *SL-QuantityConfig* [1456](#sl-quantityconfig)

-- *SL-RadioBearerConfig* [1456](#sl-radiobearerconfig)

-- *SL-RBSetConfig* [1457](#sl-rbsetconfig)

-- *SL-RelayIndicationMP* [1458](#sl-relayindicationmp)

-- *SL-RelayUE-Config* [1458](#_Toc193463699)

-- *SL-RelayUE-ConfigU2U* [1459](#sl-relayue-configu2u)

-- *SL-RemoteUE-Config* [1460](#sl-remoteue-config)

*--* *SL-RemoteUE-ConfigU2U* [1461](#sl-remoteue-configu2u)

-- *SL-ReportConfigList* [1462](#sl-reportconfiglist)

-- *SL-ResourcePool* [1464](#sl-resourcepool)

-- *SL-RLC-BearerConfig* [1476](#sl-rlc-bearerconfig)

-- *SL-RLC-BearerConfigIndex* [1477](#sl-rlc-bearerconfigindex)

-- *SL-RLC-ChannelConfig* [1477](#sl-rlc-channelconfig)

-- *SL-RLC-ChannelID* [1478](#sl-rlc-channelid)

-- *SL-RLC-Config* [1478](#sl-rlc-config)

-- *SL-ScheduledConfig* [1479](#sl-scheduledconfig)

-- *SL-SDAP-Config* [1481](#sl-sdap-config)

-- *SL-ServingCellInfo* [1482](#sl-servingcellinfo)

-- *SL-SourceIdentity* [1483](#sl-sourceidentity)

-- *SL-SRAP-Config* [1483](#sl-srap-config)

-- *SL-SRAP-ConfigU2U* [1484](#sl-srap-configu2u)

-- *SL-SyncConfig* [1485](#sl-syncconfig)

-- *SL-Thres-RSRP-List* [1487](#sl-thres-rsrp-list)

-- *SL-TxPower* [1488](#sl-txpower)

-- *SL-TypeTxSync* [1488](#sl-typetxsync)

-- *SL-UE-SelectedConfig* [1489](#sl-ue-selectedconfig)

-- *SL-ZoneConfig* [1490](#sl-zoneconfig)

-- *SLRB-Uu-ConfigIndex* [1490](#slrb-uu-configindex)

6.3.6 MBS information elements [1491](#mbs-information-elements)

-- *CarrierFreqListMBS* [1491](#carrierfreqlistmbs)

-- *CFR-ConfigMCCH-MTCH* [1491](#cfr-configmcch-mtch)

-- *DRX-ConfigPTM* [1492](#drx-configptm)

-- *MBS-NeighbourCellList* [1494](#mbs-neighbourcelllist)

-- *MBS-NonServingInfoList* [1494](#mbs-nonservinginfolist)

-- *MBS-ServiceList* [1496](#mbs-servicelist)

-- *MBS-SessionInfoList* [1496](#mbs-sessioninfolist)

-- *MBS-SessionInfoListMulticast* [1499](#mbs-sessioninfolistmulticast)

-- *MTCH-SSB-MappingWindowList* [1502](#mtch-ssb-mappingwindowlist)

-- *PDSCH-ConfigBroadcast* [1503](#pdsch-configbroadcast)

-- *TMGI* [1504](#tmgi)

6.4 RRC multiplicity and type constraint values
[1505](#rrc-multiplicity-and-type-constraint-values)

-- Multiplicity and type constraint definitions
[1505](#multiplicity-and-type-constraint-definitions)

-- End of NR-RRC-Definitions [1514](#end-of-nr-rrc-definitions)

6.5 Short Message [1515](#short-message)

6.6 PC5 RRC messages [1515](#pc5-rrc-messages)

6.6.1 General message structure [1515](#general-message-structure-1)

-- *PC5-RRC-Definitions* [1515](#pc5-rrc-definitions)

-- *SBCCH-SL-BCH-Message* [1517](#sbcch-sl-bch-message)

-- *SCCH-Message* [1517](#scch-message)

6.6.2 Message definitions [1518](#_Toc193463744)

-- *MasterInformationBlockSidelink*
[1518](#masterinformationblocksidelink)

-- *MeasurementReportSidelink* [1519](#measurementreportsidelink)

-- *NotificationMessageSidelink* [1520](#notificationmessagesidelink)

-- *RemoteUEInformationSidelink* [1521](#remoteueinformationsidelink)

-- *RRCReconfigurationSidelink* [1523](#rrcreconfigurationsidelink)

-- *RRCReconfigurationCompleteSidelink*
[1528](#rrcreconfigurationcompletesidelink)

-- *RRCReconfigurationFailureSidelink*
[1529](#rrcreconfigurationfailuresidelink)

-- *UEAssistanceInformationSidelink*
[1530](#ueassistanceinformationsidelink)

-- *UECapabilityEnquirySidelink* [1531](#uecapabilityenquirysidelink)

-- *UECapabilityInformationSidelink*
[1532](#uecapabilityinformationsidelink)

*--* *UEInformationRequestSidelink*
[1535](#ueinformationrequestsidelink)

-- *UEInformationResponseSidelink*
[1536](#ueinformationresponsesidelink)

-- *UuMessageTransferSidelink* [1537](#uumessagetransfersidelink)

-- *End of PC5-RRC-Definitions* [1538](#end-of-pc5-rrc-definitions)

7 Variables and constants [1539](#variables-and-constants)

7.1 Timers [1539](#timers)

7.1.1 Timers (Informative) [1539](#timers-informative)

7.1.2 Timer handling [1550](#timer-handling)

7.2 Counters [1551](#counters)

7.3 Constants [1551](#constants)

7.4 UE variables [1551](#ue-variables)

-- *NR-UE-Variables* [1551](#nr-ue-variables)

-- *VarAppLayerIdleConfig* [1553](#varapplayeridleconfig)

-- *VarAppLayerPLMN-ListConfig* [1554](#varapplayerplmn-listconfig)

-- *VarConditionalReconfig* [1554](#varconditionalreconfig)

-- *VarConnEstFailReport* [1555](#varconnestfailreport)

-- *VarConnEstFailReportList* [1555](#varconnestfailreportlist)

-- *VarLogMeasConfig* [1556](#varlogmeasconfig)

-- *VarLogMeasReport* [1556](#varlogmeasreport)

-- *VarLTM-ServingCellNoResetID* [1557](#varltm-servingcellnoresetid)

-- *VarLTM-ServingCellUE-MeasuredTA-ID*
[1557](#varltm-servingcellue-measuredta-id)

-- *VarMeasConfig* [1557](#varmeasconfig)

-- *VarMeasConfigSL* [1558](#varmeasconfigsl)

-- *VarMeasIdleConfig* [1559](#varmeasidleconfig)

-- *VarMeasIdleReport* [1559](#varmeasidlereport)

-- *VarMeasReportList* [1559](#varmeasreportlist)

-- *VarMeasReportListSL* [1560](#varmeasreportlistsl)

-- *VarMeasReselectionConfig* [1561](#varmeasreselectionconfig)

-- *VarMobilityHistoryReport* [1561](#varmobilityhistoryreport)

-- *VarPendingRNA-Update* [1562](#varpendingrna-update)

-- *VarRA-Report* [1562](#varra-report)

-- *VarResumeMAC-Input* [1562](#varresumemac-input)

-- *VarRLF-Report* [1563](#varrlf-report)

-- *VarServingSecurityCellSetID* [1563](#varservingsecuritycellsetid)

-- *VarShortMAC-Input* [1564](#varshortmac-input)

-- *VarSuccessHO-Report* [1564](#varsuccessho-report)

-- *VarSuccessPSCell-Report* [1565](#varsuccesspscell-report)

-- *VarTSS-Info* [1565](#vartss-info)

-- End of *NR-UE-Variables* [1566](#end-of-nr-ue-variables)

8 Protocol data unit abstract syntax
[1567](#protocol-data-unit-abstract-syntax)

8.1 General [1567](#general-69)

8.2 Structure of encoded RRC messages
[1567](#structure-of-encoded-rrc-messages)

8.3 Basic production [1567](#basic-production)

8.4 Extension [1567](#extension)

8.5 Padding [1568](#padding)

9 Specified and default radio configurations
[1568](#specified-and-default-radio-configurations)

9.1 Specified configurations [1568](#specified-configurations)

9.1.1 Logical channel configurations
[1568](#logical-channel-configurations)

9.1.1.1 BCCH configuration [1568](#bcch-configuration)

9.1.1.2 CCCH configuration [1569](#ccch-configuration)

9.1.1.3 PCCH configuration [1569](#pcch-configuration)

9.1.1.4 SCCH configuration [1569](#scch-configuration)

9.1.1.5 STCH configuration [1576](#stch-configuration)

9.1.1.6 MCCH configuration [1577](#mcch-configuration)

9.1.1.7 MTCH configuration for MBS broadcast
[1577](#mtch-configuration-for-mbs-broadcast)

9.1.2 Void [1578](#void-16)

9.2 Default radio configurations [1578](#default-radio-configurations)

9.2.1 Default SRB configurations [1578](#default-srb-configurations)

9.2.2 Default MAC Cell Group configuration
[1578](#default-mac-cell-group-configuration)

9.2.3 Default values timers and constants
[1578](#default-values-timers-and-constants)

9.2.4 Default PC5 Relay RLC Channel
[1579](#default-pc5-relay-rlc-channel)

9.2.5 Default SRAP configurations [1579](#default-srap-configurations)

9.3 Sidelink pre-configured parameters
[1580](#sidelink-pre-configured-parameters)

-- *NR-Sidelink-Preconf* [1580](#nr-sidelink-preconf)

-- *SL-PreconfigurationNR* [1580](#sl-preconfigurationnr)

-- *End of NR-Sidelink-Preconf* [1584](#end-of-nr-sidelink-preconf)

9.4 Radio Information Related to Discovery Message
[1584](#_Toc193463821)

-- *SL-AccessInfo-L2U2N* [1584](#sl-accessinfo-l2u2n)

9.5 Void [1586](#void-17)

10 Generic error handling [1586](#generic-error-handling)

10.1 General [1586](#general-70)

10.2 ASN.1 violation or encoding error
[1586](#asn.1-violation-or-encoding-error)

10.3 Field set to a not comprehended value
[1586](#field-set-to-a-not-comprehended-value)

10.4 Mandatory field missing [1586](#mandatory-field-missing)

10.5 Not comprehended field [1588](#not-comprehended-field)

11 Radio information related interactions between network nodes
[1589](#radio-information-related-interactions-between-network-nodes)

11.1 General [1589](#general-71)

11.2 Inter-node RRC messages [1589](#inter-node-rrc-messages)

11.2.1 General [1589](#general-72)

11.2.2 Message definitions [1591](#message-definitions-1)

-- *CG-CandidateList* [1591](#cg-candidatelist)

-- *HandoverCommand* [1592](#handovercommand)

-- *HandoverPreparationInformation*
[1593](#handoverpreparationinformation)

-- *CG-Config* [1598](#cg-config)

*--* *CG-ConfigInfo* [1608](#cg-configinfo)

-- *MeasurementTimingConfiguration*
[1622](#measurementtimingconfiguration)

-- *UERadioPagingInformation* [1624](#ueradiopaginginformation)

-- *UERadioAccessCapabilityInformation*
[1626](#ueradioaccesscapabilityinformation)

11.2.3 Mandatory information in inter-node RRC messages
[1627](#mandatory-information-in-inter-node-rrc-messages)

11.3 Inter-node RRC information element definitions
[1629](#inter-node-rrc-information-element-definitions)

*--* *L1-MeasConfigNRDC* [1629](#l1-measconfignrdc)

*--* *LTM-ResourceConfigNRDC* [1630](#ltm-resourceconfignrdc)

-- *ResourceConfigNRDC* [1632](#resourceconfignrdc)

11.4 Inter-node RRC multiplicity and type constraint values
[1633](#inter-node-rrc-multiplicity-and-type-constraint-values)

-- Multiplicity and type constraints definitions
[1633](#multiplicity-and-type-constraints-definitions)

-- *End of NR-InterNodeDefinitions*
[1634](#end-of-nr-internodedefinitions)

12 Processing delay requirements for RRC procedures
[1635](#processing-delay-requirements-for-rrc-procedures)

Annex A (informative): Guidelines mainly on use of ASN.1
[1640](#annex-a-informative-guidelines-mainly-on-use-of-asn.1)

A.1 Introduction [1640](#a.1-introduction)

A.2 Procedural specification [1640](#a.2-procedural-specification)

A.2.1 General principles [1640](#a.2.1-general-principles)

A.2.2 More detailed aspects [1640](#a.2.2-more-detailed-aspects)

A.3 PDU specification [1641](#a.3-pdu-specification)

A.3.1 General principles [1641](#a.3.1-general-principles)

A.3.1.1 ASN.1 clauses [1641](#a.3.1.1-asn.1-clauses)

A.3.1.2 ASN.1 identifier naming conventions
[1642](#a.3.1.2-asn.1-identifier-naming-conventions)

A.3.1.3 Text references using ASN.1 identifiers
[1643](#a.3.1.3-text-references-using-asn.1-identifiers)

A.3.2 High-level message structure
[1644](#a.3.2-high-level-message-structure)

A.3.3 Message definition [1645](#a.3.3-message-definition)

A.3.4 Information elements [1647](#a.3.4-information-elements)

A.3.5 Fields with optional presence
[1648](#a.3.5-fields-with-optional-presence)

A.3.6 Fields with conditional presence
[1649](#a.3.6-fields-with-conditional-presence)

A.3.7 Guidelines on use of lists with elements of SEQUENCE type
[1650](#a.3.7-guidelines-on-use-of-lists-with-elements-of-sequence-type)

A.3.8 Guidelines on use of parameterised SetupRelease type
[1650](#a.3.8-guidelines-on-use-of-parameterised-setuprelease-type)

A.3.9 Guidelines on use of ToAddModList and ToReleaseList
[1652](#a.3.9-guidelines-on-use-of-toaddmodlist-and-toreleaselist)

A.3.10 Guidelines on use of lists (without ToAddModList and
ToReleaseList)
[1653](#a.3.10-guidelines-on-use-of-lists-without-toaddmodlist-and-toreleaselist)

A.4 Extension of the PDU specifications
[1654](#a.4-extension-of-the-pdu-specifications)

A.4.1 General principles to ensure compatibility
[1654](#a.4.1-general-principles-to-ensure-compatibility)

A.4.2 Critical extension of messages and fields
[1654](#a.4.2-critical-extension-of-messages-and-fields)

A.4.3 Non-critical extension of messages
[1657](#a.4.3-non-critical-extension-of-messages)

A.4.3.1 General principles [1657](#a.4.3.1-general-principles)

A.4.3.2 Further guidelines [1658](#a.4.3.2-further-guidelines)

A.4.3.3 Typical example of evolution of IE with local extensions
[1659](#a.4.3.3-typical-example-of-evolution-of-ie-with-local-extensions)

A.4.3.4 Typical examples of non critical extension at the end of a
message
[1660](#a.4.3.4-typical-examples-of-non-critical-extension-at-the-end-of-a-message)

A.4.3.5 Examples of non-critical extensions not placed at the default
extension location
[1661](#a.4.3.5-examples-of-non-critical-extensions-not-placed-at-the-default-extension-location)

-- *ParentIE-WithEM* [1661](#parentie-withem)

*--* *ChildIE1-WithoutEM* [1661](#childie1-withoutem)

*--* *ChildIE2-WithoutEM* [1662](#childie2-withoutem)

A.4.3.6 Non-critical extensions of lists with ToAddMod/ToRelease
[1663](#_Toc46440049)

A.5 Guidelines regarding inclusion of transaction identifiers in RRC
messages
[1666](#a.5-guidelines-regarding-inclusion-of-transaction-identifiers-in-rrc-messages)

A.6 Guidelines regarding use of need codes
[1667](#a.6-guidelines-regarding-use-of-need-codes)

A.7 Guidelines regarding use of conditions
[1667](#a.7-guidelines-regarding-use-of-conditions)

A.8 Miscellaneous [1668](#a.8-miscellaneous)

Annex B (informative): RRC Information
[1669](#annex-b-informative-rrc-information)

B.1 Protection of RRC messages [1669](#b.1-protection-of-rrc-messages)

B.2 Description of BWP configuration options
[1671](#b.2-description-of-bwp-configuration-options)

Annex C (normative): List of CRs Containing Early Implementable Features
and Corrections
[1673](#annex-c-normative-list-of-crs-containing-early-implementable-features-and-corrections)

Annex D (normative): UE requirements on ASN.1 comprehension
[1678](#annex-d-normative-ue-requirements-on-asn.1-comprehension)

Annex E (informative): Change history
[1680](#annex-e-informative-change-history)