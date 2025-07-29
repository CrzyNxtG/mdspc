## 9.3 Sidelink pre-configured parameters

This ASN.1 segment is the start of the NR definitions of pre-configured
sidelink parameters.

#### -- *NR-Sidelink-Preconf*

\-- ASN1START

\-- TAG-NR-SIDELINK-PRECONF-DEFINITIONS-START

NR-Sidelink-Preconf DEFINITIONS AUTOMATIC TAGS ::=

BEGIN

IMPORTS

SL-RelayUE-ConfigU2U-r18,

SL-RemoteUE-ConfigU2U-r18,

SL-RelayUE-ConfigU2U-v1840,

SL-RemoteUE-ConfigU2U-v1830,

SL-RemoteUE-Config-r17,

SL-DRX-ConfigGC-BC-r17,

SL-Freq-Id-r16,

maxNrofFreqSL-1-r18,

SL-FreqConfigCommon-r16,

SL-RadioBearerConfig-r16,

SL-RLC-BearerConfig-r16,

SL-EUTRA-AnchorCarrierFreqList-r16,

SL-NR-AnchorCarrierFreqList-r16,

SL-MeasConfigCommon-r16,

SL-UE-SelectedConfig-r16,

TDD-UL-DL-ConfigCommon,

maxNrofFreqSL-r16,

maxNrofSLRB-r16,

maxSL-LCID-r16,

SL-FreqConfigCommonExt-v16k0

FROM NR-RRC-Definitions;

\-- TAG-NR-SIDELINK-PRECONF-DEFINITIONS-STOP

\-- ASN1STOP

#### -- *SL-PreconfigurationNR*

The IE *SL-PreconfigurationNR* includes the sidelink pre-configured
parameters used for NR sidelink communication. Need codes or conditions
specified for subfields in *SL-PreconfigurationNR* do not apply.

*SL-PreconfigurationNR* information elements

\-- ASN1START

\-- TAG-SL-PRECONFIGURATIONNR-START

SL-PreconfigurationNR-r16 ::= SEQUENCE {

sidelinkPreconfigNR-r16 SidelinkPreconfigNR-r16,

\...,

\[\[

sidelinkPreconfigNR-v16k0 SidelinkPreconfigNR-v16k0

\]\]

}

SidelinkPreconfigNR-r16 ::= SEQUENCE {

sl-PreconfigFreqInfoList-r16 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-FreqConfigCommon-r16 OPTIONAL,

sl-PreconfigNR-AnchorCarrierFreqList-r16 SL-NR-AnchorCarrierFreqList-r16
OPTIONAL,

sl-PreconfigEUTRA-AnchorCarrierFreqList-r16
SL-EUTRA-AnchorCarrierFreqList-r16 OPTIONAL,

sl-RadioBearerPreConfigList-r16 SEQUENCE (SIZE (1..maxNrofSLRB-r16)) OF
SL-RadioBearerConfig-r16 OPTIONAL,

sl-RLC-BearerPreConfigList-r16 SEQUENCE (SIZE (1..maxSL-LCID-r16)) OF
SL-RLC-BearerConfig-r16 OPTIONAL,

sl-MeasPreConfig-r16 SL-MeasConfigCommon-r16 OPTIONAL,

sl-OffsetDFN-r16 INTEGER (1..1000) OPTIONAL,

t400-r16 ENUMERATED{ms100, ms200, ms300, ms400, ms600, ms1000, ms1500,
ms2000} OPTIONAL,

sl-MaxNumConsecutiveDTX-r16 ENUMERATED {n1, n2, n3, n4, n6, n8, n16,
n32} OPTIONAL,

sl-SSB-PriorityNR-r16 INTEGER (1..8) OPTIONAL,

sl-PreconfigGeneral-r16 SL-PreconfigGeneral-r16 OPTIONAL,

sl-UE-SelectedPreConfig-r16 SL-UE-SelectedConfig-r16 OPTIONAL,

sl-CSI-Acquisition-r16 ENUMERATED {enabled} OPTIONAL,

sl-RoHC-Profiles-r16 SL-RoHC-Profiles-r16 OPTIONAL,

sl-MaxCID-r16 INTEGER (1..16383) DEFAULT 15,

\...,

\[\[

sl-DRX-PreConfigGC-BC-r17 SL-DRX-ConfigGC-BC-r17 OPTIONAL,

sl-TxProfileList-r17 SL-TxProfileList-r17 OPTIONAL,

sl-PreconfigDiscConfig-r17 SL-RemoteUE-Config-r17 OPTIONAL

\]\],

\[\[

sl-PreconfigFreqInfoListSizeExt-v1800 SEQUENCE (SIZE
(1..maxNrofFreqSL-1-r18)) OF SL-FreqConfigCommon-r16 OPTIONAL,

sl-RLC-BearerConfigListSizeExt-v1800 SEQUENCE (SIZE (1..maxSL-LCID-r16))
OF SL-RLC-BearerConfig-r16 OPTIONAL,

sl-SyncFreqList-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-Freq-Id-r16 OPTIONAL,

sl-SyncTxMultiFreq-r18 ENUMERATED {true} OPTIONAL,

sl-PreconfigDiscConfig-v1800 SL-PreconfigDiscConfig-v1800 OPTIONAL,

sl-PosPreconfigFreqInfoList-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-r16))
OF SL-FreqConfigCommon-r16 OPTIONAL

\]\],

