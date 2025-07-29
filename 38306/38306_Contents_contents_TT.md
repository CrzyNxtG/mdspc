#  Contents {#contents .TT}

Foreword [6](#foreword)

1 Scope [7](#scope)

2 References [7](#references)

3 Definitions, symbols and abbreviations
[8](#definitions-symbols-and-abbreviations)

3.1 Definitions [8](#definitions)

3.2 Symbols [9](#symbols)

3.3 Abbreviations [9](#abbreviations)

4 UE radio access capability parameters
[10](#ue-radio-access-capability-parameters)

4.1 Supported max data rate [10](#supported-max-data-rate)

4.1.1 General [10](#general)

4.1.2 Supported max data rate for DL/UL
[10](#supported-max-data-rate-for-dlul)

4.1.3 Void [12](#void)

4.1.4 Total layer 2 buffer size for DL/UL
[12](#total-layer-2-buffer-size-for-dlul)

4.1.5 Supported max data rate for SL
[12](#supported-max-data-rate-for-sl)

4.1.6 Total layer 2 buffer size for NR SL
[13](#total-layer-2-buffer-size-for-nr-sl)

4.2 UE Capability Parameters [13](#ue-capability-parameters)

4.2.1 Introduction [13](#introduction)

4.2.2 General parameters [16](#general-parameters)

4.2.3 SDAP Parameters [21](#sdap-parameters)

4.2.4 PDCP Parameters [22](#pdcp-parameters)

4.2.5 RLC parameters [25](#rlc-parameters)

4.2.6 MAC parameters [26](#mac-parameters)

4.2.6.1 *MAC-Parameters* [26](#mac-parameters-1)

4.2.6.2 *MAC-ParametersPerBand* [31](#mac-parametersperband)

4.2.7 Physical layer parameters [32](#physical-layer-parameters)

4.2.7.1 *BandCombinationList* parameters
[32](#bandcombinationlist-parameters)

4.2.7.2 *BandNR parameters* [44](#bandnr-parameters)

4.2.7.2a *SharedSpectrumChAccessParamsPerBand*
[143](#a-sharedspectrumchaccessparamsperband)

4.2.7.2b *FR2-2-AccessParamsPerBand* [149](#b-fr2-2-accessparamsperband)

4.2.7.3 *CA-ParametersEUTRA* [153](#ca-parameterseutra)

4.2.7.4 *CA-ParametersNR* [154](#ca-parametersnr)

4.2.7.5 *FeatureSetDownlink* parameters
[218](#featuresetdownlink-parameters)

4.2.7.6 *FeatureSetDownlinkPerCC* parameters
[232](#featuresetdownlinkpercc-parameters)

4.2.7.7 *FeatureSetUplink* parameters
[239](#featuresetuplink-parameters)

4.2.7.8 *FeatureSetUplinkPerCC* parameters
[260](#featuresetuplinkpercc-parameters)

4.2.7.9 *MRDC-Parameters* [268](#mrdc-parameters)

4.2.7.10 *Phy-Parameters* [273](#phy-parameters)

4.2.7.11 Other PHY parameters [292](#other-phy-parameters)

4.2.7.12 *NRDC-Parameters* [295](#nrdc-parameters)

4.2.7.13 *CarrierAggregationVariant* [297](#carrieraggregationvariant)

4.2.7.14 *Phy-ParametersSharedSpectrumChAccess*
[298](#phy-parameterssharedspectrumchaccess)

4.2.8 Void [300](#void-1)

4.2.9 *MeasAndMobParameters* [301](#measandmobparameters)

4.2.9a *MeasAndMobParametersMRDC* [314](#a-measandmobparametersmrdc)

4.2.10 Inter-RAT parameters [318](#inter-rat-parameters)

4.2.10.1 Void [318](#void-2)

4.2.10.2 Void [318](#void-3)

4.2.11 Void [318](#void-4)

4.2.12 Void [318](#void-5)

4.2.13 IMS Parameters [318](#ims-parameters)

4.2.14 RRC buffer size [319](#rrc-buffer-size)

4.2.15 IAB Parameters [319](#iab-parameters)

4.2.15.1 Mandatory IAB-MT features [319](#mandatory-iab-mt-features)

4.2.15.1a Mandatory mobile IAB-MT features
[325](#a-mandatory-mobile-iab-mt-features)

4.2.15.2 General Parameters [325](#general-parameters-1)

4.2.15.3 SDAP Parameters [325](#sdap-parameters-1)

4.2.15.4 PDCP Parameters [325](#pdcp-parameters-1)

4.2.15.5 BAP Parameters [326](#bap-parameters)

4.2.15.6 MAC Parameters [326](#mac-parameters-2)

4.2.15.7 Physical layer parameters [326](#physical-layer-parameters-1)

4.2.15.7.1 BandNR parameters [326](#bandnr-parameters-1)

4.2.15.7.2 Phy-Parameters [327](#phy-parameters-1)

4.2.15.8 MeasAndMobParameters Parameters
[329](#measandmobparameters-parameters)

4.2.15.9 MR-DC Parameters [329](#mr-dc-parameters)

4.2.15.10 NRDC Parameters [329](#nrdc-parameters-1)

4.2.16 Sidelink Parameters [330](#sidelink-parameters)

4.2.16.1 Sidelink Parameters in NR [330](#sidelink-parameters-in-nr)

4.2.16.1.1 Sidelink General Parameters
[330](#sidelink-general-parameters)

4.2.16.1.2 Sidelink PDCP Parameters [332](#sidelink-pdcp-parameters)

4.2.16.1.3 Sidelink RLC Parameters [332](#sidelink-rlc-parameters)

4.2.16.1.4 Sidelink MAC Parameters [333](#sidelink-mac-parameters)

4.2.16.1.5 Other PHY parameters [333](#other-phy-parameters-1)

4.2.16.1.6 *BandSidelink* Parameters [334](#bandsidelink-parameters)

4.2.16.1.6a *SharedSpectrumChAccessParamsSidelinkPerBand* Parameters
[348](#a-sharedspectrumchaccessparamssidelinkperband-parameters)

4.2.16.1.7 *BandCombinationListSidelinkEUTRA-NR* Parameters
[351](#bandcombinationlistsidelinkeutra-nr-parameters)

4.2.16.2 Sidelink Parameters in E-UTRA
[354](#sidelink-parameters-in-e-utra)

4.2.16.2.0 General [354](#general-1)

4.2.16.2.1 *BandSideLinkEUTRA* parameters
[355](#bandsidelinkeutra-parameters)

4.2.17 SON parameters [355](#son-parameters)

4.2.18 UE-based performance measurement parameters
[356](#ue-based-performance-measurement-parameters)

4.2.19 High speed parameters [357](#high-speed-parameters)

4.2.20 Application layer measurement parameters
[358](#application-layer-measurement-parameters)

4.2.21 RedCap Parameters [358](#redcap-parameters)

4.2.21.1 Definition of RedCap UE [358](#definition-of-redcap-ue)

4.2.21.2 General parameters [359](#general-parameters-2)

4.2.21.3 PDCP parameters [360](#pdcp-parameters-2)

4.2.21.4 RLC parameters [360](#rlc-parameters-1)

4.2.21.5 MeasAndMobParameters [360](#measandmobparameters-1)

4.2.21.6 Physical layer parameters [361](#physical-layer-parameters-2)

4.2.21.6.1 *BandNR* parameters [361](#bandnr-parameters-2)

4.2.21.7 SON parameters [364](#son-parameters-1)

4.2.22 eRedCap Parameters [365](#eredcap-parameters)

4.2.22.1 Definition of eRedCap UE [365](#definition-of-eredcap-ue)

4.2.22.2 General parameters [366](#general-parameters-3)

4.2.23 NCR Parameters [368](#ncr-parameters)

4.2.23.1 Mandatory NCR-MT features [368](#mandatory-ncr-mt-features)

4.2.23.2 General Parameters [375](#general-parameters-4)

4.2.23.3 SDAP Parameters [375](#sdap-parameters-2)

4.2.23.4 PDCP Parameters [375](#pdcp-parameters-3)

4.2.23.5 RLC Parameters [375](#rlc-parameters-2)

4.2.23.6 Physical layer Parameters [376](#physical-layer-parameters-3)

4.2.23.6.1 Phy-Parameters [376](#phy-parameters-2)

4.2.23.6.2 *BandNR parameters* [376](#bandnr-parameters-3)

4.2.24 Aerial UE Parameters [377](#aerial-ue-parameters)

5 Optional features without UE radio access capability parameters
[378](#optional-features-without-ue-radio-access-capability-parameters)

5.1 PWS features [378](#pws-features)

5.2 UE receiver features [378](#ue-receiver-features)

5.3 RRC connection [379](#rrc-connection)

5.4 Other features [380](#other-features)

5.5 Sidelink Features [381](#sidelink-features)

5.6 RRM measurement features [382](#rrm-measurement-features)

5.7 MDT and SON features [383](#mdt-and-son-features)

5.8 Extended DRX features [383](#extended-drx-features)

5.9 Sidelink Relay Features [384](#sidelink-relay-features)

5.10 MBS features [384](#mbs-features)

6 Conditionally mandatory features without UE radio access capability
parameters
[386](#conditionally-mandatory-features-without-ue-radio-access-capability-parameters)

7 Void [388](#void-6)

8 UE Capability Constraints [388](#ue-capability-constraints)

Annex A (normative): Differentiation of capabilities
[389](#annex-a-normative-differentiation-of-capabilities)

A.1: TDD/FDD differentiation of capabilities in TDD-FDD CA
[389](#a.1-tddfdd-differentiation-of-capabilities-in-tdd-fdd-ca)

A.2: FR1/FR2 differentiation of capabilities in FR1-FR2 CA
[390](#a.2-fr1fr2-differentiation-of-capabilities-in-fr1-fr2-ca)

A.3: TDD/FDD differentiation of capabilities for sidelink
[391](#a.3-tddfdd-differentiation-of-capabilities-for-sidelink)

A.4: Sidelink capabilities applicable to Uu and PC5
[392](#a.4-sidelink-capabilities-applicable-to-uu-and-pc5)

A.5: General differentiation of capabilities in Cross-Carrier operation
[396](#a.5-general-differentiation-of-capabilities-in-cross-carrier-operation)

Annex B (informative): UE capability indication for UE capabilities with
both FDD/TDD and FR1/FR2 differentiations
[398](#annex-b-informative-ue-capability-indication-for-ue-capabilities-with-both-fddtdd-and-fr1fr2-differentiations)

Annex C (informative): Change history
[400](#annex-c-informative-change-history)