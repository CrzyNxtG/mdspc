### 6.3.3 UE capability information elements

#### -- *AccessStratumRelease*

The IE *AccessStratumRelease* indicates the release supported by the UE.

*AccessStratumRelease* information element

\-- ASN1START

\-- TAG-ACCESSSTRATUMRELEASE-START

AccessStratumRelease ::= ENUMERATED {

rel15, rel16, rel17, rel18, spare4, spare3, spare2, spare1, \... }

\-- TAG-ACCESSSTRATUMRELEASE-STOP

\-- ASN1STOP

#### -- *AerialParameters*

The IE *AerialParameters* is used to convey the capabilities supported
by the UE for aerial operation.

*AerialParameters* information element

\-- ASN1START

\-- TAG-AERIALPARAMETERS-START

AerialParameters-r18 ::= SEQUENCE {

\-- Support of Aerial UE features

aerialUE-Capability-r18 ENUMERATED {supported} OPTIONAL,

\-- Support of altitude measurement and event H1/H2-triggered reporting

altitudeMeas-r18 ENUMERATED {supported} OPTIONAL,

\-- Support of altitude based measurement configuration of SSB-ToMeasure

altitudeBasedSSB-ToMeasure-r18 ENUMERATED {supported} OPTIONAL,

\-- Support of events A3H1, A3H2, A4H1, A4H2, A5H1, A5H2

eventAxHy-r18 ENUMERATED {supported} OPTIONAL,

\-- Support of flight path reporting

flightPathReporting-r18 ENUMERATED {supported} OPTIONAL,

\-- Support of flight path availability indication via UAI

flightPathAvailabilityIndicationUAI-r18 ENUMERATED {supported} OPTIONAL,

\-- Support of numberOfTriggeringCells for eventA3, eventA4, and
eventA5, and additionally, if the UE supports eventAxHy-r18,

\-- support of numberOfTriggeringCells for eventA3H1, eventA3H2,
eventA4H1, eventA4H2, eventA5H1, and eventA5H2

multipleCellsMeasExtension-r18 ENUMERATED {supported} OPTIONAL,

\-- Support of handling aerial-specific Ns value(s) and Pmax list
broadcasted by the cell

nr-NS-PmaxListAerial-r18 ENUMERATED {supported} OPTIONAL,

\-- Support of reporting only the measurement report corresponding to
the event with the smallest value between the

\-- altitude of the UAV and the altitude threshold for which the
altitude-related entering condition e.g. A3H1-2 is satisfied, when

\-- multiple events of the same type (Hx or AxHy) for the same MO (for
AxHy) are triggered simultaneously.

simulMultiTriggerSingleMeasReport-r18 ENUMERATED {supported} OPTIONAL,

\-- Support of A2X service(s) using PC5 Sidelink and dedicated resource
pool for A2X service(s)

sl-A2X-Service-r18 ENUMERATED {brid, daa, bridAndDAA} OPTIONAL,

\...

}

\-- TAG-AERIALPARAMETERS-STOP

\-- ASN1STOP

#### -- *AppLayerMeasParameters*

The IE *AppLayerMeasParameters* is used to convey the capabilities
supported by the UE for application layer measurements.

*AppLayerMeasParameters* information element

\-- ASN1START

\-- TAG-APPLAYERMEASPARAMETERS-START

AppLayerMeasParameters-r17 ::= SEQUENCE {

qoe-Streaming-MeasReport-r17 ENUMERATED {supported} OPTIONAL,

qoe-MTSI-MeasReport-r17 ENUMERATED {supported} OPTIONAL,

qoe-VR-MeasReport-r17 ENUMERATED {supported} OPTIONAL,

ran-VisibleQoE-Streaming-MeasReport-r17 ENUMERATED {supported} OPTIONAL,

ran-VisibleQoE-VR-MeasReport-r17 ENUMERATED {supported} OPTIONAL,

ul-MeasurementReportAppLayer-Seg-r17 ENUMERATED {supported} OPTIONAL,

\...,

\[\[

qoe-IdleInactiveMeasReport-r18 ENUMERATED {supported} OPTIONAL,

qoe-NRDC-MeasReport-r18 ENUMERATED {supported} OPTIONAL,

qoe-AdditionalMemoryMeasReport-r18 ENUMERATED {kB128, kB256, kB512,
kB1024} OPTIONAL,

qoe-PriorityBasedDiscarding-r18 ENUMERATED {supported} OPTIONAL,

srb5-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

\-- TAG-APPLAYERMEASPARAMETERS-STOP

\-- ASN1STOP

#### -- *BandCombinationList*

The IE *BandCombinationList* contains a list of NR CA, NR non-CA and/or
MR-DC band combinations (also including DL only or UL only band).

*BandCombinationList* information element

\-- ASN1START

\-- TAG-BANDCOMBINATIONLIST-START

BandCombinationList ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination

BandCombinationList-v1540 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1540

BandCombinationList-v1550 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1550

BandCombinationList-v1560 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1560

BandCombinationList-v1570 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1570

BandCombinationList-v1580 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1580

BandCombinationList-v1590 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1590

BandCombinationList-v15g0 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v15g0

BandCombinationList-v15n0 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v15n0

BandCombinationList-v1610 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1610

BandCombinationList-v1630 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1630

BandCombinationList-v1640 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1640

BandCombinationList-v1650 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1650

BandCombinationList-v1680 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1680

BandCombinationList-v1690 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1690

BandCombinationList-v16a0 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v16a0

BandCombinationList-v16j0 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v16j0

BandCombinationList-v1700 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1700

BandCombinationList-v1720 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1720

BandCombinationList-v1730 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1730

BandCombinationList-v1740 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1740

BandCombinationList-v1760 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1760

BandCombinationList-v1770 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1770

BandCombinationList-v1780 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1780

BandCombinationList-v1790 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1790

BandCombinationList-v17b0 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v17b0

BandCombinationList-v1800 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1800

BandCombinationList-v1830 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1830

BandCombinationList-v1840 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1840

BandCombinationList-v1860 ::= SEQUENCE (SIZE (1..maxBandComb)) OF
BandCombination-v1860

BandCombinationList-UplinkTxSwitch-r16 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-r16

BandCombinationList-UplinkTxSwitch-v1630 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1630

BandCombinationList-UplinkTxSwitch-v1640 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1640

BandCombinationList-UplinkTxSwitch-v1650 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1650

BandCombinationList-UplinkTxSwitch-v1670 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1670

BandCombinationList-UplinkTxSwitch-v1690 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1690

BandCombinationList-UplinkTxSwitch-v16a0 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v16a0

BandCombinationList-UplinkTxSwitch-v16e0 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v16e0

BandCombinationList-UplinkTxSwitch-v16j0 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v16j0

BandCombinationList-UplinkTxSwitch-v1700 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1700

BandCombinationList-UplinkTxSwitch-v1720 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1720

BandCombinationList-UplinkTxSwitch-v1730 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1730

BandCombinationList-UplinkTxSwitch-v1740 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1740

BandCombinationList-UplinkTxSwitch-v1760 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1760

BandCombinationList-UplinkTxSwitch-v1770 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1770

BandCombinationList-UplinkTxSwitch-v1780 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1780

BandCombinationList-UplinkTxSwitch-v1790 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1790

BandCombinationList-UplinkTxSwitch-v17b0 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v17b0

BandCombinationList-UplinkTxSwitch-v1800 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1800

BandCombinationList-UplinkTxSwitch-v1830 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1830

BandCombinationList-UplinkTxSwitch-v1840 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1840

BandCombinationList-UplinkTxSwitch-v1860 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombination-UplinkTxSwitch-v1860

BandCombination ::= SEQUENCE {

bandList SEQUENCE (SIZE (1..maxSimultaneousBands)) OF BandParameters,

featureSetCombination FeatureSetCombinationId,

ca-ParametersEUTRA CA-ParametersEUTRA OPTIONAL,

ca-ParametersNR CA-ParametersNR OPTIONAL,

mrdc-Parameters MRDC-Parameters OPTIONAL,

supportedBandwidthCombinationSet BIT STRING (SIZE (1..32)) OPTIONAL,

powerClass-v1530 ENUMERATED {pc2} OPTIONAL

}

BandCombination-v1540::= SEQUENCE {

bandList-v1540 SEQUENCE (SIZE (1..maxSimultaneousBands)) OF
BandParameters-v1540,

ca-ParametersNR-v1540 CA-ParametersNR-v1540 OPTIONAL

}

BandCombination-v1550 ::= SEQUENCE {

ca-ParametersNR-v1550 CA-ParametersNR-v1550

}

BandCombination-v1560::= SEQUENCE {

ne-DC-BC ENUMERATED {supported} OPTIONAL,

ca-ParametersNRDC CA-ParametersNRDC OPTIONAL,

ca-ParametersEUTRA-v1560 CA-ParametersEUTRA-v1560 OPTIONAL,

ca-ParametersNR-v1560 CA-ParametersNR-v1560 OPTIONAL

}

BandCombination-v1570 ::= SEQUENCE {

ca-ParametersEUTRA-v1570 CA-ParametersEUTRA-v1570

}

BandCombination-v1580 ::= SEQUENCE {

mrdc-Parameters-v1580 MRDC-Parameters-v1580

}

BandCombination-v1590::= SEQUENCE {

supportedBandwidthCombinationSetIntraENDC BIT STRING (SIZE (1..32))
OPTIONAL,

mrdc-Parameters-v1590 MRDC-Parameters-v1590

}

BandCombination-v15g0::= SEQUENCE {

ca-ParametersNR-v15g0 CA-ParametersNR-v15g0 OPTIONAL,

ca-ParametersNRDC-v15g0 CA-ParametersNRDC-v15g0 OPTIONAL,

mrdc-Parameters-v15g0 MRDC-Parameters-v15g0 OPTIONAL

}

BandCombination-v15n0::= SEQUENCE {

mrdc-Parameters-v15n0 MRDC-Parameters-v15n0

}

BandCombination-v1610 ::= SEQUENCE {

bandList-v1610 SEQUENCE (SIZE (1..maxSimultaneousBands)) OF
BandParameters-v1610 OPTIONAL,

ca-ParametersNR-v1610 CA-ParametersNR-v1610 OPTIONAL,

ca-ParametersNRDC-v1610 CA-ParametersNRDC-v1610 OPTIONAL,

powerClass-v1610 ENUMERATED {pc1dot5} OPTIONAL,

powerClassNRPart-r16 ENUMERATED {pc1, pc2, pc3, pc5} OPTIONAL,

featureSetCombinationDAPS-r16 FeatureSetCombinationId OPTIONAL,

mrdc-Parameters-v1620 MRDC-Parameters-v1620 OPTIONAL

}

BandCombination-v1630 ::= SEQUENCE {

ca-ParametersNR-v1630 CA-ParametersNR-v1630 OPTIONAL,

ca-ParametersNRDC-v1630 CA-ParametersNRDC-v1630 OPTIONAL,

mrdc-Parameters-v1630 MRDC-Parameters-v1630 OPTIONAL,

supportedTxBandCombListPerBC-Sidelink-r16 BIT STRING (SIZE
(1..maxBandComb)) OPTIONAL,

supportedRxBandCombListPerBC-Sidelink-r16 BIT STRING (SIZE
(1..maxBandComb)) OPTIONAL,

scalingFactorTxSidelink-r16 SEQUENCE (SIZE (1..maxBandComb)) OF
ScalingFactorSidelink-r16 OPTIONAL,

scalingFactorRxSidelink-r16 SEQUENCE (SIZE (1..maxBandComb)) OF
ScalingFactorSidelink-r16 OPTIONAL

}

BandCombination-v1640 ::= SEQUENCE {

ca-ParametersNR-v1640 CA-ParametersNR-v1640 OPTIONAL,

ca-ParametersNRDC-v1640 CA-ParametersNRDC-v1640 OPTIONAL

}

BandCombination-v1650 ::= SEQUENCE {

ca-ParametersNRDC-v1650 CA-ParametersNRDC-v1650 OPTIONAL

}

BandCombination-v1680 ::= SEQUENCE {

intrabandConcurrentOperationPowerClass-r16 SEQUENCE (SIZE
(1..maxBandComb)) OF IntraBandPowerClass-r16 OPTIONAL

}

BandCombination-v1690 ::= SEQUENCE {

dummy CA-ParametersNR-v1690 OPTIONAL

}

BandCombination-v16a0 ::= SEQUENCE {

ca-ParametersNR-v16a0 CA-ParametersNR-v16a0 OPTIONAL,

ca-ParametersNRDC-v16a0 CA-ParametersNRDC-v16a0 OPTIONAL

}

BandCombination-v16j0::= SEQUENCE {

ca-ParametersNR-v16j0 CA-ParametersNR-v1690 OPTIONAL,

ca-ParametersNRDC-v16j0 CA-ParametersNRDC-v16j0 OPTIONAL

}

BandCombination-v1700 ::= SEQUENCE {

ca-ParametersNR-v1700 CA-ParametersNR-v1700 OPTIONAL,

ca-ParametersNRDC-v1700 CA-ParametersNRDC-v1700 OPTIONAL,

mrdc-Parameters-v1700 MRDC-Parameters-v1700 OPTIONAL,

bandList-v1710 SEQUENCE (SIZE (1..maxSimultaneousBands)) OF
BandParameters-v1710 OPTIONAL,

supportedBandCombListPerBC-SL-RelayDiscovery-r17 BIT STRING (SIZE
(1..maxBandComb)) OPTIONAL,

supportedBandCombListPerBC-SL-NonRelayDiscovery-r17 BIT STRING (SIZE
(1..maxBandComb)) OPTIONAL

}

BandCombination-v1720 ::= SEQUENCE {

ca-ParametersNR-v1720 CA-ParametersNR-v1720 OPTIONAL,

ca-ParametersNRDC-v1720 CA-ParametersNRDC-v1720 OPTIONAL

}

BandCombination-v1730 ::= SEQUENCE {

ca-ParametersNR-v1730 CA-ParametersNR-v1730 OPTIONAL,

ca-ParametersNRDC-v1730 CA-ParametersNRDC-v1730 OPTIONAL,

bandList-v1730 SEQUENCE (SIZE (1..maxSimultaneousBands)) OF
BandParameters-v1730 OPTIONAL

}

BandCombination-v1740 ::= SEQUENCE {

dummy CA-ParametersNR-v1740 OPTIONAL

}

BandCombination-v1760 ::= SEQUENCE {

ca-ParametersNR-v1760 CA-ParametersNR-v1760,

ca-ParametersNRDC-v1760 CA-ParametersNRDC-v1760

}

BandCombination-v1770::= SEQUENCE {

bandList-v1770 SEQUENCE (SIZE (1..maxSimultaneousBands)) OF
BandParameters-v1770,

mrdc-Parameters-v1770 MRDC-Parameters-v1770 OPTIONAL,

ca-ParametersNR-v1770 CA-ParametersNR-v1770 OPTIONAL

}

BandCombination-v1780 ::= SEQUENCE {

ca-ParametersNR-v1780 CA-ParametersNR-v1780 OPTIONAL,

ca-ParametersNRDC-v1780 CA-ParametersNRDC-v1780 OPTIONAL,

bandList-v1780 SEQUENCE (SIZE (1..maxSimultaneousBands)) OF
BandParameters-v1780 OPTIONAL,

mrdc-Parameters-v1780 MRDC-Parameters-v1770 OPTIONAL

}

BandCombination-v1790 ::= SEQUENCE {

supportedIntraENDC-BandCombinationList-r17 SEQUENCE (SIZE
(1..maxNrofIntraEndc-Components-r17)) OF
SupportedIntraENDC-BandCombination-r17 OPTIONAL

}

BandCombination-v17b0::= SEQUENCE {

ca-ParametersNR-v17b0 CA-ParametersNR-v1740 OPTIONAL,

ca-ParametersNRDC-v17b0 CA-ParametersNRDC-v17b0 OPTIONAL

}

BandCombination-v1800 ::= SEQUENCE {

ca-ParametersNR-v1800 CA-ParametersNR-v1800 OPTIONAL,

ca-ParametersNRDC-v1800 CA-ParametersNRDC-v1800 OPTIONAL,

supportedBandCombListPerBC-SL-U2U-RelayDiscovery-r18 BIT STRING (SIZE
(1..maxBandComb)) OPTIONAL,

bandList-v1810 SEQUENCE (SIZE (1..maxSimultaneousBands)) OF
BandParameters-v1810 OPTIONAL

}

BandCombination-v1830 ::= SEQUENCE {

ca-ParametersNR-v1830 CA-ParametersNR-v1830 OPTIONAL,

ca-ParametersNRDC-v1830 CA-ParametersNRDC-v1830 OPTIONAL

}

BandCombination-v1840 ::= SEQUENCE {

mrdc-Parameters-v1840 MRDC-Parameters-v1840 OPTIONAL

}

BandCombination-v1860 ::= SEQUENCE {

ca-ParametersNR-v1860 CA-ParametersNR-v1860 OPTIONAL

}

BandCombination-UplinkTxSwitch-r16 ::= SEQUENCE {

bandCombination-r16 BandCombination,

bandCombination-v1540 BandCombination-v1540 OPTIONAL,

bandCombination-v1560 BandCombination-v1560 OPTIONAL,

bandCombination-v1570 BandCombination-v1570 OPTIONAL,

bandCombination-v1580 BandCombination-v1580 OPTIONAL,

bandCombination-v1590 BandCombination-v1590 OPTIONAL,

bandCombination-v1610 BandCombination-v1610 OPTIONAL,

supportedBandPairListNR-r16 SEQUENCE (SIZE
(1..maxULTxSwitchingBandPairs)) OF ULTxSwitchingBandPair-r16,

uplinkTxSwitching-OptionSupport-r16 ENUMERATED {switchedUL, dualUL,
both} OPTIONAL,

uplinkTxSwitching-PowerBoosting-r16 ENUMERATED {supported} OPTIONAL,

\...,

\[\[

\-- R4 16-5 UL-MIMO coherence capability for dynamic Tx switching
between 3CC 1Tx-2Tx switching

uplinkTxSwitching-PUSCH-TransCoherence-r16 ENUMERATED {nonCoherent,
fullCoherent} OPTIONAL

\]\]

}

BandCombination-UplinkTxSwitch-v1630 ::= SEQUENCE {

bandCombination-v1630 BandCombination-v1630 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1640 ::= SEQUENCE {

bandCombination-v1640 BandCombination-v1640 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1650 ::= SEQUENCE {

bandCombination-v1650 BandCombination-v1650 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1670 ::= SEQUENCE {

bandCombination-v15g0 BandCombination-v15g0 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1690 ::= SEQUENCE {

bandCombination-v1690 BandCombination-v1690 OPTIONAL

}

BandCombination-UplinkTxSwitch-v16a0 ::= SEQUENCE {

bandCombination-v16a0 BandCombination-v16a0 OPTIONAL

}

BandCombination-UplinkTxSwitch-v16e0 ::= SEQUENCE {

bandCombination-v15n0 BandCombination-v15n0 OPTIONAL

}

BandCombination-UplinkTxSwitch-v16j0 ::= SEQUENCE {

bandCombination-v16j0 BandCombination-v16j0 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1700 ::= SEQUENCE {

bandCombination-v1700 BandCombination-v1700 OPTIONAL,

\-- R4 16-1/16-2/16-3 Dynamic Tx switching between 2CC/3CC
2Tx-2Tx/1Tx-2Tx switching

supportedBandPairListNR-v1700 SEQUENCE (SIZE
(1..maxULTxSwitchingBandPairs)) OF ULTxSwitchingBandPair-v1700 OPTIONAL,

\-- R4 16-6: UL-MIMO coherence capability for dynamic Tx switching
between 2Tx-2Tx switching

uplinkTxSwitchingBandParametersList-v1700 SEQUENCE (SIZE (1..
maxSimultaneousBands)) OF UplinkTxSwitchingBandParameters-v1700 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1720 ::= SEQUENCE {

bandCombination-v1720 BandCombination-v1720 OPTIONAL,

uplinkTxSwitching-OptionSupport2T2T-r17 ENUMERATED {switchedUL, dualUL,
both} OPTIONAL

}

BandCombination-UplinkTxSwitch-v1730 ::= SEQUENCE {

bandCombination-v1730 BandCombination-v1730 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1740 ::= SEQUENCE {

bandCombination-v1740 BandCombination-v1740 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1760 ::= SEQUENCE {

bandCombination-v1760 BandCombination-v1760 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1770 ::= SEQUENCE {

bandCombination-v1770 BandCombination-v1770 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1780 ::= SEQUENCE {

bandCombination-v1780 BandCombination-v1780 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1790 ::= SEQUENCE {

bandCombination-v1790 BandCombination-v1790 OPTIONAL

}

BandCombination-UplinkTxSwitch-v17b0 ::= SEQUENCE {

bandCombination-v17b0 BandCombination-v17b0 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1800 ::= SEQUENCE {

bandCombination-v1800 BandCombination-v1800 OPTIONAL,

supportedBandPairListNR-r18 SEQUENCE (SIZE
(1..maxULTxSwitchingBandPairs)) OF ULTxSwitchingBandPair-r18 OPTIONAL,

\-- R1 49-Y: Minimum separation time for two uplink switching on more
than 2 bands within any two consecutive reference slots

uplinkTxSwitchingMinimumSeparationTime-r18 ENUMERATED {n0us, n500us}
OPTIONAL,

\-- R4 38-4: Switching Period for unaffected Band for Dual UL

uplinkTxSwitchingAdditionalPeriodDualUL-List-r18 SEQUENCE (SIZE
(1..maxULTxSwitchingBetweenBandPairs-r18)) OF

UplinkTxSwitchingAdditionalPeriodDualUL-r18 OPTIONAL,

\-- R4 38-6: Switching period restriction for fallback band combination

switchingPeriodRestriction-r18 ENUMERATED {true} OPTIONAL

}

BandCombination-UplinkTxSwitch-v1830 ::= SEQUENCE {

bandCombination-v1830 BandCombination-v1830 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1840 ::= SEQUENCE {

bandCombination-v1840 BandCombination-v1840 OPTIONAL,

supportedBandPairListNR-v1840 SEQUENCE (SIZE
(1..maxULTxSwitchingBandPairs)) OF ULTxSwitchingBandPair-v1840 OPTIONAL

}

BandCombination-UplinkTxSwitch-v1860 ::= SEQUENCE {

bandCombination-v1860 BandCombination-v1860 OPTIONAL

}

ULTxSwitchingBandPair-r16 ::= SEQUENCE {

bandIndexUL1-r16 INTEGER(1..maxSimultaneousBands),

bandIndexUL2-r16 INTEGER(1..maxSimultaneousBands),

uplinkTxSwitchingPeriod-r16 ENUMERATED {n35us, n140us, n210us},

uplinkTxSwitching-DL-Interruption-r16 BIT STRING
(SIZE(1..maxSimultaneousBands)) OPTIONAL

}

ULTxSwitchingBandPair-v1700 ::= SEQUENCE {

uplinkTxSwitchingPeriod2T2T-r17 ENUMERATED {n35us, n140us, n210us}
OPTIONAL

}

ULTxSwitchingBandPair-r18 ::= SEQUENCE {

bandIndexUL1-r18 INTEGER(1..maxSimultaneousBands),

bandIndexUL2-r18 INTEGER(1..maxSimultaneousBands),

\-- R1 49-X: Supported switching option for each band pair in the band
combination for UL Tx switching across more than 2 bands

uplinkTxSwitchingOptionForBandPair-r18 ENUMERATED {switchedUL, dualUL,
both},

\-- R4 38-1: Switching period for dynamic UL Tx switching across up to 4
bands in case of inter-band CA, SUL up to two TAGs

uplinkTxSwitchingPeriodForBandPair-r18 SEQUENCE {

switchingPeriodFor2T-r18 ENUMERATED {n35us, n140us, n210us} OPTIONAL,

switchingPeriodFor1T-r18 ENUMERATED {n35us, n140us, n210us}

},

\-- R4 38-2: Application of DL interruptions due to dynamic UL Tx
switching

uplinkTxSwitching-DL-Interruption-r18 BIT STRING
(SIZE(1..maxSimultaneousBands)) OPTIONAL,

\-- R4 38-3: Switching Period for unaffected Band for Dual UL

uplinkTxSwitchingPeriodUnaffectedBandDualUL-List-r18 SEQUENCE (SIZE
(1..maxSimultaneousBands-2-r18)) OF

SwitchingPeriodUnaffectedBandDualUL-r18 OPTIONAL

}

ULTxSwitchingBandPair-v1840 ::= SEQUENCE {

\-- R1 49-Z: Support of 2-band configuration of 1T-1T UL Tx switching by
using Rel-18 UL Tx switching configurations

configured1T1T-OnTwoBands-r18 ENUMERATED {supported} OPTIONAL

}

UplinkTxSwitchingBandParameters-v1700 ::= SEQUENCE {

bandIndex-r17 INTEGER(1..maxSimultaneousBands),

\-- R4 38-5: UL-MIMO coherence capability for dynamic Tx switching
between 2Tx-2Tx switching among up to 4 bands

uplinkTxSwitching2T2T-PUSCH-TransCoherence-r17 ENUMERATED {nonCoherent,
fullCoherent} OPTIONAL

}

UplinkTxSwitchingAdditionalPeriodDualUL-r18::= SEQUENCE {

uplinkTxSwitchingBetweenBandPairs-r18 SEQUENCE {

bandPairIndex1-r18 INTEGER(1.. maxULTxSwitchingBandPairs),

anotherBandPairOrBand-r18 CHOICE {

bandPairIndex2-r18 INTEGER(1.. maxULTxSwitchingBandPairs),

bandIndex-r18 INTEGER(1..maxSimultaneousBands)

}

},

\-- R4 38-4: Additional switching Period for switching case across three
or four bands for Dual UL

switchingAdditionalPeriodDualUL-r18 ENUMERATED {n35us, n140us, n210us}

}

SwitchingPeriodUnaffectedBandDualUL-r18::= SEQUENCE {

bandIndexUnaffected-r18 INTEGER(1..maxSimultaneousBands),

periodUnaffectedBandDualUL-r18 CHOICE {

maintainedUL-Trans-r18 NULL,

periodOnULBands-r18 ENUMERATED {n35us, n140us, n210us}

}

}

BandParameters ::= CHOICE {

eutra SEQUENCE {

bandEUTRA FreqBandIndicatorEUTRA,

ca-BandwidthClassDL-EUTRA CA-BandwidthClassEUTRA OPTIONAL,

ca-BandwidthClassUL-EUTRA CA-BandwidthClassEUTRA OPTIONAL

},

nr SEQUENCE {

bandNR FreqBandIndicatorNR,

ca-BandwidthClassDL-NR CA-BandwidthClassNR OPTIONAL,

ca-BandwidthClassUL-NR CA-BandwidthClassNR OPTIONAL

}

}

BandParameters-v1540 ::= SEQUENCE {

srs-CarrierSwitch CHOICE {

nr SEQUENCE {

srs-SwitchingTimesListNR SEQUENCE (SIZE (1..maxSimultaneousBands)) OF
SRS-SwitchingTimeNR

},

eutra SEQUENCE {

srs-SwitchingTimesListEUTRA SEQUENCE (SIZE (1..maxSimultaneousBands)) OF
SRS-SwitchingTimeEUTRA

}

} OPTIONAL,

srs-TxSwitch SEQUENCE {

supportedSRS-TxPortSwitch ENUMERATED {t1r2, t1r4, t2r4, t1r4-t2r4, t1r1,
t2r2, t4r4, notSupported},

txSwitchImpactToRx INTEGER (1..32) OPTIONAL,

txSwitchWithAnotherBand INTEGER (1..32) OPTIONAL

} OPTIONAL

}

BandParameters-v1610 ::= SEQUENCE {

srs-TxSwitch-v1610 SEQUENCE {

supportedSRS-TxPortSwitch-v1610 ENUMERATED {t1r1-t1r2, t1r1-t1r2-t1r4,
t1r1-t1r2-t2r2-t2r4, t1r1-t1r2-t2r2-t1r4-t2r4,

t1r1-t2r2, t1r1-t2r2-t4r4}

} OPTIONAL

}

BandParameters-v1710 ::= SEQUENCE {

\-- R1 23-8-3 SRS Antenna switching for \>4Rx

srs-AntennaSwitchingBeyond4RX-r17 SEQUENCE {

\-- 1. Support of SRS antenna switching xTyR with y\>4

supportedSRS-TxPortSwitchBeyond4Rx-r17 BIT STRING (SIZE (11)),

\-- 2. Report the entry number of the first-listed band with UL in the
band combination that affects this DL

entryNumberAffectBeyond4Rx-r17 INTEGER (1..32) OPTIONAL,

\-- 3. Report the entry number of the first-listed band with UL in the
band combination that switches together with this UL

entryNumberSwitchBeyond4Rx-r17 INTEGER (1..32) OPTIONAL

} OPTIONAL

}

BandParameters-v1730 ::= SEQUENCE {

\-- R1 39-3-2 Affected bands for inter-band CA during SRS carrier
switching

srs-SwitchingAffectedBandsListNR-r17 SEQUENCE (SIZE
(1..maxSimultaneousBands)) OF SRS-SwitchingAffectedBandsNR-r17

}

BandParameters-v1770 ::= SEQUENCE {

ca-BandwidthClassDL-NR-r17 CA-BandwidthClassNR-r17 OPTIONAL,

ca-BandwidthClassUL-NR-r17 CA-BandwidthClassNR-r17 OPTIONAL

}

BandParameters-v1780 ::= SEQUENCE {

ca-BandwidthClassDL-NR-r17 CA-BandwidthClassNR-r17 OPTIONAL,

ca-BandwidthClassUL-NR-r17 CA-BandwidthClassNR-r17 OPTIONAL,

supportedAggBW-FR2-r17 SEQUENCE {

supportedAggBW-DL-r17 SupportedAggBandwidth-r17 OPTIONAL,

supportedAggBW-UL-r17 SupportedAggBandwidth-r17 OPTIONAL

} OPTIONAL

}

BandParameters-v1810 ::= SEQUENCE {

\-- R1 40-5-4: SRS 8 Tx ports-antenna switching

srs-AntennaSwitching8T8R-r18 SEQUENCE {

antennaSwitch8T8R-r18 ENUMERATED {noTdm, tdmAndNoTdm} OPTIONAL,

downgradeConfig-r18 CHOICE {

empty-r18 NULL,

downgrade-r18 BIT STRING (SIZE (11))

} OPTIONAL,

entryNumberAffect-r18 INTEGER (1..32) OPTIONAL,

entryNumberSwitch-r18 INTEGER (1..32) OPTIONAL

} OPTIONAL

}

ScalingFactorSidelink-r16 ::= ENUMERATED {f0p4, f0p75, f0p8, f1}

IntraBandPowerClass-r16 ::= ENUMERATED {pc2, pc3, spare6, spare5,
spare4, spare3, spare2, spare1}

SRS-SwitchingAffectedBandsNR-r17 ::= BIT STRING (SIZE
(1..maxSimultaneousBands))

SupportedIntraENDC-BandCombination-r17 ::= SEQUENCE {

supportedBandwidthCombinationSetIntraENDC-v1790 BIT STRING (SIZE
(1..32)) OPTIONAL,

mrdc-Parameters-v1790 MRDC-Parameters-v1790 OPTIONAL

}

\-- TAG-BANDCOMBINATIONLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *BandCombination* field descriptions                                  |
+=======================================================================+
| ***BandCombinationList-v1540, BandCombinationList-v1550,              |
| BandCombinationList-v1560, BandCombinationList-v1570,                 |
| BandCombinationList-v1580, BandCombinationList-v1590,                 |
| BandCombinationList-v15g0, BandCombinationList-v15n0,                 |
| BandCombinationList-v1610*, *BandCombinationList-v1630*,              |
| *BandCombinationList-v1640*, *BandCombinationList-v1650,              |
| BandCombinationList-v1680, BandCombinationList-v1690,                 |
| BandCombinationList-v16a0, BandCombinationList-v16j0,                 |
| BandCombinationList-v1700, BandCombinationList-v1720,                 |
| BandCombinationList-v1730, BandCombinationList-v1760,                 |
| BandCombinationList-v1780, BandCombinationList-v1790,                 |
| BandCombinationList-v17b0, BandCombinationList-v1800,                 |
| BandCombinationList-v1830, BandCombinationList-v1840,                 |
| BandCombinationList-v1860***                                          |
|                                                                       |
| The UE shall include the same number of entries, and listed in the    |
| same order, as in *BandCombinationList* (without suffix). If the      |
| field is included in *supportedBandCombinationListNEDC-Only-v1610*,   |
| the UE shall include the same number of entries, and listed in the    |
| same order, as in *BandCombinationList* of                            |
| *supportedBandCombinationListNEDC-Only* (without suffix) field.       |
|                                                                       |
| If the field is included in                                           |
| *supportedBandCombinationListNEDC-Only-v15a0*, the UE shall include   |
| the same number of entries, and listed in the same order, as in       |
| *BandCombinationList* (without suffix) of                             |
| *supportedBandCombinationListNEDC-Only* (without suffix) field.       |
+-----------------------------------------------------------------------+
| ***BandCombinationList-UplinkTxSwitch-r16,                            |
| BandCombinationList-UplinkTxSwitch-v1630,                             |
| BandCombinationList-UplinkTxSwitch-v1640,                             |
| BandCombinationList-UplinkTxSwitch-v1650,                             |
| BandCombinationList-UplinkTxSwitch-v1690,                             |
| BandCombinationList-UplinkTxSwitch-v16a0,                             |
| BandCombinationList-UplinkTxSwitch-v16e0,                             |
| BandCombinationList-UplinkTxSwitch-v16j0,                             |
| BandCombinationList-UplinkTxSwitch-v1700,                             |
| BandCombinationList-UplinkTxSwitch-v1720,                             |
| BandCombinationList-UplinkTxSwitch-v1730,                             |
| BandCombinationList-UplinkTxSwitch-v1760,                             |
| BandCombinationList-UplinkTxSwitch-v1780,                             |
| BandCombinationList-UplinkTxSwitch-v1790,                             |
| BandCombinationList-UplinkTxSwitch-v17b0,                             |
| BandCombinationList-UplinkTxSwitch-v1800,                             |
| BandCombinationList-UplinkTxSwitch-v1830,                             |
| BandCombinationList-UplinkTxSwitch-v1840,                             |
| BandCombinationList-UplinkTxSwitch-v1860***                           |
|                                                                       |
| The UE shall include the same number of entries, and listed in the    |
| same order, as in *BandCombinationList-UplinkTxSwitch-r16*.           |
|                                                                       |
| For the field of *supportedBandCombinationList-UplinkTxSwitch-v1700*, |
| if the UE does not support 2Tx-2Tx switching for a given band         |
| combination, the field of *supportedBandPairListNR-v1700* in the      |
| corresponding entry is absent.                                        |
+-----------------------------------------------------------------------+
| ***ca-ParametersNRDC***                                               |
|                                                                       |
| If the field (without suffix) is included for a band combination in   |
| the NR capability container, the field (without suffix) indicates     |
| support of NR-DC. Otherwise, the field is absent. If a version of the |
| field (with suffix) is absent for a band combination,                 |
| *ca-ParametersNR* field version in *BandCombination* corresponding to |
| the *ca-ParametersNR-ForDC* field version in the field (with suffix)  |
| is applicable to the UE configured with NR-DC for the band            |
| combination.                                                          |
+-----------------------------------------------------------------------+
| ***featureSetCombinationDAPS***                                       |
|                                                                       |
| If this field is present for a band combination, it reports the       |
| feature set combination supported for the band combination when any   |
| DAPS bearer is configured.                                            |
+-----------------------------------------------------------------------+
| ***ne-DC-BC***                                                        |
|                                                                       |
| If the field is included for a band combination in the MR-DC          |
| capability container, the field indicates support of NE-DC.           |
| Otherwise, the field is absent.                                       |
+-----------------------------------------------------------------------+
| ***supportedBandPairListNR-r16, supportedBandPairListNR-v1700***      |
|                                                                       |
| Indicates a list of band pair supporting UL Tx switching as defined   |
| in TS 38.101-1 \[15\] for a given band combination.                   |
|                                                                       |
| A UE supporting 2Tx-2Tx switching should include both of              |
| *supportedBandPairListNR-r16* and *supportedBandPairListNR-v1700*.    |
| And the UE shall include the same number of entries listed in the     |
| same order as in *supportedBandPairListNR-r16*.                       |
|                                                                       |
| If the UE does not support 2Tx-2Tx switching for a given band pair,   |
| the field of *uplinkTxSwitchingPeriod2T2T* in the corresponding entry |
| is absent.                                                            |
+-----------------------------------------------------------------------+
| ***supportedBandPairListNR-r18*, *supportedBandPairListNR-v1840***    |
|                                                                       |
| Indicates a list of band pair supporting UL Tx switching up to 4      |
| bands as defined in TS 38.101-1 \[15\] for a given band combination.  |
| The UE shall include all the possible band pairs. If                  |
| *supportedBandPairListNR-v1840* is included, the UE shall include the |
| same number of entries listed in the same order as in                 |
| *supportedBandPairListNR-r18*.                                        |
|                                                                       |
| For a band pair only supporting 1Tx-1Tx switching, the UE should      |
| include *switchingPeriodFor1T* in *ULTxSwitchingBandPair-r18*.        |
|                                                                       |
| For a band pair supporting 1Tx-2Tx switching, the UE always supports  |
| 1Tx-1Tx switching, and the UE should include *switchingPeriodFor1T*   |
| in *ULTxSwitchingBandPair-r18*.                                       |
|                                                                       |
| For a band pair supporting 2Tx-2Tx switching, the UE always supports  |
| 1Tx-2Tx switching and 1Tx-1Tx switching, the UE should include        |
| *switchingPeriodFor2T* as well as *switchingPeriodFor1T* in           |
| *ULTxSwitchingBandPair-r18*.                                          |
+-----------------------------------------------------------------------+
| ***srs-SwitchingTimesListNR***                                        |
|                                                                       |
| Indicates, for a particular pair of NR bands, the RF retuning time    |
| when switching between a NR carrier corresponding to this band entry  |
| and another (PUSCH-less) NR carrier corresponding to the band entry   |
| in the order indicated below:                                         |
|                                                                       |
| > \- For the first NR band, the UE shall include the same number of   |
| > entries for NR bands as in *bandList*, i.e. first entry corresponds |
| > to first NR band in *bandList* and so on,                           |
| >                                                                     |
| > \- For the second NR band, the UE shall include one entry less,     |
| > i.e. first entry corresponds to the second NR band in *bandList*    |
| > and so on                                                           |
| >                                                                     |
| > \- And so on                                                        |
+-----------------------------------------------------------------------+
| ***srs-SwitchingTimesListEUTRA***                                     |
|                                                                       |
| Indicates, for a particular pair of E-UTRA bands, the RF retuning     |
| time when switching between an E-UTRA carrier corresponding to this   |
| band entry and another (PUSCH-less) E-UTRA carrier corresponding to   |
| the band entry in the order indicated below:                          |
|                                                                       |
| > \- For the first E-UTRA band, the UE shall include the same number  |
| > of entries for E-UTRA bands as in *bandList,* i.e. first entry      |
| > corresponds to first E-UTRA band in *bandList* and so on,           |
| >                                                                     |
| > \- For the second E-UTRA band, the UE shall include one entry less, |
| > i.e. first entry corresponds to the second E-UTRA band in           |
| > *bandList* and so on                                                |
| >                                                                     |
| > \- And so on                                                        |
+-----------------------------------------------------------------------+
| ***srs-TxSwitch***                                                    |
|                                                                       |
| Indicates supported SRS antenna switch capability for the associated  |
| band. If the UE indicates support of *SRS-SwitchingTimeNR*, the UE is |
| allowed to set this field for a band with associated                  |
| *FeatureSetUplinkId* set to 0 for SRS carrier switching.              |
+-----------------------------------------------------------------------+
| ***supportedIntraENDC-BandCombinationList***                          |
|                                                                       |
| Indicates BCS and/or spectrum contiguity capability for each entry in |
| a list of intra-band (NG)EN-DC components in an inter-band (NG)EN-DC  |
| band combination. The UE shall include the entries in the order       |
| corresponding to the order of NR band entries of the intra-band       |
| (NG)EN-DC components in the *bandList* in the inter-band (NG)EN-DC    |
| band combination (i.e., *BandCombination* without suffix).            |
+-----------------------------------------------------------------------+
| ***uplinkTxSwitchingBandParametersList-v1700***                       |
|                                                                       |
| Indicates a list of per band per band combination capabilities for UL |
| Tx switching.                                                         |
+-----------------------------------------------------------------------+

#### -- *BandCombinationListSidelinkEUTRA-NR*

The IE *BandCombinationListSidelinkEUTRA-NR* contains a list of V2X
sidelink and NR sidelink band combinations.

BandCombinationListSidelinkEUTRA-NR information element

\-- ASN1START

\-- TAG-BANDCOMBINATIONLISTSIDELINKEUTRANR-START

BandCombinationListSidelinkEUTRA-NR-r16 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombinationParametersSidelinkEUTRA-NR-r16

BandCombinationListSidelinkEUTRA-NR-v1630 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombinationParametersSidelinkEUTRA-NR-v1630

BandCombinationListSidelinkEUTRA-NR-v1710 ::= SEQUENCE (SIZE
(1..maxBandComb)) OF BandCombinationParametersSidelinkEUTRA-NR-v1710

BandCombinationParametersSidelinkEUTRA-NR-r16 ::= SEQUENCE (SIZE
(1..maxSimultaneousBands)) OF BandParametersSidelinkEUTRA-NR-r16

BandCombinationParametersSidelinkEUTRA-NR-v1630 ::= SEQUENCE (SIZE
(1..maxSimultaneousBands)) OF BandParametersSidelinkEUTRA-NR-v1630

BandCombinationParametersSidelinkEUTRA-NR-v1710 ::= SEQUENCE (SIZE
(1..maxSimultaneousBands)) OF BandParametersSidelinkEUTRA-NR-v1710

BandParametersSidelinkEUTRA-NR-r16 ::= CHOICE {

eutra SEQUENCE {

bandParametersSidelinkEUTRA1-r16 OCTET STRING OPTIONAL,

bandParametersSidelinkEUTRA2-r16 OCTET STRING OPTIONAL

},

nr SEQUENCE {

bandParametersSidelinkNR-r16 BandParametersSidelink-r16

}

}

BandParametersSidelinkEUTRA-NR-v1630 ::= CHOICE {

eutra NULL,

nr SEQUENCE {

tx-Sidelink-r16 ENUMERATED {supported} OPTIONAL,

rx-Sidelink-r16 ENUMERATED {supported} OPTIONAL,

sl-CrossCarrierScheduling-r16 ENUMERATED {supported} OPTIONAL

}

}

BandParametersSidelinkEUTRA-NR-v1710 ::= CHOICE {

eutra NULL,

nr SEQUENCE {

\--32-4

sl-TransmissionMode2-PartialSensing-r17 SEQUENCE {

harq-TxProcessModeTwoSidelink-r17 ENUMERATED {n8, n16},

scs-CP-PatternTxSidelinkModeTwo-r17 CHOICE {

fr1-r17 SEQUENCE {

scs-15kHz-r17 BIT STRING (SIZE (16)) OPTIONAL,

scs-30kHz-r17 BIT STRING (SIZE (16)) OPTIONAL,

scs-60kHz-r17 BIT STRING (SIZE (16)) OPTIONAL

},

fr2-r17 SEQUENCE {

scs-60kHz-r17 BIT STRING (SIZE (16)) OPTIONAL,

scs-120kHz-r17 BIT STRING (SIZE (16)) OPTIONAL

}

} OPTIONAL,

extendedCP-Mode2PartialSensing-r17 ENUMERATED {supported} OPTIONAL,

dl-openLoopPC-Sidelink-r17 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\--32-2a: Receiving NR sidelink of PSFCH

rx-sidelinkPSFCH-r17 ENUMERATED {n5, n15, n25, n32, n35, n45, n50, n64}
OPTIONAL,

\--32-5a-1

tx-IUC-Scheme1-Mode2Sidelink-r17 ENUMERATED {supported} OPTIONAL,

\--32-5b-1

tx-IUC-Scheme2-Mode2Sidelink-r17 ENUMERATED {n4, n8, n16} OPTIONAL

}

}

BandParametersSidelink-r16 ::= SEQUENCE {

freqBandSidelink-r16 FreqBandIndicatorNR

}

\-- TAG-BANDCOMBINATIONLISTSIDELINKEUTRANR-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *BandParametersSidelinkEUTRA-NR* field descriptions                   |
+=======================================================================+
| ***bandParametersSidelinkEUTRA1,***                                   |
| ***bandParametersSidelinkEUTRA2***                                    |
|                                                                       |
| This field includes the *V2X-BandParameters-r14* and                  |
| *V2X-BandParameters-v1530* IE as specified in 36.331 \[10\]. It is    |
| used for reporting the per-band capability for V2X sidelink           |
| communication.                                                        |
+-----------------------------------------------------------------------+

#### -- *BandCombinationListSL-Discovery*

The IE *BandCombinationListSL-Discovery* contains a list of NR Sidelink
discovery band combinations.

*BandCombinationListSidelinkSL-Discovery* information element

\-- ASN1START

\-- TAG-BANDCOMBINATIONLISTSLDISCOVERY-START

BandCombinationListSL-Discovery-r17 ::= SEQUENCE (SIZE
(1..maxSimultaneousBands)) OF BandParametersSidelinkDiscovery-r17

BandParametersSidelinkDiscovery-r17 ::= SEQUENCE {

sl-CrossCarrierScheduling-r17 ENUMERATED {supported} OPTIONAL,

\--R1 32-4: Transmitting NR sidelink mode 2 with partial sensing

sl-TransmissionMode2-PartialSensing-r17 SEQUENCE {

harq-TxProcessModeTwoSidelink-r17 ENUMERATED {n8, n16},

scs-CP-PatternTxSidelinkModeTwo-r17 CHOICE {

fr1-r17 SEQUENCE {

scs-15kHz-r17 BIT STRING (SIZE (16)) OPTIONAL,

scs-30kHz-r17 BIT STRING (SIZE (16)) OPTIONAL,

scs-60kHz-r17 BIT STRING (SIZE (16)) OPTIONAL

},

fr2-r17 SEQUENCE {

scs-60kHz-r17 BIT STRING (SIZE (16)) OPTIONAL,

scs-120kHz-r17 BIT STRING (SIZE (16)) OPTIONAL

}

} OPTIONAL,

extendedCP-Mode2PartialSensing-r17 ENUMERATED {supported} OPTIONAL,

dl-openLoopPC-Sidelink-r17 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\--R1 32-5a-1: Transmitting Inter-UE coordination scheme 1 in NR
sidelink mode 2

tx-IUC-Scheme1-Mode2Sidelink-r17 ENUMERATED {supported} OPTIONAL

}

\-- TAG-BANDCOMBINATIONLISTSLDISCOVERY-STOP

\-- ASN1STOP

#### -- *CA-BandwidthClassEUTRA*

The IE *CA-BandwidthClassEUTRA* indicates the E-UTRA CA bandwidth class
as defined in TS 36.101 \[22\], table 5.6A-1.

*CA-BandwidthClassEUTRA* information element

\-- ASN1START

\-- TAG-CA-BANDWIDTHCLASSEUTRA-START

CA-BandwidthClassEUTRA ::= ENUMERATED {a, b, c, d, e, f, \...}

\-- TAG-CA-BANDWIDTHCLASSEUTRA-STOP

\-- ASN1STOP

#### -- *CA-BandwidthClassNR*

The IE *CA-BandwidthClassNR* indicates the NR CA bandwidth class as
defined in TS 38.101-1 \[15\], table 5.3A.5-1 and TS 38.101-2 \[39\],
table 5.3A.4-1.

*CA-BandwidthClassNR* information element

\-- ASN1START

\-- TAG-CA-BANDWIDTHCLASSNR-START

\-- R4 17-6: new CA BW Classes R2-R12

\-- R4 17-7: new CA BW Classes V, W

CA-BandwidthClassNR ::= ENUMERATED {a, b, c, d, e, f, g, h, i, j, k, l,
m, n, o, p, q, \...,r2-v1730, r3-v1730, r4-v1730, r5-v1730, r6-v1730,
r7-v1730, r8-v1730, r9-v1730, r10-v1730, r11-v1730, r12-v1730,v-v1770,
w-v1770 }

CA-BandwidthClassNR-r17 ::= ENUMERATED {r, s, t, u, \...}

\-- TAG-CA-BANDWIDTHCLASSNR-STOP

\-- ASN1STOP

#### -- *CA-ParametersEUTRA*

The IE *CA-ParametersEUTRA* contains the E-UTRA part of band combination
parameters for a given MR-DC band combination.

NOTE: If additional E-UTRA band combination parameters are defined in TS
36.331 \[10\], which are supported for MR-DC, they will be defined here
as well.

*CA-ParametersEUTRA* information element

\-- ASN1START

\-- TAG-CA-PARAMETERSEUTRA-START

CA-ParametersEUTRA ::= SEQUENCE {

multipleTimingAdvance ENUMERATED {supported} OPTIONAL,

simultaneousRx-Tx ENUMERATED {supported} OPTIONAL,

supportedNAICS-2CRS-AP BIT STRING (SIZE (1..8)) OPTIONAL,

additionalRx-Tx-PerformanceReq ENUMERATED {supported} OPTIONAL,

ue-CA-PowerClass-N ENUMERATED {class2} OPTIONAL,

supportedBandwidthCombinationSetEUTRA-v1530 BIT STRING (SIZE (1..32))
OPTIONAL,

\...

}

CA-ParametersEUTRA-v1560 ::= SEQUENCE {

fd-MIMO-TotalWeightedLayers INTEGER (2..128) OPTIONAL

}

CA-ParametersEUTRA-v1570 ::= SEQUENCE {

dl-1024QAM-TotalWeightedLayers INTEGER (0..10) OPTIONAL

}

\-- TAG-CA-PARAMETERSEUTRA-STOP

\-- ASN1STOP

#### -- *CA-ParametersNR*

The IE *CA-ParametersNR* contains carrier aggregation and
inter-frequency DAPS handover related capabilities that are defined per
band combination.

*CA-ParametersNR* information element

\-- ASN1START

\-- TAG-CA-PARAMETERSNR-START

CA-ParametersNR ::= SEQUENCE {

dummy ENUMERATED {supported} OPTIONAL,

parallelTxSRS-PUCCH-PUSCH ENUMERATED {supported} OPTIONAL,

parallelTxPRACH-SRS-PUCCH-PUSCH ENUMERATED {supported} OPTIONAL,

simultaneousRxTxInterBandCA ENUMERATED {supported} OPTIONAL,

simultaneousRxTxSUL ENUMERATED {supported} OPTIONAL,

diffNumerologyAcrossPUCCH-Group ENUMERATED {supported} OPTIONAL,

diffNumerologyWithinPUCCH-GroupSmallerSCS ENUMERATED {supported}
OPTIONAL,

supportedNumberTAG ENUMERATED {n2, n3, n4} OPTIONAL,

\...

}

CA-ParametersNR-v1540 ::= SEQUENCE {

simultaneousSRS-AssocCSI-RS-AllCC INTEGER (5..32) OPTIONAL,

csi-RS-IM-ReceptionForFeedbackPerBandComb SEQUENCE {

maxNumberSimultaneousNZP-CSI-RS-ActBWP-AllCC INTEGER (1..64) OPTIONAL,

totalNumberPortsSimultaneousNZP-CSI-RS-ActBWP-AllCC INTEGER (2..256)
OPTIONAL

} OPTIONAL,

simultaneousCSI-ReportsAllCC INTEGER (5..32) OPTIONAL,

dualPA-Architecture ENUMERATED {supported} OPTIONAL

}

CA-ParametersNR-v1550 ::= SEQUENCE {

dummy ENUMERATED {supported} OPTIONAL

}

CA-ParametersNR-v1560 ::= SEQUENCE {

diffNumerologyWithinPUCCH-GroupLargerSCS ENUMERATED {supported} OPTIONAL

}

CA-ParametersNR-v15g0 ::= SEQUENCE {

simultaneousRxTxInterBandCAPerBandPair SimultaneousRxTxPerBandPair
OPTIONAL,

simultaneousRxTxSULPerBandPair SimultaneousRxTxPerBandPair OPTIONAL

}

CA-ParametersNR-v1610 ::= SEQUENCE {

\-- R1 9-3: Parallel MsgA and SRS/PUCCH/PUSCH transmissions across CCs
in inter-band CA

parallelTxMsgA-SRS-PUCCH-PUSCH-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 9-4: MsgA operation in a band combination including SUL

msgA-SUL-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-9c: Joint search space group switching across multiple cells

jointSearchSpaceSwitchAcrossCells-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 14-5: Half-duplex UE behaviour in TDD CA for same SCS

half-DuplexTDD-CA-SameSCS-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 18-4: SCell dormancy within active time

scellDormancyWithinActiveTime-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 18-4a: SCell dormancy outside active time

scellDormancyOutsideActiveTime-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 18-6: Cross-carrier A-CSI RS triggering with different SCS

crossCarrierA-CSI-trigDiffSCS-r16 ENUMERATED
{higherA-CSI-SCS,lowerA-CSI-SCS,both} OPTIONAL,

\-- R1 18-6a: Default QCL assumption for cross-carrier A-CSI-RS
triggering

defaultQCL-CrossCarrierA-CSI-Trig-r16 ENUMERATED {diffOnly, both}
OPTIONAL,

\-- R1 18-7: CA with non-aligned frame boundaries for inter-band CA

interCA-NonAlignedFrame-r16 ENUMERATED {supported} OPTIONAL,

simul-SRS-Trans-BC-r16 ENUMERATED {n2} OPTIONAL,

interFreqDAPS-r16 SEQUENCE {

interFreqAsyncDAPS-r16 ENUMERATED {supported} OPTIONAL,

interFreqDiffSCS-DAPS-r16 ENUMERATED {supported} OPTIONAL,

interFreqMultiUL-TransmissionDAPS-r16 ENUMERATED {supported} OPTIONAL,

interFreqSemiStaticPowerSharingDAPS-Mode1-r16 ENUMERATED {supported}
OPTIONAL,

interFreqSemiStaticPowerSharingDAPS-Mode2-r16 ENUMERATED {supported}
OPTIONAL,

interFreqDynamicPowerSharingDAPS-r16 ENUMERATED {short, long} OPTIONAL,

interFreqUL-TransCancellationDAPS-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

codebookParametersPerBC-r16 CodebookParameters-v1610 OPTIONAL,

\-- R1 16-2a-10 Value of R for BD/CCE

blindDetectFactor-r16 INTEGER (1..2) OPTIONAL,

\-- R1 11-2a: Capability on the number of CCs for monitoring a maximum
number of BDs and non-overlapped CCEs per span when configured

\-- with DL CA with Rel-16 PDCCH monitoring capability on all the
serving cells

pdcch-MonitoringCA-r16 SEQUENCE {

maxNumberOfMonitoringCC-r16 INTEGER (2..16),

supportedSpanArrangement-r16 ENUMERATED {alignedOnly,
alignedAndNonAligned}

} OPTIONAL,

\-- R1 11-2c: Number of carriers for CCE/BD scaling with DL CA with mix
of Rel. 16 and Rel. 15 PDCCH monitoring capabilities on

\-- different carriers

pdcch-BlindDetectionCA-Mixed-r16 SEQUENCE {

pdcch-BlindDetectionCA1-r16 INTEGER (1..15),

pdcch-BlindDetectionCA2-r16 INTEGER (1..15),

supportedSpanArrangement-r16 ENUMERATED {alignedOnly,
alignedAndNonAligned}

} OPTIONAL,

\-- R1 11-2d: Capability on the number of CCs for monitoring a maximum
number of BDs and non-overlapped CCEs per span for MCG and for

\-- SCG when configured for NR-DC operation with Rel-16 PDCCH monitoring
capability on all the serving cells

pdcch-BlindDetectionMCG-UE-r16 INTEGER (1..14) OPTIONAL,

pdcch-BlindDetectionSCG-UE-r16 INTEGER (1..14) OPTIONAL,

\-- R1 11-2e: Number of carriers for CCE/BD scaling for MCG and for SCG
when configured for NR-DC operation with mix of Rel. 16 and

\-- Rel. 15 PDCCH monitoring capabilities on different carriers

pdcch-BlindDetectionMCG-UE-Mixed-r16 SEQUENCE {

pdcch-BlindDetectionMCG-UE1-r16 INTEGER (0..15),

pdcch-BlindDetectionMCG-UE2-r16 INTEGER (0..15)

} OPTIONAL,

pdcch-BlindDetectionSCG-UE-Mixed-r16 SEQUENCE {

pdcch-BlindDetectionSCG-UE1-r16 INTEGER (0..15),

pdcch-BlindDetectionSCG-UE2-r16 INTEGER (0..15)

} OPTIONAL,

\-- R1 18-5 cross-carrier scheduling with different SCS in DL CA

crossCarrierSchedulingDL-DiffSCS-r16 ENUMERATED {low-to-high,
high-to-low, both} OPTIONAL,

\-- R1 18-5a Default QCL assumption for cross-carrier scheduling

crossCarrierSchedulingDefaultQCL-r16 ENUMERATED {diff-only, both}
OPTIONAL,

\-- R1 18-5b cross-carrier scheduling with different SCS in UL CA

crossCarrierSchedulingUL-DiffSCS-r16 ENUMERATED {low-to-high,
high-to-low, both} OPTIONAL,

\-- R1 13.19a Simultaneous positioning SRS and MIMO SRS transmission for
a given BC

simul-SRS-MIMO-Trans-BC-r16 ENUMERATED {n2} OPTIONAL,

\-- R1 16-3a, 16-3a-1, 16-3b, 16-3b-1: New Individual Codebook

codebookParametersAdditionPerBC-r16 CodebookParametersAdditionPerBC-r16
OPTIONAL,

\-- R1 16-8: Mixed codebook

codebookComboParametersAdditionPerBC-r16
CodebookComboParametersAdditionPerBC-r16 OPTIONAL

}

CA-ParametersNR-v1630 ::= SEQUENCE {

\-- R1 22-5b: Simultaneous transmission of SRS for antenna switching and
SRS for CB/NCB /BM for inter-band UL CA

\-- R1 22-5d: Simultaneous transmission of SRS for antenna switching for
inter-band UL CA

simulTX-SRS-AntSwitchingInterBandUL-CA-r16
SimulSRS-ForAntennaSwitching-r16 OPTIONAL,

\-- R4 8-5: supported beam management type for inter-band CA

beamManagementType-r16 ENUMERATED {ibm, dummy} OPTIONAL,

\-- R4 7-3a: UL frequency separation class with aggregate BW and Gap BW

intraBandFreqSeparationUL-AggBW-GapBW-r16 ENUMERATED {classI, classII,
classIII} OPTIONAL,

\-- RAN 89: Case B in case of Inter-band CA with non-aligned frame
boundaries

interCA-NonAlignedFrame-B-r16 ENUMERATED {supported} OPTIONAL

}

CA-ParametersNR-v1640 ::= SEQUENCE {

\-- R4 7-5: Support of reporting UL Tx DC locations for uplink
intra-band CA.

uplinkTxDC-TwoCarrierReport-r16 ENUMERATED {supported} OPTIONAL,

\-- RAN 22-6: Support of up to 3 different numerologies in the same NR
PUCCH group for NR part of EN-DC, NGEN-DC, NE-DC and NR-CA

\-- where UE is not configured with two NR PUCCH groups

maxUpTo3Diff-NumerologiesConfigSinglePUCCH-grp-r16
PUCCH-Grp-CarrierTypes-r16 OPTIONAL,

\-- RAN 22-6a: Support of up to 4 different numerologies in the same NR
PUCCH group for NR part of EN-DC, NGEN-DC, NE-DC and NR-CA

\-- where UE is not configured with two NR PUCCH groups

maxUpTo4Diff-NumerologiesConfigSinglePUCCH-grp-r16
PUCCH-Grp-CarrierTypes-r16 OPTIONAL,

\-- RAN 22-7: Support two PUCCH groups for NR-CA with 3 or more bands
with at least two carrier types

twoPUCCH-Grp-ConfigurationsList-r16 SEQUENCE (SIZE
(1..maxTwoPUCCH-Grp-ConfigList-r16)) OF TwoPUCCH-Grp-Configurations-r16
OPTIONAL,

\-- R1 22-7a: Different numerology across NR PUCCH groups

diffNumerologyAcrossPUCCH-Group-CarrierTypes-r16 ENUMERATED {supported}
OPTIONAL,

\-- R1 22-7b: Different numerologies across NR carriers within the same
NR PUCCH group, with PUCCH on a carrier of smaller SCS

diffNumerologyWithinPUCCH-GroupSmallerSCS-CarrierTypes-r16 ENUMERATED
{supported} OPTIONAL,

\-- R1 22-7c: Different numerologies across NR carriers within the same
NR PUCCH group, with PUCCH on a carrier of larger SCS

diffNumerologyWithinPUCCH-GroupLargerSCS-CarrierTypes-r16 ENUMERATED
{supported} OPTIONAL,

\-- R1 11-2f: add the replicated FGs of 11-2a/c with restriction for
non-aligned span case

\-- with DL CA with Rel-16 PDCCH monitoring capability on all the
serving cells

pdcch-MonitoringCA-NonAlignedSpan-r16 INTEGER (2..16) OPTIONAL,

\-- R1 11-2g: add the replicated FGs of 11-2a/c with restriction for
non-aligned span case

pdcch-BlindDetectionCA-Mixed-NonAlignedSpan-r16 SEQUENCE {

pdcch-BlindDetectionCA1-r16 INTEGER (1..15),

pdcch-BlindDetectionCA2-r16 INTEGER (1..15)

} OPTIONAL

}

CA-ParametersNR-v1690 ::= SEQUENCE {

csi-ReportingCrossPUCCH-Grp-r16 SEQUENCE {

computationTimeForA-CSI-r16 ENUMERATED {sameAsNoCross, relaxed},

additionalSymbols-r16 SEQUENCE {

scs-15kHz-additionalSymbols-r16 ENUMERATED {s14, s28} OPTIONAL,

scs-30kHz-additionalSymbols-r16 ENUMERATED {s14, s28} OPTIONAL,

scs-60kHz-additionalSymbols-r16 ENUMERATED {s14, s28, s56} OPTIONAL,

scs-120kHz-additionalSymbols-r16 ENUMERATED {s14, s28, s56} OPTIONAL

} OPTIONAL,

sp-CSI-ReportingOnPUCCH-r16 ENUMERATED {supported} OPTIONAL,

sp-CSI-ReportingOnPUSCH-r16 ENUMERATED {supported} OPTIONAL,

carrierTypePairList-r16 SEQUENCE (SIZE (1..maxCarrierTypePairList-r16))
OF CarrierTypePair-r16

} OPTIONAL

}

CA-ParametersNR-v16a0 ::= SEQUENCE {

pdcch-BlindDetectionMixedList-r16
SEQUENCE(SIZE(1..maxNrofPdcch-BlindDetectionMixed-1-r16)) OF
PDCCH-BlindDetectionMixedList-r16

}

CA-ParametersNR-v1700 ::= SEQUENCE {

\-- R1 23-9-1: Basic Features of Further Enhanced Port-Selection Type II
Codebook (FeType-II) per band combination information

codebookParametersfetype2PerBC-r17 CodebookParametersfetype2PerBC-r17
OPTIONAL,

\-- R4 18-4: Support of enhanced Demodulation requirements for CA in HST
SFN FR1

demodulationEnhancementCA-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 20-1: Maximum uplink duty cycle for NR inter-band CA power class
2

maxUplinkDutyCycle-interBandCA-PC2-r17 ENUMERATED {n50, n60, n70, n80,
n90, n100} OPTIONAL,

\-- R4 20-2: Maximum uplink duty cycle for NR SUL combination power
class 2

maxUplinkDutyCycle-SULcombination-PC2-r17 ENUMERATED {n50, n60, n70,
n80, n90, n100} OPTIONAL,

beamManagementType-CBM-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 25-18: Parallel PUCCH and PUSCH transmission across CCs in
inter-band CA

parallelTxPUCCH-PUSCH-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-9-5 Active CSI-RS resources and ports for mixed codebook types
in any slot per band combination

codebookComboParameterMixedTypePerBC-r17
CodebookComboParameterMixedTypePerBC-r17 OPTIONAL,

\-- R1 23-7-1 Basic Features of CSI Enhancement for Multi-TRP

mTRP-CSI-EnhancementPerBC-r17 SEQUENCE {

maxNumNZP-CSI-RS-r17 INTEGER (2..8),

cSI-Report-mode-r17 ENUMERATED {mode1, mode2, both},

supportedComboAcrossCCs-r17 SEQUENCE (SIZE (1..16)) OF
CSI-MultiTRP-SupportedCombinations-r17,

codebookMode-NCJT-r17 ENUMERATED{mode1,mode1And2}

} OPTIONAL,

\-- R1 23-7-1b Active CSI-RS resources and ports in the presence of
multi-TRP CSI

codebookComboParameterMultiTRP-PerBC-r17
CodebookComboParameterMultiTRP-PerBC-r17 OPTIONAL,

\-- R1 24-8b: 32 DL HARQ processes for FR 2-2 - maximum number of
component carriers

maxCC-32-DL-HARQ-ProcessFR2-2-r17 ENUMERATED {n1, n2, n3, n4, n6, n8,
n16, n32} OPTIONAL,

\-- R1 24-9b: 32 UL HARQ processes for FR 2-2 - maximum number of
component carriers

maxCC-32-UL-HARQ-ProcessFR2-2-r17 ENUMERATED {n1, n2, n3, n4, n5, n8,
n16, n32} OPTIONAL,

\-- R1 34-2: Cross-carrier scheduling from SCell to PCell/PSCell (Type
B)

crossCarrierSchedulingSCell-SpCellTypeB-r17
CrossCarrierSchedulingSCell-SpCell-r17 OPTIONAL,

\-- R1 34-1: Cross-carrier scheduling from SCell to PCell/PSCell with
search space restrictions (Type A)

crossCarrierSchedulingSCell-SpCellTypeA-r17
CrossCarrierSchedulingSCell-SpCell-r17 OPTIONAL,

\-- R1 34-1a: DCI formats on PCell/PSCell USS set(s) support

dci-FormatsPCellPSCellUSS-Sets-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 34-3: Disabling scaling factor alpha when sSCell is deactivated

disablingScalingFactorDeactSCell-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 34-4: Disabling scaling factor alpha when sSCell is deactivated

disablingScalingFactorDormantSCell-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 34-5: Non-aligned frame boundaries between PCell/PSCell and
sSCell

non-AlignedFrameBoundaries-r17 SEQUENCE {

scs15kHz-15kHz-r17 BIT STRING (SIZE (1..496)) OPTIONAL,

scs15kHz-30kHz-r17 BIT STRING (SIZE (1..496)) OPTIONAL,

scs15kHz-60kHz-r17 BIT STRING (SIZE (1..496)) OPTIONAL,

scs30kHz-30kHz-r17 BIT STRING (SIZE (1..496)) OPTIONAL,

scs30kHz-60kHz-r17 BIT STRING (SIZE (1..496)) OPTIONAL,

scs60kHz-60kHz-r17 BIT STRING (SIZE (1..496)) OPTIONAL

} OPTIONAL

}

CA-ParametersNR-v1720 ::= SEQUENCE {

\-- R1 39-1: Parallel SRS and PUCCH/PUSCH transmission across CCs in
intra-band non-contiguous CA

parallelTxSRS-PUCCH-PUSCH-intraBand-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 39-2: Parallel PRACH and SRS/PUCCH/PUSCH transmissions across CCs
in intra-band non-contiguous CA

parallelTxPRACH-SRS-PUCCH-PUSCH-intraBand-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 25-9: Semi-static PUCCH cell switching for a single PUCCH group
only

semiStaticPUCCH-CellSwitchSingleGroup-r17 SEQUENCE {

pucch-Group-r17 ENUMERATED {primaryGroupOnly, secondaryGroupOnly,
eitherPrimaryOrSecondaryGroup},

pucch-Group-Config-r17 PUCCH-Group-Config-r17

} OPTIONAL,

\-- R1 25-9a: Semi-static PUCCH cell switching for two PUCCH groups

semiStaticPUCCH-CellSwitchTwoGroups-r17 SEQUENCE (SIZE
(1..maxTwoPUCCH-Grp-ConfigList-r17)) OF TwoPUCCH-Grp-Configurations-r17
OPTIONAL,

\-- R1 25-10: PUCCH cell switching based on dynamic indication for same
length of overlapping PUCCH slots/sub-slots for a single

\-- PUCCH group only

dynamicPUCCH-CellSwitchSameLengthSingleGroup-r17 SEQUENCE {

pucch-Group-r17 ENUMERATED {primaryGroupOnly, secondaryGroupOnly,
eitherPrimaryOrSecondaryGroup},

pucch-Group-Config-r17 PUCCH-Group-Config-r17

} OPTIONAL,

\-- R1 25-10a: PUCCH cell switching based on dynamic indication for
different length of overlapping PUCCH slots/sub-slots

\-- for a single PUCCH group only

dynamicPUCCH-CellSwitchDiffLengthSingleGroup-r17 SEQUENCE {

pucch-Group-r17 ENUMERATED {primaryGroupOnly, secondaryGroupOnly,
eitherPrimaryOrSecondaryGroup},

pucch-Group-Config-r17 PUCCH-Group-Config-r17

} OPTIONAL,

\-- R1 25-10b: PUCCH cell switching based on dynamic indication for same
length of overlapping PUCCH slots/sub-slots for two PUCCH

\-- groups

dynamicPUCCH-CellSwitchSameLengthTwoGroups-r17 SEQUENCE (SIZE
(1..maxTwoPUCCH-Grp-ConfigList-r17)) OF TwoPUCCH-Grp-Configurations-r17

OPTIONAL,

\-- R1 25-10c: PUCCH cell switching based on dynamic indication for
different length of overlapping PUCCH slots/sub-slots for two

\-- PUCCH groups

dynamicPUCCH-CellSwitchDiffLengthTwoGroups-r17 SEQUENCE (SIZE
(1..maxTwoPUCCH-Grp-ConfigList-r17)) OF TwoPUCCH-Grp-Configurations-r17

OPTIONAL,

\-- R1 33-2a: ACK/NACK based HARQ-ACK feedback and RRC-based
enabling/disabling ACK/NACK-based

\-- feedback for dynamic scheduling for multicast

ack-NACK-FeedbackForMulticast-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-2d: PTP retransmission for multicast dynamic scheduling

ptp-Retx-Multicast-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-4: NACK-only based HARQ-ACK feedback for RRC-based
enabling/disabling multicast with ACK/NACK transforming

nack-OnlyFeedbackForMulticast-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-4a: NACK-only based HARQ-ACK feedback for multicast
corresponding to a specific sequence or a PUCCH transmission

nack-OnlyFeedbackSpecificResourceForMulticast-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 33-5-1a: ACK/NACK based HARQ-ACK feedback and RRC-based
enabling/disabling ACK/NACK-based feedback

\-- for SPS group-common PDSCH for multicast

ack-NACK-FeedbackForSPS-Multicast-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-5-1d: PTP retransmission for SPS group-common PDSCH for
multicast

ptp-Retx-SPS-Multicast-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 26-1: Higher Power Limit CA DC

higherPowerLimit-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 39-4: Parallel MsgA and SRS/PUCCH/PUSCH transmissions across CCs
in intra-band non-contiguous CA

parallelTxMsgA-SRS-PUCCH-PUSCH-intraBand-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 24-11a: Capability on the number of CCs for monitoring a maximum
number of BDs and non-overlapped CCEs per span when

\-- configured with DL CA with Rel-17 PDCCH monitoring capability on all
the serving cells

pdcch-MonitoringCA-r17 INTEGER (4..16) OPTIONAL,

\-- R1 24-11f: Capability on the number of CCs for monitoring a maximum
number of BDs and non-overlapped CCEs for MCG and for SCG

\-- when configured for NR-DC operation with Rel-17 PDCCH monitoring
capability on all the serving cells

pdcch-BlindDetectionMCG-SCG-List-r17
SEQUENCE(SIZE(1..maxNrofPdcch-BlindDetection-r17)) OF
PDCCH-BlindDetectionMCG-SCG-r17

OPTIONAL,

\-- R1 24-11c: Number of carriers for CCE/BD scaling with DL CA with mix
of Rel. 17 and Rel. 15 PDCCH monitoring capabilities on

\-- different Carriers

\-- R1 24-11g: Number of carriers for CCE/BD scaling for MCG and for SCG
when configured for NR-DC operation with mix of Rel. 17 and

\-- Rel. 15 PDCCH monitoring capabilities on different carriers

pdcch-BlindDetectionMixedList1-r17
SEQUENCE(SIZE(1..maxNrofPdcch-BlindDetection-r17)) OF
PDCCH-BlindDetectionMixed-r17

OPTIONAL,

\-- R1 24-11d: Number of carriers for CCE/BD scaling with DL CA with mix
of Rel. 17 and Rel. 16 PDCCH monitoring capabilities on

\-- different Carriers

\-- R1 24-11h: Number of carriers for CCE/BD scaling for MCG and for SCG
when configured for NR-DC operation with mix of Rel. 17 and

\-- Rel. 16 PDCCH monitoring capabilities on different carriers

pdcch-BlindDetectionMixedList2-r17
SEQUENCE(SIZE(1..maxNrofPdcch-BlindDetection-r17)) OF
PDCCH-BlindDetectionMixed-r17

OPTIONAL,

\-- R1 24-11e: Number of carriers for CCE/BD scaling with DL CA with mix
of Rel. 17, Rel. 16 and Rel. 15 PDCCH monitoring

\-- capabilities on different carriers

\-- R1 24-11i: Number of carriers for CCE/BD scaling for MCG and for SCG
when configured for NR-DC operation with mix of Rel. 17,

\-- Rel. 16 and Rel. 15 PDCCH monitoring capabilities on different
carriers

pdcch-BlindDetectionMixedList3-r17
SEQUENCE(SIZE(1..maxNrofPdcch-BlindDetection-r17)) OF
PDCCH-BlindDetectionMixed1-r17

OPTIONAL

}

CA-ParametersNR-v1730 ::= SEQUENCE {

\-- R1 30-4a: DM-RS bundling for PUSCH repetition type A (per BC)

dmrs-BundlingPUSCH-RepTypeAPerBC-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-4b: DM-RS bundling for PUSCH repetition type B(per BC)

dmrs-BundlingPUSCH-RepTypeBPerBC-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-4c: DM-RS bundling for TB processing over multi-slot PUSCH(per
BC)

dmrs-BundlingPUSCH-multiSlotPerBC-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-4d: DMRS bundling for PUCCH repetitions(per BC)

dmrs-BundlingPUCCH-RepPerBC-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-4g: Restart DM-RS bundling (per BC)

dmrs-BundlingRestartPerBC-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-4h: DM-RS bundling for non-back-to-back transmission (per BC)

dmrs-BundlingNonBackToBackTX-PerBC-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 39-3-1: Stay on the target CC for SRS carrier switching

stayOnTargetCC-SRS-CarrierSwitch-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-3-3a: FDM-ed Type-1 and Type-2 HARQ-ACK codebooks for
multiplexing HARQ-ACK for unicast and HARQ-ACK for multicast

fdm-CodebookForMux-UnicastMulticastHARQ-ACK-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 33-3-3b: Mode 2 TDM-ed Type-1 and Type-2 HARQ-ACK codebook for
multiplexing HARQ-ACK for unicast and HARQ-ACK for multicast

mode2-TDM-CodebookForMux-UnicastMulticastHARQ-ACK-r17 ENUMERATED
{supported} OPTIONAL,

\-- R1 33-3-4: Mode 1 for type1 codebook generation

mode1-ForType1-CodebookGeneration-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-5-1j: NACK-only based HARQ-ACK feedback for multicast
corresponding to a specific sequence or a PUCCH transmission

\-- for SPS group-commmon PDSCH for multicast

nack-OnlyFeedbackSpecificResourceForSPS-Multicast-r17 ENUMERATED
{supported} OPTIONAL,

\-- R1 33-8-2: Up to 2 PUCCH resources configuration for multicast
feedback for dynamically scheduled multicast

multiPUCCH-ConfigForMulticast-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-8-3: PUCCH resource configuration for multicast feedback for
SPS GC-PDSCH

pucch-ConfigForSPS-Multicast-r17 ENUMERATED {supported} OPTIONAL,

\-- The following parameter is associated with R1 33-2a, R1 33-3-3a, and
R1 33-3-3b, and is not a RAN1 FG.

maxNumberG-RNTI-HARQ-ACK-Codebook-r17 INTEGER (1..4) OPTIONAL,

\-- R1 33-3-5: Feedback multiplexing for unicast PDSCH and group-common
PDSCH for multicast with same priority and different codebook

\-- type

mux-HARQ-ACK-UnicastMulticast-r17 ENUMERATED {supported} OPTIONAL

}

CA-ParametersNR-v1740 ::= SEQUENCE {

\-- R1 33-5-1f: NACK-only based HARQ-ACK feedback for multicast
RRC-based enabling/disabling NACK-only based feedback

\-- for SPS group-common PDSCH for multicast

nack-OnlyFeedbackForSPS-Multicast-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-8-1: PUCCH resource configuration for multicast feedback for
dynamically scheduled multicast

singlePUCCH-ConfigForMulticast-r17 ENUMERATED {supported} OPTIONAL

}

CA-ParametersNR-v1760 ::= SEQUENCE {

prioSCellPRACH-OverSP-PeriodicSRS-Support-r17 ENUMERATED {supported}
OPTIONAL

}

CA-ParametersNR-v1770 ::= SEQUENCE {

parallelTxPUCCH-PUSCH-SamePriority-r17 ENUMERATED {supported} OPTIONAL

}

CA-ParametersNR-v1780 ::= SEQUENCE {

parallelTxPUCCH-PUSCH-SamePriority-r17 ENUMERATED {supported} OPTIONAL,

supportedAggBW-FR1-r17 SEQUENCE {

scalingFactorSCS-r17 ENUMERATED {true} OPTIONAL,

supportedAggBW-FDD-DL-r17 SupportedAggBandwidth-r17 OPTIONAL,

supportedAggBW-FDD-UL-r17 SupportedAggBandwidth-r17 OPTIONAL,

supportedAggBW-TDD-DL-r17 SupportedAggBandwidth-r17 OPTIONAL,

supportedAggBW-TDD-UL-r17 SupportedAggBandwidth-r17 OPTIONAL,

supportedAggBW-TotalDL-r17 SupportedAggBandwidth-r17 OPTIONAL,

supportedAggBW-TotalUL-r17 SupportedAggBandwidth-r17 OPTIONAL

} OPTIONAL

}

CA-ParametersNR-v1800 ::= SEQUENCE {

codebookParametersetype2DopplerCSI-PerBC-r18
CodebookParametersetype2DopplerCSI-r18 OPTIONAL,

codebookParametersfetype2DopplerCSI-PerBC-r18
CodebookParametersfetype2DopplerCSI-r18 OPTIONAL,

codebookParametersetype2CJT-PerBC-r18 CodebookParametersetype2CJT-r18
OPTIONAL,

codebookParametersfetype2CJT-PerBC-r18 CodebookParametersfetype2CJT-r18
OPTIONAL,

codebookComboParametersCJT-PerBC-r18 CodebookComboParametersCJT-r18
OPTIONAL,

codebookParametersHARQ-ACK-PUSCH-PerBC-r18
CodebookParametersHARQ-ACK-PUSCH-r18 OPTIONAL,

\-- R1 40-2-8: Maximum number of TAGs across all CCs

maxNumberTAG-AcrossCC-r18 INTEGER (2..4) OPTIONAL,

\-- R1 40-3-3-1: TDCP (Time Domain Channel Properties) report

tdcp-ReportPerBC-r18 SEQUENCE {

valueX-r18 INTEGER (1..2),

maxNumberActiveResource-r18 INTEGER (2..32)

} OPTIONAL,

\-- R1 40-3-3-5: Number of CSI-RS resources for TDCP

tdcp-ResourcePerBC-r18 SEQUENCE {

maxNumberConfigPerCC-r18 ENUMERATED {n2,n4,n6,n8,n10,n12},

maxNumberConfigAcrossCC-r18 INTEGER (1..32),

maxNumberSimultaneousPerCC-r18 ENUMERATED {n2, n4, n6, n8, n12, n16,
n20, n24, n28, n32}

} OPTIONAL,

\-- R1 40-3-1-24: Timeline for regular eType-II-CJT CSI, or for port
selection FeType-II-CJT CSI

timelineRelax-CJT-CSI-CA-r18 ENUMERATED {n0,n2} OPTIONAL,

\-- R1 42-1: Spatial domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for periodic CSI reporting

spatialAdaptation-CSI-FeedbackPerBC-r18 SEQUENCE {

maxNumberCSI-ResourceAcrossCC-r18 SEQUENCE {

sdType1-Resource-r18 ENUMERATED {n5, n6, n7, n8, n9, n10, n12, n14, n16,
n18, n20, n22,

n24, n26, n28, n30, n32, n34, n36, n38, n40, n42, n44,

n46, n48, n50, n52, n54, n56, n58, n60, n62, n64},

sdType2-Resource-r18 ENUMERATED {n5, n6, n7, n8, n9, n10, n12, n14, n16,
n18, n20, n22,

n24, n26, n28, n30, n32, n34, n36, n38, n40, n42, n44,

n46, n48, n50, n52, n54, n56, n58, n60, n62, n64}

},

maxNumberPortsAcrossCC-r18 SEQUENCE {

sdType1-Resource-r18 INTEGER (1..32),

sdType2-Resource-r18 INTEGER (1..32)

}

} OPTIONAL,

\-- R1 40-7-2a: Association between CSI-RS and SRS for non-codebook case

nonCodebook-CSI-RS-SRS-PerBC-r18 SEQUENCE (SIZE (1..
maxNrofCSI-RS-Resources)) OF SupportedCSI-RS-Resource OPTIONAL,

\-- R1 42-1a: Spatial domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for periodic CSI reporting on

\-- PUSCH

spatialAdaptation-CSI-FeedbackPUSCH-PerBC-r18 SEQUENCE {

maxNumberCSI-ResourceAcrossCC-r18 ENUMERATED {n5, n6, n7, n8, n9, n10,
n12, n14, n16, n18, n20, n22, n24, n26, n28,

n30, n32, n34, n36, n38, n40, n42, n44, n46, n48, n50, n52, n54,

n56, n58, n60, n62, n64},

maxNumberPortsAcrossCC-r18 INTEGER (1..32)

} OPTIONAL,

\-- R1 42-1b: Spatial domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for aperiodic CSI reporting

spatialAdaptation-CSI-FeedbackAperiodicPerBC-r18 SEQUENCE {

maxNumberCSI-ResourceAcrossCC-r18 SEQUENCE {

sdType1-Resource-r18 ENUMERATED {n5, n6, n7, n8, n9, n10, n12, n14, n16,
n18, n20, n22,

n24, n26, n28, n30, n32, n34, n36, n38, n40, n42, n44,

n46, n48, n50, n52, n54, n56, n58, n60, n62, n64},

sdType2-Resource-r18 ENUMERATED {n5, n6, n7, n8, n9, n10, n12, n14, n16,
n18, n20, n22,

n24, n26, n28, n30, n32, n34, n36, n38, n40, n42, n44,

n46, n48, n50, n52, n54, n56, n58, n60, n62, n64}

},

maxNumberPortsAcrossCC-r18 SEQUENCE {

sdType1-Resource-r18 INTEGER (1..32),

sdType2-Resource-r18 INTEGER (1..32) }

} OPTIONAL,

\-- R1 42-1c: Spatial domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for semi-persistent CSI

\-- reporting on PUCCH

spatialAdaptation-CSI-FeedbackPUCCH-PerBC-r18 SEQUENCE {

maxNumberCSI-ResourceAcrossCC-r18 ENUMERATED {n5, n6, n7, n8, n9, n10,
n12, n14, n16, n18, n20, n22, n24, n26, n28,

n30, n32, n34, n36, n38, n40, n42, n44, n46, n48, n50, n52, n54,

n56, n58, n60, n62, n64},

maxNumberPortsAcrossCC-r18 INTEGER (1..32)

} OPTIONAL,

\-- R1 42-2: Spatial domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for periodic CSI reporting

powerAdaptation-CSI-FeedbackPerBC-r18 SEQUENCE {

maxNumberCSI-ResourceAcrossCC-r18 ENUMERATED {n5, n6, n7, n8, n9, n10,
n12, n14, n16, n18, n20, n22, n24, n26, n28,

n30, n32, n34, n36, n38, n40, n42, n44, n46, n48, n50, n52, n54,

n56, n58, n60, n62, n64},

maxNumberPortsAcrossCC-r18 INTEGER (1..32)

} OPTIONAL,

\-- R1 42-2a: Spatial domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for periodic CSI reporting on PUSCH

powerAdaptation-CSI-FeedbackPUSCH-PerBC-r18 SEQUENCE {

maxNumberCSI-ResourceAcrossCC-r18 ENUMERATED {n5, n6, n7, n8, n9, n10,
n12, n14, n16, n18, n20, n22, n24, n26, n28,

n30, n32, n34, n36, n38, n40, n42, n44, n46, n48, n50, n52, n54,

n56, n58, n60, n62, n64},

maxNumberPortsAcrossCC-r18 INTEGER (1..32)

} OPTIONAL,

\-- R1 42-2b: Spatial domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for aperiodic CSI reporting

powerAdaptation-CSI-FeedbackAperiodicPerBC-r18 SEQUENCE {

maxNumberCSI-ResourceAcrossCC-r18 ENUMERATED {n5, n6, n7, n8, n9, n10,
n12, n14, n16, n18, n20, n22, n24, n26, n28,

n30, n32, n34, n36, n38, n40, n42, n44, n46, n48, n50, n52, n54,

n56, n58, n60, n62, n64},

maxNumberPortsAcrossCC-r18 INTEGER (1..32)

} OPTIONAL,

\-- R1 42-2c: Spatial domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for semi-persistent CSI

\-- reporting on PUCCH

powerAdaptation-CSI-FeedbackPUCCH-PerBC-r18 SEQUENCE {

maxNumberCSI-ResourceAcrossCC-r18 ENUMERATED {n5, n6, n7, n8, n9, n10,
n12, n14, n16, n18, n20, n22, n24, n26, n28,

n30, n32, n34, n36, n38, n40, n42, n44, n46, n48, n50, n52, n54,

n56, n58, n60, n62, n64},

maxNumberPortsAcrossCC-r18 INTEGER (1..32)

} OPTIONAL,

\-- R1 42-7: Mixed codebook combination for spatial domain adaptation
with CSI feedback based on CSI report sub-configuration(s),

\-- each containing one port subset configuration

mixCodeBookSpatialAdaptationPerBC-r18 SEQUENCE (SIZE (1..
maxNrofCSI-RS-Resources)) OF SupportedCSI-RS-Resource OPTIONAL,

\-- R1 42-9: Indicates whether the UE supports CSI report framework and
the number of CSI report(s) which the UE can

\-- simultaneously process across all CCs, and across MCG and SCG in
case of NR-DC.

simultaneousCSI-SubReportsAllCC-r18 INTEGER (5..32) OPTIONAL,

\-- R1 49-1: Multi-cell PDSCH scheduling by DCI format 1_3 on a
scheduling cell with same SCS between scheduling

\-- cell and cells in the set

multiCell-PDSCH-DCI-1-3-SameSCS-r18 SEQUENCE {

coScheduledCellSCS-r18 SEQUENCE {

nonSharedSpectrum-fdd-fr1 ENUMERATED {supported} OPTIONAL,

nonSharedSpectrum-tdd-fr1 ENUMERATED {supported} OPTIONAL,

sharedSpectrum-tdd-fr1 ENUMERATED {supported} OPTIONAL,

fr2-1 ENUMERATED {supported} OPTIONAL,

fr2-2 ENUMERATED {supported} OPTIONAL

},

maxNumberCoScheduledCell-r18 INTEGER (2..4),

maxNumberSetsOfCellAcrossPUCCH-Group-r18 INTEGER (1..8),

maxNumberSetsOfCellScheduling-r18 INTEGER (1..4),

harqFeedbackType-r18 ENUMERATED {type1, type2, type1And2},

coScheduledCellIndicationScheme-r18 ENUMERATED {fdra,cellInd, both},

supportOfSearchSpace-r18 ENUMERATED {supported} OPTIONAL,

licensed-fdd-tdd-fr1-r18 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- R1 49-1b: Multi-cell PDSCH scheduling by DCI format 1_3 on a
scheduling cell not included in a set of cells with different

\-- SCS/carrier type between scheduling cell and cells in the set

multiCell-PDSCH-DCI-1-3-DiffSCS-r18 SEQUENCE {

coScheduledCellSCS-r18 ENUMERATED {lowScheduling-highScheduled,
highScheduling-lowScheduled, both},

combinationCarrierType-r18 SEQUENCE
(SIZE(1..maxSchedulingBandCombination-r18)) OF

CombinationCarrierType-r18,

maxNumberCoScheduledCell-r18 INTEGER (2..4),

maxNumberSetsOfCellAcrossPUCCH-Group-r18 INTEGER (1..8),

maxNumberSetsOfCellScheduling-r18 INTEGER (1..4),

harqFeedbackType-r18 ENUMERATED {type1, type2, type1And2},

coScheduledCellIndicationScheme-r18 ENUMERATED {fdra,cellInd, both}

} OPTIONAL,

\-- R1 49-2: Multi-cell PUSCH scheduling by DCI format 0_3 on a
scheduling cell with same SCS between scheduling cell

\-- and cells in the set

multiCell-PUSCH-DCI-0-3-SameSCS-r18 SEQUENCE {

coScheduledCellSCS-r18 SEQUENCE {

nonSharedSpectrum-fdd-fr1 ENUMERATED {supported} OPTIONAL,

nonSharedSpectrum-tdd-fr1 ENUMERATED {supported} OPTIONAL,

sharedSpectrum-tdd-fr1 ENUMERATED {supported} OPTIONAL,

fr2-1 ENUMERATED {supported} OPTIONAL,

fr2-2 ENUMERATED {supported} OPTIONAL

},

maxNumberCoScheduledCell-r18 INTEGER (2..4),

maxNumberSetsOfCellAcrossPUCCH-Group-r18 INTEGER (1..8),

maxNumberSetsOfCellScheduling-r18 INTEGER (1..4),

coScheduledCellIndicationScheme-r18 ENUMERATED {fdra,cellInd, both},

supportOfSearchSpace-r18 ENUMERATED {supported} OPTIONAL,

licensed-fdd-tdd-fr1-r18 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- R1 49-2b: Multi-cell PUSCH scheduling by DCI format 0_3 on a
scheduling cell not included in a set of cells with

\-- different SCS/carrier type between scheduling cell and cells in the
set

multiCell-PUSCH-DCI-0-3-DiffSCS-r18 SEQUENCE {

coScheduledCellSCS-r18 ENUMERATED {lowScheduling-highScheduled,
highScheduling-lowScheduled, both},

combinationCarrierType-r18 SEQUENCE
(SIZE(1..maxSchedulingBandCombination-r18)) OF

CombinationCarrierType-r18,

maxNumberCoScheduledCell-r18 INTEGER (2..4),

maxNumberSetsOfCellAcrossPUCCH-Group-r18 INTEGER (1..8),

maxNumberSetsOfCellScheduling-r18 INTEGER (1..4),

coScheduledCellIndicationScheme-r18 ENUMERATED {fdra,cellInd, both}

} OPTIONAL,

\-- R1 49-3x: Advanced UE capability for larger number of unicast DL DCI

advUnicastDCI-DL-r18 SEQUENCE {

scs-15kHz-120kHz-r18 ENUMERATED {n2, n4} OPTIONAL,

scs-15kHz-60kHz-r18 ENUMERATED {n2, n4} OPTIONAL,

scs-30kHz-120kHz-r18 ENUMERATED {n2, n4} OPTIONAL,

scs-15kHz-30kHz-r18 ENUMERATED {n2} OPTIONAL,

scs-30kHz-60kHz-r18 ENUMERATED {n2} OPTIONAL,

scs-60kHz-120kHz-r18 ENUMERATED {n2} OPTIONAL

} OPTIONAL,

\-- R1 49-3y: Advanced UE capability for larger number of unicast UL DCI

advUnicastDCI-UL-r18 SEQUENCE {

scs-15kHz-120kHz-r18 ENUMERATED {n2, n4} OPTIONAL,

scs-15kHz-60kHz-r18 ENUMERATED {n2, n4} OPTIONAL,

scs-30kHz-120kHz-r18 ENUMERATED {n2, n4} OPTIONAL,

scs-15kHz-30kHz-r18 ENUMERATED {n2} OPTIONAL,

scs-30kHz-60kHz-r18 ENUMERATED {n2} OPTIONAL,

scs-60kHz-120kHz-r18 ENUMERATED {n2} OPTIONAL

} OPTIONAL,

\-- R1 49-5a: Trigger Type 3 HARQ CB based feedback using DCI format 1_3

type3HARQ-CB-DCI-1-3-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 49-5b: Trigger enhanced Type 3 HARQ CB based feedback using DCI
format 1_3

type3EnhHARQ-CB-DCI-1-3-r18 SEQUENCE {

numberOfCodebook-r18 ENUMERATED {n1, n2, n4, n8},

maxNumberPUCCH-Trans-r18 INTEGER (1..7)

} OPTIONAL,

\-- R1 49-9: SCell dormancy indication within active time in DCI format
0_3/1_3

scellDormancyWithinActiveTime-DCI-0-3-And-1-3-r18 ENUMERATED {supported}
OPTIONAL,

pdcch-MonitoringCA-Ext-r18 CHOICE {

\-- R1 55-6a: Capability on the number of CCs for monitoring a maximum
number of BDs and non-overlapped CCEs per span when

\-- configured with DL CA with Rel-16 PDCCH monitoring capability on all
the serving cells

pdcch-MonitoringCA-r18 SEQUENCE {

maxNumberOfMonitoringCC-r18 INTEGER (2..16),

supportedSpanArrangement-r18 ENUMERATED {alignedOnly,
alignedAndNonAligned}

},

\-- R1 55-6f: Capability on the number of CCs for monitoring a maximum
number of BDs and non-overlapped CCEs per span when

\-- configured with DL CA with Rel-16 PDCCH monitoring capability on all
the serving cells with restriction for non-aligned

\-- span case

pdcch-MonitoringCA-NonAlignedSpan-r18 INTEGER (2..16)

} OPTIONAL,

pdcch-BlindDetectionCA-MixedExt-r18 CHOICE {

\-- R1 55-6c: Number of carriers for CCE/BD scaling with DL CA with mix
of Rel. 16 and Rel. 15 PDCCH monitoring capabilities on

\-- different carriers

pdcch-BlindDetectionCA-Mixed-r18 SEQUENCE {

blindDetectionCA-Mixed-r18 SEQUENCE(SIZE
(1..maxNrofPdcch-BlindDetectionMixed-1-r16)) OF

PDCCH-BlindDetectionCA-MixedExt-r16,

supportedSpanArrangement-r18 ENUMERATED{ alignedOnly,
alignedAndNonAligned }

},

\-- R1 55-6g: Number of carriers for CCE/BD scaling with DL CA with mix
of Rel. 16 and Rel. 15 PDCCH monitoring capabilities on

\-- different carriers with restriction for non-aligned span case

pdcch-BlindDetectionCA-Mixed-NonAlignedSpan-r18 SEQUENCE(SIZE
(1..maxNrofPdcch-BlindDetectionMixed-1-r16)) OF

PDCCH-BlindDetectionCA-MixedExt-r16

} OPTIONAL,

\-- R1 55-6e: Number of carriers for CCE/BD scaling for MCG and for SCG
when configured for NR-DC operation with mix of Rel. 16

\-- and Rel. 15 PDCCH monitoring capabilities on different carriers

pdcch-BlindDetectionMCG-SCG-List-r18 SEQUENCE(SIZE
(1..maxNrofPdcch-BlindDetectionMixed-1-r16)) OF

PDCCH-BlindDetectionMixed2-r18 OPTIONAL,

\-- R4 33-1: Support of intra-band non-collocated NR CA operation

intraBandNR-CA-non-collocated-r18 ENUMERATED {supported} OPTIONAL

}

CA-ParametersNR-v1830 ::= SEQUENCE {

\-- R1 45-1: Intra-frequency L1 measurement and reports for L1-L2
Triggered Mobility (LTM) procedure

intraFreqL1-MeasConfig-r18 SEQUENCE {

supportedMaxIntraFreqCellsConfig-r18 INTEGER (1..8),

supportedMaxIntraFreqCellsPerReport-r18 INTEGER (1..4),

supportedMaxReportBeamsPerReportedCell-r18 INTEGER (1..4),

supportedMaxReportBeamsReports-r18 ENUMERATED
{n1,n2,n3,n4,n6,n8,n9,n12,n16},

supportedMaxAperiodic-LTM-CSI-ReportConfig-r18 INTEGER (0..4),

supportedMaxPeriodic-LTM-CSI-ReportConfig-r18 INTEGER (1..4),

supportedMaxSemiPersistent-LTM-CSI-ReportConfig-r18 INTEGER (0..4)

} OPTIONAL,

\-- R1 45-1a: Inter-frequency L1 measurement and reports for L1-L2
Triggered Mobility (LTM) procedure

interFreqL1-MeasConfig-r18 SEQUENCE {

supportedMaxIntraInterFreqCellsConfig-r18 INTEGER (1..8),

supportedMaxIntraInterFreqCellsPerReport-r18 INTEGER (1..4),

supportedMaxIntraInterFreqBeamsPerCellReports-r18 INTEGER (1..4),

supportedMaxIntraInterFreqBeamsReports-r18 ENUMERATED
{n1,n2,n3,n4,n6,n8,n9,n12,n16}

} OPTIONAL,

\-- R1 45-2: Inclusion of current SpCell in the L1 measurement report

currentSpCellInclL1-Report-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 39-1: SSB based L1-RSRP measurements for multiple cells with RTD
\> CP

multiCellL1-measRTD-greaterThan-CP-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 39-2: SSB based inter-frequency L1-RSRP measurements without
measurement gaps

interFreqSSB-L1-MeasWithoutGaps-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 39-3-1: Number of frequency layers for L1-RSRP measurement

maxFreqLayersL1-Meas-r18 SEQUENCE {

supportedMaxIntraInterFreqLayersWithoutGaps-r18 INTEGER (1..8) OPTIONAL,

supportedMaxInterFreqLayersWithGaps-r18 INTEGER (1..8) OPTIONAL

} OPTIONAL,

\-- R4 39-3-2: Number of neighbour cells to be measured per frequency
layer

maxNeighCellsPerFreqLayerL1-Meas-r18 SEQUENCE {

supportedMaxNeighCellsPerFreqLayersWithoutGaps-r18 INTEGER (1..8)
OPTIONAL,

supportedMaxNeighCellsPerFreqLayersWithGaps-r18 INTEGER (1..8) OPTIONAL

} OPTIONAL,

\-- R4 39-3-3: Number of total cells to be measured

supportedMaxCellsWithoutGapsL1-Meas-r18 INTEGER (1..24) OPTIONAL,

\-- R4 39-3-4: Number of SSB resources for L1-RSRP measurement within a
slot

supportedMaxSSB-WithinSlotL1-Meas-r18 ENUMERATED
{n1,n2,n3,n4,n5,n6,n7,n8,n16,n32,n48,n64} OPTIONAL,

dummy SEQUENCE {

supportedMaxSSB-PerFreqLayerWithoutGaps-r18 INTEGER (1..8) OPTIONAL,

supportedMaxSSB-PerFreqLayerWithGaps-r18 INTEGER (1..8) OPTIONAL

} OPTIONAL,

\-- R4 39-3-6: Number of total SSB resources to be measured

supportedMaxSSB-L1-Meas-r18 ENUMERATED {n2,n4,n8,n12,n16,n32,n64}
OPTIONAL,

\-- R1 49-13: Default QCL assumption for multi-cell scheduling by DCI
format 1_3

qcl-MultiCellDCI-1-3-r18 ENUMERATED {diff, both} OPTIONAL,

\-- R1 49-14: Support of BWP switch indication by DCI format 0_3/1_3

bwp-SwitchingDCI-0-3-And-1-3-r18 ENUMERATED {supported} OPTIONAL

}

CA-ParametersNR-v1860 ::= SEQUENCE {

\-- R4 39-3-5: Number of SSB resources for L1-RSRP measurement per
frequency layer

maxSSB-PerFreqLayerL1-Meas-r18 SEQUENCE {

supportedMaxSSB-PerFreqLayerWithoutGaps-r18 ENUMERATED
{n1,n2,n3,n4,n5,n6,n7,n8,n12,n16,n20,n24} OPTIONAL,

supportedMaxSSB-PerFreqLayerWithGaps-r18 INTEGER (1..8) OPTIONAL

} OPTIONAL

}

CrossCarrierSchedulingSCell-SpCell-r17 ::= SEQUENCE {

supportedSCS-Combinations-r17 SEQUENCE {

scs15kHz-15kHz-r17 ENUMERATED {supported} OPTIONAL,

scs15kHz-30kHz-r17 ENUMERATED {supported} OPTIONAL,

scs15kHz-60kHz-r17 ENUMERATED {supported} OPTIONAL,

scs30kHz-30kHz-r17 BIT STRING (SIZE (1..496)) OPTIONAL,

scs30kHz-60kHz-r17 BIT STRING (SIZE (1..496)) OPTIONAL,

scs60kHz-60kHz-r17 BIT STRING (SIZE (1..496)) OPTIONAL

},

pdcch-MonitoringOccasion-r17 ENUMERATED {val1, val2}

}

PDCCH-BlindDetectionMixedList-r16::= SEQUENCE {

pdcch-BlindDetectionCA-MixedExt-r16 CHOICE {

pdcch-BlindDetectionCA-Mixed-v16a0 PDCCH-BlindDetectionCA-MixedExt-r16,

pdcch-BlindDetectionCA-Mixed-NonAlignedSpan-v16a0
PDCCH-BlindDetectionCA-MixedExt-r16

} OPTIONAL,

pdcch-BlindDetectionCG-UE-MixedExt-r16 SEQUENCE{

pdcch-BlindDetectionMCG-UE-Mixed-v16a0
PDCCH-BlindDetectionCG-UE-MixedExt-r16,

pdcch-BlindDetectionSCG-UE-Mixed-v16a0
PDCCH-BlindDetectionCG-UE-MixedExt-r16

} OPTIONAL

}

PDCCH-BlindDetectionCA-MixedExt-r16 ::= SEQUENCE {

pdcch-BlindDetectionCA1-r16 INTEGER (1..15),

pdcch-BlindDetectionCA2-r16 INTEGER (1..15)

}

PDCCH-BlindDetectionCG-UE-MixedExt-r16 ::= SEQUENCE {

pdcch-BlindDetectionCG-UE1-r16 INTEGER (0..15),

pdcch-BlindDetectionCG-UE2-r16 INTEGER (0..15)

}

PDCCH-BlindDetectionMCG-SCG-r17 ::= SEQUENCE {

pdcch-BlindDetectionMCG-UE-r17 INTEGER (1..15),

pdcch-BlindDetectionSCG-UE-r17 INTEGER (1..15)

}

PDCCH-BlindDetectionMixed-r17::= SEQUENCE {

pdcch-BlindDetectionCA-Mixed-r17 PDCCH-BlindDetectionCA-Mixed-r17
OPTIONAL,

pdcch-BlindDetectionCG-UE-Mixed-r17 SEQUENCE{

pdcch-BlindDetectionMCG-UE-Mixed-v17
PDCCH-BlindDetectionCG-UE-Mixed-r17,

pdcch-BlindDetectionSCG-UE-Mixed-v17 PDCCH-BlindDetectionCG-UE-Mixed-r17

} OPTIONAL

}

PDCCH-BlindDetectionCG-UE-Mixed-r17 ::= SEQUENCE {

pdcch-BlindDetectionCG-UE1-r17 INTEGER (0..15),

pdcch-BlindDetectionCG-UE2-r17 INTEGER (0..15)

}

PDCCH-BlindDetectionCA-Mixed-r17 ::= SEQUENCE {

pdcch-BlindDetectionCA1-r17 INTEGER (1..15) OPTIONAL,

pdcch-BlindDetectionCA2-r17 INTEGER (1..15) OPTIONAL

}

PDCCH-BlindDetectionMixed1-r17::= SEQUENCE {

pdcch-BlindDetectionCA-Mixed1-r17 PDCCH-BlindDetectionCA-Mixed1-r17
OPTIONAL,

pdcch-BlindDetectionCG-UE-Mixed1-r17 SEQUENCE{

pdcch-BlindDetectionMCG-UE-Mixed1-v17
PDCCH-BlindDetectionCG-UE-Mixed1-r17,

pdcch-BlindDetectionSCG-UE-Mixed1-v17
PDCCH-BlindDetectionCG-UE-Mixed1-r17

} OPTIONAL

}

PDCCH-BlindDetectionCG-UE-Mixed1-r17 ::= SEQUENCE {

pdcch-BlindDetectionCG-UE1-r17 INTEGER (0..15),

pdcch-BlindDetectionCG-UE2-r17 INTEGER (0..15),

pdcch-BlindDetectionCG-UE3-r17 INTEGER (0..15)

}

PDCCH-BlindDetectionCA-Mixed1-r17 ::= SEQUENCE {

pdcch-BlindDetectionCA1-r17 INTEGER (1..15) OPTIONAL,

pdcch-BlindDetectionCA2-r17 INTEGER (1..15) OPTIONAL,

pdcch-BlindDetectionCA3-r17 INTEGER (1..15) OPTIONAL

}

PDCCH-BlindDetectionMixed2-r18 ::= SEQUENCE{

pdcch-BlindDetectionMCG-UE-Mixed-r18
PDCCH-BlindDetectionCG-UE-MixedExt-r16,

pdcch-BlindDetectionSCG-UE-Mixed-r18
PDCCH-BlindDetectionCG-UE-MixedExt-r16

}

SimulSRS-ForAntennaSwitching-r16 ::= SEQUENCE {

supportSRS-xTyR-xLessThanY-r16 ENUMERATED {supported} OPTIONAL,

supportSRS-xTyR-xEqualToY-r16 ENUMERATED {supported} OPTIONAL,

supportSRS-AntennaSwitching-r16 ENUMERATED {supported} OPTIONAL

}

TwoPUCCH-Grp-Configurations-r16 ::= SEQUENCE {

pucch-PrimaryGroupMapping-r16 TwoPUCCH-Grp-ConfigParams-r16,

pucch-SecondaryGroupMapping-r16 TwoPUCCH-Grp-ConfigParams-r16

}

TwoPUCCH-Grp-Configurations-r17 ::= SEQUENCE {

primaryPUCCH-GroupConfig-r17 PUCCH-Group-Config-r17,

secondaryPUCCH-GroupConfig-r17 PUCCH-Group-Config-r17

}

TwoPUCCH-Grp-ConfigParams-r16 ::= SEQUENCE {

pucch-GroupMapping-r16 PUCCH-Grp-CarrierTypes-r16,

pucch-TX-r16 PUCCH-Grp-CarrierTypes-r16

}

CarrierTypePair-r16 ::= SEQUENCE {

carrierForCSI-Measurement-r16 PUCCH-Grp-CarrierTypes-r16,

carrierForCSI-Reporting-r16 PUCCH-Grp-CarrierTypes-r16

}

PUCCH-Grp-CarrierTypes-r16 ::= SEQUENCE {

fr1-NonSharedTDD-r16 ENUMERATED {supported} OPTIONAL,

fr1-SharedTDD-r16 ENUMERATED {supported} OPTIONAL,

fr1-NonSharedFDD-r16 ENUMERATED {supported} OPTIONAL,

fr2-r16 ENUMERATED {supported} OPTIONAL

}

PUCCH-Group-Config-r17 ::= SEQUENCE {

fr1-FR1-NonSharedTDD-r17 ENUMERATED {supported} OPTIONAL,

fr2-FR2-NonSharedTDD-r17 ENUMERATED {supported} OPTIONAL,

fr1-FR2-NonSharedTDD-r17 ENUMERATED {supported} OPTIONAL

}

CombinationCarrierType-r18 ::= SEQUENCE {

schedulingCellCarrierType-r18 ENUMERATED {licensed-fdd-fr1,
licensed-tdd-fr1, unlicensed-tdd-fr1, fr2-1, fr2-2},

scheduledCellCarrierType-r18 ENUMERATED {licensed-fdd-fr1,
licensed-tdd-fr1, unlicensed-tdd-fr1, fr2-1, fr2-2}

}

\-- TAG-CA-PARAMETERSNR-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *CA-ParametersNR* field description                                   |
+=======================================================================+
| ***codebookParametersPerBC***                                         |
|                                                                       |
| For a given supported band combination, this field indicates the      |
| alternative list of *SupportedCSI-RS-Resource* supported for each     |
| codebook type, amongst the supported CSI-RS resources included in     |
| *codebookParametersPerBand* in *MIMO-ParametersPerBand*.              |
+-----------------------------------------------------------------------+
| ***dummy***                                                           |
|                                                                       |
| The field is not used in the specification and the network ignores    |
| the received value.                                                   |
+-----------------------------------------------------------------------+

#### -- *CA-ParametersNRDC*

The IE *CA-ParametersNRDC* contains dual connectivity related
capabilities that are defined per band combination.

*CA-ParametersNRDC* information element

\-- ASN1START

\-- TAG-CA-PARAMETERS-NRDC-START

CA-ParametersNRDC ::= SEQUENCE {

ca-ParametersNR-ForDC CA-ParametersNR OPTIONAL,

ca-ParametersNR-ForDC-v1540 CA-ParametersNR-v1540 OPTIONAL,

ca-ParametersNR-ForDC-v1550 CA-ParametersNR-v1550 OPTIONAL,

ca-ParametersNR-ForDC-v1560 CA-ParametersNR-v1560 OPTIONAL,

featureSetCombinationDC FeatureSetCombinationId OPTIONAL

}

CA-ParametersNRDC-v15g0 ::= SEQUENCE {

ca-ParametersNR-ForDC-v15g0 CA-ParametersNR-v15g0 OPTIONAL

}

CA-ParametersNRDC-v1610 ::= SEQUENCE {

\-- R1 18-1: Semi-static power sharing mode1 between MCG and SCG cells
of same FR for NR dual connectivity

intraFR-NR-DC-PwrSharingMode1-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 18-1a: Semi-static power sharing mode 2 between MCG and SCG cells
of same FR for NR dual connectivity

intraFR-NR-DC-PwrSharingMode2-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 18-1b: Dynamic power sharing between MCG and SCG cells of same FR
for NR dual connectivity

intraFR-NR-DC-DynamicPwrSharing-r16 ENUMERATED {short, long} OPTIONAL,

asyncNRDC-r16 ENUMERATED {supported} OPTIONAL

}

CA-ParametersNRDC-v1630 ::= SEQUENCE {

ca-ParametersNR-ForDC-v1610 CA-ParametersNR-v1610 OPTIONAL,

ca-ParametersNR-ForDC-v1630 CA-ParametersNR-v1630 OPTIONAL

}

CA-ParametersNRDC-v1640 ::= SEQUENCE {

ca-ParametersNR-ForDC-v1640 CA-ParametersNR-v1640 OPTIONAL

}

CA-ParametersNRDC-v1650 ::= SEQUENCE {

supportedCellGrouping-r16 BIT STRING (SIZE (1..maxCellGroupings-r16))
OPTIONAL

}

CA-ParametersNRDC-v16a0 ::= SEQUENCE {

ca-ParametersNR-ForDC-v16a0 CA-ParametersNR-v16a0 OPTIONAL

}

CA-ParametersNRDC-v16j0 ::= SEQUENCE {

ca-ParametersNR-ForDC-v16j0 CA-ParametersNR-v1690 OPTIONAL

}

CA-ParametersNRDC-v1700 ::= SEQUENCE {

\-- R1 31-9: Indicates the support of simultaneous transmission and
reception of an IAB-node from multiple parent nodes

simultaneousRxTx-IAB-MultipleParents-r17 ENUMERATED {supported}
OPTIONAL,

condPSCellAdditionNRDC-r17 ENUMERATED {supported} OPTIONAL,

scg-ActivationDeactivationNRDC-r17 ENUMERATED {supported} OPTIONAL,

scg-ActivationDeactivationResumeNRDC-r17 ENUMERATED {supported}
OPTIONAL,

beamManagementType-CBM-r17 ENUMERATED {supported} OPTIONAL

}

CA-ParametersNRDC-v1720 ::= SEQUENCE {

ca-ParametersNR-ForDC-v1700 CA-ParametersNR-v1700 OPTIONAL,

ca-ParametersNR-ForDC-v1720 CA-ParametersNR-v1720 OPTIONAL

}

CA-ParametersNRDC-v1730 ::= SEQUENCE {

ca-ParametersNR-ForDC-v1730 CA-ParametersNR-v1730 OPTIONAL

}

CA-ParametersNRDC-v1760 ::= SEQUENCE {

ca-ParametersNR-ForDC-v1760 CA-ParametersNR-v1760

}

CA-ParametersNRDC-v1780 ::= SEQUENCE {

ca-ParametersNR-ForDC-v1780 CA-ParametersNR-v1780 OPTIONAL

}

CA-ParametersNRDC-v17b0 ::= SEQUENCE {

ca-ParametersNR-ForDC-v17b0 CA-ParametersNR-v1740 OPTIONAL

}

CA-ParametersNRDC-v1800 ::= SEQUENCE {

ca-ParametersNR-ForDC-v1800 CA-ParametersNR-v1800 OPTIONAL,

\-- R1 55-6d: Capability on the number of CCs for monitoring a maximum
number of BDs and non-overlapped CCEs per span for MCG and for

\-- SCG when configured for NR-DC operation with Rel-16 PDCCH monitoring
on all the serving cells

pdcch-BlindDetectionNRDC-r18 SEQUENCE(SIZE
(1..maxNrofPdcch-BlindDetectionMixed-1-r16)) OF

PDCCH-BlindDetectionMixed1-r18 OPTIONAL

}

CA-ParametersNRDC-v1830 ::= SEQUENCE {

ca-ParametersNR-ForDC-v1830 CA-ParametersNR-v1830 OPTIONAL

}

PDCCH-BlindDetectionMixed1-r18::= SEQUENCE {

pdcch-BlindDetectionCG-UE-Mixed-r18 SEQUENCE{

pdcch-BlindDetectionMCG-UE-Mixed-r18 INTEGER (1..15),

pdcch-BlindDetectionSCG-UE-Mixed-r18 INTEGER (1..15)

}

}

\-- TAG-CA-PARAMETERS-NRDC-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *CA-ParametersNRDC* field descriptions                                |
+=======================================================================+
| ***ca-ParametersNR-forDC (with and without suffix)***                 |
|                                                                       |
| If this field is present for a band combination, it reports the UE    |
| capabilities when NR-DC is configured with the band combination. If a |
| version of this field (i.e., with or without suffix) is absent for a  |
| band combination, the corresponding *ca-ParametersNR* field version   |
| in *BandCombination* is applicable to the UE configured with NR-DC    |
| for the band combination. If a version of this field (i.e., with or   |
| without suffix) is present for a band combination but does not        |
| contain any parameters, the UE does not support the corresponding     |
| field version when configured with NR-DC for the band combination.    |
+-----------------------------------------------------------------------+
| ***featureSetCombinationDC***                                         |
|                                                                       |
| If this field is present for a band combination, it reports the       |
| feature set combination supported for the band combination when NR-DC |
| is configured. If this field is absent for a band combination, the    |
| *featureSetCombination* in *BandCombination* (without suffix) is      |
| applicable to the UE configured with NR-DC for the band combination.  |
+-----------------------------------------------------------------------+

#### -- *CarrierAggregationVariant*

The IE *CarrierAggregationVariant* informs the network about supported
\"placement\" of the SpCell in an NR cell group.

*CarrierAggregationVariant* information element

\-- ASN1START

\-- TAG-CARRIERAGGREGATIONVARIANT-START

CarrierAggregationVariant ::= SEQUENCE {

fr1fdd-FR1TDD-CA-SpCellOnFR1FDD ENUMERATED {supported} OPTIONAL,

fr1fdd-FR1TDD-CA-SpCellOnFR1TDD ENUMERATED {supported} OPTIONAL,

fr1fdd-FR2TDD-CA-SpCellOnFR1FDD ENUMERATED {supported} OPTIONAL,

fr1fdd-FR2TDD-CA-SpCellOnFR2TDD ENUMERATED {supported} OPTIONAL,

fr1tdd-FR2TDD-CA-SpCellOnFR1TDD ENUMERATED {supported} OPTIONAL,

fr1tdd-FR2TDD-CA-SpCellOnFR2TDD ENUMERATED {supported} OPTIONAL,

fr1fdd-FR1TDD-FR2TDD-CA-SpCellOnFR1FDD ENUMERATED {supported} OPTIONAL,

fr1fdd-FR1TDD-FR2TDD-CA-SpCellOnFR1TDD ENUMERATED {supported} OPTIONAL,

fr1fdd-FR1TDD-FR2TDD-CA-SpCellOnFR2TDD ENUMERATED {supported} OPTIONAL

}

\-- TAG-CARRIERAGGREGATIONVARIANT-STOP

\-- ASN1STOP

#### -- *CodebookParameters*

The IE *CodebookParameters* is used to convey codebook related
parameters.

*CodebookParameters* information element

\-- ASN1START

\-- TAG-CODEBOOKPARAMETERS-START

CodebookParameters ::= SEQUENCE {

type1 SEQUENCE {

singlePanel SEQUENCE {

supportedCSI-RS-ResourceList SEQUENCE (SIZE (1..
maxNrofCSI-RS-Resources)) OF SupportedCSI-RS-Resource,

modes ENUMERATED {mode1, mode1andMode2},

maxNumberCSI-RS-PerResourceSet INTEGER (1..8)

},

multiPanel SEQUENCE {

supportedCSI-RS-ResourceList SEQUENCE (SIZE (1..
maxNrofCSI-RS-Resources)) OF SupportedCSI-RS-Resource,

modes ENUMERATED {mode1, mode2, both},

nrofPanels ENUMERATED {n2, n4},

maxNumberCSI-RS-PerResourceSet INTEGER (1..8)

} OPTIONAL

},

type2 SEQUENCE {

supportedCSI-RS-ResourceList SEQUENCE (SIZE (1..
maxNrofCSI-RS-Resources)) OF SupportedCSI-RS-Resource,

parameterLx INTEGER (2..4),

amplitudeScalingType ENUMERATED {wideband, widebandAndSubband},

amplitudeSubsetRestriction ENUMERATED {supported} OPTIONAL

} OPTIONAL,

type2-PortSelection SEQUENCE {

supportedCSI-RS-ResourceList SEQUENCE (SIZE (1..
maxNrofCSI-RS-Resources)) OF SupportedCSI-RS-Resource,

parameterLx INTEGER (2..4),

amplitudeScalingType ENUMERATED {wideband, widebandAndSubband}

} OPTIONAL

}

CodebookParameters-v1610 ::= SEQUENCE {

supportedCSI-RS-ResourceListAlt-r16 SEQUENCE {

type1-SinglePanel-r16 SEQUENCE (SIZE (1..maxNrofCSI-RS-Resources)) OF
INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16) OPTIONAL,

type1-MultiPanel-r16 SEQUENCE (SIZE (1..maxNrofCSI-RS-Resources)) OF
INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16) OPTIONAL,

type2-r16 SEQUENCE (SIZE (1..maxNrofCSI-RS-Resources)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16) OPTIONAL,

type2-PortSelection-r16 SEQUENCE (SIZE (1..maxNrofCSI-RS-Resources)) OF
INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16) OPTIONAL

} OPTIONAL

}

CodebookParametersAddition-r16 ::= SEQUENCE {

etype2-r16 SEQUENCE {

\-- R1 16-3a Regular eType 2 R=1

etype2R1-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF

INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

},

\-- R1 16-3a-1 Regular eType 2 R=2

etype2R2-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF

INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

\-- R1 16-3a-2: Support of parameter combinations 7-8

paramComb7-8-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-3a-3: Support of rank 3,4

rank3-4-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-3a-4: CBSR with soft amplitude restriction

amplitudeSubsetRestriction-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

etype2-PS-r16 SEQUENCE {

\-- R1 16-3b Regular eType 2 R=1 PortSelection

etype2R1-PortSelection-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF

INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

},

\-- R1 16-3b-1 Regular eType 2 R=2 PortSelection

etype2R2-PortSelection-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF

INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

\-- R1 16-3b-2: Support of rank 3,4

rank3-4-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL

}

CodebookComboParametersAddition-r16 ::= SEQUENCE {

\-- R1 16-8 Mixed codebook types

type1SP-Type2-null-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1SP-Type2PS-null-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1SP-eType2R1-null-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1SP-eType2R2-null-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1SP-eType2R1PS-null-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1SP-eType2R2PS-null-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1SP-Type2-Type2PS-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1MP-Type2-null-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1MP-Type2PS-null-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1MP-eType2R1-null-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1MP-eType2R2-null-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1MP-eType2R1PS-null-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1MP-eType2R2PS-null-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL,

type1MP-Type2-Type2PS-r16 SEQUENCE {

supportedCSI-RS-ResourceListAdd-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

} OPTIONAL

}

CodebookParametersfetype2-r17 ::= SEQUENCE {

\-- R1 23-9-1 Basic Features of Further Enhanced Port-Selection Type II
Codebook (FeType-II)

fetype2basic-r17 SEQUENCE (SIZE (1.. maxNrofCSI-RS-ResourcesExt-r16)) OF
INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16),

\-- R1 23-9-2 Support of M=2 and R=1 for FeType-II

fetype2R1-r17 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r17)) OF
INTEGER (0.. maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- R1 23-9-4 Support of R = 2 for FeType-II

fetype2R2-r17 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r17)) OF
INTEGER (0.. maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- R1 23-9-3 Support of rank 3, 4 for FeType-II

fetype2Rank3Rank4-r17 ENUMERATED {supported} OPTIONAL

}

CodebookComboParameterMixedType-r17 ::= SEQUENCE {

\-- R1 23-9-5 Active CSI-RS resources and ports for mixed codebook types
in any slot

type1SP-feType2PS-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-feType2PS-M2R1-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-feType2PS-M2R2-null-r1 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-Type2-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-Type2-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-eType2R1-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-eType2R1-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-feType2PS-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-feType2PS-M2R1-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-feType2PS-M2R2-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-Type2-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-Type2-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-eType2R1-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-eType2R1-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL

}

CodebookComboParameterMultiTRP-r17::= SEQUENCE {

\-- R1 23-7-1b Active CSI-RS resources and ports in the presence of
multi-TRP CSI

\-- {Codebook 2, Codebook 3} =(NULL, NULL}

nCJT-null-null SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16)) OF
INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-null-null SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16)) OF
INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- {Codebook 2, Codebook 3} = {( {\"Rel 16 combinations in FG 16-8\"}

nCJT-Type2-null-r16 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16))
OF INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-Type2PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-eType2R1-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-eType2R2-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-eType2R1PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-eType2R2PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-Type2-Type2PS-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-Type2-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-Type2PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-eType2R1-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-eType2R2-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-eType2R1PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-eType2R2PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-Type2-Type2PS-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- {Codebook 2, Codebook 3} = {\"New Rel17 combinations in FG 23-9-5\"}

nCJT-feType2PS-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-feType2PS-M2R1-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-feType2PS-M2R2-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-Type2-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-Type2-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-eType2R1-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-eType2R1-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-feType2PS-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-feType2PS-M2R1-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-feType2PS-M2R2-null-r1 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-Type2-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-Type2-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-eType2R1-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-eType2R1-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL

}

CodebookParametersAdditionPerBC-r16::= SEQUENCE {

\-- R1 16-3a Regular eType 2 R=1

etype2R1-r16 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16)) OF
INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- R1 16-3a-1 Regular eType 2 R=2

etype2R2-r16 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16)) OF
INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- R1 16-3b Regular eType 2 R=1 PortSelection

etype2R1-PortSelection-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- R1 16-3b-1 Regular eType 2 R=2 PortSelection

etype2R2-PortSelection-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL

}

CodebookComboParametersAdditionPerBC-r16::= SEQUENCE {

\-- R1 16-8 Mixed codebook types

type1SP-Type2-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-Type2PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-eType2R1-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-eType2R2-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-eType2R1PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-eType2R2PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-Type2-Type2PS-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-Type2-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-Type2PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-eType2R1-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-eType2R2-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-eType2R1PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-eType2R2PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-Type2-Type2PS-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL

}

CodebookParametersfetype2PerBC-r17 ::= SEQUENCE {

\-- R1 23-9-1 Basic Features of Further Enhanced Port-Selection Type II
Codebook (FeType-II)

fetype2basic-r17 SEQUENCE (SIZE (1.. maxNrofCSI-RS-ResourcesExt-r16)) OF
INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16),

\-- R1 23-9-2 Support of M=2 and R=1 for FeType-II

fetype2R1-r17 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r17)) OF
INTEGER (0.. maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- R1 23-9-4 Support of R = 2 for FeType-II

fetype2R2-r17 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r17)) OF
INTEGER (0.. maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL

}

CodebookComboParameterMixedTypePerBC-r17 ::= SEQUENCE {

\-- R1 23-9-5 Active CSI-RS resources and ports for mixed codebook types
in any slot

type1SP-feType2PS-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-feType2PS-M2R1-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-feType2PS-M2R2-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-Type2-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-Type2-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-eType2R1-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1SP-eType2R1-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-feType2PS-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-feType2PS-M2R1-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-feType2PS-M2R2-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-Type2-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-Type2-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-eType2R1-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

type1MP-eType2R1-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL

}

CodebookComboParameterMultiTRP-PerBC-r17::= SEQUENCE {

\-- R1 23-7-1b Active CSI-RS resources and ports in the presence of
multi-TRP CSI

\-- {Codebook 2, Codebook 3} =(NULL, NULL}

nCJT-null-null SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16)) OF
INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-null-null SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16)) OF
INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- {Codebook 2, Codebook 3} = {( {\"Rel 16 combinations in FG 16-8\"}

nCJT-Type2-null-r16 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16))
OF INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-Type2PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-eType2R1-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-eType2R2-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-eType2R1PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-eType2R2PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-Type2-Type2PS-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-Type2-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-Type2PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-eType2R1-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-eType2R2-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-eType2R1PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-eType2R2PS-null-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-Type2-Type2PS-r16 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- {Codebook 2, Codebook 3} = {\"New Rel17 combinations in FG 23-9-5\"}

nCJT-feType2PS-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-feType2PS-M2R1-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-feType2PS-M2R2-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-Type2-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-Type2-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-eType2R1-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT-eType2R1-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-feType2PS-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-feType2PS-M2R1-null-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-feType2PS-M2R2-null-r1 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-Type2-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-Type2-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-eType2R1-feType2-PS-M1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

nCJT1SP-eType2R1-feType2-PS-M2R1-r17 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL

}

CodebookParametersetype2DopplerCSI-r18 ::= SEQUENCE {

\-- R1 40-3-2-1: Support of Rel-16-based doppler CSI

eType2Doppler-r18 SEQUENCE {

supportedCSI-RS-ResourceList-r18 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER

(0..maxNrofCSI-RS-ResourcesAlt-1-r16),

valueY-P-SP-CSI-RS-r18 INTEGER (1..3),

valueY-A-CSI-RS-r18 INTEGER (1..3),

scalingfactor-r18 ENUMERATED {n1, n2, n4}

},

\-- R1 40-3-2-1a: Support of Rel-16-based doppler measurement with N4\>1

eType2DopplerN4-r18 SEQUENCE {

supportedCSI-RS-ReportSettingList1-r18 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF

SupportedCSI-RS-ReportSetting-r18,

supportedCSI-RS-ReportSettingList2-r18 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF

SupportedCSI-RS-ReportSetting-r18

} OPTIONAL,

\-- R1 40-3-2-1a-1: DD unit size when A-CSI-RS is configured for CMR
N4\>1

ddUnitSize-A-CSI-RS-CMR-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-2-1b: Maximum number of aperiodic CSI-RS resources that can
be configured in the same CSI report setting for

\-- Rel-16-based doppler measurement

maxNumberAperiodicCSI-RS-Resource-r18 ENUMERATED {n4, n8, n12} OPTIONAL,

\-- R1 40-3-2-2: Support R=2 for Rel-16-based doppler codebook

eType2DopplerR2-r18 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16))
OF INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- R1 40-3-2-3: Support X=1 based on first and last slot of WCSI, for
Rel-16-based doppler codebook

eType2DopplerX1-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-2-3a: Support X=2 CQI based on 2 slots for Rel-16-based
doppler codebook

eType2DopplerX2-r18 ENUMERATED {supported} OPTIONAL,

\--R1 40-3-2-7: support of l = (n - nCSI,ref ) for CSI reference slot
for Rel-16 based doppler codebook

eType2DopplerL-N4D1-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-2-8: Support of L=6 for Rel-16 based doppler codebook

eType2DopplerL6-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-2-9: Support of rank equals 3 and 4 for Rel-16 based doppler
codebook

eType2DopplerR3R4-r18 ENUMERATED {supported} OPTIONAL

}

CodebookParametersfetype2DopplerCSI-r18 ::= SEQUENCE {

\-- R1 40-3-2-4: Support of Rel-17-based doppler CSI

feType2Doppler-r18 SEQUENCE {

supportedCSI-RS-ResourceList-r18 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER

(0..maxNrofCSI-RS-ResourcesAlt-1-r16),

valueY-A-CSI-RS-r18 INTEGER (1..3),

scalingfactor-r18 ENUMERATED {n1, n2, n4}

},

\-- R1 40-3-2-4b: Maximum number of aperiodic CSI-RS resources that can
be configured in the same CSI report setting for

\-- Rel-17-based doppler CSI

maxNumberAperiodicCSI-RS-Resource-r18 ENUMERATED {n4, n8, n12} OPTIONAL,

\-- R1 40-3-2-5: Support of M=2 and R=1 for Rel-17-based doppler
codebook

feType2DopplerM2R1-r18 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER

(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- R1 40-3-2-6: Support R=2 for Rel-17-based doppler codebook

feType2DopplerR2-r18 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16))
OF INTEGER (0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\--R1 40-3-2-7a: Support of l = (n - nCSI,ref ) for CSI reference slot
for Rel-17 based doppler codebook

feType2DopplerL-N4D1-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-2-10: Support of rank equals 3 and 4 for Rel-17 based
doppler codebook

feType2DopplerR3R4-r18 ENUMERATED {supported} OPTIONAL

}

CodebookParametersetype2CJT-r18 ::= SEQUENCE {

\-- R1 40-3-1-1: Basic feature for Rel-16-based CJT type-II codebook

eType2CJT-r18 SEQUENCE {

supportedCSI-RS-ResourceList-r18 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER

(0..maxNrofCSI-RS-ResourcesAlt-1-r16),

scalingfactor-r18 ENUMERATED {n1, n1dot5, n2},

maxNumberNZP-CSI-RS-MultiTRP-CJT-r18 INTEGER (2..4)

},

\-- R1 40-3-1-1a: Support of mode 1 for Rel-16-based CJT type-II
codebook with FD basis selection integer frequency offset

eType2CJT-FD-IO-r18 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16))
OF INTEGER

(0..maxNrofCSI-RS-ResourcesAlt-1-r16) OPTIONAL,

\-- R1 40-3-1-2: Support for FD basis selection fractional offset mode
for Rel-16-based CJT codebook with mode1

eType2CJT-FD-FO-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-1-3: Support R=2 for Rel-16-based CJT codebook

eType2CJT-R2-r18 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16)) OF
INTEGER

(0..maxNrofCSI-RS-ResourcesAlt-1-r16) OPTIONAL,

\-- R1 40-3-1-4: Support pv={1/2,1/2,1/2,1/2} and beta=1/2 for
Rel-16-based CJT codebook

eType2CJT-PV-Beta-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-1-9: Support for 2NN1N2 \>32 for Rel-16 based CJT codebook

eType2CJT-2NN1N2-r18 ENUMERATED {n64,n96,n128} OPTIONAL,

\-- R1 40-3-1-12: Support of Rank 3 and 4 for Rel-16-based CJT type-II
codebook

eType2CJT-Rank3Rank4-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-1-14: Support of Support of L=6 for Rel-16-based CJT type-II
codebook

eType2CJT-L6-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-1-15: dynamic selection of N\<=N_TRP for Rel-16-based CJT
type-II codebook

eType2CJT-NN-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-1-17: Support for N_L\>1 combinations of number of SD basis
across CSI-RS resources for Rel-16-based CJT

\-- type-II codebook

eType2CJT-NL-SD-r18 ENUMERATED {n2,n4} OPTIONAL,

\-- R1 40-3-1-23: Unequal number of spatial basis selection
configuration for multi-TRP CJT

eType2CJT-Unequal-r18 ENUMERATED {supported} OPTIONAL

}

CodebookParametersfetype2CJT-r18 ::= SEQUENCE {

\-- R1 40-3-1-5: Basic feature for Rel-17-based CJT type-II codebook

feType2CJT-r18 SEQUENCE {

supportedCSI-RS-ResourceList-r18 SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER

(0..maxNrofCSI-RS-ResourcesAlt-1-r16),

scalingfactor-r18 ENUMERATED {n1, n1dot5, n2},

maxNumberNZP-CSI-RS-MultiTRP-CJT-r18 INTEGER (2..4)

},

\-- R1 40-3-1-5a: Support of mode 1 for Rel-17-based CJT type-II
codebook with FD basis selection integer frequency offset

feType2CJT-FD-IO-r18 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16))
OF INTEGER

(0..maxNrofCSI-RS-ResourcesAlt-1-r16) OPTIONAL,

\-- R1 40-3-1-6: Support for FD basis selection fractional offset mode
for Rel-17-based CJT codebook with mode1

feType2CJT-FD-FO-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-1-7: Support of M=2 and R=1 for Rel-17-based CJT codebook

feType2CJT-M2R1-r18 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16))
OF INTEGER

(0..maxNrofCSI-RS-ResourcesAlt-1-r16) OPTIONAL,

\-- R1 40-3-1-8: Support of R=2 for Rel-17-based CJT codebook

feType2CJT-R2-r18 SEQUENCE (SIZE (1..maxNrofCSI-RS-ResourcesExt-r16)) OF
INTEGER

(0..maxNrofCSI-RS-ResourcesAlt-1-r16) OPTIONAL,

\-- R1 40-3-1-9a: Support for 2NN1N2 \>32 for Rel-17 based CJT codebook

feType2CJT-2NN1N2-r18 ENUMERATED {n64,n96,n128} OPTIONAL,

\-- R1 40-3-1-13: Support of Rank 3 and 4 for Rel-17-based CJT type-II
codebook

feType2CJT-Rank3Rank4-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-1-16: dynamic selection of N\<=N_TRP for Rel-17-based CJT
type-II codebook

feType2CJT-NN-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-1-18: Support for N_L\>1 combinations of number of SD basis
across CSI-RS resources for Rel-17-based CJT

\-- type-II codebook

feType2CJT-NL-r18 ENUMERATED {n2,n4} OPTIONAL,

\-- R1 40-3-1-23a: Unequal number of port selection configuration for
multi-TRP CJT

feType2CJT-Unequal-r18 ENUMERATED {supported} OPTIONAL

}

CodebookComboParametersCJT-r18::= SEQUENCE {

\-- R1 40-3-1-11: Active CSI-RS resources and ports for mixed codebook
types including Type-II-CJT in any slot

\-- {Codebook 1} = Type I SP

cjt-Type1SP-eType2R1-null SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

cjt-Type1SP-eType2R2-null SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

cjt-Type1SP-feType2R1M1-null SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

cjt-Type1SP-feType2R1M2-null SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

cjt-Type1SP-feType2R2M2-null SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

\-- {Codebook 1} = Type I MP

cjt-Type1MP-eType2R1-null SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

cjt-Type1MP-eType2R2-null SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

cjt-Type1MP-feType2R1M1-null SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

cjt-Type1MP-feType2R1M2-null SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL,

cjt-Type1MP-feType2R2M2-null SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesExt-r16)) OF INTEGER
(0..maxNrofCSI-RS-ResourcesAlt-1-r16)

OPTIONAL

}

CodebookParametersHARQ-ACK-PUSCH-r18::= SEQUENCE {

\-- R1 55-4a: Multiplexing Type-1 HARQ-ACK codebook in a PUSCH for PDSCH
scheduled after UL grant

multiplexingType1-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 55-4b: Multiplexing Type-2 HARQ-ACK codebook in a PUSCH for PDSCH
scheduled after UL grant

multiplexingType2-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 55-4c: Multiplexing Type-3 HARQ-ACK codebook in a PUSCH for PDSCH
scheduled after UL grant

multiplexingType3-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 55-4d: Determining a different PUCCH resource to transmit
HARQ-ACK for PDSCH scheduled after UL grant

pucch-DiffResource-PDSCH-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 55-4e: Determining different codebook size to transmit HARQ-ACK
for PDSCH scheduled after UL grant

diffCB-Size-PDSCH-r18 ENUMERATED {supported} OPTIONAL

}

CodebookVariantsList-r16 ::= SEQUENCE (SIZE
(1..maxNrofCSI-RS-ResourcesAlt-r16)) OF SupportedCSI-RS-Resource

SupportedCSI-RS-Resource ::= SEQUENCE {

maxNumberTxPortsPerResource ENUMERATED {p2, p4, p8, p12, p16, p24, p32},

maxNumberResourcesPerBand INTEGER (1..64),

totalNumberTxPortsPerBand INTEGER (2..256)

}

SupportedCSI-RS-ReportSetting-r18 ::= SEQUENCE {

maxN4-r18 ENUMERATED {n1, n2, n4, n8},

maxNumberTxPortsPerResource-r18 ENUMERATED {p2, p4, p8, p12, p16, p24,
p32},

maxNumberResourcesPerBand-r18 INTEGER (1..64),

totalNumberTxPortsPerBand-r18 INTEGER (2..256)

}

\-- TAG-CODEBOOKPARAMETERS-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *CodebookParameters* field descriptions                               |
+=======================================================================+
| ***supportedCSI-RS-ResourceListAlt***                                 |
|                                                                       |
| This field indicates the alternative list of                          |
| *SupportedCSI-RS-Resource* supported for each codebook type. The      |
| supported CSI-RS resource is indicated by an integer value which      |
| pinpoints *SupportedCSI-RS-Resource* defined in                       |
| *CodebookVariantsList*. The value 0 corresponds to the first entry of |
| *CodebookVariantsList*. The value 1 corresponds to the second entry   |
| of *CodebookVariantsList*, and so on. For each codebook type, the     |
| field shall be included in both *codebookParametersPerBC* (but        |
| optional for single CC) and *codebookParametersPerBand*.              |
+-----------------------------------------------------------------------+

#### -- *DL-PRS-MeasurementWithRxFH-RRC-Connected*

The IE *DL-PRS-MeasurementWithRxFH-RRC-Connected* is used to convey the
capabilities supported by the UE for PRS measurement with Rx frequency
hopping within a measurement gap and measurement reporting in
RRC_CONNECTED for RedCap UEs.

*DL-PRS-MeasurementWithRxFH-RRC-Connected information element*

\-- ASN1START

\-- TAG-DL-PRS-MEASUREMENTWITHRXFH-RRC-CONNECTED-START

DL-PRS-MeasurementWithRxFH-RRC-Connected-r18 ::= SEQUENCE {

maximumPRS-BandwidthAcrossAllHopsFR1-r18 ENUMERATED {mhz40, mhz50,
mhz80, mhz100} OPTIONAL,

maximumPRS-BandwidthAcrossAllHopsFR2-r18 ENUMERATED {mhz100, mhz200,
mhz400} OPTIONAL,

maximumFH-Hops-r18 ENUMERATED {n2, n3, n4, n5, n6} OPTIONAL,

processingDuration-r18 SEQUENCE {

processingPRS-SymbolsDurationN3-r18 ENUMERATED {msDot125, msDot25,
msDot5, ms1, ms2, ms4, ms6, ms8, ms12,

ms16, ms20, ms25, ms30, ms32, ms35, ms40, ms45, ms50},

processingDurationT3-r18 ENUMERATED {ms8, ms16, ms20, ms30, ms40, ms80,
ms160, ms320, ms640, ms1280}

} OPTIONAL,

rf-RxRetuneTimeFR1-r18 ENUMERATED {n70, n140, n210} OPTIONAL,

rf-RxRetuneTimeFR2-r18 ENUMERATED {n35, n70, n140} OPTIONAL,

numOfOverlappingPRB-r18 ENUMERATED {n0, n1, n2, n4} OPTIONAL,

\...

}

\-- TAG-DL-PRS-MEASUREMENTWITHRXFH-RRC-CONNECTED-STOP

\-- ASN1STOP

#### -- *ERedCapParameters*

The IE *ERedCapParameters* is used to indicate the UE capabilities
supported by eRedCap UEs.

*ERedCapParameters* information element

\-- ASN1START

\-- TAG-EREDCAPPARAMETERS-START

ERedCapParameters-r18::= SEQUENCE {

\-- R1 48-1: eRedCap UE with reduced peak data rate and reduced baseband
bandwidth in FR1

supportOfERedCap-r18 ENUMERATED {supported},

\-- R1 48-2: eRedCap UE with reduced peak data rate without reduced
baseband bandwidth in FR1

eRedCapNotReducedBB-BW-r18 ENUMERATED {supported} OPTIONAL,

eRedCapIgnoreCapabilityFiltering-r18 ENUMERATED {supported} OPTIONAL

}

\-- TAG-EREDCAPPARAMETERS-STOP

\-- ASN1STOP

#### -- *FeatureSetCombination*

The IE *FeatureSetCombination* is a two-dimensional matrix of
*FeatureSet* entries.

Each *FeatureSetsPerBand* contains a list of feature sets applicable to
the carrier(s) of one band entry of the associated band combination.
Across the associated bands, the UE shall support the combination of
*FeatureSets* at the same position in the *FeatureSetsPerBand*. All
*FeatureSetsPerBand* in one *FeatureSetCombination* must have the same
number of entries.

The number of *FeatureSetsPerBand* in the *FeatureSetCombination* must
be equal to the number of band entries in an associated band
combination. The first *FeatureSetPerBand* applies to the first band
entry of the band combination, and so on.

Each *FeatureSet* contains either a pair of NR or E-UTRA feature set IDs
for UL and DL.

In case of NR, the actual feature sets for UL and DL are defined in the
*FeatureSets* IE and referred to from here by their ID, i.e., their
position in the *featureSetsUplink* / *featureSetsDownlink* list in the
FeatureSet IE.

In case of E-UTRA, the feature sets referred to from this list are
defined in TS 36.331 \[10\] and conveyed as part of the
*UE-EUTRA-Capability* container.

The *FeatureSetUplink* and *FeatureSetDownlink* referred to from the
*FeatureSet* comprise, among other information, a set of
*FeatureSetUplinkPerCC-Ids* and *FeatureSetDownlinkPerCC-Ids*. The
number of these per-CC IDs determines the number of carriers that the UE
is able to aggregate contiguously in frequency domain in the
corresponding band. The number of carriers supported by the UE is also
restricted by the bandwidth class indicated in the associated
*BandCombination*, if present.

In feature set combinations the UE shall exclude entries with same or
lower capabilities, since the network may anyway assume that the UE
supports those.

NOTE 1: The UE may advertise fallback band-combinations in which it
supports additional functionality explicitly in two ways: Either by
setting FeatureSet IDs to zero (inter-band and intra-band non-contiguous
fallback) and by reducing the number of FeatureSet-PerCC Ids in a
Feature Set (intra-band contiguous fallback). Or by separate
*BandCombination* entries with associated *FeatureSetCombinations*.

NOTE 2: The UE may advertise a *FeatureSetCombination* containing only
fallback band combinations. That means, in a *FeatureSetCombination,*
each group of *FeatureSets* across the bands may contain at least one
pair of *FeatureSetUplinkId* and *FeatureSetDownlinkId* which is set to
0/0.

NOTE 3: The Network configures serving cell(s) and BWP(s) configuration
to comply with capabilities derived from the combination of FeatureSets
at the same position in the FeatureSetsPerBand, regardless of
activated/deactivated serving cell(s) and BWP(s).

*FeatureSetCombination* information element

\-- ASN1START

\-- TAG-FEATURESETCOMBINATION-START

FeatureSetCombination ::= SEQUENCE (SIZE (1..maxSimultaneousBands)) OF
FeatureSetsPerBand

FeatureSetsPerBand ::= SEQUENCE (SIZE (1..maxFeatureSetsPerBand)) OF
FeatureSet

FeatureSet ::= CHOICE {

eutra SEQUENCE {

downlinkSetEUTRA FeatureSetEUTRA-DownlinkId,

uplinkSetEUTRA FeatureSetEUTRA-UplinkId

},

nr SEQUENCE {

downlinkSetNR FeatureSetDownlinkId,

uplinkSetNR FeatureSetUplinkId

}

}

\-- TAG-FEATURESETCOMBINATION-STOP

\-- ASN1STOP

#### -- *FeatureSetCombinationId*

The IE *FeatureSetCombinationId* identifies a *FeatureSetCombination*.
The *FeatureSetCombinationId* of a *FeatureSetCombination* is the
position of the *FeatureSetCombination* in the featureSetCombinations
list (in *UE-NR-Capability* or *UE-MRDC-Capability*). The
*FeatureSetCombinationId* = 0 refers to the first entry in the
*featureSetCombinations* list (in *UE-NR-Capability* or
*UE-MRDC-Capability*).

NOTE: The *FeatureSetCombinationId* = 1024 is not used due to the
maximum entry number of *featureSetCombinations*.

*FeatureSetCombinationId* information element

\-- ASN1START

\-- TAG-FEATURESETCOMBINATIONID-START

FeatureSetCombinationId ::= INTEGER (0.. maxFeatureSetCombinations)

\-- TAG-FEATURESETCOMBINATIONID-STOP

\-- ASN1STOP

#### -- *FeatureSetDownlink*

The IE *FeatureSetDownlink* indicates a set of features that the UE
supports on the carriers corresponding to one band entry in a band
combination.

*FeatureSetDownlink* information element

\-- ASN1START

\-- TAG-FEATURESETDOWNLINK-START

FeatureSetDownlink ::= SEQUENCE {

featureSetListPerDownlinkCC SEQUENCE (SIZE (1..maxNrofServingCells)) OF
FeatureSetDownlinkPerCC-Id,

intraBandFreqSeparationDL FreqSeparationClass OPTIONAL,

scalingFactor ENUMERATED {f0p4, f0p75, f0p8} OPTIONAL,

dummy8 ENUMERATED {supported} OPTIONAL,

scellWithoutSSB ENUMERATED {supported} OPTIONAL,

csi-RS-MeasSCellWithoutSSB ENUMERATED {supported} OPTIONAL,

dummy1 ENUMERATED {supported} OPTIONAL,

type1-3-CSS ENUMERATED {supported} OPTIONAL,

pdcch-MonitoringAnyOccasions ENUMERATED {withoutDCI-Gap, withDCI-Gap}
OPTIONAL,

dummy2 ENUMERATED {supported} OPTIONAL,

ue-SpecificUL-DL-Assignment ENUMERATED {supported} OPTIONAL,

searchSpaceSharingCA-DL ENUMERATED {supported} OPTIONAL,

timeDurationForQCL SEQUENCE {

scs-60kHz ENUMERATED {s7, s14, s28} OPTIONAL,

scs-120kHz ENUMERATED {s14, s28} OPTIONAL

} OPTIONAL,

pdsch-ProcessingType1-DifferentTB-PerSlot SEQUENCE {

scs-15kHz ENUMERATED {upto2, upto4, upto7} OPTIONAL,

scs-30kHz ENUMERATED {upto2, upto4, upto7} OPTIONAL,

scs-60kHz ENUMERATED {upto2, upto4, upto7} OPTIONAL,

scs-120kHz ENUMERATED {upto2, upto4, upto7} OPTIONAL

} OPTIONAL,

dummy3 DummyA OPTIONAL,

dummy4 SEQUENCE (SIZE (1.. maxNrofCodebooks)) OF DummyB OPTIONAL,

dummy5 SEQUENCE (SIZE (1.. maxNrofCodebooks)) OF DummyC OPTIONAL,

dummy6 SEQUENCE (SIZE (1.. maxNrofCodebooks)) OF DummyD OPTIONAL,

dummy7 SEQUENCE (SIZE (1.. maxNrofCodebooks)) OF DummyE OPTIONAL

}

FeatureSetDownlink-v1540 ::= SEQUENCE {

oneFL-DMRS-TwoAdditionalDMRS-DL ENUMERATED {supported} OPTIONAL,

additionalDMRS-DL-Alt ENUMERATED {supported} OPTIONAL,

twoFL-DMRS-TwoAdditionalDMRS-DL ENUMERATED {supported} OPTIONAL,

oneFL-DMRS-ThreeAdditionalDMRS-DL ENUMERATED {supported} OPTIONAL,

pdcch-MonitoringAnyOccasionsWithSpanGap SEQUENCE {

scs-15kHz ENUMERATED {set1, set2, set3} OPTIONAL,

scs-30kHz ENUMERATED {set1, set2, set3} OPTIONAL,

scs-60kHz ENUMERATED {set1, set2, set3} OPTIONAL,

scs-120kHz ENUMERATED {set1, set2, set3} OPTIONAL

} OPTIONAL,

pdsch-SeparationWithGap ENUMERATED {supported} OPTIONAL,

pdsch-ProcessingType2 SEQUENCE {

scs-15kHz ProcessingParameters OPTIONAL,

scs-30kHz ProcessingParameters OPTIONAL,

scs-60kHz ProcessingParameters OPTIONAL

} OPTIONAL,

pdsch-ProcessingType2-Limited SEQUENCE {

differentTB-PerSlot-SCS-30kHz ENUMERATED {upto1, upto2, upto4, upto7}

} OPTIONAL,

dl-MCS-TableAlt-DynamicIndication ENUMERATED {supported} OPTIONAL

}

FeatureSetDownlink-v15a0 ::= SEQUENCE {

supportedSRS-Resources SRS-Resources OPTIONAL

}

FeatureSetDownlink-v15t0 ::= SEQUENCE {

zeroSlotOffsetAperiodicSRS ENUMERATED {supported} OPTIONAL

}

FeatureSetDownlink-v1610 ::= SEQUENCE {

\-- R1 22-4e/4f/4g/4h: CBG based reception for DL with unicast PDSCH(s)
per slot per CC with UE processing time Capability 1

cbgPDSCH-ProcessingType1-DifferentTB-PerSlot-r16 SEQUENCE {

scs-15kHz-r16 ENUMERATED {one, upto2, upto4, upto7} OPTIONAL,

scs-30kHz-r16 ENUMERATED {one, upto2, upto4, upto7} OPTIONAL,

scs-60kHz-r16 ENUMERATED {one, upto2, upto4, upto7} OPTIONAL,

scs-120kHz-r16 ENUMERATED {one, upto2, upto4, upto7} OPTIONAL

} OPTIONAL,

\-- R1 22-3e/3f/3g/3h: CBG based reception for DL with unicast PDSCH(s)
per slot per CC with UE processing time Capability 2

cbgPDSCH-ProcessingType2-DifferentTB-PerSlot-r16 SEQUENCE {

scs-15kHz-r16 ENUMERATED {one, upto2, upto4, upto7} OPTIONAL,

scs-30kHz-r16 ENUMERATED {one, upto2, upto4, upto7} OPTIONAL,

scs-60kHz-r16 ENUMERATED {one, upto2, upto4, upto7} OPTIONAL,

scs-120kHz-r16 ENUMERATED {one, upto2, upto4, upto7} OPTIONAL

} OPTIONAL,

intraFreqDAPS-r16 SEQUENCE {

intraFreqDiffSCS-DAPS-r16 ENUMERATED {supported} OPTIONAL,

intraFreqAsyncDAPS-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

intraBandFreqSeparationDL-v1620 FreqSeparationClassDL-v1620 OPTIONAL,

intraBandFreqSeparationDL-Only-r16 FreqSeparationClassDL-Only-r16
OPTIONAL,

\-- R1 11-2: Rel-16 PDCCH monitoring capability

pdcch-Monitoring-r16 SEQUENCE {

pdsch-ProcessingType1-r16 SEQUENCE {

scs-15kHz-r16 PDCCH-MonitoringOccasions-r16 OPTIONAL,

scs-30kHz-r16 PDCCH-MonitoringOccasions-r16 OPTIONAL

} OPTIONAL,

pdsch-ProcessingType2-r16 SEQUENCE {

scs-15kHz-r16 PDCCH-MonitoringOccasions-r16 OPTIONAL,

scs-30kHz-r16 PDCCH-MonitoringOccasions-r16 OPTIONAL

} OPTIONAL

} OPTIONAL,

\-- R1 11-2b: Mix of Rel. 16 PDCCH monitoring capability and Rel. 15
PDCCH monitoring capability on different carriers

pdcch-MonitoringMixed-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 18-5c: Processing up to X unicast DCI scheduling for DL per
scheduled CC

crossCarrierSchedulingProcessing-DiffSCS-r16 SEQUENCE {

scs-15kHz-120kHz-r16 ENUMERATED {n1,n2,n4} OPTIONAL,

scs-15kHz-60kHz-r16 ENUMERATED {n1,n2,n4} OPTIONAL,

scs-30kHz-120kHz-r16 ENUMERATED {n1,n2,n4} OPTIONAL,

scs-15kHz-30kHz-r16 ENUMERATED {n2} OPTIONAL,

scs-30kHz-60kHz-r16 ENUMERATED {n2} OPTIONAL,

scs-60kHz-120kHz-r16 ENUMERATED {n2} OPTIONAL

} OPTIONAL,

\-- R1 16-2b-1: Support of single-DCI based SDM scheme

singleDCI-SDM-scheme-r16 ENUMERATED {supported} OPTIONAL

}

FeatureSetDownlink-v16k0 ::= SEQUENCE {

\-- R1 22-8: For SRS for CB PUSCH and antenna switching on FR1 with
symbol level offset for aperiodic SRS transmission

offsetSRS-CB-PUSCH-Ant-Switch-fr1-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 22-8a: PDCCH monitoring on any span of up to 3 consecutive OFDM
symbols of a slot and constrained timeline for SRS for CB

\-- PUSCH and antenna switching on FR1

offsetSRS-CB-PUSCH-PDCCH-MonitorSingleOcc-fr1-r16 ENUMERATED {supported}
OPTIONAL,

\-- R1 22-8b: For type 1 CSS with dedicated RRC configuration, type 3
CSS, and UE-SS, monitoring occasion can be any OFDM symbol(s)

\-- of a slot for Case 2 and constrained timeline for SRS for CB PUSCH
and antenna switching on FR1

offsetSRS-CB-PUSCH-PDCCH-MonitorAnyOccWithoutGap-fr1-r16 ENUMERATED
{supported} OPTIONAL,

\-- R1 22-8c: For type 1 CSS with dedicated RRC configuration, type 3
CSS, and UE-SS, monitoring occasion can be any OFDM symbol(s)

\-- of a slot for Case 2 with a DCI gap and constrained timeline for SRS
for CB PUSCH and antenna switching on FR1

offsetSRS-CB-PUSCH-PDCCH-MonitorAnyOccWithGap-fr1-r16 ENUMERATED
{supported} OPTIONAL,

\-- R1 22-8d: All PDCCH monitoring occasion can be any OFDM symbol(s) of
a slot for Case 2 with a span gap and constrained timeline

\-- for SRS for CB PUSCH and antenna switching on FR1

offsetSRS-CB-PUSCH-PDCCH-MonitorAnyOccWithSpanGap-fr1-r16 SEQUENCE {

scs-15kHz-r16 ENUMERATED {set1, set2, set3} OPTIONAL,

scs-30kHz-r16 ENUMERATED {set1, set2, set3} OPTIONAL,

scs-60kHz-r16 ENUMERATED {set1, set2, set3} OPTIONAL

} OPTIONAL

}

FeatureSetDownlink-v1700 ::= SEQUENCE {

\-- R1 36-2: Scaling factor to be applied to 1024QAM for FR1

scalingFactor-1024QAM-FR1-r17 ENUMERATED {f0p4, f0p75, f0p8} OPTIONAL,

\-- R1 24 feature for existing UE cap to include new SCS

timeDurationForQCL-v1710 SEQUENCE {

scs-480kHz ENUMERATED {s56, s112} OPTIONAL,

scs-960kHz ENUMERATED {s112, s224} OPTIONAL

} OPTIONAL,

\-- R1 23-6-1 SFN scheme A (scheme 1) for PDSCH and PDCCH

sfn-SchemeA-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-6-1-1 SFN scheme A (scheme 1) for PDCCH only

sfn-SchemeA-PDCCH-only-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-6-1a Dynamic switching - scheme A

sfn-SchemeA-DynamicSwitching-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-6-1b SFN scheme A (scheme 1) for PDSCH only

sfn-SchemeA-PDSCH-only-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-6-2 SFN scheme B (TRP based pre-compensation) for PDSCH and
PDCCH

sfn-SchemeB-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-6-2a Dynamic switching - scheme B

sfn-SchemeB-DynamicSwitching-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-6-2b SFN scheme B (TRP based pre-compensation) for PDSCH only

sfn-SchemeB-PDSCH-only-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-2-1d PDCCH repetition for Case 2 PDCCH monitoring with a span
gap

mTRP-PDCCH-Case2-1SpanGap-r17 SEQUENCE {

scs-15kHz-r17 PDCCH-RepetitionParameters-r17 OPTIONAL,

scs-30kHz-r17 PDCCH-RepetitionParameters-r17 OPTIONAL,

scs-60kHz-r17 PDCCH-RepetitionParameters-r17 OPTIONAL,

scs-120kHz-r17 PDCCH-RepetitionParameters-r17 OPTIONAL

} OPTIONAL,

\-- R1 23-2-1e PDCCH repetition for Rel-16 PDCCH monitoring

mTRP-PDCCH-legacyMonitoring-r17 SEQUENCE {

scs-15kHz-r17 PDCCH-RepetitionParameters-r17 OPTIONAL,

scs-30kHz-r17 PDCCH-RepetitionParameters-r17 OPTIONAL

} OPTIONAL,

\-- R1 23-2-4 Simultaneous configuration of PDCCH repetition and
multi-DCI based multi-TRP

mTRP-PDCCH-multiDCI-multiTRP-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-2: Dynamic scheduling for multicast for PCell

dynamicMulticastPCell-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-2-1 PDCCH repetition

mTRP-PDCCH-Repetition-r17 SEQUENCE {

numBD-twoPDCCH-r17 INTEGER (2..3),

maxNumOverlaps-r17 ENUMERATED {n1,n2,n3,n5,n10,n20,n40}

} OPTIONAL

}

FeatureSetDownlink-v1720 ::= SEQUENCE {

\-- R1 25-19: RTT-based Propagation delay compensation based on CSI-RS
for tracking and SRS

rtt-BasedPDC-CSI-RS-ForTracking-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 25-19a: RTT-based Propagation delay compensation based on DL PRS
for RTT-based PDC and SRS

rtt-BasedPDC-PRS-r17 SEQUENCE {

maxNumberPRS-Resource-r17 ENUMERATED {n1, n2, n4, n8, n16, n32, n64},

maxNumberPRS-ResourceProcessedPerSlot-r17 SEQUENCE {

scs-15kHz-r17 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48,
n64} OPTIONAL,

scs-30kHz-r17 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48,
n64} OPTIONAL,

scs-60kHz-r17 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48,
n64} OPTIONAL,

scs-120kHz-r17 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48,
n64} OPTIONAL

}

} OPTIONAL,

\-- R1 33-5-1: SPS group-common PDSCH for multicast on PCell

sps-Multicast-r17 ENUMERATED {supported} OPTIONAL

}

FeatureSetDownlink-v1730 ::= SEQUENCE {

\-- R1 25-19b: Support of PRS as spatial relation RS for SRS

prs-AsSpatialRelationRS-For-SRS-r17 ENUMERATED {supported} OPTIONAL

}

FeatureSetDownlink-v17d0 ::= SEQUENCE {

\-- R1 23-8-4 Maximum 2 SP and 1 periodic SRS sets for antenna switching

srs-AntennaSwitching2SP-1Periodic-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-8-9 Extension of aperiodic SRS configuration for 1T4R, 1T2R
and 2T4R

srs-ExtensionAperiodicSRS-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-8-10 1 aperiodic SRS resource set for 1T4R

srs-OneAP-SRS-r17 ENUMERATED {supported} OPTIONAL

}

FeatureSetDownlink-v1800 ::= SEQUENCE {

\-- R1 40-1-14a: Dynamic switching - scheme A

dynamicSwitchingA-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-1-14b: Dynamic switching - scheme B

dynamicSwitchingB-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-2-11: Aperiodic CSI report timing relaxation for doppler
codebook based on Type-II codebook

aperiodicCSI-TimeRelaxation-r18 SEQUENCE {

valueW-r18 SEQUENCE{

scs-15kHz ENUMERATED {value1, value2} OPTIONAL,

scs-30kHz ENUMERATED {value1, value2} OPTIONAL,

scs-60kHz ENUMERATED {value1, value2} OPTIONAL,

scs-120kHz ENUMERATED {value1, value2} OPTIONAL

},

timeRelaxation-r18 ENUMERATED {cap1, cap2}

} OPTIONAL,

\-- R1 40-4-1: Basic feature of Rel.18 enhanced DMRS ports for PDSCH for
scheduling of mapping type A

pdsch-TypeA-DMRS-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-1a: Basic feature of Rel.18 enhanced DMRS ports for PDSCH
for scheduling of mapping type B

pdsch-TypeB-DMRS-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-1b: 1 symbol FL DMRS and 2 additional DMRS symbols for more
than one port for Rel.18 enhanced DMRS ports for PDSCH

pdsch-1SymbolFL-DMRS-Addition2Symbol-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-4-1c: Alternative additional DMRS position for co-existence
with LTE CRS for Rel.18 enhanced DMRS ports for PDSCH

pdsch-AlternativeDMRS-Coexistence-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-1d: 2 symbols FL-DMRS for Rel.18 enhanced DMRS ports for
PDSCH

pdsch-2SymbolFL-DMRS-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-1e: 2-symbol FL DMRS + one additional 2-symbols DMRS for
Rel.18 enhanced DMRS ports for PDSCH

pdsch-2SymbolFL-DMRS-Addition2Symbol-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-4-1f: 1 symbol FL DMRS and 3 additional DMRS symbols for
Rel.18 enhanced DMRS ports for PDSCH

pdsch-1SymbolFL-DMRS-Addition3Symbol-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-4-1g: DMRS type for Rel.18 enhanced DMRS ports for PDSCH

pdsch-DMRS-Type-r18 ENUMERATED {etype1, etype1And2} OPTIONAL,

\-- R1 40-4-1h: 1 port DL PTRS for Rel.18 enhanced DMRS ports for PDSCH
with rank 1-8

pdsch-1PortDL-PTRS-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-1i: 2 port DL PTRS for Rel.18 enhanced DMRS ports for PDSCH
with rank 1-8

pdsch-2PortDL-PTRS-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-1j: Support 1 symbol FL DMRS and 2 additional DMRS symbols
for one port for scheduling of mapping type A

mappingTypeA-1SymbolFL-DMRS-Addition2Symbol-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-4-2: Capability on the maximum number of configured DMRS types
for PDSCH across all DL DCI formats per cell

maxNumberDMRS-AcrossAllDL-DCI-r18 INTEGER (2..4) OPTIONAL,

\-- R1 40-4-4: Reception of PDSCH without the scheduling restriction for
Rel.18 eType1 DMRS ports

pdsch-ReceptionWithoutSchedulingRestriction-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-4-4a: Reception of PDSCH without the scheduling restriction
for Rel.18 eType1 DMRS ports for PDSCH with fdmSchemeA

pdsch-ReceptionSchemeA-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-4b: Reception of PDSCH without the scheduling restriction
for Rel.18 eType1 DMRS ports for PDSCH with fdmSchemeB

pdsch-ReceptionSchemeB-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-5: Rel-18 DL DMRS with single DCI based M-TRP

dmrs-MultiTRP-SingleDCI-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-5a: Additional row(s) for antenna ports (0,2,3) for Rel.18
DL DMRS ports for single-DCI based M-TRP

dmrs-MultiTRP-AdditionRows-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-7: Rel-18 DL DMRS with M-DCI based M-TRP

dmrs-MultiTRP-MultiDCI-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-12: Support of Rel-18 DMRS and PDSCH processing capability 2
simultaneously

simulDMRS-PDSCH-r18 SEQUENCE {

scs-15kHz-r18 INTEGER (0..4) OPTIONAL,

scs-30kHz-r18 INTEGER (0..5) OPTIONAL,

scs-60kHz-r18 INTEGER (0..7) OPTIONAL

} OPTIONAL,

\-- R1 53-1: Support RLM/BM/BFD and gapless L3 intra-frequency
measurements based on CD-SSB outside active BWP without interruptions

bwpOperationMeasWithoutInterrupt-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 55-6: (2, 2) span-based PDCCH monitoring with additional
restriction(s)

pdcch-MonitoringSpan2-2-r18 SEQUENCE{

pdsch-ProcessingType1-r18 SEQUENCE{

scs-15kHz-r18 ENUMERATED {supported} OPTIONAL,

scs-30kHz-r18 ENUMERATED {supported} OPTIONAL

},

pdsch-ProcessingType2-r18 SEQUENCE{

scs-15kHz-r18 ENUMERATED {supported} OPTIONAL,

scs-30kHz-r18 ENUMERATED {supported} OPTIONAL

}

} OPTIONAL,

\-- R1 55-6b: Mix of Rel-16 PDCCH monitoring capability and Rel. 15
PDCCH monitoring capability on different carriers

pdcch-MonitoringMixed-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 55-6h: PDCCH repetition for Rel-16 PDCCH monitoring

mTRP-PDCCH-legacyMonitoring-r18 SEQUENCE {

scs-15kHz-r18 PDCCH-RepetitionParameters-r17 OPTIONAL,

scs-30kHz-r18 PDCCH-RepetitionParameters-r17 OPTIONAL

} OPTIONAL,

\-- R4 42-1: Support of SCell without SS/PBCH block for inter-band CA

scellWithoutSSB-InterBandCA-r18 CHOICE {

supportOfSingleGroup ENUMERATED {referenceBand, scellWithoutSSB, both},

supportOfMultipleGroups ENUMERATED {referenceBand1, scellWithoutSSB1,
referenceBand2, scellWithoutSSB2}

} OPTIONAL,

dummy SEQUENCE (SIZE (1..maxBandsMRDC)) OF Dummy-PDCCH-RACH-DL-Info-r18
OPTIONAL

}

FeatureSetDownlink-v1830 ::= SEQUENCE {

\-- R4 39-4: Interruption on DL slot(s) due to PDCCH- ordered RACH
transmission

pdcch-RACH-AffectedBands-TargetBandList-r18 SEQUENCE (SIZE
(1..maxBandsMRDC)) OF ENUMERATED {noInterruption, interruption}

OPTIONAL,

\-- R4 39-4a: Interruption due to RF retuning for PDCCH- ordered RACH

pdcch-RACH-SwitchingTime-TargetBandList-r18 SEQUENCE (SIZE
(1..maxBandsMRDC)) OF ENUMERATED {ms0, ms0dot25, ms0dot5, ms1, ms2,
notSupported}

OPTIONAL,

\-- R4 39-5: the RF/BB preparation time for PDCCH ordered RACH of which
the resources are not fully contained

\-- in any of UE\'s configured UL BWP(s) of active serving cells

pdcch-RACH-PrepTime-TargetBandList-r18 SEQUENCE (SIZE (1..maxBandsMRDC))
OF ENUMERATED {ms1, ms3, ms5, ms10, notSupported}

OPTIONAL

}

FeatureSetDownlink-v1860 ::= SEQUENCE {

\-- R1 40-5-5: Maximum 2 SP and 1 periodic SRS sets for 8T8R antenna
switching

srs-AntennaSwitching8T8R2SP-1Periodic-r18 ENUMERATED {supported}
OPTIONAL

}

PDCCH-MonitoringOccasions-r16 ::= SEQUENCE {

period7span3-r16 ENUMERATED {supported} OPTIONAL,

period4span3-r16 ENUMERATED {supported} OPTIONAL,

period2span2-r16 ENUMERATED {supported} OPTIONAL

}

PDCCH-RepetitionParameters-r17 ::= SEQUENCE {

supportedMode-r17 ENUMERATED {intra-span, inter-span, both},

limitX-PerCC-r17 ENUMERATED {n4, n8, n16, n32, n44, n64, nolimit}
OPTIONAL,

limitX-AcrossCC-r17 ENUMERATED {n4, n8, n16, n32, n44, n64, n128, n256,
n512, nolimit} OPTIONAL

}

DummyA ::= SEQUENCE {

maxNumberNZP-CSI-RS-PerCC INTEGER (1..32),

maxNumberPortsAcrossNZP-CSI-RS-PerCC ENUMERATED {p2, p4, p8, p12, p16,
p24, p32, p40, p48, p56, p64, p72, p80,

p88, p96, p104, p112, p120, p128, p136, p144, p152, p160, p168,

p176, p184, p192, p200, p208, p216, p224, p232, p240, p248, p256},

maxNumberCS-IM-PerCC ENUMERATED {n1, n2, n4, n8, n16, n32},

maxNumberSimultaneousCSI-RS-ActBWP-AllCC ENUMERATED {n5, n6, n7, n8, n9,
n10, n12, n14, n16, n18, n20, n22, n24, n26,

n28, n30, n32, n34, n36, n38, n40, n42, n44, n46, n48, n50, n52,

n54, n56, n58, n60, n62, n64},

totalNumberPortsSimultaneousCSI-RS-ActBWP-AllCC ENUMERATED {p8, p12,
p16, p24, p32, p40, p48, p56, p64, p72, p80,

p88, p96, p104, p112, p120, p128, p136, p144, p152, p160, p168,

p176, p184, p192, p200, p208, p216, p224, p232, p240, p248, p256}

}

DummyB ::= SEQUENCE {

maxNumberTxPortsPerResource ENUMERATED {p2, p4, p8, p12, p16, p24, p32},

maxNumberResources INTEGER (1..64),

totalNumberTxPorts INTEGER (2..256),

supportedCodebookMode ENUMERATED {mode1, mode1AndMode2},

maxNumberCSI-RS-PerResourceSet INTEGER (1..8)

}

DummyC ::= SEQUENCE {

maxNumberTxPortsPerResource ENUMERATED {p8, p16, p32},

maxNumberResources INTEGER (1..64),

totalNumberTxPorts INTEGER (2..256),

supportedCodebookMode ENUMERATED {mode1, mode2, both},

supportedNumberPanels ENUMERATED {n2, n4},

maxNumberCSI-RS-PerResourceSet INTEGER (1..8)

}

DummyD ::= SEQUENCE {

maxNumberTxPortsPerResource ENUMERATED {p4, p8, p12, p16, p24, p32},

maxNumberResources INTEGER (1..64),

totalNumberTxPorts INTEGER (2..256),

parameterLx INTEGER (2..4),

amplitudeScalingType ENUMERATED {wideband, widebandAndSubband},

amplitudeSubsetRestriction ENUMERATED {supported} OPTIONAL,

maxNumberCSI-RS-PerResourceSet INTEGER (1..8)

}

DummyE ::= SEQUENCE {

maxNumberTxPortsPerResource ENUMERATED {p4, p8, p12, p16, p24, p32},

maxNumberResources INTEGER (1..64),

totalNumberTxPorts INTEGER (2..256),

parameterLx INTEGER (2..4),

amplitudeScalingType ENUMERATED {wideband, widebandAndSubband},

maxNumberCSI-RS-PerResourceSet INTEGER (1..8)

}

Dummy-PDCCH-RACH-DL-Info-r18 ::= CHOICE {

notSupported NULL,

supported SEQUENCE {

\-- R4 39-4: Interruption on DL slot(s) due to PDCCH- ordered RACH
transmission

pdcch-RACH-AffectedBands-r18 ENUMERATED {noIntrruption, interruption},

\-- R4 39-4a: Interruption on DL slot(s) due to PDCCH- ordered RACH
transmission

pdcch-RACH-SwitchingTimeList-r18 ENUMERATED {ms0, ms0dot25, ms0dot5 ,
ms1, ms2} OPTIONAL,

\-- R4 39-5: the RF/BB preparation time for PDCCH ordered RACH of which
the resources are not fully contained

\-- in any of UE\'s configured UL BWP(s) of active serving cells

pdcch-RACH-PrepTime-r18 ENUMERATED {ms1, ms3, ms5, ms10} OPTIONAL

}

}

\-- TAG-FEATURESETDOWNLINK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *FeatureSetDownlink* field descriptions                               |
+=======================================================================+
| ***featureSetListPerDownlinkCC***                                     |
|                                                                       |
| Indicates which features the UE supports on the individual DL         |
| carriers of the feature set (and hence of a band entry that refer to  |
| the feature set). The UE shall hence include at least as many         |
| *FeatureSetDownlinkPerCC-Id* in this list as the number of carriers   |
| it supports according to the *ca-BandwidthClassDL*, except if         |
| indicating additional functionality by reducing the number of         |
| *FeatureSetDownlinkPerCC-Id* in the feature set (see NOTE 1 in        |
| *FeatureSetCombination* IE description). The order of the elements in |
| this list is not relevant, i.e., the network may configure any of the |
| carriers in accordance with any of the *FeatureSetDownlinkPerCC-Id*   |
| in this list.                                                         |
+-----------------------------------------------------------------------+
| ***supportedSRS-Resources***                                          |
|                                                                       |
| Indicates supported SRS resources for SRS carrier switching to the    |
| band associated with this *FeatureSetDownlink*. The UE is only        |
| allowed to set this field for a band with associated                  |
| *FeatureSetUplinkId* set to 0.                                        |
+-----------------------------------------------------------------------+

#### -- *FeatureSetDownlinkId*

The IE *FeatureSetDownlinkId* identifies a downlink feature set. The
*FeatureSetDownlinkId* of a *FeatureSetDownlink* is the index position
of the *FeatureSetDownlink* in the *featureSetsDownlink* list in the
*FeatureSets* IE. The first element in that list is referred to by
*FeatureSetDownlinkId* = 1. The *FeatureSetDownlinkId=0* is not used by
an actual *FeatureSetDownlink* but means that the UE does not support a
carrier in this band of a band combination.

*FeatureSetDownlinkId* information element

\-- ASN1START

\-- TAG-FEATURESETDOWNLINKID-START

FeatureSetDownlinkId ::= INTEGER (0..maxDownlinkFeatureSets)

\-- TAG-FEATURESETDOWNLINKID-STOP

\-- ASN1STOP

#### -- *FeatureSetDownlinkPerCC*

The IE *FeatureSetDownlinkPerCC* indicates a set of features that the UE
supports on the corresponding carrier of one band entry of a band
combination.

*FeatureSetDownlinkPerCC* information element

\-- ASN1START

\-- TAG-FEATURESETDOWNLINKPERCC-START

FeatureSetDownlinkPerCC ::= SEQUENCE {

supportedSubcarrierSpacingDL SubcarrierSpacing,

supportedBandwidthDL SupportedBandwidth,

channelBW-90mhz ENUMERATED {supported} OPTIONAL,

maxNumberMIMO-LayersPDSCH MIMO-LayersDL OPTIONAL,

supportedModulationOrderDL ModulationOrder OPTIONAL

}

FeatureSetDownlinkPerCC-v1620 ::= SEQUENCE {

\-- R1 16-2a: Mulit-DCI based multi-TRP

multiDCI-MultiTRP-r16 MultiDCI-MultiTRP-r16 OPTIONAL,

\-- R1 16-2b-3: Support of single-DCI based FDMSchemeB

supportFDM-SchemeB-r16 ENUMERATED {supported} OPTIONAL

}

FeatureSetDownlinkPerCC-v1700 ::= SEQUENCE {

supportedMinBandwidthDL-r17 SupportedBandwidth-v1700 OPTIONAL,

broadcastSCell-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-2g: MIMO layers for multicast PDSCH

maxNumberMIMO-LayersMulticastPDSCH-r17 ENUMERATED {n2, n4, n8} OPTIONAL,

\-- R1 33-2h: Dynamic scheduling for multicast for SCell

dynamicMulticastSCell-r17 ENUMERATED {supported} OPTIONAL,

supportedBandwidthDL-v1710 SupportedBandwidth-v1700 OPTIONAL,

\-- R4 24-1/24-2/24-3/24-4/24-5

supportedCRS-InterfMitigation-r17 CRS-InterfMitigation-r17 OPTIONAL

}

FeatureSetDownlinkPerCC-v1720 ::= SEQUENCE {

\-- R1 33-2j: Supported maximum modulation order used for maximum data
rate calculation for multicast PDSCH

maxModulationOrderForMulticastDataRateCalculation-r17 ENUMERATED {qam64,
qam256, qam1024} OPTIONAL,

\-- R1 33-1-2: FDM-ed unicast PDSCH and group-common PDSCH for broadcast

fdm-BroadcastUnicast-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-3-2: FDM-ed unicast PDSCH and one group-common PDSCH for
multicast

fdm-MulticastUnicast-r17 ENUMERATED {supported} OPTIONAL

}

FeatureSetDownlinkPerCC-v1730 ::= SEQUENCE {

\-- R1 33-3-3: Intra-slot TDM-ed unicast PDSCH and group-common PDSCH

intraSlotTDM-UnicastGroupCommonPDSCH-r17 ENUMERATED {yes, no} OPTIONAL,

\-- R1 33-5-3: One SPS group-common PDSCH configuration for multicast
for SCell

sps-MulticastSCell-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-5-4: Up to 8 SPS group-common PDSCH configurations per CFR for
multicast for SCell

sps-MulticastSCellMultiConfig-r17 INTEGER (1..8) OPTIONAL,

\-- R1 33-1-1: Dynamic slot-level repetition for broadcast MTCH

dci-BroadcastWith16Repetitions-r17 ENUMERATED {supported} OPTIONAL

}

FeatureSetDownlinkPerCC-v1780 ::= SEQUENCE {

supportedBandwidthDL-v1780 SupportedBandwidth-v1700 OPTIONAL

}

FeatureSetDownlinkPerCC-v1800 ::= SEQUENCE {

\-- R1 40-2-1: Basic feature for multi-DCI based intra-cell Multi-TRP
operation with two TA enhancement

multiDCI-IntraCellMultiTRP-TwoTA-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-2-2: Basic feature for multi-DCI based inter-cell Multi-TRP
operation with two TA enhancement

multiDCI-InterCellMultiTRP-TwoTA-r18 INTEGER (1..2) OPTIONAL,

\-- R1 40-2-6: Rx timing difference larger than CP length

rxTimingDiff-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 55-7: Two QCL TypeD for CORESET monitoring in multi-DCI based
multi-TRP

multiDCI-MultiTRP-CORESET-Monitoring-r18 ENUMERATED {supported}
OPTIONAL,

broadcastNonServingCell-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 30-1: Supports scheduling restriction relaxation and measurement
restriction relaxation

schedulingMeasurementRelaxation-r18 ENUMERATED {supported} OPTIONAL

}

FeatureSetDownlinkPerCC-v1840 ::= SEQUENCE {

supportedBandwidthDL-v1840 SupportedBandwidth-v1840 OPTIONAL,

supportedMinBandwidthDL-v1840 SupportedBandwidth-v1840 OPTIONAL

}

MultiDCI-MultiTRP-r16 ::= SEQUENCE {

maxNumberCORESET-r16 ENUMERATED {n2, n3, n4, n5},

maxNumberCORESETPerPoolIndex-r16 INTEGER (1..3),

maxNumberUnicastPDSCH-PerPool-r16 ENUMERATED {n1, n2, n3, n4, n7}

}

CRS-InterfMitigation-r17 ::= SEQUENCE {

\-- R4 24-1 CRS-IM (Interference Mitigation) in DSS scenario

crs-IM-DSS-15kHzSCS-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 24-2 CRS-IM in non-DSS and 15 kHz NR SCS scenario, without the
assistance of network signaling on LTE channel bandwidth

crs-IM-nonDSS-15kHzSCS-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 24-3 CRS-IM in non-DSS and 15 kHz NR SCS scenario, with the
assistance of network signaling on LTE channel bandwidth

crs-IM-nonDSS-NWA-15kHzSCS-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 24-4 CRS-IM in non-DSS and 30 kHz NR SCS scenario, without the
assistance of network signaling on LTE channel bandwidth

crs-IM-nonDSS-30kHzSCS-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 24-5 CRS-IM in non-DSS and 30 kHz NR SCS scenario, with the
assistance of network signaling on LTE channel bandwidth

crs-IM-nonDSS-NWA-30kHzSCS-r17 ENUMERATED {supported} OPTIONAL

}

\-- TAG-FEATURESETDOWNLINKPERCC-STOP

\-- ASN1STOP

#### -- *FeatureSetDownlinkPerCC-Id*

The IE *FeatureSetDownlinkPerCC-Id* identifies a set of features
applicable to one carrier of a feature set. The
*FeatureSetDownlinkPerCC-Id* of a *FeatureSetDownlinkPerCC* is the index
position of the *FeatureSetDownlinkPerCC* in the
*featureSetsDownlinkPerCC*. The first element in the list is referred to
by *FeatureSetDownlinkPerCC-Id* = 1, and so on.

*FeatureSetDownlinkPerCC-Id* information element

\-- ASN1START

\-- TAG-FEATURESETDOWNLINKPERCC-ID-START

FeatureSetDownlinkPerCC-Id ::= INTEGER (1..maxPerCC-FeatureSets)

\-- TAG-FEATURESETDOWNLINKPERCC-ID-STOP

\-- ASN1STOP

#### -- *FeatureSetEUTRA-DownlinkId*

The IE *FeatureSetEUTRA-DownlinkId* identifies a downlink feature set in
E-UTRA list (see TS 36.331 \[10\]. The first element in that list is
referred to by *FeatureSetEUTRA-DownlinkId* = 1. The
*FeatureSetEUTRA-DownlinkId=0* is used when the UE does not support a
carrier in this band of a band combination.

*FeatureSetEUTRA-DownlinkId* information element

\-- ASN1START

\-- TAG-FEATURESETEUTRADOWNLINKID-START

FeatureSetEUTRA-DownlinkId ::= INTEGER (0..maxEUTRA-DL-FeatureSets)

\-- TAG-FEATURESETEUTRADOWNLINKID-STOP

\-- ASN1STOP

#### -- *FeatureSetEUTRA-UplinkId*

The IE *FeatureSetEUTRA-UplinkId* identifies an uplink feature set in
E-UTRA list (see TS 36.331 \[10\]. The first element in that list is
referred to by *FeatureSetEUTRA-UplinkId* = 1. The
*FeatureSetEUTRA-UplinkId* *=0* is used when the UE does not support a
carrier in this band of a band combination.

*FeatureSetEUTRA-UplinkId* information element

\-- ASN1START

\-- TAG-FEATURESETEUTRAUPLINKID-START

FeatureSetEUTRA-UplinkId ::= INTEGER (0..maxEUTRA-UL-FeatureSets)

\-- TAG-FEATURESETEUTRAUPLINKID-STOP

\-- ASN1STOP

#### -- *FeatureSets*

The IE *FeatureSets* is used to provide pools of downlink and uplink
features sets. A *FeatureSetCombination* refers to the IDs of the
feature set(s) that the UE supports in that *FeatureSetCombination*. The
*BandCombination* entries in the *BandCombinationList* then indicate the
ID of the *FeatureSetCombination* that the UE supports for that band
combination.

The entries in the lists in this IE are identified by their index
position. For example, the *FeatureSetUplinkPerCC-Id* = 4 identifies the
4^th^ element in the *featureSetsUplinkPerCC* list.

NOTE: When feature sets (per CC) IEs require extension in future
versions of the specification, new versions of the *FeatureSetDownlink*,
*FeatureSetUplink*, *FeatureSets*, *FeatureSetDownlinkPerCC* and/or
*FeatureSetUplinkPerCC* will be created and instantiated in
corresponding new lists in the *FeatureSets* IE. For example, if new
capability bits are to be added to the *FeatureSetDownlink*, they will
instead be defined in a new *FeatureSetDownlink-rxy* which will be
instantiated in a new *featureSetDownlinkList-rxy* list. If a UE
indicates in a *FeatureSetCombination* that it supports the
*FeatureSetDownlink* with ID #5, it implies that it supports both the
features in *FeatureSetDownlink* #5 and *FeatureSetDownlink-rxy* #5 (if
present). The number of entries in the new list(s) shall be the same as
in the original list(s).

*FeatureSets* information element

\-- ASN1START

\-- TAG-FEATURESETS-START

FeatureSets ::= SEQUENCE {

featureSetsDownlink SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink OPTIONAL,

featureSetsDownlinkPerCC SEQUENCE (SIZE (1..maxPerCC-FeatureSets)) OF
FeatureSetDownlinkPerCC OPTIONAL,

featureSetsUplink SEQUENCE (SIZE (1..maxUplinkFeatureSets)) OF
FeatureSetUplink OPTIONAL,

featureSetsUplinkPerCC SEQUENCE (SIZE (1..maxPerCC-FeatureSets)) OF
FeatureSetUplinkPerCC OPTIONAL,

\...,

\[\[

featureSetsDownlink-v1540 SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink-v1540 OPTIONAL,

featureSetsUplink-v1540 SEQUENCE (SIZE (1..maxUplinkFeatureSets)) OF
FeatureSetUplink-v1540 OPTIONAL,

featureSetsUplinkPerCC-v1540 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetUplinkPerCC-v1540 OPTIONAL

\]\],

\[\[

featureSetsDownlink-v15a0 SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink-v15a0 OPTIONAL

\]\],

\[\[

featureSetsDownlink-v1610 SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink-v1610 OPTIONAL,

featureSetsUplink-v1610 SEQUENCE (SIZE (1..maxUplinkFeatureSets)) OF
FeatureSetUplink-v1610 OPTIONAL,

featureSetDownlinkPerCC-v1620 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetDownlinkPerCC-v1620 OPTIONAL

\]\],

\[\[

featureSetsUplink-v1630 SEQUENCE (SIZE (1..maxUplinkFeatureSets)) OF
FeatureSetUplink-v1630 OPTIONAL

\]\],

\[\[

featureSetsUplink-v1640 SEQUENCE (SIZE (1..maxUplinkFeatureSets)) OF
FeatureSetUplink-v1640 OPTIONAL

\]\],

\[\[

featureSetsDownlink-v1700 SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink-v1700 OPTIONAL,

featureSetsDownlinkPerCC-v1700 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetDownlinkPerCC-v1700 OPTIONAL,

featureSetsUplink-v1710 SEQUENCE (SIZE (1..maxUplinkFeatureSets)) OF
FeatureSetUplink-v1710 OPTIONAL,

featureSetsUplinkPerCC-v1700 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetUplinkPerCC-v1700 OPTIONAL

\]\],

\[\[

featureSetsDownlink-v1720 SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink-v1720 OPTIONAL,

featureSetsDownlinkPerCC-v1720 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetDownlinkPerCC-v1720 OPTIONAL,

featureSetsUplink-v1720 SEQUENCE (SIZE (1..maxUplinkFeatureSets)) OF
FeatureSetUplink-v1720 OPTIONAL

\]\],

\[\[

featureSetsDownlink-v1730 SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink-v1730 OPTIONAL,

featureSetsDownlinkPerCC-v1730 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetDownlinkPerCC-v1730 OPTIONAL

\]\],

\[\[

featureSetsDownlinkPerCC-v1780 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetDownlinkPerCC-v1780 OPTIONAL,

featureSetsUplinkPerCC-v1780 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetUplinkPerCC-v1780 OPTIONAL

\]\],

\[\[

featureSetsDownlink-v1800 SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink-v1800 OPTIONAL,

featureSetsDownlinkPerCC-v1800 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetDownlinkPerCC-v1800 OPTIONAL,

featureSetsUplink-v1800 SEQUENCE (SIZE (1..maxUplinkFeatureSets)) OF
FeatureSetUplink-v1800 OPTIONAL,

featureSetsUplinkPerCC-v1800 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetUplinkPerCC-v1800 OPTIONAL

\]\],

\[\[

featureSetsDownlink-v1830 SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink-v1830 OPTIONAL

\]\],

\[\[

featureSetsDownlinkPerCC-v1840 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetDownlinkPerCC-v1840 OPTIONAL,

featureSetsUplinkPerCC-v1840 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetUplinkPerCC-v1840 OPTIONAL

\]\],

\[\[

featureSetsUplink-v1850 SEQUENCE (SIZE (1..maxUplinkFeatureSets)) OF
FeatureSetUplink-v1850 OPTIONAL,

featureSetsUplinkPerCC-v1850 SEQUENCE (SIZE (1..maxPerCC-FeatureSets))
OF FeatureSetUplinkPerCC-v1850 OPTIONAL

\]\],

\[\[

featureSetsDownlink-v1860 SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink-v1860 OPTIONAL

\]\]

}

FeatureSets-v15t0 ::= SEQUENCE {

featureSetsDownlink-v15t0 SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink-v15t0 OPTIONAL

}

FeatureSets-v16d0 ::= SEQUENCE {

featureSetsUplink-v16d0 SEQUENCE (SIZE (1..maxUplinkFeatureSets)) OF
FeatureSetUplink-v16d0 OPTIONAL

}

FeatureSets-v16k0 ::= SEQUENCE {

featureSetsDownlink-v16k0 SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink-v16k0 OPTIONAL

}

FeatureSets-v17d0 ::= SEQUENCE {

featureSetsDownlink-v17d0 SEQUENCE (SIZE (1..maxDownlinkFeatureSets)) OF
FeatureSetDownlink-v17d0 OPTIONAL

}

\-- TAG-FEATURESETS-STOP

\-- ASN1STOP

#### -- *FeatureSetUplink*

The IE *FeatureSetUplink* is used to indicate the features that the UE
supports on the carriers corresponding to one band entry in a band
combination.

*FeatureSetUplink* information element

\-- ASN1START

\-- TAG-FEATURESETUPLINK-START

FeatureSetUplink ::= SEQUENCE {

featureSetListPerUplinkCC SEQUENCE (SIZE (1.. maxNrofServingCells)) OF
FeatureSetUplinkPerCC-Id,

scalingFactor ENUMERATED {f0p4, f0p75, f0p8} OPTIONAL,

dummy3 ENUMERATED {supported} OPTIONAL,

intraBandFreqSeparationUL FreqSeparationClass OPTIONAL,

searchSpaceSharingCA-UL ENUMERATED {supported} OPTIONAL,

dummy1 DummyI OPTIONAL,

supportedSRS-Resources SRS-Resources OPTIONAL,

twoPUCCH-Group ENUMERATED {supported} OPTIONAL,

dynamicSwitchSUL ENUMERATED {supported} OPTIONAL,

simultaneousTxSUL-NonSUL ENUMERATED {supported} OPTIONAL,

pusch-ProcessingType1-DifferentTB-PerSlot SEQUENCE {

scs-15kHz ENUMERATED {upto2, upto4, upto7} OPTIONAL,

scs-30kHz ENUMERATED {upto2, upto4, upto7} OPTIONAL,

scs-60kHz ENUMERATED {upto2, upto4, upto7} OPTIONAL,

scs-120kHz ENUMERATED {upto2, upto4, upto7} OPTIONAL

} OPTIONAL,

dummy2 DummyF OPTIONAL

}

FeatureSetUplink-v1540 ::= SEQUENCE {

zeroSlotOffsetAperiodicSRS ENUMERATED {supported} OPTIONAL,

pa-PhaseDiscontinuityImpacts ENUMERATED {supported} OPTIONAL,

pusch-SeparationWithGap ENUMERATED {supported} OPTIONAL,

pusch-ProcessingType2 SEQUENCE {

scs-15kHz ProcessingParameters OPTIONAL,

scs-30kHz ProcessingParameters OPTIONAL,

scs-60kHz ProcessingParameters OPTIONAL

} OPTIONAL,

ul-MCS-TableAlt-DynamicIndication ENUMERATED {supported} OPTIONAL

}

FeatureSetUplink-v1610 ::= SEQUENCE {

\-- R1 11-5: PUsCH repetition Type B

pusch-RepetitionTypeB-r16 SEQUENCE {

maxNumberPUSCH-Tx-r16 ENUMERATED {n2, n3, n4, n7, n8, n12},

hoppingScheme-r16 ENUMERATED {interSlotHopping, interRepetitionHopping,
both}

} OPTIONAL,

\-- R1 11-7: UL cancelation scheme for self-carrier

ul-CancellationSelfCarrier-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-7a: UL cancelation scheme for cross-carrier

ul-CancellationCrossCarrier-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-5c: The maximum number of SRS resources in one SRS resource
set with usage set to \'codebook\' for Mode 2

ul-FullPwrMode2-MaxSRS-ResInSet-r16 ENUMERATED {n1, n2, n4} OPTIONAL,

\-- R1 22-4a/4b/4c/4d: CBG based transmission for UL with unicast
PUSCH(s) per slot per CC with UE processing time Capability 1

cbgPUSCH-ProcessingType1-DifferentTB-PerSlot-r16 SEQUENCE {

scs-15kHz-r16 ENUMERATED {one-pusch, upto2, upto4, upto7} OPTIONAL,

scs-30kHz-r16 ENUMERATED {one-pusch, upto2, upto4, upto7} OPTIONAL,

scs-60kHz-r16 ENUMERATED {one-pusch, upto2, upto4, upto7} OPTIONAL,

scs-120kHz-r16 ENUMERATED {one-pusch, upto2, upto4, upto7} OPTIONAL

} OPTIONAL,

\-- R1 22-3a/3b/3c/3d: CBG based transmission for UL with unicast
PUSCH(s) per slot per CC with UE processing time Capability 2

cbgPUSCH-ProcessingType2-DifferentTB-PerSlot-r16 SEQUENCE {

scs-15kHz-r16 ENUMERATED {one-pusch, upto2, upto4, upto7} OPTIONAL,

scs-30kHz-r16 ENUMERATED {one-pusch, upto2, upto4, upto7} OPTIONAL,

scs-60kHz-r16 ENUMERATED {one-pusch, upto2, upto4, upto7} OPTIONAL,

scs-120kHz-r16 ENUMERATED {one-pusch, upto2, upto4, upto7} OPTIONAL

} OPTIONAL,

supportedSRS-PosResources-r16 SRS-AllPosResources-r16 OPTIONAL,

intraFreqDAPS-UL-r16 SEQUENCE {

dummy ENUMERATED {supported} OPTIONAL,

intraFreqTwoTAGs-DAPS-r16 ENUMERATED {supported} OPTIONAL,

dummy1 ENUMERATED {supported} OPTIONAL,

dummy2 ENUMERATED {supported} OPTIONAL,

dummy3 ENUMERATED {short, long} OPTIONAL

} OPTIONAL,

intraBandFreqSeparationUL-v1620 FreqSeparationClassUL-v1620 OPTIONAL,

\-- R1 11-3: More than one PUCCH for HARQ-ACK transmission within a slot

multiPUCCH-r16 SEQUENCE {

sub-SlotConfig-NCP-r16 ENUMERATED {set1, set2} OPTIONAL,

sub-SlotConfig-ECP-r16 ENUMERATED {set1, set2} OPTIONAL

} OPTIONAL,

\-- R1 11-3c: 2 PUCCH of format 0 or 2 for a single 7\*2-symbol subslot
based HARQ-ACK codebook

twoPUCCH-Type1-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-3d: 2 PUCCH of format 0 or 2 for a single 2\*7-symbol subslot
based HARQ-ACK codebook

twoPUCCH-Type2-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-3e: 1 PUCCH format 0 or 2 and 1 PUCCH format 1, 3 or 4 in the
same subslot for a single 2\*7-symbol HARQ-ACK codebooks

twoPUCCH-Type3-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-3f: 2 PUCCH transmissions in the same subslot for a single
2\*7-symbol HARQ-ACK codebooks which are not covered by 11-3d and

\-- 11-3e

twoPUCCH-Type4-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-3g: SR/HARQ-ACK multiplexing once per subslot using a PUCCH
(or HARQ-ACK piggybacked on a PUSCH) when SR/HARQ-ACK

\-- are supposed to be sent with different starting symbols in a subslot

mux-SR-HARQ-ACK-r16 ENUMERATED {supported} OPTIONAL,

dummy1 ENUMERATED {supported} OPTIONAL,

dummy2 ENUMERATED {supported} OPTIONAL,

\-- R1 11-4c: 2 PUCCH of format 0 or 2 for two HARQ-ACK codebooks with
one 7\*2-symbol sub-slot based HARQ-ACK codebook

twoPUCCH-Type5-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-4d: 2 PUCCH of format 0 or 2 in consecutive symbols for two
HARQ-ACK codebooks with one 2\*7-symbol sub-slot based HARQ-ACK

\-- codebook

twoPUCCH-Type6-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-4e: 2 PUCCH of format 0 or 2 for two subslot based HARQ-ACK
codebooks

twoPUCCH-Type7-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-4f: 1 PUCCH format 0 or 2 and 1 PUCCH format 1, 3 or 4 in the
same subslot for HARQ-ACK codebooks with one 2\*7-symbol

\-- subslot based HARQ-ACK codebook

twoPUCCH-Type8-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-4g: 1 PUCCH format 0 or 2 and 1 PUCCH format 1, 3 or 4 in the
same subslot for two subslot based HARQ-ACK codebooks

twoPUCCH-Type9-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-4h: 2 PUCCH transmissions in the same subslot for two HARQ-ACK
codebooks with one 2\*7-symbol subslot which are not covered

\-- by 11-4c and 11-4e

twoPUCCH-Type10-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-4i: 2 PUCCH transmissions in the same subslot for two subslot
based HARQ-ACK codebooks which are not covered by 11-4d and

\-- 11-4f

twoPUCCH-Type11-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 12-1: UL intra-UE multiplexing/prioritization of overlapping
channel/signals with two priority levels in physical layer

ul-IntraUE-Mux-r16 SEQUENCE {

pusch-PreparationLowPriority-r16 ENUMERATED {sym0, sym1, sym2},

pusch-PreparationHighPriority-r16 ENUMERATED {sym0, sym1, sym2}

} OPTIONAL,

\-- R1 16-5a: Supported UL full power transmission mode of fullpower

ul-FullPwrMode-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 18-5d: Processing up to X unicast DCI scheduling for UL per
scheduled CC

crossCarrierSchedulingProcessing-DiffSCS-r16 SEQUENCE {

scs-15kHz-120kHz-r16 ENUMERATED {n1,n2,n4} OPTIONAL,

scs-15kHz-60kHz-r16 ENUMERATED {n1,n2,n4} OPTIONAL,

scs-30kHz-120kHz-r16 ENUMERATED {n1,n2,n4} OPTIONAL,

scs-15kHz-30kHz-r16 ENUMERATED {n2} OPTIONAL,

scs-30kHz-60kHz-r16 ENUMERATED {n2} OPTIONAL,

scs-60kHz-120kHz-r16 ENUMERATED {n2} OPTIONAL

} OPTIONAL,

\-- R1 16-5b: Supported UL full power transmission mode of
fullpowerMode1

ul-FullPwrMode1-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-5c-2: Ports configuration for Mode 2

ul-FullPwrMode2-SRSConfig-diffNumSRSPorts-r16 ENUMERATED {p1-2, p1-4,
p1-2-4} OPTIONAL,

\-- R1 16-5c-3: TPMI group for Mode 2

ul-FullPwrMode2-TPMIGroup-r16 SEQUENCE {

twoPorts-r16 BIT STRING(SIZE(2)) OPTIONAL,

fourPortsNonCoherent-r16 ENUMERATED{g0, g1, g2, g3} OPTIONAL,

fourPortsPartialCoherent-r16 ENUMERATED{g0, g1, g2, g3, g4, g5, g6}
OPTIONAL

} OPTIONAL

}

FeatureSetUplink-v1630 ::= SEQUENCE {

\-- R1 22-8: For SRS for CB PUSCH and antenna switching on FR1 with
symbol level offset for aperiodic SRS transmission

offsetSRS-CB-PUSCH-Ant-Switch-fr1-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 22-8a: PDCCH monitoring on any span of up to 3 consecutive OFDM
symbols of a slot and constrained timeline for SRS for CB

\-- PUSCH and antenna switching on FR1

offsetSRS-CB-PUSCH-PDCCH-MonitorSingleOcc-fr1-r16 ENUMERATED {supported}
OPTIONAL,

\-- R1 22-8b: For type 1 CSS with dedicated RRC configuration, type 3
CSS, and UE-SS, monitoring occasion can be any OFDM symbol(s)

\-- of a slot for Case 2 and constrained timeline for SRS for CB PUSCH
and antenna switching on FR1

offsetSRS-CB-PUSCH-PDCCH-MonitorAnyOccWithoutGap-fr1-r16 ENUMERATED
{supported} OPTIONAL,

\-- R1 22-8c: For type 1 CSS with dedicated RRC configuration, type 3
CSS, and UE-SS, monitoring occasion can be any OFDM symbol(s)

\-- of a slot for Case 2 with a DCI gap and constrained timeline for SRS
for CB PUSCH and antenna switching on FR1

offsetSRS-CB-PUSCH-PDCCH-MonitorAnyOccWithGap-fr1-r16 ENUMERATED
{supported} OPTIONAL,

dummy ENUMERATED {supported} OPTIONAL,

\-- R1 22-9: Cancellation of PUCCH, PUSCH or PRACH with a DCI scheduling
a PDSCH or CSI-RS or a DCI format 2_0 for SFI

partialCancellationPUCCH-PUSCH-PRACH-TX-r16 ENUMERATED {supported}
OPTIONAL

}

FeatureSetUplink-v1640 ::= SEQUENCE {

\-- R1 11-4: Two HARQ-ACK codebooks with up to one sub-slot based
HARQ-ACK codebook (i.e. slot-based + slot-based, or slot-based +

\-- sub-slot based) simultaneously constructed for supporting HARQ-ACK
codebooks with different priorities at a UE

twoHARQ-ACK-Codebook-type1-r16 SubSlot-Config-r16 OPTIONAL,

\-- R1 11-4a: Two sub-slot based HARQ-ACK codebooks simultaneously
constructed for supporting HARQ-ACK codebooks with different

\-- priorities at a UE

twoHARQ-ACK-Codebook-type2-r16 SubSlot-Config-r16 OPTIONAL,

\-- R1 22-8d: All PDCCH monitoring occasion can be any OFDM symbol(s) of
a slot for Case 2 with a span gap and constrained timeline

\-- for SRS for CB PUSCH and antenna switching on FR1

offsetSRS-CB-PUSCH-PDCCH-MonitorAnyOccWithSpanGap-fr1-r16 SEQUENCE {

scs-15kHz-r16 ENUMERATED {set1, set2, set3} OPTIONAL,

scs-30kHz-r16 ENUMERATED {set1, set2, set3} OPTIONAL,

scs-60kHz-r16 ENUMERATED {set1, set2, set3} OPTIONAL

} OPTIONAL

}

FeatureSetUplink-v16d0 ::= SEQUENCE {

pusch-RepetitionTypeB-v16d0 SEQUENCE {

maxNumberPUSCH-Tx-Cap1-r16 ENUMERATED {n2, n3, n4, n7, n8, n12},

maxNumberPUSCH-Tx-Cap2-r16 ENUMERATED {n2, n3, n4, n7, n8, n12}

} OPTIONAL

}

FeatureSetUplink-v1710 ::= SEQUENCE {

\-- R1 23-3-1 Multi-TRP PUSCH repetition (type A) -codebook based

mTRP-PUSCH-TypeA-CB-r17 ENUMERATED {n1,n2,n4} OPTIONAL,

\-- R1 23-3-1-2 Multi-TRP PUSCH repetition (type A) - non-codebook based

mTRP-PUSCH-RepetitionTypeA-r17 ENUMERATED {n1,n2,n3,n4} OPTIONAL,

\-- R1 23-3-3 Multi-TRP PUCCH repetition-intra-slot

mTRP-PUCCH-IntraSlot-r17 ENUMERATED {pf0-2, pf1-3-4, pf0-4} OPTIONAL,

\-- R1 23-8-4 Maximum 2 SP and 1 periodic SRS sets for antenna switching

srs-AntennaSwitching2SP-1Periodic-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-8-9 Extension of aperiodic SRS configuration for 1T4R, 1T2R
and 2T4R

srs-ExtensionAperiodicSRS-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-8-10 1 aperiodic SRS resource set for 1T4R

srs-OneAP-SRS-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 16-8 UE power class per band per band combination

ue-PowerClassPerBandPerBC-r17 ENUMERATED {pc1dot5, pc2, pc3} OPTIONAL,

\-- R4 17-8 UL transmission in FR2 bands within an UL gap when the UL
gap is activated

tx-Support-UL-GapFR2-r17 ENUMERATED {supported} OPTIONAL

}

FeatureSetUplink-v1720 ::= SEQUENCE {

\-- R1 25-3: Repetitions for PUCCH format 0, 1, 2, 3 and 4 over multiple
PUCCH subslots with configured K = 2, 4, 8

pucch-Repetition-F0-1-2-3-4-RRC-Config-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 25-3a: Repetitions for PUCCH format 0, 1, 2, 3 and 4 over
multiple PUCCH subslots using dynamic repetition indication

pucch-Repetition-F0-1-2-3-4-DynamicIndication-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 25-3b: Inter-subslot frequency hopping for PUCCH repetitions

interSubslotFreqHopping-PUCCH-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 25-8: Semi-static HARQ-ACK codebook for sub-slot PUCCH

semiStaticHARQ-ACK-CodebookSub-SlotPUCCH-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 25-14: PHY prioritization of overlapping low-priority DG-PUSCH
and high-priority CG-PUSCH

phy-PrioritizationLowPriorityDG-HighPriorityCG-r17 INTEGER(1..16)
OPTIONAL,

\-- R1 25-15: PHY prioritization of overlapping high-priority DG-PUSCH
and low-priority CG-PUSCH

phy-PrioritizationHighPriorityDG-LowPriorityCG-r17 SEQUENCE {

pusch-PreparationLowPriority-r17 ENUMERATED{sym0, sym1, sym2},

additionalCancellationTime-r17 SEQUENCE {

scs-15kHz-r17 ENUMERATED{sym0, sym1, sym2} OPTIONAL,

scs-30kHz-r17 ENUMERATED{sym0, sym1, sym2, sym3, sym4} OPTIONAL,

scs-60kHz-r17 ENUMERATED{sym0, sym1, sym2, sym3, sym4, sym5, sym6, sym7,
sym8} OPTIONAL,

scs-120kHz-r17 ENUMERATED{sym0, sym1, sym2, sym3, sym4, sym5, sym6,
sym7, sym8, sym9,

sym10, sym11, sym12, sym13, sym14, sym15, sym16} OPTIONAL

},

maxNumberCarriers-r17 INTEGER(1..16)

} OPTIONAL,

\-- R4 17-5 Support of UL DC location(s) report

extendedDC-LocationReport-r17 ENUMERATED {supported} OPTIONAL

}

FeatureSetUplink-v1800 ::= SEQUENCE {

\-- R1 40-3-3-1a: Supported maximum delay value larger than D_basic

maxDelayValueBeyondD-Basic-r18 ENUMERATED {sl2,sl3,sl4,sl5,sl6,sl10}
OPTIONAL,

\-- R1 40-3-3-2: Number of delay values

tdcp-NumberDelayValue-r18 INTEGER (2..4) OPTIONAL,

\-- R1 40-3-3-4: Phase report

phaseReportMoreThanOne-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-3-6: Maximum number of TRS resource sets in a report
configuration

maxNumberTRS-ResourceSet-r18 INTEGER (2..3) OPTIONAL,

\-- R1 40-3-3-7: Maximum number of TDCP report settings per-BWP

maxNumberTDCP-PerBWP-r18 INTEGER (1..4) OPTIONAL,

\-- R1 40-4-6c: DMRS type for Rel.18 enhanced DMRS ports for PUSCH

pusch-DMRS-TypeEnh-r18 SEQUENCE {

dmrs-Type-r18 ENUMERATED {etype1, both},

pusch-TypeA-DMRS-r18 SEQUENCE {

\-- R1 40-4-6: Basic feature of Rel.18 enhanced DMRS ports for PUSCH for
scheduling mapping of type A for Rel.18 enhanced

\-- DMRS ports

dmrs-TypeA-r18 ENUMERATED {supported},

\-- R1 40-4-6d: 2 symbols front-loaded DMRS (uplink) for Rel.18 enhanced
DMRS ports for PUSCH

pusch-2SymbolFL-DMRS-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-6e: 2-symbol FL DMRS + one additional 2-symbols DMRS for
Rel.18 enhanced DMRS ports for PUSCH

pusch-2SymbolFL-DMRS-Addition2Symbol-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-4-6f: 1 symbol FL DMRS and 3 additional DMRS symbols for
Rel.18 enhanced DMRS ports for PUSCH

pusch-1SymbolFL-DMRS-Addition3Symbol-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-4-6k: 1 symbol FL DMRS and 2 additional DMRS symbols for more
than one port for Rel.18 enhanced DMRS ports for

\-- PUSCH

pusch-1SymbolFL-DMRS-BeyondOnePort-r18 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- R1 40-4-10: DMRS port configuration for PUSCH with 8Tx

dummy ENUMERATED {rel15, both} OPTIONAL,

\-- R1 40-4-6a: Basic feature of Rel.18 enhanced DMRS ports for PUSCH
for scheduling type B for Rel.18 enhanced DMRS ports

pusch-TypeB-DMRS-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-6g: 1 port UL PTRS for Rel.18 enhanced DMRS ports for PUSCH
with rank 1-4

pusch-rank-1-4-1Port-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-6h: 1 port UL PTRS for Rel.18 enhanced DMRS ports for PUSCH
with rank 5-8

pusch-rank-5-8-1Port-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-6i: 2 port UL PTRS for Rel.18 enhanced DMRS ports for PUSCH
with rank 1-4

pusch-rank-1-4-2Port-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-6j: 2 port UL PTRS for Rel.18 enhanced DMRS ports for PUSCH
with rank 5-8

pusch-rank-5-8-2Port-r18 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- R1 40-4-13: Support Rel-18 UL DMRS with single-DCI based M-TRP

ul-DMRS-SingleDCI-M-TRP-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-4-14: Support Rel-18 UL DMRS with M-DCI based M-TRP

ul-DMRS-M-DCI-M-TRP-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-5-5: Maximum 2 SP and 1 periodic SRS sets for 8T8R antenna
switching

srs-AntennaSwitching8T8R2SP-1Periodic-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-6-4: Single-DCI based STx2P SFN scheme for PUCCH

pucch-SingleDCI-STx2P-SFN-r18 ENUMERATED {pf0-2, pf1-3-4, pf0-4}
OPTIONAL,

\-- R1 41-4-6: Positioning SRS bandwidth aggregation in RRC_CONNECTED

posSRS-BWA-RRC-Connected-r18 PosSRS-BWA-RRC-Connected-r18 OPTIONAL,

\-- R1 41-4-7: Positioning SRS bandwidth aggregation independent from UL
communication CA in RRC_CONNECTED

posSRS-BWA-IndependentCA-RRC-Connected-r18
PosSRS-BWA-IndependentCA-RRC-Connected-r18 OPTIONAL,

\-- R1 41-4-9: Indicate which other bands in the band combination are
affected due to the need of a guard period

posSRS-BWA-AffectedBandList-r18 SEQUENCE (SIZE (1..maxBands)) OF
FreqBandIndicatorNR OPTIONAL,

\-- R1 45-5a: RACH-based early TA acquisition with simultaneous
transmission

rach-EarlyTA-BandList-r18 SEQUENCE (SIZE (1..maxBandsMRDC)) OF BOOLEAN
OPTIONAL,

\-- R1 49-6: Two HARQ-ACK codebooks with up to one sub-slot based
HARQ-ACK codebook simultaneously constructed for supporting

\-- HARQ-ACK codebooks with different priorities by DCI format 1_3

simultaneous-2-1-HARQ-ACK-CB-r18 SubSlot-Config-r16 OPTIONAL,

\-- R1 49-6a: Two HARQ-ACK codebooks with two sub-slot based HARQ-ACK
codebook simultaneously constructed for supporting

\-- HARQ-ACK codebooks with different priorities by DCI format 1_3

simultaneous-2-2-HARQ-ACK-CB-r18 SubSlot-Config-r16 OPTIONAL,

\-- R1 49-7: UL intra-UE multiplexing/prioritization of overlapping
channel/signals with two priority levels in physical

\-- layer for DCI format 1_3/0_3

ul-IntraUE-MuxEnh-r18 SEQUENCE {

pusch-PreparationLowPriority-r18 ENUMERATED {sym0, sym1, sym2},

pusch-PreparationHighPriority-r18 ENUMERATED {sym0, sym1, sym2}

} OPTIONAL,

\-- R4 27-1 TxDiversity for 4Tx

txDiversity4Tx-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 41-2: Power boosting for DFT-s-OFDM pi/2 BPSK and QPSK
transmissions without modified spectrum flatness requirement

powerBoosting-pi2BPSK-QPSK-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 41-3: Power boosting for DFT-s-OFDM pi/2 BPSK and QPSK
transmissions with modified spectrum flatness requirement shaping

powerBoosting-pi2BPSK-QPSK-Modified-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 44-1 TxDiversity for 2Tx

txDiversity2Tx-r18 ENUMERATED {supported} OPTIONAL,

ue-PowerClassPerBandPerBC-v1820 ENUMERATED {pc5} OPTIONAL

}

FeatureSetUplink-v1850 ::= SEQUENCE {

\-- R1 40-4-10: DMRS port configuration for PUSCH with 8Tx

pusch-DMRS8Tx-r18 ENUMERATED {rel15, both} OPTIONAL,

\-- R1 40-7-1h: UE 8Tx PUSCH processing capability for codebook

additionalTime-CB-8TxPUSCH-r18 SEQUENCE {

scs-15kHz-r18 ENUMERATED {sym1, sym2, sym4} OPTIONAL,

scs-30kHz-r18 ENUMERATED {sym1, sym2, sym4, sym8} OPTIONAL,

scs-60kHz-r18 ENUMERATED {sym2, sym4, sym8, sym16} OPTIONAL,

scs-120kHz-r18 ENUMERATED {sym4, sym8, sym16, sym32} OPTIONAL,

scs-480kHz-r18 ENUMERATED {sym16, sym32, sym64, sym128} OPTIONAL,

scs-960kHz-r18 ENUMERATED {sym32, sym64, sym128, sym256} OPTIONAL

} OPTIONAL,

\-- R1 40-7-2b: UE 8Tx PUSCH processing capability for non-codebook

additionalTime-NonCB-8TxPUSCH-r18 SEQUENCE {

scs-15kHz-r18 ENUMERATED {sym1, sym2, sym4} OPTIONAL,

scs-30kHz-r18 ENUMERATED {sym1, sym2, sym4, sym8} OPTIONAL,

scs-60kHz-r18 ENUMERATED {sym2, sym4, sym8, sym16} OPTIONAL,

scs-120kHz-r18 ENUMERATED {sym4, sym8, sym16, sym32} OPTIONAL,

scs-480kHz-r18 ENUMERATED {sym16, sym32, sym64, sym128} OPTIONAL,

scs-960kHz-r18 ENUMERATED {sym32, sym64, sym128, sym256} OPTIONAL

} OPTIONAL

}

SubSlot-Config-r16 ::= SEQUENCE {

sub-SlotConfig-NCP-r16 ENUMERATED {n4,n5,n6,n7} OPTIONAL,

sub-SlotConfig-ECP-r16 ENUMERATED {n4,n5,n6} OPTIONAL

}

SRS-AllPosResources-r16 ::= SEQUENCE {

srs-PosResources-r16 SRS-PosResources-r16,

srs-PosResourceAP-r16 SRS-PosResourceAP-r16 OPTIONAL,

srs-PosResourceSP-r16 SRS-PosResourceSP-r16 OPTIONAL

}

SRS-PosResources-r16 ::= SEQUENCE {

maxNumberSRS-PosResourceSetPerBWP-r16 ENUMERATED {n1, n2, n4, n8, n12,
n16},

maxNumberSRS-PosResourcesPerBWP-r16 ENUMERATED {n1, n2, n4, n8, n16,
n32, n64},

maxNumberSRS-ResourcesPerBWP-PerSlot-r16 ENUMERATED {n1, n2, n3, n4, n5,
n6, n8, n10, n12, n14},

maxNumberPeriodicSRS-PosResourcesPerBWP-r16 ENUMERATED {n1, n2, n4, n8,
n16, n32, n64},

maxNumberPeriodicSRS-PosResourcesPerBWP-PerSlot-r16 ENUMERATED {n1, n2,
n3, n4, n5, n6, n8, n10, n12, n14}

}

SRS-PosResourceAP-r16 ::= SEQUENCE {

maxNumberAP-SRS-PosResourcesPerBWP-r16 ENUMERATED {n1, n2, n4, n8, n16,
n32, n64},

maxNumberAP-SRS-PosResourcesPerBWP-PerSlot-r16 ENUMERATED {n1, n2, n3,
n4, n5, n6, n8, n10, n12, n14}

}

SRS-PosResourceSP-r16 ::= SEQUENCE {

maxNumberSP-SRS-PosResourcesPerBWP-r16 ENUMERATED {n1, n2, n4, n8, n16,
n32, n64},

maxNumberSP-SRS-PosResourcesPerBWP-PerSlot-r16 ENUMERATED {n1, n2, n3,
n4, n5, n6, n8, n10, n12, n14}

}

SRS-Resources ::= SEQUENCE {

maxNumberAperiodicSRS-PerBWP ENUMERATED {n1, n2, n4, n8, n16},

maxNumberAperiodicSRS-PerBWP-PerSlot INTEGER (1..6),

maxNumberPeriodicSRS-PerBWP ENUMERATED {n1, n2, n4, n8, n16},

maxNumberPeriodicSRS-PerBWP-PerSlot INTEGER (1..6),

maxNumberSemiPersistentSRS-PerBWP ENUMERATED {n1, n2, n4, n8, n16},

maxNumberSemiPersistentSRS-PerBWP-PerSlot INTEGER (1..6),

maxNumberSRS-Ports-PerResource ENUMERATED {n1, n2, n4}

}

DummyF ::= SEQUENCE {

maxNumberPeriodicCSI-ReportPerBWP INTEGER (1..4),

maxNumberAperiodicCSI-ReportPerBWP INTEGER (1..4),

maxNumberSemiPersistentCSI-ReportPerBWP INTEGER (0..4),

simultaneousCSI-ReportsAllCC INTEGER (5..32)

}

PosSRS-BWA-RRC-Connected-r18 ::= SEQUENCE {

numOfCarriersIntraBandContiguous-r18 ENUMERATED {two, three,
twoandthree},

maximumAggregatedBW-TwoCarriersFR1-r18 ENUMERATED {mhz20, mhz40, mhz50,
mhz80, mhz100,

mhz160, mhz180, mhz190, mhz200} OPTIONAL,

maximumAggregatedBW-TwoCarriersFR2-r18 ENUMERATED {mhz50, mhz100,
mhz200, mhz400, mhz600, mhz800} OPTIONAL,

maximumAggregatedBW-ThreeCarriersFR1-r18 ENUMERATED {mhz80, mhz100,
mhz160, mhz200, mhz240, mhz300} OPTIONAL,

maximumAggregatedBW-ThreeCarriersFR2-r18 ENUMERATED {mhz50, mhz100,
mhz200, mhz300, mhz400,

mhz600, mhz800, mhz1000, mhz1200}

OPTIONAL,

maximumAggregatedResourceSet-r18 ENUMERATED {n1, n2, n4, n8, n12, n16},

maximumAggregatedResourcePeriodic-r18 ENUMERATED {n1, n2, n4, n8, n16,
n32, n64},

maximumAggregatedResourceAperiodic-r18 ENUMERATED {n0, n1, n2, n4, n8,
n16, n32, n64},

maximumAggregatedResourceSemi-r18 ENUMERATED {n0, n1, n2, n4, n8, n16,
n32, n64},

maximumAggregatedResourcePeriodicPerSlot-r18 ENUMERATED {n1, n2, n3, n4,
n5, n6, n8, n10, n12, n14},

maximumAggregatedResourceAperiodicPerSlot-r18 ENUMERATED {n0, n1, n2,
n3, n4, n5, n6, n8, n10, n12, n14},

maximumAggregatedResourceSemiPerSlot-r18 ENUMERATED {n0, n1, n2, n3, n4,
n5, n6, n8, n10, n12, n14},

\...

}

PosSRS-BWA-IndependentCA-RRC-Connected-r18 ::= SEQUENCE {

numOfCarriersIntraBandContiguous-r18 ENUMERATED {two, three,
twoandthree},

maximumAggregatedBW-TwoCarriersFR1-r18 ENUMERATED {mhz20, mhz40, mhz50,
mhz80, mhz100,

mhz160, mhz180, mhz190, mhz200} OPTIONAL,

maximumAggregatedBW-TwoCarriersFR2-r18 ENUMERATED {mhz50, mhz100,
mhz200, mhz400, mhz600, mhz800} OPTIONAL,

maximumAggregatedBW-ThreeCarriersFR1-r18 ENUMERATED {mhz80, mhz100,
mhz160, mhz200, mhz240, mhz300} OPTIONAL,

maximumAggregatedBW-ThreeCarriersFR2-r18 ENUMERATED {mhz50, mhz100,
mhz200, mhz300, mhz400,

mhz600, mhz800, mhz1000, mhz1200}

OPTIONAL,

maximumAggregatedResourceSet-r18 ENUMERATED {n1, n2, n4, n8, n12, n16},

maximumAggregatedResourcePeriodic-r18 ENUMERATED {n1, n2, n4, n8, n16,
n32, n64},

maximumAggregatedResourceAperiodic-r18 ENUMERATED {n0, n1, n2, n4, n8,
n16, n32, n64},

maximumAggregatedResourceSemi-r18 ENUMERATED {n0, n1, n2, n4, n8, n16,
n32, n64},

maximumAggregatedResourcePeriodicPerSlot-r18 ENUMERATED {n1, n2, n3, n4,
n5, n6, n8, n10, n12, n14},

maximumAggregatedResourceAperiodicPerSlot-r18 ENUMERATED {n0, n1, n2,
n3, n4, n5, n6, n8, n10, n12, n14},

maximumAggregatedResourceSemiPerSlot-r18 ENUMERATED {n0, n1, n2, n3, n4,
n5, n6, n8, n10, n12, n14},

guardPeriod-r18 ENUMERATED {n0, n30, n100, n140, n200},

powerClassForTwoAggregatedCarriers-r18 ENUMERATED {pc2, pc3} OPTIONAL,

powerClassForThreeAggregatedCarriers-r18 ENUMERATED {pc2, pc3} OPTIONAL,

\...

}

\-- TAG-FEATURESETUPLINK-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *FeatureSetUplink* field descriptions                                 |
+=======================================================================+
| ***featureSetListPerUplinkCC***                                       |
|                                                                       |
| Indicates which features the UE supports on the individual UL         |
| carriers of the feature set (and hence of a band entry that refers to |
| the feature set). The UE shall hence include at least as many         |
| *FeatureSetUplinkPerCC-Id* in this list as the number of carriers it  |
| supports according to the *ca-BandwidthClassUL*, except if indicating |
| additional functionality by reducing the number of                    |
| *FeatureSetUplinkPerCC-Id* in the feature set (see NOTE 1 in          |
| *FeatureSetCombination* IE description). The order of the elements in |
| this list is not relevant, i.e., the network may configure any of the |
| carriers in accordance with any of the *FeatureSetUplinkPerCC-Id* in  |
| this list.                                                            |
+-----------------------------------------------------------------------+

#### -- *FeatureSetUplinkId*

The IE *FeatureSetUplinkId* identifies an uplink feature set. The
*FeatureSetUplinkId* of a *FeatureSetUplink* is the index position of
the *FeatureSetUplink* in the *featureSetsUplink* list in the
*FeatureSets* IE. The first element in the list is referred to by
*FeatureSetUplinkId* = 1, and so on. The *FeatureSetUplinkId =0* is not
used by an actual *FeatureSetUplink* but means that the UE does not
support a carrier in this band of a band combination.

*FeatureSetUplinkId* information element

\-- ASN1START

\-- TAG-FEATURESETUPLINKID-START

FeatureSetUplinkId ::= INTEGER (0..maxUplinkFeatureSets)

\-- TAG-FEATURESETUPLINKID-STOP

\-- ASN1STOP

#### -- *FeatureSetUplinkPerCC*

The IE *FeatureSetUplinkPerCC* indicates a set of features that the UE
supports on the corresponding carrier of one band entry of a band
combination.

*FeatureSetUplinkPerCC* information element

\-- ASN1START

\-- TAG-FEATURESETUPLINKPERCC-START

FeatureSetUplinkPerCC ::= SEQUENCE {

supportedSubcarrierSpacingUL SubcarrierSpacing,

supportedBandwidthUL SupportedBandwidth,

channelBW-90mhz ENUMERATED {supported} OPTIONAL,

mimo-CB-PUSCH SEQUENCE {

maxNumberMIMO-LayersCB-PUSCH MIMO-LayersUL OPTIONAL,

maxNumberSRS-ResourcePerSet INTEGER (1..2)

} OPTIONAL,

maxNumberMIMO-LayersNonCB-PUSCH MIMO-LayersUL OPTIONAL,

supportedModulationOrderUL ModulationOrder OPTIONAL

}

FeatureSetUplinkPerCC-v1540 ::= SEQUENCE {

mimo-NonCB-PUSCH SEQUENCE {

maxNumberSRS-ResourcePerSet INTEGER (1..4),

maxNumberSimultaneousSRS-ResourceTx INTEGER (1..4)

} OPTIONAL

}

FeatureSetUplinkPerCC-v1700 ::= SEQUENCE {

supportedMinBandwidthUL-r17 SupportedBandwidth-v1700 OPTIONAL,

\-- R1 23-3-1-3 FeMIMO: Multi-TRP PUSCH repetition (type B) -
non-codebook based

mTRP-PUSCH-RepetitionTypeB-r17 ENUMERATED {n1,n2,n3,n4} OPTIONAL,

\-- R1 23-3-1-1 -codebook based Multi-TRP PUSCH repetition (type B)

mTRP-PUSCH-TypeB-CB-r17 ENUMERATED {n1,n2,n4} OPTIONAL,

supportedBandwidthUL-v1710 SupportedBandwidth-v1700 OPTIONAL

}

FeatureSetUplinkPerCC-v1780 ::= SEQUENCE {

supportedBandwidthUL-v1780 SupportedBandwidth-v1700 OPTIONAL

}

FeatureSetUplinkPerCC-v1800 ::= SEQUENCE {

\-- R1 40-2-7: Two TAs for multi-DCI STxMP PUSCH+PUSCH

twoPUSCH-MultiDCI-STx2P-TwoTA-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-6-1: Single-DCI based STx2P SDM scheme for PUSCH-codebook

pusch-CB-SingleDCI-STx2P-SDM-r18 SEQUENCE {

maxNumberSRS-ResourcePerSet-r18 ENUMERATED {n1,n2,n4},

maxNumberLayerPerPanel-r18 INTEGER (1..2),

maxNumberNZP-PUSCH-PortsPerSet-r18 ENUMERATED {n1,n2,n4},

maxNumberSRS-AntennaPortsPerSet-r18 ENUMERATED {n1,n2,n4}

} OPTIONAL,

\-- R1 40-6-1a: Single-DCI based STx2P SDM scheme for PUSCH-noncodebook

pusch-NonCB-SingleDCI-STx2P-SDM-r18 SEQUENCE {

maxNumberSRS-ResourcePerSet-r18 INTEGER (1..4),

maxNumberLayerPerPanel-r18 INTEGER (1..2),

maxNumberSimulSRS-OneResourcePerSet-r18 INTEGER (1..4),

maxNumberSimulSRS-TwoResourcePerSet-r18 INTEGER (1..8)

} OPTIONAL,

\-- R1 40-6-2: Single-DCI based STx2P SFN scheme for PUSCH-codebook

pusch-CB-SingleDCI-STx2P-SFN-r18 SEQUENCE {

maxNumberSRS-ResourcePerSet-r18 ENUMERATED {n1,n2,n4},

maxNumberLayerPerSet-r18 INTEGER (1..2),

maxNumberSRS-AntennaPortsPerSet-r18 ENUMERATED {n1,n2,n4},

maxNumberNZP-PUSCH-PortsPerSet-r18 ENUMERATED {n1,n2,n4}

} OPTIONAL,

\-- R1 40-6-2a: Single-DCI based STx2P SFN scheme for PUSCH-noncodebook

pusch-NonCB-SingleDCI-STx2P-SFN-r18 SEQUENCE {

maxNumberSRS-ResourcePerSet-r18 INTEGER (1..4),

maxNumberLayerPerSet-r18 INTEGER (1..2),

maxNumberSimulSRS-OneResourcePerSet-r18 INTEGER (1..4),

maxNumberSimulSRS-TwoResourcePerSet-r18 INTEGER (1..8)

} OPTIONAL,

\-- R1 40-6-3a: codebook multi-DCI based STx2P PUSCH+PUSCH for DG+DG

twoPUSCH-CB-MultiDCI-STx2P-DG-DG-r18 SEQUENCE {

maxNumberSRS-ResourcePerSet-r18 ENUMERATED {n1, n2, n4},

maxNumberLayerOverlapping-r18 INTEGER (1..2),

maxNumberNZP-PUSCH-Overlapping-r18 ENUMERATED {n1, n2, n4},

maxNumberPUSCH-PerCORESET-PerSlot-r18 SEQUENCE {

scs-60kHz-r18 ENUMERATED {n1,n2,n3,n4,n7} OPTIONAL,

scs-120kHz-r18 ENUMERATED {n1,n2,n3,n4,n7} OPTIONAL

} OPTIONAL,

maxNumberTotalLayerOverlapping-r18 INTEGER (2..4),

maxNumberSRS-AntennaPortsPerSet-r18 ENUMERATED {n1,n2,n4}

} OPTIONAL,

\-- R1 40-6-3b: Noncodebook multi-DCI based STx2P PUSCH+PUSCH for DG+DG

twoPUSCH-NonCB-MultiDCI-STx2P-DG-DG-r18 SEQUENCE {

maxNumberSRS-ResourcePerSet-r18 INTEGER (1..4),

maxNumberLayerOverlapping-r18 INTEGER (1..2),

maxNumberSimulSRS-ResourcePerSet-r18 INTEGER (1..4),

maxNumberPUSCH-PerCORESET-PerSlot-r18 SEQUENCE {

scs-60kHz-r18 ENUMERATED {n1,n2,n3,n4,n7} OPTIONAL,

scs-120kHz-r18 ENUMERATED {n1,n2,n3,n4,n7} OPTIONAL

} OPTIONAL,

maxNumberTotalLayerOverlapping-r18 INTEGER (2..4)

} OPTIONAL,

\-- R1 40-6-6: Out-of-order operation for multi-DCI based STx2P
PUSCH+PUSCH

twoPUSCH-MultiDCI-STx2P-OutOfOrder-r18 ENUMERATED {supported} OPTIONAL,

codebookParameter8TxPUSCH-r18 SEQUENCE {

\-- R1 40-7-1: Basic features for Codebook-based 8Tx PUSCH

codebook-8TxBasic-r18 SEQUENCE {

maxNumberPUSCH-MIMO-Layer-r18 INTEGER (1..8),

maxNumberSRS-Resource-r18 INTEGER (1..2),

srs-8TxPorts-r18 ENUMERATED {noTDM, both}

},

\-- R1 40-7-1a: Codebook-based 8Tx PUSCH-codebook1

codebook1-8TxPUSCH-r18 SEQUENCE {

codebookN1N4-r18 ENUMERATED {ng1n4n1,ng1n2n2,both} OPTIONAL,

srs-8TxPorts-r18 ENUMERATED {noTDM, both}

},

\-- R1 40-7-1b: Codebook-based 8Tx PUSCH-codebook2

codebook2-8TxPUSCH-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-7-1c: Codebook-based 8Tx PUSCH-codebook3

codebook3-8TxPUSCH-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-7-1d: Codebook-based 8Tx PUSCH-codebook4

codebook4-8TxPUSCH-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-7-1e: UL full power transmission mode 0

ul-FullPwrTransMode0-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-7-1f: UL full power transmission mode 1

ul-FullPwrTransMode1-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-7-1g: UL full power transmission mode 2 with 1/2/4 resources

ul-FullPwrTransMode2-r18 ENUMERATED {n1,n2,n4} OPTIONAL,

\-- R1 40-7-1g-1: SRS resources for UL full power transmission mode 2

ul-SRS-TransMode2-r18 BIT STRING (SIZE(3)) OPTIONAL,

\-- R1 40-7-1g-2: TPMI group(s) which delivers full power for codebook2

tpmi-FullPwrCodebook2-r18 ENUMERATED {first, second} OPTIONAL

} OPTIONAL,

\-- R1 40-7-2: Basic features for Non-Codebook-based 8Tx PUSCH

nonCodebook-8TxPUSCH-r18 SEQUENCE {

maxNumberPUSCH-MIMO-Layer-r18 INTEGER (1..8),

maxNumberSRS-Resource-r18 INTEGER (1..8),

maxNumberSimultaneousSRS-r18 INTEGER (1..8)

} OPTIONAL,

\-- R1 40-7-2a: Association between CSI-RS and SRS for non-codebook case

nonCodebook-CSI-RS-SRS-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-7-3: CBG based 2 CWs PUSCH with rank \>4

cgb-2CW-PUSCH-r18 ENUMERATED {supported} OPTIONAL

}

FeatureSetUplinkPerCC-v1840 ::= SEQUENCE {

supportedBandwidthUL-v1840 SupportedBandwidth-v1840 OPTIONAL,

supportedMinBandwidthUL-v1840 SupportedBandwidth-v1840 OPTIONAL

}

FeatureSetUplinkPerCC-v1850 ::= SEQUENCE {

\-- R1 40-6-3a-1: UE STxMP processing capability for codebook

twoPUSCH-CB-MultiDCI-STx2P-AdditionalTime-r18 CHOICE {

scs-60kHz-r18 ENUMERATED {sym1, sym4, sym8, sym16},

scs-120kHz-r18 ENUMERATED {sym4, sym8, sym16, sym32},

scs-480kHz-r18 ENUMERATED {sym16, sym32, sym64, sym128},

scs-960kHz-r18 ENUMERATED {sym32, sym64, sym128,sym256}

} OPTIONAL,

\-- R1 40-6-3b-2: UE STxMP processing capability for non-codebook

twoPUSCH-NonCB-MultiDCI-STx2P-AdditionalTime-r18 CHOICE {

scs-60kHz-r18 ENUMERATED {sym1, sym4, sym8, sym16},

scs-120kHz-r18 ENUMERATED {sym4, sym8, sym16, sym32},

scs-480kHz-r18 ENUMERATED {sym16, sym32, sym64, sym128},

scs-960kHz-r18 ENUMERATED {sym32, sym64, sym128,sym256}

} OPTIONAL

}

\-- TAG-FEATURESETUPLINKPERCC-STOP

\-- ASN1STOP

#### -- *FeatureSetUplinkPerCC-Id*

The IE *FeatureSetUplinkPerCC-Id* identifies a set of features
applicable to one carrier of a feature set. The
*FeatureSetUplinkPerCC-Id* of a *FeatureSetUplinkPerCC* is the index
position of the *FeatureSetUplinkPerCC* in the *featureSetsUplinkPerCC*.
The first element in the list is referred to by
*FeatureSetUplinkPerCC-Id* = 1, and so on.

*FeatureSetUplinkPerCC-Id* information element

\-- ASN1START

\-- TAG-FEATURESETUPLINKPERCC-ID-START

FeatureSetUplinkPerCC-Id ::= INTEGER (1..maxPerCC-FeatureSets)

\-- TAG-FEATURESETUPLINKPERCC-ID-STOP

\-- ASN1STOP

#### -- *FreqBandIndicatorEUTRA*

\-- ASN1START

\-- TAG-FREQBANDINDICATOREUTRA-START

FreqBandIndicatorEUTRA ::= INTEGER (1..maxBandsEUTRA)

\-- TAG-FREQBANDINDICATOREUTRA-STOP

\-- ASN1STOP

#### -- *FreqBandList*

The IE *FreqBandList* is used by the network to request NR CA, NR non-CA
and/or MR-DC band combinations for specific NR and/or E-UTRA frequency
bands and/or up to a specific number of carriers and/or up to specific
aggregated bandwidth. This is also used to request feature sets (for NR)
and feature set combinations (for NR and MR-DC). For NR sidelink
communication, this is used by the initiating UE to request sidelink UE
radio access capabilities from the peer UE. This is also used to request
lower MSD capability for specific NR frequency bands for the UE
supporting lower MSD.

*FreqBandList* information element

\-- ASN1START

\-- TAG-FREQBANDLIST-START

FreqBandList ::= SEQUENCE (SIZE (1..maxBandsMRDC)) OF
FreqBandInformation

FreqBandInformation ::= CHOICE {

bandInformationEUTRA FreqBandInformationEUTRA,

bandInformationNR FreqBandInformationNR

}

FreqBandInformationEUTRA ::= SEQUENCE {

bandEUTRA FreqBandIndicatorEUTRA,

ca-BandwidthClassDL-EUTRA CA-BandwidthClassEUTRA OPTIONAL, \-- Need N

ca-BandwidthClassUL-EUTRA CA-BandwidthClassEUTRA OPTIONAL \-- Need N

}

FreqBandInformationNR ::= SEQUENCE {

bandNR FreqBandIndicatorNR,

maxBandwidthRequestedDL AggregatedBandwidth OPTIONAL, \-- Need N

maxBandwidthRequestedUL AggregatedBandwidth OPTIONAL, \-- Need N

maxCarriersRequestedDL INTEGER (1..maxNrofServingCells) OPTIONAL, \--
Need N

maxCarriersRequestedUL INTEGER (1..maxNrofServingCells) OPTIONAL \--
Need N

}

AggregatedBandwidth ::= ENUMERATED {mhz50, mhz100, mhz150, mhz200,
mhz250, mhz300, mhz350,

mhz400, mhz450, mhz500, mhz550, mhz600, mhz650, mhz700, mhz750, mhz800}

\-- TAG-FREQBANDLIST-STOP

\-- ASN1STOP

#### -- *FreqSeparationClass*

The IE *FreqSeparationClas*s is used for an intra-band non-contiguous CA
band combination to indicate frequency separation between lower edge of
lowest CC and upper edge of highest CC in a frequency band.

*FreqSeparationClass* information element

\-- ASN1START

\-- TAG-FREQSEPARATIONCLASS-START

FreqSeparationClass ::= ENUMERATED { mhz800, mhz1200, mhz1400, \...,
mhz400-v1650, mhz600-v1650}

FreqSeparationClassDL-v1620 ::= ENUMERATED {mhz1000, mhz1600, mhz1800,
mhz2000, mhz2200, mhz2400}

FreqSeparationClassUL-v1620 ::= ENUMERATED {mhz1000}

\-- TAG-FREQSEPARATIONCLASS-STOP

\-- ASN1STOP

#### *-- FreqSeparationClassDL-Only*

The IE *FreqSeparationClassDL-Only* is used to indicate the frequency
separation between lower edge of lowest CC and upper edge of highest CC
of DL only frequency spectrum in a frequency band.

*FreqSeparationClassDL-Only* information element

\-- ASN1START

\-- TAG-FREQSEPARATIONCLASSDL-Only-START

FreqSeparationClassDL-Only-r16 ::= ENUMERATED {mhz200, mhz400, mhz600,
mhz800, mhz1000, mhz1200}

\-- TAG-FREQSEPARATIONCLASSDL-Only-STOP

\-- ASN1STOP

#### -- *FR2-2-AccessParamsPerBand*

The IE *FR2-2-AccessParamsPerBand* is used to convey FR2-2 related
parameters specific for a certain frequency band (not per feature set or
band combination).

FR2-2-AccessParamsPerBand information element

\-- ASN1START

\-- TAG-FR2-2-ACCESSPARAMSPERBAND-START

FR2-2-AccessParamsPerBand-r17 ::= SEQUENCE {

\-- R1 24-1: Basic FR2-2 DL support

dl-FR2-2-SCS-120kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-1a: Basic FR2-2 UL support

ul-FR2-2-SCS-120kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-2: 120KHz SSB support for initial access in FR2-2

initialAccessSSB-120kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-1b: Wideband PRACH for 120 kHz in FR2-2

widebandPRACH-SCS-120kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-1c: Multi-RB support PUCCH format 0/1/4 for 120 kHz in FR2-2

multiRB-PUCCH-SCS-120kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-1d: Multiple PDSCH scheduling by single DCI for 120kHz in
FR2-2

multiPDSCH-SingleDCI-FR2-2-SCS-120kHz-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 24-1e: Multiple PUSCH scheduling by single DCI for 120kHz in
FR2-2

multiPUSCH-SingleDCI-FR2-2-SCS-120kHz-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 24-4: 480KHz SCS support for DL

dl-FR2-2-SCS-480kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-4a: 480KHz SCS support for UL

ul-FR2-2-SCS-480kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-3: 480KHz SSB support for initial access in FR2-2

initialAccessSSB-480kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-4b: Wideband PRACH for 480 kHz in FR2-2

widebandPRACH-SCS-480kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-4c: Multi-RB support PUCCH format 0/1/4 for 480 kHz in FR2-2

multiRB-PUCCH-SCS-480kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-4f: Enhanced PDCCH monitoring for 480KHz in FR2-2

enhancedPDCCH-monitoringSCS-480kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-5: 960KHz SCS support for DL

dl-FR2-2-SCS-960kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-5a: 960KHz SCS support for UL

ul-FR2-2-SCS-960kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-5c: Multi-RB support PUCCH format 0/1/4 for 960 kHz in FR2-2

multiRB-PUCCH-SCS-960kHz-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-5f: Enhanced PDCCH monitoring for 960KHz in FR2-2

enhancedPDCCH-monitoringSCS-960kHz-r17 SEQUENCE {

pdcch-monitoring4-1-r17 ENUMERATED {supported} OPTIONAL,

pdcch-monitoring4-2-r17 ENUMERATED {supported} OPTIONAL,

pdcch-monitoring8-4-r17 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- R1 24-6: Type 1 channel access procedure in uplink for FR2-2 with
shared spectrum channel access

type1-ChannelAccess-FR2-2-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-7: Type 2 channel access procedure in uplink for FR2-2 with
shared spectrum channel access

type2-ChannelAccess-FR2-2-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-10: Reduced beam switching time delay

reduced-BeamSwitchTiming-FR2-2-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-8: 32 DL HARQ processes for FR 2-2

support32-DL-HARQ-ProcessPerSCS-r17 SEQUENCE {

scs-120kHz-r17 ENUMERATED {supported} OPTIONAL,

scs-480kHz-r17 ENUMERATED {supported} OPTIONAL,

scs-960kHz-r17 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- R1 24-9: 32 UL HARQ processes for FR 2-2

support32-UL-HARQ-ProcessPerSCS-r17 SEQUENCE {

scs-120kHz-r17 ENUMERATED {supported} OPTIONAL,

scs-480kHz-r17 ENUMERATED {supported} OPTIONAL,

scs-960kHz-r17 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\...,

\[\[

\-- R4 15-1: 64QAM for PUSCH for FR2-2

modulation64-QAM-PUSCH-FR2-2-r17 ENUMERATED {supported} OPTIONAL

\]\]

}

\-- TAG-FR2-2-ACCESSPARAMSPERBAND-STOP

\-- ASN1STOP

#### -- *HighSpeedParameters*

The IE *HighSpeedParameters* is used to convey capabilities related to
high speed scenarios.

*HighSpeedParameters* information element

\-- ASN1START

\-- TAG-HIGHSPEEDPARAMETERS-START

HighSpeedParameters-r16 ::= SEQUENCE {

measurementEnhancement-r16 ENUMERATED {supported} OPTIONAL,

demodulationEnhancement-r16 ENUMERATED {supported} OPTIONAL

}

HighSpeedParameters-v1650 ::= CHOICE {

intraNR-MeasurementEnhancement-r16 ENUMERATED {supported},

interRAT-MeasurementEnhancement-r16 ENUMERATED {supported}

}

HighSpeedParameters-v1700 ::= SEQUENCE {

\-- R4 18-1: Enhanced RRM requirements specified for CA for FR1 HST

measurementEnhancementCA-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 18-2: Enhanced RRM requirements specified for inter-frequency
measurement in connected mode for FR1 HST

measurementEnhancementInterFreq-r17 ENUMERATED {supported} OPTIONAL

}

\-- TAG-HIGHSPEEDPARAMETERS-STOP

\-- ASN1STOP

#### -- *IMS-Parameters*

The IE *IMS-Parameters* is used to convey capabilities related to IMS.

*IMS-Parameters* information element

\-- ASN1START

\-- TAG-IMS-PARAMETERS-START

IMS-Parameters ::= SEQUENCE {

ims-ParametersCommon IMS-ParametersCommon OPTIONAL,

ims-ParametersFRX-Diff IMS-ParametersFRX-Diff OPTIONAL,

\...

}

IMS-Parameters-v1700 ::= SEQUENCE {

ims-ParametersFR2-2-r17 IMS-ParametersFR2-2-r17 OPTIONAL

}

IMS-ParametersCommon ::= SEQUENCE {

voiceOverEUTRA-5GC ENUMERATED {supported} OPTIONAL,

\...,

\[\[

voiceOverSCG-BearerEUTRA-5GC ENUMERATED {supported} OPTIONAL

\]\],

\[\[

voiceFallbackIndicationEPS-r16 ENUMERATED {supported} OPTIONAL

\]\]

}

IMS-ParametersFRX-Diff ::= SEQUENCE {

voiceOverNR ENUMERATED {supported} OPTIONAL,

\...

}

IMS-ParametersFR2-2-r17 ::= SEQUENCE {

voiceOverNR-r17 ENUMERATED {supported} OPTIONAL,

\...

}

\-- TAG-IMS-PARAMETERS-STOP

\-- ASN1STOP

#### -- *InterRAT-Parameters*

The IE *InterRAT-Parameters* is used convey UE capabilities related to
the other RATs.

*InterRAT-Parameters* information element

\-- ASN1START

\-- TAG-INTERRAT-PARAMETERS-START

InterRAT-Parameters ::= SEQUENCE {

eutra EUTRA-Parameters OPTIONAL,

\...,

\[\[

utra-FDD-r16 UTRA-FDD-Parameters-r16 OPTIONAL

\]\]

}

EUTRA-Parameters ::= SEQUENCE {

supportedBandListEUTRA SEQUENCE (SIZE (1..maxBandsEUTRA)) OF
FreqBandIndicatorEUTRA,

eutra-ParametersCommon EUTRA-ParametersCommon OPTIONAL,

eutra-ParametersXDD-Diff EUTRA-ParametersXDD-Diff OPTIONAL,

\...

}

EUTRA-ParametersCommon ::= SEQUENCE {

mfbi-EUTRA ENUMERATED {supported} OPTIONAL,

modifiedMPR-BehaviorEUTRA BIT STRING (SIZE (32)) OPTIONAL,

multiNS-Pmax-EUTRA ENUMERATED {supported} OPTIONAL,

rs-SINR-MeasEUTRA ENUMERATED {supported} OPTIONAL,

\...,

\[\[

ne-DC ENUMERATED {supported} OPTIONAL

\]\],

\[\[

nr-HO-ToEN-DC-r16 ENUMERATED {supported} OPTIONAL

\]\]

}

EUTRA-ParametersXDD-Diff ::= SEQUENCE {

rsrqMeasWidebandEUTRA ENUMERATED {supported} OPTIONAL,

\...

}

UTRA-FDD-Parameters-r16 ::= SEQUENCE {

supportedBandListUTRA-FDD-r16 SEQUENCE (SIZE (1..maxBandsUTRA-FDD-r16))
OF SupportedBandUTRA-FDD-r16,

\...

}

SupportedBandUTRA-FDD-r16 ::= ENUMERATED {

bandI, bandII, bandIII, bandIV, bandV, bandVI,

bandVII, bandVIII, bandIX, bandX, bandXI,

bandXII, bandXIII, bandXIV, bandXV, bandXVI,

bandXVII, bandXVIII, bandXIX, bandXX,

bandXXI, bandXXII, bandXXIII, bandXXIV,

bandXXV, bandXXVI, bandXXVII, bandXXVIII,

bandXXIX, bandXXX, bandXXXI, bandXXXII}

\-- TAG-INTERRAT-PARAMETERS-STOP

\-- ASN1STOP

#### -- *MAC-Parameters*

The IE *MAC-Parameters* is used to convey capabilities related to MAC.

*MAC-Parameters* information element

\-- ASN1START

\-- TAG-MAC-PARAMETERS-START

MAC-Parameters ::= SEQUENCE {

mac-ParametersCommon MAC-ParametersCommon OPTIONAL,

mac-ParametersXDD-Diff MAC-ParametersXDD-Diff OPTIONAL

}

MAC-Parameters-v1610 ::= SEQUENCE {

mac-ParametersFRX-Diff-r16 MAC-ParametersFRX-Diff-r16 OPTIONAL

}

MAC-Parameters-v1700 ::= SEQUENCE {

mac-ParametersFR2-2-r17 MAC-ParametersFR2-2-r17 OPTIONAL

}

MAC-Parameters-v17b0 ::= SEQUENCE {

mTRP-PUSCH-PHR-Type1-Reporting-r17 ENUMERATED {supported} OPTIONAL

}

MAC-Parameters-v17c0 ::= SEQUENCE {

directSCellActivationWithTCI-r17 ENUMERATED {supported} OPTIONAL

}

MAC-ParametersCommon ::= SEQUENCE {

lcp-Restriction ENUMERATED {supported} OPTIONAL,

dummy ENUMERATED {supported} OPTIONAL,

lch-ToSCellRestriction ENUMERATED {supported} OPTIONAL,

\...,

\[\[

recommendedBitRate ENUMERATED {supported} OPTIONAL,

recommendedBitRateQuery ENUMERATED {supported} OPTIONAL

\]\],

\[\[

recommendedBitRateMultiplier-r16 ENUMERATED {supported} OPTIONAL,

preEmptiveBSR-r16 ENUMERATED {supported} OPTIONAL,

autonomousTransmission-r16 ENUMERATED {supported} OPTIONAL,

lch-PriorityBasedPrioritization-r16 ENUMERATED {supported} OPTIONAL,

lch-ToConfiguredGrantMapping-r16 ENUMERATED {supported} OPTIONAL,

lch-ToGrantPriorityRestriction-r16 ENUMERATED {supported} OPTIONAL,

singlePHR-P-r16 ENUMERATED {supported} OPTIONAL,

ul-LBT-FailureDetectionRecovery-r16 ENUMERATED {supported} OPTIONAL,

\-- R4 8-1: MPE

tdd-MPE-P-MPR-Reporting-r16 ENUMERATED {supported} OPTIONAL,

lcid-ExtensionIAB-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

spCell-BFR-CBRA-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

srs-ResourceId-Ext-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

enhancedUuDRX-forSidelink-r17 ENUMERATED {supported} OPTIONAL,

\--27-10: Support of UL MAC CE based MG activation request for PRS
measurements

mg-ActivationRequestPRS-Meas-r17 ENUMERATED {supported} OPTIONAL,

\--27-11: Support of DL MAC CE based MG activation request for PRS
measurements

mg-ActivationCommPRS-Meas-r17 ENUMERATED {supported} OPTIONAL,

intraCG-Prioritization-r17 ENUMERATED {supported} OPTIONAL,

jointPrioritizationCG-Retx-Timer-r17 ENUMERATED {supported} OPTIONAL,

survivalTime-r17 ENUMERATED {supported} OPTIONAL,

lcg-ExtensionIAB-r17 ENUMERATED {supported} OPTIONAL,

harq-FeedbackDisabled-r17 ENUMERATED {supported} OPTIONAL,

uplink-Harq-ModeB-r17 ENUMERATED {supported} OPTIONAL,

sr-TriggeredBy-TA-Report-r17 ENUMERATED {supported} OPTIONAL,

extendedDRX-CycleInactive-r17 ENUMERATED {supported} OPTIONAL,

simultaneousSR-PUSCH-DiffPUCCH-groups-r17 ENUMERATED {supported}
OPTIONAL,

lastTransmissionUL-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

harq-RTT-TimerDL-ForNTN-MulticastMBS-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

sr-TriggeredByTA-ReportATG-r18 ENUMERATED {supported} OPTIONAL,

extendedDRX-CycleInactive-r18 ENUMERATED {supported} OPTIONAL,

additionalBS-Table-r18 ENUMERATED {supported} OPTIONAL,

delayStatusReport-r18 ENUMERATED {supported} OPTIONAL,

cg-RetransmissionMonitoringDisabling-r18 ENUMERATED {supported}
OPTIONAL,

non-IntegerDRX-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

MAC-ParametersFRX-Diff-r16 ::= SEQUENCE {

directMCG-SCellActivation-r16 ENUMERATED {supported} OPTIONAL,

directMCG-SCellActivationResume-r16 ENUMERATED {supported} OPTIONAL,

directSCG-SCellActivation-r16 ENUMERATED {supported} OPTIONAL,

directSCG-SCellActivationResume-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 19-1: DRX Adaptation

drx-Adaptation-r16 SEQUENCE {

non-SharedSpectrumChAccess-r16 MinTimeGap-r16 OPTIONAL,

sharedSpectrumChAccess-r16 MinTimeGap-r16 OPTIONAL

} OPTIONAL,

\...

}

MAC-ParametersFR2-2-r17 ::= SEQUENCE {

directMCG-SCellActivation-r17 ENUMERATED {supported} OPTIONAL,

directMCG-SCellActivationResume-r17 ENUMERATED {supported} OPTIONAL,

directSCG-SCellActivation-r17 ENUMERATED {supported} OPTIONAL,

directSCG-SCellActivationResume-r17 ENUMERATED {supported} OPTIONAL,

drx-Adaptation-r17 SEQUENCE {

non-SharedSpectrumChAccess-r17 MinTimeGapFR2-2-r17 OPTIONAL,

sharedSpectrumChAccess-r17 MinTimeGapFR2-2-r17 OPTIONAL

} OPTIONAL,

\...

}

MAC-ParametersXDD-Diff ::= SEQUENCE {

skipUplinkTxDynamic ENUMERATED {supported} OPTIONAL,

logicalChannelSR-DelayTimer ENUMERATED {supported} OPTIONAL,

longDRX-Cycle ENUMERATED {supported} OPTIONAL,

shortDRX-Cycle ENUMERATED {supported} OPTIONAL,

multipleSR-Configurations ENUMERATED {supported} OPTIONAL,

multipleConfiguredGrants ENUMERATED {supported} OPTIONAL,

\...,

\[\[

secondaryDRX-Group-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

enhancedSkipUplinkTxDynamic-r16 ENUMERATED {supported} OPTIONAL,

enhancedSkipUplinkTxConfigured-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

dummy1 ENUMERATED {supported} OPTIONAL,

dummy2 ENUMERATED {supported} OPTIONAL

\]\]

}

MinTimeGap-r16 ::= SEQUENCE {

scs-15kHz-r16 ENUMERATED {sl1, sl3} OPTIONAL,

scs-30kHz-r16 ENUMERATED {sl1, sl6} OPTIONAL,

scs-60kHz-r16 ENUMERATED {sl1, sl12} OPTIONAL,

scs-120kHz-r16 ENUMERATED {sl2, sl24} OPTIONAL

}

MinTimeGapFR2-2-r17 ::= SEQUENCE {

scs-120kHz-r17 ENUMERATED {sl2, sl24} OPTIONAL,

scs-480kHz-r17 ENUMERATED {sl8, sl96} OPTIONAL,

scs-960kHz-r17 ENUMERATED {sl16, sl192} OPTIONAL

}

MAC-ParametersPerBand-r18 ::= SEQUENCE {

ptm-Retransmission-r18 ENUMERATED {supported} OPTIONAL,

ptm-RetransmissionInactive-r18 ENUMERATED {supported} OPTIONAL,

\...

}

\-- TAG-MAC-PARAMETERS-STOP

\-- ASN1STOP

#### -- *MeasAndMobParameters*

The IE *MeasAndMobParameters* is used to convey UE capabilities related
to measurements for radio resource management (RRM), radio link
monitoring (RLM) and mobility (e.g. handover).

*MeasAndMobParameters* information element

\-- ASN1START

\-- TAG-MEASANDMOBPARAMETERS-START

MeasAndMobParameters ::= SEQUENCE {

measAndMobParametersCommon MeasAndMobParametersCommon OPTIONAL,

measAndMobParametersXDD-Diff MeasAndMobParametersXDD-Diff OPTIONAL,

measAndMobParametersFRX-Diff MeasAndMobParametersFRX-Diff OPTIONAL

}

MeasAndMobParameters-v15t0 ::= SEQUENCE {

measAndMobParametersCommon-v15t0 MeasAndMobParametersCommon-v15t0
OPTIONAL

}

MeasAndMobParameters-v1700 ::= SEQUENCE {

measAndMobParametersFR2-2-r17 MeasAndMobParametersFR2-2-r17 OPTIONAL

}

MeasAndMobParametersCommon ::= SEQUENCE {

supportedGapPattern BIT STRING (SIZE (22)) OPTIONAL,

ssb-RLM ENUMERATED {supported} OPTIONAL,

ssb-AndCSI-RS-RLM ENUMERATED {supported} OPTIONAL,

\...,

\[\[

eventB-MeasAndReport ENUMERATED {supported} OPTIONAL,

handoverFDD-TDD ENUMERATED {supported} OPTIONAL,

eutra-CGI-Reporting ENUMERATED {supported} OPTIONAL,

nr-CGI-Reporting ENUMERATED {supported} OPTIONAL

\]\],

\[\[

independentGapConfig ENUMERATED {supported} OPTIONAL,

periodicEUTRA-MeasAndReport ENUMERATED {supported} OPTIONAL,

handoverFR1-FR2 ENUMERATED {supported} OPTIONAL,

maxNumberCSI-RS-RRM-RS-SINR ENUMERATED {n4, n8, n16, n32, n64, n96}
OPTIONAL

\]\],

\[\[

nr-CGI-Reporting-ENDC ENUMERATED {supported} OPTIONAL

\]\],

\[\[

eutra-CGI-Reporting-NEDC ENUMERATED {supported} OPTIONAL,

eutra-CGI-Reporting-NRDC ENUMERATED {supported} OPTIONAL,

nr-CGI-Reporting-NEDC ENUMERATED {supported} OPTIONAL,

nr-CGI-Reporting-NRDC ENUMERATED {supported} OPTIONAL

\]\],

\[\[

reportAddNeighMeasForPeriodic-r16 ENUMERATED {supported} OPTIONAL,

condHandoverParametersCommon-r16 SEQUENCE {

condHandoverFDD-TDD-r16 ENUMERATED {supported} OPTIONAL,

condHandoverFR1-FR2-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

nr-NeedForGap-Reporting-r16 ENUMERATED {supported} OPTIONAL,

supportedGapPattern-NRonly-r16 BIT STRING (SIZE (10)) OPTIONAL,

supportedGapPattern-NRonly-NEDC-r16 ENUMERATED {supported} OPTIONAL,

maxNumberCLI-RSSI-r16 ENUMERATED {n8, n16, n32, n64} OPTIONAL,

maxNumberCLI-SRS-RSRP-r16 ENUMERATED {n4, n8, n16, n32} OPTIONAL,

maxNumberPerSlotCLI-SRS-RSRP-r16 ENUMERATED {n2, n4, n8} OPTIONAL,

mfbi-IAB-r16 ENUMERATED {supported} OPTIONAL,

dummy ENUMERATED {supported} OPTIONAL,

nr-CGI-Reporting-NPN-r16 ENUMERATED {supported} OPTIONAL,

idleInactiveEUTRA-MeasReport-r16 ENUMERATED {supported} OPTIONAL,

idleInactive-ValidityArea-r16 ENUMERATED {supported} OPTIONAL,

eutra-AutonomousGaps-r16 ENUMERATED {supported} OPTIONAL,

eutra-AutonomousGaps-NEDC-r16 ENUMERATED {supported} OPTIONAL,

eutra-AutonomousGaps-NRDC-r16 ENUMERATED {supported} OPTIONAL,

pcellT312-r16 ENUMERATED {supported} OPTIONAL,

supportedGapPattern-r16 BIT STRING (SIZE (2)) OPTIONAL

\]\],

\[\[

\-- R4 19-2 Concurrent measurement gaps

concurrentMeasGap-r17 CHOICE {

concurrentPerUE-OnlyMeasGap-r17 ENUMERATED {supported},

concurrentPerUE-PerFRCombMeasGap-r17 ENUMERATED {supported}

} OPTIONAL,

\-- R4 19-1 Network controlled small gap (NCSG)

nr-NeedForGapNCSG-Reporting-r17 ENUMERATED {supported} OPTIONAL,

eutra-NeedForGapNCSG-Reporting-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 19-1-1 per FR Network controlled small gap (NCSG)

ncsg-MeasGapPerFR-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 19-1-2 Network controlled small gap (NCSG) supported patterns

ncsg-MeasGapPatterns-r17 BIT STRING (SIZE(24)) OPTIONAL,

\-- R4 19-1-3 Network controlled small gap (NCSG) supported NR-only
patterns

ncsg-MeasGapNR-Patterns-r17 BIT STRING (SIZE(24)) OPTIONAL,

\-- R4 19-3-2 pre-configured measurement gap

preconfiguredUE-AutonomousMeasGap-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 19-3-1 pre-configured measurement gap

preconfiguredNW-ControlledMeasGap-r17 ENUMERATED {supported} OPTIONAL,

handoverFR1-FR2-2-r17 ENUMERATED {supported} OPTIONAL,

handoverFR2-1-FR2-2-r17 ENUMERATED {supported} OPTIONAL,

\-- RAN4 14-1: per-FR MG for PRS measurement

independentGapConfigPRS-r17 ENUMERATED {supported} OPTIONAL,

rrm-RelaxationRRC-ConnectedRedCap-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 25-3: Parallel measurements with multiple measurement gaps

parallelMeasurementGap-r17 ENUMERATED {n2} OPTIONAL,

condHandoverWithSCG-NRDC-r17 ENUMERATED {supported} OPTIONAL,

gNB-ID-LengthReporting-r17 ENUMERATED {supported} OPTIONAL,

gNB-ID-LengthReporting-ENDC-r17 ENUMERATED {supported} OPTIONAL,

gNB-ID-LengthReporting-NEDC-r17 ENUMERATED {supported} OPTIONAL,

gNB-ID-LengthReporting-NRDC-r17 ENUMERATED {supported} OPTIONAL,

gNB-ID-LengthReporting-NPN-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R4 25-1: Parallel measurements on multiple SMTC-s for a single
frequency carrier

parallelSMTC-r17 ENUMERATED {n4} OPTIONAL,

\-- R4 19-2-1 Concurrent measurement gaps for EUTRA

concurrentMeasGapEUTRA-r17 ENUMERATED {supported} OPTIONAL,

serviceLinkPropDelayDiffReporting-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 19-1-4 Network controlled small gap (NCSG) performing measurement
based on flag deriveSSB-IndexFromCellInter

ncsg-SymbolLevelScheduleRestrictionInter-r17 ENUMERATED {supported}
OPTIONAL

\]\],

\[\[

eventD1-MeasReportTrigger-r17 ENUMERATED {supported} OPTIONAL,

independentGapConfig-maxCC-r17 SEQUENCE {

fr1-Only-r17 INTEGER (1..32) OPTIONAL,

fr2-Only-r17 INTEGER (1..32) OPTIONAL,

fr1-AndFR2-r17 INTEGER (1..32) OPTIONAL

} OPTIONAL

\]\],

\[\[

interSatMeas-r17 ENUMERATED {supported} OPTIONAL,

deriveSSB-IndexFromCellInterNon-NCSG-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R4 31-1 Enhanced L3 measurement reporting for unknown SCell
activation if the valid L3 measurement results are available

l3-MeasUnknownSCellActivation-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 31-3 Shorter measurement interval for unknown SCell activation

shortMeasInterval-r18 ENUMERATED {supported} OPTIONAL,

nr-NeedForInterruptionReport-r18 ENUMERATED {supported} OPTIONAL,

measSequenceConfig-r18 ENUMERATED {supported} OPTIONAL,

cellIndividualOffsetPerMeasEvent-r18 ENUMERATED {supported} OPTIONAL,

eventD2-MeasReportTrigger-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 32-1: Concurrent gaps with Pre-MG in a FR

concurrentMeasGapsPreMG-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 32-2: Support for dynamic collisions

dynamicCollision-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 32-3: Concurrent gaps with NCSG in a FR

concurrentMeasGapsNCSG-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 32-4: Inter-RAT EUTRAN measurements without gap and outside
active DL BWP

eutra-NoGapMeasurementOutsideBWP-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 32-5: Inter-RAT EUTRAN measurement without gap and within active
DL BWP

eutra-NoGapMeasurementInsideBWP-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 32-6: Effective measurement window for inter-RAT EUTRAN
measurements

eutra-MeasEMW-r18 BIT STRING (SIZE(6)) OPTIONAL,

\-- R4 32-7: Simultaneous reception of NR data and EUTRAN CRS with
different numerology

concurrentMeasCRS-InsideBWP-EUTRA-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 39-2a: SSB based inter-frequency L1-RSRP measurements with
measurement gaps

ltm-InterFreqMeasGap-r18 ENUMERATED {supported} OPTIONAL,

dummy-ltm-FastUE-Processing-r18 SEQUENCE {

fr1-r18 ENUMERATED {ms10, ms15},

fr2-r18 ENUMERATED {ms10, ms15},

fr1-AndFR2-r18 ENUMERATED {ms20, ms30}

} OPTIONAL,

rach-LessHandoverInterFreq-r18 ENUMERATED {supported} OPTIONAL,

enterAndLeaveCellReport-r18 ENUMERATED {supported} OPTIONAL,

bestCellChangeReport-r18 ENUMERATED {supported} OPTIONAL,

secondBestCellChangeReport-r18 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

ltm-InterFreq-r18 ENUMERATED {supported} OPTIONAL,

ltm-MCG-NRDC-r18 ENUMERATED {supported} OPTIONAL,

ltm-RACH-LessDG-r18 ENUMERATED {supported} OPTIONAL,

ltm-RACH-LessCG-r18 ENUMERATED {supported} OPTIONAL,

ltm-Recovery-r18 ENUMERATED {supported} OPTIONAL,

ltm-ReferenceConfig-r18 ENUMERATED {supported} OPTIONAL,

ltm-MCG-NRDC-Release-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 39-7: Faster UE processing time during cell switch

ltm-FastUE-Processing-r18 SEQUENCE {

fr1-r18 ENUMERATED {ms10, ms15} OPTIONAL,

fr2-r18 ENUMERATED {ms10, ms15} OPTIONAL,

fr1-AndFR2-r18 ENUMERATED {ms20, ms30} OPTIONAL

} OPTIONAL,

ntn-NeighbourCellInfoSupport-r18 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

ltm-interFreqL1-OnlyInBC-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

MeasAndMobParametersCommon-v15t0 ::= SEQUENCE {

intraF-NeighMeasForSCellWithoutSSB ENUMERATED{supported} OPTIONAL

}

MeasAndMobParametersXDD-Diff ::= SEQUENCE {

intraAndInterF-MeasAndReport ENUMERATED {supported} OPTIONAL,

eventA-MeasAndReport ENUMERATED {supported} OPTIONAL,

\...,

\[\[

handoverInterF ENUMERATED {supported} OPTIONAL,

handoverLTE-EPC ENUMERATED {supported} OPTIONAL,

handoverLTE-5GC ENUMERATED {supported} OPTIONAL

\]\],

\[\[

sftd-MeasNR-Neigh ENUMERATED {supported} OPTIONAL,

sftd-MeasNR-Neigh-DRX ENUMERATED {supported} OPTIONAL

\]\],

\[\[

dummy ENUMERATED {supported} OPTIONAL

\]\]

}

MeasAndMobParametersFRX-Diff ::= SEQUENCE {

ss-SINR-Meas ENUMERATED {supported} OPTIONAL,

csi-RSRP-AndRSRQ-MeasWithSSB ENUMERATED {supported} OPTIONAL,

csi-RSRP-AndRSRQ-MeasWithoutSSB ENUMERATED {supported} OPTIONAL,

csi-SINR-Meas ENUMERATED {supported} OPTIONAL,

csi-RS-RLM ENUMERATED {supported} OPTIONAL,

\...,

\[\[

handoverInterF ENUMERATED {supported} OPTIONAL,

handoverLTE-EPC ENUMERATED {supported} OPTIONAL,

handoverLTE-5GC ENUMERATED {supported} OPTIONAL

\]\],

\[\[

maxNumberResource-CSI-RS-RLM ENUMERATED {n2, n4, n6, n8} OPTIONAL

\]\],

\[\[

simultaneousRxDataSSB-DiffNumerology ENUMERATED {supported} OPTIONAL

\]\],

\[\[

nr-AutonomousGaps-r16 ENUMERATED {supported} OPTIONAL,

nr-AutonomousGaps-ENDC-r16 ENUMERATED {supported} OPTIONAL,

nr-AutonomousGaps-NEDC-r16 ENUMERATED {supported} OPTIONAL,

nr-AutonomousGaps-NRDC-r16 ENUMERATED {supported} OPTIONAL,

dummy ENUMERATED {supported} OPTIONAL,

cli-RSSI-Meas-r16 ENUMERATED {supported} OPTIONAL,

cli-SRS-RSRP-Meas-r16 ENUMERATED {supported} OPTIONAL,

interFrequencyMeas-NoGap-r16 ENUMERATED {supported} OPTIONAL,

simultaneousRxDataSSB-DiffNumerology-Inter-r16 ENUMERATED {supported}
OPTIONAL,

idleInactiveNR-MeasReport-r16 ENUMERATED {supported} OPTIONAL,

\-- R4 6-2: Support of beam level Early Measurement Reporting

idleInactiveNR-MeasBeamReport-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

increasedNumberofCSIRSPerMO-r16 ENUMERATED {supported} OPTIONAL

\]\]

}

MeasAndMobParametersFR2-2-r17 ::= SEQUENCE {

handoverInterF-r17 ENUMERATED {supported} OPTIONAL,

handoverLTE-EPC-r17 ENUMERATED {supported} OPTIONAL,

handoverLTE-5GC-r17 ENUMERATED {supported} OPTIONAL,

idleInactiveNR-MeasReport-r17 ENUMERATED {supported} OPTIONAL,

\...

}

\-- TAG-MEASANDMOBPARAMETERS-STOP

\-- ASN1STOP

#### -- *MeasAndMobParametersMRDC*

The IE *MeasAndMobParametersMRDC* is used to convey capability
parameters related to RRM measurements and RRC mobility.

*MeasAndMobParametersMRDC* information element

\-- ASN1START

\-- TAG-MEASANDMOBPARAMETERSMRDC-START

MeasAndMobParametersMRDC ::= SEQUENCE {

measAndMobParametersMRDC-Common MeasAndMobParametersMRDC-Common
OPTIONAL,

measAndMobParametersMRDC-XDD-Diff MeasAndMobParametersMRDC-XDD-Diff
OPTIONAL,

measAndMobParametersMRDC-FRX-Diff MeasAndMobParametersMRDC-FRX-Diff
OPTIONAL

}

MeasAndMobParametersMRDC-v1560 ::= SEQUENCE {

measAndMobParametersMRDC-XDD-Diff-v1560
MeasAndMobParametersMRDC-XDD-Diff-v1560 OPTIONAL

}

MeasAndMobParametersMRDC-v1610 ::= SEQUENCE {

measAndMobParametersMRDC-Common-v1610
MeasAndMobParametersMRDC-Common-v1610 OPTIONAL,

interNR-MeasEUTRA-IAB-r16 ENUMERATED {supported} OPTIONAL

}

MeasAndMobParametersMRDC-v1700 ::= SEQUENCE {

measAndMobParametersMRDC-Common-v1700
MeasAndMobParametersMRDC-Common-v1700 OPTIONAL

}

MeasAndMobParametersMRDC-v1730 ::= SEQUENCE {

measAndMobParametersMRDC-Common-v1730
MeasAndMobParametersMRDC-Common-v1730 OPTIONAL

}

MeasAndMobParametersMRDC-v1810 ::= SEQUENCE {

measAndMobParametersMRDC-Common-v1810
MeasAndMobParametersMRDC-Common-v1810 OPTIONAL

}

MeasAndMobParametersMRDC-Common ::= SEQUENCE {

independentGapConfig ENUMERATED {supported} OPTIONAL

}

MeasAndMobParametersMRDC-Common-v1610 ::= SEQUENCE {

condPSCellChangeParametersCommon-r16 SEQUENCE {

condPSCellChangeFDD-TDD-r16 ENUMERATED {supported} OPTIONAL,

condPSCellChangeFR1-FR2-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

pscellT312-r16 ENUMERATED {supported} OPTIONAL

}

MeasAndMobParametersMRDC-Common-v1700 ::= SEQUENCE {

condPSCellChangeParameters-r17 SEQUENCE {

inter-SN-condPSCellChangeFDD-TDD-NRDC-r17 ENUMERATED {supported}
OPTIONAL,

inter-SN-condPSCellChangeFR1-FR2-NRDC-r17 ENUMERATED {supported}
OPTIONAL,

inter-SN-condPSCellChangeFDD-TDD-ENDC-r17 ENUMERATED {supported}
OPTIONAL,

inter-SN-condPSCellChangeFR1-FR2-ENDC-r17 ENUMERATED {supported}
OPTIONAL,

mn-InitiatedCondPSCellChange-FR1FDD-ENDC-r17 ENUMERATED {supported}
OPTIONAL,

mn-InitiatedCondPSCellChange-FR1TDD-ENDC-r17 ENUMERATED {supported}
OPTIONAL,

mn-InitiatedCondPSCellChange-FR2TDD-ENDC-r17 ENUMERATED {supported}
OPTIONAL,

sn-InitiatedCondPSCellChange-FR1FDD-ENDC-r17 ENUMERATED {supported}
OPTIONAL,

sn-InitiatedCondPSCellChange-FR1TDD-ENDC-r17 ENUMERATED {supported}
OPTIONAL,

sn-InitiatedCondPSCellChange-FR2TDD-ENDC-r17 ENUMERATED {supported}
OPTIONAL

} OPTIONAL,

condHandoverWithSCG-ENDC-r17 ENUMERATED {supported} OPTIONAL,

condHandoverWithSCG-NEDC-r17 ENUMERATED {supported} OPTIONAL

}

MeasAndMobParametersMRDC-Common-v1730 ::= SEQUENCE {

independentGapConfig-maxCC-r17 SEQUENCE {

fr1-Only-r17 INTEGER (1..32) OPTIONAL,

fr2-Only-r17 INTEGER (1..32) OPTIONAL,

fr1-AndFR2-r17 INTEGER (1..32) OPTIONAL

}

}

MeasAndMobParametersMRDC-Common-v1810 ::= SEQUENCE {

mn-ConfiguredMN-TriggerSCPAC-r18 ENUMERATED {supported} OPTIONAL,

mn-ConfiguredSN-TriggerSCPAC-r18 ENUMERATED {supported} OPTIONAL,

sn-ConfiguredSCPAC-r18 ENUMERATED {supported} OPTIONAL,

mn-ConfiguredMN-TriggerSCPAC-afterSCG-release-r18 ENUMERATED {supported}
OPTIONAL,

mn-ConfiguredReferenceConfigSCPAC-r18 ENUMERATED {supported} OPTIONAL,

sn-ConfiguredReferenceConfigSCPAC-r18 ENUMERATED {supported} OPTIONAL,

condHandoverWithCandSCG-Addition-r18 ENUMERATED {supported} OPTIONAL,

condHandoverWithCandSCG-FR1-FR2-Change-r18 ENUMERATED {supported}
OPTIONAL,

condHandoverWithCandSCG-FDD-TDD-Change-r18 ENUMERATED {supported}
OPTIONAL

}

MeasAndMobParametersMRDC-XDD-Diff ::= SEQUENCE {

sftd-MeasPSCell ENUMERATED {supported} OPTIONAL,

sftd-MeasNR-Cell ENUMERATED {supported} OPTIONAL

}

MeasAndMobParametersMRDC-XDD-Diff-v1560 ::= SEQUENCE {

sftd-MeasPSCell-NEDC ENUMERATED {supported} OPTIONAL

}

MeasAndMobParametersMRDC-FRX-Diff ::= SEQUENCE {

simultaneousRxDataSSB-DiffNumerology ENUMERATED {supported} OPTIONAL

}

\-- TAG-MEASANDMOBPARAMETERSMRDC-STOP

\-- ASN1STOP

#### -- *MIMO-Layers*

The IE *MIMO-Layers* is used to convey the number of supported MIMO
layers.

*MIMO-Layers* information element

\-- ASN1START

\-- TAG-MIMO-LAYERS-START

MIMO-LayersDL ::= ENUMERATED {twoLayers, fourLayers, eightLayers}

MIMO-LayersUL ::= ENUMERATED {oneLayer, twoLayers, fourLayers}

\-- TAG-MIMO-LAYERS-STOP

\-- ASN1STOP

#### -- *MIMO-ParametersPerBand*

The IE *MIMO-ParametersPerBand* is used to convey MIMO related
parameters specific for a certain band (not per feature set or band
combination).

*MIMO-ParametersPerBand* information element

\-- ASN1START

\-- TAG-MIMO-PARAMETERSPERBAND-START

MIMO-ParametersPerBand ::= SEQUENCE {

tci-StatePDSCH SEQUENCE {

maxNumberConfiguredTCI-StatesPerCC ENUMERATED {n4, n8, n16, n32, n64,
n128} OPTIONAL,

maxNumberActiveTCI-PerBWP ENUMERATED {n1, n2, n4, n8} OPTIONAL

} OPTIONAL,

additionalActiveTCI-StatePDCCH ENUMERATED {supported} OPTIONAL,

pusch-TransCoherence ENUMERATED {nonCoherent, partialCoherent,
fullCoherent} OPTIONAL,

beamCorrespondenceWithoutUL-BeamSweeping ENUMERATED {supported}
OPTIONAL,

periodicBeamReport ENUMERATED {supported} OPTIONAL,

aperiodicBeamReport ENUMERATED {supported} OPTIONAL,

sp-BeamReportPUCCH ENUMERATED {supported} OPTIONAL,

sp-BeamReportPUSCH ENUMERATED {supported} OPTIONAL,

dummy1 DummyG OPTIONAL,

maxNumberRxBeam INTEGER (2..8) OPTIONAL,

maxNumberRxTxBeamSwitchDL SEQUENCE {

scs-15kHz ENUMERATED {n4, n7, n14} OPTIONAL,

scs-30kHz ENUMERATED {n4, n7, n14} OPTIONAL,

scs-60kHz ENUMERATED {n4, n7, n14} OPTIONAL,

scs-120kHz ENUMERATED {n4, n7, n14} OPTIONAL,

scs-240kHz ENUMERATED {n4, n7, n14} OPTIONAL

} OPTIONAL,

maxNumberNonGroupBeamReporting ENUMERATED {n1, n2, n4} OPTIONAL,

groupBeamReporting ENUMERATED {supported} OPTIONAL,

uplinkBeamManagement SEQUENCE {

maxNumberSRS-ResourcePerSet-BM ENUMERATED {n2, n4, n8, n16},

maxNumberSRS-ResourceSet INTEGER (1..8)

} OPTIONAL,

maxNumberCSI-RS-BFD INTEGER (1..64) OPTIONAL,

maxNumberSSB-BFD INTEGER (1..64) OPTIONAL,

maxNumberCSI-RS-SSB-CBD INTEGER (1..256) OPTIONAL,

dummy2 ENUMERATED {supported} OPTIONAL,

twoPortsPTRS-UL ENUMERATED {supported} OPTIONAL,

dummy5 SRS-Resources OPTIONAL,

dummy3 INTEGER (1..4) OPTIONAL,

beamReportTiming SEQUENCE {

scs-15kHz ENUMERATED {sym2, sym4, sym8} OPTIONAL,

scs-30kHz ENUMERATED {sym4, sym8, sym14, sym28} OPTIONAL,

scs-60kHz ENUMERATED {sym8, sym14, sym28} OPTIONAL,

scs-120kHz ENUMERATED {sym14, sym28, sym56} OPTIONAL

} OPTIONAL,

ptrs-DensityRecommendationSetDL SEQUENCE {

scs-15kHz PTRS-DensityRecommendationDL OPTIONAL,

scs-30kHz PTRS-DensityRecommendationDL OPTIONAL,

scs-60kHz PTRS-DensityRecommendationDL OPTIONAL,

scs-120kHz PTRS-DensityRecommendationDL OPTIONAL

} OPTIONAL,

ptrs-DensityRecommendationSetUL SEQUENCE {

scs-15kHz PTRS-DensityRecommendationUL OPTIONAL,

scs-30kHz PTRS-DensityRecommendationUL OPTIONAL,

scs-60kHz PTRS-DensityRecommendationUL OPTIONAL,

scs-120kHz PTRS-DensityRecommendationUL OPTIONAL

} OPTIONAL,

dummy4 DummyH OPTIONAL,

aperiodicTRS ENUMERATED {supported} OPTIONAL,

\...,

\[\[

dummy6 ENUMERATED {true} OPTIONAL,

beamManagementSSB-CSI-RS BeamManagementSSB-CSI-RS OPTIONAL,

beamSwitchTiming SEQUENCE {

scs-60kHz ENUMERATED {sym14, sym28, sym48, sym224, sym336} OPTIONAL,

scs-120kHz ENUMERATED {sym14, sym28, sym48, sym224, sym336} OPTIONAL

} OPTIONAL,

codebookParameters CodebookParameters OPTIONAL,

csi-RS-IM-ReceptionForFeedback CSI-RS-IM-ReceptionForFeedback OPTIONAL,

csi-RS-ProcFrameworkForSRS CSI-RS-ProcFrameworkForSRS OPTIONAL,

csi-ReportFramework CSI-ReportFramework OPTIONAL,

csi-RS-ForTracking CSI-RS-ForTracking OPTIONAL,

srs-AssocCSI-RS SEQUENCE (SIZE (1.. maxNrofCSI-RS-Resources)) OF
SupportedCSI-RS-Resource OPTIONAL,

spatialRelations SpatialRelations OPTIONAL

\]\],

\[\[

\-- R1 16-2b-0: Support of default QCL assumption with two TCI states

defaultQCL-TwoTCI-r16 ENUMERATED {supported} OPTIONAL,

codebookParametersPerBand-r16 CodebookParameters-v1610 OPTIONAL,

\-- R1 16-1b-3: Support of PUCCH resource groups per BWP for
simultaneous spatial relation update

simul-SpatialRelationUpdatePUCCHResGroup-r16 ENUMERATED {supported}
OPTIONAL,

\-- R1 16-1f: Maximum number of SCells configured for SCell beam failure
recovery simultaneously

maxNumberSCellBFR-r16 ENUMERATED {n1,n2,n4,n8} OPTIONAL,

\-- R1 16-2c: Supports simultaneous reception with different Type-D for
FR2 only

simultaneousReceptionDiffTypeD-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-1a-1: SSB/CSI-RS for L1-SINR measurement

ssb-csirs-SINR-measurement-r16 SEQUENCE {

maxNumberSSB-CSIRS-OneTx-CMR-r16 ENUMERATED {n8, n16, n32, n64},

maxNumberCSI-IM-NZP-IMR-res-r16 ENUMERATED {n8, n16, n32, n64},

maxNumberCSIRS-2Tx-res-r16 ENUMERATED {n0, n4, n8, n16, n32, n64},

maxNumberSSB-CSIRS-res-r16 ENUMERATED {n8, n16, n32, n64, n128},

maxNumberCSI-IM-NZP-IMR-res-mem-r16 ENUMERATED {n8, n16, n32, n64,
n128},

supportedCSI-RS-Density-CMR-r16 ENUMERATED {one, three, oneAndThree},

maxNumberAperiodicCSI-RS-Res-r16 ENUMERATED {n2, n4, n8, n16, n32, n64},

supportedSINR-meas-r16 ENUMERATED {ssbWithCSI-IM, ssbWithNZP-IMR,
csirsWithNZP-IMR, csi-RSWithoutIMR} OPTIONAL

} OPTIONAL,

\-- R1 16-1a-2: Non-group based L1-SINR reporting

nonGroupSINR-reporting-r16 ENUMERATED {n1, n2, n4} OPTIONAL,

\-- R1 16-1a-3: Non-group based L1-SINR reporting

groupSINR-reporting-r16 ENUMERATED {supported} OPTIONAL,

multiDCI-multiTRP-Parameters-r16 SEQUENCE {

\-- R1 16-2a-0: Overlapping PDSCHs in time and fully overlapping in
frequency and time

overlapPDSCHsFullyFreqTime-r16 INTEGER (1..2) OPTIONAL,

\-- R1 16-2a-1: Overlapping PDSCHs in time and partially overlapping in
frequency and time

overlapPDSCHsInTimePartiallyFreq-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-2a-2: Out of order operation for DL

outOfOrderOperationDL-r16 SEQUENCE {

supportPDCCH-ToPDSCH-r16 ENUMERATED {supported} OPTIONAL,

supportPDSCH-ToHARQ-ACK-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- R1 16-2a-3: Out of order operation for UL

outOfOrderOperationUL-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-2a-5: Separate CRS rate matching

separateCRS-RateMatching-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-2a-6: Default QCL enhancement for multi-DCI based multi-TRP

defaultQCL-PerCORESETPoolIndex-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-2a-7: Maximum number of activated TCI states

maxNumberActivatedTCI-States-r16 SEQUENCE {

maxNumberPerCORESET-Pool-r16 ENUMERATED {n1, n2, n4, n8},

maxTotalNumberAcrossCORESET-Pool-r16 ENUMERATED {n2, n4, n8, n16}

} OPTIONAL

} OPTIONAL,

singleDCI-SDM-scheme-Parameters-r16 SEQUENCE {

\-- R1 16-2b-1b: Single-DCI based SDM scheme - Support of new DMRS port
entry

supportNewDMRS-Port-r16 ENUMERATED {supported1, supported2, supported3}
OPTIONAL,

\-- R1 16-2b-1a: Support of s-port DL PTRS

supportTwoPortDL-PTRS-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- R1 16-2b-2: Support of single-DCI based FDMSchemeA

supportFDM-SchemeA-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-2b-3a: Single-DCI based FDMSchemeB CW soft combining

supportCodeWordSoftCombining-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-2b-4: Single-DCI based TDMSchemeA

supportTDM-SchemeA-r16 ENUMERATED {kb3, kb5, kb10, kb20, noRestriction}
OPTIONAL,

\-- R1 16-2b-5: Single-DCI based inter-slot TDM

supportInter-slotTDM-r16 SEQUENCE {

supportRepNumPDSCH-TDRA-r16 ENUMERATED {n2, n3, n4, n5, n6, n7, n8,
n16},

maxTBS-Size-r16 ENUMERATED {kb3, kb5, kb10, kb20, noRestriction},

maxNumberTCI-states-r16 INTEGER (1..2)

} OPTIONAL,

\-- R1 16-4: Low PAPR DMRS for PDSCH

lowPAPR-DMRS-PDSCH-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-6a: Low PAPR DMRS for PUSCH without transform precoding

lowPAPR-DMRS-PUSCHwithoutPrecoding-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-6b: Low PAPR DMRS for PUCCH

lowPAPR-DMRS-PUCCH-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-6c: Low PAPR DMRS for PUSCH with transform precoding & pi/2
BPSK

lowPAPR-DMRS-PUSCHwithPrecoding-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-7: Extension of the maximum number of configured aperiodic CSI
report settings

csi-ReportFrameworkExt-r16 CSI-ReportFrameworkExt-r16 OPTIONAL,

\-- R1 16-3a, 16-3a-1, 16-3b, 16-3b-1, 16-8: Individual new codebook
types

codebookParametersAddition-r16 CodebookParametersAddition-r16 OPTIONAL,

\-- R1 16-8: Mixed codebook types

codebookComboParametersAddition-r16 CodebookComboParametersAddition-r16
OPTIONAL,

\-- R4 8-2: SSB based beam correspondence

beamCorrespondenceSSB-based-r16 ENUMERATED {supported} OPTIONAL,

\-- R4 8-3: CSI-RS based beam correspondence

beamCorrespondenceCSI-RS-based-r16 ENUMERATED {supported} OPTIONAL,

beamSwitchTiming-r16 SEQUENCE {

scs-60kHz-r16 ENUMERATED {sym224, sym336} OPTIONAL,

scs-120kHz-r16 ENUMERATED {sym224, sym336} OPTIONAL

} OPTIONAL

\]\],

\[\[

\-- R1 16-1a-4: Semi-persistent L1-SINR report on PUCCH

semi-PersistentL1-SINR-Report-PUCCH-r16 SEQUENCE {

supportReportFormat1-2OFDM-syms-r16 ENUMERATED {supported} OPTIONAL,

supportReportFormat4-14OFDM-syms-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- R1 16-1a-5: Semi-persistent L1-SINR report on PUSCH

semi-PersistentL1-SINR-Report-PUSCH-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 16-1h: Support of 64 configured PUCCH spatial relations

spatialRelations-v1640 SEQUENCE {

maxNumberConfiguredSpatialRelations-v1640 ENUMERATED {n96, n128, n160,
n192, n224, n256, n288, n320}

} OPTIONAL,

\-- R1 16-1i: Support of 64 configured candidate beam RSs for BFR

support64CandidateBeamRS-BFR-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 16-2a-9: Interpretation of maxNumberMIMO-LayersPDSCH for
multi-DCI based mTRP

maxMIMO-LayersForMulti-DCI-mTRP-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

supportedSINR-meas-v1670 BIT STRING (SIZE (4)) OPTIONAL

\]\],

\[\[

\-- R1 23-8-5 Increased repetition for SRS

srs-increasedRepetition-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-8-6 Partial frequency sounding of SRS

srs-partialFrequencySounding-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-8-7 Start RB location hopping for partial frequency SRS

srs-startRB-locationHoppingPartial-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-8-8 Comb-8 SRS

srs-combEight-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-9-1 Basic Features of Further Enhanced Port-Selection Type II
Codebook (FeType-II) per band information

codebookParametersfetype2-r17 CodebookParametersfetype2-r17 OPTIONAL,

\-- R1 23-3-1-2a Two associated CSI-RS resources

mTRP-PUSCH-twoCSI-RS-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-3-2 Multi-TRP PUCCH repetition scheme 1 (inter-slot)

mTRP-PUCCH-InterSlot-r17 ENUMERATED {pf0-2, pf1-3-4, pf0-4} OPTIONAL,

\-- R1 23-3-2b Cyclic mapping for multi-TRP PUCCH repetition

mTRP-PUCCH-CyclicMapping-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-3-2c Second TPC field for multi-TRP PUCCH repetition

mTRP-PUCCH-SecondTPC-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-5-2 MTRP BFR based on two BFD-RS set

mTRP-BFR-twoBFD-RS-Set-r17 SEQUENCE {

maxBFD-RS-resourcesPerSetPerBWP-r17 ENUMERATED {n1, n2},

maxBFR-r17 INTEGER (1..9),

maxBFD-RS-resourcesAcrossSetsPerBWP-r17 ENUMERATED {n2, n3, n4}

} OPTIONAL,

\-- R1 23-5-2a PUCCH-SR resources for MTRP BFRQ - Max number of PUCCH-SR
resources for MTRP BFRQ per cell group

mTRP-BFR-PUCCH-SR-perCG-r17 ENUMERATED{n1, n2} OPTIONAL,

\-- R1 23-5-2b Association between a BFD-RS resource set on SpCell and a
PUCCH SR resource

mTRP-BFR-association-PUCCH-SR-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-6-3 Simultaneous activation of two TCI states for PDCCH across
multiple CCs (HST/URLLC)

sfn-SimulTwoTCI-AcrossMultiCC-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-6-4 Default DL beam setup for SFN

sfn-DefaultDL-BeamSetup-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-6-4a Default UL beam setup for SFN PDCCH(FR2 only)

sfn-DefaultUL-BeamSetup-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-8-1 SRS triggering offset enhancement

srs-TriggeringOffset-r17 ENUMERATED {n1, n2, n4} OPTIONAL,

\-- R1 23-8-2 Triggering SRS only in DCI 0_1/0_2

srs-TriggeringDCI-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-9-5 Active CSI-RS resources and ports for mixed codebook types
in any slot per band information

codebookComboParameterMixedType-r17 CodebookComboParameterMixedType-r17
OPTIONAL,

\-- R1 23-1-1 Unified TCI \[with joint DL/UL TCI update\] for intra-cell
beam management

unifiedJointTCI-r17 SEQUENCE{

maxConfiguredJointTCI-r17 ENUMERATED {n8, n12, n16, n24, n32, n48, n64,
n128},

maxActivatedTCIAcrossCC-r17 ENUMERATED {n1, n2, n4, n8, n16}

} OPTIONAL,

\-- R1 23-1-1b Unified TCI with joint DL/UL TCI update for intra- and
inter-cell beam management with more than one MAC-CE

unifiedJointTCI-multiMAC-CE-r17 SEQUENCE{

minBeamApplicationTime-r17 ENUMERATED {n1, n2, n4, n7, n14, n28, n42,
n56, n70, n84, n98, n112, n224, n336}

OPTIONAL,

maxNumMAC-CE-PerCC ENUMERATED {n2, n3, n4, n5, n6, n7, n8}

} OPTIONAL,

\-- R1 23-1-1d Per BWP TCI state pool configuration for CA mode

unifiedJointTCI-perBWP-CA-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-1-1e TCI state pool configuration with TCI pool sharing for CA
mode

unifiedJointTCI-ListSharingCA-r17 ENUMERATED {n1,n2,n4,n8} OPTIONAL,

\-- R1 23-1-1f Common multi-CC TCI state ID update and activation

unifiedJointTCI-commonMultiCC-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-1-1g Beam misalignment between the DL source RS in the TCI
state

unifiedJointTCI-BeamAlignDLRS-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-1-1h Association between TCI state and UL PC settings for
PUCCH, PUSCH, and SRS

unifiedJointTCI-PC-association-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-1-1i Indication/configuration of R17 TCI states for aperiodic
CSI-RS, PDCCH, PDSCH

unifiedJointTCI-Legacy-r17 ENUMERATED {supported} OPTIONAL,

\-- 23-1-1m Indication/configuration of R17 TCI states for SRS

unifiedJointTCI-Legacy-SRS-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-1-1j Indication/configuration of R17 TCI states for CORESET #0

unifiedJointTCI-Legacy-CORESET0-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-1-1c SCell BFR with unified TCI framework (NOTE; pre-requisite
is empty)

unifiedJointTCI-SCellBFR-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-1-1a Unified TCI with joint DL/UL TCI update for inter-cell
beam management

unifiedJointTCI-InterCell-r17 SEQUENCE{

additionalMAC-CE-PerCC-r17 ENUMERATED {n0, n1, n2, n4},

additionalMAC-CE-AcrossCC-r17 ENUMERATED {n0, n1, n2, n4}

} OPTIONAL,

\-- R1 23-10-1 Unified TCI with separate DL/UL TCI update for intra-cell
beam management

unifiedSeparateTCI-r17 SEQUENCE{

maxConfiguredDL-TCI-r17 ENUMERATED {n4, n8, n12, n16, n24, n32, n48,
n64, n128},

maxConfiguredUL-TCI-r17 ENUMERATED {n4, n8, n12, n16, n24, n32, n48,
n64},

maxActivatedDL-TCIAcrossCC-r17 ENUMERATED {n1, n2, n4, n8, n16},

maxActivatedUL-TCIAcrossCC-r17 ENUMERATED {n1, n2, n4, n8, n16}

} OPTIONAL,

\-- R1 23-10-1b Unified TCI with separate DL/UL TCI update for
intra-cell beam management with more than one MAC-CE

unifiedSeparateTCI-multiMAC-CE-r17 SEQUENCE{

minBeamApplicationTime-r17 ENUMERATED {n1, n2, n4, n7, n14, n28, n42,
n56, n70, n84, n98, n112, n224, n336},

maxActivatedDL-TCIPerCC-r17 INTEGER (2..8),

maxActivatedUL-TCIPerCC-r17 INTEGER (2..8)

} OPTIONAL,

\-- R1 23-10-1d Per BWP DL/UL-TCI state pool configuration for CA mode

unifiedSeparateTCI-perBWP-CA-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-10-1e TCI state pool configuration with DL/UL-TCI pool sharing
for CA mode

unifiedSeparateTCI-ListSharingCA-r17 SEQUENCE {

maxNumListDL-TCI-r17 ENUMERATED {n1,n2,n4,n8} OPTIONAL,

maxNumListUL-TCI-r17 ENUMERATED {n1,n2,n4,n8} OPTIONAL

} OPTIONAL,

\-- R1 23-10-1f Common multi-CC DL/UL-TCI state ID update and activation
with separate DL/UL TCI update

unifiedSeparateTCI-commonMultiCC-r17 ENUMERATED {supported} OPTIONAL,

\-- 23-10-1m Unified TCI with separate DL/UL TCI update for inter-cell
beam management with more than one MAC-CE

unifiedSeparateTCI-InterCell-r17 SEQUENCE {

k-DL-PerCC-r17 ENUMERATED {n0, n1, n2, n4},

k-UL-PerCC-r17 ENUMERATED {n0, n1, n2, n4},

k-DL-AcrossCC-r17 ENUMERATED {n0, n1, n2, n4},

k-UL-AcrossCC-r17 ENUMERATED {n0, n1, n2, n4}

} OPTIONAL,

\-- R1 23-1-2 Inter-cell beam measurement and reporting (for inter-cell
BM and mTRP)

unifiedJointTCI-mTRP-InterCell-BM-r17 SEQUENCE {

maxNumAdditionalPCI-L1-RSRP-r17 INTEGER (1..7),

maxNumSSB-ResourceL1-RSRP-AcrossCC-r17 ENUMERATED {n1,n2,n4,n8}

} OPTIONAL,

\-- R1 23-1-3 MPE mitigation

mpe-Mitigation-r17 SEQUENCE {

maxNumP-MPR-RI-pairs-r17 INTEGER (1..4),

maxNumConfRS-r17 ENUMERATED {n1, n2, n4, n8, n12, n16, n28, n32, n48,
n64}

} OPTIONAL,

\-- R1 23-1-4 UE capability value reporting

srs-PortReport-r17 SEQUENCE {

capVal1-r17 ENUMERATED {n1, n2, n4} OPTIONAL,

capVal2-r17 ENUMERATED {n1, n2, n4} OPTIONAL,

capVal3-r17 ENUMERATED {n1, n2, n4} OPTIONAL,

capVal4-r17 ENUMERATED {n1, n2, n4} OPTIONAL

} OPTIONAL,

\-- R1 23-2-1a Monitoring of individual candidates

mTRP-PDCCH-individual-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-2-1b PDCCH repetition with PDCCH monitoring on any span of up
to 3 consecutive OFDM symbols of a slot

mTRP-PDCCH-anySpan-3Symbols-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-2-2 Two QCL TypeD for CORESET monitoring in PDCCH repetition

mTRP-PDCCH-TwoQCL-TypeD-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-3-1-2b CSI-RS processing framework for SRS with two associated
CSI-RS resources

mTRP-PUSCH-CSI-RS-r17 SEQUENCE {

maxNumPeriodicSRS-r17 INTEGER (1..8),

maxNumAperiodicSRS-r17 INTEGER (1..8),

maxNumSP-SRS-r17 INTEGER (0..8),

numSRS-ResourcePerCC-r17 INTEGER (1..16),

numSRS-ResourceNonCodebook-r17 INTEGER (1..2)

} OPTIONAL,

\-- R1 23-3-1a Cyclic mapping for Multi-TRP PUSCH repetition

mTRP-PUSCH-cyclicMapping-r17 ENUMERATED {typeA,typeB,both} OPTIONAL,

\-- R1 23-3-1b Second TPC field for Multi-TRP PUSCH repetition

mTRP-PUSCH-secondTPC-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-3-1c Two PHR reporting

mTRP-PUSCH-twoPHR-Reporting-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-3-1e A-CSI report

mTRP-PUSCH-A-CSI-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-3-1f SP-CSI report

mTRP-PUSCH-SP-CSI-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-3-1g CG PUSCH transmission

mTRP-PUSCH-CG-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-3-2d Updating two Spatial relation or two sets of power
control parameters for PUCCH group

mTRP-PUCCH-MAC-CE-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-3-2e Maximum number of power control parameter sets configured
for multi-TRP PUCCH repetition in FR1

mTRP-PUCCH-maxNum-PC-FR1-r17 INTEGER (3..8) OPTIONAL,

\-- R1 23-4 IntCell-mTRP

mTRP-inter-Cell-r17 SEQUENCE {

maxNumAdditionalPCI-Case1-r17 INTEGER (1..7),

maxNumAdditionalPCI-Case2-r17 INTEGER (0..7)

} OPTIONAL,

\-- R1 23-5-1 Group based L1-RSRP reporting enhancements

mTRP-GroupBasedL1-RSRP-r17 SEQUENCE {

maxNumBeamGroups-r17 INTEGER (1..4),

maxNumRS-WithinSlot-r17 ENUMERATED {n2,n3,n4,n8,n16,n32,n64},

maxNumRS-AcrossSlot-r17 ENUMERATED {n8, n16, n32, n64, n128}

} OPTIONAL,

\-- R1 23-5-2c MAC-CE based update of explicit BFD-RS
mTRP-PUCCH-IntraSlot-r17 =\> per band

mTRP-BFD-RS-MAC-CE-r17 ENUMERATED {n4, n8, n12, n16, n32, n48, n64 }
OPTIONAL,

\-- R1 23-7-1 Basic Features of CSI Enhancement for Multi-TRP

mTRP-CSI-EnhancementPerBand-r17 SEQUENCE {

maxNumNZP-CSI-RS-r17 INTEGER (2..8),

cSI-Report-mode-r17 ENUMERATED {mode1, mode2, both},

supportedComboAcrossCCs-r17 SEQUENCE (SIZE (1..16)) OF
CSI-MultiTRP-SupportedCombinations-r17,

codebookModeNCJT-r17 ENUMERATED{mode1,mode1And2}

} OPTIONAL,

\-- R1 23-7-1b Active CSI-RS resources and ports in the presence of
multi-TRP CSI

codebookComboParameterMultiTRP-r17 CodebookComboParameterMultiTRP-r17
OPTIONAL,

\-- R1 23-7-1a Additional CSI report mode 1

mTRP-CSI-additionalCSI-r17 ENUMERATED{x1,x2} OPTIONAL,

\-- R1 23-7-4 Support of Nmax=2 for Multi-TRP CSI

mTRP-CSI-N-Max2-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-7-5 CMR sharing

mTRP-CSI-CMR-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 23-8-11 Partial frequency sounding of SRS for non-frequency
hopping case

srs-partialFreqSounding-r17 ENUMERATED {supported} OPTIONAL,

\-- R1-24 feature: Extend beamSwitchTiming for FR2-2

beamSwitchTiming-v1710 SEQUENCE {

scs-480kHz ENUMERATED {sym56, sym112, sym192, sym896, sym1344} OPTIONAL,

scs-960kHz ENUMERATED {sym112, sym224, sym384, sym1792, sym2688}
OPTIONAL

} OPTIONAL,

\-- R1-24 feature: Extend beamSwitchTiming-r16 for FR2-2

beamSwitchTiming-r17 SEQUENCE {

scs-480kHz-r17 ENUMERATED {sym896, sym1344} OPTIONAL,

scs-960kHz-r17 ENUMERATED {sym1792, sym2688} OPTIONAL

} OPTIONAL,

\-- R1-24 feature: Extend beamReportTiming for FR2-2

beamReportTiming-v1710 SEQUENCE {

scs-480kHz-r17 ENUMERATED {sym56, sym112, sym224} OPTIONAL,

scs-960kHz-r17 ENUMERATED {sym112, sym224, sym448} OPTIONAL

} OPTIONAL,

\-- R1-24 feature: Extend maximum number of RX/TX beam switch DL for
FR2-2

maxNumberRxTxBeamSwitchDL-v1710 SEQUENCE {

scs-480kHz-r17 ENUMERATED {n2, n4, n7} OPTIONAL,

scs-960kHz-r17 ENUMERATED {n1, n2, n4, n7} OPTIONAL

} OPTIONAL

\]\],

\[\[

\-- R1-23-1-4a: Semi-persistent/aperiodic capability value report

srs-PortReportSP-AP-r17 ENUMERATED {supported} OPTIONAL,

maxNumberRxBeam-v1720 INTEGER (9..12) OPTIONAL,

\-- R1-23-6-5 Support implicit configuration of RS(s) with two TCI
states for beam failure detection

sfn-ImplicitRS-twoTCI-r17 ENUMERATED {supported} OPTIONAL,

\-- R1-23-6-6 QCL-TypeD collision handling with CORESET with 2 TCI
states

sfn-QCL-TypeD-Collision-twoTCI-r17 ENUMERATED {supported} OPTIONAL,

\-- R1-23-7-1c Basic Features of CSI Enhancement for Multi-TRP - number
of CPUs

mTRP-CSI-numCPU-r17 ENUMERATED {n2, n3, n4} OPTIONAL

\]\],

\[\[

supportRepNumPDSCH-TDRA-DCI-1-2-r17 ENUMERATED {n2, n3, n4, n5, n6, n7,
n8, n16} OPTIONAL

\]\],

\[\[

codebookParametersetype2DopplerCSI-r18
CodebookParametersetype2DopplerCSI-r18 OPTIONAL,

codebookParametersfetype2DopplerCSI-r18
CodebookParametersfetype2DopplerCSI-r18 OPTIONAL,

codebookParametersetype2CJT-r18 CodebookParametersetype2CJT-r18
OPTIONAL,

codebookParametersfetype2CJT-r18 CodebookParametersfetype2CJT-r18
OPTIONAL,

codebookComboParametersCJT-r18 CodebookComboParametersCJT-r18 OPTIONAL,

codebookParametersHARQ-ACK-PUSCH-r18
CodebookParametersHARQ-ACK-PUSCH-r18 OPTIONAL,

\-- R1 40-1-1: Unified TCI with joint DL/UL TCI update for single-DCI
based intra-cell multi-TRP with single activated TCI

\-- codepoint per CC

tci-JointTCI-UpdateSingleActiveTCI-PerCC-r18 SEQUENCE {

maxNumberConfigJointTCIPerCC-PerBWP-r18 ENUMERATED
{n8,n12,n16,n24,n32,n48,n64,n128},

maxNumberActiveJointTCI-AcrossCC-r18 ENUMERATED {n2,n4,n6,n8,n16,n32}

} OPTIONAL,

\-- R1 40-1-1a: Unified TCI with joint DL/UL TCI update for single-DCI
based intra-cell multi-TRP with multiple activated TCI

\-- codepoints per CC

tci-JointTCI-UpdateMultiActiveTCI-PerCC-r18 SEQUENCE {

tci-StateInd-r18 ENUMERATED {withAssignment, withoutAssignment},

maxNumberActiveJointTCI-PerCC-r18 INTEGER (2..8)

} OPTIONAL,

\-- R1 40-1-1c: DCI format 1_1 and if supported 1_2 configured with TCI
selection field

tci-SelectionDCI-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-1-2: Unified TCI with separate DL/UL TCI update for single-DCI
based intra-cell multi-TRP with single activated TCI

\-- codepoint per CC

tci-SeparateTCI-UpdateSingleActiveTCI-PerCC-r18 SEQUENCE {

maxNumConfigDL-TCI-PerCC-PerBWP-r18 ENUMERATED {n4, n8, n12, n16, n24,
n32, n48, n64, n128},

maxNumConfigUL-TCI-PerCC-PerBWP-r18 ENUMERATED {n4, n8, n12, n16, n24,
n32, n48, n64},

maxNumActiveDL-TCI-AcrossCC-r18 ENUMERATED {n2, n4, n8, n16},

maxNumActiveUL-TCI-AcrossCC-r18 ENUMERATED {n2, n4, n8, n16}

} OPTIONAL,

\-- R1 40-1-2a: Unified TCI with separate DL/UL TCI update for
single-DCI based intra-cell multi-TRP with multiple

\-- activated TCI codepoints per CC

tci-SeparateTCI-UpdateMultiActiveTCI-PerCC-r18 SEQUENCE {

maxNumActiveDL-TCI-AcrossCC-r18 ENUMERATED {n2, n4, n8, n16},

maxNumActiveUL-TCI-AcrossCC-r18 ENUMERATED {n2, n4, n8, n16}

} OPTIONAL,

\-- R1 40-1-3: Per aperiodic CSI-RS resource/resource set configuration
for TCI selection in S-DCI based MTRP

tci-SelectionAperiodicCSI-RS-r18 ENUMERATED {perResource,
perResourceSet, both} OPTIONAL,

\-- R1 40-1-3a: Per aperiodic CSI-RS resource/resource set configuration
for TCI selection in M-DCI based MTRP

tci-SelectionAperiodicCSI-RS-M-DCI-r18 ENUMERATED {perResource,
perResourceSet, both} OPTIONAL,

\-- R1 40-1-4: Two TCI states for CJT Tx scheme for PDSCH

twoTCI-StatePDSCH-CJT-TxScheme-r18 ENUMERATED {cjtSchemeA, cjtSchemeB,
both} OPTIONAL,

\-- R1 40-1-7: Unified TCI with joint DL/UL TCI update for multi-DCI
based multi-TRP with single activated TCI

\-- codepoint per CORESETPoolIndex per CC

tci-JointTCI-UpdateSingleActiveTCI-PerCC-PerCORESET-r18 SEQUENCE {

mTRP-Operation-r18 ENUMERATED {intraCell, intraCellAndInterCell},

maxNumberConfigJointTCIPerCC-PerBWP-r18 ENUMERATED
{n8,n12,n16,n24,n32,n48,n64,n128},

maxNumberActiveJointTCIAcrossCC-PerCORESET-r18 ENUMERATED
{n1,n2,n4,n8,n16}

} OPTIONAL,

\-- R1 40-1-7a: Unified TCI with joint DL/UL TCI update for multi-DCI
based multi-TRP with multiple activated TCI

\-- codepoints per CORESETPoolIndex per CC

tci-JointTCI-UpdateMultiActiveTCI-PerCC-PerCORESET-r18 INTEGER (2..8)
OPTIONAL,

\-- R1 40-1-8: TRP-specific BFR with unified TCI framework with Unified
TCI

tci-TRP-BFR-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-1-9: Unified TCI with separate DL/UL TCI update for multi-DCI
based multi-TRP with single activated TCI

\-- codepoint per CORESETPoolIndex per CC

tci-SeparateTCI-UpdateSingleActiveTCI-PerCC-PerCORESET-r18 SEQUENCE {

mTRP-Operation-r18 ENUMERATED {intraCell, intraCellAndInterCell},

maxNumConfigDL-TCI-PerCC-PerBWP-r18 ENUMERATED {n8, n12, n16, n24, n32,
n48, n64, n128},

maxNumConfigUL-TCI-PerCC-PerBWP-r18 ENUMERATED {n8, n12, n16, n24, n32,
n48, n64},

maxNumActiveDL-TCI-AcrossCC-r18 ENUMERATED {n1, n2, n4, n8, n16},

maxNumActiveUL-TCI-AcrossCC-r18 ENUMERATED {n1, n2, n4, n8, n16}

} OPTIONAL,

\-- R1 40-1-9a: Unified TCI with separate DL/UL TCI update for multi-DCI
based multi-TRP with multiple activated TCI

\-- codepoints per CORESETPoolIndex per CC

tci-SeparateTCI-UpdateMultiActiveTCI-PerCC-PerCORESET-r18 SEQUENCE {

maxNumConfigDL-TCI-PerCC-PerBWP-r18 INTEGER (1..8),

maxNumConfigUL-TCI-PerCC-PerBWP-r18 INTEGER (1..8)

} OPTIONAL,

\-- R1 40-1-12: Common multi-CC TCI state ID update and activation for
single-DCI based multi-TRP

commonTCI-SingleDCI-r18 INTEGER (1..4) OPTIONAL,

\-- R1 40-1-13: Common multi-CC TCI state ID update and activation for
multi-DCI based multi-TRP

commonTCI-MultiDCI-r18 INTEGER (1..4) OPTIONAL,

\-- R1 40-1-14: Two PHR reporting for STx2P

twoPHR-Reporting-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-2-3: TAG ID indication via absolute TA command MAC CE

spCell-TAG-Ind-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-2-4: PDCCH order sent by one TRP triggers RACH procedure
(specifically PRACH) towards a different TRP based on CFRA for

\-- inter-cell

interCellCrossTRP-PDCCH-OrderCFRA-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-2-4a: PDCCH order sent by one TRP triggers RACH procedure
(specifically PRACH) towards a different TRP based on CFRA for

\-- intra-cell

intraCellCrossTRP-PDCCH-OrderCFRA-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-2-9: Overlapping UL transmission reduction

overlapUL-TransReduction-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-3-2-12: Supported maximum periodicity of CMR when configured
as periodic CSI-RS

maxPeriodicityCMR-r18 ENUMERATED {sl4, sl5, sl8, sl10, sl20} OPTIONAL,

\-- R1 40-3-3-1: TDCP (Time Domain Channel Properties) report

tdcp-Report-r18 SEQUENCE {

valueX-r18 INTEGER (1..2),

maxNumberActiveResource-r18 INTEGER (2..32)

} OPTIONAL,

\-- R1 40-3-3-5: Number of CSI-RS resources for TDCP

tdcp-Resource-r18 SEQUENCE {

maxNumberConfigPerCC-r18 ENUMERATED {n2,n4,n6,n8,n10,n12},

maxNumberConfigAcrossCC-r18 INTEGER (1..32),

maxNumberSimultaneousPerCC-r18 ENUMERATED {n2, n4, n6, n8, n12, n16,
n20, n24, n28, n32}

} OPTIONAL,

\-- R1 40-3-1-24: Timeline for regular eType-II-CJT CSI, or for port
selection FeType-II-CJT CSI

timelineRelax-CJT-CSI-r18 ENUMERATED {n0,n2} OPTIONAL,

\-- R1 40-4-11: Joint configuration of Rel.18 DMRS ports and Rel.18
dynamic switching between DFT-S-OFDM and CP-OFDM for PUSCH

jointConfigDMRSPortDynamicSwitching-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-5-1: SRS comb offset hopping

srs-combOffsetHopping-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-5-1a: Comb offset hopping time-domain behavior when repetition
factor R\>1

srs-combOffsetInTime-r18 ENUMERATED {srs, rsrs, both} OPTIONAL,

\-- R1 40-5-1b: SRS comb offset hopping combined with group/sequence
hopping

srs-combOffsetCombinedGroupSequence-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-5-1c: Comb offset hopping within a subset

srs-combOffsetHoppingWithinSubset-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-5-2: SRS cyclic shift hopping

srs-cyclicShiftHopping-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-5-2a: Smaller cyclic shift granularity for cyclic shift
hopping

srs-cyclicShiftHoppingSmallGranularity-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-5-2b: SRS cyclic shift hopping combined with group/sequence
hopping

srs-cyclicShiftCombinedGroupSequence-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-5-2c: Cyclic shift hopping within a subset

cyclicShiftHoppingWithinSubset-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-5-3: SRS cyclic shift hopping combined with SRS comb offset
hopping

srs-cyclicShiftCombinedCombOffset-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-6-1-1: 2 PTRS ports for single-DCI based STx2P SDM scheme for
PUSCH-codebook

pusch-CB-2PTRS-SingleDCI-STx2P-SDM-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-6-1a-1: 2 PTRS ports for single-DCI based STx2P SDM scheme for
PUSCH-noncodebook

pusch-NonCB-2PTRS-SingleDCI-STx2P-SDM-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-6-1b: Association between CSI-RS and SRS for noncodebook
single-DCI based STx2P SDM scheme for PUSCH

pusch-NonCB-SingleDCI-STx2P-SDM-CSI-RS-SRS-r18 SEQUENCE {

maxNumberPeriodicSRS-Resource-PerBWP-r18 INTEGER (1..8),

maxNumberAperiodicSRS-Resource-PerBWP-r18 INTEGER (1..8),

maxNumberSemiPersistentSRS-ResourcePerBWP-r18 INTEGER (0..8),

valueY-SRS-ResourceAssociate-r18 INTEGER (1..16),

valueX-CSI-RS-ResourceAssociate-r18 INTEGER (1..2)

} OPTIONAL,

\-- R1 40-6-3b-1: Associated CSI-RS resources for noncodebook multi-DCI
based STx2P PUSCH+PUSCH

twoPUSCH-NonCB-Multi-DCI-STx2P-CSI-RS-Resource-r18 SEQUENCE {

maxNumberPeriodicSRS-r18 INTEGER (1..8),

maxNumberAperiodicSRS-r18 INTEGER (1..8),

maxNumberSemiPersistentSRS-r18 INTEGER (0..8),

simultaneousSRS-PerCC-r18 INTEGER (1..16),

simultaneousCSI-RS-NonCB-r18 INTEGER (1..2)

} OPTIONAL,

\-- R1 40-6-1-2: New UL DMRS port entry for single-DCI based SDM scheme
for Rel-15 DMRS port and/or Rel-18 DMRS port

dmrs-PortEntrySingleDCI-SDM-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-6-2-1: 2 PTRS ports for single-DCI based STx2P SFN scheme for
PUSCH-codebook

pusch-CB-2PTRS-SingleDCI-STx2P-SFN-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-6-2a-1: 2 PTRS ports for single-DCI based STx2P SFN scheme for
PUSCH-codebook

pusch-NonCB-2PTRS-SingleDCI-STx2P-SFN-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-6-2b: Association between CSI-RS and SRS for noncodebook
single-DCI based STx2P SFN scheme for PUSCH

pusch-NonCB-SingleDCI-STx2P-SFN-CSI-RS-SRS-r18 SEQUENCE {

maxNumberPeriodicSRS-Resource-PerBWP-r18 INTEGER (1..8),

maxNumberAperiodicSRS-Resource-PerBWP-r18 INTEGER (1..8),

maxNumberSemiPersistentSRS-ResourcePerBWP-r18 INTEGER (0..8),

valueY-SRS-ResourceAssociate-r18 INTEGER (1..16),

valueX-CSI-RS-ResourceAssociate-r18 INTEGER (1..2)

} OPTIONAL,

\-- R1 40-6-3c: Codebook multi-DCI based STx2P PUSCH+PUSCH - Fully
overlapping PUSCHs in time and fully overlapping in frequency

twoPUSCH-CB-MultiDCI-STx2P-FullTimeFullFreqOverlap-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 40-6-3d: Codebook multi-DCI based STx2P PUSCH+PUSCH - Fully
overlapping PUSCHs in time and partially overlapping in frequency

twoPUSCH-CB-MultiDCI-STx2P-FullTimePartialFreqOverlap-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 40-6-3e: Codebook multi-DCI based STx2P PUSCH+PUSCH - Partially
overlapping PUSCHs in time and fully overlapping in frequency

twoPUSCH-CB-MultiDCI-STx2P-PartialTimeFullFreqOverlap-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 40-6-3f: Codebook multi-DCI based STx2P PUSCH+PUSCH - Partially
overlapping PUSCHs in time, partially overlapping in frequency

twoPUSCH-CB-MultiDCI-STx2P-PartialTimePartialFreqOverlap-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 40-6-3g: Codebook multi-DCI based STx2P PUSCH+PUSCH - Partially
overlapping PUSCHs in time, partially or non-overlapping

\-- in frequency

twoPUSCH-CB-MultiDCI-STx2P-PartialTimeNonFreqOverlap-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 40-6-3h: Codebook multi-DCI based STx2P PUSCH+PUSCH for CG+CG

twoPUSCH-CB-MultiDCI-STx2P-CG-CG-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-6-3i: Codebook multi-DCI based STx2P PUSCH+PUSCH for DG+CG

twoPUSCH-CB-MultiDCI-STx2P-CG-DG-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-6-3j: Noncodebook multi-DCI based STx2P PUSCH+PUSCH - Fully
overlapping PUSCHs in time and fully overlapping in frequency

twoPUSCH-NonCB-MultiDCI-STx2P-FullTimeFullFreqOverlap-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 40-6-3k: Noncodebook multi-DCI based STx2P PUSCH+PUSCH - Fully
overlapping PUSCHs in time and partially overlapping in

\-- frequency

twoPUSCH-NonCB-MultiDCI-STx2P-FullTimePartialFreqOverlap-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 40-6-3l: Noncodebook multi-DCI based STx2P PUSCH+PUSCH -
Partially overlapping PUSCHs in time and fully overlapping in

\-- frequency

twoPUSCH-NonCB-MultiDCI-STx2P-PartialTimeFullFreqOverlap-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 40-6-3m: Noncodebook multi-DCI based STx2P PUSCH+PUSCH -
Partially overlapping PUSCHs in time, partially overlapping in

\-- frequency

twoPUSCH-NonCB-MultiDCI-STx2P-PartialTimePartialFreqOverlap-r18
ENUMERATED {supported} OPTIONAL,

\-- R1 40-6-3n: Noncodebook multi-DCI based STx2P PUSCH+PUSCH -
Partially overlapping PUSCHs in time, non-overlapping in frequency

twoPUSCH-NonCB-MultiDCI-STx2P-PartialTimeNonFreqOverlap-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 40-6-3o: Noncodebook multi-DCI based STx2P PUSCH+PUSCH for CG+CG

twoPUSCH-NonCB-MultiDCI-STx2P-CG-CG-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-6-3p: Noncodebook multi-DCI based STx2P PUSCH+PUSCH for DG+CG

twoPUSCH-NonCB-MultiDCI-STx2P-CG-DG-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 40-6-4a: Dynamic indication of repetition number for SFN scheme
for PUCCH

pucch-RepetitionDynamicIndicationSFN-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 40-6-5: Support grouped-based beam reporting for STx2P

groupBeamReporting-STx2P-r18 SEQUENCE {

groupL1-RSRP-Reporting-r18 ENUMERATED {jointULandDL, ulOnly, both},

maxNumberBeamGroups-r18 INTEGER (1..4),

maxNumberResWithinSlotAcrossCC-r18 ENUMERATED {n2,n3,n4,n8,n16,n32,n64},

maxNumberResAcrossCC-r18 ENUMERATED {n8,n16,n32,n64,n128}

} OPTIONAL

\]\],

\[\[

\-- R1 40-4-1k: Simultaneous Configuration of Rel-18 DL DMRS and DCI
format 1_3

simulConfigDMRS-DCI-1-3-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

MIMO-ParametersPerBand-v17b0 ::= SEQUENCE {

\-- R1 23-1-1b Unified TCI with joint DL/UL TCI update for intra- and
inter-cell beam management with more than one MAC-CE

unifiedJointTCI-multiMAC-CE-v17b0 SEQUENCE{

minBeamApplicationTimeJointTCI-v17b0 CHOICE {

fr1-v17b0 SEQUENCE {

scs-15kHz-v17b0 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70} OPTIONAL,

scs-30kHz-v17b0 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70} OPTIONAL,

scs-60kHz-v17b0 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70} OPTIONAL

},

fr2-v17b0 SEQUENCE {

scs-60kHz-v17b0 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70,

sym84, sym98, sym112, sym224, sym336} OPTIONAL,

scs-120kHz-v17b0 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28,
sym42, sym56, sym70,

sym84, sym98, sym112, sym224, sym336} OPTIONAL

}

},

maxNumMAC-CE-PerCC-v17b0 ENUMERATED {n2, n3, n4, n5, n6, n7, n8}

} OPTIONAL,

\-- R1 23-10-1b Unified TCI with separate DL/UL TCI update for
intra-cell beam management with more than one MAC-CE

unifiedSeparateTCI-multiMAC-CE-v17b0 SEQUENCE{

minBeamApplicationTimeSeparateTCI-v17b0 CHOICE {

fr1-v17b0 SEQUENCE {

scs-15kHz-v17b0 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70} OPTIONAL,

scs-30kHz-v17b0 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70} OPTIONAL,

scs-60kHz-v17b0 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70} OPTIONAL

},

fr2-v17b0 SEQUENCE {

scs-60kHz-v17b0 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70,

sym84, sym98, sym112, sym224, sym336} OPTIONAL,

scs-120kHz-v17b0 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28,
sym42, sym56, sym70,

sym84, sym98, sym112, sym224, sym336} OPTIONAL

}

},

maxActivatedDL-TCIPerCC-v17b0 INTEGER (2..8),

maxActivatedUL-TCIPerCC-v17b0 INTEGER (2..8)

} OPTIONAL

}

DummyG ::= SEQUENCE {

maxNumberSSB-CSI-RS-ResourceOneTx ENUMERATED {n8, n16, n32, n64},

maxNumberSSB-CSI-RS-ResourceTwoTx ENUMERATED {n0, n4, n8, n16, n32,
n64},

supportedCSI-RS-Density ENUMERATED {one, three, oneAndThree}

}

BeamManagementSSB-CSI-RS ::= SEQUENCE {

maxNumberSSB-CSI-RS-ResourceOneTx ENUMERATED {n0, n8, n16, n32, n64},

maxNumberCSI-RS-Resource ENUMERATED {n0, n4, n8, n16, n32, n64},

maxNumberCSI-RS-ResourceTwoTx ENUMERATED {n0, n4, n8, n16, n32, n64},

supportedCSI-RS-Density ENUMERATED {one, three, oneAndThree} OPTIONAL,

maxNumberAperiodicCSI-RS-Resource ENUMERATED {n0, n1, n4, n8, n16, n32,
n64}

}

DummyH ::= SEQUENCE {

burstLength INTEGER (1..2),

maxSimultaneousResourceSetsPerCC INTEGER (1..8),

maxConfiguredResourceSetsPerCC INTEGER (1..64),

maxConfiguredResourceSetsAllCC INTEGER (1..128)

}

CSI-RS-ForTracking ::= SEQUENCE {

maxBurstLength INTEGER (1..2),

maxSimultaneousResourceSetsPerCC INTEGER (1..8),

maxConfiguredResourceSetsPerCC INTEGER (1..64),

maxConfiguredResourceSetsAllCC INTEGER (1..256)

}

CSI-RS-IM-ReceptionForFeedback ::= SEQUENCE {

maxConfigNumberNZP-CSI-RS-PerCC INTEGER (1..64),

maxConfigNumberPortsAcrossNZP-CSI-RS-PerCC INTEGER (2..256),

maxConfigNumberCSI-IM-PerCC ENUMERATED {n1, n2, n4, n8, n16, n32},

maxNumberSimultaneousNZP-CSI-RS-PerCC INTEGER (1..64),

totalNumberPortsSimultaneousNZP-CSI-RS-PerCC INTEGER (2..256)

}

CSI-RS-ProcFrameworkForSRS ::= SEQUENCE {

maxNumberPeriodicSRS-AssocCSI-RS-PerBWP INTEGER (1..4),

maxNumberAperiodicSRS-AssocCSI-RS-PerBWP INTEGER (1..4),

maxNumberSP-SRS-AssocCSI-RS-PerBWP INTEGER (0..4),

simultaneousSRS-AssocCSI-RS-PerCC INTEGER (1..8)

}

CSI-ReportFramework ::= SEQUENCE {

maxNumberPeriodicCSI-PerBWP-ForCSI-Report INTEGER (1..4),

maxNumberAperiodicCSI-PerBWP-ForCSI-Report INTEGER (1..4),

maxNumberSemiPersistentCSI-PerBWP-ForCSI-Report INTEGER (0..4),

maxNumberPeriodicCSI-PerBWP-ForBeamReport INTEGER (1..4),

maxNumberAperiodicCSI-PerBWP-ForBeamReport INTEGER (1..4),

maxNumberAperiodicCSI-triggeringStatePerCC ENUMERATED {n3, n7, n15, n31,
n63, n128},

maxNumberSemiPersistentCSI-PerBWP-ForBeamReport INTEGER (0..4),

simultaneousCSI-ReportsPerCC INTEGER (1..8)

}

CSI-ReportFrameworkExt-r16 ::= SEQUENCE {

maxNumberAperiodicCSI-PerBWP-ForCSI-ReportExt-r16 INTEGER (5..8)

}

PTRS-DensityRecommendationDL ::= SEQUENCE {

frequencyDensity1 INTEGER (1..276),

frequencyDensity2 INTEGER (1..276),

timeDensity1 INTEGER (0..29),

timeDensity2 INTEGER (0..29),

timeDensity3 INTEGER (0..29)

}

PTRS-DensityRecommendationUL ::= SEQUENCE {

frequencyDensity1 INTEGER (1..276),

frequencyDensity2 INTEGER (1..276),

timeDensity1 INTEGER (0..29),

timeDensity2 INTEGER (0..29),

timeDensity3 INTEGER (0..29),

sampleDensity1 INTEGER (1..276),

sampleDensity2 INTEGER (1..276),

sampleDensity3 INTEGER (1..276),

sampleDensity4 INTEGER (1..276),

sampleDensity5 INTEGER (1..276)

}

SpatialRelations ::= SEQUENCE {

maxNumberConfiguredSpatialRelations ENUMERATED {n4, n8, n16, n32, n64,
n96},

maxNumberActiveSpatialRelations ENUMERATED {n1, n2, n4, n8, n14},

additionalActiveSpatialRelationPUCCH ENUMERATED {supported} OPTIONAL,

maxNumberDL-RS-QCL-TypeD ENUMERATED {n1, n2, n4, n8, n14}

}

DummyI ::= SEQUENCE {

supportedSRS-TxPortSwitch ENUMERATED {t1r2, t1r4, t2r4, t1r4-t2r4,
tr-equal},

txSwitchImpactToRx ENUMERATED {true} OPTIONAL

}

CSI-MultiTRP-SupportedCombinations-r17 ::= SEQUENCE {

maxNumTx-Ports-r17 ENUMERATED {n2, n4, n8, n12, n16, n24, n32},

maxTotalNumCMR-r17 INTEGER (2..64),

maxTotalNumTx-PortsNZP-CSI-RS-r17 INTEGER (2..256)

}

\-- TAG-MIMO-PARAMETERSPERBAND-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *MIMO-ParametersPerBand* field descriptions                           |
+=======================================================================+
| ***codebookParametersPerBand***                                       |
|                                                                       |
| For a given frequency band, this field this field indicates the       |
| alternative list of *SupportedCSI-RS-Resource* supported for each     |
| codebook type. The supported CSI-RS resources indicated by this field |
| are referred by *codebookParametersperBC* in *CA-ParametersNR* to     |
| indicate the supported CSI-RS resource per band combination.          |
+-----------------------------------------------------------------------+
| ***csi-RS-IM-ReceptionForFeedback/ csi-RS-ProcFrameworkForSRS/        |
| csi-ReportFramework***                                                |
|                                                                       |
| CSI related capabilities which the UE supports on each of the         |
| carriers operated on this band. If the network configures the UE with |
| serving cells on both FR1 and FR2 bands these values may be further   |
| limited by the corresponding fields in                                |
| *fr1-fr2-Add-UE-NR-Capabilities*.                                     |
+-----------------------------------------------------------------------+
| ***supportNewDMRS-Port***                                             |
|                                                                       |
| Presence of this field set to *supported1*, *supported2* or           |
| *supported3* indicates that the UE supports the new DMRS port entry   |
| {0,2,3}.                                                              |
+-----------------------------------------------------------------------+

#### -- *ModulationOrder*

The IE *ModulationOrder* is used to convey the maximum supported
modulation order.

*ModulationOrder* information element

\-- ASN1START

\-- TAG-MODULATIONORDER-START

ModulationOrder ::= ENUMERATED {bpsk-halfpi, bpsk, qpsk, qam16, qam64,
qam256}

\-- TAG-MODULATIONORDER-STOP

\-- ASN1STOP

#### -- *MRDC-Parameters*

The IE *MRDC-Parameters* contains the band combination parameters
specific to MR-DC for a given MR-DC band combination.

*MRDC-Parameters* information element

\-- ASN1START

\-- TAG-MRDC-PARAMETERS-START

MRDC-Parameters ::= SEQUENCE {

singleUL-Transmission ENUMERATED {supported} OPTIONAL,

dynamicPowerSharingENDC ENUMERATED {supported} OPTIONAL,

tdm-Pattern ENUMERATED {supported} OPTIONAL,

ul-SharingEUTRA-NR ENUMERATED {tdm, fdm, both} OPTIONAL,

ul-SwitchingTimeEUTRA-NR ENUMERATED {type1, type2} OPTIONAL,

simultaneousRxTxInterBandENDC ENUMERATED {supported} OPTIONAL,

asyncIntraBandENDC ENUMERATED {supported} OPTIONAL,

\...,

\[\[

dualPA-Architecture ENUMERATED {supported} OPTIONAL,

intraBandENDC-Support ENUMERATED {non-contiguous, both} OPTIONAL,

ul-TimingAlignmentEUTRA-NR ENUMERATED {required} OPTIONAL

\]\]

}

MRDC-Parameters-v1580 ::= SEQUENCE {

dynamicPowerSharingNEDC ENUMERATED {supported} OPTIONAL

}

MRDC-Parameters-v1590 ::= SEQUENCE {

interBandContiguousMRDC ENUMERATED {supported} OPTIONAL

}

MRDC-Parameters-v15g0 ::= SEQUENCE {

simultaneousRxTxInterBandENDCPerBandPair SimultaneousRxTxPerBandPair
OPTIONAL

}

MRDC-Parameters-v15n0 ::= SEQUENCE {

intraBandENDC-Support-UL ENUMERATED {non-contiguous, both} OPTIONAL

}

MRDC-Parameters-v1620 ::= SEQUENCE {

maxUplinkDutyCycle-interBandENDC-TDD-PC2-r16 SEQUENCE{

eutra-TDD-Config0-r16 ENUMERATED {n20, n40, n50, n60, n70, n80, n90,
n100} OPTIONAL,

eutra-TDD-Config1-r16 ENUMERATED {n20, n40, n50, n60, n70, n80, n90,
n100} OPTIONAL,

eutra-TDD-Config2-r16 ENUMERATED {n20, n40, n50, n60, n70, n80, n90,
n100} OPTIONAL,

eutra-TDD-Config3-r16 ENUMERATED {n20, n40, n50, n60, n70, n80, n90,
n100} OPTIONAL,

eutra-TDD-Config4-r16 ENUMERATED {n20, n40, n50, n60, n70, n80, n90,
n100} OPTIONAL,

eutra-TDD-Config5-r16 ENUMERATED {n20, n40, n50, n60, n70, n80, n90,
n100} OPTIONAL,

eutra-TDD-Config6-r16 ENUMERATED {n20, n40, n50, n60, n70, n80, n90,
n100} OPTIONAL

} OPTIONAL,

\-- R1 18-2 Single UL TX operation for TDD PCell in EN-DC

tdm-restrictionTDD-endc-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 18-2a Single UL TX operation for FDD PCell in EN-DC

tdm-restrictionFDD-endc-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 18-2b Support of HARQ-offset for SUO case1 in EN-DC with LTE TDD
PCell for type 1 UE

singleUL-HARQ-offsetTDD-PCell-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 18-3 Dual Tx transmission for EN-DC with FDD PCell(TDM pattern
for dual Tx UE)

tdm-restrictionDualTX-FDD-endc-r16 ENUMERATED {supported} OPTIONAL

}

MRDC-Parameters-v1630 ::= SEQUENCE {

\-- R4 2-20 Maximum uplink duty cycle for FDD+TDD EN-DC power class 2

maxUplinkDutyCycle-interBandENDC-FDD-TDD-PC2-r16 SEQUENCE {

maxUplinkDutyCycle-FDD-TDD-EN-DC1-r16 ENUMERATED {n30, n40, n50, n60,
n70, n80, n90, n100} OPTIONAL,

maxUplinkDutyCycle-FDD-TDD-EN-DC2-r16 ENUMERATED {n30, n40, n50, n60,
n70, n80, n90, n100} OPTIONAL

} OPTIONAL,

\-- R4 2-19 FDD-FDD or TDD-TDD inter-band MR-DC with overlapping or
partially overlapping DL spectrum

interBandMRDC-WithOverlapDL-Bands-r16 ENUMERATED {supported} OPTIONAL

}

MRDC-Parameters-v1700 ::= SEQUENCE {

condPSCellAdditionENDC-r17 ENUMERATED {supported} OPTIONAL,

scg-ActivationDeactivationENDC-r17 ENUMERATED {supported} OPTIONAL,

scg-ActivationDeactivationResumeENDC-r17 ENUMERATED {supported} OPTIONAL

}

MRDC-Parameters-v1770 ::= SEQUENCE {

\-- R4 26-1: Higher Power Limit CA DC

higherPowerLimitMRDC-r17 ENUMERATED {supported} OPTIONAL

}

MRDC-Parameters-v1790 ::= SEQUENCE {

intraBandENDC-Support-v1790 ENUMERATED {non-contiguous, both} OPTIONAL,

intraBandENDC-Support-UL-v1790 ENUMERATED {non-contiguous, both}
OPTIONAL

}

MRDC-Parameters-v1840 ::= SEQUENCE {

intraBandENDC-NominalSpacing-r18 ENUMERATED {supported} OPTIONAL

}

\-- TAG-MRDC-PARAMETERS-STOP

\-- ASN1STOP

#### -- *NCR-Parameters*

The IE *NCR-Parameters* is used to indicate the UE capabilities
supported by NCR-MT.

*NCR-Parameters* information element

\-- ASN1START

\-- TAG-NCR-PARAMETERS-START

NCR-Parameters-r18::= SEQUENCE {

inactiveStateNCR-r18 ENUMERATED {supported} OPTIONAL,

supportedNumberOfDRBs-NCR-r18 ENUMERATED {n1,n16} OPTIONAL,

dummy ENUMERATED {supported} OPTIONAL

}

\-- TAG-NCR-PARAMETERS-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *NCR-Parameters* field descriptions                                   |
+=======================================================================+
| ***dummy***                                                           |
|                                                                       |
| The field is not used in the specification and the network ignores    |
| the received value.                                                   |
+-----------------------------------------------------------------------+

#### -- *NRDC-Parameters*

The IE *NRDC-Parameters* contains parameters specific to NR-DC, i.e.,
which are not applicable to NR SA.

*NRDC-Parameters* information element

\-- ASN1START

\-- TAG-NRDC-PARAMETERS-START

NRDC-Parameters ::= SEQUENCE {

measAndMobParametersNRDC MeasAndMobParametersMRDC OPTIONAL,

generalParametersNRDC GeneralParametersMRDC-XDD-Diff OPTIONAL,

fdd-Add-UE-NRDC-Capabilities UE-MRDC-CapabilityAddXDD-Mode OPTIONAL,

tdd-Add-UE-NRDC-Capabilities UE-MRDC-CapabilityAddXDD-Mode OPTIONAL,

fr1-Add-UE-NRDC-Capabilities UE-MRDC-CapabilityAddFRX-Mode OPTIONAL,

fr2-Add-UE-NRDC-Capabilities UE-MRDC-CapabilityAddFRX-Mode OPTIONAL,

dummy2 OCTET STRING OPTIONAL,

dummy SEQUENCE {} OPTIONAL

}

NRDC-Parameters-v1570 ::= SEQUENCE {

sfn-SyncNRDC ENUMERATED {supported} OPTIONAL

}

NRDC-Parameters-v15c0 ::= SEQUENCE {

pdcp-DuplicationSplitSRB ENUMERATED {supported} OPTIONAL,

pdcp-DuplicationSplitDRB ENUMERATED {supported} OPTIONAL

}

NRDC-Parameters-v1610 ::= SEQUENCE {

measAndMobParametersNRDC-v1610 MeasAndMobParametersMRDC-v1610 OPTIONAL

}

NRDC-Parameters-v1700 ::= SEQUENCE {

f1c-OverNR-RRC-r17 ENUMERATED {supported} OPTIONAL,

measAndMobParametersNRDC-v1700 MeasAndMobParametersMRDC-v1700

}

\-- TAG-NRDC-PARAMETERS-STOP

\-- ASN1STOP

#### -- *NTN-Parameters*

The IE *NTN-Parameters* is used to convey the subset of UE Radio Access
Capability Parameters that apply to NTN access when there is a
difference compared to TN access.

*NTN-Parameters* information element

\-- ASN1START

\-- TAG-NTN-PARAMETERS-START

NTN-Parameters-r17 ::= SEQUENCE {

inactiveStateNTN-r17 ENUMERATED {supported} OPTIONAL,

ra-SDT-NTN-r17 ENUMERATED {supported} OPTIONAL,

srb-SDT-NTN-r17 ENUMERATED {supported} OPTIONAL,

measAndMobParametersNTN-r17 MeasAndMobParameters OPTIONAL,

mac-ParametersNTN-r17 MAC-Parameters OPTIONAL,

phy-ParametersNTN-r17 Phy-Parameters OPTIONAL,

fdd-Add-UE-NR-CapabilitiesNTN-r17 UE-NR-CapabilityAddXDD-Mode OPTIONAL,

fr1-Add-UE-NR-CapabilitiesNTN-r17 UE-NR-CapabilityAddFRX-Mode OPTIONAL,

ue-BasedPerfMeas-ParametersNTN-r17 UE-BasedPerfMeas-Parameters-r16
OPTIONAL,

son-ParametersNTN-r17 SON-Parameters-r16 OPTIONAL

}

NTN-Parameters-v1820 ::= SEQUENCE {

fr2-Add-UE-NR-CapabilitiesNTN-r18 UE-NR-CapabilityAddFRX-Mode OPTIONAL

}

\-- TAG-NTN-PARAMETERS-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *NTN-Parameters* field descriptions                                   |
+=======================================================================+
| ***fdd-Add-UE-NR-CapabilitiesNTN***                                   |
|                                                                       |
| NTN related capabilities which the UE supports in NTN differently     |
| than in TN. If absent, *fdd-Add-UE-NR-Capabilities* applies to NTN.   |
+-----------------------------------------------------------------------+
| ***fr1-Add-UE-NR-CapabilitiesNTN***                                   |
|                                                                       |
| NTN related capabilities which the UE supports in NTN differently     |
| than in TN. If absent, *fr1-Add-UE-NR-Capabilities* applies to NTN.   |
+-----------------------------------------------------------------------+
| ***fr2-Add-UE-NR-CapabilitiesNTN***                                   |
|                                                                       |
| NTN related capabilities which the UE supports in NTN differently     |
| than in TN. If absent, *fr2-Add-UE-NR-Capabilities* applies to NTN.   |
| This field is not used in this release of specification.              |
+-----------------------------------------------------------------------+
| ***mac-ParametersNTN***                                               |
|                                                                       |
| NTN related capabilities which the UE supports in NTN differently     |
| than in TN. If absent, *mac-Parameters* applies to NTN.               |
+-----------------------------------------------------------------------+
| ***measAndMobParametersNTN***                                         |
|                                                                       |
| NTN related capabilities which the UE supports in NTN differently     |
| than in TN. If absent, *measAndMobParameters* applies to NTN.         |
+-----------------------------------------------------------------------+
| ***phy-ParametersNTN***                                               |
|                                                                       |
| NTN related capabilities which the UE supports in NTN differently     |
| than in TN. If absent, *phy-Parameters* applies to NTN.               |
+-----------------------------------------------------------------------+
| ***son-ParametersNTN***                                               |
|                                                                       |
| NTN related capabilities which the UE supports in NTN differently     |
| than in TN. If absent, *son-Parameters-r16* applies to NTN.           |
+-----------------------------------------------------------------------+
| ***ue-BasedPerfMeas-ParametersNTN***                                  |
|                                                                       |
| NTN related capabilities which the UE supports in NTN differently     |
| than in TN. If absent, *ue-BasedPerfMeas-Parameters-r16* applies to   |
| NTN.                                                                  |
+-----------------------------------------------------------------------+

#### -- *OLPC-SRS-Pos*

The IE *OLPC-SRS-Pos* is used to convey OLPC SRS positioning related
parameters specific for a certain band.

*OLPC-SRS-Pos* information element

\-- ASN1START

\-- TAG-OLPC-SRS-POS-START

OLPC-SRS-Pos-r16 ::= SEQUENCE {

olpc-SRS-PosBasedOnPRS-Serving-r16 ENUMERATED {supported} OPTIONAL,

olpc-SRS-PosBasedOnSSB-Neigh-r16 ENUMERATED {supported} OPTIONAL,

olpc-SRS-PosBasedOnPRS-Neigh-r16 ENUMERATED {supported} OPTIONAL,

maxNumberPathLossEstimatePerServing-r16 ENUMERATED {n1, n4, n8, n16}
OPTIONAL

}

\--TAG-OLPC-SRS-POS-STOP

\-- ASN1STOP

#### -- *PDCP-Parameters*

The IE *PDCP-Parameters* is used to convey capabilities related to PDCP.

*PDCP-Parameters* information element

\-- ASN1START

\-- TAG-PDCP-PARAMETERS-START

PDCP-Parameters ::= SEQUENCE {

supportedROHC-Profiles SEQUENCE {

profile0x0000 BOOLEAN,

profile0x0001 BOOLEAN,

profile0x0002 BOOLEAN,

profile0x0003 BOOLEAN,

profile0x0004 BOOLEAN,

profile0x0006 BOOLEAN,

profile0x0101 BOOLEAN,

profile0x0102 BOOLEAN,

profile0x0103 BOOLEAN,

profile0x0104 BOOLEAN

},

maxNumberROHC-ContextSessions ENUMERATED {cs2, cs4, cs8, cs12, cs16,
cs24, cs32, cs48, cs64,

cs128, cs256, cs512, cs1024, cs16384, spare2, spare1},

uplinkOnlyROHC-Profiles ENUMERATED {supported} OPTIONAL,

continueROHC-Context ENUMERATED {supported} OPTIONAL,

outOfOrderDelivery ENUMERATED {supported} OPTIONAL,

shortSN ENUMERATED {supported} OPTIONAL,

pdcp-DuplicationSRB ENUMERATED {supported} OPTIONAL,

pdcp-DuplicationMCG-OrSCG-DRB ENUMERATED {supported} OPTIONAL,

\...,

\[\[

drb-IAB-r16 ENUMERATED {supported} OPTIONAL,

non-DRB-IAB-r16 ENUMERATED {supported} OPTIONAL,

extendedDiscardTimer-r16 ENUMERATED {supported} OPTIONAL,

continueEHC-Context-r16 ENUMERATED {supported} OPTIONAL,

ehc-r16 ENUMERATED {supported} OPTIONAL,

maxNumberEHC-Contexts-r16 ENUMERATED {cs2, cs4, cs8, cs16, cs32, cs64,
cs128, cs256, cs512,

cs1024, cs2048, cs4096, cs8192, cs16384, cs32768, cs65536} OPTIONAL,

jointEHC-ROHC-Config-r16 ENUMERATED {supported} OPTIONAL,

pdcp-DuplicationMoreThanTwoRLC-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

longSN-RedCap-r17 ENUMERATED {supported} OPTIONAL,

udc-r17 SEQUENCE {

standardDictionary-r17 ENUMERATED {supported} OPTIONAL,

operatorDictionary-r17 SEQUENCE {

versionOfDictionary-r17 INTEGER (0..15),

associatedPLMN-ID-r17 PLMN-Identity

} OPTIONAL,

continueUDC-r17 ENUMERATED {supported} OPTIONAL,

supportOfBufferSize-r17 ENUMERATED {kbyte4, kbyte8} OPTIONAL

} OPTIONAL

\]\],

\[\[

longSN-NCR-r18 ENUMERATED {supported} OPTIONAL,

supportOfPDU-SetDiscard-r18 ENUMERATED {supported} OPTIONAL,

psi-BasedDiscard-r18 ENUMERATED {supported} OPTIONAL,

supportOfSN-GapReport-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

\-- TAG-PDCP-PARAMETERS-STOP

\-- ASN1STOP

#### -- *PDCP-ParametersMRDC*

The IE *PDCP-ParametersMRDC* is used to convey PDCP related capabilities
for MR-DC.

*PDCP-ParametersMRDC* information element

\-- ASN1START

\-- TAG-PDCP-PARAMETERSMRDC-START

PDCP-ParametersMRDC ::= SEQUENCE {

pdcp-DuplicationSplitSRB ENUMERATED {supported} OPTIONAL,

pdcp-DuplicationSplitDRB ENUMERATED {supported} OPTIONAL

}

PDCP-ParametersMRDC-v1610 ::= SEQUENCE {

scg-DRB-NR-IAB-r16 ENUMERATED {supported} OPTIONAL

}

\-- TAG-PDCP-PARAMETERSMRDC-STOP

\-- ASN1STOP

#### -- *Phy-Parameters*

The IE *Phy-Parameters* is used to convey the physical layer
capabilities.

*Phy-Parameters* information element

\-- ASN1START

\-- TAG-PHY-PARAMETERS-START

Phy-Parameters ::= SEQUENCE {

phy-ParametersCommon Phy-ParametersCommon OPTIONAL,

phy-ParametersXDD-Diff Phy-ParametersXDD-Diff OPTIONAL,

phy-ParametersFRX-Diff Phy-ParametersFRX-Diff OPTIONAL,

phy-ParametersFR1 Phy-ParametersFR1 OPTIONAL,

phy-ParametersFR2 Phy-ParametersFR2 OPTIONAL

}

Phy-Parameters-v16a0 ::= SEQUENCE {

phy-ParametersCommon-v16a0 Phy-ParametersCommon-v16a0 OPTIONAL

}

Phy-ParametersCommon ::= SEQUENCE {

csi-RS-CFRA-ForHO ENUMERATED {supported} OPTIONAL,

dynamicPRB-BundlingDL ENUMERATED {supported} OPTIONAL,

sp-CSI-ReportPUCCH ENUMERATED {supported} OPTIONAL,

sp-CSI-ReportPUSCH ENUMERATED {supported} OPTIONAL,

nzp-CSI-RS-IntefMgmt ENUMERATED {supported} OPTIONAL,

type2-SP-CSI-Feedback-LongPUCCH ENUMERATED {supported} OPTIONAL,

precoderGranularityCORESET ENUMERATED {supported} OPTIONAL,

dynamicHARQ-ACK-Codebook ENUMERATED {supported} OPTIONAL,

semiStaticHARQ-ACK-Codebook ENUMERATED {supported} OPTIONAL,

spatialBundlingHARQ-ACK ENUMERATED {supported} OPTIONAL,

dynamicBetaOffsetInd-HARQ-ACK-CSI ENUMERATED {supported} OPTIONAL,

pucch-Repetition-F1-3-4 ENUMERATED {supported} OPTIONAL,

ra-Type0-PUSCH ENUMERATED {supported} OPTIONAL,

dynamicSwitchRA-Type0-1-PDSCH ENUMERATED {supported} OPTIONAL,

dynamicSwitchRA-Type0-1-PUSCH ENUMERATED {supported} OPTIONAL,

pdsch-MappingTypeA ENUMERATED {supported} OPTIONAL,

pdsch-MappingTypeB ENUMERATED {supported} OPTIONAL,

interleavingVRB-ToPRB-PDSCH ENUMERATED {supported} OPTIONAL,

interSlotFreqHopping-PUSCH ENUMERATED {supported} OPTIONAL,

type1-PUSCH-RepetitionMultiSlots ENUMERATED {supported} OPTIONAL,

type2-PUSCH-RepetitionMultiSlots ENUMERATED {supported} OPTIONAL,

pusch-RepetitionMultiSlots ENUMERATED {supported} OPTIONAL,

pdsch-RepetitionMultiSlots ENUMERATED {supported} OPTIONAL,

downlinkSPS ENUMERATED {supported} OPTIONAL,

configuredUL-GrantType1 ENUMERATED {supported} OPTIONAL,

configuredUL-GrantType2 ENUMERATED {supported} OPTIONAL,

pre-EmptIndication-DL ENUMERATED {supported} OPTIONAL,

cbg-TransIndication-DL ENUMERATED {supported} OPTIONAL,

cbg-TransIndication-UL ENUMERATED {supported} OPTIONAL,

cbg-FlushIndication-DL ENUMERATED {supported} OPTIONAL,

dynamicHARQ-ACK-CodeB-CBG-Retx-DL ENUMERATED {supported} OPTIONAL,

rateMatchingResrcSetSemi-Static ENUMERATED {supported} OPTIONAL,

rateMatchingResrcSetDynamic ENUMERATED {supported} OPTIONAL,

bwp-SwitchingDelay ENUMERATED {type1, type2} OPTIONAL,

\...,

\[\[

dummy ENUMERATED {supported} OPTIONAL

\]\],

\[\[

maxNumberSearchSpaces ENUMERATED {n10} OPTIONAL,

rateMatchingCtrlResrcSetDynamic ENUMERATED {supported} OPTIONAL,

maxLayersMIMO-Indication ENUMERATED {supported} OPTIONAL

\]\],

\[\[

spCellPlacement CarrierAggregationVariant OPTIONAL

\]\],

\[\[

\-- R1 9-1: Basic channel structure and procedure of 2-step RACH

twoStepRACH-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-1: Monitoring DCI format 1_2 and DCI format 0_2

dci-Format1-2And0-2-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-1a: Monitoring both DCI format 0_1/1_1 and DCI format 0_2/1_2
in the same search space

monitoringDCI-SameSearchSpace-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-10: Type 2 configured grant release by DCI format 0_1

type2-CG-ReleaseDCI-0-1-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-11: Type 2 configured grant release by DCI format 0_2

type2-CG-ReleaseDCI-0-2-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 12-3: SPS release by DCI format 1_1

sps-ReleaseDCI-1-1-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 12-3a: SPS release by DCI format 1_2

sps-ReleaseDCI-1-2-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 14-8: CSI trigger states containing non-active BWP

csi-TriggerStateNon-ActiveBWP-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 20-2: Support up to 4 SMTCs configured for an IAB node MT per
frequency location, including IAB-specific SMTC window periodicities

separateSMTC-InterIAB-Support-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 20-3: Support RACH configuration separately from the RACH
configuration for UE access, including new IAB-specific offset and
scaling factors

separateRACH-IAB-Support-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 20-5a: Support semi-static configuration/indication of
UL-Flexible-DL slot formats for IAB-MT resources

ul-flexibleDL-SlotFormatSemiStatic-IAB-r16 ENUMERATED {supported}
OPTIONAL,

\-- R1 20-5b: Support dynamic indication of UL-Flexible-DL slot formats
for IAB-MT resources

ul-flexibleDL-SlotFormatDynamics-IAB-r16 ENUMERATED {supported}
OPTIONAL,

dft-S-OFDM-WaveformUL-IAB-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 20-6: Support DCI Format 2_5 based indication of soft resource
availability to an IAB node

dci-25-AI-RNTI-Support-IAB-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 20-7: Support T_delta reception.

t-DeltaReceptionSupport-IAB-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 20-8: Support of Desired guard symbol reporting and provided
guard symbok reception.

guardSymbolReportReception-IAB-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 18-8 HARQ-ACK codebook type and spatial bundling per PUCCH group

harqACK-CB-SpatialBundlingPUCCH-Group-r16 ENUMERATED {supported}
OPTIONAL,

\-- R1 19-2: Cross Slot Scheduling

crossSlotScheduling-r16 SEQUENCE {

non-SharedSpectrumChAccess-r16 ENUMERATED {supported} OPTIONAL,

sharedSpectrumChAccess-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

maxNumberSRS-PosPathLossEstimateAllServingCells-r16 ENUMERATED {n1, n4,
n8, n16} OPTIONAL,

extendedCG-Periodicities-r16 ENUMERATED {supported} OPTIONAL,

extendedSPS-Periodicities-r16 ENUMERATED {supported} OPTIONAL,

codebookVariantsList-r16 CodebookVariantsList-r16 OPTIONAL,

\-- R1 11-6: PUSCH repetition Type A

pusch-RepetitionTypeA-r16 SEQUENCE {

sharedSpectrumChAccess-r16 ENUMERATED {supported} OPTIONAL,

non-SharedSpectrumChAccess-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- R1 11-4b: DL priority indication in DCI with mixed DCI formats

dci-DL-PriorityIndicator-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 12-1a: UL priority indication in DCI with mixed DCI formats

dci-UL-PriorityIndicator-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-1e: Maximum number of configured pathloss reference RSs for
PUSCH/PUCCH/SRS by RRC for MAC-CE based pathloss reference RS update

maxNumberPathlossRS-Update-r16 ENUMERATED {n4, n8, n16, n32, n64}
OPTIONAL,

\-- R1 18-9: Usage of the PDSCH starting time for HARQ-ACK type 2
codebook

type2-HARQ-ACK-Codebook-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-1g-1: Resources for beam management, pathloss measurement,
BFD, RLM and new beam identification across frequency ranges

maxTotalResourcesForAcrossFreqRanges-r16 SEQUENCE {

maxNumberResWithinSlotAcrossCC-AcrossFR-r16 ENUMERATED {n2, n4, n8, n12,
n16, n32, n64, n128} OPTIONAL,

maxNumberResAcrossCC-AcrossFR-r16 ENUMERATED {n2, n4, n8, n12, n16, n32,
n40, n48, n64, n72, n80, n96, n128, n256}

OPTIONAL

} OPTIONAL,

\-- R1 16-2a-4: HARQ-ACK for multi-DCI based multi-TRP - separate

harqACK-separateMultiDCI-MultiTRP-r16 SEQUENCE {

maxNumberLongPUCCHs-r16 ENUMERATED {longAndLong, longAndShort,
shortAndShort} OPTIONAL

} OPTIONAL,

\-- R1 16-2a-4: HARQ-ACK for multi-DCI based multi-TRP - joint

harqACK-jointMultiDCI-MultiTRP-r16 ENUMERATED {supported} OPTIONAL,

\-- R4 9-1: BWP switching on multiple CCs RRM requirements

bwp-SwitchingMultiCCs-r16 CHOICE {

type1-r16 ENUMERATED {us100, us200},

type2-r16 ENUMERATED {us200, us400, us800, us1000}

} OPTIONAL

\]\],

\[\[

targetSMTC-SCG-r16 ENUMERATED {supported} OPTIONAL,

supportRepetitionZeroOffsetRV-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-12: in-order CBG-based re-transmission

cbg-TransInOrderPUSCH-UL-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R4 6-3: Dormant BWP switching on multiple CCs RRM requirements

bwp-SwitchingMultiDormancyCCs-r16 CHOICE {

type1-r16 ENUMERATED {us100, us200},

type2-r16 ENUMERATED {us200, us400, us800, us1000}

} OPTIONAL,

\-- R1 16-2a-8: Indicates that retransmission scheduled by a different
CORESETPoolIndex for multi-DCI multi-TRP is not supported.

supportRetx-Diff-CoresetPool-Multi-DCI-TRP-r16 ENUMERATED {notSupported}
OPTIONAL,

\-- R1 22-10: Support of pdcch-MonitoringAnyOccasionsWithSpanGap in case
of cross-carrier scheduling with different SCSs

pdcch-MonitoringAnyOccasionsWithSpanGapCrossCarrierSch-r16 ENUMERATED
{mode2, mode3} OPTIONAL

\]\],

\[\[

\-- R1 16-1j-1: Support of 2 port CSI-RS for new beam identification

newBeamIdentifications2PortCSI-RS-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-1j-2: Support of 2 port CSI-RS for pathloss estimation

pathlossEstimation2PortCSI-RS-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

mux-HARQ-ACK-withoutPUCCH-onPUSCH-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 31-1: Support of Desired Guard Symbol reporting and provided
guard symbol reception.

guardSymbolReportReception-IAB-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 31-2: support of restricted IAB-DU beam reception

restricted-IAB-DU-BeamReception-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 31-3: support of recommended IAB-MT beam transmission for DL and
UL beam

recommended-IAB-MT-BeamTransmission-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 31-4: support of case 6 timing alignment indication reception

case6-TimingAlignmentReception-IAB-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 31-5: support of case 7 timing offset indication reception and
case 7 timing at parent-node indication reception

case7-TimingAlignmentReception-IAB-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 31-6: support of desired DL Tx power adjustment reporting and DL
Tx power adjustment reception

dl-tx-PowerAdjustment-IAB-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 31-7: support of desired IAB-MT PSD range reporting

desired-ul-tx-PowerAdjustment-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 31-8: support of monitoring DCI Format 2_5 scrambled by AI-RNTI
for indication of FDM soft resource availability to an IAB node

fdm-SoftResourceAvailability-DynamicIndication-r17 ENUMERATED{supported}
OPTIONAL,

\-- R1 31-10: Support of updated T_delta range reception

updated-T-DeltaRangeReception-r17 ENUMERATED{supported} OPTIONAL,

\-- R1 30-5: Support slot based dynamic PUCCH repetition indication for
PUCCH formats 0/1/2/3/4

slotBasedDynamicPUCCH-Rep-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 25-1: Support of HARQ-ACK deferral in case of TDD collision

sps-HARQ-ACK-Deferral-r17 SEQUENCE {

non-SharedSpectrumChAccess-r17 ENUMERATED {supported} OPTIONAL,

sharedSpectrumChAccess-r17 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- R1 23-1-1k Maximum number of configured CC lists (per UE)

unifiedJointTCI-commonUpdate-r17 INTEGER (1..4) OPTIONAL,

\-- R1 23-2-1c PDCCH repetition with a single span of three contiguous
OFDM symbols that is within the first four OFDM symbols in a slot

mTRP-PDCCH-singleSpan-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 27-23: Support of more than one activated PRS processing windows
across all active DL BWPs

supportedActivatedPRS-ProcessingWindow-r17 ENUMERATED {n2, n3, n4}
OPTIONAL,

cg-TimeDomainAllocationExtension-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 25-20: Propagation delay compensation based on Rel-15 TA
procedure for TN and licensed

ta-BasedPDC-TN-NonSharedSpectrumChAccess-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 31-11: Directional Collision Handling in DC operation

directionalCollisionDC-IAB-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

dummy1 ENUMERATED {supported} OPTIONAL,

dummy2 ENUMERATED {supported} OPTIONAL,

dummy3 ENUMERATED {supported} OPTIONAL,

dummy4 ENUMERATED {supported} OPTIONAL,

srs-AdditionalRepetition-r17 ENUMERATED {supported} OPTIONAL,

pusch-Repetition-CG-SDT-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

multiPDSCH-PerSlotType1-CB-Support-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 42-6: Joint operation of power domain and spatial domain
adaptation

jointPowerSpatialAdaptation-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 43-3: Aperiodic beam indication for access link

ncr-AperiodicBeamInd-AccessLink-r18 SEQUENCE {

scs-15kHz-r18 INTEGER (0..1) OPTIONAL,

scs-30kHz-r18 INTEGER (0..1) OPTIONAL,

scs-60kHz-r18 INTEGER (0..2) OPTIONAL,

scs-120kHz-r18 INTEGER (0..2) OPTIONAL

} OPTIONAL,

\-- R1 43-4: Semi-persistent beam indication for access link

ncr-Semi-PersistentBeamInd-AccessLink-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 43-5: Simulatenous UL transmission of backhaul link and C-Link

ncr-SimultaneousUL-BackhaulAndC-Link-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 43-6: Dedicated signalling for backhaul link beam indication

ncr-BackhaulBeamInd-r18 ENUMERATED {nonUnifiedTCI, unifiedTCI, both}
OPTIONAL,

\-- R1 43-8: Adaptive beam for NCR backhaul link/C-link

ncr-AdaptiveBeamBackhaulAndC-Link-r18 ENUMERATED {nonUnifiedTCI,
unifiedTCI, both} OPTIONAL,

\-- R1 49-4a: Nominal RBG size of Configuration 3 for FDRA type 0 for
DCI format 1_3

nominalRBG-SizeOfConfig-3-FDRA-Type-0-DCI-1-3-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 49-4b: Nominal RBG size of Configuration 3 for FDRA type 0 for
DCI format 0_3

nominalRBG-SizeOfConfig-3-FDRA-Type-0-DCI-0-3-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 49-4c: Configurable Type-1A fields for DCI format 0_3/1_3

configurableType-1A-FieldsForDCI-0-3-And-1-3-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 49-4d: FDRA Type 1 granularity of 2, 4, 8, or 16 consecutive RBs
based RIV for DCI format 1_3/0_3

fdra-Type-1-Gty-2-4-8-16-RBs-RIV-DCI-1-3-And-0-3-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 49-6b: DL priority indication in DCI with mixed DCI formats
including DCI format 1_3

priorityIndicationDL-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 49-7a: UL priority indication in DCI with mixed DCI formats
including DCI format 0_3

priorityIndicationUL-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 49-10: Dynamic indication of applicable minimum scheduling
restriction by DCI format 0_3/1_3

dynamicIndicationSchedulingRestriction-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 49-11: PHY priority indication for one-shot HARQ-ACK feedback
triggered by DCI format 1_3

priorityIndicationOneSlotHARQ-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 50-1c: Multi-PUSCHs Type 2 configured grant release by DCI format
0_1

multiPUSCH-DCI-0-1-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 50-1d: Multi-PUSCHs Type 2 configured grant release by DCI format
0_2

multiPUSCH-DCI-0-2-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 55-1: Additional SR periodicities

additionalSR-Periodicities-r18 SEQUENCE {

scs-30kHz-r18 ENUMERATED {supported} OPTIONAL,

scs-120kHz-r18 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- R1 55-5: Enable MAC CE based pathloss RS updates for Type 1 CG-PUSCH

pathlossRS-UpdateForType1CG-PUSCH-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 38-9: Dormant BWP switching on multiple CCs RRM requirements with
DCI 0-3/1-3

bwp-SwitchingMultiDormancyCC-DCI-0-3-And-1-3-r18 CHOICE {

type1-r18 ENUMERATED {us100, us200},

type2-r18 ENUMERATED {us200, us400, us800, us1000}

} OPTIONAL

\]\],

\[\[

ncr-dft-S-OFDM-WaveformUL-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

Phy-ParametersCommon-v16a0 ::= SEQUENCE {

srs-PeriodicityAndOffsetExt-r16 ENUMERATED {supported} OPTIONAL

}

Phy-ParametersXDD-Diff ::= SEQUENCE {

dynamicSFI ENUMERATED {supported} OPTIONAL,

twoPUCCH-F0-2-ConsecSymbols ENUMERATED {supported} OPTIONAL,

twoDifferentTPC-Loop-PUSCH ENUMERATED {supported} OPTIONAL,

twoDifferentTPC-Loop-PUCCH ENUMERATED {supported} OPTIONAL,

\...,

\[\[

dl-SchedulingOffset-PDSCH-TypeA ENUMERATED {supported} OPTIONAL,

dl-SchedulingOffset-PDSCH-TypeB ENUMERATED {supported} OPTIONAL,

ul-SchedulingOffset ENUMERATED {supported} OPTIONAL

\]\]

}

Phy-ParametersFRX-Diff ::= SEQUENCE {

dynamicSFI ENUMERATED {supported} OPTIONAL,

dummy1 BIT STRING (SIZE (2)) OPTIONAL,

twoFL-DMRS BIT STRING (SIZE (2)) OPTIONAL,

dummy2 BIT STRING (SIZE (2)) OPTIONAL,

dummy3 BIT STRING (SIZE (2)) OPTIONAL,

supportedDMRS-TypeDL ENUMERATED {type1, type1And2} OPTIONAL,

supportedDMRS-TypeUL ENUMERATED {type1, type1And2} OPTIONAL,

semiOpenLoopCSI ENUMERATED {supported} OPTIONAL,

csi-ReportWithoutPMI ENUMERATED {supported} OPTIONAL,

csi-ReportWithoutCQI ENUMERATED {supported} OPTIONAL,

onePortsPTRS BIT STRING (SIZE (2)) OPTIONAL,

twoPUCCH-F0-2-ConsecSymbols ENUMERATED {supported} OPTIONAL,

pucch-F2-WithFH ENUMERATED {supported} OPTIONAL,

pucch-F3-WithFH ENUMERATED {supported} OPTIONAL,

pucch-F4-WithFH ENUMERATED {supported} OPTIONAL,

pucch-F0-2WithoutFH ENUMERATED {notSupported} OPTIONAL,

pucch-F1-3-4WithoutFH ENUMERATED {notSupported} OPTIONAL,

mux-SR-HARQ-ACK-CSI-PUCCH-MultiPerSlot ENUMERATED {supported} OPTIONAL,

uci-CodeBlockSegmentation ENUMERATED {supported} OPTIONAL,

onePUCCH-LongAndShortFormat ENUMERATED {supported} OPTIONAL,

twoPUCCH-AnyOthersInSlot ENUMERATED {supported} OPTIONAL,

intraSlotFreqHopping-PUSCH ENUMERATED {supported} OPTIONAL,

pusch-LBRM ENUMERATED {supported} OPTIONAL,

pdcch-BlindDetectionCA INTEGER (4..16) OPTIONAL,

tpc-PUSCH-RNTI ENUMERATED {supported} OPTIONAL,

tpc-PUCCH-RNTI ENUMERATED {supported} OPTIONAL,

tpc-SRS-RNTI ENUMERATED {supported} OPTIONAL,

absoluteTPC-Command ENUMERATED {supported} OPTIONAL,

twoDifferentTPC-Loop-PUSCH ENUMERATED {supported} OPTIONAL,

twoDifferentTPC-Loop-PUCCH ENUMERATED {supported} OPTIONAL,

pusch-HalfPi-BPSK ENUMERATED {supported} OPTIONAL,

pucch-F3-4-HalfPi-BPSK ENUMERATED {supported} OPTIONAL,

almostContiguousCP-OFDM-UL ENUMERATED {supported} OPTIONAL,

sp-CSI-RS ENUMERATED {supported} OPTIONAL,

sp-CSI-IM ENUMERATED {supported} OPTIONAL,

tdd-MultiDL-UL-SwitchPerSlot ENUMERATED {supported} OPTIONAL,

multipleCORESET ENUMERATED {supported} OPTIONAL,

\...,

\[\[

csi-RS-IM-ReceptionForFeedback CSI-RS-IM-ReceptionForFeedback OPTIONAL,

csi-RS-ProcFrameworkForSRS CSI-RS-ProcFrameworkForSRS OPTIONAL,

csi-ReportFramework CSI-ReportFramework OPTIONAL,

mux-SR-HARQ-ACK-CSI-PUCCH-OncePerSlot SEQUENCE {

sameSymbol ENUMERATED {supported} OPTIONAL,

diffSymbol ENUMERATED {supported} OPTIONAL

} OPTIONAL,

mux-SR-HARQ-ACK-PUCCH ENUMERATED {supported} OPTIONAL,

mux-MultipleGroupCtrlCH-Overlap ENUMERATED {supported} OPTIONAL,

dl-SchedulingOffset-PDSCH-TypeA ENUMERATED {supported} OPTIONAL,

dl-SchedulingOffset-PDSCH-TypeB ENUMERATED {supported} OPTIONAL,

ul-SchedulingOffset ENUMERATED {supported} OPTIONAL,

dl-64QAM-MCS-TableAlt ENUMERATED {supported} OPTIONAL,

ul-64QAM-MCS-TableAlt ENUMERATED {supported} OPTIONAL,

cqi-TableAlt ENUMERATED {supported} OPTIONAL,

oneFL-DMRS-TwoAdditionalDMRS-UL ENUMERATED {supported} OPTIONAL,

twoFL-DMRS-TwoAdditionalDMRS-UL ENUMERATED {supported} OPTIONAL,

oneFL-DMRS-ThreeAdditionalDMRS-UL ENUMERATED {supported} OPTIONAL

\]\],

\[\[

pdcch-BlindDetectionNRDC SEQUENCE {

pdcch-BlindDetectionMCG-UE INTEGER (1..15),

pdcch-BlindDetectionSCG-UE INTEGER (1..15)

} OPTIONAL,

mux-HARQ-ACK-PUSCH-DiffSymbol ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 11-1b: Type 1 HARQ-ACK codebook support for relative TDRA for DL

type1-HARQ-ACK-Codebook-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-8: Enhanced UL power control scheme

enhancedPowerControl-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-1b-1: TCI state activation across multiple CCs

simultaneousTCI-ActMultipleCC-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-1b-2: Spatial relation update across multiple CCs

simultaneousSpatialRelationMultipleCC-r16 ENUMERATED {supported}
OPTIONAL,

cli-RSSI-FDM-DL-r16 ENUMERATED {supported} OPTIONAL,

cli-SRS-RSRP-FDM-DL-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 19-3: Maximum MIMO Layer Adaptation

maxLayersMIMO-Adaptation-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 12-5: Configuration of aggregation factor per SPS configuration

aggregationFactorSPS-DL-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-1g: Resources for beam management, pathloss measurement, BFD,
RLM and new beam identification

maxTotalResourcesForOneFreqRange-r16 SEQUENCE {

maxNumberResWithinSlotAcrossCC-OneFR-r16 ENUMERATED {n2, n4, n8, n12,
n16, n32, n64, n128} OPTIONAL,

maxNumberResAcrossCC-OneFR-r16 ENUMERATED {n2, n4, n8, n12, n16, n32,
n40, n48, n64, n72, n80, n96, n128, n256}

OPTIONAL

} OPTIONAL,

\-- R1 16-7: Extension of the maximum number of configured aperiodic CSI
report settings

csi-ReportFrameworkExt-r16 CSI-ReportFrameworkExt-r16 OPTIONAL

\]\],

\[\[

twoTCI-Act-servingCellInCC-List-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 22-11: Support of \'cri-RI-CQI\' report without
non-PMI-PortIndication

cri-RI-CQI-WithoutNon-PMI-PortInd-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 25-11: 4-bits subband CQI for TN and licensed

cqi-4-BitsSubbandTN-NonSharedSpectrumChAccess-r17 ENUMERATED {supported}
OPTIONAL

\]\],

\[\[

multipleCORESET-RedCap-r17 ENUMERATED {supported} OPTIONAL

\]\]

}

Phy-ParametersFR1 ::= SEQUENCE {

pdcch-MonitoringSingleOccasion ENUMERATED {supported} OPTIONAL,

scs-60kHz ENUMERATED {supported} OPTIONAL,

pdsch-256QAM-FR1 ENUMERATED {supported} OPTIONAL,

pdsch-RE-MappingFR1-PerSymbol ENUMERATED {n10, n20} OPTIONAL,

\...,

\[\[

pdsch-RE-MappingFR1-PerSlot ENUMERATED {n16, n32, n48, n64, n80, n96,
n112, n128,

n144, n160, n176, n192, n208, n224, n240, n256} OPTIONAL

\]\],

\[\[

\-- R1 22-12: PDCCH monitoring with a single span of three contiguous
OFDM symbols that is within the first four OFDM symbols in a

\-- slot

pdcch-MonitoringSingleSpanFirst4Sym-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 56-4: K1 range extension defined for ATG as well

k1-RangeExtensionATG-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 56-3: Increasing the number of HARQ processes defined for ATG as
well

maxHARQ-ProcessNumberATG-r18 ENUMERATED {u16d32, u32d16, u32d32}
OPTIONAL,

\-- R1 56-1: Uplink Time and Frequency pre-compensation and timing
relationship enhancements defined for ATG as well

uplinkPreCompensationATG-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 56-2: UE reporting of TA information

uplinkTA-ReportingATG-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 36-1: MU-MIMO Interference Mitigation advanced receiver

advReceiver-MU-MIMO-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 41-1: Support of delta PPowerClass reporting mechanism

deltaPowerClassReporting-r18 ENUMERATED {type1, type2} OPTIONAL,

\-- R1 51-2b: Support 12 PRB CORESET0 with an associated SS/PBCH block
located at GSCN 41637

support12PRB-CORESET0-GSCN-41637-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 51-3: Support 5 MHz channel bandwidth with 20 PRB CORESET0

support5MHz-ChannelBW-20PRB-CORESET0-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

Phy-ParametersFR2 ::= SEQUENCE {

dummy ENUMERATED {supported} OPTIONAL,

pdsch-RE-MappingFR2-PerSymbol ENUMERATED {n6, n20} OPTIONAL,

\...,

\[\[

pCell-FR2 ENUMERATED {supported} OPTIONAL,

pdsch-RE-MappingFR2-PerSlot ENUMERATED {n16, n32, n48, n64, n80, n96,
n112, n128,

n144, n160, n176, n192, n208, n224, n240, n256} OPTIONAL

\]\],

\[\[

\-- R1 16-1c: Support of default spatial relation and pathloss reference
RS for dedicated-PUCCH/SRS and PUSCH

defaultSpatialRelationPathlossRS-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 16-1d: Support of spatial relation update for AP-SRS via MAC CE

spatialRelationUpdateAP-SRS-r16 ENUMERATED {supported} OPTIONAL,

maxNumberSRS-PosSpatialRelationsAllServingCells-r16 ENUMERATED {n0, n1,
n2, n4, n8, n16} OPTIONAL

\]\],

\[\[

\-- R4 30-3: Supports Indication of multi-Rx operation preference

multiRxPreferenceIndication-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

\-- TAG-PHY-PARAMETERS-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *Phy-ParametersFRX-Diff* field descriptions                           |
+=======================================================================+
| ***csi-RS-IM-ReceptionForFeedback/ csi-RS-ProcFrameworkForSRS/        |
| csi-ReportFramework***                                                |
|                                                                       |
| These fields are optionally present in                                |
| *fr1-fr2-Add-UE-NR-Capabilities* in *UE-NR-Capability*. They shall    |
| not be set in any other instance of the IE *Phy-ParametersFRX-Diff*.  |
| If the network configures the UE with serving cells on both FR1 and   |
| FR2 bands, these parameters, if present, limit the corresponding      |
| parameters in *MIMO-ParametersPerBand*.                               |
+-----------------------------------------------------------------------+

#### -- *Phy-ParametersMRDC*

The IE *Phy-ParametersMRDC* is used to convey physical layer
capabilities for MR-DC.

*Phy-ParametersMRDC* information element

\-- ASN1START

\-- TAG-PHY-PARAMETERSMRDC-START

Phy-ParametersMRDC ::= SEQUENCE {

naics-Capability-List SEQUENCE (SIZE (1..maxNrofNAICS-Entries)) OF
NAICS-Capability-Entry OPTIONAL,

\...,

\[\[

spCellPlacement CarrierAggregationVariant OPTIONAL

\]\],

\[\[

\-- R1 18-3b: Semi-statically configured LTE UL transmissions in all UL
subframes not limited to tdm-pattern in case of TDD PCell

tdd-PCellUL-TX-AllUL-Subframe-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 18-3a: Semi-statically configured LTE UL transmissions in all UL
subframes not limited to tdm-pattern in case of FDD PCell

fdd-PCellUL-TX-AllUL-Subframe-r16 ENUMERATED {supported} OPTIONAL

\]\]

}

NAICS-Capability-Entry ::= SEQUENCE {

numberOfNAICS-CapableCC INTEGER(1..5),

numberOfAggregatedPRB ENUMERATED {n50, n75, n100, n125, n150, n175,
n200, n225,

n250, n275, n300, n350, n400, n450, n500, spare},

\...

}

\-- TAG-PHY-PARAMETERSMRDC-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *PHY-ParametersMRDC* field descriptions                               |
+=======================================================================+
| ***naics-Capability-List***                                           |
|                                                                       |
| Indicates that UE in MR-DC supports NAICS as defined in TS 36.331     |
| \[10\].                                                               |
+-----------------------------------------------------------------------+

#### -- *Phy-ParametersSharedSpectrumChAccess*

The IE *Phy-ParametersSharedSpectrumChAccess* is used to convey the
physical layer capabilities specific for shared spectrum channel access.

*Phy-ParametersSharedSpectrumChAccess* information element

\-- ASN1START

\-- TAG-PHY-PARAMETERSSHAREDSPECTRUMCHACCESS-START

Phy-ParametersSharedSpectrumChAccess-r16 ::= SEQUENCE {

\-- 10-32 (1-2): SS block based SINR measurement (SS-SINR) for
unlicensed spectrum

ss-SINR-Meas-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-33 (2-32a): Semi-persistent CSI report on PUCCH for unlicensed
spectrum

sp-CSI-ReportPUCCH-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-33a (2-32b): Semi-persistent CSI report on PUSCH for unlicensed
spectrum

sp-CSI-ReportPUSCH-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-34 (3-6): Dynamic SFI monitoring for unlicensed spectrum

dynamicSFI-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-35c (4-19c): SR/HARQ-ACK/CSI multiplexing once per slot using a
PUCCH (or HARQ-ACK/CSI piggybacked on a PUSCH) when SR/HARQ-

\-- ACK/CSI are supposed to be sent with different starting symbols in a
slot for unlicensed spectrum

\-- 10-35 (4-19): SR/HARQ-ACK/CSI multiplexing once per slot using a
PUCCH (or HARQ-ACK/CSI piggybacked on a PUSCH) when SR/HARQ-

\-- ACK/CSI are supposed to be sent with the same starting symbol on the
PUCCH resources in a slot for unlicensed spectrum

mux-SR-HARQ-ACK-CSI-PUCCH-OncePerSlot-r16 SEQUENCE {

sameSymbol-r16 ENUMERATED {supported} OPTIONAL,

diffSymbol-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\-- 10-35a (4-19a): Overlapping PUCCH resources have different starting
symbols in a slot for unlicensed spectrum

mux-SR-HARQ-ACK-PUCCH-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-35b (4-19b): SR/HARQ-ACK/CSI multiplexing more than once per slot
using a PUCCH (or HARQ-ACK/CSI piggybacked on a PUSCH) when

\-- SR/HARQ ACK/CSI are supposed to be sent with the same or different
starting symbol in a slot for unlicensed spectrum

mux-SR-HARQ-ACK-CSI-PUCCH-MultiPerSlot-r16 ENUMERATED {supported}
OPTIONAL,

\-- 10-36 (4-28): HARQ-ACK multiplexing on PUSCH with different
PUCCH/PUSCH starting OFDM symbols for unlicensed spectrum

mux-HARQ-ACK-PUSCH-DiffSymbol-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-37 (4-23): Repetitions for PUCCH format 1, 3, and 4 over multiple
slots with K = 2, 4, 8 for unlicensed spectrum

pucch-Repetition-F1-3-4-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-38 (5-14): Type 1 configured PUSCH repetitions over multiple
slots for unlicensed spectrum

type1-PUSCH-RepetitionMultiSlots-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-39 (5-16): Type 2 configured PUSCH repetitions over multiple
slots for unlicensed spectrum

type2-PUSCH-RepetitionMultiSlots-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-40 (5-17): PUSCH repetitions over multiple slots for unlicensed
spectrum

pusch-RepetitionMultiSlots-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-40a (5-17a): PDSCH repetitions over multiple slots for unlicensed
spectrum

pdsch-RepetitionMultiSlots-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-41 (5-18): DL SPS

downlinkSPS-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-42 (5-19): Type 1 Configured UL grant

configuredUL-GrantType1-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-43 (5-20): Type 2 Configured UL grant

configuredUL-GrantType2-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-44 (5-21): Pre-emption indication for DL

pre-EmptIndication-DL-r16 ENUMERATED {supported} OPTIONAL,

\...

}

\-- TAG-PHY-PARAMETERSSHAREDSPECTRUMCHACCESS-STOP

\-- ASN1STOP

#### -- *PosSRS-BWA-RRC-Inactive*

The IE *PosSRS-BWA-RRC-Inactive* is used to convey the capabilities
supported by the UE for support of positioning SRS bandwidth aggregation
in RRC_INACTIVE

*PosSRS-BWA-RRC-Inactive* information element

\-- ASN1START

\-- TAG-POSSRS-BWA-RRC-INACTIVE-START

PosSRS-BWA-RRC-Inactive-r18 ::= SEQUENCE {

numOfCarriersIntraBandContiguous-r18 ENUMERATED {two, three,
twoandthree},

maximumAggregatedBW-TwoCarriersFR1-r18 ENUMERATED { mhz20, mhz40, mhz50,
mhz80, mhz100, mhz160,

mhz180, mhz190, mhz200} OPTIONAL,

maximumAggregatedBW-TwoCarriersFR2-r18 ENUMERATED {mhz50, mhz100,
mhz200, mhz400, mhz600, mhz800} OPTIONAL,

maximumAggregatedBW-ThreeCarriersFR1-r18 ENUMERATED {mhz80, mhz100,
mhz160, mhz200, mhz240, mhz300} OPTIONAL,

maximumAggregatedBW-ThreeCarriersFR2-r18 ENUMERATED {mhz50, mhz100,
mhz200, mhz300, mhz400, mhz600,

mhz800, mhz1000, mhz1200} OPTIONAL,

maximumAggregatedResourceSet-r18 ENUMERATED {n1, n2, n4, n8, n12, n16},

maximumAggregatedResourcePeriodic-r18 ENUMERATED {n1, n2, n4, n8, n16,
n32, n64},

maximumAggregatedResourceSemi-r18 ENUMERATED {n0, n1, n2, n4, n8, n16,
n32, n64},

maximumAggregatedResourcePeriodicPerSlot-r18 ENUMERATED {n1, n2, n3, n4,
n5, n6, n8, n10, n12, n14},

maximumAggregatedResourceSemiPerSlot-r18 ENUMERATED {n0, n1, n2, n3, n4,
n5, n6, n8, n10, n12, n14},

guardPeriod-r18 ENUMERATED {n0, n30, n100, n140, n200},

powerClassForTwoAggregatedCarriers-r18 ENUMERATED {pc2, pc3} OPTIONAL,

powerClassForThreeAggregatedCarriers-r18 ENUMERATED {pc2, pc3} OPTIONAL,

\...

}

\-- TAG-POSSRS-BWA-RRC-INACTIVE-STOP

\-- ASN1STOP

#### -- *PosSRS-RRC-Inactive-OutsideInitialUL-BWP*

The IE *PosSRS-RRC-Inactive-OutsideInitialUL-BWP* is used to convey the
capabilities supported by the UE for SRS for Positioning transmission in
RRC_INACTIVE state configured outside initial UL BWP.

*PosSRS-RRC-Inactive-OutsideInitialUL-BWP* information element

\-- ASN1START

\-- TAG-POSSRS-RRC-INACTIVE-OUTSIDEINITIALUL-BWP-START

PosSRS-RRC-Inactive-OutsideInitialUL-BWP-r17::= SEQUENCE {

\-- R1 27-15b: Positioning SRS transmission in RRC_INACTIVE state
configured outside initial UL BWP

maxSRSposBandwidthForEachSCS-withinCC-FR1-r17 ENUMERATED {mhz5, mhz10,
mhz15, mhz20, mhz25, mhz30, mhz35, mhz40,

mhz45, mhz50, mhz60, mhz70, mhz80, mhz90, mhz100} OPTIONAL,

maxSRSposBandwidthForEachSCS-withinCC-FR2-r17 ENUMERATED {mhz50, mhz100,
mhz200, mhz400} OPTIONAL,

maxNumOfSRSposResourceSets-r17 ENUMERATED {n1, n2, n4, n8, n12, n16}
OPTIONAL,

maxNumOfPeriodicSRSposResources-r17 ENUMERATED {n1, n2, n4, n8, n16,
n32, n64} OPTIONAL,

maxNumOfPeriodicSRSposResourcesPerSlot-r17 ENUMERATED {n1, n2, n3, n4,
n5, n6, n8, n10, n12, n14} OPTIONAL,

differentNumerologyBetweenSRSposAndInitialBWP-r17 ENUMERATED {supported}
OPTIONAL,

srsPosWithoutRestrictionOnBWP-r17 ENUMERATED {supported} OPTIONAL,

maxNumOfPeriodicAndSemipersistentSRSposResources-r17 ENUMERATED {n1, n2,
n4, n8, n16, n32, n64} OPTIONAL,

maxNumOfPeriodicAndSemipersistentSRSposResourcesPerSlot-r17 ENUMERATED
{n1, n2, n3, n4, n5, n6, n8, n10, n12, n14} OPTIONAL,

differentCenterFreqBetweenSRSposAndInitialBWP-r17 ENUMERATED {supported}
OPTIONAL,

switchingTimeSRS-TX-OtherTX-r17 ENUMERATED {us100, us140, us200, us300,
us500} OPTIONAL,

\-- R1 27-15c: Support of positioning SRS transmission in RRC_INACTIVE
state outside initial BWP with semi-persistent SRS

maxNumOfSemiPersistentSRSposResources-r17 ENUMERATED {n1, n2, n4, n8,
n16, n32, n64} OPTIONAL,

maxNumOfSemiPersistentSRSposResourcesPerSlot-r17 ENUMERATED {n1, n2, n3,
n4, n5, n6, n8, n10, n12, n14} OPTIONAL,

\...

}

\-- TAG-POSSRS-RRC-INACTIVE-OUTSIDEINITIALUL-BWP-STOP

\-- ASN1STOP

#### -- *PosSRS-TxFrequencyHoppingRRC-Connected*

The IE *PosSRS-TxFrequencyHoppingRRC-Connected* is used to convey the
capabilities supported by the RRC_CONNECTED UE for support of
positioning SRS with Tx frequency hopping for RedCap UEs.

*PosSRS-TxFrequencyHoppingRRC-Connected* information element

\-- ASN1START

\-- TAG-POSSRS-TXFREQUENCYHOPPINGRRCCONNECTED-START

PosSRS-TxFrequencyHoppingRRC-Connected-r18 ::= SEQUENCE {

maximumSRS-BandwidthAcrossAllHopsFR1-r18 ENUMERATED {mhz40, mhz50,
mhz80, mhz100} OPTIONAL,

maximumSRS-BandwidthAcrossAllHopsFR2-r18 ENUMERATED {mhz100, mhz200,
mhz400} OPTIONAL,

maximumTxFH-Hops-r18 ENUMERATED {n2, n3, n4, n5, n6} OPTIONAL,

rf-TxRetuneTimeFR1-r18 ENUMERATED {n70, n140, n210} OPTIONAL,

rf-TxRetuneTimeFR2-r18 ENUMERATED {n35, n70, n140} OPTIONAL,

switchTimeBetweenActiveBWP-FrequencyHop-r18 ENUMERATED {n100, n140,
n200, n300, n500} OPTIONAL,

numOfOverlappingPRB-r18 ENUMERATED {n0, n1, n2, n4} OPTIONAL,

maximumSRS-ResourcePeriodic-r18 ENUMERATED {n1, n2, n4, n8, n16, n32,
n64} OPTIONAL,

maximumSRS-ResourceAperiodic-r18 ENUMERATED {n0,n1, n2, n4, n8, n16,
n32, n64} OPTIONAL,

maximumSRS-ResourceSemipersistent-r18 ENUMERATED {n0,n1, n2, n4, n8,
n16, n32, n64} OPTIONAL,

\...

}

\-- TAG-POSSRS-TXFREQUENCYHOPPINGRRCCONNECTED-STOP

\-- ASN1STOP

#### -- *PosSRS-TxFrequencyHoppingRRC-Inactive*

The IE *PosSRS-TxFrequencyHoppingRRC-Inactive* is used to convey the
capabilities supported by the RRC_INACTIVE UE for support of positioning
SRS with Tx frequency hopping for RedCap UEs.

*PosSRS-TxFrequencyHoppingRRC-Inactive* information element

\-- ASN1START

\-- TAG-POSSRS-TXFREQUENCYHOPPINGRRCINACTIVE-START

PosSRS-TxFrequencyHoppingRRC-Inactive-r18 ::= SEQUENCE {

maximumSRS-BandwidthAcrossAllHopsFR1-r18 ENUMERATED {mhz40, mhz50,
mhz80, mhz100} OPTIONAL,

maximumSRS-BandwidthAcrossAllHopsFR2-r18 ENUMERATED {mhz100, mhz200,
mhz400} OPTIONAL,

maximumTxFH-Hops-r18 ENUMERATED {n2, n3, n4, n5, n6} OPTIONAL,

rf-TxRetuneTimeFR1-r18 ENUMERATED {n70, n140, n210} OPTIONAL,

rf-TxRetuneTimeFR2-r18 ENUMERATED {n35, n70, n140} OPTIONAL,

switchTimeBetweenActiveBWP-FrequencyHop-r18 ENUMERATED {n100, n140,
n200, n300, n500} OPTIONAL,

numOfOverlappingPRB-r18 ENUMERATED {n0, n1, n2, n4} OPTIONAL,

maximumSRS-Resource-Periodic-r18 ENUMERATED {n1, n2, n4, n8, n16, n32,
n64} OPTIONAL,

maximumSRS-Resource-Semipersistent-r18 ENUMERATED {n0, n1, n2, n4, n8,
n16, n32, n64} OPTIONAL,

\...

}

\-- TAG-POSSRS-TXFREQUENCYHOPPINGRRCINACTIVE-STOP

\-- ASN1STOP

#### *-- PowSav-Parameters*

The IE *PowSav-Parameters* is used to convey the capabilities supported
by the UE for the power saving preferences.

*PowSav-Parameters* information element

\-- ASN1START

\-- TAG-POWSAV-PARAMETERS-START

PowSav-Parameters-r16 ::= SEQUENCE {

powSav-ParametersCommon-r16 PowSav-ParametersCommon-r16 OPTIONAL,

powSav-ParametersFRX-Diff-r16 PowSav-ParametersFRX-Diff-r16 OPTIONAL,

\...

}

PowSav-Parameters-v1700 ::= SEQUENCE {

powSav-ParametersFR2-2-r17 PowSav-ParametersFR2-2-r17 OPTIONAL,

\...

}

PowSav-ParametersCommon-r16 ::= SEQUENCE {

drx-Preference-r16 ENUMERATED {supported} OPTIONAL,

maxCC-Preference-r16 ENUMERATED {supported} OPTIONAL,

releasePreference-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 19-4a: UE assistance information

minSchedulingOffsetPreference-r16 ENUMERATED {supported} OPTIONAL,

\...

}

PowSav-ParametersFRX-Diff-r16 ::= SEQUENCE {

maxBW-Preference-r16 ENUMERATED {supported} OPTIONAL,

maxMIMO-LayerPreference-r16 ENUMERATED {supported} OPTIONAL,

\...

}

PowSav-ParametersFR2-2-r17 ::= SEQUENCE {

maxBW-Preference-r17 ENUMERATED {supported} OPTIONAL,

maxMIMO-LayerPreference-r17 ENUMERATED {supported} OPTIONAL,

\...

}

\-- TAG-POWSAV-PARAMETERS-STOP

\-- ASN1STOP

#### -- *ProcessingParameters*

The IE *ProcessingParameters* is used to indicate PDSCH/PUSCH processing
capabilities supported by the UE.

*ProcessingParameters* information element

\-- ASN1START

\-- TAG-PROCESSINGPARAMETERS-START

ProcessingParameters ::= SEQUENCE {

fallback ENUMERATED {sc, cap1-only},

differentTB-PerSlot SEQUENCE {

upto1 NumberOfCarriers OPTIONAL,

upto2 NumberOfCarriers OPTIONAL,

upto4 NumberOfCarriers OPTIONAL,

upto7 NumberOfCarriers OPTIONAL

} OPTIONAL

}

NumberOfCarriers ::= INTEGER (1..16)

\-- TAG-PROCESSINGPARAMETERS-STOP

\-- ASN1STOP

#### -- *PRS-ProcessingCapabilityOutsideMGinPPWperType*

The IE *PRS-ProcessingCapabilityOutsideMGinPPWperType* is used to
indicate DL PRS Processing Capability outside MG capabilities supported
by the UE.

*PRS-ProcessingCapabilityOutsideMGinPPWperType* information element

\-- ASN1START

\-- TAG-PRS-PROCESSINGCAPABILITYOUTSIDEMGINPPWPERType-START

PRS-ProcessingCapabilityOutsideMGinPPWperType-r17 ::= SEQUENCE {

prsProcessingType-r17 ENUMERATED {type1A, type1B, type2},

ppw-dl-PRS-BufferType-r17 ENUMERATED {type1, type2, \...},

ppw-durationOfPRS-Processing-r17 CHOICE {

ppw-durationOfPRS-Processing1-r17 SEQUENCE {

ppw-durationOfPRS-ProcessingSymbolsN-r17 ENUMERATED {msDot125, msDot25,
msDot5, ms1, ms2, ms4, ms6, ms8, ms12,

ms16, ms20, ms25, ms30, ms32, ms35, ms40, ms45, ms50},

ppw-durationOfPRS-ProcessingSymbolsT-r17 ENUMERATED {ms1, ms2, ms4, ms8,
ms16, ms20, ms30, ms40, ms80,

ms160, ms320, ms640, ms1280}

},

ppw-durationOfPRS-Processing2-r17 SEQUENCE {

ppw-durationOfPRS-ProcessingSymbolsN2-r17 ENUMERATED {msDot125, msDot25,
msDot5, ms1, ms2, ms3, ms4, ms5,

ms6, ms8, ms12},

ppw-durationOfPRS-ProcessingSymbolsT2-r17 ENUMERATED {ms4, ms5, ms6,
ms8}

}

} OPTIONAL,

ppw-maxNumOfDL-PRS-ResProcessedPerSlot-r17 SEQUENCE {

scs15-r17 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48, n64}
OPTIONAL,

scs30-r17 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48, n64}
OPTIONAL,

scs60-r17 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48, n64}
OPTIONAL,

scs120-r17 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48, n64}
OPTIONAL,

\...

},

ppw-maxNumOfDL-Bandwidth-r17 CHOICE {

fr1-r17 ENUMERATED {mhz5, mhz10, mhz20, mhz40, mhz50, mhz80, mhz100},

fr2-r17 ENUMERATED {mhz50, mhz100, mhz200, mhz400}

} OPTIONAL

}

\-- TAG-PRS-PROCESSINGCAPABILITYOUTSIDEMGINPPWPERType-STOP

\-- ASN1STOP

#### -- *RAT-Type*

The IE *RAT-Type* is used to indicate the radio access technology (RAT),
including NR, of the requested/transferred UE capabilities.

*RAT-Type* information element

\-- ASN1START

\-- TAG-RAT-TYPE-START

RAT-Type ::= ENUMERATED {nr, eutra-nr, eutra, utra-fdd-v1610, \...}

\-- TAG-RAT-TYPE-STOP

\-- ASN1STOP

#### -- *RedCapParameters*

The IE *RedCapParameters* is used to indicate the UE capabilities
supported by RedCap UEs.

*RedCapParameters* information element

\-- ASN1START

\-- TAG-REDCAPPARAMETERS-START

RedCapParameters-r17::= SEQUENCE {

\-- R1 28-1: RedCap UE

supportOfRedCap-r17 ENUMERATED {supported} OPTIONAL,

supportOf16DRB-RedCap-r17 ENUMERATED {supported} OPTIONAL

}

RedCapParameters-v1740::= SEQUENCE {

ncd-SSB-ForRedCapInitialBWP-SDT-r17 ENUMERATED {supported} OPTIONAL

}

\-- TAG-REDCAPPARAMETERS-STOP

\-- ASN1STOP

#### -- *RF-Parameters*

The IE *RF-Parameters* is used to convey RF-related capabilities for NR
operation.

*RF-Parameters* information element

\-- ASN1START

\-- TAG-RF-PARAMETERS-START

RF-Parameters ::= SEQUENCE {

supportedBandListNR SEQUENCE (SIZE (1..maxBands)) OF BandNR,

supportedBandCombinationList BandCombinationList OPTIONAL,

appliedFreqBandListFilter FreqBandList OPTIONAL,

\...,

\[\[

supportedBandCombinationList-v1540 BandCombinationList-v1540 OPTIONAL,

srs-SwitchingTimeRequested ENUMERATED {true} OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1550 BandCombinationList-v1550 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1560 BandCombinationList-v1560 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1610 BandCombinationList-v1610 OPTIONAL,

supportedBandCombinationListSidelinkEUTRA-NR-r16
BandCombinationListSidelinkEUTRA-NR-r16 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-r16
BandCombinationList-UplinkTxSwitch-r16 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1630 BandCombinationList-v1630 OPTIONAL,

supportedBandCombinationListSidelinkEUTRA-NR-v1630
BandCombinationListSidelinkEUTRA-NR-v1630 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1630
BandCombinationList-UplinkTxSwitch-v1630 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1640 BandCombinationList-v1640 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1640
BandCombinationList-UplinkTxSwitch-v1640 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1650 BandCombinationList-v1650 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1650
BandCombinationList-UplinkTxSwitch-v1650 OPTIONAL

\]\],

\[\[

extendedBand-n77-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

supportedBandCombinationList-UplinkTxSwitch-v1670
BandCombinationList-UplinkTxSwitch-v1670 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1680 BandCombinationList-v1680 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1690 BandCombinationList-v1690 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1690
BandCombinationList-UplinkTxSwitch-v1690 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1700 BandCombinationList-v1700 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1700
BandCombinationList-UplinkTxSwitch-v1700 OPTIONAL,

supportedBandCombinationListSL-RelayDiscovery-r17 OCTET STRING OPTIONAL,
\-- Contains PC5 BandCombinationListSidelinkNR-r16

supportedBandCombinationListSL-NonRelayDiscovery-r17 OCTET STRING
OPTIONAL, \-- Contains PC5 BandCombinationListSidelinkNR-r16

supportedBandCombinationListSidelinkEUTRA-NR-v1710
BandCombinationListSidelinkEUTRA-NR-v1710 OPTIONAL,

sidelinkRequested-r17 ENUMERATED {true} OPTIONAL,

extendedBand-n77-2-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1720 BandCombinationList-v1720 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1720
BandCombinationList-UplinkTxSwitch-v1720 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1730 BandCombinationList-v1730 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1730
BandCombinationList-UplinkTxSwitch-v1730 OPTIONAL,

supportedBandCombinationListSL-RelayDiscovery-v1730
BandCombinationListSL-Discovery-r17 OPTIONAL,

supportedBandCombinationListSL-NonRelayDiscovery-v1730
BandCombinationListSL-Discovery-r17 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1740 BandCombinationList-v1740 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1740
BandCombinationList-UplinkTxSwitch-v1740 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1760 BandCombinationList-v1760 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1760
BandCombinationList-UplinkTxSwitch-v1760 OPTIONAL

\]\],

\[\[

dummy1 BandCombinationList-v1770 OPTIONAL,

dummy2 BandCombinationList-UplinkTxSwitch-v1770 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1780 BandCombinationList-v1780 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1780
BandCombinationList-UplinkTxSwitch-v1780 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1800 BandCombinationList-v1800 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1800
BandCombinationList-UplinkTxSwitch-v1800 OPTIONAL,

supportedBandCombinationListSL-U2U-Relay-r18 SEQUENCE {

supportedBandCombinationListSL-U2U-RelayDiscovery-r18 OCTET STRING
OPTIONAL, \-- Contains PC5

\-- BandCombinationListSidelinkNR-r16

supportedBandCombinationListSL-U2U-DiscoveryExt
BandCombinationListSL-Discovery-r17 OPTIONAL

} OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1830 BandCombinationList-v1830 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1830
BandCombinationList-UplinkTxSwitch-v1830 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1840 BandCombinationList-v1840 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1840
BandCombinationList-UplinkTxSwitch-v1840 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1860 BandCombinationList-v1860 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1860
BandCombinationList-UplinkTxSwitch-v1860 OPTIONAL

\]\]

}

RF-Parameters-v15g0 ::= SEQUENCE {

supportedBandCombinationList-v15g0 BandCombinationList-v15g0 OPTIONAL

}

RF-Parameters-v16a0 ::= SEQUENCE {

supportedBandCombinationList-v16a0 BandCombinationList-v16a0 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v16a0
BandCombinationList-UplinkTxSwitch-v16a0 OPTIONAL

}

RF-Parameters-v16c0 ::= SEQUENCE {

supportedBandListNR-v16c0 SEQUENCE (SIZE (1..maxBands)) OF BandNR-v16c0

}

RF-Parameters-v16j0 ::= SEQUENCE {

supportedBandCombinationList-v16j0 BandCombinationList-v16j0 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v16j0
BandCombinationList-UplinkTxSwitch-v16j0 OPTIONAL

}

RF-Parameters-v17b0 ::= SEQUENCE {

supportedBandListNR-v17b0 SEQUENCE (SIZE (1..maxBands)) OF BandNR-v17b0
OPTIONAL,

supportedBandCombinationList-v17b0 BandCombinationList-v17b0 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v17b0
BandCombinationList-UplinkTxSwitch-v17b0 OPTIONAL

}

BandNR ::= SEQUENCE {

bandNR FreqBandIndicatorNR,

modifiedMPR-Behaviour BIT STRING (SIZE (8)) OPTIONAL,

mimo-ParametersPerBand MIMO-ParametersPerBand OPTIONAL,

extendedCP ENUMERATED {supported} OPTIONAL,

multipleTCI ENUMERATED {supported} OPTIONAL,

bwp-WithoutRestriction ENUMERATED {supported} OPTIONAL,

bwp-SameNumerology ENUMERATED {upto2, upto4} OPTIONAL,

bwp-DiffNumerology ENUMERATED {upto4} OPTIONAL,

crossCarrierScheduling-SameSCS ENUMERATED {supported} OPTIONAL,

pdsch-256QAM-FR2 ENUMERATED {supported} OPTIONAL,

pusch-256QAM ENUMERATED {supported} OPTIONAL,

ue-PowerClass ENUMERATED {pc1, pc2, pc3, pc4} OPTIONAL,

rateMatchingLTE-CRS ENUMERATED {supported} OPTIONAL,

channelBWs-DL CHOICE {

fr1 SEQUENCE {

scs-15kHz BIT STRING (SIZE (10)) OPTIONAL,

scs-30kHz BIT STRING (SIZE (10)) OPTIONAL,

scs-60kHz BIT STRING (SIZE (10)) OPTIONAL

},

fr2 SEQUENCE {

scs-60kHz BIT STRING (SIZE (3)) OPTIONAL,

scs-120kHz BIT STRING (SIZE (3)) OPTIONAL

}

} OPTIONAL,

channelBWs-UL CHOICE {

fr1 SEQUENCE {

scs-15kHz BIT STRING (SIZE (10)) OPTIONAL,

scs-30kHz BIT STRING (SIZE (10)) OPTIONAL,

scs-60kHz BIT STRING (SIZE (10)) OPTIONAL

},

fr2 SEQUENCE {

scs-60kHz BIT STRING (SIZE (3)) OPTIONAL,

scs-120kHz BIT STRING (SIZE (3)) OPTIONAL

}

} OPTIONAL,

\...,

\[\[

maxUplinkDutyCycle-PC2-FR1 ENUMERATED {n60, n70, n80, n90, n100}
OPTIONAL

\]\],

\[\[

pucch-SpatialRelInfoMAC-CE ENUMERATED {supported} OPTIONAL,

powerBoosting-pi2BPSK ENUMERATED {supported} OPTIONAL

\]\],

\[\[

maxUplinkDutyCycle-FR2 ENUMERATED {n15, n20, n25, n30, n40, n50, n60,
n70, n80, n90, n100} OPTIONAL

\]\],

\[\[

channelBWs-DL-v1590 CHOICE {

fr1 SEQUENCE {

scs-15kHz BIT STRING (SIZE (16)) OPTIONAL,

scs-30kHz BIT STRING (SIZE (16)) OPTIONAL,

scs-60kHz BIT STRING (SIZE (16)) OPTIONAL

},

fr2 SEQUENCE {

scs-60kHz BIT STRING (SIZE (8)) OPTIONAL,

scs-120kHz BIT STRING (SIZE (8)) OPTIONAL

}

} OPTIONAL,

channelBWs-UL-v1590 CHOICE {

fr1 SEQUENCE {

scs-15kHz BIT STRING (SIZE (16)) OPTIONAL,

scs-30kHz BIT STRING (SIZE (16)) OPTIONAL,

scs-60kHz BIT STRING (SIZE (16)) OPTIONAL

},

fr2 SEQUENCE {

scs-60kHz BIT STRING (SIZE (8)) OPTIONAL,

scs-120kHz BIT STRING (SIZE (8)) OPTIONAL

}

} OPTIONAL

\]\],

\[\[

asymmetricBandwidthCombinationSet BIT STRING (SIZE (1..32)) OPTIONAL

\]\],

\[\[

\-- R1 10: NR-unlicensed

sharedSpectrumChAccessParamsPerBand-r16
SharedSpectrumChAccessParamsPerBand-r16 OPTIONAL,

\-- R1 11-7b: Independent cancellation of the overlapping PUSCHs in an
intra-band UL CA

cancelOverlappingPUSCH-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 14-1: Multiple LTE-CRS rate matching patterns

multipleRateMatchingEUTRA-CRS-r16 SEQUENCE {

maxNumberPatterns-r16 INTEGER (2..6),

maxNumberNon-OverlapPatterns-r16 INTEGER (1..3)

} OPTIONAL,

\-- R1 14-1a: Two LTE-CRS overlapping rate matching patterns within a
part of NR carrier using 15 kHz overlapping with a LTE carrier

overlapRateMatchingEUTRA-CRS-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 14-2: PDSCH Type B mapping of length 9 and 10 OFDM symbols

pdsch-MappingTypeB-Alt-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 14-3: One slot periodic TRS configuration for FR1

oneSlotPeriodicTRS-r16 ENUMERATED {supported} OPTIONAL,

olpc-SRS-Pos-r16 OLPC-SRS-Pos-r16 OPTIONAL,

spatialRelationsSRS-Pos-r16 SpatialRelationsSRS-Pos-r16 OPTIONAL,

simulSRS-MIMO-TransWithinBand-r16 ENUMERATED {n2} OPTIONAL,

channelBW-DL-IAB-r16 CHOICE {

fr1-100mhz SEQUENCE {

scs-15kHz ENUMERATED {supported} OPTIONAL,

scs-30kHz ENUMERATED {supported} OPTIONAL,

scs-60kHz ENUMERATED {supported} OPTIONAL

},

fr2-200mhz SEQUENCE {

scs-60kHz ENUMERATED {supported} OPTIONAL,

scs-120kHz ENUMERATED {supported} OPTIONAL

}

} OPTIONAL,

channelBW-UL-IAB-r16 CHOICE {

fr1-100mhz SEQUENCE {

scs-15kHz ENUMERATED {supported} OPTIONAL,

scs-30kHz ENUMERATED {supported} OPTIONAL,

scs-60kHz ENUMERATED {supported} OPTIONAL

},

fr2-200mhz SEQUENCE {

scs-60kHz ENUMERATED {supported} OPTIONAL,

scs-120kHz ENUMERATED {supported} OPTIONAL

}

} OPTIONAL,

rasterShift7dot5-IAB-r16 ENUMERATED {supported} OPTIONAL,

ue-PowerClass-v1610 ENUMERATED {pc1dot5} OPTIONAL,

condHandover-r16 ENUMERATED {supported} OPTIONAL,

condHandoverFailure-r16 ENUMERATED {supported} OPTIONAL,

condHandoverTwoTriggerEvents-r16 ENUMERATED {supported} OPTIONAL,

condPSCellChange-r16 ENUMERATED {supported} OPTIONAL,

condPSCellChangeTwoTriggerEvents-r16 ENUMERATED {supported} OPTIONAL,

mpr-PowerBoost-FR2-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 11-9: Multiple active configured grant configurations for a BWP
of a serving cell

activeConfiguredGrant-r16 SEQUENCE {

maxNumberConfigsPerBWP-r16 ENUMERATED {n1, n2, n4, n8, n12},

maxNumberConfigsAllCC-r16 INTEGER (2..32)

} OPTIONAL,

\-- R1 11-9a: Joint release in a DCI for two or more configured grant
Type 2 configurations for a given BWP of a serving cell

jointReleaseConfiguredGrantType2-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 12-2: Multiple SPS configurations

sps-r16 SEQUENCE {

maxNumberConfigsPerBWP-r16 INTEGER (1..8),

maxNumberConfigsAllCC-r16 INTEGER (2..32)

} OPTIONAL,

\-- R1 12-2a: Joint release in a DCI for two or more SPS configurations
for a given BWP of a serving cell

jointReleaseSPS-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 13-19: Simultaneous positioning SRS and MIMO SRS transmission
within a band across multiple CCs

simulSRS-TransWithinBand-r16 ENUMERATED {n2} OPTIONAL,

trs-AdditionalBandwidth-r16 ENUMERATED {trs-AddBW-Set1, trs-AddBW-Set2}
OPTIONAL,

handoverIntraF-IAB-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 22-5a: Simultaneous transmission of SRS for antenna switching and
SRS for CB/NCB /BM for intra-band UL CA

\-- R1 22-5c: Simultaneous transmission of SRS for antenna switching and
SRS for antenna switching for intra-band UL CA

simulTX-SRS-AntSwitchingIntraBandUL-CA-r16
SimulSRS-ForAntennaSwitching-r16 OPTIONAL,

\-- R1 10: NR-unlicensed

sharedSpectrumChAccessParamsPerBand-v1630
SharedSpectrumChAccessParamsPerBand-v1630 OPTIONAL

\]\],

\[\[

handoverUTRA-FDD-r16 ENUMERATED {supported} OPTIONAL,

\-- R4 7-4: Report the shorter transient capability supported by the UE:
2, 4 or 7us

enhancedUL-TransientPeriod-r16 ENUMERATED {us2, us4, us7} OPTIONAL,

sharedSpectrumChAccessParamsPerBand-v1640
SharedSpectrumChAccessParamsPerBand-v1640 OPTIONAL

\]\],

\[\[

type1-PUSCH-RepetitionMultiSlots-v1650 ENUMERATED {supported} OPTIONAL,

type2-PUSCH-RepetitionMultiSlots-v1650 ENUMERATED {supported} OPTIONAL,

pusch-RepetitionMultiSlots-v1650 ENUMERATED {supported} OPTIONAL,

configuredUL-GrantType1-v1650 ENUMERATED {supported} OPTIONAL,

configuredUL-GrantType2-v1650 ENUMERATED {supported} OPTIONAL,

sharedSpectrumChAccessParamsPerBand-v1650
SharedSpectrumChAccessParamsPerBand-v1650 OPTIONAL

\]\],

\[\[

enhancedSkipUplinkTxConfigured-v1660 ENUMERATED {supported} OPTIONAL,

enhancedSkipUplinkTxDynamic-v1660 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

maxUplinkDutyCycle-PC1dot5-MPE-FR1-r16 ENUMERATED {n10, n15, n20, n25,
n30, n40, n50, n60, n70, n80, n90, n100} OPTIONAL,

txDiversity-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 36-1: Support of 1024QAM for PDSCH for FR1

pdsch-1024QAM-FR1-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 22-1 support of FR2 HST operation

ue-PowerClass-v1700 ENUMERATED {pc5, pc6, pc7} OPTIONAL,

\-- R1 24: NR extension to 71GHz (FR2-2)

fr2-2-AccessParamsPerBand-r17 FR2-2-AccessParamsPerBand-r17 OPTIONAL,

rlm-Relaxation-r17 ENUMERATED {supported} OPTIONAL,

bfd-Relaxation-r17 ENUMERATED {supported} OPTIONAL,

cg-SDT-r17 ENUMERATED {supported} OPTIONAL,

locationBasedCondHandover-r17 ENUMERATED {supported} OPTIONAL,

timeBasedCondHandover-r17 ENUMERATED {supported} OPTIONAL,

eventA4BasedCondHandover-r17 ENUMERATED {supported} OPTIONAL,

mn-InitiatedCondPSCellChangeNRDC-r17 ENUMERATED {supported} OPTIONAL,

sn-InitiatedCondPSCellChangeNRDC-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 29-3a: PDCCH skipping

pdcch-SkippingWithoutSSSG-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 29-3b: 2 search space sets group switching

sssg-Switching-1BitInd-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 29-3c: 3 search space sets group switching

sssg-Switching-2BitInd-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 29-3d: 2 search space sets group switching with PDCCH skipping

pdcch-SkippingWithSSSG-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 29-3e: Support Search space set group switching capability 2 for
FR1

searchSpaceSetGrp-switchCap2-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 26-1: Uplink Time and Frequency pre-compensation and timing
relationship enhancements

uplinkPreCompensation-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 26-4: UE reporting of information related to TA pre-compensation

uplink-TA-Reporting-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 26-5: Increasing the number of HARQ processes

max-HARQ-ProcessNumber-r17 ENUMERATED {u16d32, u32d16, u32d32} OPTIONAL,

\-- R1 26-6: Type-2 HARQ codebook enhancement

type2-HARQ-Codebook-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 26-6a: Type-1 HARQ codebook enhancement

type1-HARQ-Codebook-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 26-6b: Type-3 HARQ codebook enhancement

type3-HARQ-Codebook-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 26-9: UE-specific K_offset

ue-specific-K-Offset-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 24-1f: Multiple PDSCH scheduling by single DCI for 120kHz in
FR2-1

multiPDSCH-SingleDCI-FR2-1-SCS-120kHz-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 24-1g: Multiple PUSCH scheduling by single DCI for 120kHz in
FR2-1

multiPUSCH-SingleDCI-FR2-1-SCS-120kHz-r17 ENUMERATED {supported}
OPTIONAL,

\-- R4 14-4: Parallel PRS measurements in RRC_INACTIVE state, FR1/FR2
diff

parallelPRS-MeasRRC-Inactive-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 27-1-2: Support of UE-TxTEGs for UL TDOA

nr-UE-TxTEG-ID-MaxSupport-r17 ENUMERATED {n1, n2, n3, n4, n6, n8}
OPTIONAL,

\-- R1 27-17: PRS processing in RRC_INACTIVE

prs-ProcessingRRC-Inactive-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 27-3-2: DL PRS measurement outside MG and in a PRS processing
window

prs-ProcessingWindowType1A-r17 ENUMERATED {option1, option2, option3}
OPTIONAL,

prs-ProcessingWindowType1B-r17 ENUMERATED {option1, option2, option3}
OPTIONAL,

prs-ProcessingWindowType2-r17 ENUMERATED {option1, option2, option3}
OPTIONAL,

\-- R1 27-15: Positioning SRS transmission in RRC_INACTIVE state for
initial UL BWP

srs-AllPosResourcesRRC-Inactive-r17 SRS-AllPosResourcesRRC-Inactive-r17
OPTIONAL,

\-- R1 27-16: OLPC for positioning SRS in RRC_INACTIVE state - gNB

olpc-SRS-PosRRC-Inactive-r17 OLPC-SRS-Pos-r16 OPTIONAL,

\-- R1 27-19: Spatial relation for positioning SRS in RRC_INACTIVE
state - gNB

spatialRelationsSRS-PosRRC-Inactive-r17 SpatialRelationsSRS-Pos-r16
OPTIONAL,

\-- R1 30-1: Increased maximum number of PUSCH Type A repetitions

maxNumberPUSCH-TypeA-Repetition-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-2: PUSCH Type A repetitions based on available slots

puschTypeA-RepetitionsAvailSlot-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-3: TB processing over multi-slot PUSCH

tb-ProcessingMultiSlotPUSCH-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-3a: Repetition of TB processing over multi-slot PUSCH

tb-ProcessingRepMultiSlotPUSCH-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-4: The maximum duration for DM-RS bundling

maxDurationDMRS-Bundling-r17 SEQUENCE {

fdd-r17 ENUMERATED {n4, n8, n16, n32} OPTIONAL,

tdd-r17 ENUMERATED {n2, n4, n8, n16} OPTIONAL

} OPTIONAL,

\-- R1 30-6: Repetition of PUSCH transmission scheduled by RAR UL grant
and DCI format 0_0 with CRC scrambled by TC-RNTI

pusch-RepetitionMsg3-r17 ENUMERATED {supported} OPTIONAL,

sharedSpectrumChAccessParamsPerBand-v1710
SharedSpectrumChAccessParamsPerBand-v1710 OPTIONAL,

\-- R4 25-2: Parallel measurements on cells belonging to a different
NGSO satellite than a serving satellite without scheduling restrictions

\-- on normal operations with the serving cell

parallelMeasurementWithoutRestriction-r17 ENUMERATED {supported}
OPTIONAL,

\-- R4 25-5: Parallel measurements on multiple NGSO satellites within a
SMTC

maxNumber-NGSO-SatellitesWithinOneSMTC-r17 ENUMERATED {n1, n2, n3, n4}
OPTIONAL,

\-- R1 26-10: K1 range extension

k1-RangeExtension-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 35-1: Aperiodic CSI-RS for tracking for fast SCell activation

aperiodicCSI-RS-FastScellActivation-r17 SEQUENCE {

maxNumberAperiodicCSI-RS-PerCC-r17 ENUMERATED {n8, n16, n32, n48, n64,
n128, n255},

maxNumberAperiodicCSI-RS-AcrossCCs-r17 ENUMERATED {n8, n16, n32, n64,
n128, n256, n512, n1024}

} OPTIONAL,

\-- R1 35-2: Aperiodic CSI-RS bandwidth for tracking for fast SCell
activation for 10MHz UE channel bandwidth

aperiodicCSI-RS-AdditionalBandwidth-r17 ENUMERATED {addBW-Set1,
addBW-Set2} OPTIONAL,

\-- R1 28-1a: RRC-configured DL BWP without CD-SSB or NCD-SSB

bwp-WithoutCD-SSB-OrNCD-SSB-RedCap-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 28-3: Half-duplex FDD operation type A for (e)RedCap UE

halfDuplexFDD-TypeA-RedCap-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 27-15b: Positioning SRS transmission in RRC_INACTIVE state
configured outside initial UL BWP

posSRS-RRC-Inactive-OutsideInitialUL-BWP-r17
PosSRS-RRC-Inactive-OutsideInitialUL-BWP-r17 OPTIONAL,

\-- R4 15-3 UE support of CBW for 480kHz SCS

channelBWs-DL-SCS-480kHz-FR2-2-r17 BIT STRING (SIZE (8)) OPTIONAL,

channelBWs-UL-SCS-480kHz-FR2-2-r17 BIT STRING (SIZE (8)) OPTIONAL,

\-- R4 15-4 UE support of CBW for 960kHz SCS

channelBWs-DL-SCS-960kHz-FR2-2-r17 BIT STRING (SIZE (8)) OPTIONAL,

channelBWs-UL-SCS-960kHz-FR2-2-r17 BIT STRING (SIZE (8)) OPTIONAL,

\-- R4 17-1 UL gap for Tx power management

ul-GapFR2-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 25-4: One-shot HARQ ACK feedback triggered by DCI format 1_2

oneShotHARQ-feedbackTriggeredByDCI-1-2-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 25-5: PHY priority handling for one-shot HARQ ACK feedback

oneShotHARQ-feedbackPhy-Priority-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 25-6: Enhanced type 3 HARQ-ACK codebook feedback

enhancedType3-HARQ-CodebookFeedback-r17 SEQUENCE {

enhancedType3-HARQ-Codebooks-r17 ENUMERATED {n1, n2, n4, n8},

maxNumberPUCCH-Transmissions-r17 ENUMERATED {n1, n2, n3, n4, n5, n6, n7}

} OPTIONAL,

\-- R1 25-7: Triggered HARQ-ACK codebook re-transmission

triggeredHARQ-CodebookRetx-r17 SEQUENCE {

minHARQ-Retx-Offset-r17 ENUMERATED {n-7, n-5, n-3, n-1, n1},

maxHARQ-Retx-Offset-r17 ENUMERATED {n4, n6, n8, n10, n12, n14, n16, n18,
n20, n22, n24}

} OPTIONAL

\]\],

\[\[

\-- R4 22-2 support of one shot large UL timing adjustment

ue-OneShotUL-TimingAdj-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 25-2: Repetitions for PUCCH format 0, and 2 over multiple slots
with K = 2, 4, 8

pucch-Repetition-F0-2-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 25-11a: 4-bits subband CQI for NTN and unlicensed

cqi-4-BitsSubbandNTN-SharedSpectrumChAccess-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 25-16: HARQ-ACK with different priorities multiplexing on a
PUCCH/PUSCH

mux-HARQ-ACK-DiffPriorities-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 25-20a: Propagation delay compensation based on Rel-15 TA
procedure for NTN and unlicensed

ta-BasedPDC-NTN-SharedSpectrumChAccess-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 33-2b: DCI-based enabling/disabling ACK/NACK-based feedback for
dynamic scheduling for multicast

ack-NACK-FeedbackForMulticastWithDCI-Enabler-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 33-2e: Multiple G-RNTIs for group-common PDSCHs

maxNumberG-RNTI-r17 INTEGER (2..8) OPTIONAL,

\-- R1 33-2f: Dynamic multicast with DCI format 4_2

dynamicMulticastDCI-Format4-2-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-2i: Supported maximal modulation order for multicast PDSCH

maxModulationOrderForMulticast-r17 CHOICE {

fr1-r17 ENUMERATED {qam256, qam1024},

fr2-r17 ENUMERATED {qam64, qam256}

} OPTIONAL,

\-- R1 33-3-1: Dynamic Slot-level repetition for group-common PDSCH for
TN and licensed

dynamicSlotRepetitionMulticastTN-NonSharedSpectrumChAccess-r17
ENUMERATED {n8, n16} OPTIONAL,

\-- R1 33-3-1a: Dynamic Slot-level repetition for group-common PDSCH for
NTN and unlicensed

dynamicSlotRepetitionMulticastNTN-SharedSpectrumChAccess-r17 ENUMERATED
{n8, n16} OPTIONAL,

\-- R1 33-4-1: DCI-based enabling/disabling NACK-only based feedback for
dynamic scheduling for multicast

nack-OnlyFeedbackForMulticastWithDCI-Enabler-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 33-5-1b: DCI-based enabling/disabling ACK/NACK-based feedback for
dynamic scheduling for multicast

ack-NACK-FeedbackForSPS-MulticastWithDCI-Enabler-r17 ENUMERATED
{supported} OPTIONAL,

\-- R1 33-5-1h: Multiple G-CS-RNTIs for SPS group-common PDSCHs

maxNumberG-CS-RNTI-r17 INTEGER (2..8) OPTIONAL,

\-- R1 33-10: Support group-common PDSCH RE-level rate matching for
multicast

re-LevelRateMatchingForMulticast-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 36-1a: Support of 1024QAM for PDSCH with maximum 2 MIMO layers
for FR1

pdsch-1024QAM-2MIMO-FR1-r17 ENUMERATED {supported} OPTIONAL,

\-- R4 14-3 PRS measurement without MG

prs-MeasurementWithoutMG-r17 ENUMERATED {cpLength, quarterSymbol,
halfSymbol, halfSlot} OPTIONAL,

\-- R4 25-7: The number of target NGSO satellites the UE can monitor per
carrier

maxNumber-NGSO-SatellitesPerCarrier-r17 INTEGER (3..4) OPTIONAL,

\-- R1 27-3-3 DL PRS Processing Capability outside MG - buffering
capability

prs-ProcessingCapabilityOutsideMGinPPW-r17 SEQUENCE (SIZE(1..3)) OF
PRS-ProcessingCapabilityOutsideMGinPPWperType-r17 OPTIONAL,

\-- R1 27-15a: Positioning SRS transmission in RRC_INACTIVE state for
initial UL BWP with semi-persistent SRS

srs-SemiPersistent-PosResourcesRRC-Inactive-r17 SEQUENCE {

maxNumOfSemiPersistentSRSposResources-r17 ENUMERATED {n1, n2, n4, n8,
n16, n32, n64},

maxNumOfSemiPersistentSRSposResourcesPerSlot-r17 ENUMERATED {n1, n2, n3,
n4, n5, n6, n8, n10, n12, n14}

} OPTIONAL,

\-- R2: UE support of CBW for 120kHz SCS

channelBWs-DL-SCS-120kHz-FR2-2-r17 BIT STRING (SIZE (8)) OPTIONAL,

channelBWs-UL-SCS-120kHz-FR2-2-r17 BIT STRING (SIZE (8)) OPTIONAL

\]\],

\[\[

\-- R1 30-4a: DM-RS bundling for PUSCH repetition type A

dmrs-BundlingPUSCH-RepTypeA-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-4b: DM-RS bundling for PUSCH repetition type B

dmrs-BundlingPUSCH-RepTypeB-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-4c: DM-RS bundling for TB processing over multi-slot PUSCH

dmrs-BundlingPUSCH-multiSlot-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-4d: DMRS bundling for PUCCH repetitions

dmrs-BundlingPUCCH-Rep-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-4e: Enhanced inter-slot frequency hopping with inter-slot
bundling for PUSCH

interSlotFreqHopInterSlotBundlingPUSCH-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 30-4f: Enhanced inter-slot frequency hopping for PUCCH
repetitions with DMRS bundling

interSlotFreqHopPUCCH-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-4g: Restart DM-RS bundling

dmrs-BundlingRestart-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 30-4h: DM-RS bundling for non-back-to-back transmission

dmrs-BundlingNonBackToBackTX-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 33-5-1e: Dynamic Slot-level repetition for SPS group-common PDSCH
for multicast

maxDynamicSlotRepetitionForSPS-Multicast-r17 ENUMERATED {n8, n16}
OPTIONAL,

\-- R1 33-5-1g: DCI-based enabling/disabling NACK-only based feedback
for SPS group-common PDSCH for multicast

nack-OnlyFeedbackForSPS-MulticastWithDCI-Enabler-r17 ENUMERATED
{supported} OPTIONAL,

\-- R1 33-5-1i: Multicast SPS scheduling with DCI format 4_2

sps-MulticastDCI-Format4-2-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-5-2: Multiple SPS group-common PDSCH configuration on PCell

sps-MulticastMultiConfig-r17 INTEGER (1..8) OPTIONAL,

\-- R1 33-6-1: DL priority indication for multicast in DCI

priorityIndicatorInDCI-Multicast-r17 ENUMERATED {supported} OPTIONAL,

\-- R1 33-6-1a: DL priority configuration for SPS multicast

priorityIndicatorInDCI-SPS-Multicast-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 33-6-2: Two HARQ-ACK codebooks simultaneously constructed for
supporting HARQ-ACK codebooks with different priorities

\-- for unicast and multicast at a UE

twoHARQ-ACK-CodebookForUnicastAndMulticast-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 33-6-3: More than one PUCCH for HARQ-ACK transmission for
multicast or for unicast and multicast within a slot

multiPUCCH-HARQ-ACK-ForMulticastUnicast-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 33-9: Supporting unicast PDCCH to release SPS group-common PDSCH

releaseSPS-MulticastWithCS-RNTI-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 41-3-1a UE automomous TA adjustment when cell-reselection happens

posUE-TA-AutoAdjustment-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 41-3-1: SRS for positioning configuration in multiple cells for
UEs in RRC_INACTIVE state for initial UL BWP

posSRS-ValidityAreaRRC-InactiveInitialUL-BWP-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 41-3-2: SRS for positioning configuration in multiple cells for
UEs in RRC_INACTIVE state for configured outside

\-- initial UL BWP

posSRS-ValidityAreaRRC-InactiveOutsideInitialUL-BWP-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 41-5-1:PRS measurement with Rx frequency hopping within a MG and
measurement reporting RRC_CONNECTED for RedCap UEs

dl-PRS-MeasurementWithRxFH-RRC-ConnectedForRedCap-r18
DL-PRS-MeasurementWithRxFH-RRC-Connected-r18 OPTIONAL,

\-- R1 41-5-2: Support of positioning SRS with Tx frequency hopping in
RRC_CONNECTED for RedCap UEs

posSRS-TxFH-RRC-ConnectedForRedCap-r18
PosSRS-TxFrequencyHoppingRRC-Connected-r18 OPTIONAL,

\-- R1 41-5-2a: Support of positioning SRS with Tx frequency hopping in
RRC_INACTIVE for RedCap UEs

posSRS-TxFH-RRC-InactiveForRedCap-r18
PosSRS-TxFrequencyHoppingRRC-Inactive-r18 OPTIONAL,

\-- R1 41-4-8: Support of Positioning SRS bandwidth aggregation in
RRC_INACTIVE

posSRS-BWA-RRC-Inactive-r18 PosSRS-BWA-RRC-Inactive-r18 OPTIONAL,

\-- R1 41-4-6a support a Rel-17 single DCI scheduling positioning SRS
resource sets across the linked carriers

\-- for SRS bandwidth aggregation in RRC_CONNECTED state

posJointTriggerBySingleDCI-RRC-Connected-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 41-5-1a PRS measurement with Rx frequency hopping in RRC_INACTIVE
for RedCap UEs

dl-PRS-MeasurementWithRxFH-RRC-InactiveforRedCap-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 41-5-1b PRS measurement with Rx frequency hopping in RRC_IDLE for
RedCap UEs

dl-PRS-MeasurementWithRxFH-RRC-IdleforRedCap-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 42-1: Spatial domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for periodic CSI reporting

spatialAdaptation-CSI-Feedback-r18 SEQUENCE {

csiFeedbackType-r18 ENUMERATED {sdType1, sdType2, both},

maxNumberLmax-r18 INTEGER (2..4),

maxNumberCSI-ResourcePerCC-r18 SEQUENCE {

sdType1-Resource-r18 INTEGER (1..32),

sdType2-Resource-r18 INTEGER (1..32)

},

maxNumberTotalCSI-ResourcePerCC-r18 SEQUENCE {

sdType1-Resource-r18 ENUMERATED {n8, n16, n24, n32, n64, n128},

sdType2-Resource-r18 ENUMERATED {n8, n16, n24, n32, n64, n128}

},

totalNumberCSI-Reporting-r18 INTEGER (2..4)

} OPTIONAL,

\-- R1 42-1a: Spatial domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for periodic CSI

\-- reporting on PUSCH

spatialAdaptation-CSI-FeedbackPUSCH-r18 SEQUENCE {

csiFeedbackType-r18 ENUMERATED {sdType1, sdType2, both},

maxNumberLmax-r18 INTEGER (2..8),

subReportCSI-r18 INTEGER (2..4),

maxNumberCSI-ResourcePerCC-r18 INTEGER (1..32),

maxNumberTotalCSI-ResourcePerCC-r18 ENUMERATED {n8, n16, n24, n32, n64,
n128},

totalNumberCSI-Reporting-r18 INTEGER (2..12)

} OPTIONAL,

\-- R1 42-1b: Spatial domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for aperiodic CSI reporting

spatialAdaptation-CSI-FeedbackAperiodic-r18 SEQUENCE {

csiFeedbackType-r18 ENUMERATED {sdType1, sdType2, both},

maxNumberLmax-r18 INTEGER (2..8),

subReportCSI-r18 INTEGER (2..4),

maxNumberCSI-ResourcePerCC-r18 SEQUENCE {

sdType1-Resource-r18 INTEGER (1..32),

sdType2-Resource-r18 INTEGER (1..32)

},

maxNumberTotalCSI-ResourcePerCC-r18 SEQUENCE {

sdType1-Resource-r18 ENUMERATED {n8, n16, n24, n32, n64, n128},

sdType2-Resource-r18 ENUMERATED {n8, n16, n24, n32, n64, n128}

},

totalNumberCSI-Reporting-r18 INTEGER (2..12)

} OPTIONAL,

\-- R1 42-1c: Spatial domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for semi-persistent

\-- CSI reporting on PUCCH

spatialAdaptation-CSI-FeedbackPUCCH-r18 SEQUENCE {

csiFeedbackType-r18 ENUMERATED {sdType1, sdType2, both},

maxNumberLmax-r18 INTEGER (2..4),

subReportCSI-r18 INTEGER (2..4),

maxNumberCSI-ResourcePerCC-r18 INTEGER (1..32),

maxNumberTotalCSI-ResourcePerCC-r18 ENUMERATED {n8, n16, n24, n32, n64,
n128},

totalNumberCSI-Reporting-r18 INTEGER (2..4)

} OPTIONAL,

\-- R1 42-2: Power domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for periodic CSI reporting

powerAdaptation-CSI-Feedback-r18 SEQUENCE {

maxNumberLmax-r18 INTEGER (2..4),

maxNumberCSI-ResourcePerCC-r18 INTEGER (1..32),

maxNumberTotalCSI-ResourcePerCC-r18 ENUMERATED {n8, n16, n24, n32, n64,
n128},

totalNumberCSI-Reporting-r18 INTEGER (2..4)

} OPTIONAL,

\-- R1 42-2a: Power domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for semi-persistent CSI

\-- reporting on PUSCH

powerAdaptation-CSI-FeedbackPUSCH-r18 SEQUENCE {

maxNumberLmax-r18 INTEGER (2..8),

subReportCSI-r18 INTEGER (2..4),

maxNumberCSI-ResourcePerCC-r18 INTEGER (1..32),

maxNumberTotalCSI-ResourcePerCC-r18 ENUMERATED {n8, n16, n24, n32, n64,
n128},

totalNumberCSI-Reporting-r18 INTEGER (2..12)

} OPTIONAL,

\-- R1 42-2b: Power domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for aperiodic CSI reporting

powerAdaptation-CSI-FeedbackAperiodic-r18 SEQUENCE {

maxNumberLmax-r18 INTEGER (2..8),

subReportCSI-r18 INTEGER (2..4),

maxNumberCSI-ResourcePerCC-r18 INTEGER (1..32),

maxNumberTotalCSI-ResourcePerCC-r18 ENUMERATED {n8, n16, n24, n32, n64,
n128},

totalNumberCSI-Reporting-r18 INTEGER (2..12)

} OPTIONAL,

\-- R1 42-2c: Power domain adaptation with CSI feedback based on CSI
report sub-configuration(s) for semi-persistent CSI

\-- reporting on PUCCH

powerAdaptation-CSI-FeedbackPUCCH-r18 SEQUENCE {

maxNumberLmax-r18 INTEGER (2..4),

subReportCSI-r18 INTEGER (2..4),

maxNumberCSI-ResourcePerCC-r18 INTEGER (1..32),

maxNumberTotalCSI-ResourcePerCC-r18 ENUMERATED {n8, n16, n24, n32, n64,
n128},

totalNumberCSI-Reporting-r18 INTEGER (2..4)

} OPTIONAL,

\-- R1 42-4: Cell DTX and/or DRX operation based on RRC configuration

nes-CellDTX-DRX-r18 ENUMERATED {cellDTXonly, cellDRXonly, both}
OPTIONAL,

\-- R1 42-5: Cell DTX/DRX operation triggered by DCI format 2_9

nes-CellDTX-DRX-DCI2-9-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 42-7: Mixed codebook combination for spatial domain adaptation
with CSI feedback based on CSI report sub-configuration(s),

\-- each containing one port subset configuration

mixCodeBookSpatialAdaptation-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 42-8: the number of CSI report(s) for which the UE can measure
and process reference signals simultaneously in a CC of the

\-- band for which this capability is provided.

simultaneousCSI-SubReportsPerCC-r18 INTEGER (1..8) OPTIONAL,

\-- R1 44-2: NTN DMRS bundling enhancement for PUSCH in NGSO scenarios

ntn-DMRS-BundlingNGSO-r18 ENUMERATED {n4, n8, n16, n32} OPTIONAL,

\-- R1 45-3: Beam indication with joint DL/UL LTM TCI states

ltm-BeamIndicationJointTCI-r18 SEQUENCE {

maxNumberJointTCI-PerCell-r18 ENUMERATED
{n8,n12,n16,n24,n32,n48,n64,n128},

qcl-Resource-r18 ENUMERATED {ssb, trs, both},

maxNumberJointTCI-AcrossCells-r18 INTEGER (1..128),

maxNumberCells-r18 INTEGER (1..8)

} OPTIONAL,

dummy-ltm-MAC-CE-JointTCI-r18 SEQUENCE {

qcl-Resource-r18 ENUMERATED {ssb, trs, both},

maxNumberJointTCI-PerCell-r18 INTEGER (1..16),

maxNumberJointTCI-AcrossCells-r18 ENUMERATED {n1,n2,n3,n4,n8,n16,n32}

} OPTIONAL,

\-- R1 45-4: Beam indication with separate DL/UL LTM TCI states

ltm-BeamIndicationSeparateTCI-r18 SEQUENCE {

maxNumberDL-TCI-PerCell-r18 ENUMERATED
{n4,n8,n12,n16,n24,n32,n48,n64,n128},

maxNumberUL-TCI-PerCell-r18 ENUMERATED {n4,n8,n12,n16,n24,n32,n48,n64},

qcl-Resource-r18 ENUMERATED {ssb, trs, both},

maxNumberDL-TCI-AcrossCells-r18 INTEGER (1..128),

maxNumberUL-TCI-AcrossCells-r18 INTEGER (1..64),

maxNumberCells-r18 INTEGER (1..8)

} OPTIONAL,

dummy-ltm-MAC-CE-SeparateTCI-r18 SEQUENCE {

qcl-Resource-r18 ENUMERATED {ssb, trs, both},

maxNumberDL-TCI-PerCell-r18 INTEGER (1..8),

maxNumberUL-TCI-PerCell-r18 INTEGER (1..8),

maxNumberDL-TCI-AcrossCells-r18 ENUMERATED {n1,n2,n4,n8,n16},

maxNumberUL-TCI-AcrossCells-r18 ENUMERATED {n1,n2,n4,n8,n16}

} OPTIONAL,

\-- R1 45-5: RACH-based early TA acquisition

rach-EarlyTA-Measurement-r18 INTEGER (1..8) OPTIONAL,

\-- R1 45-6: UE-based TA measurement

ue-TA-Measurement-r18 INTEGER (1..8) OPTIONAL,

\-- R1 45-7: TA indication in cell switch command

ta-IndicationCellSwitch-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 49-8: Triggered HARQ-ACK codebook re-transmission for DCI format
1_3

triggeredHARQ-CodebookRetxDCI-1-3-r18 SEQUENCE {

minHARQ-Retx-Offset-r18 ENUMERATED {n-7, n-5, n-3, n-1, n1},

maxHARQ-Retx-Offset-r18 ENUMERATED {n4, n6, n8, n10, n12, n14, n16, n18,
n20, n22, n24}

} OPTIONAL,

\-- R1 49-12: Unified TCI with joint DL/UL TCI update by DCI format 1_3
for intra-cell and inter-cell beam management with more than

\-- one MAC-CE activated joint TCI state per CC

unifiedJointTCI-MultiMAC-CE-DCI-1-3-r18 SEQUENCE {

minBeamApplicationTime-r18 CHOICE {

fr1-r18 SEQUENCE {

scs-15kHz-r18 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70} OPTIONAL,

scs-30kHz-r18 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70} OPTIONAL,

scs-60kHz-r18 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70} OPTIONAL

},

fr2-r18 SEQUENCE {

scs-60kHz-r18 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70,

sym84, sym98, sym112, sym224, sym336} OPTIONAL,

scs-120kHz-r18 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70,

sym84, sym98, sym112, sym224, sym336} OPTIONAL

}

},

maxActivatedTCI-PerCC-r18 INTEGER (2..8) OPTIONAL

} OPTIONAL,

\-- R1 49-12a: Unified TCI with separate DL/UL TCI update by DCI format
1_3 for intra-cell beam management with more than

\-- one MAC-CE activated separate TCI state per CC

unifiedSeparateTCI-MultiMAC-CE-IntraCell-r18 SEQUENCE {

minBeamApplicationTime-r18 CHOICE {

fr1-r18 SEQUENCE {

scs-15kHz-r18 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70,

sym84, sym98, sym112, sym224, sym336} OPTIONAL,

scs-30kHz-r18 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70,

sym84, sym98, sym112, sym224, sym336} OPTIONAL,

scs-60kHz-r18 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70,

sym84, sym98, sym112, sym224, sym336} OPTIONAL

},

fr2-r18 SEQUENCE {

scs-60kHz-r18 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70,

sym84, sym98, sym112, sym224, sym336} OPTIONAL,

scs-120kHz-r18 ENUMERATED {sym1, sym2, sym4, sym7, sym14, sym28, sym42,
sym56, sym70,

sym84, sym98, sym112, sym224, sym336} OPTIONAL

}

},

maxActivatedDL-TCI-PerCC-r18 INTEGER (2..8) OPTIONAL,

maxActivatedUL-TCI-PerCC-r18 INTEGER (2..8) OPTIONAL

} OPTIONAL,

\-- R1 50-1: Multi-PUSCHs for Configured Grant

multiPUSCH-CG-r18 ENUMERATED {n16, n32} OPTIONAL,

\-- R1 50-1a: Multiple active multi-PUSCHs configured grant
configurations for a BWP of a serving cell

multiPUSCH-ActiveConfiguredGrant-r18 SEQUENCE {

maxNumberConfigsPerBWP ENUMERATED {n1, n2, n4, n8, n12},

maxNumberConfigsAllCC-FR1 INTEGER (2..32),

maxNumberConfigsAllCC-FR2 INTEGER (2..32)

} OPTIONAL,

\-- R1 50-1b: Joint release in a DCI for two or more configured grant
Type 2 configurations, including multi-PUSCH CG

\-- configuration(s), for a given BWP of a serving cell

jointReleaseDCI-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 50-2: UCI indication of unused CG-PUSCH transmission occasions

cg-PUSCH-UTO-UCI-Ind-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 50-3: PDCCH monitoring resumption after UL NACK

pdcch-MonitoringResumptionAfterUL-NACK-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 51-1: Support for 3 MHz symmetric channel bandwidth in DL and UL

support3MHz-ChannelBW-Symmetric-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 51-1a: Support for 3 MHz channel bandwidth in uplink with larger
than 3 MHz channel BW in DL

support3MHz-ChannelBW-Asymmetric-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 51-2a: support 12 PRB CORESET0

support12PRB-CORESET0-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 52-1: Reception of NR PDCCH candidates overlapping with LTE CRS
REs

nr-PDCCH-OverlapLTE-CRS-RE-r18 SEQUENCE {

overlapInRE-r18 ENUMERATED {oneSymbolNoOverlap, someOrAllSymOverlap},

overlapInSymbol-r18 ENUMERATED {symbol2,symbol1And2}

} OPTIONAL,

\-- R1 52-1a: Reception of NR PDCCH candidates overlapping with LTE CRS
REs with multiple non-overlapping CRS rate matching patterns

nr-PDCCH-OverlapLTE-CRS-RE-MultiPatterns-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 52-1b: NR PDCCH reception that overlaps with LTE CRS within a
single span of 3 consecutive OFDM symbols that is within the

\-- first 4 OFDM symbols in a slot

nr-PDCCH-OverlapLTE-CRS-RE-Span-3-4-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 52-2: Two LTE-CRS overlapping rate matching patterns within NR 15
kHz carrier overlapping with LTE carrier (regardless of

\-- support or configuration of multi-TRP)

twoRateMatchingEUTRA-CRS-patterns-3-4-r18 SEQUENCE {

maxNumberPatterns-r18 INTEGER (2..6),

maxNumberNon-OverlapPatterns-r18 INTEGER (1..3)

} OPTIONAL,

\-- R1 52-2a: Two LTE-CRS overlapping rate matching patterns with two
different values of coresetPoolIndex within NR 15 kHz carrier

\-- overlapping with LTE carrier

overlapRateMatchingEUTRA-CRS-Patterns-3-4-Diff-CS-Pool-r18 ENUMERATED
{supported} OPTIONAL,

\-- R1 53-3: Support RLM/BM/BFD measurements based on NCD-SSB within
active BWP

ncd-SSB-BWP-Wor-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 53-4: Support Support RLM/BM/BFD measurements based on CSI-RS
when CD-SSB is outside active BWP

rlm-BM-BFD-CSI-RS-OutsideActiveBWP-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 54-1: PRACH coverage enhancements

prach-CoverageEnh-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 54-1a: PRACH repetitions with less than N symbols gap

prach-Repetition-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 54-3: Dynamic waveform switching

dynamicWaveformSwitch-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 54-3a: PHR enhancement for dynamic waveform switching

dynamicWaveformSwitchPHR-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 54-3b: Dynamic waveform switching for intra-band UL CA

dynamicWaveformSwitchIntraCA-r18 INTEGER (2..8) OPTIONAL,

\-- R1 55-3: Multiple PUSCHs scheduling by single DCI for
non-consecutive slots in FR1

multiPUSCH-SingleDCI-NonConsSlots-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 55-2d: single-symbol DL-PRS used in RTT-based Propagation delay
compensation

pdc-maxNumberPRS-ResourceProcessedPerSlot-r18 SEQUENCE {

fr1-r18 SEQUENCE {

scs-15kHz-r18 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48,
n64} OPTIONAL,

scs-30kHz-r18 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48,
n64} OPTIONAL,

scs-60kHz-r18 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48,
n64} OPTIONAL

},

fr2-r18 SEQUENCE {

scs-60kHz-r18 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48,
n64} OPTIONAL,

scs-120kHz-r18 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48,
n64} OPTIONAL

}

} OPTIONAL,

\-- R1 57-2: Intra-slot TDM-ed unicast PDSCH and group-common PDSCH for
multicast in RRC_INACTIVE state

intraSlot-PDSCH-MulticastInactive-r18 BOOLEAN OPTIONAL,

\-- R1 57-1: Dynamic scheduling for multicast in RRC_INACTIVE state

multicastInactive-r18 ENUMERATED {supported} OPTIONAL,

thresholdBasedMulticastResume-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 27-2: LowerMSD for inter-band NR CA and EN-DC

lowerMSD-r18 SEQUENCE (SIZE (1..maxLowerMSD-r18)) OF LowerMSD-r18
OPTIONAL,

lowerMSD-ENDC-r18 SEQUENCE (SIZE (1..maxLowerMSD-r18)) OF LowerMSD-r18
OPTIONAL,

\-- R4 28-1: Enhanced channel raster

enhancedChannelRaster-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 30-2: Fast beam sweeping for layer-1 measurement when the UE is
in multi-Rx operation

fastBeamSweepingMultiRx-r18 ENUMERATED {n2,n4,n6} OPTIONAL,

\-- R4 31-2 Beam sweeping factor reduction for FR2 unknown SCell
activation

beamSweepingFactorReduction-r18 SEQUENCE {

reduceForCellDetection ENUMERATED {n1, n2, n4, n6},

reduceForSSB-L1-RSRP-Meas INTEGER (0..7)

} OPTIONAL,

\-- R4 34-1: Support of NR FR2 HST with simultaneous DL reception with
two different QCL TypeD RSs

simultaneousReceptionTwoQCL-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 34-2: Enhanced FR2 HST RRM requirements for intra-band CA and
inter-frequency measurements in connected mode

measEnhCAInterFreqFR2-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 34-4: Support of enhanced MAC CE for TCI state switch indication
for FR2 HST

tci-StateSwitchInd-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 35-2: the requirements defined for ATG UE with antenna array or
omni-direction antenna requirements.

antennaArrayType-r18 ENUMERATED {supported} OPTIONAL,

locationBasedCondHandoverATG-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 35-3: rated maximum output power value range from 23dBm to 40dBm
with 1dB as granularity at maximum modulation order and full

\-- PRB configurations.

maxOutputPowerATG-r18 INTEGER (1..18) OPTIONAL,

\-- R4 39-6: Fast processing of LTM candidate cell RRC configuration

ltm-FastProcessingConfig-r18 SEQUENCE {

maxNumberStoredConfigCells-r18 ENUMERATED
{n2,n3,n4,n5,n6,n7,n8,n9,n10,n11,n12,n16},

maxNumberConfigs-r18 INTEGER (1..4)

} OPTIONAL,

\-- R4 39-8: Measurement validation based on EMR measurement during
connection setup/resume

measValidationReportEMR-r18 ENUMERATED {supported} OPTIONAL,

\-- R4 39-9: Measurement validation based on reselection measurement
during connection setup/resume

measValidationReportReselectionMeasurements-r18 ENUMERATED {supported}
OPTIONAL,

eventA4BasedCondHandoverNES-r18 ENUMERATED {supported} OPTIONAL,

nesBasedCondHandoverWithDCI-r18 ENUMERATED {supported} OPTIONAL,

rach-LessHandoverCG-r18 ENUMERATED {supported} OPTIONAL,

rach-LessHandoverDG-r18 ENUMERATED {supported} OPTIONAL,

locationBasedCondHandoverEMC-r18 ENUMERATED {supported} OPTIONAL,

mt-CG-SDT-r18 ENUMERATED {supported} OPTIONAL,

posSRS-PreconfigureRRC-InactiveInitialUL-BWP-r18 ENUMERATED {supported}
OPTIONAL,

posSRS-PreconfigureRRC-InactiveOutsideInitialUL-BWP-r18 ENUMERATED
{supported} OPTIONAL,

cg-SDT-PeriodicityExt-r18 ENUMERATED {supported} OPTIONAL,

\-- R2: 2Rx XR UEs

supportOf2RxXR-r18 ENUMERATED {supported} OPTIONAL,

condHandoverWithCandSCG-change-r18 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

mac-ParametersPerBand-r18 MAC-ParametersPerBand-r18 OPTIONAL,

channelBW-DL-NCR-r18 CHOICE {

fr1-100mhz SEQUENCE {

scs-15kHz ENUMERATED {supported} OPTIONAL,

scs-30kHz ENUMERATED {supported} OPTIONAL,

scs-60kHz ENUMERATED {supported} OPTIONAL

},

fr2-200mhz SEQUENCE {

scs-60kHz ENUMERATED {supported} OPTIONAL,

scs-120kHz ENUMERATED {supported} OPTIONAL

}

} OPTIONAL,

channelBW-UL-NCR-r18 CHOICE {

fr1-100mhz SEQUENCE {

scs-15kHz ENUMERATED {supported} OPTIONAL,

scs-30kHz ENUMERATED {supported} OPTIONAL,

scs-60kHz ENUMERATED {supported} OPTIONAL

},

fr2-200mhz SEQUENCE {

scs-60kHz ENUMERATED {supported} OPTIONAL,

scs-120kHz ENUMERATED {supported} OPTIONAL

}

} OPTIONAL,

ncr-PDSCH-64QAM-FR2-r18 ENUMERATED {supported} OPTIONAL,

ltm-MCG-IntraFreq-r18 ENUMERATED {supported} OPTIONAL,

ltm-SCG-IntraFreq-r18 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 45-3a: MAC-CE activated joint LTM TCI states

ltm-MAC-CE-JointTCI-r18 SEQUENCE {

qcl-Resource-r18 ENUMERATED {ssb, trs, both},

maxNumberJointTCI-PerCell-r18 INTEGER (1..16),

maxNumberJointTCI-AcrossCells-r18 INTEGER (1..32)

} OPTIONAL,

\-- R1 45-4a: MAC-CE activated DL/UL LTM TCI states

ltm-MAC-CE-SeparateTCI-r18 SEQUENCE {

qcl-Resource-r18 ENUMERATED {ssb, trs, both},

maxNumberDL-TCI-PerCell-r18 INTEGER (1..8),

maxNumberUL-TCI-PerCell-r18 INTEGER (1..8),

maxNumberDL-TCI-AcrossCells-r18 INTEGER (1..32),

maxNumberUL-TCI-AcrossCells-r18 INTEGER (1..32)

} OPTIONAL

\]\]

}

BandNR-v16c0 ::= SEQUENCE {

pusch-RepetitionTypeA-v16c0 ENUMERATED {supported} OPTIONAL,

\...

}

BandNR-v17b0 ::= SEQUENCE {

mimo-ParametersPerBand-v17b0 MIMO-ParametersPerBand-v17b0 OPTIONAL,

\...

}

LowerMSD-r18 ::= SEQUENCE {

aggressorband1-r18 CHOICE {

nr FreqBandIndicatorNR,

eutra FreqBandIndicatorEUTRA

},

aggressorband2-r18 FreqBandIndicatorNR OPTIONAL,

msd-Information-r18 SEQUENCE (SIZE (1..maxLowerMSDInfo-r18)) OF
MSD-Information-r18

}

MSD-Information-r18 ::= SEQUENCE {

msd-Type-r18 ENUMERATED {harmonic, harmonicMixing, crossBandIsolation,
imd2, imd3, imd4, imd5, all, spare8, spare7,

spare6, spare5,spare4, spare3, spare2, spare1},

msd-PowerClass-r18 ENUMERATED {pc1dot5, pc2, pc3},

msd-Class-r18 ENUMERATED {classI, classII, classIII, classIV, classV,
classVI, classVII, classVIII }

}

\-- TAG-RF-PARAMETERS-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RF-Parameters* field descriptions                                    |
+=======================================================================+
| ***appliedFreqBandListFilter***                                       |
|                                                                       |
| In this field the UE mirrors the *FreqBandList* that the NW provided  |
| in the capability enquiry, if any, as described in clause 5.6.1.4.    |
| The UE filtered the band combinations in the                          |
| *supportedBandCombinationList* in accordance with this                |
| *appliedFreqBandListFilter*. The UE does not include this field if    |
| the UE capability is requested by E-UTRAN and the network request     |
| includes the field *eutra-nr-only* \[10\].                            |
+-----------------------------------------------------------------------+
| ***dummy1, dummy2, dummy-ltm-MAC-CE-JointTCI-r18,                     |
| dummy-ltm-MAC-CE-SeparateTCI-r18***                                   |
|                                                                       |
| The fields are not used in the specification and the network ignores  |
| the received values.                                                  |
+-----------------------------------------------------------------------+
| ***supportedBandCombinationList***                                    |
|                                                                       |
| A list of band combinations that the UE supports for NR (and NR-DC,   |
| if requested). The *FeatureSetCombinationId*:s in this list refer to  |
| the *FeatureSetCombination* entries in the *featureSetCombinations*   |
| list in the *UE-NR-Capability* IE. The UE does not include this field |
| if the UE capability is requested by E-UTRAN and the network request  |
| includes the field *eutra-nr-only* \[10\].                            |
+-----------------------------------------------------------------------+
| ***supportedBandCombinationListSidelinkEUTRA-NR***                    |
|                                                                       |
| A list of band combinations that the UE supports for NR sidelink      |
| communication only, for joint NR sidelink communication and V2X       |
| sidelink communication, or for V2X sidelink communication only. The   |
| UE does not include this field if the UE capability is requested by   |
| E-UTRAN (see TS 36.331\[10\]) and the network request includes the    |
| field *eutra-nr-only*.                                                |
+-----------------------------------------------------------------------+
| ***supportedBandCombinationListSL-NonRelayDiscovery***                |
|                                                                       |
| A list of band combinations that the UE supports for NR sidelink      |
| non-relay discovery. The encoding is defined in PC5                   |
| *BandCombinationListSidelinkNR-r16.*                                  |
+-----------------------------------------------------------------------+
| ***supportedBandCombinationListSL-RelayDiscovery***                   |
|                                                                       |
| A list of band combinations that the UE supports for NR sidelink      |
| relay discovery. The encoding is defined in PC5                       |
| *BandCombinationListSidelinkNR-r16.*                                  |
+-----------------------------------------------------------------------+
| ***supportedBandCombinationListSL-U2U-DiscoveryExt***                 |
|                                                                       |
| This field indicates the band parameter in                            |
| *BandCombinationListSL-Discovery-r17* that the UE supports for NR U2U |
| sidelink relay discovery in a band included in                        |
| *supportedBandCombinationListSL-U2U-RelayDiscovery*.                  |
+-----------------------------------------------------------------------+
| ***supportedBandCombinationListSL-U2U-RelayDiscovery***               |
|                                                                       |
| A list of band combinations that the UE supports for NR U2U sidelink  |
| relay discovery. The encoding is defined in PC5                       |
| *BandCombinationListSidelinkNR-r16.*                                  |
+-----------------------------------------------------------------------+
| ***supportedBandCombinationList-UplinkTxSwitch***                     |
|                                                                       |
| A list of band combinations that the UE supports dynamic uplink Tx    |
| switching for NR UL CA and SUL. The *FeatureSetCombinationId*:s in    |
| this list refer to the *FeatureSetCombination* entries in the         |
| *featureSetCombinations* list in the *UE-NR-Capability* IE. The UE    |
| does not include this field if the UE capability is requested by      |
| E-UTRAN and the network request includes the field *eutra-nr-only*    |
| \[10\].                                                               |
+-----------------------------------------------------------------------+
| ***supportedBandListNR***                                             |
|                                                                       |
| A list of NR bands supported by the UE. If                            |
| *supportedBandListNR-v16c0* is included, the UE shall include the     |
| same number of entries, and listed in the same order, as in           |
| *supportedBandListNR* (without suffix).                               |
+-----------------------------------------------------------------------+

#### -- *RF-ParametersMRDC*

The IE *RF-ParametersMRDC* is used to convey RF related capabilities for
MR-DC.

*RF-ParametersMRDC* information element

\-- ASN1START

\-- TAG-RF-PARAMETERSMRDC-START

RF-ParametersMRDC ::= SEQUENCE {

supportedBandCombinationList BandCombinationList OPTIONAL,

appliedFreqBandListFilter FreqBandList OPTIONAL,

\...,

\[\[

srs-SwitchingTimeRequested ENUMERATED {true} OPTIONAL,

supportedBandCombinationList-v1540 BandCombinationList-v1540 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1550 BandCombinationList-v1550 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1560 BandCombinationList-v1560 OPTIONAL,

supportedBandCombinationListNEDC-Only BandCombinationList OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1570 BandCombinationList-v1570 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1580 BandCombinationList-v1580 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1590 BandCombinationList-v1590 OPTIONAL

\]\],

\[\[

supportedBandCombinationListNEDC-Only-v15a0 SEQUENCE {

supportedBandCombinationList-v1540 BandCombinationList-v1540 OPTIONAL,

supportedBandCombinationList-v1560 BandCombinationList-v1560 OPTIONAL,

supportedBandCombinationList-v1570 BandCombinationList-v1570 OPTIONAL,

supportedBandCombinationList-v1580 BandCombinationList-v1580 OPTIONAL,

supportedBandCombinationList-v1590 BandCombinationList-v1590 OPTIONAL

} OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1610 BandCombinationList-v1610 OPTIONAL,

supportedBandCombinationListNEDC-Only-v1610 BandCombinationList-v1610
OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-r16
BandCombinationList-UplinkTxSwitch-r16 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1630 BandCombinationList-v1630 OPTIONAL,

supportedBandCombinationListNEDC-Only-v1630 BandCombinationList-v1630
OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1630
BandCombinationList-UplinkTxSwitch-v1630 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1640 BandCombinationList-v1640 OPTIONAL,

supportedBandCombinationListNEDC-Only-v1640 BandCombinationList-v1640
OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1640
BandCombinationList-UplinkTxSwitch-v1640 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-UplinkTxSwitch-v1670
BandCombinationList-UplinkTxSwitch-v1670 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1700 BandCombinationList-v1700 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1700
BandCombinationList-UplinkTxSwitch-v1700 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1720 BandCombinationList-v1720 OPTIONAL,

supportedBandCombinationListNEDC-Only-v1720 SEQUENCE {

supportedBandCombinationList-v1700 BandCombinationList-v1700 OPTIONAL,

supportedBandCombinationList-v1720 BandCombinationList-v1720 OPTIONAL

} OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1720
BandCombinationList-UplinkTxSwitch-v1720 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1730 BandCombinationList-v1730 OPTIONAL,

supportedBandCombinationListNEDC-Only-v1730 BandCombinationList-v1730
OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1730
BandCombinationList-UplinkTxSwitch-v1730 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1740 BandCombinationList-v1740 OPTIONAL,

supportedBandCombinationListNEDC-Only-v1740 BandCombinationList-v1740
OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1740
BandCombinationList-UplinkTxSwitch-v1740 OPTIONAL

\]\],

\[\[

dummy1 BandCombinationList-v1770 OPTIONAL,

dummy2 BandCombinationList-UplinkTxSwitch-v1770 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1780 BandCombinationList-v1780 OPTIONAL,

supportedBandCombinationListNEDC-Only-v1780 BandCombinationList-v1780
OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1780
BandCombinationList-UplinkTxSwitch-v1780 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1790 BandCombinationList-v1790 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1790
BandCombinationList-UplinkTxSwitch-v1790 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1800 BandCombinationList-v1800 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1800
BandCombinationList-UplinkTxSwitch-v1800 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1830 BandCombinationList-v1830 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1830
BandCombinationList-UplinkTxSwitch-v1830 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1840 BandCombinationList-v1840 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1840
BandCombinationList-UplinkTxSwitch-v1840 OPTIONAL

\]\],

\[\[

supportedBandCombinationList-v1860 BandCombinationList-v1860 OPTIONAL,

supportedBandCombinationList-UplinkTxSwitch-v1860
BandCombinationList-UplinkTxSwitch-v1860 OPTIONAL

\]\]

}

RF-ParametersMRDC-v15g0 ::= SEQUENCE {

supportedBandCombinationList-v15g0 BandCombinationList-v15g0 OPTIONAL,

supportedBandCombinationListNEDC-Only-v15g0 BandCombinationList-v15g0
OPTIONAL

}

RF-ParametersMRDC-v15n0 ::= SEQUENCE {

supportedBandCombinationList-v15n0 BandCombinationList-v15n0 OPTIONAL

}

RF-ParametersMRDC-v16e0 ::= SEQUENCE {

supportedBandCombinationList-UplinkTxSwitch-v16e0
BandCombinationList-UplinkTxSwitch-v16e0 OPTIONAL

}

\-- TAG-RF-PARAMETERSMRDC-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *RF-ParametersMRDC* field descriptions                                |
+=======================================================================+
| ***appliedFreqBandListFilter***                                       |
|                                                                       |
| In this field the UE mirrors the *FreqBandList* that the NW provided  |
| in the capability enquiry, if any. The UE filtered the band           |
| combinations in the *supportedBandCombinationList* in accordance with |
| this *appliedFreqBandListFilter*.                                     |
+-----------------------------------------------------------------------+
| ***dummy1, dummy2***                                                  |
|                                                                       |
| The fields are not used in the specification and the network ignores  |
| the received values.                                                  |
+-----------------------------------------------------------------------+
| ***supportedBandCombinationList***                                    |
|                                                                       |
| A list of band combinations that the UE supports for (NG)EN-DC, or    |
| both (NG)EN-DC and NE-DC. The *FeatureSetCombinationId*:s in this     |
| list refer to the *FeatureSetCombination* entries in the              |
| *featureSetCombinations* list in the *UE-MRDC-Capability* IE.         |
+-----------------------------------------------------------------------+
| ***supportedBandCombinationListNEDC-Only,                             |
| supportedBandCombinationListNEDC-Only-v1610,                          |
| supportedBandCombinationListNEDC-Only-v1780***                        |
|                                                                       |
| A list of band combinations that the UE supports only for NE-DC. The  |
| *FeatureSetCombinationId*:s in this list refer to the                 |
| *FeatureSetCombination* entries in the *featureSetCombinations* list  |
| in the *UE-MRDC-Capability* IE.                                       |
+-----------------------------------------------------------------------+
| ***supportedBandCombinationList-UplinkTxSwitch***                     |
|                                                                       |
| A list of band combinations that the UE supports dynamic UL Tx        |
| switching for (NG)EN-DC. The *FeatureSetCombinationId*:s in this list |
| refer to the *FeatureSetCombination* entries in the                   |
| *featureSetCombinations* list in the *UE-MRDC-Capability* IE.         |
+-----------------------------------------------------------------------+

#### -- *RLC-Parameters*

The IE *RLC-Parameters* is used to convey capabilities related to RLC.

*RLC-Parameters* information element

\-- ASN1START

\-- TAG-RLC-PARAMETERS-START

RLC-Parameters ::= SEQUENCE {

am-WithShortSN ENUMERATED {supported} OPTIONAL,

um-WithShortSN ENUMERATED {supported} OPTIONAL,

um-WithLongSN ENUMERATED {supported} OPTIONAL,

\...,

\[\[

extendedT-PollRetransmit-r16 ENUMERATED {supported} OPTIONAL,

extendedT-StatusProhibit-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

am-WithLongSN-RedCap-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

am-WithLongSN-NCR-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

\-- TAG-RLC-PARAMETERS-STOP

\-- ASN1STOP

#### -- *SDAP-Parameters*

The IE *SDAP-Parameters* is used to convey capabilities related to SDAP.

*SDAP-Parameters* information element

\-- ASN1START

\-- TAG-SDAP-PARAMETERS-START

SDAP-Parameters ::= SEQUENCE {

as-ReflectiveQoS ENUMERATED {true} OPTIONAL,

\...,

\[\[

sdap-QOS-IAB-r16 ENUMERATED {supported} OPTIONAL,

sdapHeaderIAB-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

sdap-QOS-NCR-r18 ENUMERATED {supported} OPTIONAL,

sdap-HeaderNCR-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

\-- TAG-SDAP-PARAMETERS-STOP

\-- ASN1STOP

#### -- *SharedSpectrumChAccessParamsPerBand*

The IE *SharedSpectrumChAccessParamsPerBand* is used to convey shared
channel access related parameters specific for a certain frequency band
(not per feature set or band combination).

*SharedSpectrumChAccessParamsPerBand* information element

\-- ASN1START

\-- TAG-SHAREDSPECTRUMCHACCESSPARAMSPERBAND-START

SharedSpectrumChAccessParamsPerBand-r16 ::= SEQUENCE {

\-- R1 10-1: UL channel access for dynamic channel access mode

ul-DynamicChAccess-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-1a: UL channel access for semi-static channel access mode

ul-Semi-StaticChAccess-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-2: SSB-based RRM for dynamic channel access mode

ssb-RRM-DynamicChAccess-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-2a: SSB-based RRM for semi-static channel access mode

ssb-RRM-Semi-StaticChAccess-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-2b: MIB reading on unlicensed cell

mib-Acquisition-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-2c: SSB-based RLM for dynamic channel access mode

ssb-RLM-DynamicChAccess-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-2d: SSB-based RLM for semi-static channel access mode

ssb-RLM-Semi-StaticChAccess-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-2e: SIB1 reception on unlicensed cell

sib1-Acquisition-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-2f: Support monitoring of extended RAR window

extRA-ResponseWindow-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-2g: SSB-based BFD/CBD for dynamic channel access mode

ssb-BFD-CBD-dynamicChannelAccess-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-2h: SSB-based BFD/CBD for semi-static channel access mode

ssb-BFD-CBD-semi-staticChannelAccess-r16 ENUMERATED {supported}
OPTIONAL,

\-- R1 10-2i: CSI-RS-based BFD/CBD for NR-U

csi-RS-BFD-CBD-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-7: UL channel access for 10 MHz SCell

ul-ChannelBW-SCell-10mhz-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-10: RSSI and channel occupancy measurement and reporting

rssi-ChannelOccupancyReporting-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-11:SRS starting position at any OFDM symbol in a slot

srs-StartAnyOFDM-Symbol-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-20: Support search space set configuration with
freqMonitorLocation-r16

searchSpaceFreqMonitorLocation-r16 INTEGER (1..5) OPTIONAL,

\-- R1 10-20a: Support coreset configuration with rb-Offset

coreset-RB-Offset-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-23:CGI reading on unlicensed cell for ANR functionality

cgi-Acquisition-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-25: Enable configured UL transmissions when DCI 2_0 is
configured but not detected

configuredUL-Tx-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-27: Wideband PRACH

prach-Wideband-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-29: Support available RB set indicator field in DCI 2_0

dci-AvailableRB-Set-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-30: Support channel occupancy duration indicator field in DCI
2_0

dci-ChOccupancyDuration-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-8: Type B PDSCH length {3, 5, 6, 8, 9, 10, 11, 12, 13} without
DMRS shift due to CRS collision

typeB-PDSCH-length-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-9: Search space set group switching with explicit DCI 2_0 bit
field trigger or with implicit PDCCH decoding with DCI 2_0 monitoring

searchSpaceSwitchWithDCI-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-9b: Search space set group switching with implicit PDCCH
decoding without DCI 2_0 monitoring

searchSpaceSwitchWithoutDCI-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-9d: Support Search space set group switching capability 2

searchSpaceSwitchCapability2-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-14: Non-numerical PDSCH to HARQ-ACK timing

non-numericalPDSCH-HARQ-timing-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-15: Enhanced dynamic HARQ codebook

enhancedDynamicHARQ-codebook-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-16: One-shot HARQ ACK feedback

oneShotHARQ-feedback-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-17: Multi-PUSCH UL grant

multiPUSCH-UL-grant-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-26: CSI-RS based RLM for NR-U

csi-RS-RLM-r16 ENUMERATED {supported} OPTIONAL,

dummy ENUMERATED {supported} OPTIONAL,

\-- R1 10-31: Support of P/SP-CSI-RS reception with
CSI-RS-ValidationWith-DCI-r16 configured

periodicAndSemi-PersistentCSI-RS-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-3: PRB interlace mapping for PUSCH

pusch-PRB-interlace-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-3a: PRB interlace mapping for PUCCH

pucch-F0-F1-PRB-Interlace-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-12: OCC for PRB interlace mapping for PF2 and PF3

occ-PRB-PF2-PF3-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-13a: Extended CP range of more than one symbol for CG-PUSCH

extCP-rangeCG-PUSCH-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-18: Configured grant with retransmission in CG resources

configuredGrantWithReTx-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-21a: Support using ED threshold given by gNB for UL to DL COT
sharing

ed-Threshold-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-21b: Support UL to DL COT sharing

ul-DL-COT-Sharing-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-24: CG-UCI multiplexing with HARQ ACK

mux-CG-UCI-HARQ-ACK-r16 ENUMERATED {supported} OPTIONAL,

\-- R1 10-28: Configured grant with Rel-16 enhanced resource
configuration

cg-resourceConfig-r16 ENUMERATED {supported} OPTIONAL

}

SharedSpectrumChAccessParamsPerBand-v1630 ::= SEQUENCE {

\-- R4 4-1: DL reception in intra-carrier guardband

dl-ReceptionIntraCellGuardband-r16 ENUMERATED {supported} OPTIONAL,

\-- R4 4-2: DL reception when gNB does not transmit on all RB sets of a
carrier as a result of LBT

dl-ReceptionLBT-subsetRB-r16 ENUMERATED {supported} OPTIONAL

}

SharedSpectrumChAccessParamsPerBand-v1640 ::= SEQUENCE {

\-- 10-26b(1-4): CSI-RS based RRM measurement with associated SS-block

csi-RSRP-AndRSRQ-MeasWithSSB-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-26c(1-5): CSI-RS based RRM measurement without associated
SS-block

csi-RSRP-AndRSRQ-MeasWithoutSSB-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-26d(1-6): CSI-RS based RS-SINR measurement

csi-SINR-Meas-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-26e(1-8): RLM based on a mix of SS block and CSI-RS signals
within active BWP

ssb-AndCSI-RS-RLM-r16 ENUMERATED {supported} OPTIONAL,

\-- 10-26f(1-9): CSI-RS based contention free RA for HO

csi-RS-CFRA-ForHO-r16 ENUMERATED {supported} OPTIONAL

}

SharedSpectrumChAccessParamsPerBand-v1650 ::= SEQUENCE {

\-- Extension of R1 10-9 capability to configure up to 16 instead of 4
cells or cell groups, respectively

extendedSearchSpaceSwitchWithDCI-r16 ENUMERATED {supported} OPTIONAL

}

SharedSpectrumChAccessParamsPerBand-v1710 ::= SEQUENCE {

\-- R1 25-12: UE initiated semi-static channel occupancy with dependent
configurations

ul-Semi-StaticChAccessDependentConfig-r17 ENUMERATED {supported}
OPTIONAL,

\-- R1 25-13: UE initiated semi-static channel occupancy with
independent configurations

ul-Semi-StaticChAccessIndependentConfig-r17 ENUMERATED {supported}
OPTIONAL

}

\-- TAG-SHAREDSPECTRUMCHACCESSPARAMSPERBAND-STOP

\-- ASN1STOP

#### -- S*haredSpectrumChAccessParamsSidelinkPerBand*

The IE *SharedSpectrumChAccessParamsSidelinkPerBand* is used to convey
shared channel access related parameters related to NR sidelink
communication, specific for a certain frequency band (not per feature
set or band combination).

*SharedSpectrumChAccessParamsSidelinkPerBand* information element

\-- ASN1START

\-- TAG-SHAREDSPECTRUMCHACCESSPARAMSSIDELINKPERBAND-START

SharedSpectrumChAccessParamsSidelinkPerBand-r18 ::= SEQUENCE {

\-- R1 47-k1: SL channel access for dynamic channel access mode

sl-DynamicChannelAccess-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-k2: SL multi-channel access for dynamic channel access mode

sl-DynamicMultiChannelAccess-r18 INTEGER (2..5) OPTIONAL,

\-- R1 47-k6: Type1 LBT blocking Option 1

sl-LBT-Option1-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-k7: Type1 LBT blocking Option 2

sl-LBT-Option2-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-k9: Sidelink mode 1 resource allocation in shared spectrum

sl-ResourceAllocMode1-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-m1: Interlace RB-based SL transmission/reception

sl-Interlace-RB-TxRx-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-m5: Multiple PSFCH occasions per PSCCH/PSSCH

sl-PSFCH-MultiOccasion-r18 INTEGER (1..4) OPTIONAL,

\-- R1 47-m10: Contiguous RB-based PSCCH/PSSCH transmission/reception

sl-ContiguousRB-TxRx-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-m11: PSFCH transmissions in multiple contiguous RB sets

sl-PSFCH-MultiContiguousRB-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-m11a: PSFCH transmissions in multiple non-contiguous RB sets

sl-PSFCH-MultiNonContiguousRB-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-m13: Transmissions/receptions of multiple dedicated PRBs in
common interlace-based PSFCH

sl-MultiplePRB-CommonInterlacePSFCH-r18 SEQUENCE {

tx-TotalPRB-PSFCH-r18 ENUMERATED {n4, n5, n8, n15, n16, n20},

rx-TotalPRB-PSFCH-r18 ENUMERATED {n5, n6, n15, n16, n25, n26, n32, n35,
n45, n46, n50, n64, n65}

} OPTIONAL,

\-- R1 47-m13a: Transmissions/receptions of multiple interlaces in
dedicated interlace-based PSFCH

sl-MultiplePRB-DedicatedInterlacePSFCH-r18 SEQUENCE {

tx-TotalPRB-PSFCH-r18 INTEGER (1..3),

rx-TotalPRB-PSFCH-r18 INTEGER (1..5)

} OPTIONAL

}

\-- TAG-SHAREDSPECTRUMCHACCESSPARAMSSIDELINKPERBAND-STOP

\-- ASN1STOP

#### -- *SidelinkParameters*

The IE *SidelinkParameters* is used to convey capabilities related to NR
and V2X sidelink communications/positioning.

*SidelinkParameters* information element

\-- ASN1START

\-- TAG-SIDELINKPARAMETERS-START

SidelinkParameters-r16 ::= SEQUENCE {

sidelinkParametersNR-r16 SidelinkParametersNR-r16 OPTIONAL,

sidelinkParametersEUTRA-r16 SidelinkParametersEUTRA-r16 OPTIONAL

}

SidelinkParametersNR-r16 ::= SEQUENCE {

rlc-ParametersSidelink-r16 RLC-ParametersSidelink-r16 OPTIONAL,

mac-ParametersSidelink-r16 MAC-ParametersSidelink-r16 OPTIONAL,

fdd-Add-UE-Sidelink-Capabilities-r16
UE-SidelinkCapabilityAddXDD-Mode-r16 OPTIONAL,

tdd-Add-UE-Sidelink-Capabilities-r16
UE-SidelinkCapabilityAddXDD-Mode-r16 OPTIONAL,

supportedBandListSidelink-r16 SEQUENCE (SIZE (1..maxBands)) OF
BandSidelink-r16 OPTIONAL,

\...,

\[\[

relayParameters-r17 RelayParameters-r17 OPTIONAL

\]\],

\[\[

\-- R1 32-x: Use of new P0 parameters for open loop power control

p0-OLPC-Sidelink-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

pdcp-ParametersSidelink-r18 PDCP-ParametersSidelink-r18 OPTIONAL,

\--R1 41-1-1a: Common SL-PRS processing capability

sl-PRS-CommonProcCapabilityPerUE-r18 SEQUENCE {

maxNumOfActiveSL-PRS-Resources-r18 SEQUENCE {

fr1-r18 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24} OPTIONAL,

fr2-r18 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48, n64,
n128} OPTIONAL

},

maxNumOfSlotswithActiveSL-PRS-Resources-r18 SEQUENCE {

fr1-r18 ENUMERATED {n1, n2, n3, n4, n6, n8} OPTIONAL,

fr2-r18 ENUMERATED {n1, n2, n4, n8, n12, n16, n24, n32, n48, n64}
OPTIONAL

}

} OPTIONAL

\]\]

}

SidelinkParametersEUTRA-r16 ::= SEQUENCE {

sl-ParametersEUTRA1-r16 OCTET STRING OPTIONAL,

sl-ParametersEUTRA2-r16 OCTET STRING OPTIONAL,

sl-ParametersEUTRA3-r16 OCTET STRING OPTIONAL,

supportedBandListSidelinkEUTRA-r16 SEQUENCE (SIZE (1..maxBandsEUTRA)) OF
BandSidelinkEUTRA-r16 OPTIONAL,

\...

}

RLC-ParametersSidelink-r16 ::= SEQUENCE {

am-WithLongSN-Sidelink-r16 ENUMERATED {supported} OPTIONAL,

um-WithLongSN-Sidelink-r16 ENUMERATED {supported} OPTIONAL,

\...

}

MAC-ParametersSidelink-r16 ::= SEQUENCE {

mac-ParametersSidelinkCommon-r16 MAC-ParametersSidelinkCommon-r16
OPTIONAL,

mac-ParametersSidelinkXDD-Diff-r16 MAC-ParametersSidelinkXDD-Diff-r16
OPTIONAL,

\...

}

UE-SidelinkCapabilityAddXDD-Mode-r16 ::= SEQUENCE {

mac-ParametersSidelinkXDD-Diff-r16 MAC-ParametersSidelinkXDD-Diff-r16
OPTIONAL

}

MAC-ParametersSidelinkCommon-r16 ::= SEQUENCE {

lcp-RestrictionSidelink-r16 ENUMERATED {supported} OPTIONAL,

multipleConfiguredGrantsSidelink-r16 ENUMERATED {supported} OPTIONAL,

\...,

\[\[

drx-OnSidelink-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

sl-LBT-FailureDectectionRecovery-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

MAC-ParametersSidelinkXDD-Diff-r16 ::= SEQUENCE {

multipleSR-ConfigurationsSidelink-r16 ENUMERATED {supported} OPTIONAL,

logicalChannelSR-DelayTimerSidelink-r16 ENUMERATED {supported} OPTIONAL,

\...

}

BandSidelinkEUTRA-r16 ::= SEQUENCE {

freqBandSidelinkEUTRA-r16 FreqBandIndicatorEUTRA,

\-- R1 15-7: Transmitting LTE sidelink mode 3 scheduled by NR Uu

gnb-ScheduledMode3SidelinkEUTRA-r16 SEQUENCE {

gnb-ScheduledMode3DelaySidelinkEUTRA-r16 ENUMERATED {ms0, ms0dot25,
ms0dot5, ms0dot625, ms0dot75, ms1,

ms1dot25, ms1dot5, ms1dot75, ms2, ms2dot5, ms3, ms4,

ms5, ms6, ms8, ms10, ms20}

} OPTIONAL,

\-- R1 15-9: Transmitting LTE sidelink mode 4 configured by NR Uu

gnb-ScheduledMode4SidelinkEUTRA-r16 ENUMERATED {supported} OPTIONAL

}

BandSidelink-r16 ::= SEQUENCE {

freqBandSidelink-r16 FreqBandIndicatorNR,

\--15-1

sl-Reception-r16 SEQUENCE {

harq-RxProcessSidelink-r16 ENUMERATED {n16, n24, n32, n48, n64},

pscch-RxSidelink-r16 ENUMERATED {value1, value2},

scs-CP-PatternRxSidelink-r16 CHOICE {

fr1-r16 SEQUENCE {

scs-15kHz-r16 BIT STRING (SIZE (16)) OPTIONAL,

scs-30kHz-r16 BIT STRING (SIZE (16)) OPTIONAL,

scs-60kHz-r16 BIT STRING (SIZE (16)) OPTIONAL

},

fr2-r16 SEQUENCE {

scs-60kHz-r16 BIT STRING (SIZE (16)) OPTIONAL,

scs-120kHz-r16 BIT STRING (SIZE (16)) OPTIONAL

}

} OPTIONAL,

extendedCP-RxSidelink-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\--15-2

sl-TransmissionMode1-r16 SEQUENCE {

harq-TxProcessModeOneSidelink-r16 ENUMERATED {n8, n16},

scs-CP-PatternTxSidelinkModeOne-r16 CHOICE {

fr1-r16 SEQUENCE {

scs-15kHz-r16 BIT STRING (SIZE (16)) OPTIONAL,

scs-30kHz-r16 BIT STRING (SIZE (16)) OPTIONAL,

scs-60kHz-r16 BIT STRING (SIZE (16)) OPTIONAL

},

fr2-r16 SEQUENCE {

scs-60kHz-r16 BIT STRING (SIZE (16)) OPTIONAL,

scs-120kHz-r16 BIT STRING (SIZE (16)) OPTIONAL

}

},

extendedCP-TxSidelink-r16 ENUMERATED {supported} OPTIONAL,

harq-ReportOnPUCCH-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\--15-4

sync-Sidelink-r16 SEQUENCE {

gNB-Sync-r16 ENUMERATED {supported} OPTIONAL,

gNB-GNSS-UE-SyncWithPriorityOnGNB-ENB-r16 ENUMERATED {supported}
OPTIONAL,

gNB-GNSS-UE-SyncWithPriorityOnGNSS-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\--15-10

sl-Tx-256QAM-r16 ENUMERATED {supported} OPTIONAL,

\--15-11

psfch-FormatZeroSidelink-r16 SEQUENCE {

psfch-RxNumber ENUMERATED {n5, n15, n25, n32, n35, n45, n50, n64},

psfch-TxNumber ENUMERATED {n4, n8, n16}

} OPTIONAL,

\--15-12

lowSE-64QAM-MCS-TableSidelink-r16 ENUMERATED {supported} OPTIONAL,

\--15-15

enb-sync-Sidelink-r16 ENUMERATED {supported} OPTIONAL,

\...,

\[\[

\--15-3

sl-TransmissionMode2-r16 SEQUENCE {

harq-TxProcessModeTwoSidelink-r16 ENUMERATED {n8, n16},

scs-CP-PatternTxSidelinkModeTwo-r16 ENUMERATED {supported} OPTIONAL,

dl-openLoopPC-Sidelink-r16 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\--15-5

congestionControlSidelink-r16 SEQUENCE {

cbr-ReportSidelink-r16 ENUMERATED {supported} OPTIONAL,

cbr-CR-TimeLimitSidelink-r16 ENUMERATED {time1, time2}

} OPTIONAL,

\--15-22

fewerSymbolSlotSidelink-r16 ENUMERATED {supported} OPTIONAL,

\--15-23

sl-openLoopPC-RSRP-ReportSidelink-r16 ENUMERATED {supported} OPTIONAL,

\--13-1

sl-Rx-256QAM-r16 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

ue-PowerClassSidelink-r16 ENUMERATED {pc2, pc3, pc5-v1820, spare5,
spare4, spare3, spare2, spare1}

OPTIONAL

\]\],

\[\[

\--32-4a

sl-TransmissionMode2-RandomResourceSelection-r17 SEQUENCE {

harq-TxProcessModeTwoSidelink-r17 ENUMERATED {n8, n16},

scs-CP-PatternTxSidelinkModeTwo-r17 CHOICE {

fr1-r17 SEQUENCE {

scs-15kHz-r17 BIT STRING (SIZE (16)) OPTIONAL,

scs-30kHz-r17 BIT STRING (SIZE (16)) OPTIONAL,

scs-60kHz-r17 BIT STRING (SIZE (16)) OPTIONAL

},

fr2-r17 SEQUENCE {

scs-60kHz-r17 BIT STRING (SIZE (16)) OPTIONAL,

scs-120kHz-r17 BIT STRING (SIZE (16)) OPTIONAL

}

} OPTIONAL,

extendedCP-Mode2Random-r17 ENUMERATED {supported} OPTIONAL,

dl-openLoopPC-Sidelink-r17 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\--32-4b

sync-Sidelink-v1710 SEQUENCE {

sync-GNSS-r17 ENUMERATED {supported} OPTIONAL,

gNB-Sync-r17 ENUMERATED {supported} OPTIONAL,

gNB-GNSS-UE-SyncWithPriorityOnGNB-ENB-r17 ENUMERATED {supported}
OPTIONAL,

gNB-GNSS-UE-SyncWithPriorityOnGNSS-r17 ENUMERATED {supported} OPTIONAL

} OPTIONAL,

\--32-4c

enb-sync-Sidelink-v1710 ENUMERATED {supported} OPTIONAL,

\--32-5a-2

rx-IUC-Scheme1-PreferredMode2Sidelink-r17 ENUMERATED {supported}
OPTIONAL,

\--32-5a-3

rx-IUC-Scheme1-NonPreferredMode2Sidelink-r17 ENUMERATED {supported}
OPTIONAL,

\--32-5b-2

rx-IUC-Scheme2-Mode2Sidelink-r17 ENUMERATED {n5, n15, n25, n32, n35,
n45, n50, n64} OPTIONAL,

\--32-6-1

rx-IUC-Scheme1-SCI-r17 ENUMERATED {supported} OPTIONAL,

\--32-6-2

rx-IUC-Scheme1-SCI-ExplicitReq-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

sharedSpectrumChAccessParamsSidelinkPerBand-r18
SharedSpectrumChAccessParamsSidelinkPerBand-r18 OPTIONAL,

\--R1 41-1-1 Common SL-PRS processing capability in a SL BWP

sl-PRS-CommonProcCapabilityPerBand-r18 SEQUENCE {

maxSL-PRS-Bandwidth-r18 CHOICE {

fr1-r18 ENUMERATED {mhz5, mhz10, mhz20, mhz40, mhz50, mhz80, mhz100},

fr2-r18 ENUMERATED {mhz50, mhz100, mhz200, mhz400}

},

maxNumOfActiveSL-PRS-ResourcesInOneSlot-r18 CHOICE {

fr1-r18 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24},

fr2-r18 ENUMERATED {n1, n2, n4, n6, n8, n12, n16, n24, n32, n48, n64,
n128}

},

maxNumOfSlotsWithActiveSL-PRS-Resources-r18 CHOICE {

fr1-r18 ENUMERATED {n1, n2, n3, n4, n6, n8},

fr2-r18 ENUMERATED {n1, n2, n4, n8, n12, n16, n24, n32, n48, n64}

},

minTimeAfterEndofSlotCarryActiveSL-PRS-Resources-r18 ENUMERATED {ms20,
ms30, ms40, ms50, ms80, ms100, ms160}

} OPTIONAL,

\-- R1 41-1-2: Receiving SL-PRS in a shared resource pool

sl-PRS-RxInSharedResourcePool-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 41-1-3: Receiving SL-PRS in a dedicated resource pool

sl-PRS-RxInDedicatedResourcePool-r18 SEQUENCE {

numOfSupportedRxPSCCH-PerSlot-r18 ENUMERATED {value1, value2},

supportedCP-TypeFor60kHzSCS-r18 ENUMERATED {ncp, ncpAndECP}

} OPTIONAL,

\-- R1 41-1-4a: Transmitting SL-PRS in a shared resource pool

sl-PRS-TxInSharedResourcePool-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 41-1-4b: Transmitting SL-PRS scheme 1 in a dedicated resource
pool

sl-PRS-TxScheme1InDedicatedResourcePool-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 41-1-4c: Transmitting SL-PRS mode 2 in a dedicated resource pool

sl-PRS-TxScheme2InDedicatedResourcePool-r18 ENUMERATED {supported}
OPTIONAL,

\-- R1 41-1-5: SL-PRS congestion control in a dedicated resource pool

sl-PRS-CongestionCtrl-r18 ENUMERATED {cpt1, cpt2, cpt3} OPTIONAL,

\-- R1 41-1-8: Support of random selection in a dedicated resource pool

sl-PRS-TxRandomSelection-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 41-1-10: Support of full sensing in a dedicated resource pool

sl-PRS-TxUsingFullSensing-r18 ENUMERATED {value1, value2} OPTIONAL,

\-- R1 41-1-20: Supports SL PRS Rx for a band configured with SL CA

sl-PRS-RxForBandWithSL-CA-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 41-1-21: Supports SL PRS Tx for a band configured with SL CA

sl-PRS-TxForBandWithSL-CA-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-s1: Transmission/Reception using dynamic resource pool sharing

sl-DynamicSharingTxRx-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-v1: NR SL communication with SL CA

sl-CA-Communication-r18 SEQUENCE {

numberOfCarriers-r18 INTEGER (2..8),

numberOfPSCCH-DecodeValueZ-r18 INTEGER (1..2),

totalBandwidth-r18 ENUMERATED {mhz20,mhz30,mhz40,mhz50,mhz60,mhz70}

} OPTIONAL,

\-- R1 47-v2: Synchronization for SL CA

sl-CA-Synchronization-r18 ENUMERATED {supported} OPTIONAL,

\-- R1 47-v3: PSFCH for SL CA

sl-CA-PSFCH-r18 SEQUENCE {

rx-PSFCH-Resource-r18 ENUMERATED {n5,n15,n25,n32,n35,n45,n50,n64,n100},

tx-PSFCH-Resource-r18 ENUMERATED {n4,n8,n16,n24}

} OPTIONAL,

\-- R4 45-2: SL reception in intra-carrier guard band

sl-ReceptionIntraCarrierGuardBand-r18 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

\-- R1 41-1-17: Open loop SL pathloss based power control for SL-PRS and
associated PSCCH and SL RSRP report for dedicated

\-- resource pool

sl-PathlossBasedOLPC-SL-RSRP-Report-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

RelayParameters-r17 ::= SEQUENCE {

relayUE-Operation-L2-r17 ENUMERATED {supported} OPTIONAL,

remoteUE-Operation-L2-r17 ENUMERATED {supported} OPTIONAL,

remoteUE-PathSwitchToIdleInactiveRelay-r17 ENUMERATED {supported}
OPTIONAL,

\...,

\[\[

relayUE-U2U-OperationL2-r18 ENUMERATED {supported} OPTIONAL,

remoteUE-U2U-OperationL2-r18 ENUMERATED {supported} OPTIONAL,

remoteUE-U2N-PathSwitchOperationL2-r18 ENUMERATED {supported} OPTIONAL,

multipathRemoteUE-PC5L2-r18 ENUMERATED {supported} OPTIONAL,

multipathRelayUE-N3C-r18 ENUMERATED {supported} OPTIONAL,

multipathRemoteUE-N3C-r18 ENUMERATED {supported} OPTIONAL,

remoteUE-IndirectPathAddChangeToIdleInactiveRelay-r18 ENUMERATED
{supported} OPTIONAL,

pdcp-DuplicationMoreThanOneUuRLC-r18 ENUMERATED {supported} OPTIONAL,

pdcp-CADuplicationDirectpath-DRB-r18 ENUMERATED {supported} OPTIONAL,

pdcp-CADuplicationDirectpath-SRB-r18 ENUMERATED {supported} OPTIONAL,

pdcp-DuplicationMP-SplitDRB-r18 ENUMERATED {supported} OPTIONAL,

pdcp-DuplicationMP-SplitSRB-r18 ENUMERATED {supported} OPTIONAL,

directpathRLF-RecoveryViaSRB1-r18 ENUMERATED {supported} OPTIONAL,

splitDRB-WithUL-BothDirectIndirect-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

PDCP-ParametersSidelink-r18 ::= SEQUENCE {

pdcp-DuplicationSRB-sidelink-r18 ENUMERATED {supported} OPTIONAL,

pdcp-DuplicationDRB-sidelink-r18 ENUMERATED {supported} OPTIONAL,

\...

}

\-- TAG-SIDELINKPARAMETERS-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SidelinkParametersEUTRA* field descriptions                          |
+=======================================================================+
| ***sl-ParametersEUTRA1, sl-ParametersEUTRA2, sl-ParametersEUTRA3***   |
|                                                                       |
| This field includes IE of *SL-Parameters-v1430* (where                |
| *v2x-eNB-Scheduled-r14* and *V2X-SupportedBandCombination-r14* shall  |
| not be included), *SL-Parameters-v1530* (where                        |
| *V2X-SupportedBandCombination-r1530* shall not be included) and       |
| *SL-Parameters-v1540* respectively defined in 36.331 \[10\]. It is    |
| used for reporting the per-UE capability for V2X sidelink             |
| communication.                                                        |
+-----------------------------------------------------------------------+

#### -- *SimultaneousRxTxPerBandPair*

The IE *SimultaneousRxTxPerBandPair* contains the simultaneous Rx/Tx UE
capability for each band pair in a band combination.

***SimultaneousRxTxPerBandPair* information element**

\-- ASN1START

\-- TAG-SIMULTANEOUSRXTXPERBANDPAIR-START

SimultaneousRxTxPerBandPair ::= BIT STRING (SIZE (3..496))

\-- TAG-SIMULTANEOUSRXTXPERBANDPAIR-STOP

\-- ASN1STOP

#### -- *SON-Parameters*

The IE *SON-Parameters* contains SON related parameters.

*SON-Parameters* information element

\-- ASN1START

\-- TAG-SON-PARAMETERS-START

SON-Parameters-r16 ::= SEQUENCE {

rach-Report-r16 ENUMERATED {supported} OPTIONAL,

\...,

\[\[

rlfReportCHO-r17 ENUMERATED {supported} OPTIONAL,

rlfReportDAPS-r17 ENUMERATED {supported} OPTIONAL,

success-HO-Report-r17 ENUMERATED {supported} OPTIONAL,

twoStepRACH-Report-r17 ENUMERATED {supported} OPTIONAL,

pscell-MHI-Report-r17 ENUMERATED {supported} OPTIONAL,

onDemandSI-Report-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

cef-ReportRedCap-r17 ENUMERATED {supported} OPTIONAL,

rlf-ReportRedCap-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

spr-Report-r18 ENUMERATED {supported} OPTIONAL,

successIRAT-HO-Report-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

\-- TAG-SON-PARAMETERS-STOP

\-- ASN1STOP

#### -- *SpatialRelationsSRS-Pos*

The IE *SpatialRelationsSRS-Pos* is used to convey spatial relation for
SRS for positioning related parameters.

*SpatialRelationsSRS-Pos* information element

\-- ASN1START

\-- TAG-SPATIALRELATIONSSRS-POS-START

SpatialRelationsSRS-Pos-r16 ::= SEQUENCE {

spatialRelation-SRS-PosBasedOnSSB-Serving-r16 ENUMERATED {supported}
OPTIONAL,

spatialRelation-SRS-PosBasedOnCSI-RS-Serving-r16 ENUMERATED {supported}
OPTIONAL,

spatialRelation-SRS-PosBasedOnPRS-Serving-r16 ENUMERATED {supported}
OPTIONAL,

spatialRelation-SRS-PosBasedOnSRS-r16 ENUMERATED {supported} OPTIONAL,

spatialRelation-SRS-PosBasedOnSSB-Neigh-r16 ENUMERATED {supported}
OPTIONAL,

spatialRelation-SRS-PosBasedOnPRS-Neigh-r16 ENUMERATED {supported}
OPTIONAL

}

\--TAG-SPATIALRELATIONSSRS-POS-STOP

\-- ASN1STOP

#### -- *SRS-AllPosResourcesRRC-Inactive*

The IE *SRS-AllPosResourcesRRC-Inactive* is used to convey SRS
positioning related parameters specific for a certain band.

*SRS-AllPosResourcesRRC-Inactive* information element

\-- ASN1START

\-- TAG-SRS-ALLPOSRESOURCESRRC-INACTIVE-START

SRS-AllPosResourcesRRC-Inactive-r17 ::= SEQUENCE {

srs-PosResourcesRRC-Inactive-r17 SEQUENCE {

\-- R1 27-15: Positioning SRS transmission in RRC_INACTIVE state for
initial UL BWP

maxNumberSRS-PosResourceSetPerBWP-r17 ENUMERATED {n1, n2, n4, n8, n12,
n16},

maxNumberSRS-PosResourcesPerBWP-r17 ENUMERATED {n1, n2, n4, n8, n16,
n32, n64},

maxNumberSRS-ResourcesPerBWP-PerSlot-r17 ENUMERATED {n1, n2, n3, n4, n5,
n6, n8, n10, n12, n14},

maxNumberPeriodicSRS-PosResourcesPerBWP-r17 ENUMERATED {n1, n2, n4, n8,
n16, n32, n64},

maxNumberPeriodicSRS-PosResourcesPerBWP-PerSlot-r17 ENUMERATED {n1, n2,
n3, n4, n5, n6, n8, n10, n12, n14},

dummy1 ENUMERATED {n1, n2, n4, n8, n16, n32, n64 },

dummy2 ENUMERATED {n1, n2, n3, n4, n5, n6, n8, n10, n12, n14}

}

}

\-- TAG-SRS-ALLPOSRESOURCESRRC-INACTIVE-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SRS-AllPosResourcesRRC-Inactive* field descriptions                  |
+=======================================================================+
| ***dummy1, dummy2***                                                  |
|                                                                       |
| The fields are not used in the specification and the network ignores  |
| the received values.                                                  |
+-----------------------------------------------------------------------+

#### -- *SRS-SwitchingTimeNR*

The IE *SRS-SwitchingTimeNR* is used to indicate the SRS carrier
switching time supported by the UE for one NR band pair.

*SRS-SwitchingTimeNR information element*

\-- ASN1START

\-- TAG-SRS-SWITCHINGTIMENR-START

SRS-SwitchingTimeNR ::= SEQUENCE {

switchingTimeDL ENUMERATED {n0us, n30us, n100us, n140us, n200us, n300us,
n500us, n900us} OPTIONAL,

switchingTimeUL ENUMERATED {n0us, n30us, n100us, n140us, n200us, n300us,
n500us, n900us} OPTIONAL

}

\-- TAG-SRS-SWITCHINGTIMENR-STOP

\-- ASN1STOP

#### -- *SRS-SwitchingTimeEUTRA*

The IE *SRS-SwitchingTimeEUTRA* is used to indicate the SRS carrier
switching time supported by the UE for one E-UTRA band pair.

*SRS-SwitchingTimeEUTRA information element*

\-- ASN1START

\-- TAG-SRS-SWITCHINGTIMEEUTRA-START

SRS-SwitchingTimeEUTRA ::= SEQUENCE {

switchingTimeDL ENUMERATED {n0, n0dot5, n1, n1dot5, n2, n2dot5, n3,
n3dot5, n4, n4dot5, n5, n5dot5, n6, n6dot5, n7}

OPTIONAL,

switchingTimeUL ENUMERATED {n0, n0dot5, n1, n1dot5, n2, n2dot5, n3,
n3dot5, n4, n4dot5, n5, n5dot5, n6, n6dot5, n7}

OPTIONAL

}

\-- TAG-SRS-SWITCHINGTIMEEUTRA-STOP

\-- ASN1STOP

#### -- *SupportedAggBandwidth*

The IE *SupportedAggBandwidth* is used to indicate the aggregated
bandwidth supported by the UE.

*SupportedAggBandwidth* information element

\-- ASN1START

\-- TAG-SUPPORTEDAGGBANDWIDTH-START

SupportedAggBandwidth-r17 ::= CHOICE {

fr1-r17 ENUMERATED {mhz20, mhz30, mhz35, mhz40, mhz50, mhz60, mhz70,
mhz80, mhz90, mhz100, mhz110, mhz120, mhz130, mhz140,

mhz150, mhz160, mhz180, mhz200, mhz220, mhz230, mhz250, mhz280, mhz290,
mhz300, mhz350, mhz400, mhz450,

mhz500, mhz600, mhz700, mhz800, spare1},

fr2-r17 ENUMERATED {mhz200, mhz300, mhz400, mhz500, mhz600, mhz700,
mhz800, mhz900, mhz1000, mhz1100, mhz1200, mhz1300, mhz1400,

mhz1500, mhz1600, mhz1700, mhz1800, mhz1900, mhz2000, mhz2100, mhz2200,
mhz2300, mhz2400, spare9, spare8,

spare7, spare6, spare5, spare4, spare3, spare2, spare1}

}

\-- TAG-SUPPORTEDAGGBANDWIDTH-STOP

\-- ASN1STOP

#### -- *SupportedBandwidth*

The IE *SupportedBandwidth* is used to indicate the channel bandwidth
supported by the UE on one carrier of a band of a band combination.

*SupportedBandwidth* information element

\-- ASN1START

\-- TAG-SUPPORTEDBANDWIDTH-START

SupportedBandwidth ::= CHOICE {

fr1 ENUMERATED {mhz5, mhz10, mhz15, mhz20, mhz25, mhz30, mhz40, mhz50,
mhz60, mhz80, mhz100},

fr2 ENUMERATED {mhz50, mhz100, mhz200, mhz400}

}

SupportedBandwidth-v1700 ::= CHOICE {

fr1-r17 ENUMERATED {mhz5, mhz10, mhz15, mhz20, mhz25, mhz30, mhz35,
mhz40, mhz45, mhz50, mhz60, mhz70, mhz80, mhz90, mhz100},

fr2-r17 ENUMERATED {mhz50, mhz100, mhz200, mhz400, mhz800, mhz1600,
mhz2000}

}

SupportedBandwidth-v1840 ::= ENUMERATED {mhz3}

\-- TAG-SUPPORTEDBANDWIDTH-STOP

\-- ASN1STOP

#### -- *UE-BasedPerfMeas-Parameters*

The IE *UE-BasedPerfMeas-Parameters* contains UE-based performance
measurement parameters.

*UE-BasedPerfMeas-Parameters* information element

\-- ASN1START

\-- TAG-UE-BASEDPERFMEAS-PARAMETERS-START

UE-BasedPerfMeas-Parameters-r16 ::= SEQUENCE {

barometerMeasReport-r16 ENUMERATED {supported} OPTIONAL,

immMeasBT-r16 ENUMERATED {supported} OPTIONAL,

immMeasWLAN-r16 ENUMERATED {supported} OPTIONAL,

loggedMeasBT-r16 ENUMERATED {supported} OPTIONAL,

loggedMeasurements-r16 ENUMERATED {supported} OPTIONAL,

loggedMeasWLAN-r16 ENUMERATED {supported} OPTIONAL,

orientationMeasReport-r16 ENUMERATED {supported} OPTIONAL,

speedMeasReport-r16 ENUMERATED {supported} OPTIONAL,

gnss-Location-r16 ENUMERATED {supported} OPTIONAL,

ulPDCP-Delay-r16 ENUMERATED {supported} OPTIONAL,

\...,

\[\[

sigBasedLogMDT-OverrideProtect-r17 ENUMERATED {supported} OPTIONAL,

multipleCEF-Report-r17 ENUMERATED {supported} OPTIONAL,

excessPacketDelay-r17 ENUMERATED {supported} OPTIONAL,

earlyMeasLog-r17 ENUMERATED {supported} OPTIONAL

\]\],

\[\[

loggedMDT-PNI-NPN-r18 ENUMERATED {supported} OPTIONAL,

loggedMDT-SNPN-r18 ENUMERATED {supported} OPTIONAL

\]\]

}

\-- TAG-UE-BASEDPERFMEAS-PARAMETERS-STOP

\-- ASN1STOP

#### -- *UE-CapabilityRAT-ContainerList*

The IE *UE-CapabilityRAT-ContainerList* contains a list of radio access
technology specific capability containers.

*UE-CapabilityRAT-ContainerList* information element

\-- ASN1START

\-- TAG-UE-CAPABILITYRAT-CONTAINERLIST-START

UE-CapabilityRAT-ContainerList ::= SEQUENCE (SIZE
(0..maxRAT-CapabilityContainers)) OF UE-CapabilityRAT-Container

UE-CapabilityRAT-Container ::= SEQUENCE {

rat-Type RAT-Type,

ue-CapabilityRAT-Container OCTET STRING

}

\-- TAG-UE-CAPABILITYRAT-CONTAINERLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UE-CapabilityRAT-ContainerList* field descriptions                   |
+=======================================================================+
| ***ue-CapabilityRAT-Container***                                      |
|                                                                       |
| Container for the UE capabilities of the indicated RAT. The encoding  |
| is defined in the specification of each RAT:                          |
|                                                                       |
| For *rat-Type* set to *nr*: the encoding of UE capabilities is        |
| defined in *UE-NR-Capability*.                                        |
|                                                                       |
| For *rat-Type* set to *eutra-nr*: the encoding of UE capabilities is  |
| defined in *UE-MRDC-Capability*.                                      |
|                                                                       |
| For *rat-Type* set to *eutra*: the encoding of UE capabilities is     |
| defined in *UE-EUTRA-Capability* specified in TS 36.331 \[10\].       |
|                                                                       |
| For *rat-Type* set to *utra-fdd*: the octet string contains the INTER |
| RAT HANDOVER INFO message defined in TS 25.331 \[45\].                |
+-----------------------------------------------------------------------+

#### -- *UE-CapabilityRAT-RequestList*

The IE *UE-CapabilityRAT-RequestList* is used to request UE capabilities
for one or more RATs from the UE.

*UE-CapabilityRAT-RequestList* information element

\-- ASN1START

\-- TAG-UE-CAPABILITYRAT-REQUESTLIST-START

UE-CapabilityRAT-RequestList ::= SEQUENCE (SIZE
(1..maxRAT-CapabilityContainers)) OF UE-CapabilityRAT-Request

UE-CapabilityRAT-Request ::= SEQUENCE {

rat-Type RAT-Type,

capabilityRequestFilter OCTET STRING OPTIONAL, \-- Need N

\...

}

\-- TAG-UE-CAPABILITYRAT-REQUESTLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UE-CapabilityRAT-Request* field descriptions                         |
+=======================================================================+
| ***capabilityRequestFilter***                                         |
|                                                                       |
| Information by which the network requests the UE to filter the UE     |
| capabilities.                                                         |
|                                                                       |
| For *rat-Type* set to *nr* or *eutra-nr*: the encoding of the         |
| *capabilityRequestFilter* is defined in                               |
| *UE-CapabilityRequestFilterNR*.                                       |
|                                                                       |
| For *rat-Type* set to *eutra*: the encoding of the                    |
| *capabilityRequestFilter* is defined by *UECapabilityEnquiry* message |
| defined in TS36.331 \[10\], in which *RAT-Type* in                    |
| *UE-CapabilityRequest* includes only \'*eutra\'*.                     |
+-----------------------------------------------------------------------+
| ***rat-Type***                                                        |
|                                                                       |
| The RAT type for which the NW requests UE capabilities.               |
+-----------------------------------------------------------------------+

#### -- *UE-CapabilityRequestFilterCommon*

The IE *UE-CapabilityRequestFilterCommon* is used to request filtered UE
capabilities. The filter is common for all capability containers that
are requested.

*UE-CapabilityRequestFilterCommon* information element

\-- ASN1START

\-- TAG-UE-CAPABILITYREQUESTFILTERCOMMON-START

UE-CapabilityRequestFilterCommon ::= SEQUENCE {

mrdc-Request SEQUENCE {

omitEN-DC ENUMERATED {true} OPTIONAL, \-- Need N

includeNR-DC ENUMERATED {true} OPTIONAL, \-- Need N

includeNE-DC ENUMERATED {true} OPTIONAL \-- Need N

} OPTIONAL, \-- Need N

\...,

\[\[

codebookTypeRequest-r16 SEQUENCE {

type1-SinglePanel-r16 ENUMERATED {true} OPTIONAL, \-- Need N

type1-MultiPanel-r16 ENUMERATED {true} OPTIONAL, \-- Need N

type2-r16 ENUMERATED {true} OPTIONAL, \-- Need N

type2-PortSelection-r16 ENUMERATED {true} OPTIONAL \-- Need N

} OPTIONAL, \-- Need N

uplinkTxSwitchRequest-r16 ENUMERATED {true} OPTIONAL \-- Need N

\]\],

\[\[

requestedCellGrouping-r16 SEQUENCE (SIZE (1..maxCellGroupings-r16)) OF
CellGrouping-r16 OPTIONAL \-- Cond NRDC

\]\],

\[\[

fallbackGroupFiveRequest-r17 ENUMERATED {true} OPTIONAL \-- Need N

\]\],

\[\[

lowerMSDRequest-r18 SEQUENCE {

pc1dot5-r18 ENUMERATED {true} OPTIONAL, \-- Need N

pc2-r18 ENUMERATED {true} OPTIONAL, \-- Need N

pc3-r18 ENUMERATED {true} OPTIONAL \-- Need N

} OPTIONAL \-- Need N

\]\]

}

CellGrouping-r16 ::= SEQUENCE {

mcg-r16 SEQUENCE (SIZE (1..maxBands)) OF FreqBandIndicatorNR,

scg-r16 SEQUENCE (SIZE (1..maxBands)) OF FreqBandIndicatorNR,

mode-r16 ENUMERATED {sync, async}

}

\-- TAG-UE-CAPABILITYREQUESTFILTERCOMMON-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UE-CapabilityRequestFilterCommon field descriptions*                 |
+=======================================================================+
| ***codebookTypeRequest***                                             |
|                                                                       |
| Only if this field is present, the UE includes                        |
| *SupportedCSI-RS-Resource* supported for the codebook type(s)         |
| requested within this field (i.e. type I single/multi-panel, type II  |
| and type II port selection) into *codebookVariantsList*,              |
| *codebookParametersPerBand* and *codebookParametersPerBC*. If this    |
| field is present and none of the codebook types is requested within   |
| this field (i.e. empty field), the UE includes                        |
| *SupportedCSI-RS-Resource* supported for all codebook types into      |
| *codebookVariantsList*, *codebookParametersPerBand* and               |
| *codebookParametersPerBC*.                                            |
+-----------------------------------------------------------------------+
| ***fallbackGroupFiveRequest***                                        |
|                                                                       |
| Only if this field is present, the UE supporting FR2 CA bandwidth     |
| class from fallback group 5 shall include band combinations with FR2  |
| CA bandwidth class from fallback group 5, and shall omit band         |
| combinations with FR2 CA bandwidth class from fallback group 2 or 3   |
| (see TS 38.101-2 \[39\]) with same or lower capabilities.             |
+-----------------------------------------------------------------------+
| ***includeNE-DC***                                                    |
|                                                                       |
| Only if this field is present, the UE supporting NE-DC shall indicate |
| support for NE-DC in band combinations and include feature set        |
| combinations which are applicable to NE-DC. Band combinations         |
| supporting both NE-DC and (NG)EN-DC shall be included in              |
| *supportedBandCombinationList*, band combinations supporting only     |
| NE-DC shall be included in *supportedBandCombinationListNEDC-Only*.   |
+-----------------------------------------------------------------------+
| ***includeNR-DC***                                                    |
|                                                                       |
| Only if this field is present, the UE supporting NR-DC shall indicate |
| support for NR-DC in band combinations and include feature set        |
| combinations which are applicable to NR-DC.                           |
+-----------------------------------------------------------------------+
| ***lowerMSDRequest***                                                 |
|                                                                       |
| Only if this field is present, the UE supporting lower MSD shall      |
| indicate the lower MSD capability for the requested power class if    |
| supported. If no power class is explicitly requested, the UE          |
| supporting lower MSD shall indicate the lower MSD capability for the  |
| highest supported power class of the band combination consisting of   |
| victim band and aggressor band(s).                                    |
+-----------------------------------------------------------------------+
| ***mode***                                                            |
|                                                                       |
| The mode of NR-DC operation that the NW is interested in for this     |
| cell grouping. The value *sync* means that the UE only indicates      |
| NR-DC support for band combinations for which it supports synchronous |
| NR-DC with the requested cell grouping. The value *async* means that  |
| the UE only indicates NR-DC support for band combinations for which   |
| it supports asynchronous NR-DC with the requested cell grouping.      |
+-----------------------------------------------------------------------+
| ***omitEN-DC***                                                       |
|                                                                       |
| Only if this field is present, the UE shall omit band combinations    |
| and feature set combinations which are only applicable to (NG)EN-DC.  |
+-----------------------------------------------------------------------+
| ***requestedCellGrouping***                                           |
|                                                                       |
| The NR-DC cell groupings that the NW is interested in, i.e., the      |
| bands that it might use in an MCG and the bands that it might use in  |
| an SCG. Only if this field is present, the UE indicates NR-DC support |
| for band combinations for which it supports the requested cell        |
| grouping, i.e., in which it supports at least one of the *mcg* bands  |
| on MCG and at least one of the *scg* bands on the SCG. In its         |
| *supportedBandCombinationList*, the UE indicates which of its NR-DC   |
| band combinations supports which of the requested cell groupings. The |
| first element in this list is referred to by ID#0, the second by ID#1 |
| and so on. If this field is absent, the UE only includes band         |
| combinations for which it supports NR-DC with only FR1 bands in MCG   |
| and only FR2 bands in SCG.                                            |
|                                                                       |
| Example 1: *requestedCellGrouping* is set to *mcg*=\[n1, n7, n41,     |
| n66\] and *scg*=\[n78, n261\]. This assumes that the NW would always  |
| use CA among n1, n7, n41 and n66 (depending on which are deployed on  |
| a given site) whereas with n78 and/or n261 the NW may need to use DC. |
| With this filter a UE may report a band combination n1A-n7A-n78A for  |
| NR-DC only if it supports that serving cells for n1 and n7 are in the |
| MCG and a serving cell for n78 is in the SCG. The UE may also report  |
| a band combination n41C-n261M for NR-DC provided that it supports a   |
| serving cell for n41 in the MCG and a serving cell for n261 in the    |
| SCG.                                                                  |
|                                                                       |
| Example 2: One *requestedCellGrouping* is set to *mcg*=\[n1, n7, n41, |
| n66\] and s*cg*=\[n78, n261\] and another *requestedCellGrouping* is  |
| set to *mcg*=\[n1, n7, n66\] and s*cg*=\[ n41, n78, n261\]. This      |
| assumes that the NW uses sometimes CA among n1, n7, n41 and n66 (as   |
| in example 1) and sometimes CA among n1, n7 and n66 but DC towards    |
| one or several of n41, n78, n261. If a UE supports n1A-n41A-n78A only |
| if n41A and n78A are in the same cell group, this UE may only         |
| indicate cell grouping ID#1 (not #0) in its BC.                       |
+-----------------------------------------------------------------------+
| ***uplinkTxSwitchRequest***                                           |
|                                                                       |
| Only if this field is present, the UE supporting dynamic UL Tx        |
| switching shall indicate support for UL Tx switching in band          |
| combinations which are applicable to inter-band UL CA, SUL and        |
| (NG)EN-DC.                                                            |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *NRDC*               The field is optionally present, Need N, if
                       *includeNR-DC* is included. It is absent
                       otherwise.

  -----------------------------------------------------------------------

#### -- *UE-CapabilityRequestFilterNR*

The IE *UE-CapabilityRequestFilterNR* is used to request filtered UE
capabilities.

*UE-CapabilityRequestFilterNR* information element

\-- ASN1START

\-- TAG-UE-CAPABILITYREQUESTFILTERNR-START

UE-CapabilityRequestFilterNR ::= SEQUENCE {

frequencyBandListFilter FreqBandList OPTIONAL, \-- Need N

nonCriticalExtension UE-CapabilityRequestFilterNR-v1540 OPTIONAL

}

UE-CapabilityRequestFilterNR-v1540 ::= SEQUENCE {

srs-SwitchingTimeRequest ENUMERATED {true} OPTIONAL, \-- Need N

nonCriticalExtension UE-CapabilityRequestFilterNR-v1710 OPTIONAL

}

UE-CapabilityRequestFilterNR-v1710 ::= SEQUENCE {

sidelinkRequest-r17 ENUMERATED {true} OPTIONAL, \-- Need N

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- TAG-UE-CAPABILITYREQUESTFILTERNR-STOP

\-- ASN1STOP

#### -- *UE-MRDC-Capability*

The IE *UE-MRDC-Capability* is used to convey the UE Radio Access
Capability Parameters for MR-DC, see TS 38.306 \[26\].

*UE-MRDC-Capability* information element

\-- ASN1START

\-- TAG-UE-MRDC-CAPABILITY-START

UE-MRDC-Capability ::= SEQUENCE {

measAndMobParametersMRDC MeasAndMobParametersMRDC OPTIONAL,

phy-ParametersMRDC-v1530 Phy-ParametersMRDC OPTIONAL,

rf-ParametersMRDC RF-ParametersMRDC,

generalParametersMRDC GeneralParametersMRDC-XDD-Diff OPTIONAL,

fdd-Add-UE-MRDC-Capabilities UE-MRDC-CapabilityAddXDD-Mode OPTIONAL,

tdd-Add-UE-MRDC-Capabilities UE-MRDC-CapabilityAddXDD-Mode OPTIONAL,

fr1-Add-UE-MRDC-Capabilities UE-MRDC-CapabilityAddFRX-Mode OPTIONAL,

fr2-Add-UE-MRDC-Capabilities UE-MRDC-CapabilityAddFRX-Mode OPTIONAL,

featureSetCombinations SEQUENCE (SIZE (1..maxFeatureSetCombinations)) OF
FeatureSetCombination OPTIONAL,

pdcp-ParametersMRDC-v1530 PDCP-ParametersMRDC OPTIONAL,

lateNonCriticalExtension OCTET STRING (CONTAINING
UE-MRDC-Capability-v15g0) OPTIONAL,

nonCriticalExtension UE-MRDC-Capability-v1560 OPTIONAL

}

\-- Regular non-critical extensions:

UE-MRDC-Capability-v1560 ::= SEQUENCE {

receivedFilters OCTET STRING (CONTAINING UECapabilityEnquiry-v1560-IEs)
OPTIONAL,

measAndMobParametersMRDC-v1560 MeasAndMobParametersMRDC-v1560 OPTIONAL,

fdd-Add-UE-MRDC-Capabilities-v1560 UE-MRDC-CapabilityAddXDD-Mode-v1560
OPTIONAL,

tdd-Add-UE-MRDC-Capabilities-v1560 UE-MRDC-CapabilityAddXDD-Mode-v1560
OPTIONAL,

nonCriticalExtension UE-MRDC-Capability-v1610 OPTIONAL

}

UE-MRDC-Capability-v1610 ::= SEQUENCE {

measAndMobParametersMRDC-v1610 MeasAndMobParametersMRDC-v1610 OPTIONAL,

generalParametersMRDC-v1610 GeneralParametersMRDC-v1610 OPTIONAL,

pdcp-ParametersMRDC-v1610 PDCP-ParametersMRDC-v1610 OPTIONAL,

nonCriticalExtension UE-MRDC-Capability-v1700 OPTIONAL

}

UE-MRDC-Capability-v1700 ::= SEQUENCE {

measAndMobParametersMRDC-v1700 MeasAndMobParametersMRDC-v1700,

nonCriticalExtension UE-MRDC-Capability-v1730 OPTIONAL

}

UE-MRDC-Capability-v1730 ::= SEQUENCE {

measAndMobParametersMRDC-v1730 MeasAndMobParametersMRDC-v1730 OPTIONAL,

nonCriticalExtension UE-MRDC-Capability-v1800 OPTIONAL

}

UE-MRDC-Capability-v1800 ::= SEQUENCE {

\-- R4 33-2: Support network control of requirementnetwork applicability
for UE supporting interBandMRDC-WithOverlapDL-Bands-r16

requirementTypeIndication-r18 ENUMERATED {supported} OPTIONAL,

measAndMobParametersMRDC-v1810 MeasAndMobParametersMRDC-v1810 OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- Late non-critical extensions:

UE-MRDC-Capability-v15g0 ::= SEQUENCE {

rf-ParametersMRDC-v15g0 RF-ParametersMRDC-v15g0 OPTIONAL,

nonCriticalExtension UE-MRDC-Capability-v15n0 OPTIONAL

}

UE-MRDC-Capability-v15n0 ::= SEQUENCE {

rf-ParametersMRDC-v15n0 RF-ParametersMRDC-v15n0 OPTIONAL,

\-- Following field is only for REL-15 late non-critical extensions

lateNonCriticalExtension OCTET STRING OPTIONAL,

nonCriticalExtension UE-MRDC-Capability-v16e0 OPTIONAL

}

UE-MRDC-Capability-v16e0 ::= SEQUENCE {

rf-ParametersMRDC-v16e0 RF-ParametersMRDC-v16e0 OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

UE-MRDC-CapabilityAddXDD-Mode ::= SEQUENCE {

measAndMobParametersMRDC-XDD-Diff MeasAndMobParametersMRDC-XDD-Diff
OPTIONAL,

generalParametersMRDC-XDD-Diff GeneralParametersMRDC-XDD-Diff OPTIONAL

}

UE-MRDC-CapabilityAddXDD-Mode-v1560 ::= SEQUENCE {

measAndMobParametersMRDC-XDD-Diff-v1560
MeasAndMobParametersMRDC-XDD-Diff-v1560 OPTIONAL

}

UE-MRDC-CapabilityAddFRX-Mode ::= SEQUENCE {

measAndMobParametersMRDC-FRX-Diff MeasAndMobParametersMRDC-FRX-Diff

}

GeneralParametersMRDC-XDD-Diff ::= SEQUENCE {

splitSRB-WithOneUL-Path ENUMERATED {supported} OPTIONAL,

splitDRB-withUL-Both-MCG-SCG ENUMERATED {supported} OPTIONAL,

srb3 ENUMERATED {supported} OPTIONAL,

dummy ENUMERATED {supported} OPTIONAL,

\...

}

GeneralParametersMRDC-v1610 ::= SEQUENCE {

f1c-OverEUTRA-r16 ENUMERATED {supported} OPTIONAL

}

\-- TAG-UE-MRDC-CAPABILITY-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UE-MRDC-Capability* field descriptions                               |
+=======================================================================+
| ***featureSetCombinations***                                          |
|                                                                       |
| A list of *FeatureSetCombination*:s for                               |
| *supportedBandCombinationList* and                                    |
| *supportedBandCombinationListNEDC-Only* in *UE-MRDC-Capability*. The  |
| *FeatureSetDownlink*:s and *FeatureSetUplink*:s referred to from      |
| these *FeatureSetCombination*:s are defined in the *featureSets* list |
| in *UE-NR-Capability*.                                                |
+-----------------------------------------------------------------------+

#### -- *UE-NR-Capability*

The IE *UE-NR-Capability* is used to convey the NR UE Radio Access
Capability Parameters, see TS 38.306 \[26\].

*UE-NR-Capability* information element

\-- ASN1START

\-- TAG-UE-NR-CAPABILITY-START

UE-NR-Capability ::= SEQUENCE {

accessStratumRelease AccessStratumRelease,

pdcp-Parameters PDCP-Parameters,

rlc-Parameters RLC-Parameters OPTIONAL,

mac-Parameters MAC-Parameters OPTIONAL,

phy-Parameters Phy-Parameters,

rf-Parameters RF-Parameters,

measAndMobParameters MeasAndMobParameters OPTIONAL,

fdd-Add-UE-NR-Capabilities UE-NR-CapabilityAddXDD-Mode OPTIONAL,

tdd-Add-UE-NR-Capabilities UE-NR-CapabilityAddXDD-Mode OPTIONAL,

fr1-Add-UE-NR-Capabilities UE-NR-CapabilityAddFRX-Mode OPTIONAL,

fr2-Add-UE-NR-Capabilities UE-NR-CapabilityAddFRX-Mode OPTIONAL,

featureSets FeatureSets OPTIONAL,

featureSetCombinations SEQUENCE (SIZE (1..maxFeatureSetCombinations)) OF
FeatureSetCombination OPTIONAL,

lateNonCriticalExtension OCTET STRING (CONTAINING
UE-NR-Capability-v15c0) OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1530 OPTIONAL

}

\-- Regular non-critical Rel-15 extensions:

UE-NR-Capability-v1530 ::= SEQUENCE {

fdd-Add-UE-NR-Capabilities-v1530 UE-NR-CapabilityAddXDD-Mode-v1530
OPTIONAL,

tdd-Add-UE-NR-Capabilities-v1530 UE-NR-CapabilityAddXDD-Mode-v1530
OPTIONAL,

dummy ENUMERATED {supported} OPTIONAL,

interRAT-Parameters InterRAT-Parameters OPTIONAL,

inactiveState ENUMERATED {supported} OPTIONAL,

delayBudgetReporting ENUMERATED {supported} OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1540 OPTIONAL

}

UE-NR-Capability-v1540 ::= SEQUENCE {

sdap-Parameters SDAP-Parameters OPTIONAL,

overheatingInd ENUMERATED {supported} OPTIONAL,

ims-Parameters IMS-Parameters OPTIONAL,

fr1-Add-UE-NR-Capabilities-v1540 UE-NR-CapabilityAddFRX-Mode-v1540
OPTIONAL,

fr2-Add-UE-NR-Capabilities-v1540 UE-NR-CapabilityAddFRX-Mode-v1540
OPTIONAL,

fr1-fr2-Add-UE-NR-Capabilities UE-NR-CapabilityAddFRX-Mode OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1550 OPTIONAL

}

UE-NR-Capability-v1550 ::= SEQUENCE {

reducedCP-Latency ENUMERATED {supported} OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1560 OPTIONAL

}

UE-NR-Capability-v1560 ::= SEQUENCE {

nrdc-Parameters NRDC-Parameters OPTIONAL,

receivedFilters OCTET STRING (CONTAINING UECapabilityEnquiry-v1560-IEs)
OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1570 OPTIONAL

}

UE-NR-Capability-v1570 ::= SEQUENCE {

nrdc-Parameters-v1570 NRDC-Parameters-v1570 OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1610 OPTIONAL

}

\-- Late non-critical Rel-15 extensions:

UE-NR-Capability-v15c0 ::= SEQUENCE {

nrdc-Parameters-v15c0 NRDC-Parameters-v15c0 OPTIONAL,

partialFR2-FallbackRX-Req ENUMERATED {true} OPTIONAL,

nonCriticalExtension UE-NR-Capability-v15g0 OPTIONAL

}

UE-NR-Capability-v15g0 ::= SEQUENCE {

rf-Parameters-v15g0 RF-Parameters-v15g0 OPTIONAL,

nonCriticalExtension UE-NR-Capability-v15j0 OPTIONAL

}

UE-NR-Capability-v15j0 ::= SEQUENCE {

\-- Following field is only for REL-15 late non-critical extensions

lateNonCriticalExtension OCTET STRING (CONTAINING
UE-NR-Capability-v15t0) OPTIONAL,

nonCriticalExtension UE-NR-Capability-v16a0 OPTIONAL

}

UE-NR-Capability-v15t0 ::= SEQUENCE {

featureSets-v15t0 FeatureSets-v15t0 OPTIONAL,

measAndMobParameters-v15t0 MeasAndMobParameters-v15t0 OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- Regular non-critical Rel-16 extensions:

UE-NR-Capability-v1610 ::= SEQUENCE {

inDeviceCoexInd-r16 ENUMERATED {supported} OPTIONAL,

dl-DedicatedMessageSegmentation-r16 ENUMERATED {supported} OPTIONAL,

nrdc-Parameters-v1610 NRDC-Parameters-v1610 OPTIONAL,

powSav-Parameters-r16 PowSav-Parameters-r16 OPTIONAL,

fr1-Add-UE-NR-Capabilities-v1610 UE-NR-CapabilityAddFRX-Mode-v1610
OPTIONAL,

fr2-Add-UE-NR-Capabilities-v1610 UE-NR-CapabilityAddFRX-Mode-v1610
OPTIONAL,

bh-RLF-Indication-r16 ENUMERATED {supported} OPTIONAL,

directSN-AdditionFirstRRC-IAB-r16 ENUMERATED {supported} OPTIONAL,

bap-Parameters-r16 BAP-Parameters-r16 OPTIONAL,

referenceTimeProvision-r16 ENUMERATED {supported} OPTIONAL,

sidelinkParameters-r16 SidelinkParameters-r16 OPTIONAL,

highSpeedParameters-r16 HighSpeedParameters-r16 OPTIONAL,

mac-Parameters-v1610 MAC-Parameters-v1610 OPTIONAL,

mcgRLF-RecoveryViaSCG-r16 ENUMERATED {supported} OPTIONAL,

resumeWithStoredMCG-SCells-r16 ENUMERATED {supported} OPTIONAL,

resumeWithStoredSCG-r16 ENUMERATED {supported} OPTIONAL,

resumeWithSCG-Config-r16 ENUMERATED {supported} OPTIONAL,

ue-BasedPerfMeas-Parameters-r16 UE-BasedPerfMeas-Parameters-r16
OPTIONAL,

son-Parameters-r16 SON-Parameters-r16 OPTIONAL,

onDemandSIB-Connected-r16 ENUMERATED {supported} OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1640 OPTIONAL

}

UE-NR-Capability-v1640 ::= SEQUENCE {

redirectAtResumeByNAS-r16 ENUMERATED {supported} OPTIONAL,

phy-ParametersSharedSpectrumChAccess-r16
Phy-ParametersSharedSpectrumChAccess-r16 OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1650 OPTIONAL

}

UE-NR-Capability-v1650 ::= SEQUENCE {

mpsPriorityIndication-r16 ENUMERATED {supported} OPTIONAL,

highSpeedParameters-v1650 HighSpeedParameters-v1650 OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1690 OPTIONAL

}

UE-NR-Capability-v1690 ::= SEQUENCE {

ul-RRC-Segmentation-r16 ENUMERATED {supported} OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1700 OPTIONAL

}

\-- Late non-critical extensions from Rel-16 onwards:

UE-NR-Capability-v16a0 ::= SEQUENCE {

phy-Parameters-v16a0 Phy-Parameters-v16a0 OPTIONAL,

rf-Parameters-v16a0 RF-Parameters-v16a0 OPTIONAL,

nonCriticalExtension UE-NR-Capability-v16c0 OPTIONAL

}

UE-NR-Capability-v16c0 ::= SEQUENCE {

rf-Parameters-v16c0 RF-Parameters-v16c0 OPTIONAL,

nonCriticalExtension UE-NR-Capability-v16d0 OPTIONAL

}

UE-NR-Capability-v16d0 ::= SEQUENCE {

featureSets-v16d0 FeatureSets-v16d0 OPTIONAL,

nonCriticalExtension UE-NR-Capability-v16j0 OPTIONAL

}

UE-NR-Capability-v16j0 ::= SEQUENCE {

rf-Parameters-v16j0 RF-Parameters-v16j0 OPTIONAL,

\-- Following field is only for REL-16 late non-critical extensions

lateNonCriticalExtension OCTET STRING (CONTAINING
UE-NR-Capability-v16k0) OPTIONAL,

nonCriticalExtension UE-NR-Capability-v17b0 OPTIONAL

}

UE-NR-Capability-v16k0 ::= SEQUENCE {

featureSets-v16k0 FeatureSets-v16k0 OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- Regular non-critical Rel-17 extensions:

UE-NR-Capability-v1700 ::= SEQUENCE {

inactiveStatePO-Determination-r17 ENUMERATED {supported} OPTIONAL,

highSpeedParameters-v1700 HighSpeedParameters-v1700 OPTIONAL,

powSav-Parameters-v1700 PowSav-Parameters-v1700 OPTIONAL,

mac-Parameters-v1700 MAC-Parameters-v1700 OPTIONAL,

ims-Parameters-v1700 IMS-Parameters-v1700 OPTIONAL,

measAndMobParameters-v1700 MeasAndMobParameters-v1700,

appLayerMeasParameters-r17 AppLayerMeasParameters-r17 OPTIONAL,

redCapParameters-r17 RedCapParameters-r17 OPTIONAL,

ra-SDT-r17 ENUMERATED {supported} OPTIONAL,

srb-SDT-r17 ENUMERATED {supported} OPTIONAL,

gNB-SideRTT-BasedPDC-r17 ENUMERATED {supported} OPTIONAL,

bh-RLF-DetectionRecovery-Indication-r17 ENUMERATED {supported} OPTIONAL,

nrdc-Parameters-v1700 NRDC-Parameters-v1700 OPTIONAL,

bap-Parameters-v1700 BAP-Parameters-v1700 OPTIONAL,

musim-GapPreference-r17 ENUMERATED {supported} OPTIONAL,

musimLeaveConnected-r17 ENUMERATED {supported} OPTIONAL,

mbs-Parameters-r17 MBS-Parameters-r17,

nonTerrestrialNetwork-r17 ENUMERATED {supported} OPTIONAL,

ntn-ScenarioSupport-r17 ENUMERATED {gso, ngso} OPTIONAL,

sliceInfoforCellReselection-r17 ENUMERATED {supported} OPTIONAL,

ue-RadioPagingInfo-r17 UE-RadioPagingInfo-r17 OPTIONAL,

\-- R4 17-2 UL gap pattern for Tx power management

ul-GapFR2-Pattern-r17 BIT STRING (SIZE (4)) OPTIONAL,

ntn-Parameters-r17 NTN-Parameters-r17 OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1740 OPTIONAL

}

UE-NR-Capability-v1740 ::= SEQUENCE {

redCapParameters-v1740 RedCapParameters-v1740,

nonCriticalExtension UE-NR-Capability-v1750 OPTIONAL

}

UE-NR-Capability-v1750 ::= SEQUENCE {

crossCarrierSchedulingConfigurationRelease-r17 ENUMERATED {supported}
OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1800 OPTIONAL

}

\-- Late non-critical extensions from Rel-17 onwards:

UE-NR-Capability-v17b0 ::= SEQUENCE {

mac-Parameters-v17b0 MAC-Parameters-v17b0 OPTIONAL,

rf-Parameters-v17b0 RF-Parameters-v17b0 OPTIONAL,

ul-RRC-MaxCapaSegments-r17 ENUMERATED {supported} OPTIONAL,

nonCriticalExtension UE-NR-Capability-v17c0 OPTIONAL

}

UE-NR-Capability-v17c0 ::= SEQUENCE {

mac-Parameters-v17c0 MAC-Parameters-v17c0 OPTIONAL,

nonCriticalExtension UE-NR-Capability-v17d0 OPTIONAL

}

UE-NR-Capability-v17d0 ::= SEQUENCE {

featureSets-v17d0 FeatureSets-v17d0 OPTIONAL,

nonCriticalExtension SEQUENCE {} OPTIONAL

}

\-- Regular non-critical Rel-18 extensions:

UE-NR-Capability-v1800 ::= SEQUENCE {

airToGroundNetwork-r18 ENUMERATED {supported} OPTIONAL,

eRedCapParameters-r18 ERedCapParameters-r18 OPTIONAL,

ncr-Parameters-r18 NCR-Parameters-r18 OPTIONAL,

softSatelliteSwitchResyncNTN-r18 ENUMERATED {supported} OPTIONAL,

hardSatelliteSwitchResyncNTN-r18 ENUMERATED {supported} OPTIONAL,

mt-SDT-r18 ENUMERATED {supported} OPTIONAL,

mt-SDT-NTN-r18 ENUMERATED {supported} OPTIONAL,

inDeviceCoexIndAutonomousDenial-r18 ENUMERATED {supported} OPTIONAL,

inDeviceCoexIndFDM-r18 ENUMERATED {supported} OPTIONAL,

inDeviceCoexIndTDM-r18 ENUMERATED {supported} OPTIONAL,

musim-GapPriorityPreference-r18 ENUMERATED {supported} OPTIONAL,

musim-CapabilityRestriction-r18 ENUMERATED {supported} OPTIONAL,

dummy ENUMERATED {supported} OPTIONAL,

ra-InsteadCG-SDT-r18 ENUMERATED {supported} OPTIONAL,

resumeAfterSDT-Release-r18 ENUMERATED {supported} OPTIONAL,

ul-TrafficInfo-r18 ENUMERATED {supported} OPTIONAL,

aerialParameters-r18 AerialParameters-r18 OPTIONAL,

\--R4 40-2: beam steering

ntn-VSAT-AntennaType-r18 ENUMERATED {electronic, mechanical} OPTIONAL,

\--R4 40-1: VSAT UE type in NTN

ntn-VSAT-MobilityType-r18 ENUMERATED {fixed, mobile} OPTIONAL,

ntn-Parameters-v1820 NTN-Parameters-v1820 OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1830 OPTIONAL

}

UE-NR-Capability-v1830 ::= SEQUENCE {

sib19-Support-r18 ENUMERATED {supported} OPTIONAL,

nonCriticalExtension UE-NR-Capability-v1860 OPTIONAL

}

UE-NR-Capability-v1860 ::= SEQUENCE {

ntn-CHO-OnlyLocationTimeTrigger-r18 ENUMERATED {supported} OPTIONAL,

nonCriticalExtension SEQUENCE{} OPTIONAL

}

UE-NR-CapabilityAddXDD-Mode ::= SEQUENCE {

phy-ParametersXDD-Diff Phy-ParametersXDD-Diff OPTIONAL,

mac-ParametersXDD-Diff MAC-ParametersXDD-Diff OPTIONAL,

measAndMobParametersXDD-Diff MeasAndMobParametersXDD-Diff OPTIONAL

}

UE-NR-CapabilityAddXDD-Mode-v1530 ::= SEQUENCE {

eutra-ParametersXDD-Diff EUTRA-ParametersXDD-Diff

}

UE-NR-CapabilityAddFRX-Mode ::= SEQUENCE {

phy-ParametersFRX-Diff Phy-ParametersFRX-Diff OPTIONAL,

measAndMobParametersFRX-Diff MeasAndMobParametersFRX-Diff OPTIONAL

}

UE-NR-CapabilityAddFRX-Mode-v1540 ::= SEQUENCE {

ims-ParametersFRX-Diff IMS-ParametersFRX-Diff OPTIONAL

}

UE-NR-CapabilityAddFRX-Mode-v1610 ::= SEQUENCE {

powSav-ParametersFRX-Diff-r16 PowSav-ParametersFRX-Diff-r16 OPTIONAL,

mac-ParametersFRX-Diff-r16 MAC-ParametersFRX-Diff-r16 OPTIONAL

}

BAP-Parameters-r16 ::= SEQUENCE {

flowControlBH-RLC-ChannelBased-r16 ENUMERATED {supported} OPTIONAL,

flowControlRouting-ID-Based-r16 ENUMERATED {supported} OPTIONAL

}

BAP-Parameters-v1700 ::= SEQUENCE {

bapHeaderRewriting-Rerouting-r17 ENUMERATED {supported} OPTIONAL,

bapHeaderRewriting-Routing-r17 ENUMERATED {supported} OPTIONAL

}

MBS-Parameters-r17 ::= SEQUENCE {

maxMRB-Add-r17 INTEGER (1..16) OPTIONAL

}

\-- TAG-UE-NR-CAPABILITY-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *UE-NR-Capability* field descriptions                                 |
+=======================================================================+
| ***featureSetCombinations***                                          |
|                                                                       |
| A list of *FeatureSetCombination:s* for                               |
| *supportedBandCombinationList* in *UE-NR-Capability*. The             |
| *FeatureSetDownlink:s* and *FeatureSetUplink:s* referred to from      |
| these *FeatureSetCombination:s* are defined in the *featureSets* list |
| in *UE-NR-Capability*.                                                |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *UE-NR-Capability-v1540 field descriptions*                           |
+=======================================================================+
| ***fr1-fr2-Add-UE-NR-Capabilities***                                  |
|                                                                       |
| This instance of *UE-NR-CapabilityAddFRX-Mode* does not include any   |
| other fields than *csi-RS-IM-ReceptionForFeedback*/                   |
| *csi-RS-ProcFrameworkForSRS*/ *csi-ReportFramework*.                  |
+-----------------------------------------------------------------------+

#### -- *UE-RadioPagingInfo*

The IE *UE-RadioPagingInfo* contains UE capability information needed
for paging.

*UE-RadioPagingInfo* information element

\-- ASN1START

\-- TAG-UE-RADIOPAGINGINFO-START

UE-RadioPagingInfo-r17 ::= SEQUENCE {

\-- R1 29-1: Paging enhancement

pei-SubgroupingSupportBandList-r17 SEQUENCE (SIZE (1..maxBands)) OF
FreqBandIndicatorNR OPTIONAL,

\...

}

\-- TAG-UE-RADIOPAGINGINFO-STOP

\-- ASN1STOP