\[\[

t400-U2U-r18 ENUMERATED {ms200, ms400, ms600, ms800, ms1200, ms2000,
ms3000, ms4000} OPTIONAL

\]\],

\[\[

sl-PreconfigDiscConfig-v1840 SL-PreconfigDiscConfig-v1840 OPTIONAL

\]\]

}

SidelinkPreconfigNR-v16k0 ::= SEQUENCE {

sl-PreconfigFreqInfoListExt-v16k0 SEQUENCE (SIZE (1..maxNrofFreqSL-r16))
OF SL-FreqConfigCommonExt-v16k0 OPTIONAL

}

SL-TxProfileList-r17 ::= SEQUENCE (SIZE (1..256)) OF SL-TxProfile-r17

SL-TxProfile-r17 ::= ENUMERATED {drx-Compatible, drx-Incompatible,
spare6, spare5, spare4, spare3,spare2, spare1}

SL-PreconfigGeneral-r16 ::= SEQUENCE {

sl-TDD-Configuration-r16 TDD-UL-DL-ConfigCommon OPTIONAL,

reservedBits-r16 BIT STRING (SIZE (2)) OPTIONAL,

\...

}

SL-RoHC-Profiles-r16 ::= SEQUENCE {

profile0x0001-r16 BOOLEAN,

profile0x0002-r16 BOOLEAN,

profile0x0003-r16 BOOLEAN,

profile0x0004-r16 BOOLEAN,

profile0x0006-r16 BOOLEAN,

profile0x0101-r16 BOOLEAN,

profile0x0102-r16 BOOLEAN,

profile0x0103-r16 BOOLEAN,

profile0x0104-r16 BOOLEAN

}

SL-PreconfigDiscConfig-v1800 ::= SEQUENCE {

sl-RelayUE-PreconfigU2U-r18 SL-RelayUE-ConfigU2U-r18,

sl-RemoteUE-PreconfigU2U-r18 SL-RemoteUE-ConfigU2U-r18

}

SL-PreconfigDiscConfig-v1840 ::= SEQUENCE {

sl-RelayUE-PreconfigU2U-v1840 SL-RelayUE-ConfigU2U-v1840,

sl-RemoteUE-PreconfigU2U-v1840 SL-RemoteUE-ConfigU2U-v1830

}

\-- TAG-SL-PRECONFIGURATIONNR-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-PreconfigurationNR* field descriptions                            |
+-----------------------------------------------------------------------+
| ***sl-DRX-PreConfig-GC-BC***                                          |
|                                                                       |
| This field indicates the sidelink DRX configuration for groupcast and |
| broadcast communication, as specified in TS 38.321 \[3\].             |
+=======================================================================+
| ***sl-OffsetDFN***                                                    |
|                                                                       |
| Indicates the timing offset for the UE to determine DFN timing when   |
| GNSS is used for timing reference. Value 1 corresponds to 0.001       |
| milliseconds, value 2 corresponds to 0.002 milliseconds, and so on.   |
| If the field is absent, no offset is applied.                         |
+-----------------------------------------------------------------------+
| ***sl-PosPreconfigFreqInfoList***                                     |
|                                                                       |
| This field indicates the NR sidelink positioning carrier frequencies  |
| of SL-PRS dedicated resource pool for SL-PRS transmission and         |
| reception. In this release, only one entry of *SL-FreqConfigCommon*   |
| is included in the list.                                              |
+-----------------------------------------------------------------------+
| ***sl-PreconfigDiscConfig***                                          |
|                                                                       |
| This field indicates the configuration for discovery message          |
| transmission used by NR sidelink U2N Remote UE, used by NR sidelink   |
| U2U Relay UE or used by NR sidelink U2U Remote UE.                    |
+-----------------------------------------------------------------------+
| ***sl-PreconfigEUTRA-AnchorCarrierFreqList***                         |
|                                                                       |
| This field indicates the EUTRA anchor carrier frequency list, which   |
| can provide the NR sidelink communication configuration.              |
+-----------------------------------------------------------------------+
| ***sl-PreconfigFreqInfoList, sl-PreconfigFreqInfoListSizeExt,         |
| sl-PreconfigFreqInfoListExt***                                        |
|                                                                       |
| This field indicates the NR sidelink communication and/ or NR         |
| sidelink discovery configuration some carrier frequency(ies). In this |
| release, only one *SL-FreqConfig* can be configured in                |
| *sl-PreconfigFreqInfoList*. More entries of SL-FreqConfig can be      |
| configured in *sl-PreconfigFreqInfoListSizeExt*. If                   |
| *sl-PreconfigFreqInfoListExt* is included, it contains the same       |
| number of entries, and listed in the same order, as in                |
| *sl-PreconfigFreqInfoList* together with                              |
| *sl-PreconfigFreqInfoListSizeExt*. The first entry corresponds to the |
| AdditionalSpectrumEmission of the frequency of first entry in         |
| *sl-PreconfigFreqInfoList*, the second entry corresponds to the       |
| AdditionalSpectrumEmission of the frequency of first entry in         |
| *sl-PreconfigFreqInfoListSizeExt*, the third entry corresponds to the |
| AdditionalSpectrumEmission of the frequency of second entry in        |
| *sl-PreconfigFreqInfoListSizeExt* and so on.                          |
+-----------------------------------------------------------------------+
| ***sl-PreconfigNR-AnchorCarrierFreqList***                            |
|                                                                       |
| This field indicates the NR anchor carrier frequency list, which can  |
| provide the NR sidelink communication configuration.                  |
+-----------------------------------------------------------------------+
| ***sl-RadioBearerPreConfigList***                                     |
|                                                                       |
| This field indicates one or multiple sidelink radio bearer            |
| configurations.                                                       |
+-----------------------------------------------------------------------+
| ***sl-RLC-BearerPreConfigList, sl-RLC-BearerPreConfigListSizeExt***   |
|                                                                       |
| This field indicates one or multiple sidelink RLC bearer              |
| configurations.                                                       |
+-----------------------------------------------------------------------+
| ***sl-RoHC-Profiles***                                                |
|                                                                       |
| This field indicates the supported RoHC profiles for NR sidelink      |
| communications.                                                       |
+-----------------------------------------------------------------------+
| ***sl-SSB-PriorityNR***                                               |
|                                                                       |
| This field indicates the priority of NR sidelink SSB transmission and |
| reception.                                                            |
+-----------------------------------------------------------------------+
| ***sl-SyncFreqList***                                                 |
|                                                                       |
| Indicates a list of candidate carrier frequencies that can be used    |
| for the synchronisation of NR sidelink communication. For             |
| *SL-Freq-Id-r16*, the value 1 corresponds to the frequency of first   |
| entry in *sl-PreconfigFreqInfoList*, the value 2 corresponds to the   |
| frequency of first entry in *sl-PreconfigFreqInfoListSizeExt*, the    |
| value 3 corresponds to the frequency of second entry in               |
| *sl-PreconfigFreqInfoListSizeExt* and so on.                          |
+-----------------------------------------------------------------------+
| ***sl-SyncTxMultiFreq***                                              |
|                                                                       |
| Indicates that the UE transmits S-SSB on multiple carrier frequencies |
| for NR sidelink communication. If this field is absent, the UE        |
| transmits S-SSB only on the synchronisation carrier frequency.        |
+-----------------------------------------------------------------------+
| ***sl-TxProfileList***                                                |
|                                                                       |
| List of one or multiple Tx profiles, indicating the compatibility of  |
| supporting SL DRX as specified in TS 38.321 \[3\]. Value              |
| *drx-Compatible* means SL DRX is supported, and value                 |
| *drx-Incompatible* means SL DRX is not supported. It is up to the UE  |
| implementation whether/how to apply this field.                       |
+-----------------------------------------------------------------------+
| ***t400***                                                            |
|                                                                       |
| Indicates the value for timer T400 as described in clause 7.1. Value  |
| *ms100* corresponds to 100 ms, value *ms200* corresponds to 200 ms    |
| and so on.                                                            |
+-----------------------------------------------------------------------+
| ***t400-U2U***                                                        |
|                                                                       |
| Indicates the value for timer T400 to be applied for end-to-end PC5   |
| connection in sidelink U2U relay operation as described in clause     |
| 7.1. Value *ms200* corresponds to 200 ms, value *ms400* corresponds   |
| to 400 ms and so on.                                                  |
+-----------------------------------------------------------------------+

#### -- *End of NR-Sidelink-Preconf*

\-- ASN1START

END

\-- ASN1STOP

[]{#_Toc193463821 .anchor}9.4 Radio Information Related to Discovery
Message

This clause specifies RRC information elements that are transferred in
Discovery Message.

#### -- *SL-AccessInfo-L2U2N*

The IE *SL-AccessInfo-L2U2N* includes the radio information included in
Discovery Message used for L2 U2N relay operation.

*SL-AccessInfo-L2U2N* information elements

\-- ASN1START

\-- TAG-SL-ACCESSINFO-L2U2N-START

NR-Sidelink-DiscoveryMessage DEFINITIONS AUTOMATIC TAGS ::=

BEGIN

IMPORTS

CellAccessRelatedInfo,

SL-ServingCellInfo-r17,

SL-RelayIndicationMP-r18

FROM NR-RRC-Definitions;

SL-AccessInfo-L2U2N-r17 ::= SEQUENCE {

cellAccessRelatedInfo-r17 CellAccessRelatedInfo,

sl-ServingCellInfo-r17 SL-ServingCellInfo-r17,

\...,

\[\[

sl-RelayIndication-r18 SL-RelayIndicationMP-r18 OPTIONAL

\]\]

}

END

\-- TAG-SL-ACCESSINFO-L2U2N-STOP

\-- ASN1STOP