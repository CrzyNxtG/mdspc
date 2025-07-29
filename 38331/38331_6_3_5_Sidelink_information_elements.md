### 6.3.5 Sidelink information elements

#### -- *SL-BWP-Config*

The IE *SL-BWP-Config* is used to configure the UE specific NR sidelink
communication/discovery/positioning on one particular sidelink bandwidth
part.

*SL-BWP-Config* information element

\-- ASN1START

\-- TAG-SL-BWP-CONFIG-START

SL-BWP-Config-r16 ::= SEQUENCE {

sl-BWP-Id BWP-Id,

sl-BWP-Generic-r16 SL-BWP-Generic-r16 OPTIONAL, \-- Need M

sl-BWP-PoolConfig-r16 SL-BWP-PoolConfig-r16 OPTIONAL, \-- Need M

\...,

\[\[

sl-BWP-PoolConfigPS-r17 SetupRelease {SL-BWP-PoolConfig-r16} OPTIONAL,
\-- Need M

sl-BWP-DiscPoolConfig-r17 SetupRelease {SL-BWP-DiscPoolConfig-r17}
OPTIONAL \-- Need M

\]\],

\[\[

sl-BWP-PoolConfigA2X-r18 SetupRelease {SL-BWP-PoolConfig-r16} OPTIONAL,
\-- Need M

sl-BWP-PRS-PoolConfig-r18 SetupRelease {SL-BWP-PRS-PoolConfig-r18}
OPTIONAL \-- Need M

\]\]

}

SL-BWP-Generic-r16 ::= SEQUENCE {

sl-BWP-r16 BWP OPTIONAL, \-- Need M

sl-LengthSymbols-r16 ENUMERATED {sym7, sym8, sym9, sym10, sym11, sym12,
sym13, sym14} OPTIONAL, \-- Need M

sl-StartSymbol-r16 ENUMERATED {sym0, sym1, sym2, sym3, sym4, sym5, sym6,
sym7} OPTIONAL, \-- Need M

sl-PSBCH-Config-r16 SetupRelease {SL-PSBCH-Config-r16} OPTIONAL, \--
Need M

sl-TxDirectCurrentLocation-r16 INTEGER (0..3301) OPTIONAL, \-- Need M

\...,

\[\[

sl-Unlicensed-r18 SetupRelease { SL-Unlicensed-r18 } OPTIONAL \-- Need M

\]\]

}

SL-Unlicensed-r18 ::= SEQUENCE {

sl-LBT-FailureRecoveryConfig-r18 SetupRelease {
SL-LBT-FailureRecoveryConfig-r18 } OPTIONAL, \-- Need M

sl-StartingSymbolFirst-r18 ENUMERATED {sym0, sym1, sym2, sym3, sym4,
sym5, sym6} OPTIONAL, \-- Need M

sl-StartingSymbolSecond-r18 ENUMERATED {sym3, sym4, sym5, sym6, sym7}
OPTIONAL, \-- Need M

sl-TransmissionStructureForPSCCHandPSSCH-r18 ENUMERATED {contiguousRB,
interlaceRB} OPTIONAL, \-- Need M

sl-GapOfAdditionalSSSB-Occasion-r18 INTEGER (0..639) OPTIONAL, \-- Need
M

sl-AbsoluteFrequencySSB-NonAnchorList-r18 SEQUENCE (SIZE (1..
maxSL-NonAnchorRBsets)) OF ARFCN-ValueNR OPTIONAL, \-- Need M

sl-CPE-StartingPositionS-SSB-r18 INTEGER (1..9) OPTIONAL, \-- Need M

sl-CWS-ForPsschWithoutHarqAck-r18 ENUMERATED {t1, t8, t16, t32,
infinity} OPTIONAL, \-- Need M

sl-NumOfAdditionalSSSBOccasion-r18 INTEGER (0..4) OPTIONAL, \-- Need M

sl-SSSBPowerOffsetOfAnchorRBSet-r18 ENUMERATED {value1, value2}
OPTIONAL, \-- Need M

sl-RBSetConfigList-r18 SEQUENCE (SIZE (1..5)) OF SL-RBSetConfig-r18
OPTIONAL, \-- Need M

sl-IntraCellGuardBandsSL-List-r18 SEQUENCE (SIZE (1..maxSCSs)) OF
IntraCellGuardBandsPerSCS-r16 OPTIONAL \-- Need M

}

\-- TAG-SL-BWP-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-BWP-Config* field descriptions                                    |
+=======================================================================+
| ***sl-BWP-DiscPoolConfig***                                           |
|                                                                       |
| This field indicates the NR sidelink discovery dedicated resource     |
| pool configurations on the configured sidelink BWP. The total number  |
| of Rx/Tx resource pools configured for communication and discovery    |
| does not exceed the maximum number of Rx/Tx resource pool for NR      |
| sidelink communication (i.e. *maxNrofRXPool-r16/maxNrofTXPool-r16*).  |
+-----------------------------------------------------------------------+
| ***sl-BWP-Generic***                                                  |
|                                                                       |
| This field indicates the generic parameters on the configured         |
| sidelink BWP.                                                         |
+-----------------------------------------------------------------------+
| ***sl-BWP-Id***                                                       |
|                                                                       |
| An identifier for this sidelink bandwidth part.                       |
+-----------------------------------------------------------------------+
| ***sl-BWP-PoolConfig***                                               |
|                                                                       |
| This field indicates the resource pool configurations on the          |
| configured sidelink BWP.                                              |
+-----------------------------------------------------------------------+
| ***sl-BWP-PoolConfigA2X***                                            |
|                                                                       |
| This field indicates the resource pool configurations for A2X         |
| services on the configured sidelink BWP. This field does not include  |
| *sl-TxPoolScheduling*. This field does not include                    |
| *sl-TxPoolExceptional*.                                               |
+-----------------------------------------------------------------------+
| ***sl-BWP-PoolConfigPS***                                             |
|                                                                       |
| This field indicates the resource pool configurations for power       |
| saving on the configured sidelink BWP. This field does not include    |
| *sl-TxPoolExceptional*.                                               |
+-----------------------------------------------------------------------+
| ***sl-BWP-PRS-PoolConfig***                                           |
|                                                                       |
| This field indicates the dedicated SL-PRS resource pool               |
| configurations for SL-PRS on the configured sidelink BWP. This field  |
| does not include *sl-PRS-TxPoolExceptional*. Dedicated SL-PRS         |
| resource pool is not expected to be configured in the slots colliding |
| with the slots (pre)configured for any other resource pool(s) or      |
| S-SSB resource(s) in other SL carriers.                               |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SL-BWP-Generic* field descriptions                                   |
+=======================================================================+
| ***sl-LengthSymbols***                                                |
|                                                                       |
| This field indicates the number of symbols used for sidelink in a     |
| slot without S-SSB. A single value can be (pre)configured per         |
| sidelink bandwidth part.                                              |
+-----------------------------------------------------------------------+
| ***sl-StartSymbol***                                                  |
|                                                                       |
| This field indicates the starting symbol used for sidelink in a slot  |
| without S-SSB. A single value can be (pre)configured per sidelink     |
| bandwidth part.                                                       |
+-----------------------------------------------------------------------+
| ***sl-Unlicensed***                                                   |
|                                                                       |
| This field indicates the configurations for sidelink carrier of       |
| shared spectrum channel access. This field is not expected to be      |
| provided when *sl-FreqInfoListSizeExt* or                             |
| *sl-PreconfigFreqInfoListSizeExt* is present.                         |
+-----------------------------------------------------------------------+
| ***sl-TxDirectCurrentLocation***                                      |
|                                                                       |
| The sidelink Tx/Rx Direct Current location for the carrier. Only      |
| values in the value range of this field between 0 and 3299, which     |
| indicate the subcarrier index within the carrier corresponding to the |
| numerology of the corresponding sidelink BWP and value 3300, which    |
| indicates \"Outside the carrier\" and value 3301, which indicates     |
| \"Undetermined position within the carrier\" are used in this version |
| of the specification.                                                 |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SL-Unlicensed* field descriptions                                    |
+=======================================================================+
| ***sl-AbsoluteFrequencySSB-NonAnchorList***                           |
|                                                                       |
| Indicates the lowest S-SSB in a non-anchor RB set via each parameter  |
| in this list. Anchor RB set refers to the RB set where S-SSB          |
| indicated by *sl-AbsoluteFrequencySSB-r16* locates.                   |
+-----------------------------------------------------------------------+
| ***sl-CPE-StartingPositionS-SSB***                                    |
|                                                                       |
| Indicates the CPE starting position within the last symbol before the |
| start of S-SSB transmission. The value is an index of the set of all  |
| candidate CPE starting positions specified in Table 5.3.1-3 of \[16,  |
| TS 38.211\] for Ci=1 and the corresponding SCS of the SL BWP.         |
+-----------------------------------------------------------------------+
| ***sl-CWS-ForPsschWithoutHarqAck***                                   |
|                                                                       |
| The latest CW_p is autonomously increased to the next higher allowed  |
| value for every priority class p of {1,2,3,4} if the same CW_p which  |
| is different from CW\_(max,p) is consecutively used for general of    |
| N_init in SL Type 1 LBT for a number of times indicated by this       |
| parameter. This operation is restricted only to PSCCH/PSSCH           |
| transmission(s) with \"HARQ feedback enabled/disabled indicator\" in  |
| the 2nd stage SCI set to disabled, regardless of whether PSFCH        |
| resources being configured in a resource pool.                        |
+-----------------------------------------------------------------------+
| ***sl-GapOfAdditionalSSSB-Occasion***                                 |
|                                                                       |
| Indicate the gap between each R16/R17 NR SL S-SSB slot and its first  |
| corresponding additional candidate S-SSB occasion, and the gap        |
| between adjacent two additional candidate S-SSB occasions             |
| corresponding to a R16/R17 NR SL S-SSB slot.                          |
+-----------------------------------------------------------------------+
| ***sl-IntraCellGuardBandsSL-List***                                   |
|                                                                       |
| List of intra-cell guard bands for operation with shared spectrum     |
| channel access. If not configured, the guard bands are defined        |
| according to 38.101-1 \[15\], see TS 38.214 \[19\], clause 7. For     |
| operation in licensed spectrum, this field is absent, and no UE       |
| action is required.                                                   |
|                                                                       |
| NOTE: Value \'0\' is not expected to be (pre-)configured for          |
| *nrofCRBs* when the SL BWP is larger than UE supported RF bandwidth   |
| for SL-U operation.                                                   |
+-----------------------------------------------------------------------+
| ***sl-LBT-FailureRecoveryConfig***                                    |
|                                                                       |
| Configures parameters used for detection and cancellation of Sidelink |
| consistent LBT failures for operation with shared spectrum channel    |
| access, as specified in TS 38.321 \[3\].                              |
+-----------------------------------------------------------------------+
| ***sl-NumOfAdditionalSSSBOccasion***                                  |
|                                                                       |
| Indicate the number of additional candidate S-SSB occasion(s) for     |
| each R16/R17 NR SL S-SSB slot.                                        |
+-----------------------------------------------------------------------+
| ***sl-SSSBPowerOffsetOfAnchorRBSet***                                 |
|                                                                       |
| Indicate the power offset for one S-SSB transmission on anchor RB     |
| set, where anchor RB set refers to the RB set where S-SSB indicated   |
| by *sl-AbsoluteFrequencySSB-r16* locates. Value *value1* corresponds  |
| to the power offset of 10lg(N), where N is the number of S-SSB        |
| repetitions within the anchor RB set, and *value2* corresponds to the |
| power offset of 10lg(W), where W is the maximum total number of S-SSB |
| repetitions on RB sets within the SL-BWP.                             |
+-----------------------------------------------------------------------+
| ***sl-StartingSymbolFirst***                                          |
|                                                                       |
| Indicates the location of first starting symbol within a slot. Value  |
| *sym0* corresponds to first symbol, value *sym1* corresponds to the   |
| second symbol and so on. If the field is not configured, the UE shall |
| use value *sym0*.                                                     |
+-----------------------------------------------------------------------+
| ***sl-StartingSymbolSecond***                                         |
|                                                                       |
| Indicates the location of second starting symbol within a slot. Value |
| *sym3* corresponds to fourth symbol, value *sym4* corresponds to the  |
| fifth symbol and so on.                                               |
|                                                                       |
| The number of symbols used for PSCCH/PSSCH transmission from second   |
| starting symbol is not smaller than 6. Within a slot, the second      |
| starting symbol is later than the first starting symbol. PSCCH/PSSCH  |
| transmission starting from first or second starting symbol shall have |
| the same ending symbol within a slot.                                 |
+-----------------------------------------------------------------------+
| ***sl-TransmissionStructureForPSCCHandPSSCH***                        |
|                                                                       |
| Indicate a SL-BWP is (pre-)configured with contiguous RB-based or     |
| interlace RB-based PSCCH/PSSCH transmission. Contiguous RB-based      |
| PSCCH/PSSCH are applicable in region with no OCB requirement, or with |
| OCB exemption.                                                        |
+-----------------------------------------------------------------------+

#### -- *SL-BWP-ConfigCommon*

The IE *SL-BWP-ConfigCommon* is used to configure the cell-specific
configuration information on one particular sidelink bandwidth part.

*SL-BWP-ConfigCommon* information element

\-- ASN1START

\-- TAG-SL-BWP-CONFIGCOMMON-START

SL-BWP-ConfigCommon-r16 ::= SEQUENCE {

sl-BWP-Generic-r16 SL-BWP-Generic-r16 OPTIONAL, \-- Need R

sl-BWP-PoolConfigCommon-r16 SL-BWP-PoolConfigCommon-r16 OPTIONAL, \--
Need R

\...,

\[\[

sl-BWP-PoolConfigCommonPS-r17 SL-BWP-PoolConfigCommon-r16 OPTIONAL, \--
Need R

sl-BWP-DiscPoolConfigCommon-r17 SL-BWP-DiscPoolConfigCommon-r17 OPTIONAL
\-- Need R

\]\],

\[\[

sl-BWP-PoolConfigCommonA2X-r18 SL-BWP-PoolConfigCommon-r16 OPTIONAL \--
Need R

\]\]

}

\-- TAG-SL-BWP-CONFIGCOMMON-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-BWP-ConfigCommon* field descriptions                              |
+=======================================================================+
| ***sl-BWP-DiscPoolConfigCommon***                                     |
|                                                                       |
| This field indicates the NR sidelink discovery dedicated resource     |
| pool configurations on the configured sidelink BWP. The total number  |
| of Rx/Tx resource pools configured for communication and discovery    |
| does not exceed the maximum number of Rx/Tx resource pool for NR      |
| sidelink communication (i.e. *maxNrofRXPool-r16/maxNrofTXPool-r16*).  |
+-----------------------------------------------------------------------+
| ***sl-BWP-Generic***                                                  |
|                                                                       |
| This field indicates the generic parameters on the configured         |
| sidelink BWP.                                                         |
+-----------------------------------------------------------------------+
| ***sl-BWP-PoolConfigCommon***                                         |
|                                                                       |
| This field indicates the resource pool configurations on the          |
| configured sidelink BWP.                                              |
+-----------------------------------------------------------------------+
| ***sl-BWP-PoolConfigCommonA2X***                                      |
|                                                                       |
| This field indicates the resource pool configurations for A2X         |
| services on the configured sidelink BWP. This field does not include  |
| *sl-TxPoolExceptional*.                                               |
+-----------------------------------------------------------------------+
| ***sl-BWP-PoolConfigCommonPS***                                       |
|                                                                       |
| This field indicates the resource pool configurations for power       |
| saving on the configured sidelink BWP. This field does not include    |
| *sl-TxPoolExceptional*.                                               |
+-----------------------------------------------------------------------+

#### -- *SL-BWP-DiscPoolConfig*

The IE *SL-BWP-DiscPoolConfig* is used to configure UE specific NR
sidelink discovery dedicated resource pool.

*SL-BWP-DiscPoolConfig* information element

\-- ASN1START

\-- TAG-SL-BWP-DISCPOOLCONFIG-START

SL-BWP-DiscPoolConfig-r17 ::= SEQUENCE {

sl-DiscRxPool-r17 SEQUENCE (SIZE (1..maxNrofRXPool-r16)) OF
SL-ResourcePool-r16 OPTIONAL, \-- Cond HO

sl-DiscTxPoolSelected-r17 SL-TxPoolDedicated-r16 OPTIONAL, \-- Need M

sl-DiscTxPoolScheduling-r17 SL-TxPoolDedicated-r16 OPTIONAL \-- Need N

}

\-- TAG-SL-BWP-DISCPOOLCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-BWP-DiscPoolConfig* field descriptions                            |
+=======================================================================+
| ***sl-DiscTxPoolScheduling***                                         |
|                                                                       |
| Indicates the resources by which the UE is allowed to transmit NR     |
| sidelink discover based on network scheduling on the configured BWP.  |
| For the PSFCH related configuration, if configured, will be used for  |
| PSFCH transmission/reception.                                         |
|                                                                       |
| When this field is configured together with *sl-TxPoolScheduling*,    |
| the resource pool index (which is used in DCI Format 3_0 in TS 38.212 |
| \[17\], clause 7.3.1.4.1) is defined as 0, 1, ..., x-1 for the        |
| resource pools included in the *sl-TxPoolScheduling*, and x, x+1,     |
| ..., x+y-1 for the resource pools included in                         |
| *sl-DiscTxPoolScheduling*, where x is the number of the resource      |
| pools in *sl-TxPoolScheduling*, and y is the number of resource pools |
| in *sl-DiscTxPoolScheduling*.                                         |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional       Explanation
  Presence          
  ----------------- -----------------------------------------------------
  *HO*              This field is optionally present, need M, in an
                    *RRCReconfiguration* message including
                    *reconfigurationWithSync*; otherwise it is absent,
                    need M.

  -----------------------------------------------------------------------

#### -- *SL-BWP-DiscPoolConfigCommon*

The IE *SL-BWP-DiscPoolConfigCommon* is used to configure the
cell-specific NR sidelink discovery dedicated resource pool.

*SL-BWP-DiscPoolConfigCommon* information element

\-- ASN1START

\-- TAG-SL-BWP-DISCPOOLCONFIGCOMMON-START

SL-BWP-DiscPoolConfigCommon-r17 ::= SEQUENCE {

sl-DiscRxPool-r17 SEQUENCE (SIZE (1..maxNrofRXPool-r16)) OF
SL-ResourcePool-r16 OPTIONAL, \-- Need R

sl-DiscTxPoolSelected-r17 SEQUENCE (SIZE (1..maxNrofTXPool-r16)) OF
SL-ResourcePoolConfig-r16 OPTIONAL, \-- Need R

\...

}

\-- TAG-SL-BWP-DISCPOOLCONFIGCOMMON-STOP

\-- ASN1STOP

#### -- *SL-BWP-PoolConfig*

The IE *SL-BWP-PoolConfig* is used to configure NR sidelink
communication resource pool.

*SL-BWP-PoolConfig* information element

\-- ASN1START

\-- TAG-SL-BWP-POOLCONFIG-START

SL-BWP-PoolConfig-r16 ::= SEQUENCE {

sl-RxPool-r16 SEQUENCE (SIZE (1..maxNrofRXPool-r16)) OF
SL-ResourcePool-r16 OPTIONAL, \-- Cond HO

sl-TxPoolSelectedNormal-r16 SL-TxPoolDedicated-r16 OPTIONAL, \-- Need M

sl-TxPoolScheduling-r16 SL-TxPoolDedicated-r16 OPTIONAL, \-- Need N

sl-TxPoolExceptional-r16 SL-ResourcePoolConfig-r16 OPTIONAL \-- Need M

}

SL-TxPoolDedicated-r16 ::= SEQUENCE {

sl-PoolToReleaseList-r16 SEQUENCE (SIZE (1..maxNrofTXPool-r16)) OF
SL-ResourcePoolID-r16 OPTIONAL, \-- Need N

sl-PoolToAddModList-r16 SEQUENCE (SIZE (1..maxNrofTXPool-r16)) OF
SL-ResourcePoolConfig-r16 OPTIONAL \-- Need N

}

SL-ResourcePoolConfig-r16 ::= SEQUENCE {

sl-ResourcePoolID-r16 SL-ResourcePoolID-r16,

sl-ResourcePool-r16 SL-ResourcePool-r16 OPTIONAL \-- Need M

}

SL-ResourcePoolID-r16 ::= INTEGER (1..maxNrofPoolID-r16)

\-- TAG-SL-BWP-POOLCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-BWP-PoolConfig* field descriptions                                |
+-----------------------------------------------------------------------+
| ***sl-RxPool***                                                       |
|                                                                       |
| Indicates the receiving resource pool on the configured BWP. For the  |
| PSFCH related configuration, if configured, will be used for PSFCH    |
| transmission/reception. If the field is included, it replaces any     |
| previous list, i.e. all the entries of the list are replaced and each |
| of the *SL-ResourcePool* entries is considered to be newly created.   |
+-----------------------------------------------------------------------+
| ***sl-TxPoolExceptional***                                            |
|                                                                       |
| Indicates the resources by which the UE is allowed to perform NR      |
| sidelink transmission in exceptional conditions on the configured     |
| BWP. For the PSFCH related configuration, if configured, will be used |
| for PSFCH transmission/reception.                                     |
+-----------------------------------------------------------------------+
| ***sl-TxPoolScheduling***                                             |
|                                                                       |
| Indicates the resources by which the UE is allowed to perform NR      |
| sidelink transmission based on network scheduling on the configured   |
| BWP. For the PSFCH related configuration, if configured, will be used |
| for PSFCH transmission/reception.                                     |
+-----------------------------------------------------------------------+
| ***sl-TxPoolSelectedNormal***                                         |
|                                                                       |
| Indicates the resources by which the UE is allowed to perform NR      |
| sidelink transmission by UE autonomous resource selection on the      |
| configured BWP. For the PSFCH related configuration, if configured,   |
| will be used for PSFCH transmission/reception.                        |
+=======================================================================+

  -----------------------------------------------------------------------
  Conditional       Explanation
  Presence          
  ----------------- -----------------------------------------------------
  *HO*              This field is optionally present, need M, in an
                    *RRCReconfiguration* message including
                    *reconfigurationWithSync*; otherwise it is absent,
                    Need M.

  -----------------------------------------------------------------------

#### -- *SL-BWP-PoolConfigCommon*

The IE *SL-BWP-PoolConfigCommon* is used to configure the cell-specific
NR sidelink communication resource pool.

*SL-BWP-PoolConfigCommon* information element

\-- ASN1START

\-- TAG-SL-BWP-POOLCONFIGCOMMON-START

SL-BWP-PoolConfigCommon-r16 ::= SEQUENCE {

sl-RxPool-r16 SEQUENCE (SIZE (1..maxNrofRXPool-r16)) OF
SL-ResourcePool-r16 OPTIONAL, \-- Need R

sl-TxPoolSelectedNormal-r16 SEQUENCE (SIZE (1..maxNrofTXPool-r16)) OF
SL-ResourcePoolConfig-r16 OPTIONAL, \-- Need R

sl-TxPoolExceptional-r16 SL-ResourcePoolConfig-r16 OPTIONAL \-- Need R

}

\-- TAG-SL-BWP-POOLCONFIGCOMMON-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-BWP-PoolConfigCommon* field descriptions                          |
+-----------------------------------------------------------------------+
| ***sl-TxPoolExceptional***                                            |
|                                                                       |
| Indicates the resources by which the UE is allowed to perform NR      |
| sidelink transmission in exceptional conditions on the configured     |
| BWP. For the PSFCH related configuration, if configured, will be used |
| for PSFCH transmission/reception. This field is not present when      |
| *SL-BWP-PoolConfigCommon* is included in *SidelinkPreconfigNR*.       |
+=======================================================================+

#### -- *SL-BWP-PRS-PoolConfig*

The IE *SL-BWP-PRS-PoolConfig* is used to configure UE specific NR
sidelink PRS dedicated resource pool.

*SL-BWP-PRS-PoolConfig* information element

\-- ASN1START

\-- TAG-SL-BWP-PRS-POOLCONFIG-START

SL-BWP-PRS-PoolConfig-r18 ::= SEQUENCE {

sl-PRS-RxPool-r18 SEQUENCE (SIZE (1..maxNrofRXPool-r16)) OF
SL-PRS-ResourcePool-r18 OPTIONAL, \-- Cond HO

sl-PRS-TxPoolSelectedNormal-r18 SL-PRS-TxPoolDedicated-r18 OPTIONAL, \--
Need M

sl-PRS-TxPoolScheduling-r18 SL-PRS-TxPoolDedicated-r18 OPTIONAL, \--
Need M

sl-PRS-TxPoolExceptional-r18 SL-PRS-ResourcePoolConfig-r18 OPTIONAL \--
Need R

}

SL-PRS-TxPoolDedicated-r18 ::= SEQUENCE {

sl-PRS-PoolToReleaseList-r1 SEQUENCE (SIZE
(1..maxNrofSL-PRS-TxPool-r18)) OF SL-PRS-ResourcePoolID-r18 OPTIONAL,
\-- Need N

sl-PRS-PoolToAddModList-r18 SEQUENCE (SIZE
(1..maxNrofSL-PRS-TxPool-r18)) OF SL-PRS-ResourcePoolConfig-r18 OPTIONAL
\-- Need N

}

SL-PRS-ResourcePoolConfig-r18 ::= SEQUENCE {

sl-PRS-ResourcePoolID-r18 SL-PRS-ResourcePoolID-r18,

sl-PRS-ResourcePool-r18 SL-PRS-ResourcePool-r18 OPTIONAL \-- Need M

}

SL-PRS-ResourcePoolID-r18 ::= INTEGER (1.. maxNrofSL-PRS-TxPool-r18)

\-- TAG-SL-BWP-PRS-POOLCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-BWP-PRS-PoolConfig* field descriptions                            |
+=======================================================================+
| ***sl-PRS-TxPoolSelectedNormal***                                     |
|                                                                       |
| Indicates the resources by which the UE is allowed to perform SL-PRS  |
| transmission by UE autonomous resource selection on the configured    |
| BWP.                                                                  |
+-----------------------------------------------------------------------+
| ***sl-PRS-TxPoolScheduling***                                         |
|                                                                       |
| Indicates the resources by which the UE is allowed to perform SL-PRS  |
| transmission based on network selection on the configured BWP.        |
+-----------------------------------------------------------------------+
| ***sl-PRS-TxPoolExceptional***                                        |
|                                                                       |
| Indicates the resources by which the UE is allowed to perform SL-PRS  |
| transmission in exceptional conditions on the configured BWP.         |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional       Explanation
  Presence          
  ----------------- -----------------------------------------------------
  *HO*              This field is optionally present, need M, in an
                    *RRCReconfiguration* message including
                    *reconfigurationWithSync*; otherwise it is absent,
                    Need M.

  -----------------------------------------------------------------------

#### -- *SL-BWP-PRS-PoolConfigCommon*

The IE *SL-BWP-PRS-PoolConfigCommon* is used to configure the
cell-specific NR sidelink PRS dedicated resource pool.

*SL-BWP-PRS-PoolConfigCommon* information element

\-- ASN1START

\-- TAG-SL-BWP-PRS-POOLCONFIGCOMMON-START

SL-BWP-PRS-PoolConfigCommon-r18 ::= SEQUENCE {

sl-PRS-RxPool-r18 SEQUENCE (SIZE (1..maxNrofRXPool-r16)) OF
SL-PRS-ResourcePool-r18 OPTIONAL, \-- Need R

sl-PRS-TxPoolSelectedNormal-r18 SEQUENCE (SIZE
(1..maxNrofSL-PRS-TxPool-r18)) OF SL-PRS-ResourcePoolConfig-r18
OPTIONAL, \-- Need R

sl-PRS-TxPoolExceptional-r18 SL-PRS-ResourcePoolConfig-r18 OPTIONAL, \--
Need R

\...

}

\-- TAG-SL-BWP-PRS-POOLCONFIGCOMMON-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-BWP-PRS-PoolConfigCommon* field descriptions                      |
+-----------------------------------------------------------------------+
| ***sl-PRS-TxPoolExceptional***                                        |
|                                                                       |
| Indicates the resources by which the UE is allowed to perform NR      |
| sidelink transmission in exceptional conditions on the configured     |
| BWP. This field is not present when *SL-BWP-PRS-PoolConfigCommon* is  |
| included in *SL-PreconfigurationNR*                                   |
+=======================================================================+

#### -- *SL-CBR-PriorityTxConfigList*

The IE *SL-CBR-PriorityTxConfigList* indicates the mapping between PSSCH
transmission parameter (such as MCS, PRB number, retransmission number,
CR limit) sets by using the indexes of the configurations provided in
*sl-CBR-PSSCH-TxConfigList*, CBR ranges by an index to the entry of the
CBR range configuration in *sl-CBR-RangeConfigList*, and priority
ranges. It also indicates the default PSSCH transmission parameters to
be used when CBR measurement results are not available, and MCS range
for the MCS tables used in the resource pool.

*SL-CBR-PriorityTxConfigList* information element

\-- ASN1START

\-- TAG-SL-CBR-PRIORITYTXCONFIGLIST-START

SL-CBR-PriorityTxConfigList-r16 ::= SEQUENCE (SIZE (1..8)) OF
SL-PriorityTxConfigIndex-r16

SL-CBR-PriorityTxConfigList-v1650 ::= SEQUENCE (SIZE (1..8)) OF
SL-PriorityTxConfigIndex-v1650

SL-PriorityTxConfigIndex-r16 ::= SEQUENCE {

sl-PriorityThreshold-r16 INTEGER (1..8) OPTIONAL, \-- Need M

sl-DefaultTxConfigIndex-r16 INTEGER (0..maxCBR-Level-1-r16) OPTIONAL,
\-- Need M

sl-CBR-ConfigIndex-r16 INTEGER (0..maxCBR-Config-1-r16) OPTIONAL, \--
Need M

sl-Tx-ConfigIndexList-r16 SEQUENCE (SIZE (1.. maxCBR-Level-r16)) OF
SL-TxConfigIndex-r16 OPTIONAL \-- Need M

}

SL-PriorityTxConfigIndex-v1650 ::= SEQUENCE {

sl-MCS-RangeList-r16 SEQUENCE (SIZE (1..maxCBR-Level-r16)) OF
SL-MinMaxMCS-List-r16 OPTIONAL \-- Need M

}

SL-TxConfigIndex-r16 ::= INTEGER (0..maxTxConfig-1-r16)

\-- TAG-SL-CBR-PRIORITYTXCONFIGLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-CBR-PriorityTxConfigList* field descriptions                      |
+-----------------------------------------------------------------------+
| ***sl-CBR-ConfigIndex***                                              |
|                                                                       |
| Indicates the CBR ranges to be used by an index to the entry of the   |
| CBR range configuration in *sl-CBR-RangeConfigList*.                  |
+-----------------------------------------------------------------------+
| ***sl-DefaultTxConfigIndex***                                         |
|                                                                       |
| Indicates the PSSCH transmission parameters to be used by the UEs     |
| which do not have available CBR measurement results, by means of an   |
| index to the corresponding entry in *sl-Tx-ConfigIndexList*. Value 0  |
| indicates the first entry in *sl-Tx-ConfigIndexList*. The field is    |
| ignored if the UE has available CBR measurement results.              |
+-----------------------------------------------------------------------+
| ***sl-MCS-RangeList***                                                |
|                                                                       |
| Indicates the minimum MCS value and maximum MCS value for the         |
| associated MCS table(s). UE shall ignore the minimum MCS value and    |
| maximum MCS value used for table of 64QAM indicated in                |
| *SL-CBR-PriorityTxConfigList-r16* if                                  |
| *SL-CBR-PriorityTxConfigList-v1650* is present.                       |
+-----------------------------------------------------------------------+
| ***sl-PriorityThreshold***                                            |
|                                                                       |
| Indicates the upper bound of priority range which is associated with  |
| the configurations in *sl-CBR-ConfigIndex* and in                     |
| *sl-Tx-ConfigIndexList*. The upper bounds of the priority ranges are  |
| configured in ascending order for consecutive entries of              |
| *SL-PriorityTxConfigIndex* in *SL-CBR-PriorityTxConfigList*. For the  |
| first entry of S*L-PriorityTxConfigIndex*, the lower bound of the     |
| priority range is 1.                                                  |
+-----------------------------------------------------------------------+
| ***SL-CBR-PriorityTxConfigList-v1650***                               |
|                                                                       |
| If included, it includes the same number of entries, and listed in    |
| the same order, as in *SL-CBR-PriorityTxConfigList-r16*.              |
+=======================================================================+

#### -- *SL-CBR-CommonTxConfigList*

The IE *SL-CBR-CommonTxConfigList* indicates the list of PSSCH
transmission parameters (such as MCS, sub-channel number, retransmission
number, CR limit) in *sl-CBR-PSSCH-TxConfigList*, and the list of CBR
ranges in *sl-CBR-RangeConfigList*, to configure congestion control to
the UE for sidelink communication.

*SL-CBR-CommonTxConfigList* information element

\-- ASN1START

\-- TAG-SL-CBR-COMMONTXCONFIGLIST-START

SL-CBR-CommonTxConfigList-r16 ::= SEQUENCE {

sl-CBR-RangeConfigList-r16 SEQUENCE (SIZE (1..maxCBR-Config-r16)) OF
SL-CBR-LevelsConfig-r16 OPTIONAL, \-- Need M

sl-CBR-PSSCH-TxConfigList-r16 SEQUENCE (SIZE (1.. maxTxConfig-r16)) OF
SL-CBR-PSSCH-TxConfig-r16 OPTIONAL \-- Need M

}

SL-CBR-LevelsConfig-r16 ::= SEQUENCE (SIZE (1..maxCBR-Level-r16)) OF
SL-CBR-r16

SL-CBR-PSSCH-TxConfig-r16 ::= SEQUENCE {

sl-CR-Limit-r16 INTEGER(0..10000) OPTIONAL, \-- Need M

sl-TxParameters-r16 SL-PSSCH-TxParameters-r16 OPTIONAL \-- Need M

}

SL-CBR-r16 ::= INTEGER (0..100)

\-- TAG-SL-CBR-COMMONTXCONFIGLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-CBR-CommonTxConfigList* field descriptions                        |
+-----------------------------------------------------------------------+
| ***sl-CBR-RangeConfigList***                                          |
|                                                                       |
| Each entry in *sl-CBR-RangeConfigList* is *SL-CBR-LevelsConfig*       |
| containing the list of CBR ranges. The values within each             |
| *SL-CBR-LevelsConfig* indicate the upper bound of the each CBR range  |
| (and implicitly indicate the lower bound of next CBR range) and are   |
| configured in ascending order*.* For the first CBR range of each      |
| *SL-CBR-LevelsConfig*, the lower bound of the CBR range is 0. Value 0 |
| corresponds to 0, value 1 to 0.01, value 2 to 0.02, and so on.        |
+-----------------------------------------------------------------------+
| ***sl-CR-Limit***                                                     |
|                                                                       |
| Indicates the maximum limit on the occupancy ratio. Value 0           |
| corresponds to 0, value 1 to 0.0001, value 2 to 0.0002, and so on     |
| (i.e. in steps of 0.0001) until value 10000, which corresponds to 1.  |
+-----------------------------------------------------------------------+
| ***sl-CBR-PSSCH-TxConfigList***                                       |
|                                                                       |
| Indicates the list of available PSSCH transmission parameters (such   |
| as MCS, sub-channel number, retransmission number and CR limit)       |
| configurations.                                                       |
+-----------------------------------------------------------------------+
| ***sl-TxParameters***                                                 |
|                                                                       |
| Indicates PSSCH transmission parameters.                              |
+=======================================================================+

#### -- *SL-CBR-CommonTxDedicatedSL-PRS-RP-List*

The IE *SL-CBR-CommonTxDedicatedSL-PRS-RP-List* indicates the list of SL
PRS transmission parameters (such as Maximum SL PRS transmission power,
Maximum Number of SL PRS (re-)transmissions, and CR limit) in
*sl-CBR-SL-PRS-TxConfigList*, and the list of CBR ranges in
*sl-CBR-RangeDedicatedSL-PRS-RP-List*, to configure congestion control
to the UE for sidelink positioning.

*SL-CBR-CommonTxDedicatedSL-PRS-RP-List* information element

\-- ASN1START

\-- TAG- SL-CBR-COMMONTXDEDICATEDSL-PRS-RP-LIST-START

SL-CBR-CommonTxDedicatedSL-PRS-RP-List-r18 ::= SEQUENCE {

sl-CBR-RangeDedicatedSL-PRS-RP-List-r18 SEQUENCE (SIZE
(1..maxCBR-ConfigDedSL-PRS-1-r18)) OF
SL-CBR-LevelsDedicatedSL-PRS-RP-r18

OPTIONAL, \-- Need M

sl-CBR-SL-PRS-TxConfigList-r18 SEQUENCE (SIZE
(1..maxNrofSL-PRS-TxConfig-r18)) OF SL-CBR-SL-PRS-TxConfig-r18

OPTIONAL \-- Need M

}

SL-CBR-LevelsDedicatedSL-PRS-RP-r18 ::= SEQUENCE (SIZE
(0..maxCBR-LevelDedSL-PRS-1-r18)) OF SL-CBR-Dedicated-SL-PRS-RP-r18

SL-CBR-SL-PRS-TxConfig-r18 ::= SEQUENCE {

sl-PRS-CR-Limit-r18 INTEGER(0..10000) OPTIONAL, \-- Need M

sl-PRS-MaxTx-power-r18 INTEGER (-30..33) OPTIONAL, \-- Need M

sl-PRS-MaxNum-Transmissions-r18 INTEGER(1..32) OPTIONAL \-- Need M

}

SL-CBR-Dedicated-SL-PRS-RP-r18 ::= INTEGER (0..100)

\-- TAG-SL-CBR-COMMONTXDEDICATEDSL-PRS-RP-LIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-CBR-CommonTxDedicatedSL-PRS-RP-List* field descriptions           |
+-----------------------------------------------------------------------+
| ***sl-CBR-RangeDedicatedSL-PRS-RP-List***                             |
|                                                                       |
| Indicates the list of CBR ranges. Each entry of the list in           |
| *SL-CBR-LevelsDedicatedSL-PRS-RP* indicates the upper bound of the    |
| CBR range for the respective entry. The upper bounds of the CBR       |
| ranges are configured in ascending order for consecutive entries of   |
| *SL-CBR-LevelsDedicatedSL-PRS-RP*. For the first entry of             |
| *SL-CBR-LevelsDedicatedSL-PRS-RP* the lower bound of the CBR range is |
| 0. Value 0 corresponds to 0, value 1 to 0.01, value 2 to 0.02, and so |
| on.                                                                   |
+-----------------------------------------------------------------------+
| ***sl-CBR-SL-PRS-TxConfigList***                                      |
|                                                                       |
| Indicates the list of available SL PRS transmission parameters        |
| configurations.                                                       |
+-----------------------------------------------------------------------+
| ***sl-PRS-CR-Limit***                                                 |
|                                                                       |
| Indicates the maximum limit on the occupancy ratio. Value 0           |
| corresponds to 0, value 1 to 0.0001, value 2 to 0.0002, and so on     |
| (i.e. in steps of 0.0001) until value 10000, which corresponds to 1.  |
+-----------------------------------------------------------------------+
| ***sl-PRS-MaxNum-Transmissions***                                     |
|                                                                       |
| Indicates maximum Number of SL PRS (re-)transmissions.                |
+-----------------------------------------------------------------------+
| ***sl-PRS-MaxTx-power***                                              |
|                                                                       |
| Indicates maximum SL PRS transmission power. The unit is dBm.         |
+=======================================================================+

#### -- *SL-ConfigDedicatedNR*

The IE *SL-ConfigDedicatedNR* specifies the dedicated configuration
information for NR sidelink communication/discovery/positioning.

*SL-ConfigDedicatedNR* information element

\-- ASN1START

\-- TAG-SL-CONFIGDEDICATEDNR-START

SL-ConfigDedicatedNR-r16 ::= SEQUENCE {

sl-PHY-MAC-RLC-Config-r16 SL-PHY-MAC-RLC-Config-r16 OPTIONAL, \-- Need M

sl-RadioBearerToReleaseList-r16 SEQUENCE (SIZE (1..maxNrofSLRB-r16)) OF
SLRB-Uu-ConfigIndex-r16 OPTIONAL, \-- Need N

sl-RadioBearerToAddModList-r16 SEQUENCE (SIZE (1..maxNrofSLRB-r16)) OF
SL-RadioBearerConfig-r16 OPTIONAL, \-- Need N

sl-MeasConfigInfoToReleaseList-r16 SEQUENCE (SIZE
(1..maxNrofSL-Dest-r16)) OF SL-DestinationIndex-r16 OPTIONAL, \-- Need N

sl-MeasConfigInfoToAddModList-r16 SEQUENCE (SIZE
(1..maxNrofSL-Dest-r16)) OF SL-MeasConfigInfo-r16 OPTIONAL, \-- Need N

t400-r16 ENUMERATED {ms100, ms200, ms300, ms400, ms600, ms1000, ms1500,
ms2000} OPTIONAL, \-- Need M

\...,

\[\[

sl-PHY-MAC-RLC-Config-v1700 SetupRelease { SL-PHY-MAC-RLC-Config-v1700 }
OPTIONAL, \-- Need M

sl-DiscConfig-r17 SetupRelease { SL-DiscConfig-r17} OPTIONAL \-- Need M

\]\],

\[\[

sl-DiscConfig-v1800 SL-DiscConfig-v1800 OPTIONAL \-- Need M

\]\],

\[\[

sl-DiscConfig-v1830 SL-DiscConfig-v1830 OPTIONAL \-- Need M

\]\],

\[\[

sl-DiscConfig-v1840 SL-DiscConfig-v1840 OPTIONAL \-- Need M

\]\]

}

SL-ConfigDedicatedNR-v16k0 ::= SEQUENCE {

sl-PHY-MAC-RLC-Config-v16k0 SL-PHY-MAC-RLC-Config-v16k0 OPTIONAL \--
Need M

}

SL-DestinationIndex-r16 ::= INTEGER (0..maxNrofSL-Dest-1-r16)

SL-PHY-MAC-RLC-Config-r16::= SEQUENCE {

sl-ScheduledConfig-r16 SetupRelease { SL-ScheduledConfig-r16 } OPTIONAL,
\-- Need M

sl-UE-SelectedConfig-r16 SetupRelease { SL-UE-SelectedConfig-r16 }
OPTIONAL, \-- Need M

sl-FreqInfoToReleaseList-r16 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-Freq-Id-r16 OPTIONAL, \-- Need N

sl-FreqInfoToAddModList-r16 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-FreqConfig-r16 OPTIONAL, \-- Need N

sl-RLC-BearerToReleaseList-r16 SEQUENCE (SIZE (1..maxSL-LCID-r16)) OF
SL-RLC-BearerConfigIndex-r16 OPTIONAL, \-- Need N

sl-RLC-BearerToAddModList-r16 SEQUENCE (SIZE (1..maxSL-LCID-r16)) OF
SL-RLC-BearerConfig-r16 OPTIONAL, \-- Need N

sl-MaxNumConsecutiveDTX-r16 ENUMERATED {n1, n2, n3, n4, n6, n8, n16,
n32} OPTIONAL, \-- Need M

sl-CSI-Acquisition-r16 ENUMERATED {enabled} OPTIONAL, \-- Need R

sl-CSI-SchedulingRequestId-r16 SetupRelease {SchedulingRequestId}
OPTIONAL, \-- Need M

sl-SSB-PriorityNR-r16 INTEGER (1..8) OPTIONAL, \-- Need R

networkControlledSyncTx-r16 ENUMERATED {on, off} OPTIONAL \-- Need M

}

SL-PHY-MAC-RLC-Config-v16k0 ::= SEQUENCE {

sl-FreqInfoToAddModListExt-v16k0 SEQUENCE (SIZE (1..maxNrofFreqSL-r16))
OF SL-FreqConfigExt-v16k0 OPTIONAL \-- Need N

}

SL-PHY-MAC-RLC-Config-v1700 ::= SEQUENCE {

sl-DRX-Config-r17 SL-DRX-Config-r17 OPTIONAL, \-- Need M

sl-RLC-ChannelToReleaseList-r17 SEQUENCE (SIZE (1..maxSL-LCID-r16)) OF
SL-RLC-ChannelID-r17 OPTIONAL, \-- Cond L2U2N

sl-RLC-ChannelToAddModList-r17 SEQUENCE (SIZE (1..maxSL-LCID-r16)) OF
SL-RLC-ChannelConfig-r17 OPTIONAL, \-- Cond L2U2N

\...,

\[\[

sl-RLC-BearerToAddModListSizeExt-v1800 SEQUENCE (SIZE
(1..maxSL-LCID-r16)) OF SL-RLC-BearerConfig-r16 OPTIONAL, \-- Need N

sl-RLC-BearerToReleaseListSizeExt-v1800 SEQUENCE (SIZE
(1..maxSL-LCID-r16)) OF SL-RLC-BearerConfigIndex-v1800 OPTIONAL, \--
Need N

sl-FreqInfoToAddModListExt-v1800 SEQUENCE (SIZE (1..maxNrofFreqSL-r16))
OF SL-FreqConfigExt-v1800 OPTIONAL, \-- Need N

sl-LBT-SchedulingRequestId-r18 SetupRelease {SchedulingRequestId}
OPTIONAL, \-- Need M

sl-SyncFreqList-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
SL-Freq-Id-r16 OPTIONAL, \-- Need M

sl-SyncTxMultiFreq-r18 ENUMERATED {true} OPTIONAL, \-- Need R

sl-MaxTransPowerCA-r18 P-Max OPTIONAL, \-- Need R

sl-SCCH-CarrierSetConfig-r18 SetupRelease
{SL-SCCH-CarrierSetConfigList-r18} OPTIONAL, \-- Need M

sl-PRS-SchedulingRequestId-r18 SetupRelease {SchedulingRequestId}
OPTIONAL \-- Need M

\]\]

}

SL-DiscConfig-r17::= SEQUENCE {

sl-RelayUE-Config-r17 SetupRelease { SL-RelayUE-Config-r17} OPTIONAL,
\-- Cond L2RelayUE

sl-RemoteUE-Config-r17 SetupRelease { SL-RemoteUE-Config-r17} OPTIONAL
\-- Cond L2RemoteUE

}

SL-DiscConfig-v1800 ::= SEQUENCE {

sl-RelayUE-ConfigU2U-r18 SetupRelease { SL-RelayUE-ConfigU2U-r18}
OPTIONAL, \-- Cond U2URelayUE

sl-RemoteUE-ConfigU2U-r18 SetupRelease { SL-RemoteUE-ConfigU2U-r18}
OPTIONAL \-- Cond U2URemoteUE

}

SL-SCCH-CarrierSetConfigList-r18 ::= SEQUENCE (SIZE
(1..maxNrofSL-CarrierSetConfig-r18)) OF SL-SCCH-CarrierSetConfig-r18

SL-SCCH-CarrierSetConfig-r18 ::= SEQUENCE {

sl-DestinationList-r18 SEQUENCE (SIZE (1..maxNrofSL-Dest-r16)) OF
SL-DestinationIdentity-r16,

sl-SRB-Identity-r18 SEQUENCE (SIZE (1..3)) OF SRB-Identity,

sl-AllowedCarrierFreqSet1-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
INTEGER (1..maxNrofFreqSL-r16),

sl-AllowedCarrierFreqSet2-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF
INTEGER (1..maxNrofFreqSL-r16)

}

SL-DiscConfig-v1830 ::= SEQUENCE {

sl-RemoteUE-ConfigU2U-v1830 SetupRelease { SL-RemoteUE-ConfigU2U-v1830}
OPTIONAL \-- Cond U2URemoteUE

}

SL-DiscConfig-v1840 ::= SEQUENCE {

sl-RelayUE-ConfigU2U-v1840 SetupRelease { SL-RelayUE-ConfigU2U-v1840}
OPTIONAL \-- Cond U2URelayUE

}

\-- TAG-SL-CONFIGDEDICATEDNR-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-ConfigDedicatedNR* field descriptions                             |
+-----------------------------------------------------------------------+
| ***sl-LBT-SchedulingRequestId***                                      |
|                                                                       |
| Indicates the scheduling request configuration applicable for         |
| Sidelink consistent LBT failure report, as specified in TS 38.321     |
| \[3\].                                                                |
+-----------------------------------------------------------------------+
| ***sl-MaxTransPowerCA***                                              |
|                                                                       |
| The maximum total transmit power to be used by the UE across all      |
| sidelink carriers.                                                    |
+-----------------------------------------------------------------------+
| ***sl-MeasConfigInfoToAddModList***                                   |
|                                                                       |
| This field indicates the RSRP measurement configurations for unicast  |
| destinations to add and/or modify.                                    |
+-----------------------------------------------------------------------+
| ***sl-MeasConfigInfoToReleaseList***                                  |
|                                                                       |
| This field indicates the RSRP measurement configurations for unicast  |
| destinations to remove.                                               |
+-----------------------------------------------------------------------+
| ***sl-PHY-MAC-RLC-Config***                                           |
|                                                                       |
| This field indicates the lower layer sidelink radio bearer            |
| configurations.                                                       |
+-----------------------------------------------------------------------+
| ***sl-RadioBearerToAddModList***                                      |
|                                                                       |
| This field indicates one or multiple sidelink radio bearer            |
| configurations to add and/or modify. This field is not configured to  |
| the PC5 connection used for L2 U2N relay operation.                   |
+-----------------------------------------------------------------------+
| ***sl-RadioBearerToReleaseList***                                     |
|                                                                       |
| This field indicates one or multiple sidelink radio bearer            |
| configurations to remove. This field is not configured to the PC5     |
| connection used for L2 U2N relay operation.                           |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-PHY-MAC-RLC-Config* field descriptions                            |
+-----------------------------------------------------------------------+
| ***networkControlledSyncTx***                                         |
|                                                                       |
| This field indicates whether the UE shall transmit synchronisation    |
| information (i.e. become synchronisation source). Value *on*          |
| indicates the UE to transmit synchronisation information while value  |
| *off* indicates the UE to not transmit such information.              |
+-----------------------------------------------------------------------+
| ***sl-DRX-Config***                                                   |
|                                                                       |
| This field indicates the sidelink DRX configuration(s) for unicast,   |
| groupcast and/or broadcast communication, as specified in TS 38.321   |
| \[3\].                                                                |
+-----------------------------------------------------------------------+
| ***sl-MaxNumConsecutiveDTX***                                         |
|                                                                       |
| This field indicates the maximum number of consecutive HARQ DTX       |
| before triggering sidelink RLF. Value n1 corresponds to 1, value n2   |
| corresponds to 2, and so on.                                          |
+-----------------------------------------------------------------------+
| ***sl-FreqInfoToAddModList, sl-FreqInfoToAddModListExt-v16k0,         |
| sl-FreqInfoToAddModListExt-v1800***                                   |
|                                                                       |
| This field indicates the NR sidelink communication configuration on   |
| some carrier frequency (ies) to add and/or modify. If the network     |
| includes *sl-FreqInfoToAddModListExt-v16k0*, it includes the same     |
| number of entries, and listed in the same order, as in                |
| *sl-FreqInfoToAddModList-r16*. If the network includes                |
| *sl-FreqInfoToAddModListExt-v1800*, it includes the same number of    |
| entries, and listed in the same order, as in                          |
| *sl-FreqInfoToAddModList-r16*.                                        |
+-----------------------------------------------------------------------+
| ***sl-FreqInfoToReleaseList***                                        |
|                                                                       |
| This field indicates the NR sidelink communication configuration on   |
| some carrier frequency (ies) to remove. In this release, only one     |
| entry can be configured in the list.                                  |
+-----------------------------------------------------------------------+
| ***sl-RLC-BearerToAddModList, sl-RLC-BearerToAddModListSizeExt***     |
|                                                                       |
| This field indicates one or multiple sidelink RLC bearer              |
| configurations to add and/or modify.                                  |
+-----------------------------------------------------------------------+
| ***sl-RLC-BearerToReleaseList, sl-RLC-BearerToReleaseListSizeExt***   |
|                                                                       |
| This field indicates one or multiple sidelink RLC bearer              |
| configurations to remove.                                             |
+-----------------------------------------------------------------------+
| ***sl-RLC-ChannelToAddModList***                                      |
|                                                                       |
| This field indicates one or multiple PC5 Relay RLC Channel            |
| configurations to add and/or modify. Each PC5 Relay RLC channel       |
| configuration provided by network to L2 U2N Relay UE is uniquely      |
| associated with one L2 U2N Remote UE.                                 |
+-----------------------------------------------------------------------+
| ***sl-RLC-ChannelToReleaseList***                                     |
|                                                                       |
| This field indicates one or multiple PC5 Relay RLC Channel            |
| configurations to remove.                                             |
+-----------------------------------------------------------------------+
| ***sl-ScheduledConfig***                                              |
|                                                                       |
| Indicates the configuration for UE to transmit NR sidelink            |
| communication based on network scheduling. This field is not          |
| configured simultaneously with sl-UE-SelectedConfig. This field is    |
| not configured to a L2 U2N Remote UE.                                 |
+-----------------------------------------------------------------------+
| ***sl-UE-SelectedConfig***                                            |
|                                                                       |
| Indicates the configuration used for UE autonomous resource           |
| selection. This field is not configured simultaneously with           |
| *sl-ScheduledConfig*.                                                 |
+-----------------------------------------------------------------------+
| ***sl-CSI-Acquisition***                                              |
|                                                                       |
| Indicates whether CSI reporting is enabled in sidelink unicast. If    |
| the field is absent, sidelink CSI reporting is disabled.              |
+-----------------------------------------------------------------------+
| ***sl-CSI-SchedulingRequestId***                                      |
|                                                                       |
| If present, it indicates the scheduling request configuration         |
| applicable for Sidelink CSI Reporting MAC CE and Sidelink DRX Command |
| MAC CE, as specified in TS 38.321 \[3\].                              |
+-----------------------------------------------------------------------+
| ***sl-PRS-SchedulingRequestId***                                      |
|                                                                       |
| If present, it indicates the scheduling request configuration         |
| applicable for Sidelink PRS Request MAC CE, as specified in TS 38.321 |
| \[3\].                                                                |
+-----------------------------------------------------------------------+
| ***sl-SSB-PriorityNR***                                               |
|                                                                       |
| This field indicates the priority of NR sidelink SSB transmission and |
| reception.                                                            |
+-----------------------------------------------------------------------+
| ***sl-SyncFreqList***                                                 |
|                                                                       |
| Indicates a list of candidate carrier frequencies that can be used    |
| for the synchronisation of NR sidelink communication.                 |
+-----------------------------------------------------------------------+
| ***sl-SyncTxMultiFreq***                                              |
|                                                                       |
| Indicates that the UE transmits S-SSB on multiple carrier frequencies |
| for NR sidelink communication. If this field is absent, the UE        |
| transmits S-SSB only on the synchronisation carrier frequency.        |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-SCCH-CarrierSetConfig* field descriptions                         |
+-----------------------------------------------------------------------+
| ***sl-AllowedCarrierFreqSet1, sl-AllowedCarrierFreqSet2***            |
|                                                                       |
| Indicates the set of carrier frequencies applicable for the           |
| transmission of the MAC SDUs from the sidelink SRB logical channels   |
| whose associated destination is included in sl-destinationList. If    |
| present, network ensures *sl-AllowedCarrierFreqSet1* and              |
| *sl-AllowedCarrierFreqSet2* do not include the same carrier           |
| frequency. The value 1 corresponds to the frequency of first entry in |
| *sl-FreqInfoList* broadcast in *SIB12*, the value 2 corresponds to    |
| the frequency of first entry in *sl-FreqInfoListSizeExt* broadcast in |
| *SIB12*, the value 3 corresponds to the frequency of second entry in  |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12* and so on.              |
+-----------------------------------------------------------------------+
| ***sl-DestinationList***                                              |
|                                                                       |
| This field indicates the list of destination identify that the        |
| *sl-AllowedCarrierFreqSet1* and *sl-AllowedCarrierFreqSet2* apply.    |
| Only destination identity for unicast link can be included in this    |
| field.                                                                |
+-----------------------------------------------------------------------+
| ***sl-SRB-Identity***                                                 |
|                                                                       |
| This field indicates the list of sidelink SRB identities that the     |
| *sl-AllowedCarrierFreqSet1* and *sl-AllowedCarrierFreqSet2* apply.    |
+=======================================================================+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *L2RelayUE*          For L2 U2N Relay UE, the field is optionally
                       present, Need M. Otherwise, it is absent.

  *L2RemoteUE*         For L2 U2N Remote UE, the field is optionally
                       present, Need M. Otherwise, it is absent.

  *L2U2N*              The field is optional present for L2 U2N or L2 U2U
                       Relay UE and L2 U2N or L2 U2U Remote UE, need N.
                       Otherwise, it is absent.

  *U2URelayUE*         For U2U Relay UE, the field is optionally present,
                       Need M. Otherwise, it is absent.

  *U2URemoteUE*        For U2U Remote UE, the field is optionally
                       present, Need M. Otherwise, it is absent.
  -----------------------------------------------------------------------

#### -- *SL-ConfiguredGrantConfig*

The IE *SL-ConfiguredGrantConfig* specifies the configured grant
configuration information for NR sidelink communication.

*SL-ConfiguredGrantConfig* information element

\-- ASN1START

\-- TAG-SL-CONFIGUREDGRANTCONFIG-START

SL-ConfiguredGrantConfig-r16 ::= SEQUENCE {

sl-ConfigIndexCG-r16 SL-ConfigIndexCG-r16,

sl-PeriodCG-r16 SL-PeriodCG-r16 OPTIONAL, \-- Need M

sl-NrOfHARQ-Processes-r16 INTEGER (1..16) OPTIONAL, \-- Need M

sl-HARQ-ProcID-offset-r16 INTEGER (0..15) OPTIONAL, \-- Need M

sl-CG-MaxTransNumList-r16 SL-CG-MaxTransNumList-r16 OPTIONAL, \-- Need M

rrc-ConfiguredSidelinkGrant-r16 SEQUENCE {

sl-TimeResourceCG-Type1-r16 INTEGER (0..496) OPTIONAL, \-- Need M

sl-StartSubchannelCG-Type1-r16 INTEGER (0..26) OPTIONAL, \-- Need M

sl-FreqResourceCG-Type1-r16 INTEGER (0..6929) OPTIONAL, \-- Need M

sl-TimeOffsetCG-Type1-r16 INTEGER (0..7999) OPTIONAL, \-- Need R

sl-N1PUCCH-AN-r16 PUCCH-ResourceId OPTIONAL, \-- Need M

sl-PSFCH-ToPUCCH-CG-Type1-r16 INTEGER (0..15) OPTIONAL, \-- Need M

sl-ResourcePoolID-r16 SL-ResourcePoolID-r16 OPTIONAL, \-- Need M

sl-TimeReferenceSFN-Type1-r16 ENUMERATED {sfn512} OPTIONAL \-- Need S

} OPTIONAL, \-- Need M

\...,

\[\[

sl-N1PUCCH-AN-Type2-r16 PUCCH-ResourceId OPTIONAL \-- Need M

\]\],

\[\[

sl-StartRBsetCG-Type1-r18 INTEGER (0..4) OPTIONAL \-- Need M

\]\]

}

SL-ConfigIndexCG-r16 ::= INTEGER (0..maxNrofCG-SL-1-r16)

SL-CG-MaxTransNumList-r16 ::= SEQUENCE (SIZE (1..8)) OF
SL-CG-MaxTransNum-r16

SL-CG-MaxTransNum-r16 ::= SEQUENCE {

sl-Priority-r16 INTEGER (1..8),

sl-MaxTransNum-r16 INTEGER (1..32)

}

SL-PeriodCG-r16 ::= CHOICE{

sl-PeriodCG1-r16 ENUMERATED {ms100, ms200, ms300, ms400, ms500, ms600,
ms700, ms800, ms900, ms1000, spare6,

spare5, spare4, spare3, spare2, spare1},

sl-PeriodCG2-r16 INTEGER (1..99)

}

\-- TAG-SL-CONFIGUREDGRANTCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-ConfiguredGrantConfig* field descriptions                         |
+-----------------------------------------------------------------------+
| ***rrc-ConfiguredSidelinkGrant***                                     |
|                                                                       |
| Configuration for \"sidelink configured grant\" transmission with     |
| fully RRC-configured SL grant (Type1). If this field is not           |
| configured, the UE uses SL grant configured by DCI addressed to       |
| SL-CS-RNTI (Type2).                                                   |
+-----------------------------------------------------------------------+
| ***sl-ConfigIndexCG***                                                |
|                                                                       |
| This field indicates the ID to identify sidelink configured grant.    |
+-----------------------------------------------------------------------+
| ***sl-CG-MaxTransNumList***                                           |
|                                                                       |
| This field indicates the maximum number of times that a TB can be     |
| transmitted using the resources provided by the sidelink configured   |
| grant. *sl-Priority* corresponds to the logical channel priority.     |
+-----------------------------------------------------------------------+
| ***sl-FreqResourceCG-Type1***                                         |
|                                                                       |
| Indicates the frequency resource location of sidelink configured      |
| grant type 1. An index giving valid combinations of one or two        |
| starting sub-channel and length (jointly encoded) as resource         |
| indicator value (RIV), as defined in TS 38.214 \[19\].                |
+-----------------------------------------------------------------------+
| ***sl-HARQ-ProcID-Offset***                                           |
|                                                                       |
| Indicates the offset used in deriving the HARQ process ID for         |
| sidelink configured grant type 1 or sidelink configured grant type 2, |
| see TS 38.321 \[3\], clause 5.8.3.                                    |
+-----------------------------------------------------------------------+
| ***sl-N1PUCCH-AN***                                                   |
|                                                                       |
| This field indicates the PUCCH resource for HARQ feedback for         |
| sidelink configured grant type 1. The actual PUCCH-Resource is        |
| configured in *sl-PUCCH-Config* and referred to by its ID.            |
+-----------------------------------------------------------------------+
| ***sl-N1PUCCH-AN-Type2***                                             |
|                                                                       |
| This field indicates the PUCCH resource for HARQ feedback for         |
| PSCCH/PSSCH transmissions without a corresponding PDCCH on sidelink   |
| configured grant type 2. The actual PUCCH-Resource is configured in   |
| *sl-PUCCH-Config* and referred to by its ID.                          |
+-----------------------------------------------------------------------+
| ***sl-NrOfHARQ-Processes***                                           |
|                                                                       |
| This field indicates the number of HARQ processes configured for a    |
| specific sidelink configured grant. It applies for both type 1 and    |
| type 2.                                                               |
+-----------------------------------------------------------------------+
| ***sl-PeriodCG***                                                     |
|                                                                       |
| This field indicates the period of sidelink configured grant in the   |
| unit of ms.                                                           |
+-----------------------------------------------------------------------+
| ***sl-PSFCH-ToPUCCH-CG-Type1***                                       |
|                                                                       |
| This field, for sidelink configured grant type 1, indicates slot      |
| offset between the PSFCH associated with the last PSSCH resource of   |
| each period and the PUCCH occasion used for reporting sidelink HARQ.  |
+-----------------------------------------------------------------------+
| ***sl-ResourcePoolID***                                               |
|                                                                       |
| Indicates the resource pool in which the sidelink configured grant    |
| type 1 is applied.                                                    |
+-----------------------------------------------------------------------+
| ***sl-StartRBsetCG-Type1***                                           |
|                                                                       |
| Indicates starting RB set index of the initial PSSCH transmission of  |
| the sidelink configured grant Type 1 for interlace RB-based PSSCH     |
| transmission.                                                         |
+-----------------------------------------------------------------------+
| ***sl-StartSubchannelCG-Type1***                                      |
|                                                                       |
| This field indicates the starting sub-channel of sidelink configured  |
| grant type 1. An index giving valid sub-channel index.                |
+-----------------------------------------------------------------------+
| ***sl-TimeOffsetCG-Type1***                                           |
|                                                                       |
| This field indicates the slot offset with respect to logical slot     |
| defined by *sl-TimeReferenceSFN-Type1*, as specified in TS 38.321     |
| \[3\].                                                                |
+-----------------------------------------------------------------------+
| ***sl-TimeReferenceSFN-Type1***                                       |
|                                                                       |
| Indicates SFN used for determination of the offset of a resource in   |
| time domain. If it is present, the UE uses the 1^st^ logical slot of  |
| associated resource pool after the starting time of the closest SFN   |
| with the indicated number preceding the reception of the sidelink     |
| configured grant configuration type 1 as reference logical slot, see  |
| TS 38.321 \[3\], clause 5.8.3. If it is not present, the reference    |
| SFN is 0.                                                             |
+-----------------------------------------------------------------------+
| ***sl-TimeResourceCG-Type1***                                         |
|                                                                       |
| This field indicates the time resource location of sidelink           |
| configured grant type 1. An index giving valid combinations of up to  |
| two slot positions (jointly encoded) as time resource indicator value |
| (TRIV), as defined in TS 38.212 \[17\].                               |
+=======================================================================+

#### -- *SL-ConfiguredGrantConfigDedicated-SL-PRS-RP*

The IE *SL-ConfiguredGrantConfigDedicated-SL-PRS-RP* specifies the
configured grant configuration information for NR sidelink positioning
in a dedicated SL-PRS resource pool.

***SL-ConfiguredGrantConfigDedicated-SL-PRS-RP* information element**

\-- ASN1START

\-- TAG-SL-CONFIGUREDGRANTCONFIGDEDICATEDSL-PRS-RP-START

SL-ConfiguredGrantConfigDedicatedSL-PRS-RP-r18 ::= SEQUENCE {

sl-PRS-ConfigIndexCG-r18 SL-ConfigIndexCG-r16,

sl-PRS-PeriodCG-r18 SL-PeriodCG-r16 OPTIONAL, \-- Need M

sl-PRS-ResourcePoolID-r18 SL-ResourcePoolID-r16 OPTIONAL, \-- Need M

rrc-ConfiguredSidelinkGrantDedicated-SL-PRS-RP-r18 SEQUENCE {

sl-TimeOffsetCG-Type1-r18 INTEGER (0..7999) OPTIONAL, \-- Need R

sl-TimeReferenceSFN-Type1-r18 ENUMERATED {sfn512} OPTIONAL, \-- Need S

sl-TimeResourceCG-Type1-r18 INTEGER (0..496) OPTIONAL, \-- Need M

sl-PRS-ResourceIndicationFirstType1-r18 INTEGER(0..11) OPTIONAL, \--
Need M

sl-PRS-ResourceIndicationFutureType1-r18 INTEGER(0..143) OPTIONAL \--
Need M

}

}

\-- TAG-SL-CONFIGUREDGRANTCONFIGDEDICATEDSL-PRS-RP-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-ConfiguredGrantConfigDedicated-SL-PRS-RP* field descriptions      |
+-----------------------------------------------------------------------+
| ***sl-PRS-ConfigIndexCG***                                            |
|                                                                       |
| This field indicates the ID to identify sidelink configured grant.    |
| The field value should not be duplicated with *sl-ConfigIndexCG* in   |
| IE *SL-ConfiguredGrantConfig.*                                        |
+-----------------------------------------------------------------------+
| ***sl-PRS-PeriodCG***                                                 |
|                                                                       |
| This field indicates the period of SL PRS configured grant in a       |
| dedicated resources in ms for either CG type 1 or CG type 2.          |
+-----------------------------------------------------------------------+
| ***sl-PRS-ResourceIndicationFirstType1***                             |
|                                                                       |
| Indicates SL-PRS Resource ID for the first SL-PRS transmission.       |
+-----------------------------------------------------------------------+
| ***sl-PRS-ResourceIndicationFutureType1***                            |
|                                                                       |
| Indicates SL-PRS resource IDs for future SL PRS transmissions. An     |
| index giving valid combinations of up to two SL PRS resource IDs      |
| (jointly encoded) .                                                   |
+-----------------------------------------------------------------------+
| ***sl-PRS-ResourcePoolID***                                           |
|                                                                       |
| Indicates the resource pool in which the configured sidelink grant    |
| Type 1 is applied. This field value is configured with value up to 8  |
| (*maxNrofSL-PRS-TxPool-r18*). The network always configures this      |
| field when *rrc-ConfiguredSidelinkGrantDedicated-SL-PRS-RP* contains  |
| parameters for a type 1 configured grant.                             |
+-----------------------------------------------------------------------+
| ***sl-TimeOffsetCG-Type1***                                           |
|                                                                       |
| This field indicates the slot offset with respect to logical slot     |
| defined by *sl-TimeReferenceSFN-Type1-Dedicated-SL-PRS-RP*, as        |
| specified in TS 38.321 \[3\].                                         |
+-----------------------------------------------------------------------+
| ***sl-TimeReferenceSFN-Type1***                                       |
|                                                                       |
| Indicates SFN used for determination of the offset of a resource in   |
| time domain. If it is present, the UE uses the 1^st^ logical slot of  |
| associated resource pool after the starting time of the closest SFN   |
| with the indicated number preceding the reception of the sidelink     |
| configured grant configuration type 1 as reference logical slot, see  |
| TS 38.321 \[3\], clause 5.8.3. If it is not present, the reference    |
| SFN is 0.                                                             |
+-----------------------------------------------------------------------+
| ***sl-TimeResourceCG-Type1***                                         |
|                                                                       |
| This field indicates the time resource location of sidelink           |
| configured grant type 1. An index giving valid combinations of up to  |
| two slot positions (jointly encoded) as time resource indicator value |
| (TRIV), as defined in TS 38.212 \[17\].                               |
+=======================================================================+

#### -- *SL-DestinationIdentity*

The IE *SL-DestinationIdentity* is used to identify a destination of a
NR sidelink communication.

*SL-DestinationIdentity* information element

\-- ASN1START

\-- TAG-SL-DESTINATIONIDENTITY-START

SL-DestinationIdentity-r16 ::= BIT STRING (SIZE (24))

\-- TAG-SL-DESTINATIONIDENTITY-STOP

\-- ASN1STOP

#### *-- SL-DRX-Config*

The IE *SL-DRX-Config* is used to configure DRX related parameters for
NR sidelink communication/discovery. The SL DRX timers should be
calculated in the unit of physical slot.

*SL-DRX-Config information element*

\-- ASN1START

\-- TAG-SL-DRX-CONFIG-START

SL-DRX-Config-r17 ::= SEQUENCE {

sl-DRX-ConfigGC-BC-r17 SL-DRX-ConfigGC-BC-r17 OPTIONAL, \-- Cond HO

sl-DRX-ConfigUC-ToReleaseList-r17 SEQUENCE (SIZE
(1..maxNrofSL-Dest-r16)) OF SL-DestinationIndex-r16 OPTIONAL, \-- Need N

sl-DRX-ConfigUC-ToAddModList-r17 SEQUENCE (SIZE (1..maxNrofSL-Dest-r16))
OF SL-DRX-ConfigUC-Info-r17 OPTIONAL, \-- Need N

\...

}

SL-DRX-ConfigUC-Info-r17 ::= SEQUENCE {

sl-DestinationIndex-r17 SL-DestinationIndex-r16 OPTIONAL, \-- Need N

sl-DRX-ConfigUC-r17 SL-DRX-ConfigUC-r17 OPTIONAL, \-- Need N

\...

}

\-- TAG-SL-DRX-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-DRX-Config* field descriptions                                    |
+-----------------------------------------------------------------------+
| ***sl-DRX-ConfigUC-ToReleaseList***                                   |
|                                                                       |
| This field indicates the sidelink DRX configurations for              |
| corresponding unicast destinations to remove.                         |
+-----------------------------------------------------------------------+
| ***sl-DRX-ConfigUC-ToAddModList***                                    |
|                                                                       |
| This field indicates the sidelink DRX configurations for              |
| corresponding unicast destinations to add and/or modify.              |
+=======================================================================+
| ***sl-DRX-ConfigGC-BC***                                              |
|                                                                       |
| This field indicates the sidelink DRX configurations for groupcast    |
| and broadcast communication, as specified in TS 38.321 \[3\].         |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional       Explanation
  Presence          
  ----------------- -----------------------------------------------------
  *HO*              This field is optionally present, need M, in an
                    *RRCReconfiguration* message including
                    *reconfigurationWithSync*; otherwise it is absent,
                    Need M.

  -----------------------------------------------------------------------

#### *-- SL-DRX-ConfigGC-BC*

The IE *SL-DRX-ConfigGC-BC* is used to configure DRX related parameters
for NR sidelink groupcast and broadcast communication, unicast/broadcast
based communication of Direct Link Establishment Request (TS 24.587
\[57\]), and discovery message (TS 24.554 \[72\]).

*SL-DRX-ConfigGC-BC* information element

\-- ASN1START

\-- TAG-SL-DRX-CONFIGGC-BC-START

SL-DRX-ConfigGC-BC-r17 ::= SEQUENCE {

sl-DRX-GC-BC-PerQoS-List-r17 SEQUENCE (SIZE
(1..maxSL-GC-BC-DRX-QoS-r17)) OF SL-DRX-GC-BC-QoS-r17 OPTIONAL, \-- Need
M

sl-DRX-GC-generic-r17 SL-DRX-GC-Generic-r17 OPTIONAL, \-- Need M

sl-DefaultDRX-GC-BC-r17 SL-DRX-GC-BC-QoS-r17 OPTIONAL, \-- Need M

\...

}

SL-DRX-GC-BC-QoS-r17 ::= SEQUENCE {

sl-DRX-GC-BC-MappedQoS-FlowList-r17 SEQUENCE (SIZE
(1..maxNrofSL-QFIs-r16)) OF SL-QoS-Profile-r16 OPTIONAL, \-- Need M

sl-DRX-GC-BC-OnDurationTimer-r17 CHOICE {

subMilliSeconds INTEGER (1..31),

milliSeconds ENUMERATED {

ms1, ms2, ms3, ms4, ms5,ms6, ms8, ms10, ms20, ms30, ms40, ms50, ms60,

ms80, ms100, ms200, ms300, ms400, ms500, ms600, ms800, ms1000, ms1200,

ms1600, spare8, spare7, spare6, spare5, spare4, spare3, spare2, spare1}

},

sl-DRX-GC-InactivityTimer-r17 ENUMERATED {

ms0, ms1, ms2, ms3, ms4, ms5, ms6, ms8, ms10, ms20, ms30, ms40, ms50,
ms60, ms80,

ms100, ms200, ms300, ms500, ms750, ms1280, ms1920, ms2560, spare9,
spare8,

spare7, spare6, spare5, spare4, spare3, spare2, spare1},

sl-DRX-GC-BC-Cycle-r17 ENUMERATED {

ms10, ms20, ms32, ms40, ms60, ms64, ms70, ms80, ms128, ms160, ms256,
ms320, ms512,

ms640, ms1024, ms1280, ms2048, ms2560, ms5120, ms10240, spare12,
spare11, spare10,

spare9, spare8, spare7, spare6, spare5, spare4, spare3, spare2, spare1},

\...

}

SL-DRX-GC-Generic-r17 ::= SEQUENCE {

sl-DRX-GC-HARQ-RTT-Timer1-r17 ENUMERATED {sl0, sl1, sl2, sl4, spare4,
spare3, spare2, spare1} OPTIONAL, \-- Need M

sl-DRX-GC-HARQ-RTT-Timer2-r17 ENUMERATED {sl0, sl1, sl2, sl4, spare4,
spare3, spare2, spare1} OPTIONAL, \-- Need M

sl-DRX-GC-RetransmissionTimer-r17 ENUMERATED {

sl0, sl1, sl2, sl4, sl6, sl8, sl16, sl24, sl33, sl40, sl64, sl80, sl96,
sl112, sl128,

sl160, sl320, spare15, spare14, spare13, spare12, spare11, spare10,
spare9, spare8,

spare7, spare6, spare5, spare4, spare3, spare2, spare1}

}

\-- TAG-SL-DRX-CONFIGGC-BC-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-DRX-ConfigGC-BC* field descriptions                               |
+=======================================================================+
| ***sl-DefaultDRX-GC-BC***                                             |
|                                                                       |
| Indicates the default sidelink DRX configuration for groupcast and    |
| broadcast communications, which is used for QoS profile(s) that       |
| cannot be mapped into DRX configuration(s) configured for dedicated   |
| QoS profile(s). This field can be applied for the broadcast based or  |
| unicast based communication of Direct Link Establishment Request as   |
| described in TS 24.587 \[57\], ProSe Direct Link Establishment        |
| Request message and discovery message as described in TS 24.554       |
| \[72\].                                                               |
+-----------------------------------------------------------------------+
| ***sl-DRX-GC-BC-PerQoS-List***                                        |
|                                                                       |
| List of one or multiple sidelink DRX configurations for groupcast and |
| broadcast communication, which are mapped from QoS profile(s).        |
+-----------------------------------------------------------------------+
| ***sl-DRX-GC-BC-Cycle***                                              |
|                                                                       |
| Value in ms, ms10 corresponds to 10ms, ms20 corresponds to 20 ms,     |
| ms32 corresponds to 32 ms, and so on.                                 |
+-----------------------------------------------------------------------+
| ***sl-DRX-GC-BC-MappedQoS-FlowsList***                                |
|                                                                       |
| List of QoS profiles of the NR sidelink communication, which are      |
| mapped to a sidelink DRX configuration.                               |
+-----------------------------------------------------------------------+
| ***sl-DRX-GC-BC-OnDurationTimer***                                    |
|                                                                       |
| Value in multiples of 1/32 ms (subMilliSeconds) or in ms              |
| (milliSecond). For the latter, value ms1 corresponds to 1 ms, value   |
| ms2 corresponds to 2 ms, and so on.                                   |
+-----------------------------------------------------------------------+
| ***sl-DRX-GC-HARQ-RTT-Timer1, sl-DRX-GC-HARQ-RTT-Timer2***            |
|                                                                       |
| Value in number of slot lengths of the sidelink BWP where the         |
| transport block was received. Value sl0 corresponds to 0 slots, sl1   |
| corresponds to 1 slot, sl2 corresponds to 2 slots, and so on.         |
| *sl-DRX-GC-HARQ-RTT-Timer1* is used for HARQ feedback enabled         |
| sidelink retransmission if SCI does not indicate retransmission       |
| resource(s). *sl-DRX-GC-HARQ-RTT-Timer2* is used for HARQ feedback    |
| disabled sidelink retransmission in resource pool configured with     |
| PSFCH if SCI does not indicate retransmission resource(s).            |
+-----------------------------------------------------------------------+
| ***sl-DRX-GC-Generic***                                               |
|                                                                       |
| Indicates a sidelink DRX configuration for groupcast communication,   |
| which is applicable to any QoS profile or any Destination Layer-2 ID. |
+-----------------------------------------------------------------------+
| ***sl-DRX-GC-InactivityTimer***                                       |
|                                                                       |
| Value in multiple integers of 1 ms, ms0 corresponds to 0, ms1         |
| corresponds to 1 ms, ms2 corresponds to 2 ms, and so on. This field   |
| is only valid for groupcast communication.                            |
+-----------------------------------------------------------------------+
| ***sl-DRX-GC-RetransmissionTimer***                                   |
|                                                                       |
| Value in number of slot lengths of the sidelink BWP where the         |
| transport block was received. Value sl0 corresponds to 0 slots, sl1   |
| corresponds to 1 slot, sl2 corresponds to 2 slots, and so on.         |
+-----------------------------------------------------------------------+

#### *-- SL-DRX-ConfigUC*

The IE *SL-DRX-ConfigUC* is used to configure sidelink DRX related
parameters for unicast communication.

*SL-DRX-ConfigUC* information element

\-- ASN1START

\-- TAG-DRX-CONFIGUC-START

SL-DRX-ConfigUC-r17 ::= SEQUENCE {

sl-drx-onDurationTimer-r17 CHOICE {

subMilliSeconds INTEGER (1..31),

milliSeconds ENUMERATED {

ms1, ms2, ms3, ms4, ms5, ms6, ms8, ms10, ms20, ms30, ms40, ms50, ms60,

ms80, ms100, ms200, ms300, ms400, ms500, ms600, ms800, ms1000, ms1200,

ms1600, spare8, spare7, spare6, spare5, spare4, spare3, spare2, spare1}

},

sl-drx-InactivityTimer-r17 ENUMERATED {

ms0, ms1, ms2, ms3, ms4, ms5, ms6, ms8, ms10, ms20, ms30, ms40, ms50,
ms60, ms80,

ms100, ms200, ms300, ms500, ms750, ms1280, ms1920, ms2560, spare9,
spare8,

spare7, spare6, spare5, spare4, spare3, spare2, spare1},

sl-drx-HARQ-RTT-Timer1-r17 ENUMERATED {sl0, sl1, sl2, sl4, spare4,
spare3, spare2, spare1} OPTIONAL, \-- Need M

sl-drx-HARQ-RTT-Timer2-r17 ENUMERATED {sl0, sl1, sl2, sl4, spare4,
spare3, spare2, spare1} OPTIONAL, \-- Need M

sl-drx-RetransmissionTimer-r17 ENUMERATED {

sl0, sl1, sl2, sl4, sl6, sl8, sl16, sl24, sl33, sl40, sl64, sl80, sl96,
sl112, sl128,

sl160, sl320, spare15, spare14, spare13, spare12, spare11, spare10,
spare9,

spare8, spare7, spare6, spare5, spare4, spare3, spare2, spare1},

sl-drx-CycleStartOffset-r17 CHOICE {

ms10 INTEGER(0..9),

ms20 INTEGER(0..19),

ms32 INTEGER(0..31),

ms40 INTEGER(0..39),

ms60 INTEGER(0..59),

ms64 INTEGER(0..63),

ms70 INTEGER(0..69),

ms80 INTEGER(0..79),

ms128 INTEGER(0..127),

ms160 INTEGER(0..159),

ms256 INTEGER(0..255),

ms320 INTEGER(0..319),

ms512 INTEGER(0..511),

ms640 INTEGER(0..639),

ms1024 INTEGER(0..1023),

ms1280 INTEGER(0..1279),

ms2048 INTEGER(0..2047),

ms2560 INTEGER(0..2559),

ms5120 INTEGER(0..5119),

ms10240 INTEGER(0..10239)

},

sl-drx-SlotOffset INTEGER (0..31)

}

\-- TAG-SL-DRX-CONFIGUC-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-DRX-ConfigUC* field descriptions                                  |
+=======================================================================+
| ***sl-drx-CycleStartOffset***                                         |
|                                                                       |
| *sl-drx-Cycle* in ms and *sl-drx-StartOffset* in multiples of 1 ms.   |
+-----------------------------------------------------------------------+
| ***sl-drx-HARQ-RTT-Timer1, sl-drx-HARQ-RTT-Timer2***                  |
|                                                                       |
| Value in number of slot lengths of the BWP where the transport block  |
| was received. Value sl0 corresponds to 0 slots, sl1 corresponds to 1  |
| slot, sl2 corresponds to 2 slots, and so on. *sl-drx-HARQ-RTT-Timer1* |
| is used for HARQ feedback enabled sidelink retransmission if SCI does |
| not indicate retransmission resource(s). *sl-drx-HARQ-RTT-Timer2* is  |
| used for HARQ feedback disabled sidelink retransmission in resource   |
| pool configured with PSFCH if SCI does not indicate retransmission    |
| resource(s).                                                          |
+-----------------------------------------------------------------------+
| ***sl-drx-InactivityTimer***                                          |
|                                                                       |
| Value in number of slot lengths of the BWP where the transport block  |
| was received, sl0 corresponds to 0, sl1 corresponds to 1 slot, sl2    |
| corresponds to 2 slots, and so on.                                    |
+-----------------------------------------------------------------------+
| ***sl-drx-onDurationTimer***                                          |
|                                                                       |
| Value in multiples of 1/32 ms (subMilliSeconds) or in ms              |
| (milliSecond). For the latter, value ms1 corresponds to 1 ms, value   |
| ms2 corresponds to 2 ms, and so on.                                   |
+-----------------------------------------------------------------------+
| ***sl-drx-RetransmissionTimer***                                      |
|                                                                       |
| Value in number of slot lengths of the BWP where the transport block  |
| was received. Value sl0 corresponds to 0 slots, sl1 corresponds to 1  |
| slot, sl2 corresponds to 2 slots, and so on.                          |
+-----------------------------------------------------------------------+
| ***sl-drx-SlotOffset***                                               |
|                                                                       |
| Value in 1/32 ms. Value 0 corresponds to 0 ms, value 1 corresponds to |
| 1/32 ms, value 2 corresponds to 2/32 ms, and so on.                   |
+-----------------------------------------------------------------------+

#### *-- SL-DRX-ConfigUC-SemiStatic*

The IE *SL-DRX-ConfigUC-SemiStatic* is used to indicate the semi-static
sidelink DRX related parameters for unicast communication.

*SL-DRX-ConfigUC-SemiStatic* information element

\-- ASN1START

\-- TAG-DRX-CONFIGUCSEMISTATIC-START

SL-DRX-ConfigUC-SemiStatic-r17 ::= SEQUENCE {

sl-drx-onDurationTimer-r17 CHOICE {

subMilliSeconds INTEGER (1..31),

milliSeconds ENUMERATED {

ms1, ms2, ms3, ms4, ms5, ms6, ms8, ms10, ms20, ms30, ms40, ms50, ms60,

ms80, ms100, ms200, ms300, ms400, ms500, ms600, ms800, ms1000, ms1200,

ms1600, spare8, spare7, spare6, spare5, spare4, spare3, spare2, spare1}

},

sl-drx-CycleStartOffset-r17 CHOICE {

ms10 INTEGER(0..9),

ms20 INTEGER(0..19),

ms32 INTEGER(0..31),

ms40 INTEGER(0..39),

ms60 INTEGER(0..59),

ms64 INTEGER(0..63),

ms70 INTEGER(0..69),

ms80 INTEGER(0..79),

ms128 INTEGER(0..127),

ms160 INTEGER(0..159),

ms256 INTEGER(0..255),

ms320 INTEGER(0..319),

ms512 INTEGER(0..511),

ms640 INTEGER(0..639),

ms1024 INTEGER(0..1023),

ms1280 INTEGER(0..1279),

ms2048 INTEGER(0..2047),

ms2560 INTEGER(0..2559),

ms5120 INTEGER(0..5119),

ms10240 INTEGER(0..10239)

},

sl-drx-SlotOffset-r17 INTEGER (0..31)

}

\-- TAG-SL-DRX-CONFIGUCSEMISTATIC-STOP

\-- ASN1STOP

#### -- *SL-FreqConfig*

The IE *SL-FreqConfig* specifies the dedicated configuration information
on one particular carrier frequency for NR sidelink
communication/positioning.

*SL-FreqConfig* information element

\-- ASN1START

\-- TAG-SL-FREQCONFIG-START

SL-FreqConfig-r16 ::= SEQUENCE {

sl-Freq-Id-r16 SL-Freq-Id-r16,

sl-SCS-SpecificCarrierList-r16 SEQUENCE (SIZE (1..maxSCSs)) OF
SCS-SpecificCarrier,

sl-AbsoluteFrequencyPointA-r16 ARFCN-ValueNR OPTIONAL, \-- Need M

sl-AbsoluteFrequencySSB-r16 ARFCN-ValueNR OPTIONAL, \-- Need R

frequencyShift7p5khzSL-r16 ENUMERATED {true} OPTIONAL, \-- Cond
V2X-SL-Shared

valueN-r16 INTEGER (-1..1),

sl-BWP-ToReleaseList-r16 SEQUENCE (SIZE (1..maxNrofSL-BWPs-r16)) OF
BWP-Id OPTIONAL, \-- Need N

sl-BWP-ToAddModList-r16 SEQUENCE (SIZE (1..maxNrofSL-BWPs-r16)) OF
SL-BWP-Config-r16 OPTIONAL, \-- Need N

sl-SyncConfigList-r16 SL-SyncConfigList-r16 OPTIONAL, \-- Need M

sl-SyncPriority-r16 ENUMERATED {gnss, gnbEnb} OPTIONAL \-- Need M

}

SL-Freq-Id-r16 ::= INTEGER (1.. maxNrofFreqSL-r16)

SL-FreqConfigExt-v16k0 ::= SEQUENCE {

additionalSpectrumEmission-r16 AdditionalSpectrumEmission OPTIONAL \--
Need M

}

SL-FreqConfigExt-v1800 ::= SEQUENCE {

absenceOfAnyOtherTechnology-r18 ENUMERATED {true} OPTIONAL, \-- Need R

sl-FreqSelectionConfigList-r18 SEQUENCE (SIZE (1..8)) OF
SL-FreqSelectionConfig-r18 OPTIONAL, \-- Need R

sl-SyncTxDisabled-r18 ENUMERATED {true} OPTIONAL, \-- Need R

sl-EnergyDetectionConfig-r18 CHOICE {

sl-MaxEnergyDetectionThreshold-r18 INTEGER (-85..-52),

sl-EnergyDetectionThresholdOffset-r18 INTEGER (-13..20)

} OPTIONAL, \-- Need R

ue-ToUE-COT-SharingED-Threshold-r18 INTEGER (-85..-52) OPTIONAL, \--
Need R

harq-ACK-FeedbackRatioforCW-AdjustmentGC-Option2-r18 INTEGER (10..100)
OPTIONAL, \-- Need R

\...,

\[\[

additionalSpectrumEmission-v1860 AdditionalSpectrumEmission-v1760
OPTIONAL \-- Need M

\]\]

}

\-- TAG-SL-FREQCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-FreqConfig* field descriptions                                    |
+-----------------------------------------------------------------------+
| ***absenceOfAnyOtherTechnology***                                     |
|                                                                       |
| Presence of this field indicates absence on a long term basis (e.g.   |
| by level of regulation) of any other technology sharing the carrier;  |
| absence of this field indicates the potential presence of any other   |
| technology sharing the carrier, as specified in TS 37.213 \[48\]      |
| clauses 4.5. This parameter is not expected to be provided if the     |
| sidelink carrier is overlapped with uplink carrier.                   |
+-----------------------------------------------------------------------+
| ***additionalSpectrumEmission***                                      |
|                                                                       |
| Provides the *additionalSpectrumEmission* values as defined in TS     |
| 38.101-1 \[15\], clause 6.2E.3.1 or 6.2E.3F.1. Only one of            |
| *additionalSpectrumEmission-r16* or                                   |
| *additionalSpectrumEmission-v1860* is configured by network for each  |
| sidelink frequency.                                                   |
+-----------------------------------------------------------------------+
| ***sl-EnergyDetectionConfig***                                        |
|                                                                       |
| Indicates whether to use the *maxEnergyDetectionThreshold* or the     |
| *energyDetectionThresholdOffset* (see TS 37.213 \[48\], clause        |
| 4.5.5).                                                               |
+-----------------------------------------------------------------------+
| ***sl-EnergyDetectionThresholdOffset***                               |
|                                                                       |
| Indicates the offset to the default maximum energy detection          |
| threshold value. Unit in dB. Value -13 corresponds to -13dB, value    |
| -12 corresponds to -12dB, and so on (i.e. in steps of 1dB) as         |
| specified in TS 37.213 \[48\], clause 4.5.5.                          |
+-----------------------------------------------------------------------+
| ***frequencyShift7p5khzSL***                                          |
|                                                                       |
| Enable the NR SL transmission with a 7.5 kHz shift to the LTE raster. |
| If the field is absent, the frequency shift is disabled.              |
+-----------------------------------------------------------------------+
| ***harq-ACK-FeedbackRatioforCW-AdjustmentGC-Option2***                |
|                                                                       |
| Indicates the ratio threshold for contention window adjustment for SL |
| groupcast option 2 as specified in TS 37.213 \[48\], clause 4.5.4.    |
| Unit is percentage.                                                   |
+-----------------------------------------------------------------------+
| ***sl-MaxEnergyDetectionThreshold***                                  |
|                                                                       |
| Indicates the absolute maximum energy detection threshold value. Unit |
| in dBm. Value -85 corresponds to -85 dBm, value -84 corresponds to    |
| -84 dBm, and so on (i.e. in steps of 1dBm) as specified in TS 37.213  |
| \[48\], clause 4.5.5.                                                 |
+-----------------------------------------------------------------------+
| ***sl-AbsoluteFrequencyPointA***                                      |
|                                                                       |
| Absolute frequency of the reference resource block (Common RB 0). Its |
| lowest subcarrier is also known as Point A.                           |
+-----------------------------------------------------------------------+
| ***sl-AbsoluteFrequencySSB***                                         |
|                                                                       |
| Indicates the frequency location of sidelink SSB. The transmission    |
| bandwidth for sidelink SSB is within the bandwidth of this sidelink   |
| BWP.                                                                  |
+-----------------------------------------------------------------------+
| ***sl-BWP-ToAddModList***                                             |
|                                                                       |
| This field indicates the list of sidelink BWP(s) on which the NR      |
| sidelink communication configuration is to be added or reconfigured.  |
| In this release, only one BWP is allowed to be configured for NR      |
| sidelink communication.                                               |
+-----------------------------------------------------------------------+
| ***sl-BWP-ToReleaseList***                                            |
|                                                                       |
| This field indicates the list of sidelink BWP(s) on which the NR      |
| sidelink communication configuration is to be released.               |
+-----------------------------------------------------------------------+
| ***sl-Freq-Id***                                                      |
|                                                                       |
| This field indicates the identity of the dedicated configuration      |
| information on the carrier frequency for NR sidelink communication.   |
+-----------------------------------------------------------------------+
| ***sl-SCS-SpecificCarrierList***                                      |
|                                                                       |
| A set of UE specific channel bandwidth and location configurations    |
| for different subcarrier spacings (numerologies). Defined in relation |
| to Point A. The UE uses the configuration provided in this field only |
| for the purpose of channel bandwidth and location determination. In   |
| this release, only one *SCS-SpecificCarrier* is allowed to be         |
| configured for NR sidelink communication.                             |
+-----------------------------------------------------------------------+
| ***sl-SyncTxDisabled***                                               |
|                                                                       |
| Indicates that the carrier, even though equipped with synchronisation |
| resources, cannot be used as a synchronisation carrier frequency to   |
| transmit S-SSB.                                                       |
+-----------------------------------------------------------------------+
| ***sl-SyncPriority***                                                 |
|                                                                       |
| This field indicates synchronization priority order, as specified in  |
| clause 5.8.6. *sl-SyncPriority* is configured with the same value     |
| across all carrier frequencies configured for UEs performing NR       |
| sidelink communication on multiple carrier frequencies.               |
+-----------------------------------------------------------------------+
| ***ue-ToUE-COT-SharingED-Threshold***                                 |
|                                                                       |
| Indicates the energy detection threshold that a UE uses to initiate a |
| channel occupancy with other UE(s), and the other UE(s) that shares   |
| the initiated channel occupancy shall use this configured parameter   |
| for accessing the channel(s) as specified in TS 37.213 \[48\], clause |
| 4.5.5 for sidelink channel access. Unit in dBm. Value -85 corresponds |
| to -85 dBm, value -84 corresponds to -84 dBm, and so on (i.e. in      |
| steps of 1dBm).                                                       |
+-----------------------------------------------------------------------+
| ***valueN***                                                          |
|                                                                       |
| Indicate the NR SL transmission with a valueN \*5kHz shift to the LTE |
| raster. (see TS 38.101-1 \[15\], clause 5.4E.2).                      |
+=======================================================================+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *V2X-SL-Shared*      This field is mandatory present if the carrier
                       frequency configured for NR sidelink communication
                       is shared by V2X sidelink communication. It is
                       absent, Need R, otherwise.

  -----------------------------------------------------------------------

#### -- *SL-FreqConfigCommon*

The IE *SL-FreqConfigCommon* specifies the cell-specific configuration
information on one particular carrier frequency for NR sidelink
communication/positioning.

*SL-FreqConfigCommon* information element

\-- ASN1START

\-- TAG-SL-FREQCONFIGCOMMON-START

SL-FreqConfigCommon-r16 ::= SEQUENCE {

sl-SCS-SpecificCarrierList-r16 SEQUENCE (SIZE (1..maxSCSs)) OF
SCS-SpecificCarrier,

sl-AbsoluteFrequencyPointA-r16 ARFCN-ValueNR,

sl-AbsoluteFrequencySSB-r16 ARFCN-ValueNR OPTIONAL, \-- Need R

frequencyShift7p5khzSL-r16 ENUMERATED {true} OPTIONAL, \-- Cond
V2X-SL-Shared

valueN-r16 INTEGER (-1..1),

sl-BWP-List-r16 SEQUENCE (SIZE (1..maxNrofSL-BWPs-r16)) OF
SL-BWP-ConfigCommon-r16 OPTIONAL, \-- Need R

sl-SyncPriority-r16 ENUMERATED {gnss, gnbEnb} OPTIONAL, \-- Need R

sl-NbAsSync-r16 BOOLEAN OPTIONAL, \-- Need R

sl-SyncConfigList-r16 SL-SyncConfigList-r16 OPTIONAL, \-- Need R

\...,

\[\[

sl-UnlicensedFreqConfigCommon-r18 SEQUENCE {

absenceOfAnyOtherTechnology-r18 ENUMERATED {true} OPTIONAL, \-- Need R

sl-FreqSelectionConfigList-r18 SEQUENCE (SIZE (1..8)) OF
SL-FreqSelectionConfig-r18 OPTIONAL, \-- Need R

sl-SyncTxDisabled-r18 ENUMERATED {true} OPTIONAL, \-- Need R

sl-EnergyDetectionConfig-r18 CHOICE {

sl-MaxEnergyDetectionThreshold-r18 INTEGER (-85..-52),

sl-EnergyDetectionThresholdOffset-r18 INTEGER (-13..20)

} OPTIONAL, \-- Need R

ue-ToUE-COT-SharingED-Threshold-r18 INTEGER (-85..-52) OPTIONAL, \--
Need R

harq-ACK-FeedbackRatioforCW-AdjustmentGC-Option2-r18 INTEGER (10..100)
OPTIONAL \-- Need R

} OPTIONAL, \-- Cond SIB12

sl-PosBWP-List-r18 SEQUENCE ( SIZE (1..maxNrofSL-BWPs-r16)) OF
SL-PosBWP-ConfigCommon-r18 OPTIONAL \-- Cond SIB23

\]\],

\[\[

additionalSpectrumEmission-v1860 AdditionalSpectrumEmission-v1760
OPTIONAL \-- Need R

\]\]

}

SL-FreqConfigCommonExt-v16k0 ::= SEQUENCE {

additionalSpectrumEmission-r16 AdditionalSpectrumEmission OPTIONAL \--
Need R

}

\-- TAG-SL-FREQCONFIGCOMMON-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-FreqConfigCommon* field descriptions                              |
+-----------------------------------------------------------------------+
| ***absenceOfAnyOtherTechnology***                                     |
|                                                                       |
| Presence of this field indicates absence on a long term basis (e.g.   |
| by level of regulation) of any other technology sharing the carrier;  |
| absence of this field indicates the potential presence of any other   |
| technology sharing the carrier, as specified in TS 37.213 \[48\]      |
| clauses 4.5.5. This parameter is not expected to be provided if the   |
| sidelink carrier is overlapped with uplink carrier.                   |
+-----------------------------------------------------------------------+
| ***additionalSpectrumEmission***                                      |
|                                                                       |
| Provides the *additionalSpectrumEmission* values as defined in TS     |
| 38.101-1 \[15\], clause 6.2E.3.1 or 6.2E.3F.1. Only one of            |
| *additionalSpectrumEmission-r16* or                                   |
| *additionalSpectrumEmission-v1860* is configured by network for each  |
| sidelink frequency.                                                   |
+-----------------------------------------------------------------------+
| ***sl-EnergyDetectionConfig***                                        |
|                                                                       |
| Indicates whether to use the *maxEnergyDetectionThreshold* or the     |
| *energyDetectionThresholdOffset* (see TS 37.213 \[48\], clause        |
| 4.5.5).                                                               |
+-----------------------------------------------------------------------+
| ***sl-EnergyDetectionThresholdOffset***                               |
|                                                                       |
| Indicates the offset to the default maximum energy detection          |
| threshold value. Unit in dB. Value -13 corresponds to -13dB, value    |
| -12 corresponds to -12dB, and so on (i.e. in steps of 1dB) as         |
| specified in TS 37.213 \[48\], clause 4.5.5.                          |
+-----------------------------------------------------------------------+
| ***frequencyShift7p5khzSL***                                          |
|                                                                       |
| Enable the NR SL transmission with a 7.5 kHz shift to the LTE raster. |
| If the field is absent, the frequency shift is disabled.              |
+-----------------------------------------------------------------------+
| ***harq-ACK-FeedbackRatioforCW-AdjustmentGC-Option2***                |
|                                                                       |
| Indicates the ratio threshold for contention window adjustment for SL |
| groupcast option 2 as specified in TS 37.213 \[48\], clause 4.5.4.    |
| Unit is percentage.                                                   |
+-----------------------------------------------------------------------+
| ***sl-MaxEnergyDetectionThreshold***                                  |
|                                                                       |
| Indicates the absolute maximum energy detection threshold value. Unit |
| in dBm. Value -85 corresponds to -85 dBm, value -84 corresponds to    |
| -84 dBm, and so on (i.e. in steps of 1dBm) as specified in TS 37.213  |
| \[48\], clause 4.5.5.                                                 |
+-----------------------------------------------------------------------+
| ***sl-AbsoluteFrequencyPointA***                                      |
|                                                                       |
| Absolute frequency of the reference resource block (Common RB 0). Its |
| lowest subcarrier is also known as Point A.                           |
+-----------------------------------------------------------------------+
| ***sl-AbsoluteFrequencySSB***                                         |
|                                                                       |
| Indicates the frequency location of sidelink SSB. The transmission    |
| bandwidth for sidelink SSB is within the bandwidth of this sidelink   |
| BWP.                                                                  |
+-----------------------------------------------------------------------+
| ***sl-BWP-List***                                                     |
|                                                                       |
| This field indicates the list of sidelink BWP(s) on which the NR      |
| sidelink communication configuration. In this release, only one BWP   |
| is allowed to be configured for NR sidelink communication.            |
+-----------------------------------------------------------------------+
| ***sl-NbAsSync***                                                     |
|                                                                       |
| This field indicates whether the network can be selected as           |
| synchronization reference directly/indirectly only, if                |
| *sl-SyncPriority* is set to gnss. If this field is set to TRUE, the   |
| network is enabled to be selected as synchronization reference        |
| directly/indirectly. The field is only present in                     |
| *SidelinkPreconfigNR*. Otherwise it is absent. All values in          |
| *sl-NbAsSync* are same across all carrier frequencies configured for  |
| UEs performing NR sidelink communication on multiple carrier          |
| frequencies.                                                          |
+-----------------------------------------------------------------------+
| ***sl-PosBWP-List***                                                  |
|                                                                       |
| This field indicates the list of sidelink BWP(s) for NR sidelink      |
| positioning configuration. Only one BWP is allowed to be configured   |
| for NR sidelink positioning.                                          |
+-----------------------------------------------------------------------+
| ***sl-SyncTxDisabled***                                               |
|                                                                       |
| Indicates that the carrier, even though equipped with synchronisation |
| resources, cannot be used as a synchronisation carrier frequency to   |
| transmit S-SSB.                                                       |
+-----------------------------------------------------------------------+
| ***sl-SyncPriority***                                                 |
|                                                                       |
| This field indicates synchronization priority order, as specified in  |
| clause 5.8.6. All values in sl-SyncPriority are same across all       |
| carrier frequencies configured for UEs performing NR sidelink         |
| communication on multiple carrier frequencies.                        |
+-----------------------------------------------------------------------+
| ***sl-SyncConfigList***                                               |
|                                                                       |
| This field indicates the configuration by which the UE is allowed to  |
| receive and transmit synchronisation information for NR sidelink      |
| communication. Network configures *sl-SyncConfig* including           |
| *txParameters* when configuring UEs to transmit synchronisation       |
| information. If this field is configured in                           |
| *SL-PreconfigurationNR-r16*, only one entry is configured in          |
| *sl-SyncConfigList*.                                                  |
+-----------------------------------------------------------------------+
| ***ue-ToUE-COT-SharingED-Threshold***                                 |
|                                                                       |
| Indicates the energy detection threshold that a UE uses to initiate a |
| channel occupancy with to other UE(s), and the other UE(s) that       |
| shares the initiated channel occupancy shall use this configured      |
| parameter for accessing the channel(s) as specified in TS 37.213      |
| \[48\], clause 4.5.5 for sidelink channel access. Unit in dBm. Value  |
| -85 corresponds to -85 dBm, value -84 corresponds to -84 dBm, and so  |
| on (i.e. in steps of 1dBm).                                           |
+-----------------------------------------------------------------------+
| ***valueN***                                                          |
|                                                                       |
| Indicate the NR SL transmission with a valueN \*5kHz shift to the LTE |
| raster (see TS 38.101-1 \[15\], clause 5.4E.2).                       |
+=======================================================================+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *SIB12*              This field is optional present if included within
                       *SIB12*, need R. Otherwise, the field is absent.

  *SIB23*              This field is optional present if included within
                       *SIB23*, need R. Otherwise, the field is absent.

  *V2X-SL-Shared*      This field is mandatory present if the carrier
                       frequency configured for NR sidelink communication
                       is shared by V2X sidelink communication. It is
                       absent, Need R, otherwise.
  -----------------------------------------------------------------------

#### -- *SL-FreqSelectionConfig*

The IE *SL-FreqSelectionConfig* specifies the configuration information
for carrier selection for NR sidelink transmission using UE autonomous
resource selection.

*SL-FreqSelectionConfig* information element

\-- ASN1START

\-- TAG-SL-FREQSELECTIONCONFIG-START

SL-FreqSelectionConfig-r18 ::= SEQUENCE {

sl-priorityList-r18 SEQUENCE (SIZE (1..8)) OF INTEGER (1..8),

sl-threshCBR-FreqReselection-r18 SL-CBR-r16,

sl-threshCBR-FreqKeeping-r18 SL-CBR-r16

}

\-- TAG-SL-FREQSELECTIONCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-FreqSelectionConfig* field descriptions                           |
+-----------------------------------------------------------------------+
| ***sl-priorityList***                                                 |
|                                                                       |
| Indicates the list of sidelink logical channel priority which is      |
| associated with the configurations in *sl-threshCBR-FreqReselection*  |
| and in *sl-threshCBR-FreqKeeping*.                                    |
+-----------------------------------------------------------------------+
| ***sl-threshCBR-FreqReselection***                                    |
|                                                                       |
| Indicates the CBR threshold based on which UE determines whether the  |
| carrier frequency can be (re)selected for the transmission of NR      |
| sidelink. See TS 38.321 \[3\].                                        |
+-----------------------------------------------------------------------+
| ***sl-threshCBR-FreqKeeping***                                        |
|                                                                       |
| Indicates the CBR threshold based on which UE determines whether the  |
| UE can keep using the carrier which was selected for the transmission |
| of NR sidelink. See TS 38.321 \[3\].                                  |
+=======================================================================+

#### *-- SL-IndirectPathAddChange*

The IE *SL-IndirectPathAddChange* specifies the configuration
information of SL indirect path for SL indirect path addition/change in
MP.

*SL-IndirectPathAddChange* information element

\-- ASN1START

\-- TAG-SL-INDIRECTPATHADDCHANGE-START

SL-IndirectPathAddChange-r18 ::= SEQUENCE {

sl-IndirectPathRelayUE-Identity-r18 SL-SourceIdentity-r17,

sl-IndirectPathCellIdentity-r18 CellIdentity,

t421-r18 ENUMERATED {ms50, ms100, ms150, ms200, ms500, ms1000, ms2000,
ms10000} OPTIONAL, \-- Need M

\...

}

\-- TAG-SL-INDIRECTPATHADDCHANGE-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-IndirectPathAddChange* field descriptions                         |
+-----------------------------------------------------------------------+
| ***sl-IndirectPathRelayUEIdentity***                                  |
|                                                                       |
| Indicates the L2 source ID of the L2 U2N Relay UE of SL indirect      |
| path.                                                                 |
+-----------------------------------------------------------------------+
| ***sl-IndirectPathCellIdentity***                                     |
|                                                                       |
| Identifies the serving cell of the indicated L2 U2N Relay UE.         |
+-----------------------------------------------------------------------+
| ***t421***                                                            |
|                                                                       |
| Indicates the timer value of T421 to be used during indirect path     |
| addition or change.                                                   |
+=======================================================================+

#### -- *SL-InterUE-CoordinationConfig*

The IE *SL*-*InterUE-CoordinationConfig* is used to configure the
sidelink inter-UE coordination (between a UE, UE-A, and a peer UE, UE-B)
parameters. The network ensures sidelink inter-UE coordination and
sidelink DRX are not configured at the same time for a UE.

*SL-InterUE-CoordinationConfig* information element

\-- ASN1START

\-- TAG-SL-INTERUE-COORDINATIONCONFIG-START

SL-InterUE-CoordinationConfig-r17 ::= SEQUENCE {

sl-InterUE-CoordinationScheme1-r17 SL-InterUE-CoordinationScheme1-r17
OPTIONAL, \-- Need M

sl-InterUE-CoordinationScheme2-r17 SL-InterUE-CoordinationScheme2-r17
OPTIONAL, \-- Need M

\...

}

SL-InterUE-CoordinationScheme1-r17 ::= SEQUENCE {

sl-IUC-Explicit-r17 ENUMERATED {enabled, disabled} OPTIONAL, \-- Need M

sl-IUC-Condition-r17 ENUMERATED {enabled, disabled} OPTIONAL, \-- Need M

sl-Condition1-A-2-r17 ENUMERATED {disabled} OPTIONAL, \-- Need M

sl-ThresholdRSRP-Condition1-B-1-Option1List-r17 SEQUENCE (SIZE (1..8))
OF SL-ThresholdRSRP-Condition1-B-1-r17 OPTIONAL, \-- Need M

sl-ThresholdRSRP-Condition1-B-1-Option2List-r17 SEQUENCE (SIZE (1..8))
OF SL-ThresholdRSRP-Condition1-B-1-r17 OPTIONAL, \-- Need M

sl-ContainerCoordInfo-r17 ENUMERATED {enabled, disabled} OPTIONAL, \--
Need M

sl-ContainerRequest-r17 ENUMERATED {enabled, disabled} OPTIONAL, \--
Need M

sl-TriggerConditionCoordInfo-r17 INTEGER (0..1) OPTIONAL, \-- Need M

sl-TriggerConditionRequest-r17 INTEGER (0..1) OPTIONAL, \-- Need M

sl-PriorityCoordInfoExplicit-r17 INTEGER (1..8) OPTIONAL, \-- Need M

sl-PriorityCoordInfoCondition-r17 INTEGER (1..8) OPTIONAL, \-- Need M

sl-PriorityRequest-r17 INTEGER (1..8) OPTIONAL, \-- Need M

sl-PriorityPreferredResourceSet-r17 INTEGER (1..8) OPTIONAL, \-- Need M

sl-MaxSlotOffsetTRIV-r17 INTEGER (1..8000) OPTIONAL, \-- Need M

sl-NumSubCH-PreferredResourceSet-r17 INTEGER (1..27) OPTIONAL, \-- Need
M

sl-ReservedPeriodPreferredResourceSet-r17 INTEGER (1..16) OPTIONAL, \--
Need M

sl-DetermineResourceType-r17 ENUMERATED {uea, ueb} OPTIONAL, \-- Need M

\...

}

SL-InterUE-CoordinationScheme2-r17 ::= SEQUENCE {

sl-IUC-Scheme2-r17 ENUMERATED {enabled} OPTIONAL, \-- Need R

sl-RB-SetPSFCH-r17 BIT STRING (SIZE (10..275)) OPTIONAL, \-- Need M

sl-TypeUE-A-r17 ENUMERATED {enabled} OPTIONAL, \-- Need R

sl-PSFCH-Occasion-r17 INTEGER (0..1) OPTIONAL, \-- Need M

sl-SlotLevelResourceExclusion-r17 ENUMERATED {enabled} OPTIONAL, \--
Need R

sl-OptionForCondition2-A-1-r17 INTEGER (0..1) OPTIONAL, \-- Need M

sl-IndicationUE-B-r17 ENUMERATED {enabled, disabled} OPTIONAL, \-- Need
M

\...,

\[\[

sl-DeltaRSRP-Thresh-v1720 INTEGER (-30..30) OPTIONAL \-- Need M

\]\]

}

SL-ThresholdRSRP-Condition1-B-1-r17 ::= SEQUENCE {

sl-Priority-r17 INTEGER (1..8),

sl-ThresholdRSRP-Condition1-B-1-r17 INTEGER (0..66)

}

\-- TAG-SL-INTERUE-COORDINATIONCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-InterUE-CoordinationScheme1* field descriptions                   |
+-----------------------------------------------------------------------+
| ***sl-Condition1-A-2***                                               |
|                                                                       |
| Indicates disabling the use of condition of excluding from preferred  |
| resource set resource(s) in slot(s) where UE-A, when it is intended   |
| receiver of UE-B, does not expect to perform SL reception from UE-B   |
| due to half duplex operation.                                         |
+-----------------------------------------------------------------------+
| ***sl-ContainerCoordInfo***                                           |
|                                                                       |
| Indicates whether a SCI format 2-C can be used as the container of    |
| inter-UE coordination information transmission from UE-A to UE-B in   |
| Scheme 1 in addition to using MAC CE.                                 |
+-----------------------------------------------------------------------+
| ***sl-ContainerRequest***                                             |
|                                                                       |
| Indicates whether a SCI format 2-C can be used as the container of an |
| explicit request for inter-UE coordination information transmission   |
| from UE-B to UE-A in Scheme 1 in addition to using MAC CE.            |
+-----------------------------------------------------------------------+
| ***sl-DetermineResourceType***                                        |
|                                                                       |
| Indicates how to determine the resource set type to be provided by    |
| inter-UE coordination information transmission. Value \"*uea*\" means |
| the resource set type is determined by UE-A\'s implementation. Value  |
| \"*ueb*\" means the resource set type is determined by UE-B\'s        |
| request.                                                              |
+-----------------------------------------------------------------------+
| ***sl-IUC-Condition***                                                |
|                                                                       |
| Indicates whether inter-UE coordination information triggered by a    |
| condition is enabled or not other than explicit request reception.    |
+-----------------------------------------------------------------------+
| ***sl-IUC-Explicit***                                                 |
|                                                                       |
| Indicates whether inter-UE coordination information triggered by an   |
| explicit request is enabled or not.                                   |
+-----------------------------------------------------------------------+
| ***sl-MaxSlotOffsetTRIV***                                            |
|                                                                       |
| Indicates the maximum value of logical slot offset with respect to a  |
| reference slot that is used for representing the first resource       |
| location of each TRIV to indicate the set of resources in Scheme 1 as |
| specified in TS 38.214 \[19\].                                        |
+-----------------------------------------------------------------------+
| ***sl-NumSubCH-PreferredResousrceSet***                               |
|                                                                       |
| Indicates the number of sub-channels used for determining the         |
| preferred resource set in Scheme 1 when the inter-UE coordination     |
| information transmission is triggered by a condition other than       |
| explicit request reception.                                           |
+-----------------------------------------------------------------------+
| ***sl-PriorityCoordInfoCondition***                                   |
|                                                                       |
| Parameter used to determine the priority values for the purpose       |
| defined in TS 38.213 \[13\] and TS 38.214 \[19\] including, the       |
| priority value for sensing and candidate resource (re-)selection for  |
| transmitting the TB carrying the IUC MAC CE and the priority value in |
| the SCI Format 1-A corresponding to the TB carrying the IUC MAC CE,   |
| triggered by a condition other than explicit request reception in     |
| Scheme 1. The priority value of IUC MAC CE used in LCP procedure (see |
| TS 38.321 \[3\]) is fixed as \"1\".                                   |
+-----------------------------------------------------------------------+
| ***sl-PriorityCoordInfoExplicit***                                    |
|                                                                       |
| Parameter used to determine the priority values for the purpose       |
| defined in TS 38.213 \[13\] and TS 38.214 \[19\] including, the       |
| priority value for sensing and candidate resource (re-)selection for  |
| transmitting the TB carrying the IUC MAC CE and the priority value in |
| the SCI Format 1-A corresponding to the TB carrying the IUC MAC CE,   |
| triggered by an explicit request in Scheme 1. The priority value of   |
| IUC MAC CE used in LCP procedure (see TS 38.321 \[3\]) is fixed as    |
| \"1\".                                                                |
+-----------------------------------------------------------------------+
| ***sl-PriorityPreferredResourceSet***                                 |
|                                                                       |
| Indicates the priority value used for determining the preferred       |
| resource set in Scheme 1 when the inter-UE coordination information   |
| transmission is triggered by a condition other than explicit request  |
| reception.                                                            |
+-----------------------------------------------------------------------+
| ***sl-PriorityRequest***                                              |
|                                                                       |
| Parameter used to determine the priority values for the purpose       |
| defined in TS 38.213 \[13\] and TS 38.214 \[19\] including, the       |
| priority value for sensing and candidate resource (re-)selection for  |
| transmitting the TB carrying the IUC request MAC CE and the priority  |
| value in the SCI Format 1-A corresponding to the TB carrying the IUC  |
| request MAC CE, in an explicit request for inter-UE coordination      |
| information in Scheme 1. The priority value of IUC request MAC CE     |
| used in LCP procedure (see TS 38.321 \[3\]) is fixed as \"1\".        |
+-----------------------------------------------------------------------+
| ***sl-ReservedPeriodPreferredResourceSet***                           |
|                                                                       |
| Indicates the resource reservation interval used for determining the  |
| preferred resource set in Scheme 1 when the inter-UE coordination     |
| information transmission is triggered by a condition, by means of an  |
| index to the corresponding entry of                                   |
| *sl-ResourceReservePeriodList-r16*.                                   |
+-----------------------------------------------------------------------+
| ***sl-TriggerConditionCoordInfo***                                    |
|                                                                       |
| Indicates the additional alternative trigger condition of inter-UE    |
| coordination information triggered by a condition rather than request |
| reception for data transmission in Scheme-1 from UE-A to UE-B. This   |
| field is also used to indicate the additional alternative trigger     |
| condition of inter-UE coordination information triggered by a         |
| condition rather than request reception for SL-PRS transmission in a  |
| shared SL PRS resource pool in Scheme-1 from UE-A to UE-B. Value 0    |
| means inter-UE coordination information is triggered by UE-A\'s       |
| implementation. Value 1 means inter-UE coordination information can   |
| be triggered only when UE-A has data to be transmitted together with  |
| the inter-UE coordination information to UE-B.                        |
+-----------------------------------------------------------------------+
| ***sl-TriggerConditionRequest***                                      |
|                                                                       |
| Indicates the trigger condition of an explicit request from UE-B to   |
| UE-A for data transmission. This field is also used to indicate the   |
| trigger condition of an explicit request from UE-B to UE-A for SL-PRS |
| transmission in a shared SL PRS resource pool. Value 0 means the      |
| explicit request is triggered by UE-B\'s implementation. Value 1      |
| means the explicit request can be triggered only when UE-B has data   |
| or SL-PRS to be transmitted to UE-A.                                  |
+-----------------------------------------------------------------------+
| ***sl-ThresholdRSRP-Condition1-B-1-Option1List***                     |
|                                                                       |
| Indicates the RSRP threshold used to determine reserved resource(s)   |
| of other UE(s) whose RSRP measurement is larger than it as the set of |
| resource(s) non-preferred for UE-B\'s transmission for Condition      |
| 1-B-1 of Scheme 1, as specified in TS 38.214 \[19\]. Value 0          |
| corresponds to minus infinity dBm, value 1 corresponds to -128dBm,    |
| value 2 corresponds to -126dBm, value n corresponds to (-128 +        |
| (n-1)\*2) dBm and so on, value 66 corresponds to infinity dBm.        |
+-----------------------------------------------------------------------+
| ***sl-ThresholdRSRP-Condition1-B-1-Option2List***                     |
|                                                                       |
| Indicates the RSRP threshold used to determine reserved resource(s)   |
| of other UE(s) whose RSRP measurement is smaller than it as the set   |
| of resource(s) non-preferred for UE-B\'s transmission for Condition   |
| 1-B-1 of Scheme 1, as specified in TS 38.214 \[19\]. Value 0          |
| corresponds to minus infinity dBm, value 1 corresponds to -128dBm,    |
| value 2 corresponds to -126dBm, value n corresponds to (-128 +        |
| (n-1)\*2) dBm and so on, value 66 corresponds to infinity dBm.        |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-InterUE-CoordinationScheme2* field descriptions                   |
+-----------------------------------------------------------------------+
| ***sl-DeltaRSRP-Thresh***                                             |
|                                                                       |
| Indicates the RSRP threshold delta value corresponding to             |
| *deltaRSRPThresh* specified in clause 16.3.0 of TS 38.213 \[13\] and  |
| used to determine reserved resource(s) of other UE(s). Value in dB.   |
| Only even values (step size 2) allowed.                               |
+-----------------------------------------------------------------------+
| ***sl-IndicationUE-B***                                               |
|                                                                       |
| Indicates whether to enable or disable the usage of 1 LSB of reserved |
| bits of a SCI format 1-A to indicate of whether UE scheduling a       |
| conflict TB can be UE-B or not.                                       |
+-----------------------------------------------------------------------+
| ***sl-IUC-Scheme2***                                                  |
|                                                                       |
| Indicates whether inter-UE coordination Scheme 2 is enabled or not.   |
+-----------------------------------------------------------------------+
| ***sl-OptionForCondition2-A-1***                                      |
|                                                                       |
| Indicates the RSRP threshold used to consider additional criteria for |
| condition 2-A-1. Value 0 corresponds to using the RSRP threshold      |
| according to the priorities included in the SCI, UE uses thresholds   |
| *sl-Thres-RSRP-List*, in its resource pool configuration              |
| *sl-UE-SelectedConfigRP*, corresponding to *ThresPSSCH-RSRP-List*     |
| specified in clause 16.3.0 of TS 38.213 \[13\]. Value 1 corresponds   |
| to using a (pre)configured RSRP threshold delta value                 |
| *sl-DeltaRSRP-Thresh,* corresponding to *deltaRSRPThresh* specified   |
| in clause 16.3.0 of TS 38.213 \[13\].                                 |
+-----------------------------------------------------------------------+
| ***sl-PSFCH-Occasion***                                               |
|                                                                       |
| Indicates the reference slot from which a PSFCH occasion for inter-UE |
| coordination information transmission is derived. Value 0 corresponds |
| to the slot where UE-B\'s SCI is transmitted and value 1 corresponds  |
| to the slot where expected/potential resource conflict occurs on      |
| PSSCH resource indicated by UE-B\'s SCI.                              |
+-----------------------------------------------------------------------+
| ***sl-RB-SetPSFCH***                                                  |
|                                                                       |
| Indicates the set of PRBs that are actually used for inter-UE         |
| coordination information transmission and reception in Scheme 2. The  |
| leftmost bit of the bitmap refers to the lowest RB index in the       |
| resource pool, and so on.                                             |
+-----------------------------------------------------------------------+
| ***sl-SlotLevelResourceExclusion***                                   |
|                                                                       |
| Indicates that physical layer of UE-B reports resources in a slot     |
| including the next reserved resource indicated by the corresponding   |
| UE-B\'s SCI to higher layer.                                          |
+-----------------------------------------------------------------------+
| ***sl-TypeUE-A***                                                     |
|                                                                       |
| Indicates that a non-destination UE of a TB transmitted by UE-B can   |
| be UE-A which sends inter-UE coordination information to UE-B, when   |
| UE-A is a destination UE of another TB conflicting with the TB        |
| transmitted by UE-B.                                                  |
+=======================================================================+

#### -- *SL-LBT-FailureRecoveryConfig*

The IE *SL-LBT-FailureRecoveryConfig-r18* is used to configure the
parameters used for detection and cancellation of Sidelink consistent
LBT failures for operation with shared spectrum channel access, as
specified in TS 38.321 \[3\].

*SL-LBT-FailureRecoveryConfig* information element

\-- ASN1START

\-- TAG-SL-LBT-FAILURERECOVERYCONFIG-START

SL-LBT-FailureRecoveryConfig-r18 ::= SEQUENCE {

sl-LBT-FailureInstanceMaxCount-r18 ENUMERATED {n4, n8, n16, n32, n64,
n128, spare2, spare1} OPTIONAL, \-- Need M

sl-LBT-FailureDetectionTimer-r18 ENUMERATED {ms10, ms20, ms40, ms80,
ms160, ms320, spare2, spare1} OPTIONAL, \-- Need M

sl-LBT-RecoveryTimer-r18 ENUMERATED {ms10, ms20, ms40, ms80, ms160,
ms320, spare2, spare1} OPTIONAL, \-- Need M

\...

}

\-- TAG-SL-LBT-FAILURERECOVERYCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-LBT-FailureRecoveryConfig* field descriptions                     |
+-----------------------------------------------------------------------+
| ***sl-LBT-FailureDetectionTimer***                                    |
|                                                                       |
| Timer for consistent sidelink LBT failure detection (see TS 38.321    |
| \[3\]). Value ms10 corresponds to 10 ms, value ms20 corresponds to 20 |
| ms, and so on.                                                        |
+-----------------------------------------------------------------------+
| ***sl-LBT-FailureInstanceMaxCount***                                  |
|                                                                       |
| This field determines after how many LBT failure indications received |
| from the physical layer the UE triggers sidelink LBT failure recovery |
| (see TS 38.321 \[3\]). Value n4 corresponds to 4, value n8            |
| corresponds to 8, and so on.                                          |
+-----------------------------------------------------------------------+
| ***sl-LBT-RecoveryTimer***                                            |
|                                                                       |
| Timer for consistent sidelink LBT failure cancellation (see TS 38.321 |
| \[3\]). Value ms10 corresponds to 10 ms, value ms20 corresponds to 20 |
| ms, and so on.                                                        |
+=======================================================================+

#### -- *SL-LogicalChannelConfig*

The IE *SL*-*LogicalChannelConfig* is used to configure the sidelink
logical channel parameters.

*SL-LogicalChannelConfig* information element

\-- ASN1START

\-- TAG-SL-LOGICALCHANNELCONFIG-START

SL-LogicalChannelConfig-r16 ::= SEQUENCE {

sl-Priority-r16 INTEGER (1..8),

sl-PrioritisedBitRate-r16 ENUMERATED {kBps0, kBps8, kBps16, kBps32,
kBps64, kBps128, kBps256, kBps512,

kBps1024, kBps2048, kBps4096, kBps8192, kBps16384, kBps32768, kBps65536,
infinity},

sl-BucketSizeDuration-r16 ENUMERATED {ms5, ms10, ms20, ms50, ms100,
ms150, ms300, ms500, ms1000,

spare7, spare6, spare5, spare4, spare3,spare2, spare1},

sl-ConfiguredGrantType1Allowed-r16 ENUMERATED {true} OPTIONAL, \-- Need
R

sl-HARQ-FeedbackEnabled-r16 ENUMERATED {enabled, disabled } OPTIONAL,
\-- Need R

sl-AllowedCG-List-r16 SEQUENCE (SIZE (0.. maxNrofCG-SL-1-r16)) OF
SL-ConfigIndexCG-r16

OPTIONAL, \-- Need R

sl-AllowedSCS-List-r16 SEQUENCE (SIZE (1..maxSCSs)) OF SubcarrierSpacing
OPTIONAL, \-- Need R

sl-MaxPUSCH-Duration-r16 ENUMERATED {ms0p02, ms0p04, ms0p0625, ms0p125,
ms0p25, ms0p5, spare2, spare1}

OPTIONAL, \-- Need R

sl-LogicalChannelGroup-r16 INTEGER (0..maxLCG-ID) OPTIONAL, \-- Need R

sl-SchedulingRequestId-r16 SchedulingRequestId OPTIONAL, \-- Need R

sl-LogicalChannelSR-DelayTimerApplied-r16 BOOLEAN OPTIONAL, \-- Need R

\...,

\[\[

sl-ChannelAccessPriority-r18 INTEGER (1..4) OPTIONAL, \-- Need R

sl-AllowedCarriers-r18 SEQUENCE (SIZE (1..maxNrofFreqSL-r16)) OF INTEGER
(1..maxNrofFreqSL-r16) OPTIONAL \-- Cond CONNECTED

\]\]

}

\-- TAG-SL-LOGICALCHANNELCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-LogicalChannelConfig field* descriptions                          |
+=======================================================================+
| ***sl-AllowedCarriers***                                              |
|                                                                       |
| If present, SL MAC SDUs from this logical channel can only be mapped  |
| to the sidelink carriers indicated in this list. Otherwise, SL MAC    |
| SDUs from this logical channel can be mapped to any configured        |
| sidelink carriers. The value 1 corresponds to the frequency of first  |
| entry in *sl-FreqInfoList* broadcast in *SIB12*, the value 2          |
| corresponds to the frequency of first entry in                        |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12*, the value 3            |
| corresponds to the frequency of second entry in                       |
| *sl-FreqInfoListSizeExt* broadcast in *SIB12* and so on.              |
+-----------------------------------------------------------------------+
| ***sl-AllowedCG-List***                                               |
|                                                                       |
| This restriction applies only when the SL grant is a configured       |
| grant. If present, SL MAC SDUs from this logical channel can only be  |
| mapped to the indicated configured grant configuration. If the size   |
| of the sequence is zero, then SL MAC SDUs from this logical channel   |
| cannot be mapped to any configured grant configurations. If the field |
| is not present, SL MAC SDUs from this logical channel can be mapped   |
| to any configured grant configurations. If the field                  |
| *sl-ConfiguredGrantType1Allowed* is present, only those sidelink      |
| configured grant type 1 configurations indicated in this sequence are |
| allowed for use by this sidelink logical channel; otherwise, this     |
| sequence shall not include any sidelink configured grant type 1       |
| configuration. Corresponds to \"sl-AllowedCG-List\" as specified in   |
| TS 38.321 \[3\].                                                      |
+-----------------------------------------------------------------------+
| ***sl-AllowedSCS-List***                                              |
|                                                                       |
| If present, it indicates the numerology of UL-SCH resources that this |
| sidelink logical channel is mapped to, when checking the SR trigger   |
| condition. Corresponds to \' sl-AllowedSCS-List\' in TS 38.321 \[3\]. |
+-----------------------------------------------------------------------+
| ***sl-BucketSizeDuration***                                           |
|                                                                       |
| Value in ms. *ms5* corresponds to 5 ms, value *ms10* corresponds to   |
| 10 ms, and so on.                                                     |
+-----------------------------------------------------------------------+
| ***sl-ChannelAccessPriority***                                        |
|                                                                       |
| Indicates the Channel Access Priority Class (CAPC), as specified in   |
| TS 38.300 \[2\], to be used on sidelink transmissions for operation   |
| with shared spectrum channel access in FR1. The network configures    |
| this field only for DRBs.                                             |
+-----------------------------------------------------------------------+
| ***sl-ConfiguredGrantType1Allowed***                                  |
|                                                                       |
| If present and set to true, or if the capability                      |
| *lcp-RestrictionSidelink* as specified in TS 38.306 \[26\] is not     |
| indicated, SL MAC SDUs from this sidelink logical channel can be      |
| transmitted on a sidelink configured grant type 1. Otherwise, SL MAC  |
| SDUs from this logical channel cannot be transmitted on a sidelink    |
| configured grant type 1. Corresponds to                               |
| \'sl-configuredGrantType1Allowed\' in TS 38.321 \[3\].                |
+-----------------------------------------------------------------------+
| ***sl-HARQ-FeedbackEnabled***                                         |
|                                                                       |
| Network always includes this field. It indicates the HARQ feedback    |
| enabled/disabled restriction in LCP for this sidelink logical         |
| channel. If set to *enabled*, the sidelink logical channel will be    |
| multiplexed only with a logical channel which enabling the HARQ       |
| feedback. If set to *disabled*, the sidelink logical channel cannot   |
| be multiplexed with a logical channel which enabling the HARQ         |
| feedback. Corresponds to \'sl-HARQ-FeedbackEnabled\' in TS 38.321     |
| \[3\]. If this field of at least one sidelink logical channel for the |
| UE is set to enabled, *sl-PSFCH-Config* should be mandatory present   |
| in configuration *SL-ResourcePool* of at least one of the sidelink    |
| resource pools.                                                       |
+-----------------------------------------------------------------------+
| ***sl-LogicalChannelGroup***                                          |
|                                                                       |
| ID of the sidelink logical channel group, as specified in TS 38.321   |
| \[3\], which the sidelink logical channel belongs to.                 |
+-----------------------------------------------------------------------+
| ***sl-LogicalChannelSR-DelayTimerApplied***                           |
|                                                                       |
| Indicates whether to apply the delay timer for SR transmission for    |
| this sidelink logical channel. Set to false if                        |
| *logicalChannelSR-DelayTimer* is not included in *sl-BSR-Config*.     |
+-----------------------------------------------------------------------+
| ***sl-MaxPUSCH-Duration***                                            |
|                                                                       |
| If present, it indicates the maximum PUSCH duration of UL-SCH         |
| resources that this sidelink logical channel is mapped to, when       |
| checking the SR trigger condition. Corresponds to                     |
| \"sl-MaxPUSCH-Duration\" in TS 38.321 \[3\].                          |
+-----------------------------------------------------------------------+
| ***sl-PrioritisedBitRate***                                           |
|                                                                       |
| Value in kiloBytes/s. Value *kBps0* corresponds to 0 kiloBytes/s,     |
| value *kBps8* corresponds to 8 kiloBytes/s, value *kBps16*            |
| corresponds to 16 kiloBytes/s, and so on.                             |
+-----------------------------------------------------------------------+
| ***sl-Priority***                                                     |
|                                                                       |
| Sidelink logical channel priority, as specified in TS 38.321 \[3\].   |
+-----------------------------------------------------------------------+
| ***sl-SchedulingRequestId***                                          |
|                                                                       |
| If present, it indicates the scheduling request configuration         |
| applicable for this sidelink logical channel, as specified in TS      |
| 38.321 \[3\].                                                         |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *CONNECTED*          This field is optionally present, Need M, in an
                       RRCReconfiguration message, for a SL DRB with
                       additional sidelink RLC bearer being configured.
                       The field is absent otherwise.

  -----------------------------------------------------------------------

#### -- *SL-L2RelayUE-Config*

The IE *SL*-*L2RelayUE-Config* is used to configure L2 U2N relay
operation related configurations used by L2 U2N Relay UE, or L2 U2U
relay operation related configurations used by L2 U2U Relay UE.

*SL-L2RelayUE-Config* information element

\-- ASN1START

\-- TAG-SL-L2RELAYUE-CONFIG-START

SL-L2RelayUE-Config-r17 ::= SEQUENCE {

sl-RemoteUE-ToAddModList-r17 SEQUENCE (SIZE (1..maxNrofRemoteUE-r17)) OF
SL-RemoteUE-ToAddMod-r17 OPTIONAL, \-- Need N

sl-RemoteUE-ToReleaseList-r17 SEQUENCE (SIZE (1..maxNrofRemoteUE-r17))
OF SL-DestinationIdentity-r16 OPTIONAL, \-- Need N

\...,

\[\[

sl-U2U-RemoteUE-ToAddModList-r18 SEQUENCE (SIZE (1..maxNrofSL-Dest-r16))
OF SL-U2U-RemoteUE-Config-r18 OPTIONAL, \-- Need N

sl-U2U-RemoteUE-ToReleaseList-r18 SEQUENCE (SIZE
(1..maxNrofSL-Dest-r16)) OF SL-DestinationIdentity-r16 OPTIONAL \-- Need
N

\]\]

}

SL-RemoteUE-ToAddMod-r17 ::= SEQUENCE {

sl-L2IdentityRemote-r17 SL-DestinationIdentity-r16,

sl-SRAP-ConfigRelay-r17 SL-SRAP-Config-r17 OPTIONAL, \-- Need M

\...

}

SL-U2U-RemoteUE-Config-r18 ::= SEQUENCE {

sl-L2IdentityRemoteUE-r18 SL-DestinationIdentity-r16,

sl-SourceRemoteUE-ToAddModList-r18 SEQUENCE (SIZE
(1..maxNrofSL-Dest-r16)) OF SL-SourceRemoteUE-Config-r18 OPTIONAL, \--
Need N

sl-SourceRemoteUE-ToReleaseList-r18 SEQUENCE (SIZE
(1..maxNrofSL-Dest-r16)) OF SL-SourceIdentity-r17 OPTIONAL, \-- Need N

\...

}

SL-SourceRemoteUE-Config-r18 ::= SEQUENCE {

sl-SourceUE-Identity-r18 SL-SourceIdentity-r17,

sl-SRAP-ConfigU2U-r18 SL-SRAP-ConfigU2U-r18,

\...

}

\-- TAG-SL-L2RELAYUE-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-L2RelayUE-Config* field descriptions                              |
+-----------------------------------------------------------------------+
| ***sl-RemoteUE-ToAddModList***                                        |
|                                                                       |
| List of L2 U2N Remote UEs to be added and modified to the L2 U2N      |
| Relay UE.                                                             |
+-----------------------------------------------------------------------+
| ***sl-RemoteUE-ToReleaseList***                                       |
|                                                                       |
| List of L2 U2N Remote UEs to be released by the L2 U2N Relay UE.      |
+-----------------------------------------------------------------------+
| ***sl-U2U-RemoteUE-ToAddModList***                                    |
|                                                                       |
| List of target L2 U2U Remote UEs for which the related configuration  |
| is to be added and modified to the L2 U2U Relay UE.                   |
+-----------------------------------------------------------------------+
| ***sl-U2U-RemoteUE-ToReleaseList***                                   |
|                                                                       |
| List of target L2 U2U Remote UEs for which the related configuration  |
| is to be released by the L2 U2U Relay UE.                             |
+-----------------------------------------------------------------------+
| ***sl-U2U-SourceRemoteUE-ToAddModList***                              |
|                                                                       |
| List of Source L2 U2U Remote UEs for which the related configuration  |
| is to be added and modified relative to the destination L2 U2U Remote |
| UE identified by the *sl-L2IdentityRemoteUE*.                         |
+-----------------------------------------------------------------------+
| ***sl-U2U-SourceRemoteUE-ToReleaseList***                             |
|                                                                       |
| List of Source L2 U2U Remote UEs for which the related configuration  |
| is to be released relative to the destination L2 U2U Remote UE        |
| identified by the *sl-L2IdentityRemoteUE*.                            |
+=======================================================================+

#### -- *SL-L2RemoteUE-Config*

The IE *SL*-*L2RemoteUE-Config* is used to configure L2 U2N relay
operation related configurations used by L2 U2N Remote UE, or L2 U2U
relay operation related configurations used by L2 U2U Remote UE.

*SL-L2RemoteUE-Config* information element

\-- ASN1START

\-- TAG-SL-L2REMOTEUE-CONFIG-START

SL-L2RemoteUE-Config-r17 ::= SEQUENCE {

sl-SRAP-ConfigRemote-r17 SL-SRAP-Config-r17 OPTIONAL, \--Need M

sl-UEIdentityRemote-r17 RNTI-Value OPTIONAL, \-- Cond FirstRRCReconfig

\...,

\[\[

sl-U2U-RelayUE-ToAddModList-r18 SEQUENCE (SIZE (1..maxNrofSL-Dest-r16))
OF SL-U2U-RelayUE-Config-r18 OPTIONAL, \-- Need N

sl-U2U-RelayUE-ToReleaseList-r18 SEQUENCE (SIZE (1..maxNrofSL-Dest-r16))
OF SL-DestinationIdentity-r16 OPTIONAL \-- Need N

\]\]

}

SL-U2U-RelayUE-Config-r18 ::= SEQUENCE {

sl-L2IdentityRelay-r18 SL-DestinationIdentity-r16,

sl-TargetRemoteUE-ToAddModList-r18 SEQUENCE (SIZE
(1..maxNrofSL-Dest-r16)) OF SL-TargetRemoteUE-Config-r18 OPTIONAL, \--
Need N

sl-TargetRemoteUE-ToReleaseList-r18 SEQUENCE (SIZE
(1..maxNrofSL-Dest-r16)) OF SL-DestinationIdentity-r16 OPTIONAL, \--
Need N

\...

}

SL-TargetRemoteUE-Config-r18 ::= SEQUENCE {

sl-TargetUE-Identity-r18 SL-DestinationIdentity-r16,

sl-SRAP-ConfigU2U-r18 SL-SRAP-ConfigU2U-r18,

\...

}

\-- TAG-SL-L2REMOTEUE-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-L2RemoteUE-Config* field descriptions                             |
+=======================================================================+
| ***sl-SRAP-ConfigRemote***                                            |
|                                                                       |
| Indicates SRAP configuration used for L2 U2N Remote UE.               |
+-----------------------------------------------------------------------+
| ***sl-UEIdentityRemote***                                             |
|                                                                       |
| Indicates the C-RNTI to the L2 U2N Remote UE.                         |
+-----------------------------------------------------------------------+
| ***sl-U2U-RelayUE-ToAddModList***                                     |
|                                                                       |
| List of L2 U2U Relay UEs for which the related configuration is to be |
| added and modified to the L2 U2U Remote UE.                           |
+-----------------------------------------------------------------------+
| ***sl-U2U-RelayUE-ToReleaseList***                                    |
|                                                                       |
| List of L2 U2U Relay UEs for which the related configuration is to be |
| released by the L2 U2U Remote UE.                                     |
+-----------------------------------------------------------------------+
| ***sl-U2U-TargetRemoteUE-ToAddModList***                              |
|                                                                       |
| List of target L2 U2U Remote UEs for which the related configuration  |
| is to be added and modified relative to the L2 U2U Relay UE           |
| identified by the *sl-L2IdentityRelay*.                               |
+-----------------------------------------------------------------------+
| ***sl-U2U-TargetRemoteUE-ToReleaseList***                             |
|                                                                       |
| List of target L2 U2U Remote UEs for which the related configuration  |
| is to be released relative to the L2 U2U Relay UE identified by the   |
| *sl-L2IdentityRelay*.                                                 |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *FirstRRCReconfig*   This field is mandatory present in the first
                       *RRCReconfiguration* for L2 U2N Remote UE when
                       PCell is on indirect path, i.e. MP configuration
                       is not present. Otherwise the field is absent.

  -----------------------------------------------------------------------

#### -- *SL-MeasConfigCommon*

The IE *SL-MeasConfigCommon* is used to set the cell specific SL RSRP
measurement configurations for unicast destinations.

*SL-MeasConfigCommon* information element

\-- ASN1START

\-- TAG-SL-MEASCONFIGCOMMON-START

SL-MeasConfigCommon-r16 ::= SEQUENCE {

sl-MeasObjectListCommon-r16 SL-MeasObjectList-r16 OPTIONAL, \-- Need R

sl-ReportConfigListCommon-r16 SL-ReportConfigList-r16 OPTIONAL, \-- Need
R

sl-MeasIdListCommon-r16 SL-MeasIdList-r16 OPTIONAL, \-- Need R

sl-QuantityConfigCommon-r16 SL-QuantityConfig-r16 OPTIONAL, \-- Need R

\...

}

\-- TAG-SL-MEASCONFIGCOMMON-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-MeasConfigCommon* field descriptions                              |
+-----------------------------------------------------------------------+
| ***sl-MeasIdListCommon***                                             |
|                                                                       |
| List of sidelink measurement identities                               |
+-----------------------------------------------------------------------+
| ***sl-MeasObjectListCommon***                                         |
|                                                                       |
| List of sidelink measurement objects.                                 |
+-----------------------------------------------------------------------+
| ***sl-QuantityConfigCommon***                                         |
|                                                                       |
| Indicates the layer 3 filtering coefficient for sidelink measurement. |
+-----------------------------------------------------------------------+
| ***sl-ReportConfigListCommon***                                       |
|                                                                       |
| List of sidelink measurement reporting configurations.                |
+=======================================================================+

#### -- *SL-MeasConfigInfo*

The IE *SL*-*MeasConfigInfo* is used to set RSRP measurement
configurations for unicast destinations.

*SL-MeasConfigInfo* information element

\-- ASN1START

\-- TAG-SL-MEASCONFIGINFO-START

SL-MeasConfigInfo-r16 ::= SEQUENCE {

sl-DestinationIndex-r16 SL-DestinationIndex-r16,

sl-MeasConfig-r16 SL-MeasConfig-r16,

\...

}

SL-MeasConfig-r16 ::= SEQUENCE {

sl-MeasObjectToRemoveList-r16 SL-MeasObjectToRemoveList-r16 OPTIONAL,
\-- Need N

sl-MeasObjectToAddModList-r16 SL-MeasObjectList-r16 OPTIONAL, \-- Need N

sl-ReportConfigToRemoveList-r16 SL-ReportConfigToRemoveList-r16
OPTIONAL, \-- Need N

sl-ReportConfigToAddModList-r16 SL-ReportConfigList-r16 OPTIONAL, \--
Need N

sl-MeasIdToRemoveList-r16 SL-MeasIdToRemoveList-r16 OPTIONAL, \-- Need N

sl-MeasIdToAddModList-r16 SL-MeasIdList-r16 OPTIONAL, \-- Need N

sl-QuantityConfig-r16 SL-QuantityConfig-r16 OPTIONAL, \-- Need M

\...

}

SL-MeasObjectToRemoveList-r16 ::= SEQUENCE (SIZE
(1..maxNrofSL-ObjectId-r16)) OF SL-MeasObjectId-r16

SL-ReportConfigToRemoveList-r16 ::= SEQUENCE (SIZE
(1..maxNrofSL-ReportConfigId-r16)) OF SL-ReportConfigId-r16

SL-MeasIdToRemoveList-r16 ::= SEQUENCE (SIZE (1..maxNrofSL-MeasId-r16))
OF SL-MeasId-r16

\-- TAG-SL-MEASCONFIGINFO-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-MeasConfigInfo* field descriptions                                |
+-----------------------------------------------------------------------+
| ***sl-MeasIdToAddModList***                                           |
|                                                                       |
| List of sidelink measurement identities to add and/or modify.         |
+-----------------------------------------------------------------------+
| ***sl-MeasIdToRemoveList***                                           |
|                                                                       |
| List of sidelink measurement identities to remove.                    |
+-----------------------------------------------------------------------+
| ***sl-MeasObjectToAddModList***                                       |
|                                                                       |
| List of sidelink measurement objects to add and/or modify.            |
+-----------------------------------------------------------------------+
| ***sl-MeasObjectToRemoveList***                                       |
|                                                                       |
| List of sidelink measurement objects to remove.                       |
+-----------------------------------------------------------------------+
| ***sl-QuantityConfig***                                               |
|                                                                       |
| Indicates the layer 3 filtering coefficient for sidelink measurement. |
+-----------------------------------------------------------------------+
| ***sl-ReportConfigToAddModList***                                     |
|                                                                       |
| List of sidelink measurement reporting configurations to add and/or   |
| modify.                                                               |
+-----------------------------------------------------------------------+
| ***sl-ReportConfigToRemoveList***                                     |
|                                                                       |
| List of sidelink measurement reporting configurations to remove.      |
+=======================================================================+

#### -- *SL-MeasIdList*

The IE *SL*-*MeasIdList* concerns a list of SL measurement identities to
add or modify for a destination, with for each entry the *sl-MeasId*,
the associated *sl-MeasObjectId* and the associated *sl-ReportConfigId*.

*SL-MeasIdList* information element

\-- ASN1START

\-- TAG-SL-MEASIDLIST-START

SL-MeasIdList-r16 ::= SEQUENCE (SIZE (1..maxNrofSL-MeasId-r16)) OF
SL-MeasIdInfo-r16

SL-MeasIdInfo-r16 ::= SEQUENCE {

sl-MeasId-r16 SL-MeasId-r16,

sl-MeasObjectId-r16 SL-MeasObjectId-r16,

sl-ReportConfigId-r16 SL-ReportConfigId-r16,

\...

}

SL-MeasId-r16 ::= INTEGER (1..maxNrofSL-MeasId-r16)

\-- TAG-SL-MEASIDLIST-STOP

\-- ASN1STOP

#### -- *SL-MeasObjectList*

The IE *SL*-*MeasObjectList* concerns a list of SL measurement objects
to add or modify for a destination.

*SL-MeasObjectList* information element

\-- ASN1START

\-- TAG-SL-MEASOBJECTLIST-START

SL-MeasObjectList-r16 ::= SEQUENCE (SIZE (1..maxNrofSL-ObjectId-r16)) OF
SL-MeasObjectInfo-r16

SL-MeasObjectInfo-r16 ::= SEQUENCE {

sl-MeasObjectId-r16 SL-MeasObjectId-r16,

sl-MeasObject-r16 SL-MeasObject-r16,

\...

}

SL-MeasObjectId-r16 ::= INTEGER (1..maxNrofSL-ObjectId-r16)

SL-MeasObject-r16 ::= SEQUENCE {

frequencyInfoSL-r16 ARFCN-ValueNR,

\...

}

\-- TAG-SL-MEASOBJECTLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-MeasObjectList* field descriptions                                |
+-----------------------------------------------------------------------+
| ***frequencyInfoSL***                                                 |
|                                                                       |
| It indicates the lowest usable subcarrier on the carrier where SL     |
| RSRP is measured, determined according to                             |
| *sl-AbsoluteFrequencyPointA* in IE                                    |
| *SL-FreqConfig/SL-FreqConfigCommon* and *offsetToCarrier* in IE       |
| *SCS-SpecificCarrier* configured for *sl-SCS-SpecificCarrierList* in  |
| IE *SL-FreqConfig/SL-FreqConfigCommon*. See TS 38.211 \[16\], clause  |
| 8.2.5.                                                                |
+-----------------------------------------------------------------------+
| ***sl-MeasObjectId***                                                 |
|                                                                       |
| It is used to identify a sidelink measurement object configuration.   |
+-----------------------------------------------------------------------+
| ***sl-MeasObject***                                                   |
|                                                                       |
| It specifies information applicable for sidelink DMRS, SL-PRS         |
| measurement.                                                          |
+=======================================================================+

#### -- *SL-PagingIdentityRemoteUE*

The IE *SL-PagingIdentityRemoteUE* includes the Remote UE\'s paging UE
ID.

*SL-PagingIdentityRemoteUE* information element

\-- ASN1START

\-- TAG-SL-PAGINGIDENTITYREMOTEUE-START

SL-PagingIdentityRemoteUE-r17 ::= SEQUENCE {

ng-5G-S-TMSI-r17 NG-5G-S-TMSI,

fullI-RNTI-r17 I-RNTI-Value OPTIONAL \-- Need R

}

\-- TAG-SL-PAGINGIDENTITYREMOTEUE-STOP

\-- ASN1STOP

#### -- *SL-PBPS-CPS-Config*

The IE *SL-PBPS-CPS-Config* specifies the operation information for a
resource pool which can be (pre-)configured to enable full sensing only,
partial sensing only, random resource selection only, or any
combination(s) thereof.

*SL-PBPS-CPS-Config* information element

\-- ASN1START

\-- TAG-SL-PBPS-CPS-CONFIG-START

SL-PBPS-CPS-Config-r17 ::= SEQUENCE {

sl-AllowedResourceSelectionConfig-r17 ENUMERATED {c1, c2, c3, c4, c5,
c6, c7} OPTIONAL, \-- Need M

sl-MinNumCandidateSlotsPeriodic-r17 INTEGER (1..32) OPTIONAL, \-- Need M

sl-PBPS-OccasionReservePeriodList-r17 SEQUENCE (SIZE (1..16)) OF INTEGER
(1..16) OPTIONAL, \-- Need M

sl-Additional-PBPS-Occasion-r17 ENUMERATED { monitored } OPTIONAL, \--
Need M

sl-CPS-WindowPeriodic-r17 INTEGER (5..30) OPTIONAL, \-- Need M

sl-MinNumCandidateSlotsAperiodic-r17 INTEGER (1..32) OPTIONAL, \-- Need
M

sl-MinNumRssiMeasurementSlots-r17 INTEGER (1..800) OPTIONAL, \-- Need M

sl-DefaultCBR-RandomSelection-r17 INTEGER (0..100) OPTIONAL, \-- Need M

sl-DefaultCBR-PartialSensing-r17 INTEGER (0..100) OPTIONAL, \-- Need M

sl-CPS-WindowAperiodic-r17 INTEGER (0..30) OPTIONAL, \-- Need M

sl-PartialSensingInactiveTime-r17 ENUMERATED { enabled, disabled }
OPTIONAL, \-- Need M

\...

}

\-- TAG-SL-PBPS-CPS-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-PBPS-CPS-Config* field descriptions                               |
+-----------------------------------------------------------------------+
| ***sl-Additional-PBPS-Occasion***                                     |
|                                                                       |
| Indicates that UE additionally monitors periodic sensing occasions    |
| that correspond to a set of values. (see TS 38.214 \[19\], clause     |
| 8.1.4).                                                               |
+-----------------------------------------------------------------------+
| ***sl-AllowedResourceSelectionConfig***                               |
|                                                                       |
| Indicates the allowed resource selection mechanism(s), i.e. full      |
| sensing only, partial sensing only, random resource selection only,   |
| or any combination(s) thereof. (see TS 38.214 \[19\], clause 8.1.4).  |
| Only *c1*, *c4*, *c5* or *c7* can be configured for a Rel-16 resource |
| pool. Only *c1* can be configured for a resource pool included in     |
| *sl-TxPoolSelectedNormal*, for which                                  |
| *sl-NRPSFCH-EUTRA-ThresRSRP-List*/*sl-NRPSSCH-EUTRA-ThresRSRP-List*   |
| is configured. If this field is not configured for a resource pool    |
| included in *sl-TxPoolSelectedNormal*, only full sensing is allowed   |
| in the corresponding resource pool.                                   |
|                                                                       |
| *c1*: only full sensing allowed                                       |
|                                                                       |
| *c2*: only partial sensing allowed                                    |
|                                                                       |
| *c3*: only random selection allowed                                   |
|                                                                       |
| *c4*: full sensing+random selection allowed                           |
|                                                                       |
| *c5*: full sensing+ partial sensing allowed                           |
|                                                                       |
| *c6*: partial sensing + random selection allowed                      |
|                                                                       |
| *c7*: full sensing+ partial sensing + random selection allowed.       |
+-----------------------------------------------------------------------+
| ***sl-CPS-WindowAperiodic***                                          |
|                                                                       |
| Parameter that indicates the minimum size of contiguous partial       |
| sensing window in logical slot units for a resource (re)selection     |
| procedure and re-evaluation/pre-emption checking triggered by         |
| aperiodic transmission. (see TS 38.214 \[19\], clause 8.1.4). If not  |
| configured, the size of contiguous partial sensing window in logical  |
| slot units is 31.                                                     |
+-----------------------------------------------------------------------+
| ***sl-CPS-WindowPeriodic***                                           |
|                                                                       |
| Indicates the size of contiguous partial sensing window in logical    |
| slot units when UE performs periodic-based and contiguous partial     |
| sensing for a resource (re)selection procedure triggered by periodic  |
| transmission. If not configured, the size of contiguous partial       |
| sensing window in logical slot units is 31.                           |
+-----------------------------------------------------------------------+
| ***sl-DefaultCBR-PartialSensing***                                    |
|                                                                       |
| Indicates default value of SL CBR measurement for a UE that is        |
| configured to perform partial sensing by its higher layer (including  |
| when SL DRX is configured) if the number of SL RSSI measurement slots |
| over CBR measurement window is below *sl-MinNumRssiMeasurementSlots*, |
| (see TS 38.214 \[19\], clause 8.1.6). Value 0 corresponds to 0, value |
| 1 to 0.01, value 2 to 0.02, and so on.                                |
+-----------------------------------------------------------------------+
| ***sl-DefaultCBR-RandomSelection***                                   |
|                                                                       |
| Indicates default value of CBR measurement for a UE that performs     |
| random resource selection if no SL CBR measurement result over SL CBR |
| measurement window, (see TS 38.214 \[19\], clause 8.1.6). Value 0     |
| corresponds to 0, value 1 to 0.01, value 2 to 0.02, and so on.        |
+-----------------------------------------------------------------------+
| ***sl-MinNumCandidateSlotsAperiodic***                                |
|                                                                       |
| Indicates the minimum number of Y\' slots that are included in the    |
| possible candidate resources corresponding to periodic-based partial  |
| sensing and/or contiguous partial sensing for resource (re)selection  |
| triggered by aperiodic transmission. (see TS 38.214 \[19\], clause    |
| 8.1.4).                                                               |
+-----------------------------------------------------------------------+
| ***sl-MinNumCandidateSlotsPeriodic***                                 |
|                                                                       |
| Indicates the minimum number of Y slots that are included in the      |
| possible candidate resources corresponding to periodic-based partial  |
| sensing for resource (re)selection triggered by periodic              |
| transmission. (see TS 38.214 \[19\], clause 8.1.4).                   |
+-----------------------------------------------------------------------+
| ***sl-MinNumRssiMeasurementSlots***                                   |
|                                                                       |
| Indicates a threshold for a minimum number of SL RSSI measurement     |
| slots over CBR measurement window for which the SL RSSI is measured   |
| for a UE that is configured to perform partial sensing by its higher  |
| layer (including when SL DRX is configured). (see TS 38.214 \[19\],   |
| clause 8.1.6).                                                        |
+-----------------------------------------------------------------------+
| ***sl-PartialSensingInactiveTime***                                   |
|                                                                       |
| Indicates whether or not UE is required to perform SL reception of    |
| PSCCH and RSRP measurement for partial sensing on slots in SL DRX     |
| inactive time when partial sensing is configured by its higher layer. |
| (see TS 38.214 \[19\], clause 8.1.4).                                 |
+-----------------------------------------------------------------------+
| ***sl-PBPS-OccasionReservePeriodList***                               |
|                                                                       |
| Indicates the subset of periodicity values from                       |
| *sl-ResourceReservePeriodList* used to determine periodic sensing     |
| occasions in periodic-based partial sensing, by means of an index to  |
| the corresponding entry in *sl-ResourceReservePeriodList-r16*. If not |
| configured, all periodicity values from                               |
| *sl-ResourceReservePeriodList* are used to determine periodic sensing |
| occasions in periodic-based partial sensing (see TS 38.214 \[19\],    |
| clause 8.1.4).                                                        |
+=======================================================================+

#### -- *SL-PDCP-Config*

The IE *SL*-*PDCP-Config* is used to set the configurable PDCP
parameters for a sidelink radio bearer.

*SL-PDCP-Config* information element

\-- ASN1START

\-- TAG-SL-PDCP-CONFIG-START

SL-PDCP-Config-r16 ::= SEQUENCE {

sl-DiscardTimer-r16 ENUMERATED {ms3, ms10, ms20, ms25, ms30, ms40, ms50,
ms60, ms75, ms100, ms150, ms200,

ms250, ms300, ms500, ms750, ms1500, infinity} OPTIONAL, \-- Cond Setup

sl-PDCP-SN-Size-r16 ENUMERATED {len12bits, len18bits} OPTIONAL, \-- Cond
Setup2

sl-OutOfOrderDelivery ENUMERATED { true } OPTIONAL, \-- Need R

\...

}

\-- TAG-SL-PDCP-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-PDCP-Config* field descriptions                                   |
+-----------------------------------------------------------------------+
| ***sl-DiscardTimer***                                                 |
|                                                                       |
| Value in ms of *discardTimer* specified in TS 38.323 \[5\]. Value     |
| *ms50* corresponds to 50 ms, value *ms100* corresponds to 100 ms and  |
| so on.                                                                |
+-----------------------------------------------------------------------+
| ***sl-OutOfOrderDelivery***                                           |
|                                                                       |
| Indicates whether or not outOfOrderDelivery specified in TS 38.323    |
| \[5\] is configured. This field should be either always present or    |
| always absent, after the radio bearer is established.                 |
+-----------------------------------------------------------------------+
| ***sl-PDCP-SN-Size***                                                 |
|                                                                       |
| PDCP sequence number size for unicast NR sidelink communication, 12   |
| or 18 bits, as specified in TS 38.323 \[5\]. For groupcast and        |
| broadcast NR sidelink communication, only 12 bits is applicable, as   |
| specified in 9.1.1.5.                                                 |
+=======================================================================+

  -----------------------------------------------------------------------
  Conditional         Explanation
  Presence            
  ------------------- ---------------------------------------------------
  *Setup*             The field is mandatory present in case of sidelink
                      DRB setup via dedicated signaling and in case of
                      sidelink DRB configuration via system information
                      and pre-configuration; otherwise the field is
                      optionally present, need M.

  *Setup2*            The field is mandatory present in case of sidelink
                      DRB setup via dedicated signaling and in case of
                      sidelink DRB configuration via system information
                      and pre-configuration for RLC-AM and RLC-UM for
                      unicast NR sidelink communication; otherwise the
                      field is not present, Need M.
  -----------------------------------------------------------------------

#### - *SL-PosBWP-ConfigCommon*

The IE *SL-PosBWP-ConfigCommon* is used to configure the cell-specific
configuration for sidelink positioning on one particular sidelink
bandwidth part.

*SL-PosBWP-ConfigCommon* information element

\-- ASN1START

\-- TAG-SL-POSBWP-CONFIGCOMMON-START

SL-PosBWP-ConfigCommon-r18 ::= SEQUENCE {

sl-BWP-Generic-r18 SL-BWP-Generic-r16 OPTIONAL, \-- Need R

sl-BWP-PRS-PoolConfigCommon-r18 SL-BWP-PRS-PoolConfigCommon-r18
OPTIONAL, \-- Need R

\...

}

\-- TAG-SL-POSBWP-CONFIGCOMMON-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-PosBWP-ConfigCommon* field descriptions                           |
+=======================================================================+
| ***sl-BWP-Generic***                                                  |
|                                                                       |
| This field indicates the generic parameters on the configured         |
| sidelink BWP.                                                         |
+-----------------------------------------------------------------------+
| ***sl-BWP-PRS-PoolConfigCommon***                                     |
|                                                                       |
| This field indicates the dedicated SL-PRS resource pool               |
| configurations for SL-PRS on the configured sidelink BWP. Dedicated   |
| SL-PRS resource pool is not expected to be configured in the slots    |
| colliding with the slots (pre)configured for any other resource       |
| pool(s) or S-SSB resource(s) in other SL carriers.                    |
+-----------------------------------------------------------------------+

#### -- *SL-PRS-ResourcePool*

The IE *SL-PRS-ResourcePool* specifies the configuration information for
NR sidelink PRS dedicated resource pool.

*SL-PRS-ResourcePool* information element

\-- ASN1START

\-- TAG-SL-PRS-RESOURCEPOOL-START

SL-PRS-ResourcePool-r18 ::= SEQUENCE {

sl-PRS-PSCCH-Config-r18 SetupRelease {
SL-PSCCH-ConfigDedicatedSL-PRS-RP-r18} OPTIONAL, \-- Need M

sl-StartRB-SubchannelDedicatedSL-PRS-RP-r18 INTEGER (0..265) OPTIONAL,
\-- Need M

sl-FilterCoefficient-r18 FilterCoefficient OPTIONAL, \-- Need M

sl-ThreshS-RSSI-PRS-CBR-r18 INTEGER (0..45) OPTIONAL, \-- Need M

sl-RB-Number-r18 INTEGER (10..275) OPTIONAL, \-- Need M

sl-TimeResource-r18 BIT STRING (SIZE (10..160)) OPTIONAL, \-- Need M

sl-PosAllowedResourceSelectionConfig-r18 ENUMERATED {c1, c2, c3}
OPTIONAL, \-- Need M

sl-PRS-ResourceReservePeriodList-r18 SEQUENCE (SIZE (1..16)) OF
SL-ReservationPeriodAllowedDedicatedSL-PRS-RP-r18

OPTIONAL,

sl-PRS-ResourcesDedicatedSL-PRS-RP-r18 SEQUENCE (SIZE (1..12)) OF
SL-PRS-ResourceDedicatedSL-PRS-RP-r18 OPTIONAL, \-- Need M

sl-PRS-PowerControl-r18 SL-PRS-PowerControl-r18 OPTIONAL, \-- Need M

sl-SensingWindowDedicatedSL-PRS-RP-r18 ENUMERATED {ms100, ms1100}
OPTIONAL, \-- Need M

sl-TxPercentageDedicatedSL-PRS-RP-List-r18 SEQUENCE (SIZE (8)) OF
SL-TxPercentageDedicatedSL-PRS-RP-Config-r18 OPTIONAL, \-- Need M

sl-SCI-basedSL-PRS-TxTriggerSCI1-B-r18 BOOLEAN OPTIONAL, \-- Need M

sl-NumSubchannelDedicatedSL-PRS-RP-r18 INTEGER (1..27) OPTIONAL, \--
Need M

sl-SubchannelSizeDedicatedSL-PRS-RP-r18 ENUMERATED {n10, n12, n15, n20,
n25, n50, n75, n100} OPTIONAL, \-- Need M

sl-MaxNumPerReserveDedicatedSL-PRS-RP-r18 ENUMERATED {n2, n3} OPTIONAL,
\-- Need M

sl-NumReservedBitsSCI1B-DedicatedSL-PRS-RP-r18 INTEGER (0..20) OPTIONAL,
\-- Need R

sl-SRC-ID-LenDedicatedSL-PRS-RP-r18 ENUMERATED {n12, n24} OPTIONAL, \--
Need M

sl-CBR-PriorityTxConfigDedicatedSL-PRS-RP-List-r18 SEQUENCE (SIZE
(1..8)) OF SL-PriorityTxConfigIndexDedicatedSL-PRS-RP-r18

OPTIONAL, \-- Need M

sl-TimeWindowSizeCBR-DedicatedSL-PRS-RP-r18 ENUMERATED {ms100, slot100}
OPTIONAL, \-- Need M

sl-TimeWindowSizeCR-DedicatedSL-PRS-RP-r18 ENUMERATED {ms1000, slot1000}
OPTIONAL, \-- Need M

sl-CBR-CommonTxDedicatedSL-PRS-RP-List-r18
SL-CBR-CommonTxDedicatedSL-PRS-RP-List-r18 OPTIONAL, \-- Need M

sl-PriorityThreshold-UL-URLLC-r18 INTEGER (1..9) OPTIONAL, \-- Need M

sl-PriorityThreshold-r18 INTEGER (1..9) OPTIONAL, \-- Need M

sl-SelectionWindowListDedicatedSL-PRS-RP-r18 SEQUENCE (SIZE (8)) OF
SL-SelectionWindowConfigDedicated-SL-PRS-RP-r18

OPTIONAL, \-- Need M

sl-Thres-RSRP-ListDedicatedSL-PRS-RP-r18 SEQUENCE (SIZE (64)) OF
SL-PRS-ThresRSRP-r18 OPTIONAL, \-- Need M

sl-PreemptionEnableDedicatedSL-PRS-RP-r18 ENUMERATED {enabled, pl1, pl2,
pl3, pl4, pl5, pl6, pl7, pl8} OPTIONAL \-- Need R

}

SL-PSCCH-ConfigDedicatedSL-PRS-RP-r18 ::= SEQUENCE {

sl-TimeResourcePSCCH-DedicatedSL-PRS-RP-r18 ENUMERATED {n2, n3}
OPTIONAL, \-- Need M

sl-FreqResourcePSCCH-DedicatedSL-PRS-RP-r18 ENUMERATED {n10,n12, n15,
n20, n25} OPTIONAL, \-- Need M

\...,

\[\[

sl-DMRS-ScrambleID-DedicatedSL-PRS-RP-r18 INTEGER (0..65535) OPTIONAL
\-- Need M

\]\]

}

SL-ReservationPeriodAllowedDedicatedSL-PRS-RP-r18 ::= CHOICE {

sl-ResourceReservePeriod1-r18 ENUMERATED {ms0, ms100, ms160, ms200,
ms300, ms320, ms400, ms500, ms600, ms640,

ms700, ms800, ms900, ms1000, ms1280, ms2560, ms5120, ms10240},

sl-ResourceReservePeriod2-r18 INTEGER (1..99)

}

SL-PRS-ResourceDedicatedSL-PRS-RP-r18::= SEQUENCE {

sl-PRS-ResourceID-r18 INTEGER (0..11) OPTIONAL, \-- Need M

sl-NumberOfSymbols-r18 INTEGER (1..9) OPTIONAL, \-- Need M

sl-CombSize-r18 ENUMERATED{n2,n4,n6} OPTIONAL, \-- Need R

sl-PRS-starting-symbol-r18 INTEGER (4..12) OPTIONAL, \-- Need M

sl-PRS-comb-offset-r18 INTEGER(1..5) OPTIONAL \-- Need M

}

SL-PRS-PowerControl-r18::= SEQUENCE {

dl-P0-SL-PRS-r18 INTEGER(-202..24) OPTIONAL, \-- Need M

dl-Alpha-SL-PRS-r18 ENUMERATED {alpha0, alpha04, alpha05, alpha06,
alpha07, alpha08, alpha09, alpha1} OPTIONAL, \-- Need M

sl-P0-SL-PRS-r18 INTEGER(-202..24) OPTIONAL, \-- Need M

sl-Alpha-SL-PRS-r18 ENUMERATED {alpha0, alpha04, alpha05, alpha06,
alpha07, alpha08, alpha09, alpha1} OPTIONAL \-- Need S

}

SL-TxPercentageDedicatedSL-PRS-RP-Config-r18::= SEQUENCE {

sl-TxPercentageDedicatedSL-PRS-RP-r18 INTEGER (1..8) OPTIONAL, \-- Need
M

sl-Priority-DedicatedSL-PRS-RP ENUMERATED {p20, p35, p50} OPTIONAL \--
Need M

}

SL-PriorityTxConfigIndexDedicatedSL-PRS-RP-r18 ::= SEQUENCE {

sl-PriorityThresholdDedicatedSL-PRS-RP-r18 INTEGER (1..8) OPTIONAL, \--
Need M

sl-DefaultTxConfigIndexDedicatedSL-PRS-RP-r18 INTEGER
(0..maxCBR-LevelDedSL-PRS-1-r18) OPTIONAL, \-- Need M

sl-CBR-ConfigIndexDedicatedSL-PRS-RP-r18 INTEGER
(0..maxCBR-ConfigDedSL-PRS-1-r18) OPTIONAL, \-- Need M

sl-PRS-TxConfigIndexList-r18 SEQUENCE (SIZE (1..
maxCBR-LevelDedSL-PRS-1-r18)) OF SL-PRS-TxConfigIndex-r18

OPTIONAL \-- Need M

}

SL-PRS-TxConfigIndex-r18 ::= INTEGER (0.. maxNrofSL-PRS-TxConfig-r18)

SL-SelectionWindowConfigDedicated-SL-PRS-RP-r18::= SEQUENCE {

sl-PRS-Priority-r18 INTEGER (1..8),

sl-PRS-SelectionWindow-r18 ENUMERATED {n1, n5, n10, n20}

}

SL-PRS-ThresRSRP-r18 ::= INTEGER (0..66)

\-- TAG-SL-PRS-RESOURCEPOOL-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-PRS-ResourcePool* field descriptions                              |
+=======================================================================+
| ***sl-CBR-ConfigIndexDedicatedSL-PRS-RP***                            |
|                                                                       |
| Indicates the CBR ranges to be used by an index to the entry of the   |
| CBR range configuration in *sl-CBR-RangeDedicatedSL-PRS-RP-List*.     |
+-----------------------------------------------------------------------+
| ***sl-CBR-PriorityTxConfigDedicatedSL-PRS-RP-List***                  |
|                                                                       |
| Indicates the mapping between SL-PRS transmission parameter (such as  |
| transmission power, etc.) sets by using the indexes of the            |
| configurations                                                        |
|                                                                       |
| in *sl-CBR-SL-PRS-TxConfigList*, CBR ranges by using the indexes to   |
| the entry of the CBR range configurations in                          |
| *sl-CBR-SL-PRS-RangeDedicatedSL-PRS-RP-List*, and priority ranges. It |
| also indicates the default SL-PRS transmission parameters to be used  |
| when CBR measurement results are not available.                       |
+-----------------------------------------------------------------------+
| ***sl-DefaultTxConfigIndexDedicatedSL-PRS-RP***                       |
|                                                                       |
| Indicates the SL PRS transmission parameters to be used by the UEs    |
| which do not have available CBR measurement results, by means of an   |
| index to the corresponding entry in *sl-PRS-TxConfigIndexList*. Value |
| 0 indicates the first entry in *sl-PRS-TxConfigIndexList*. The field  |
| is ignored if the UE has available CBR measurement results.           |
+-----------------------------------------------------------------------+
| ***sl-FilterCoefficient***                                            |
|                                                                       |
| This field indicates the filtering coefficient for long-term          |
| measurement and reference signal power derivation used for sidelink   |
| open-loop power control.                                              |
+-----------------------------------------------------------------------+
| ***sl-MaxNumPerReserveDedicatedSL-PRS-RP***                           |
|                                                                       |
| Indicates the maximum number of SL PRS reservations that can be       |
| indicated by an SCI.                                                  |
+-----------------------------------------------------------------------+
| ***sl-NumReservedBitsSCI1B-DedicatedSL-PRS-RP***                      |
|                                                                       |
| Indicates the number of reserved bits in SCI format 1-B.              |
+-----------------------------------------------------------------------+
| ***sl-NumSubchannelDedicatedSL-PRS-RP***                              |
|                                                                       |
| Indicates the number of subchannels in the corresponding resource     |
| pool, which consists of contiguous PRBs only.                         |
+-----------------------------------------------------------------------+
| ***sl-PosAllowedResourceSelectionConfig***                            |
|                                                                       |
| Indicates allowed resource allocation method configured per resource  |
| pool.                                                                 |
|                                                                       |
| c1: only sensing allowed                                              |
|                                                                       |
| c2: only random resource selection allowed                            |
|                                                                       |
| c3: sensing and random resource selection allowed                     |
+-----------------------------------------------------------------------+
| ***sl-PreemptionEnableDedicatedSL-PRS-RP***                           |
|                                                                       |
| Indicates whether pre-emption is disabled or enabled in a resource    |
| pool. If the field is present and the value is *pl1*, *pl2*, and so   |
| on (but not *enabled*), it means that pre-emption is enabled and a    |
| priority level p_preemption is configured. If the field is present    |
| and the value is *enabled*, the pre-emption is enabled (but           |
| p_preemption is not configured) and pre-emption is applicable to all  |
| levels.                                                               |
+-----------------------------------------------------------------------+
| ***sl-PriorityThreshold***                                            |
|                                                                       |
| Indicates the threshold used to determine whether NR sidelink         |
| transmission in dedicated SL PRS resource pool is prioritized over    |
| uplink transmission of priority index 0 as specified in TS            |
| 38.213\[13\], clause 16.2.4.3, or whether PUCCH transmission carrying |
| SL HARQ is prioritized over PUCCH transmission carrying UCI of        |
| priority index 0 if they overlap in time as specified in TS 38.213    |
| \[13\], clause 9.2.5.0.                                               |
+-----------------------------------------------------------------------+
| ***sl-PriorityThresholdDedicatedSL-PRS-RP***                          |
|                                                                       |
| Indicates the upper bound of priority range which is associated with  |
| the configurations in *sl-CBR-ConfigIndexDedicatedSL-PRS-RP* and in   |
| *sl-PRS-TxConfigIndexList*. The upper bounds of the priority ranges   |
| are configured in ascending order for consecutive entries of          |
| *SL-PriorityTxConfigIndexDedicatedSL-PRS-RP* in                       |
| *sl-CBR-PriorityTxConfigDedicatedSL-PRS-RP-List*. For the first entry |
| of *sl-PriorityThreshold-DedicatedSL-PRS-RP*, the lower bound of the  |
| priority range is 1.                                                  |
+-----------------------------------------------------------------------+
| ***sl-PriorityThreshold-UL-URLLC***                                   |
|                                                                       |
| Indicates the threshold used to determine whether NR sidelink         |
| transmission in dedicated SL PRS resource pool is prioritized over    |
| uplink transmission of priority index 1 as specified in TS            |
| 38.213\[13\], clause 16.2.4.3, or whether PUCCH transmission carrying |
| SL HARQ is prioritized over PUCCH transmission carrying UCI of        |
| priority index 1 if they overlap in time as specified in TS 38.213    |
| \[13\], clause 9.2.5.0.                                               |
+-----------------------------------------------------------------------+
| ***sl-PRS-ResourceReservePeriodList***                                |
|                                                                       |
| Indicates set of possible resource reservation period in the unit of  |
| ms allowed in the resource pool. Up to 16 values can be configured    |
| per resource pool. The value *ms0* is always configured.              |
+-----------------------------------------------------------------------+
| ***sl-PRS-ResourcesDedicatedSL-PRS-RP***                              |
|                                                                       |
| Indicates SL PRS resources in a slot of dedicated SL PRS resource     |
| pool as defined in TS 38.211 \[16\].                                  |
+-----------------------------------------------------------------------+
| ***sl-PRS-TxConfigIndex***                                            |
|                                                                       |
| Indicates SL PRS transmission Configuration index.                    |
+-----------------------------------------------------------------------+
| ***sl-PRS-TxConfigIndexList***                                        |
|                                                                       |
| Indicates List of *sl-PRS-Tx-ConfigIndex* indicating the SL PRS       |
| transmission index                                                    |
+-----------------------------------------------------------------------+
| ***sl-RB-Number***                                                    |
|                                                                       |
| Indicates the number of PRBs in the corresponding SL PRS dedicated    |
| resource pool, which consists of contiguous PRBs only.                |
+-----------------------------------------------------------------------+
| ***sl-SCI-basedSL-PRS-TxTriggerSCI1-B***                              |
|                                                                       |
| Indicates presence of a bit-field in SCI format 1-B to trigger SL-PRS |
| transmission by a receiving UE.                                       |
+-----------------------------------------------------------------------+
| ***sl-SelectionWindowListDedicatedSL-PRS-RP***                        |
|                                                                       |
| Parameter that determines the end of the selection window in the      |
| resource selection for a SL-PRS with respect to priority indicated in |
| SCI. Value n1 corresponds to 1\*2^µ^ , value n5 corresponds to        |
| 5\*2^µ^ , and so on, where µ = 0,1,2,3 refers to SCS 15,30,60,120 kHz |
| respectively.                                                         |
+-----------------------------------------------------------------------+
| ***sl-SensingWindowDedicated-SL-PRS-RP***                             |
|                                                                       |
| Indicates the start of the sensing window for SL PRS in a dedicated   |
| resource pool.                                                        |
+-----------------------------------------------------------------------+
| ***sl-SRC-ID-LenDedicatedSL-PRS-RP***                                 |
|                                                                       |
| Indicates the number of bits used for the source ID in SCI format     |
| 1-B.                                                                  |
+-----------------------------------------------------------------------+
| ***sl-StartRB-Subchannel-DedicatedSL-PRS-RP***                        |
|                                                                       |
| Indicates the lowest RB index of the SL PRS dedicated resource pool   |
| with respect to the lowest RB index of a SL BWP.                      |
+-----------------------------------------------------------------------+
| ***sl-SubchannelSizeDedicatedSL-PRS-RP***                             |
|                                                                       |
| Indicates size of a subchannel for PSCCH in number of RBs.            |
+-----------------------------------------------------------------------+
| ***sl-Thres-RSRP-ListDedicatedSL-PRS-RP***                            |
|                                                                       |
| Indicates a list of 64 thresholds, the threshold should be selected   |
| based on the priority in the decoded SCI and the priority in the SCI  |
| to be transmitted.                                                    |
+-----------------------------------------------------------------------+
| ***sl-ThreshS-RSSI-PRS-CBR***                                         |
|                                                                       |
| Indicates the S-RSSI threshold for determining the contribution of a  |
| sub-channel to the SL-PRS CBR measurement in a dedicated SL-PRS       |
| resource pool. Value 0 corresponds to -112 dBm, value 1 to -110 dBm,  |
| value n to (-112 + n\*2) dBm, and so on.                              |
+-----------------------------------------------------------------------+
| ***sl-TimeResource***                                                 |
|                                                                       |
| This field indicates the bitmap of the SL PRS dedicated resource      |
| pool, which is defined by repeating the bitmap with a periodicity     |
| during a SFN or DFN cycle.                                            |
+-----------------------------------------------------------------------+
| ***sl-TimeWindowSizeCBR-DedicatedSL-PRS-RP***                         |
|                                                                       |
| Indicates the time window size for CBR measurement in a dedicated     |
| SL-PRS resource pool.                                                 |
+-----------------------------------------------------------------------+
| ***sl-TimeWindowSizeCR-DedicatedSL-PRS-RP***                          |
|                                                                       |
| Indicates the time window size for CR evaluation in a dedicated       |
| SL-PRS resource pool.                                                 |
+-----------------------------------------------------------------------+
| ***sl-TxPercentageDedicatedSL-PRS-RP-List***                          |
|                                                                       |
| Indicates List of minimum Tx percentage (list per priority)           |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SL-PRS-PSCCH-Config* field descriptions                              |
+-----------------------------------------------------------------------+
| ***sl-DMRS-ScrambleID-DedicatedSL-PRS-RP***                           |
|                                                                       |
| Indicates the initialization value for PSCCH DMRS scrambling in a     |
| dedicated SL PRS resource pool.                                       |
+-----------------------------------------------------------------------+
| ***sl-FreqResourcePSCCH-DedicatedSL-PRS-RP***                         |
|                                                                       |
| Indicates the number of PRBs for PSCCH in a dedicated SL PRS resource |
| pool.                                                                 |
+-----------------------------------------------------------------------+
| ***sl-TimeResourcePSCCH-DedicatedSL-PRS-RP***                         |
|                                                                       |
| Indicates the number of symbols for PSCCH in a dedicated SL PRS       |
| resource pool.                                                        |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-PRS-PowerControl* field descriptions                              |
+-----------------------------------------------------------------------+
| ***dl-P0-SL-PRS***                                                    |
|                                                                       |
| Indicates P0 value for DL pathloss based open loop power control for  |
| SL PRS transmission in dedicated SL PRS resource pool.                |
+-----------------------------------------------------------------------+
| ***dl-Alpha-SL-PRS***                                                 |
|                                                                       |
| Indicates alpha value for DL pathloss based open loop power control   |
| for SL PRS transmission in dedicated SL PRS resource pool.            |
+-----------------------------------------------------------------------+
| ***sl-P0-SL-PRS***                                                    |
|                                                                       |
| Indicates P0 value for SL pathloss based open loop power control for  |
| SL PRS transmission in dedicated SL PRS resource pool.                |
+-----------------------------------------------------------------------+
| ***sl-Alpha-SL-PRS***                                                 |
|                                                                       |
| Indicates alpha value for SL pathloss based open loop power control   |
| for SL PRS transmission in dedicated SL PRS resource pool. When the   |
| field is absent the UE applies the value 1.                           |
+=======================================================================+

[]{#_Toc193463691 .anchor}-- *SL-PSBCH-Config*

The IE *SL-PSBCH-Config* indicates PSBCH transmission parameters on each
sidelink bandwidth part.

***SL-PSBCH-Config* information element**

\-- ASN1START

\-- TAG-SL-PSBCH-CONFIG-START

SL-PSBCH-Config-r16 ::= SEQUENCE {

dl-P0-PSBCH-r16 INTEGER (-16..15) OPTIONAL, \-- Need M

dl-Alpha-PSBCH-r16 ENUMERATED {alpha0, alpha04, alpha05, alpha06,
alpha07, alpha08, alpha09, alpha1} OPTIONAL, \-- Need M

\...,

\[\[

dl-P0-PSBCH-r17 INTEGER (-202..24) OPTIONAL \-- Need M

\]\]

}

\-- TAG-SL-PSBCH-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-PSBCH-Config* field descriptions                                  |
+-----------------------------------------------------------------------+
| ***dl-Alpha-PSBCH***                                                  |
|                                                                       |
| Indicates alpha value for DL pathloss based power control for PSBCH.  |
| When the field is not configured the UE applies the value 1.          |
+-----------------------------------------------------------------------+
| ***dl-P0-PSBCH***                                                     |
|                                                                       |
| Indicates P0 value for DL pathloss based power control for PSBCH. If  |
| not configured, DL pathloss based power control is disabled for       |
| PSBCH. When *dl-P0-PSBCH-r17* is configured, the UE ignores           |
| *dl-P0-PSBCH-r16*.                                                    |
|                                                                       |
| A Remote UE which is out of coverage, considers downlink pathloss     |
| based power control is disabled for PSBCH when *dl-P0-PSBCH* is       |
| configured.                                                           |
+=======================================================================+

#### -- *SL-PSSCH-TxConfigList*

The IE *SL-PSSCH-TxConfigList* indicates PSSCH transmission parameters.
When lower layers select parameters from the range indicated in IE
*SL-PSSCH-TxConfigList*, the UE considers both configurations in IE
*SL-PSSCH-TxConfigList* and the CBR-dependent configurations represented
in IE *SL-CBR-PriorityTxConfigList*. Only one IE *SL-PSSCH-TxConfig* is
provided per *SL-TypeTxSync*.

*SL-PSSCH-TxConfigList* information element

\-- ASN1START

\-- TAG-SL-PSSCH-TXCONFIGLIST-START

SL-PSSCH-TxConfigList-r16 ::= SEQUENCE (SIZE (1..maxPSSCH-TxConfig-r16))
OF SL-PSSCH-TxConfig-r16

SL-PSSCH-TxConfig-r16 ::= SEQUENCE {

sl-TypeTxSync-r16 SL-TypeTxSync-r16 OPTIONAL, \-- Need R

sl-ThresUE-Speed-r16 ENUMERATED {kmph60, kmph80, kmph100, kmph120,

kmph140, kmph160, kmph180, kmph200},

sl-ParametersAboveThres-r16 SL-PSSCH-TxParameters-r16,

sl-ParametersBelowThres-r16 SL-PSSCH-TxParameters-r16,

\...,

\[\[

sl-ParametersAboveThres-v1650 SL-MinMaxMCS-List-r16 OPTIONAL, \-- Need R

sl-ParametersBelowThres-v1650 SL-MinMaxMCS-List-r16 OPTIONAL \-- Need R

\]\]

}

SL-PSSCH-TxParameters-r16 ::= SEQUENCE {

sl-MinMCS-PSSCH-r16 INTEGER (0..27),

sl-MaxMCS-PSSCH-r16 INTEGER (0..31),

sl-MinSubChannelNumPSSCH-r16 INTEGER (1..27),

sl-MaxSubchannelNumPSSCH-r16 INTEGER (1..27),

sl-MaxTxTransNumPSSCH-r16 INTEGER (1..32),

sl-MaxTxPower-r16 SL-TxPower-r16 OPTIONAL \-- Cond CBR

}

\-- TAG-SL-PSSCH-TXCONFIGLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-PSSCH-TxConfigList* field descriptions                            |
+-----------------------------------------------------------------------+
| ***sl-MaxTxTransNumPSSCH***                                           |
|                                                                       |
| Indicates the maximum transmission number (including new transmission |
| and retransmission) for PSSCH.                                        |
+-----------------------------------------------------------------------+
| ***sl-MaxTxPower***                                                   |
|                                                                       |
| This field indicates the maximum transmission power for transmission  |
| on PSSCH and PSCCH.                                                   |
+-----------------------------------------------------------------------+
| ***sl-MinMCS-PSSCH, sl-MaxMCS-PSSCH***                                |
|                                                                       |
| This field indicates the minimum and maximum MCS values used for      |
| transmissions on PSSCH. The UE shall ignore the minimum and maximum   |
| MCS values used for the associated MCS table(s) in                    |
| *sl-ParametersAboveThres-r16* and *sl-ParametersBelowThres-r16* if    |
| *sl-ParametersAboveThres-v1650* and *sl-ParametersBelowThres-v1650*   |
| are present, respectively.                                            |
+-----------------------------------------------------------------------+
| ***sl-MinSubChannelNumPSSCH, sl-MaxSubChannelNumPSSCH***              |
|                                                                       |
| This field indicates the minimum and maximum number of sub-channels   |
| which may be used for transmissions on PSSCH.                         |
+-----------------------------------------------------------------------+
| ***sl-TypeTxSync***                                                   |
|                                                                       |
| This field indicates the synchronization reference type. For          |
| configurations by the eNB/gNB, only *gnbEnb* can be configured; and   |
| for pre-configuration or when this field is absent, the configuration |
| is applicable for all synchronization reference types.                |
+-----------------------------------------------------------------------+
| ***sl-ThresUE-Speed***                                                |
|                                                                       |
| This field indicates a UE absolute speed threshold.                   |
+=======================================================================+

  -----------------------------------------------------------------------
  Conditional         Explanation
  Presence            
  ------------------- ---------------------------------------------------
  *CBR*               The field is optionally present, Need R, when the
                      IE *SL-PSSCH-TxParameters* is present in
                      *SL-CBR-CommonTxConfigList,*
                      *SL-UE-SelectedConfig,* *SIB12* or
                      *SidelinkPreconfigNR*; otherwise the field is not
                      present, need R.

  -----------------------------------------------------------------------

#### -- *SL-QoS-FlowIdentity*

The IE *SL-QoS-FlowIdentity* is used to identify a sidelink QoS flow.

*SL-QoS-FlowIdentity* information element

\-- ASN1START

\-- TAG-SL-QOS-FLOWIDENTITY-START

SL-QoS-FlowIdentity-r16 ::= INTEGER (1..maxNrofSL-QFIs-r16)

\-- TAG-SL-QOS-FLOWIDENTITY-STOP

\-- ASN1STOP

#### -- *SL-QoS-Profile*

The IE *SL-QoS-Profile* is used to give the QoS parameters for a
sidelink QoS flow. Need codes or conditions specified for
*SL-QoS-Profile* do not apply, in case *SL-QoS-Profile* is included in
*SidelinkUEInformationNR*.

*SL-QoS-Profile* information element

\-- ASN1START

\-- TAG-SL-QOS-PROFILE-START

SL-QoS-Profile-r16 ::= SEQUENCE {

sl-PQI-r16 SL-PQI-r16 OPTIONAL, \-- Need R

sl-GFBR-r16 INTEGER (0..4000000000) OPTIONAL, \-- Need R

sl-MFBR-r16 INTEGER (0..4000000000) OPTIONAL, \-- Need R

sl-Range-r16 INTEGER (1..1000) OPTIONAL, \-- Need R

\...

}

SL-PQI-r16 ::= CHOICE {

sl-StandardizedPQI-r16 INTEGER (0..255),

sl-Non-StandardizedPQI-r16 SEQUENCE {

sl-ResourceType-r16 ENUMERATED {gbr, non-GBR, delayCriticalGBR, spare1}
OPTIONAL, \-- Need R

sl-PriorityLevel-r16 INTEGER (1..8) OPTIONAL, \-- Need R

sl-PacketDelayBudget-r16 INTEGER (0..1023) OPTIONAL, \-- Need R

sl-PacketErrorRate-r16 INTEGER (0..9) OPTIONAL, \-- Need R

sl-AveragingWindow-r16 INTEGER (0..4095) OPTIONAL, \-- Need R

sl-MaxDataBurstVolume-r16 INTEGER (0..4095) OPTIONAL, \-- Need R

\...

}

}

\-- TAG-SL-QOS-PROFILE-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-QoS-Profile* field descriptions                                   |
+-----------------------------------------------------------------------+
| ***sl-GFBR***                                                         |
|                                                                       |
| Indicate the guaranteed bit rate for a GBR QoS flow. The unit is:     |
| Kbit/s                                                                |
+-----------------------------------------------------------------------+
| ***sl-MFBR***                                                         |
|                                                                       |
| Indicate the maximum bit rate for a GBR QoS flow. The unit is: Kbit/s |
+-----------------------------------------------------------------------+
| ***sl-PQI***                                                          |
|                                                                       |
| This field indicates either the PQI for standardized PQI or           |
| non-standardized QoS parameters.                                      |
+-----------------------------------------------------------------------+
| ***sl-Range***                                                        |
|                                                                       |
| This field indicates the range parameter of the Qos flow, as defined  |
| in clause 5.4.1.1.1, TS 23.287 \[55\]. It is present only for         |
| groupcast. The unit is meter.                                         |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-PQI* field descriptions                                           |
+-----------------------------------------------------------------------+
| ***sl-AveragingWindow***                                              |
|                                                                       |
| Indicates the Averaging Window for a QoS flow, and applies to GBR QoS |
| flows only. Unit: ms. The default value of the IE is 2000ms.          |
+-----------------------------------------------------------------------+
| ***sl-MaxDataBurstVolume***                                           |
|                                                                       |
| Indicates the Maximum Data Burst Volume for a QoS flow, and applies   |
| to delay critical GBR QoS flows only. Unit: byte.                     |
+-----------------------------------------------------------------------+
| ***sl-PacketDelayBudget***                                            |
|                                                                       |
| Indicates the Packet Delay Budget for a QoS flow. Upper bound value   |
| for the delay that a packet may experience expressed in unit of       |
| 0.5ms.                                                                |
+-----------------------------------------------------------------------+
| ***sl-PacketErrorRate***                                              |
|                                                                       |
| Indicates the Packet Error Rate for a QoS flow. The packet error rate |
| is expressed as Scalar x 10-k where k is the Exponent.                |
+-----------------------------------------------------------------------+
| ***sl-PriorityLevel***                                                |
|                                                                       |
| Indicates the Priority Level for a QoS flow. Values ordered in        |
| decreasing order of priority, i.e. with 1 as the highest priority and |
| 8 as the lowest priority.                                             |
+-----------------------------------------------------------------------+
| ***sl-StandardizedPQI***                                              |
|                                                                       |
| Indicate the PQI for standardized PQI.                                |
+=======================================================================+

#### -- *SL-QuantityConfig*

The IE *SL*-*QuantityConfig* specifies the layer 3 filtering
coefficients for NR SL RSRP measurement for a destination.

*SL-QuantityConfig* information element

\-- ASN1START

\-- TAG-SL-QUANTITYCONFIG-START

SL-QuantityConfig-r16 ::= SEQUENCE {

sl-FilterCoefficientDMRS-r16 FilterCoefficient DEFAULT fc4,

\...

}

\-- TAG-SL-QuantityConfig-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-QuantityConfig* field descriptions                                |
+-----------------------------------------------------------------------+
| ***sl-FilterCoefficientDMRS***                                        |
|                                                                       |
| DMRS based L3 filter configuration:                                   |
|                                                                       |
| Specifies L3 filter configuration for sidelink RSRP measurement       |
| result from the L1 fiter(s), as defined in TS 38.215 \[9\].           |
+=======================================================================+

#### -- *SL-RadioBearerConfig*

The IE *SL-RadioBearerConfig* specifies the sidelink DRB configuration
information for NR sidelink communication.

*SL-RadioBearerConfig* information element

\-- ASN1START

\-- TAG-SL-RADIOBEARERCONFIG-START

SL-RadioBearerConfig-r16 ::= SEQUENCE {

slrb-Uu-ConfigIndex-r16 SLRB-Uu-ConfigIndex-r16,

sl-SDAP-Config-r16 SL-SDAP-Config-r16 OPTIONAL, \-- Cond SLRBSetup

sl-PDCP-Config-r16 SL-PDCP-Config-r16 OPTIONAL, \-- Cond SLRBSetup

sl-TransRange-r16 ENUMERATED {m20, m50, m80, m100, m120, m150, m180,
m200, m220, m250, m270, m300, m350, m370,

m400, m420, m450, m480, m500, m550, m600, m700, m1000, spare9, spare8,
spare7, spare6,

spare5, spare4, spare3, spare2, spare1} OPTIONAL, \-- Need R

\...

}

\-- TAG-SL-RADIOBEARERCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-RadioBearerConfig* field descriptions                             |
+-----------------------------------------------------------------------+
| ***sl-PDCP-Config***                                                  |
|                                                                       |
| This field indicates the PDCP parameters for the sidelink DRB.        |
+-----------------------------------------------------------------------+
| ***sl-SDAP-Config***                                                  |
|                                                                       |
| This field indicates how to map sidelink QoS flows to sidelink DRB.   |
+-----------------------------------------------------------------------+
| ***slrb-Uu-ConfigIndex***                                             |
|                                                                       |
| This field indicates the index of sidelink DRB configuration.         |
+-----------------------------------------------------------------------+
| ***sl-TransRange***                                                   |
|                                                                       |
| This field indicates the transmission range of the sidelink DRB. The  |
| unit is meter.                                                        |
+=======================================================================+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *SLRBSetup*          The field is mandatory present in case of sidelink
                       DRB setup via the dedicated signalling and in case
                       of sidelink DRB configuration via system
                       information and pre-configuration; otherwise the
                       field is optionally present, need M.

  -----------------------------------------------------------------------

#### -- *SL-RBSetConfig*

The IE SL-RBSetConfig specifies the configuration information for RB set
for NR Sidelink Communication.

*SL-RBSetConfig* information element

\-- ASN1START

\-- TAG-SL-RBSETCONFIG-START

SL-RBSetConfig-r18 ::= SEQUENCE {

sl-RBSetIndex-r18 INTEGER (0..4),

sl-NumOfSSSBRepetition-r18 INTEGER (2..9) OPTIONAL, \-- Need R

sl-GapBetweenSSSBRepetition-r18 INTEGER (1..84) OPTIONAL \-- Need R

}

\-- TAG-SL-RBSETCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-RBSetConfig* field descriptions                                   |
+-----------------------------------------------------------------------+
| ***sl-GapBetweenSSSBRepetition***                                     |
|                                                                       |
| Indicate the gap between two adjacent S-SSB repetitions in frequency  |
| domain in one RB set, and the gap is between the lowest subcarrier of |
| the upper PSBCH and the highest subcarrier of the lower PSBCH. The    |
| Unit is PRB.                                                          |
+-----------------------------------------------------------------------+
| ***sl-NumOfSSSBRepetition***                                          |
|                                                                       |
| Indicate the number of S-SSB repetitions in frequency domain in one   |
| RB set. S-SSB in the frequency domain indicated by                    |
| *sl-AbsoluteFrequencySSB* (i.e. S-SSB transmission without            |
| repetition) is applicable in region with no OCB requirement, or with  |
| OCB exemption.                                                        |
+-----------------------------------------------------------------------+
| ***sl-RBSetIndex***                                                   |
|                                                                       |
| Indicates the index of RB-set for which the configuration applies.    |
+=======================================================================+

#### -- *SL-RelayIndicationMP*

The IE *SL-RelayIndicationMP* is used to indicate the L2 U2N Relay UE
supporting RRC connection establishment/resume for MP operation
triggered by receiving *RemoteUEInformationSidelink* containing the
*connectionForMP* as specified in 5.3.3.1a and 5.3.13.1a in Rel-18.

*SL-RelayIndicationMP* information element

\-- ASN1START

\-- TAG-SL-RELAYINDICATIONMP-START

SL-RelayIndicationMP-r18 ::= ENUMERATED {support}

\-- TAG-SL-RELAYINDICATIONMP-STOP

\-- ASN1STOP

[]{#_Toc193463699 .anchor}-- *SL-RelayUE-Config*

The IE *SL-RelayUE-Config* specifies the configuration information for
NR sidelink U2N Relay UE.

*SL-RelayUE-Config* information element

\-- ASN1START

\-- TAG-SL-RELAYUE-CONFIG-START

SL-RelayUE-Config-r17::= SEQUENCE {

threshHighRelay-r17 RSRP-Range OPTIONAL, \-- Need R

threshLowRelay-r17 RSRP-Range OPTIONAL, \-- Need R

hystMaxRelay-r17 Hysteresis OPTIONAL, \-- Cond ThreshHighRelay

hystMinRelay-r17 Hysteresis OPTIONAL \-- Cond ThreshLowRelay

}

\-- TAG-SL-RELAYUE-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-RelayUE-Config* field descriptions                                |
+-----------------------------------------------------------------------+
| ***threshHighRelay***                                                 |
|                                                                       |
| Indicates the upper threshold of Uu RSRP for a UE that is in network  |
| coverage to evaluate AS layer conditions for U2N relay UE operation.  |
+-----------------------------------------------------------------------+
| ***threshLowRelay***                                                  |
|                                                                       |
| Indicates the lower threshold of Uu RSRP for a UE that is in network  |
| coverage to evaluate AS layer conditions for U2N relay UE operation.  |
+=======================================================================+

  -----------------------------------------------------------------------
  Conditional         Explanation
  Presence            
  ------------------- ---------------------------------------------------
  *ThreshHighRelay*   This field is mandatory present if threshHighRelay
                      is included. Otherwise, the field is absent, Need
                      R.

  *ThreshLowRelay*    This field is mandatory present if threshLowRelay
                      is included. Otherwise, the field is absent, Need
                      R.
  -----------------------------------------------------------------------

#### -- *SL-RelayUE-ConfigU2U*

The IE *SL-RelayUE-ConfigU2U* specifies the threshold configuration
information for NR sidelink U2U Relay UE.

*SL-RelayUE-ConfigU2U* information element

\-- ASN1START

\-- TAG-SL-RELAYUE-CONFIGU2U-START

SL-RelayUE-ConfigU2U-r18::= SEQUENCE {

sl-RSRP-Thresh-DiscConfig-r18 SL-RSRP-Range-r16 OPTIONAL, \-- Need R

sd-RSRP-ThreshDiscConfig-r18 SL-RSRP-Range-r16 OPTIONAL, \-- Need R

sd-hystMaxRelay-r18 Hysteresis OPTIONAL \-- Cond SD-RSRP-ThreshRelay

}

SL-RelayUE-ConfigU2U-v1840::= SEQUENCE {

sl-FilterCoefficientU2U-r18 FilterCoefficient OPTIONAL, \-- Need R

sd-FilterCoefficientU2U-r18 FilterCoefficient OPTIONAL, \-- Need R

\...

}

\-- TAG-SL-RELAYUE-CONFIGU2U-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-RelayUE-ConfigU2U* field descriptions                             |
+-----------------------------------------------------------------------+
| ***sd-FilterCoefficientU2U***                                         |
|                                                                       |
| Specifies L3 filter coefficient for SD-RSRP measurement results from  |
| L1 filter, and for SL-RSRP measurements.                              |
+-----------------------------------------------------------------------+
| ***sd-RSRP-ThreshDiscConfig***                                        |
|                                                                       |
| Indicates the threshold of SD-RSRP for a U2U Relay UE to evaluate AS  |
| layer conditions for discovery. The U2U relay UE applies the value of |
| this field to evaluate AS layer conditions to decide which UE(s) can  |
| be announced as proximity UE(s) in the discovery message when         |
| performing U2U Relay Discovery with Model A, and decide whether to    |
| forward the discovery message when performing the U2U Relay Discovery |
| with Model B or U2U relay communication with integrated Discovery as  |
| specified in TS 23.304 \[65\].                                        |
+-----------------------------------------------------------------------+
| ***sl-FilterCoefficientU2U***                                         |
|                                                                       |
| Specifies L3 filter coefficient for SL-RSRP measurement results from  |
| L1 filter.                                                            |
+-----------------------------------------------------------------------+
| ***sl-RSRP-Thresh-DiscConfig***                                       |
|                                                                       |
| Indicates the threshold of SL-RSRP for a U2U Relay UE to evaluate AS  |
| layer conditions for discovery. The U2U relay UE applies the value of |
| this field to decide which UE(s) can be announced as proximity UE(s)  |
| in the discovery message when performing U2U Relay Discovery with     |
| Model A.                                                              |
+=======================================================================+

  --------------------------------------------------------------------------
  Conditional Presence    Explanation
  ----------------------- --------------------------------------------------
  *SD-RSRP-ThreshRelay*   This field is mandatory present if
                          *sd-RSRP-ThreshDiscConfig* is included. Otherwise,
                          the field is absent, Need R.

  --------------------------------------------------------------------------

#### -- *SL-RemoteUE-Config*

The IE *SL-RemoteUE-Config* specifies the configuration information for
NR sidelink U2N Remote UE.

*SL-RemoteUE-Config* information element

\-- ASN1START

\-- TAG-SL-REMOTEUE-CONFIG-START

SL-RemoteUE-Config-r17::= SEQUENCE {

threshHighRemote-r17 RSRP-Range OPTIONAL, \-- Need R

hystMaxRemote-r17 Hysteresis OPTIONAL, \-- Cond ThreshHighRemote

sl-ReselectionConfig-r17 SL-ReselectionConfig-r17 OPTIONAL \-- Need R

}

SL-ReselectionConfig-r17::= SEQUENCE {

sl-RSRP-Thresh-r17 SL-RSRP-Range-r16 OPTIONAL, \-- Need R

sl-FilterCoefficientRSRP-r17 FilterCoefficient OPTIONAL, \-- Need R

sl-HystMin-r17 Hysteresis OPTIONAL \-- Cond SL-RSRP-Thresh

}

\-- TAG-SL-REMOTEUE-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-RemoteUE-Config* field descriptions                               |
+-----------------------------------------------------------------------+
| ***sl-ReselectionConfig***                                            |
|                                                                       |
| Includes the parameters used by the U2N remote UE when selecting/     |
| reselecting a U2N relay UE.                                           |
+-----------------------------------------------------------------------+
| ***thresHighRemote***                                                 |
|                                                                       |
| Indicates the threshold of Uu RSRP for a UE that is in network        |
| coverage to evaluate AS layer conditions for U2N remote UE operation. |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-ReselectionConfig* field descriptions                             |
+-----------------------------------------------------------------------+
| ***sl-FilterCoefficientRSRP***                                        |
|                                                                       |
| Specifies L3 filter coefficient for SL communication/ discovery RSRP  |
| measurement results from L1 filter.                                   |
+-----------------------------------------------------------------------+
| ***sl-RSRP-Thresh***                                                  |
|                                                                       |
| Indicates the threshold of SL communication/ discovery RSRP for a U2N |
| remote UE to perform relay UE selection/ reselection.                 |
+=======================================================================+

  ------------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- ---------------------------------------------------
  *SL-RSRP-Thresh*     This field is mandatory present if *sl-RSRP-Thresh*
                       is included. Otherwise, the field is absent, Need
                       R.

  *ThreshHighRemote*   This field is mandatory present if threshHighRemote
                       is included. Otherwise, the field is absent, Need
                       R.
  ------------------------------------------------------------------------

#### *-- SL-RemoteUE-ConfigU2U*

The IE *SL-RemoteUE-ConfigU2U* specifies the threshold configuration
information for NR sidelink U2U Remote UE.

*SL-RemoteUE-ConfigU2U* information element

\-- ASN1START

\-- TAG-SL-REMOTEUE-CONFIGU2U-START

SL-RemoteUE-ConfigU2U-r18::= SEQUENCE {

sl-RSRP-ThreshU2U-r18 SL-RSRP-Range-r16 OPTIONAL, \-- Need R

sl-HystMinU2U-r18 Hysteresis OPTIONAL, \-- Cond SL-RSRP-ThreshU2U

sd-RSRP-ThreshU2U-r18 SL-RSRP-Range-r16 OPTIONAL, \-- Need R

sd-FilterCoefficientU2U-r18 FilterCoefficient OPTIONAL, \-- Need R

sd-HystMinU2U-r18 Hysteresis OPTIONAL \-- Cond SD-RSRP-ThreshU2U

}

SL-RemoteUE-ConfigU2U-v1830::= SEQUENCE {

sl-FilterCoefficientU2U-r18 FilterCoefficient OPTIONAL, \-- Need R

\...

}

\-- TAG-SL-REMOTEUE-CONFIGU2U-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-RemoteUE-ConfigU2U* field descriptions                            |
+-----------------------------------------------------------------------+
| ***sl-FilterCoefficientU2U***                                         |
|                                                                       |
| Specifies L3 filter coefficient for SL-RSRP measurement results from  |
| L1 filter.                                                            |
+-----------------------------------------------------------------------+
| ***sl-RSRP-ThreshU2U***                                               |
|                                                                       |
| Indicates the threshold of SL-RSRP for a U2U Remote UE to perform     |
| Relay UE selection/ reselection. The U2U remote UE applies the value  |
| of this field to evaluate AS layer conditions on direct PC5 link with |
| the peer U2U Remote UE to trigger relay selection, and evaluate AS    |
| layer conditions on U2U relay link with U2U Relay UE to trigger relay |
| reselection.                                                          |
+-----------------------------------------------------------------------+
| ***sd-RSRP-ThreshU2U***                                               |
|                                                                       |
| Indicates the threshold of SD-RSRP for a U2U Remote UE to perform     |
| discovery and Relay UE selection/ reselection. For discovery, the U2U |
| Remote UE applies the value of this field to evaluate AS layer        |
| conditions to decide whether to respond the discovery message when    |
| performing the U2U Relay Discovery with Model B as specified in TS    |
| 23.304 \[65\]. For relay selection and reselection, the U2U remote UE |
| applies the value of this field to evaluate AS layer conditions on    |
| direct PC5 link to trigger relay selection, and evaluate AS layer     |
| conditions on U2U relay link to trigger relay reselection. The target |
| U2U remote UE applies the value of this field to evaluate AS layer    |
| conditions trigger relay selection when performing U2U relay          |
| communication with integrated Discovery as specified in TS 23.304     |
| \[65\].                                                               |
+-----------------------------------------------------------------------+
| ***sd-FilterCoefficientU2U***                                         |
|                                                                       |
| Specifies L3 filter coefficient for SD-RSRP measurement results from  |
| L1 filter, and for SL-RSRP measurement.                               |
+=======================================================================+

  ------------------------------------------------------------------------
  Conditional Presence  Explanation
  --------------------- --------------------------------------------------
  *SL-RSRP-ThreshU2U*   This field is mandatory present if
                        *sl-RSRP-ThreshU2U* is included. Otherwise, the
                        field is absent, Need R.

  *SD-RSRP-ThreshU2U*   This field is mandatory present if
                        *sd-RSRP-ThreshU2U* is included. Otherwise, the
                        field is absent, Need R.
  ------------------------------------------------------------------------

#### -- *SL-ReportConfigList*

The IE *SL*-*ReportConfigList* concerns a list of SL measurement
reporting configurations to add or modify for a destination.

*SL-ReportConfigList* information element

\-- ASN1START

\-- TAG-SL-REPORTCONFIGLIST-START

SL-ReportConfigList-r16 ::= SEQUENCE (SIZE
(1..maxNrofSL-ReportConfigId-r16)) OF SL-ReportConfigInfo-r16

SL-ReportConfigInfo-r16 ::= SEQUENCE {

sl-ReportConfigId-r16 SL-ReportConfigId-r16,

sl-ReportConfig-r16 SL-ReportConfig-r16,

\...

}

SL-ReportConfigId-r16 ::= INTEGER (1..maxNrofSL-ReportConfigId-r16)

SL-ReportConfig-r16 ::= SEQUENCE {

sl-ReportType-r16 CHOICE {

sl-Periodical-r16 SL-PeriodicalReportConfig-r16,

sl-EventTriggered-r16 SL-EventTriggerConfig-r16,

\...

},

\...

}

SL-PeriodicalReportConfig-r16 ::= SEQUENCE {

sl-ReportInterval-r16 ReportInterval,

sl-ReportAmount-r16 ENUMERATED {r1, r2, r4, r8, r16, r32, r64,
infinity},

sl-ReportQuantity-r16 SL-MeasReportQuantity-r16,

sl-RS-Type-r16 SL-RS-Type-r16,

\...

}

SL-EventTriggerConfig-r16 ::= SEQUENCE {

sl-EventId-r16 CHOICE {

eventS1-r16 SEQUENCE {

s1-Threshold-r16 SL-MeasTriggerQuantity-r16,

sl-ReportOnLeave-r16 BOOLEAN,

sl-Hysteresis-r16 Hysteresis,

sl-TimeToTrigger-r16 TimeToTrigger,

\...

},

eventS2-r16 SEQUENCE {

s2-Threshold-r16 SL-MeasTriggerQuantity-r16,

sl-ReportOnLeave-r16 BOOLEAN,

sl-Hysteresis-r16 Hysteresis,

sl-TimeToTrigger-r16 TimeToTrigger,

\...

},

\...

},

sl-ReportInterval-r16 ReportInterval,

sl-ReportAmount-r16 ENUMERATED {r1, r2, r4, r8, r16, r32, r64,
infinity},

sl-ReportQuantity-r16 SL-MeasReportQuantity-r16,

sl-RS-Type-r16 SL-RS-Type-r16,

\...

}

SL-MeasReportQuantity-r16 ::= CHOICE {

sl-RSRP-r16 BOOLEAN,

\...

}

SL-MeasTriggerQuantity-r16 ::= CHOICE {

sl-RSRP-r16 RSRP-Range,

\...

}

SL-RS-Type-r16 ::= ENUMERATED {dmrs, sl-prs, spare2, spare1}

\-- TAG-SL-REPORTCONFIGLIST-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-ReportConfig* field descriptions                                  |
+-----------------------------------------------------------------------+
| ***sl-ReportType***                                                   |
|                                                                       |
| Type of the configured sidelink measurement report.                   |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-EventTriggerConfig* field descriptions                            |
+-----------------------------------------------------------------------+
| ***sl-EventId***                                                      |
|                                                                       |
| Choice of sidelink measurement event triggered reporting criteria.    |
+-----------------------------------------------------------------------+
| ***sl-ReportAmount***                                                 |
|                                                                       |
| Number of sidelink measurement reports applicable for                 |
| *sl-EventTriggered* report type.                                      |
+-----------------------------------------------------------------------+
| ***sl-ReportInterval***                                               |
|                                                                       |
| Indicates the interval between periodical reports (i.e., when         |
| *sl-ReportAmount* exceeds 1) for *sl-EventTriggered* report type.     |
+-----------------------------------------------------------------------+
| ***sl-ReportOnLeave***                                                |
|                                                                       |
| indicates whether or not the UE shall initiate the sidelink           |
| measurement reporting procedure when the leaving condition is met for |
| a frequency in *sl-FrequencyTriggeredList*, as specified in           |
| 5.8.10.4.1.                                                           |
+-----------------------------------------------------------------------+
| ***sl-ReportQuantity***                                               |
|                                                                       |
| The sidelink measurement quantities to be included in the sidelink    |
| measurement report.                                                   |
+-----------------------------------------------------------------------+
| ***sl-TimeToTrigger***                                                |
|                                                                       |
| Time during which specific criteria for the event needs to be met in  |
| order to trigger a sidelink measurement report.                       |
+-----------------------------------------------------------------------+
| ***sN-Threshold***                                                    |
|                                                                       |
| Threshold used for events S1 and S2 specified in clauses 5.8.10.4.2   |
| and 5.8.10.4.3, respectively.                                         |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-PeriodicalReportConfig* field descriptions                        |
+-----------------------------------------------------------------------+
| ***sl-ReportAmount***                                                 |
|                                                                       |
| Number of sidelink measurement reports applicable for *sl-Periodical* |
| report type.                                                          |
+-----------------------------------------------------------------------+
| ***sl-ReportInterval***                                               |
|                                                                       |
| Indicates the interval between periodical reports (i.e., when         |
| *sl-ReportAmount* exceeds 1) for *sl-Periodical* report type.         |
+-----------------------------------------------------------------------+
| ***sl-ReportQuantity***                                               |
|                                                                       |
| The sidelink measurement quantities to be included in the sidelink    |
| measurement report.                                                   |
+=======================================================================+

#### -- *SL-ResourcePool*

The IE *SL-ResourcePool* specifies the configuration information for NR
sidelink communication resource pool.

*SL-ResourcePool* information element

\-- ASN1START

\-- TAG-SL-RESOURCEPOOL-START

SL-ResourcePool-r16 ::= SEQUENCE {

sl-PSCCH-Config-r16 SetupRelease { SL-PSCCH-Config-r16 } OPTIONAL, \--
Need M

sl-PSSCH-Config-r16 SetupRelease { SL-PSSCH-Config-r16 } OPTIONAL, \--
Need M

sl-PSFCH-Config-r16 SetupRelease { SL-PSFCH-Config-r16 } OPTIONAL, \--
Need M

sl-SyncAllowed-r16 SL-SyncAllowed-r16 OPTIONAL, \-- Need M

sl-SubchannelSize-r16 ENUMERATED {n10, n12, n15, n20, n25, n50, n75,
n100} OPTIONAL, \-- Need M

dummy INTEGER (10..160) OPTIONAL, \-- Need M

sl-StartRB-Subchannel-r16 INTEGER (0..265) OPTIONAL, \-- Need M

sl-NumSubchannel-r16 INTEGER (1..27) OPTIONAL, \-- Need M

sl-Additional-MCS-Table-r16 ENUMERATED {qam256, qam64LowSE,
qam256-qam64LowSE } OPTIONAL, \-- Need M

sl-ThreshS-RSSI-CBR-r16 INTEGER (0..45) OPTIONAL, \-- Need M

sl-TimeWindowSizeCBR-r16 ENUMERATED {ms100, slot100} OPTIONAL, \-- Need
M

sl-TimeWindowSizeCR-r16 ENUMERATED {ms1000, slot1000} OPTIONAL, \-- Need
M

sl-PTRS-Config-r16 SL-PTRS-Config-r16 OPTIONAL, \-- Need M

sl-UE-SelectedConfigRP-r16 SL-UE-SelectedConfigRP-r16 OPTIONAL, \-- Need
M

sl-RxParametersNcell-r16 SEQUENCE {

sl-TDD-Configuration-r16 TDD-UL-DL-ConfigCommon OPTIONAL, \-- Need M

sl-SyncConfigIndex-r16 INTEGER (0..15)

} OPTIONAL, \-- Need M

sl-ZoneConfigMCR-List-r16 SEQUENCE (SIZE (16)) OF SL-ZoneConfigMCR-r16
OPTIONAL, \-- Need M

sl-FilterCoefficient-r16 FilterCoefficient OPTIONAL, \-- Need M

sl-RB-Number-r16 INTEGER (10..275) OPTIONAL, \-- Need M

sl-PreemptionEnable-r16 ENUMERATED {enabled, pl1, pl2, pl3, pl4, pl5,
pl6, pl7, pl8} OPTIONAL, \-- Need R

sl-PriorityThreshold-UL-URLLC-r16 INTEGER (1..9) OPTIONAL, \-- Need M

sl-PriorityThreshold-r16 INTEGER (1..9) OPTIONAL, \-- Need M

sl-X-Overhead-r16 ENUMERATED {n0,n3, n6, n9} OPTIONAL, \-- Need S

sl-PowerControl-r16 SL-PowerControl-r16 OPTIONAL, \-- Need M

sl-TxPercentageList-r16 SL-TxPercentageList-r16 OPTIONAL, \-- Need M

sl-MinMaxMCS-List-r16 SL-MinMaxMCS-List-r16 OPTIONAL, \-- Need M

\...,

\[\[

sl-TimeResource-r16 BIT STRING (SIZE (10..160)) OPTIONAL \-- Need M

\]\],

\[\[

sl-PBPS-CPS-Config-r17 SetupRelease { SL-PBPS-CPS-Config-r17 } OPTIONAL,
\-- Need M

sl-InterUE-CoordinationConfig-r17 SetupRelease {
SL-InterUE-CoordinationConfig-r17 } OPTIONAL \-- Need M

\]\],

\[\[

sl-CPE-StartingPositionsPSCCH-PSSCH-InitiateCOT-List-r18

SetupRelease { SL-CPE-StartingPositionsPSCCH-PSSCH-List-r18 } OPTIONAL,
\-- Need M

sl-CPE-StartingPositionsPSCCH-PSSCH-InitiateCOT-Default-r18 INTEGER
(1..9) OPTIONAL, \-- Need M

sl-CPE-StartingPositionsPSCCH-PSSCH-WithinCOT-List-r18

SetupRelease { SL-CPE-StartingPositionsPSCCH-PSSCH-List-r18 } OPTIONAL,
\-- Need M

sl-CPE-StartingPositionsPSCCH-PSSCH-WithinCOT-Default-r18 INTEGER (1..9)
OPTIONAL, \-- Need M

sl-Type1-LBT-BlockingOption1-r18 ENUMERATED {enabled} OPTIONAL, \-- Need
R

sl-Type1-LBT-BlockingOption2-r18 ENUMERATED {enabled} OPTIONAL, \-- Need
R

sl-NumInterlacePerSubchannel-r18 ENUMERATED {sc1, sc2} OPTIONAL, \--
Need M

sl-NumReferencePRBs-OfInterlace-r18 ENUMERATED {prb10, prb11} OPTIONAL,
\-- Need M

sl-TransmissionStructureForPSFCH-r18 ENUMERATED {commonInterlace,
dedicatedInterlace} OPTIONAL, \-- Need M

sl-NumDedicatedPRBs-ForPSFCH-r18 ENUMERATED {prb1, prb2, prb5} OPTIONAL,
\-- Need M

sl-NumPSFCH-Occasions-r18 ENUMERATED {o1, o2, o3, o4} OPTIONAL, \-- Need
M

sl-PSFCH-CommonInterlaceIndex-r18 INTEGER (0..9) OPTIONAL, \-- Need M

sl-CPE-StartingPositionPSFCH-r18 INTEGER (1..9) OPTIONAL, \-- Need M

sl-NumRefSymbolLength-r18 ENUMERATED {sym7, sym8, sym9, sym10, sym11,
sym12, sym13, sym14} OPTIONAL, \-- Need M

sl-PSFCH-RB-SetList-r18 SEQUENCE (SIZE (1..4)) OF BIT STRING (SIZE
(10..275)) OPTIONAL, \-- Need M

sl-IUC-RB-SetList-r18 SEQUENCE (SIZE (1..4)) OF BIT STRING (SIZE
(10..275)) OPTIONAL, \-- Need M

sl-PSFCH-PowerOffset-r18 INTEGER (0..10) OPTIONAL, \-- Need M

sl-RBSetIndexOfResourcePool-r18 SEQUENCE (SIZE (1..5)) OF INTEGER (0..4)
OPTIONAL, \-- Need M

sl-A2X-Service-r18 ENUMERATED {brid, daa, bridAndDAA, spare1} OPTIONAL,
\-- Cond A2X

sl-PRS-ResourcesSharedSL-PRS-RP-r18 SEQUENCE (SIZE (1..17)) OF
SL-PRS-ResourceSharedSL-PRS-RP-r18 OPTIONAL, \-- Need M

numSym-SL-PRS-2ndStageSCI-r18 INTEGER (1..4) OPTIONAL, \-- Need M

sl-SCI-basedSL-PRS-TxTriggerSCI2-D-r18 BOOLEAN OPTIONAL \-- Need M

\]\]

}

SL-CPE-StartingPositionsPSCCH-PSSCH-List-r18 ::= SEQUENCE (SIZE (8)) OF
SL-CPE-StartingPositionsPSCCH-PSSCH-r18

SL-CPE-StartingPositionsPSCCH-PSSCH-r18 ::= SEQUENCE {

sl-Priority-r18 INTEGER (1..8),

sl-CPE-StartingPositions-r18 SEQUENCE (SIZE (1..9)) OF INTEGER (1..9)

}

SL-ZoneConfigMCR-r16 ::= SEQUENCE {

sl-ZoneConfigMCR-Index-r16 INTEGER (0..15),

sl-TransRange-r16 ENUMERATED {m20, m50, m80, m100, m120, m150, m180,
m200, m220, m250, m270, m300, m350,

m370, m400, m420, m450, m480, m500, m550, m600, m700, m1000, spare9,
spare8,

spare7, spare6, spare5, spare4, spare3, spare2, spare1}

OPTIONAL, \-- Need M

sl-ZoneConfig-r16 SL-ZoneConfig-r16 OPTIONAL, \-- Need M

\...

}

SL-SyncAllowed-r16 ::= SEQUENCE {

gnss-Sync-r16 ENUMERATED {true} OPTIONAL, \-- Need R

gnbEnb-Sync-r16 ENUMERATED {true} OPTIONAL, \-- Need R

ue-Sync-r16 ENUMERATED {true} OPTIONAL \-- Need R

}

SL-PSCCH-Config-r16 ::= SEQUENCE {

sl-TimeResourcePSCCH-r16 ENUMERATED {n2, n3} OPTIONAL, \-- Need M

sl-FreqResourcePSCCH-r16 ENUMERATED {n10,n12, n15, n20, n25} OPTIONAL,
\-- Need M

sl-DMRS-ScrambleID-r16 INTEGER (0..65535) OPTIONAL, \-- Need M

sl-NumReservedBits-r16 INTEGER (2..4) OPTIONAL, \-- Need M

\...

}

SL-PSSCH-Config-r16 ::= SEQUENCE {

sl-PSSCH-DMRS-TimePatternList-r16 SEQUENCE (SIZE (1..3)) OF INTEGER
(2..4) OPTIONAL, \-- Need M

sl-BetaOffsets2ndSCI-r16 SEQUENCE (SIZE (4)) OF SL-BetaOffsets-r16
OPTIONAL, \-- Need M

sl-Scaling-r16 ENUMERATED {f0p5, f0p65, f0p8, f1} OPTIONAL, \-- Need M

\...

}

SL-PSFCH-Config-r16 ::= SEQUENCE {

sl-PSFCH-Period-r16 ENUMERATED {sl0, sl1, sl2, sl4} OPTIONAL, \-- Need M

sl-PSFCH-RB-Set-r16 BIT STRING (SIZE (10..275)) OPTIONAL, \-- Need M

sl-NumMuxCS-Pair-r16 ENUMERATED {n1, n2, n3, n6} OPTIONAL, \-- Need M

sl-MinTimeGapPSFCH-r16 ENUMERATED {sl2, sl3} OPTIONAL, \-- Need M

sl-PSFCH-HopID-r16 INTEGER (0..1023) OPTIONAL, \-- Need M

sl-PSFCH-CandidateResourceType-r16 ENUMERATED {startSubCH, allocSubCH}
OPTIONAL, \-- Need M

\...

}

SL-PTRS-Config-r16 ::= SEQUENCE {

sl-PTRS-FreqDensity-r16 SEQUENCE (SIZE (2)) OF INTEGER (1..276)
OPTIONAL, \-- Need M

sl-PTRS-TimeDensity-r16 SEQUENCE (SIZE (3)) OF INTEGER (0..29) OPTIONAL,
\-- Need M

sl-PTRS-RE-Offset-r16 ENUMERATED {offset01, offset10, offset11}
OPTIONAL, \-- Need M

\...

}

SL-UE-SelectedConfigRP-r16 ::= SEQUENCE {

sl-CBR-PriorityTxConfigList-r16 SL-CBR-PriorityTxConfigList-r16
OPTIONAL, \-- Need M

sl-Thres-RSRP-List-r16 SL-Thres-RSRP-List-r16 OPTIONAL, \-- Need M

sl-MultiReserveResource-r16 ENUMERATED {enabled} OPTIONAL, \-- Need M

sl-MaxNumPerReserve-r16 ENUMERATED {n2, n3} OPTIONAL, \-- Need M

sl-SensingWindow-r16 ENUMERATED {ms100, ms1100} OPTIONAL, \-- Need M

sl-SelectionWindowList-r16 SL-SelectionWindowList-r16 OPTIONAL, \-- Need
M

sl-ResourceReservePeriodList-r16 SEQUENCE (SIZE (1..16)) OF
SL-ResourceReservePeriod-r16 OPTIONAL, \-- Need M

sl-RS-ForSensing-r16 ENUMERATED {pscch, pssch},

\...,

\[\[

sl-CBR-PriorityTxConfigList-v1650 SL-CBR-PriorityTxConfigList-v1650
OPTIONAL \-- Need M

\]\],

\[\[

sl-NRPSSCH-EUTRA-ThresRSRP-List-r18 SL-Thres-RSRP-List-r16 OPTIONAL, \--
Need S

sl-NRPSFCH-EUTRA-ThresRSRP-List-r18 SL-Thres-RSRP-List-r16 OPTIONAL \--
Need S

\]\]

}

SL-ResourceReservePeriod-r16 ::= CHOICE {

sl-ResourceReservePeriod1-r16 ENUMERATED {ms0, ms100, ms200, ms300,
ms400, ms500, ms600, ms700, ms800, ms900, ms1000},

sl-ResourceReservePeriod2-r16 INTEGER (1..99)

}

SL-SelectionWindowList-r16 ::= SEQUENCE (SIZE (8)) OF
SL-SelectionWindowConfig-r16

SL-SelectionWindowConfig-r16 ::= SEQUENCE {

sl-Priority-r16 INTEGER (1..8),

sl-SelectionWindow-r16 ENUMERATED {n1, n5, n10, n20}

}

SL-TxPercentageList-r16 ::= SEQUENCE (SIZE (8)) OF
SL-TxPercentageConfig-r16

SL-TxPercentageConfig-r16 ::= SEQUENCE {

sl-Priority-r16 INTEGER (1..8),

sl-TxPercentage-r16 ENUMERATED {p20, p35, p50}

}

SL-MinMaxMCS-List-r16 ::= SEQUENCE (SIZE (1..3)) OF
SL-MinMaxMCS-Config-r16

SL-MinMaxMCS-Config-r16 ::= SEQUENCE {

sl-MCS-Table-r16 ENUMERATED {qam64, qam256, qam64LowSE},

sl-MinMCS-PSSCH-r16 INTEGER (0..27),

sl-MaxMCS-PSSCH-r16 INTEGER (0..31)

}

SL-BetaOffsets-r16 ::= INTEGER (0..31)

SL-PowerControl-r16 ::= SEQUENCE {

sl-MaxTransPower-r16 INTEGER (-30..33),

sl-Alpha-PSSCH-PSCCH-r16 ENUMERATED {alpha0, alpha04, alpha05, alpha06,
alpha07, alpha08, alpha09, alpha1} OPTIONAL, \-- Need M

dl-Alpha-PSSCH-PSCCH-r16 ENUMERATED {alpha0, alpha04, alpha05, alpha06,
alpha07, alpha08, alpha09, alpha1} OPTIONAL, \-- Need S

sl-P0-PSSCH-PSCCH-r16 INTEGER (-16..15) OPTIONAL, \-- Need S

dl-P0-PSSCH-PSCCH-r16 INTEGER (-16..15) OPTIONAL, \-- Need M

dl-Alpha-PSFCH-r16 ENUMERATED {alpha0, alpha04, alpha05, alpha06,
alpha07, alpha08, alpha09, alpha1} OPTIONAL, \-- Need S

dl-P0-PSFCH-r16 INTEGER (-16..15) OPTIONAL, \-- Need M

\...,

\[\[

dl-P0-PSSCH-PSCCH-r17 INTEGER (-202..24) OPTIONAL, \-- Need M

sl-P0-PSSCH-PSCCH-r17 INTEGER (-202..24) OPTIONAL, \-- Need S

dl-P0-PSFCH-r17 INTEGER (-202..24) OPTIONAL \-- Need M

\]\]

}

SL-PRS-ResourceSharedSL-PRS-RP-r18::= SEQUENCE {

sl-PRS-ResourceID-r18 INTEGER (0..16),

mNumberOfSymbols-r18 INTEGER (1..9),

sl-PRS-CombSizeN-AndReOffset-r18 CHOICE {

n2-r18 INTEGER (0..1),

n4-r18 INTEGER (0..3),

dummy1 INTEGER (0..5),

\...

} OPTIONAL \-- Need M

}

\-- TAG-SL-RESOURCEPOOL-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-ZoneConfigMCR* field descriptions                                 |
+-----------------------------------------------------------------------+
| ***sl-TransRange***                                                   |
|                                                                       |
| Indicates the communication range requirement for the corresponding   |
| *sl-ZoneConfigMCR-Index*. The unit is meter.                          |
+-----------------------------------------------------------------------+
| ***sl-ZoneConfig***                                                   |
|                                                                       |
| Indicates the zone configuration for the corresponding                |
| *sl-ZoneConfigMCR-Index*.                                             |
+-----------------------------------------------------------------------+
| ***sl-ZoneConfigMCR-Index***                                          |
|                                                                       |
| Indicates the codepoint of the communication range requirement field  |
| in SCI.                                                               |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-ResourcePool* field descriptions                                  |
+=======================================================================+
| ***dummy, dummy1***                                                   |
|                                                                       |
| This field is not used in the specification. If received it shall be  |
| ignored by the UE.                                                    |
+-----------------------------------------------------------------------+
| ***numSym-SL-PRS-2ndStageSCI***                                       |
|                                                                       |
| Indicates the number symbols to be assumed for SL PRS in determining  |
| the number of coded modulation symbols for second stage SCI in a slot |
| of a shared SL PRS resource pool.                                     |
+-----------------------------------------------------------------------+
| ***sl-A2X-Service***                                                  |
|                                                                       |
| Presence of this field indicates the resource pool is dedicated for   |
| A2X service, i.e., not to be used for other than A2X service. Value   |
| *brid* indicates the resource pool is for BRID, value *daa* indicates |
| the resource pool is for DAA, and value *bridAndDAA* indicates the    |
| resource pool is for both BRID and DAA. If this field is absent in    |
| all the configured resource pools, the UE may choose non-dedicated    |
| resource pool for A2X service.                                        |
+-----------------------------------------------------------------------+
| ***sl-Additional-MCS-Table***                                         |
|                                                                       |
| Indicates the MCS table(s) additionally used in the resource pool.    |
| 64QAM table is (pre-)configured as default. Zero, one or two can be   |
| additionally (pre-)configured using the 256QAM and/or low-SE MCS      |
| tables. If two MCS tables are indicated, 256QAM MCS table is the      |
| 1^st^ table and qam64lowSE MCS table is the 2^nd^ table as specified  |
| in TS 38.214 \[19\], clause 8.1.3.1.                                  |
+-----------------------------------------------------------------------+
| ***sl-CPE-StartingPositionsPSCCH-PSSCH-InitiateCOT-Default***         |
|                                                                       |
| Indicates CPE starting position index for the default CPE starting    |
| position, to be used for PSCCH/PSSCH transmission when UE initiating  |
| a COT.                                                                |
+-----------------------------------------------------------------------+
| ***sl-CPE-StartingPositionsPSCCH-PSSCH-InitiateCOT-List***            |
|                                                                       |
| Indicates a set of selected indices that correspond to multiple       |
| candidate CPE starting positions to be used for PSCCH/PSSCH           |
| transmission when UE initiating a COT, associated per L1 priority of  |
| PSSCH.                                                                |
+-----------------------------------------------------------------------+
| ***sl-CPE-StartingPositionsPSCCH-PSSCH-WithinCOT-Default***           |
|                                                                       |
| Indicates CPE starting position index for the default CPE starting    |
| position, to be used by UE for PSCCH/PSSCH transmission within a COT. |
+-----------------------------------------------------------------------+
| ***sl-CPE-StartingPositionsPSCCH-PSSCH-WithinCOT-List***              |
|                                                                       |
| Indicates a set of one or multiple selected indices that correspond   |
| to one or multiple candidate CPE starting positions to be used by UE  |
| for PSCCH/PSSCH transmission within a COT, associated per L1 priority |
| of PSSCH.                                                             |
+-----------------------------------------------------------------------+
| ***sl-CPE-StartingPositionPSFCH***                                    |
|                                                                       |
| Indicates CPE starting position within the GP symbol before PSFCH     |
| transmission. The value is an index of the set of all candidate CPE   |
| starting positions specified in Table 5.3.1-3 of \[16, TS38.211\] for |
| Ci=1 and the corresponding SCS of the SL BWP.                         |
+-----------------------------------------------------------------------+
| ***sl-FilterCoefficient***                                            |
|                                                                       |
| This field indicates the filtering coefficient for long-term          |
| measurement and reference signal power derivation used for sidelink   |
| open-loop power control.                                              |
+-----------------------------------------------------------------------+
| ***sl-InterUE-CoordinationConfig***                                   |
|                                                                       |
| Indicates the configured sidelink inter-UE coordination parameters.   |
+-----------------------------------------------------------------------+
| ***sl-IUC-RB-SetList***                                               |
|                                                                       |
| The n-th value in the list indicates the set of PRBs of n-th PSFCH    |
| occasion that are actually used for inter-UE coordination information |
| transmission and reception in Scheme 2. It shall be (pre-)configured  |
| such that N candidate PSFCH occasion(s) are associated with N         |
| different PRB sets. PRBs within intra-cell guard band are not used    |
| for PSFCH transmission. The length of this list is aligned with       |
| *sl-NumPSFCH-Occasions*. For each PSFCH occasion, the set of PRBs are |
| indicated in the same format as in *sl-PSFCH-RB-Set*.                 |
+-----------------------------------------------------------------------+
| ***sl-NumDedicatedPRBs-ForPSFCH***                                    |
|                                                                       |
| Indicates the value of K3 when each PSFCH transmission occupies \"1   |
| common interlace and K3 dedicated PRB(s)\" (as indicated by           |
| *sl-TransmissionStructureForPSFCH*). Value prb1 corresponds to K3=1,  |
| value prb2 corresponds to K3=2, and so on. UE expects the same        |
| (pre-)configured value of *sl-NumDedicatedPRBs-ForPSFCH* across all   |
| resource pools.                                                       |
+-----------------------------------------------------------------------+
| ***sl-NumInterlacePerSubchannel***                                    |
|                                                                       |
| Indicates the number of (K) interlaces per sub-channel within a       |
| resource pool. Value *sc1* corresponds to 1 interlace per             |
| sub-channel, and value *sc2* corresponds to 2 interlaces per          |
| sub-channel. The applicable values are related to the subcarrier      |
| spacing as below:                                                     |
|                                                                       |
| For SCS = 15 kHz: K=1 or 2                                            |
|                                                                       |
| For SCS = 30 kHz: K=1                                                 |
+-----------------------------------------------------------------------+
| ***sl-NumPSFCH-Occasions***                                           |
|                                                                       |
| Indicates one PSCCH/PSSCH transmission has N associated candidate     |
| PSFCH occasion(s). Value *o1* corresponds to N=1, value *o2*          |
| corresponds to N=2, and so on. If the field is not configured, the UE |
| shall use value *o1*.                                                 |
+-----------------------------------------------------------------------+
| ***sl-NumReferencePRBs-OfInterlace***                                 |
|                                                                       |
| Indicate reference number of PRBs of one interlace within 1 RB set.   |
| Value *prb10* corresponds to 10 PRBs, and value *prb11* corresponds   |
| to 11 PRBs.                                                           |
+-----------------------------------------------------------------------+
| ***sl-NumRefSymbolLength***                                           |
|                                                                       |
| Indicates a reference number of symbols for TBS determination.        |
+-----------------------------------------------------------------------+
| ***sl-NumSubchannel***                                                |
|                                                                       |
| Indicates the number of subchannels in the corresponding resource     |
| pool, which consists of contiguous PRBs only.                         |
+-----------------------------------------------------------------------+
| ***sl-PBPS-CPS-Config***                                              |
|                                                                       |
| Indicates the allowed resource allocation schemes of full sensing     |
| only, partial sensing only, random resource selection only, or any    |
| combination(s), and the related configuration for power saving        |
| resource allocation schemes. This field is absent for                 |
| *sl-TxPoolExceptional*.                                               |
+-----------------------------------------------------------------------+
| ***sl-PreemptionEnable***                                             |
|                                                                       |
| Indicates whether pre-emption is disabled or enabled in a resource    |
| pool. If the field is present and the value is *pl1*, *pl2*, and so   |
| on (but not *enabled*), it means that pre-emption is enabled and a    |
| priority level p_preemption is configured. If the field is present    |
| and the value is *enabled*, the pre-emption is enabled (but           |
| p_preemption is not configured) and pre-emption is applicable to all  |
| levels.                                                               |
+-----------------------------------------------------------------------+
| ***sl-PriorityThreshold-UL-URLLC***                                   |
|                                                                       |
| Indicates the threshold used to determine whether NR sidelink         |
| transmission is prioritized over uplink transmission of priority      |
| index 1 as specified in TS 38.213\[13\], clause 16.2.4.3, or whether  |
| PUCCH transmission carrying SL HARQ is prioritized over PUCCH         |
| transmission carrying UCI of priority index 1 if they overlap in time |
| as specified in TS 38.213 \[13\], clause 9.2.5.0.                     |
+-----------------------------------------------------------------------+
| ***sl-PriorityThreshold***                                            |
|                                                                       |
| Indicates the threshold used to determine whether NR sidelink         |
| transmission is prioritized over uplink transmission of priority      |
| index 0 as specified in TS 38.213\[13\], clause 16.2.4.3, or whether  |
| PUCCH transmission carrying SL HARQ is prioritized over PUCCH         |
| transmission carrying UCI of priority index 0 if they overlap in time |
| as specified in TS 38.213 \[13\], clause 9.2.5.0.                     |
+-----------------------------------------------------------------------+
| ***sl-PRS-ResourcesSharedSL-PRS-RP***                                 |
|                                                                       |
| Indicates SL PRS resources in a slot of shared SL PRS resource pool   |
| as defined in TS 38.211 \[16\]. The UE can use the resource pool to   |
| transmit or receive SL-PRS only if this field is present.             |
+-----------------------------------------------------------------------+
| ***sl-PSFCH-CommonInterlaceIndex***                                   |
|                                                                       |
| Indicate the index of common interlace to meet OCB requirements when  |
| *transmissionStructureForPSFCH* is set to common interlace. Value 0   |
| corresponds to interlace 0 is used as common interlace, value 1       |
| corresponds to interlace 1 is used as common interlace and so on.     |
+-----------------------------------------------------------------------+
| ***sl-PSFCH-PowerOffset***                                            |
|                                                                       |
| Indicates the power offset between Tx power on one common PRB         |
| (P_common) and Tx power on one dedicated PRB (P_dedicated) when       |
| *sl-TransmissionStructureForPSFCH* is (pre-)configured as             |
| *commonInterlace*, i.e., P_common = P_dedicated - offset. UE expects  |
| the same (pre-)configured value of *sl-PSFCH-PowerOffset* across all  |
| resource pools. The unit is dB.                                       |
+-----------------------------------------------------------------------+
| ***sl-PSFCH-RB-SetList***                                             |
|                                                                       |
| The n-th value in the list indicates the set of PRBs that are         |
| actually used for PSFCH transmission and reception of n-th PSFCH      |
| occasion of a PSCCH/PSSCH transmission.                               |
|                                                                       |
| It shall be (pre-)configured such that N candidate PSFCH occasion(s)  |
| are associated with N different PRB sets. PRBs within intra-cell      |
| guard band are not used for PSFCH transmission. The length of this    |
| list is aligned with *sl-NumPSFCH-Occasions*. For each PSFCH          |
| occasion, the set of PRBs are indicated in the same format as in      |
| *sl-PSFCH-RB-Set*.                                                    |
+-----------------------------------------------------------------------+
| ***sl-RB-Number***                                                    |
|                                                                       |
| Indicates the number of PRBs in the corresponding resource pool,      |
| which consists of contiguous PRBs only. The remaining RB cannot be    |
| used (See TS 38.214\[19\], clause 8).                                 |
+-----------------------------------------------------------------------+
| ***sl-RBSetIndexOfResourcePool***                                     |
|                                                                       |
| For interlace RB based PSCCH/PSSCH, indicates the RB set index(s)     |
| included in the resource pool. Contiguous RB sets are                 |
| (pre-)configured for a resource pool.                                 |
+-----------------------------------------------------------------------+
| ***sl-SCI-basedSL-PRS-TxTriggerSCI2-D***                              |
|                                                                       |
| Indicates presence of a bit-field in SCI format 2-D to trigger SL-PRS |
| transmission by a receiving UE.                                       |
+-----------------------------------------------------------------------+
| ***sl-StartRB-Subchannel***                                           |
|                                                                       |
| Indicates the lowest RB index of the subchannel with the lowest index |
| in the resource pool with respect to the lowest RB index of a SL BWP. |
+-----------------------------------------------------------------------+
| ***sl-SubchannelSize***                                               |
|                                                                       |
| Indicates the minimum granularity in frequency domain for the sensing |
| for PSSCH resource selection in the unit of PRB.                      |
+-----------------------------------------------------------------------+
| ***sl-SyncAllowed***                                                  |
|                                                                       |
| Indicates the allowed synchronization reference(s) which is (are)     |
| allowed to use the configured resource pool.                          |
+-----------------------------------------------------------------------+
| ***sl-SyncConfigIndex***                                              |
|                                                                       |
| Indicates the synchronisation configuration that is associated with a |
| reception pool, by means of an index to the corresponding entry       |
| *SL-SyncConfigList* of in *SIB12* for NR sidelink communication.      |
+-----------------------------------------------------------------------+
| ***sl-TDD-Configuration***                                            |
|                                                                       |
| Indicates the TDD configuration associated with the reception pool of |
| the cell indicated by *sl-SyncConfigIndex*.                           |
+-----------------------------------------------------------------------+
| ***sl-ThreshS-RSSI-CBR***                                             |
|                                                                       |
| Indicates the S-RSSI threshold for determining the contribution of a  |
| sub-channel to the CBR measurement. Value 0 corresponds to -112 dBm,  |
| value 1 to -110 dBm, value n to (-112 + n\*2) dBm, and so on.         |
+-----------------------------------------------------------------------+
| ***sl-TimeResource***                                                 |
|                                                                       |
| Indicates the bitmap of the resource pool, which is defined by        |
| repeating the bitmap with a periodicity during a SFN or DFN cycle.    |
+-----------------------------------------------------------------------+
| ***sl-TimeWindowSizeCBR***                                            |
|                                                                       |
| Indicates the time window size for CBR measurement.                   |
+-----------------------------------------------------------------------+
| ***sl-TimeWindowSizeCR***                                             |
|                                                                       |
| Indicates the time window size for CR evaluation.                     |
+-----------------------------------------------------------------------+
| ***sl-TransmissionStructureForPSFCH***                                |
|                                                                       |
| Indicate each PSFCH transmission occupies \"1 common interlace and K3 |
| dedicated PRB(s)\", or \"1 dedicated interlace\". Value               |
| *commonInterlace* corresponds to \"1 common interlace and K3          |
| dedicated PRB(s)\", and value *dedicatedInterlace* corresponds to \"1 |
| dedicated interlace\". UE expects the same (pre-)configured value of  |
| *transmissionStructureForPSFCH* across all resource pools.            |
+-----------------------------------------------------------------------+
| ***sl-TxPercentageList***                                             |
|                                                                       |
| Indicates the portion of candidate single-slot PSSCH resources over   |
| the total resources. Value p20 corresponds to 20%, and so on.         |
+-----------------------------------------------------------------------+
| ***sl-Type1-LBT-BlockingOption1***                                    |
|                                                                       |
| Indicates UE may avoid selection of N consecutive resource(s) before  |
| a reserved resource of another UE when the L1 SL priority value for   |
| the transmission is higher than the L1 SL priority value of the       |
| reserved resource, and UE may also avoid selection of M consecutive   |
| resource(s) after a reserved resource of another UE when the          |
| transmitting symbols of the reserved resource overlap with LBT of the |
| selected resource. The selection of the value N is up to UE           |
| implementation from {0, 1, 2}. M is determined based on UE            |
| implementation (at least including 0).                                |
+-----------------------------------------------------------------------+
| ***sl-Type1-LBT-BlockingOption2***                                    |
|                                                                       |
| Indicates UE may prioritize/select resource(s) in the slot(s) for     |
| transmission, if UE\'s transmission in slot(s) before a reserved      |
| resource is able to share its initiated COT to the reservation.       |
+-----------------------------------------------------------------------+
| ***sl-X-Overhead***                                                   |
|                                                                       |
| Accounts for overhead from CSI-RS, PT-RS. If the field is absent, the |
| UE applies value *n0* (see TS 38.214 \[19\], clause 8.1.3.2).         |
+-----------------------------------------------------------------------+

+-----------------------------------------------------------------------+
| *SL-SyncAllowed* field descriptions                                   |
+-----------------------------------------------------------------------+
| ***gnbEnb-Sync***                                                     |
|                                                                       |
| If configured, the (pre-) configured resources can be used if the UE  |
| is directly or indirectly synchronized to eNB or gNB (i.e.,           |
| synchronized to a reference UE which is directly synchronized to eNB  |
| or gNB).                                                              |
+-----------------------------------------------------------------------+
| ***gnss-Sync***                                                       |
|                                                                       |
| If configured, the (pre-) configured resources can be used if the UE  |
| is directly or indirectly synchronized to GNSS (i.e., synchronized to |
| a reference UE which is directly synchronized to GNSS).               |
+-----------------------------------------------------------------------+
| ***ue-Sync***                                                         |
|                                                                       |
| If configured, the (pre-) configured resources can be used if the UE  |
| is synchronized to a reference UE which is not synchronized to eNB,   |
| gNB and GNSS directly or indirectly.                                  |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-PSCCH-Config* field descriptions                                  |
+-----------------------------------------------------------------------+
| ***sl-FreqResourcePSCCH***                                            |
|                                                                       |
| Indicates the number of PRBs for PSCCH in a resource pool where it is |
| not greater than the number PRBs of the subchannel.                   |
+-----------------------------------------------------------------------+
| ***sl-DMRS-ScrambleID***                                              |
|                                                                       |
| Indicates the initialization value for PSCCH DMRS scrambling.         |
+-----------------------------------------------------------------------+
| ***sl-NumReservedBits***                                              |
|                                                                       |
| Indicates the number of reserved bits in first stage SCI.             |
+-----------------------------------------------------------------------+
| ***sl-TimeResourcePSCCH***                                            |
|                                                                       |
| Indicates the number of symbols of PSCCH in a resource pool.          |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-PSSCH-Config* field descriptions                                  |
+-----------------------------------------------------------------------+
| ***sl-BetaOffsets2ndSCI***                                            |
|                                                                       |
| Indicates candidates of beta-offset values to determine the number of |
| coded modulation symbols for second stage SCI. The value indicates    |
| the index of Table 9.3-2 of TS 38.213 \[13\].                         |
+-----------------------------------------------------------------------+
| ***sl-PSSCH-DMRS-TimePatternList***                                   |
|                                                                       |
| Indicates the set of PSSCH DMRS time domain patterns in terms of      |
| PSSCH DMRS symbols in a slot that can be used in the resource pool.   |
+-----------------------------------------------------------------------+
| ***sl-Scaling***                                                      |
|                                                                       |
| Indicates a scaling factor to limit the number of resource elements   |
| assigned to the second stage SCI on PSSCH. Value *f0p5* corresponds   |
| to 0.5, value *f0p65* corresponds to 0.65, and so on.                 |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-PSFCH-Config* field descriptions                                  |
+-----------------------------------------------------------------------+
| ***sl-MinTimeGapPSFCH***                                              |
|                                                                       |
| The minimum time gap between PSFCH and the associated PSSCH in the    |
| unit of slots.                                                        |
+-----------------------------------------------------------------------+
| ***sl-NumMuxCS-Pair***                                                |
|                                                                       |
| Indicates the number of cyclic shift pairs used for a PSFCH           |
| transmission that can be multiplexed in a PRB.                        |
+-----------------------------------------------------------------------+
| ***sl-PSFCH-CandidateResourceType***                                  |
|                                                                       |
| Indicates the number of PSFCH resources available for multiplexing    |
| HARQ-ACK information in a PSFCH transmission (see TS 38.213 \[13\],   |
| clause 16.3).                                                         |
+-----------------------------------------------------------------------+
| ***sl-PSFCH-HopID***                                                  |
|                                                                       |
| Scrambling ID for sequence hopping of the PSFCH used in the resource  |
| pool.                                                                 |
+-----------------------------------------------------------------------+
| ***sl-PSFCH-Period***                                                 |
|                                                                       |
| Indicates the period of PSFCH resource in the unit of slots within    |
| this resource pool. If set to *sl0*, no resource for PSFCH, and HARQ  |
| feedback for all transmissions in the resource pool is disabled.      |
+-----------------------------------------------------------------------+
| ***sl-PSFCH-RB-Set***                                                 |
|                                                                       |
| Indicates the set of PRBs that are actually used for PSFCH            |
| transmission and reception. The leftmost bit of the bitmap refers to  |
| the lowest RB index in the resource pool, and so on. Value 0 in the   |
| bitmap indicates that the corresponding PRB is not used for PSFCH     |
| transmission and reception while value 1 indicates that the           |
| corresponding PRB is used for PSFCH transmission and reception (see   |
| TS 38.213 \[13\]).                                                    |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-PRS-ResourceSharedSL-PRS-RP* field descriptions                   |
+-----------------------------------------------------------------------+
| ***mNumberOfSymbols***                                                |
|                                                                       |
| Indicates the number of symbols in the SL PRS resource in the shared  |
| resource pool. The maximum value that is configured for this field is |
| 4.                                                                    |
+-----------------------------------------------------------------------+
| ***sl-PRS-CombSizeN-AndReOffset***                                    |
|                                                                       |
| Indicates a comb offset and a comb size of the SL PRS resource in a   |
| shared SL PRS resource pool (see TS 38.214 \[19\], clause 8.2.4).     |
+-----------------------------------------------------------------------+
| ***sl-PRS-ResourceID***                                               |
|                                                                       |
| Indicates the index of the SL PRS resource in shared resource pool.   |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-PTRS-Config* field descriptions                                   |
+-----------------------------------------------------------------------+
| ***sl-PTRS-FreqDensity***                                             |
|                                                                       |
| Presence and frequency density of SL PT-RS as a function of scheduled |
| BW. If the field is not configured, the UE uses K_PT-RS = 2           |
+-----------------------------------------------------------------------+
| ***sl-PTRS-TimeDensity***                                             |
|                                                                       |
| Presence and time density of SL PT-RS as a function of MCS. If the    |
| field is not configured, the UE uses L_PT-RS = 1                      |
+-----------------------------------------------------------------------+
| ***sl-PTRS-RE-Offset***                                               |
|                                                                       |
| Indicates the subcarrier offset for SL PT-RS . If the field is not    |
| configured, the UE applies the value *offset00* (see TS 38.211        |
| \[16\], clause 8.4.1.2.2).                                            |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-UE-SelectedConfigRP* field descriptions                           |
+-----------------------------------------------------------------------+
| ***sl-CBR-PriorityTxConfigList***                                     |
|                                                                       |
| Indicates the mapping between PSSCH transmission parameter (such as   |
| MCS, PRB number, retransmission number, CR limit) sets by using the   |
| indexes of the configurations in *sl-CBR-PSSCH-TxConfigList*, CBR     |
| ranges by using the indexes to the entry of the CBR range             |
| configurations in *sl-CBR-RangeConfigList*, and priority ranges. It   |
| also indicates the default PSSCH transmission parameters to be used   |
| when CBR measurement results are not available, and MCS range for the |
| MCS tables used in the resource pool. The field                       |
| *sl-CBR-PriorityTxConfigList-v1650* is present only when              |
| *sl-CBR-PriorityTxConfigList-r16* is configured.                      |
+-----------------------------------------------------------------------+
| ***sl-MaxNumPerReserve***                                             |
|                                                                       |
| Indicates the maximum number of reserved PSCCH/PSSCH resources that   |
| can be indicated by an SCI.                                           |
+-----------------------------------------------------------------------+
| ***sl-MultiReserveResource***                                         |
|                                                                       |
| Indicates if it is allowed to reserve a sidelink resource for an      |
| initial transmission of a TB by an SCI associated with a different    |
| TB, based on sensing and resource selection procedure.                |
+-----------------------------------------------------------------------+
| ***sl-NRPSFCH-EUTRA-ThresRSRP-List***                                 |
|                                                                       |
| Indicates a list of 64 thresholds from which a threshold should be    |
| selected based on the priority in the decoded EUTRA SCI and the       |
| priority in the NR SCI to be transmitted. A NR SL resource is         |
| excluded if the corresponding PSFCH transmission occasions overlap    |
| with resources indicated or reserved by the decoded EUTRA SCI in time |
| domain and EUTRA PSSCH RSRP in the associated data resource is above  |
| the threshold.                                                        |
+-----------------------------------------------------------------------+
| ***sl-NRPSSCH-EUTRA-ThresRSRP-List***                                 |
|                                                                       |
| Indicates a list of 64 thresholds, and a threshold should be selected |
| based on the priority in the decoded EUTRA SCI and the priority in    |
| the NR SCI to be transmitted. A NR SL resource is excluded if it is   |
| indicated or reserved by the decoded EUTRA SCI and EUTRA PSSCH RSRP   |
| in the associated data resource is above the threshold. If the field  |
| is present, the UE shall perform the dynamic co-channel coexistence   |
| of LTE sidelink and NR sidelink as specified in TS 38.214; otherwise  |
| it shall not perform it.                                              |
+-----------------------------------------------------------------------+
| ***sl-ResourceReservePeriodList***                                    |
|                                                                       |
| Set of possible resource reservation period allowed in the resource   |
| pool in the unit of ms. Up to 16 values can be configured per         |
| resource pool. The value *ms0* is always configured.                  |
+-----------------------------------------------------------------------+
| ***sl-RS-ForSensing***                                                |
|                                                                       |
| Indicates whether DMRS of PSCCH or PSSCH is used for L1 RSRP          |
| measurement in the sensing operation.                                 |
+-----------------------------------------------------------------------+
| ***sl-SensingWindow***                                                |
|                                                                       |
| Parameter that indicates the start of the sensing window.             |
+-----------------------------------------------------------------------+
| ***sl-SelectionWindowList***                                          |
|                                                                       |
| Parameter that determines the end of the selection window in the      |
| resource selection for a TB with respect to priority indicated in     |
| SCI. Value n1 corresponds to 1\*2^µ^, value n5 corresponds to         |
| 5\*2^µ^, and so on, where µ = 0,1,2,3 refers to SCS 15,30,60,120 kHz  |
| respectively.                                                         |
+-----------------------------------------------------------------------+
| ***sl-Thres-RSRP-List***                                              |
|                                                                       |
| Indicates a list of 64 thresholds, and the threshold should be        |
| selected based on the priority in the decoded SCI and the priority in |
| the SCI to be transmitted. A resource is excluded if it is indicated  |
| or reserved by a decoded SCI and PSSCH/PSCCH RSRP in the associated   |
| data resource is above a threshold.                                   |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-PowerControl* field descriptions                                  |
+-----------------------------------------------------------------------+
| ***sl-MaxTransPower***                                                |
|                                                                       |
| Indicates the maximum value of the UE\'s sidelink transmission power  |
| on this resource pool when the sidelink transmission is performed     |
| only on this resource pool. The unit is dBm. If the sidelink          |
| transmission is PSFCH, and multiple resource pools are used, the      |
| maximum transmission power for PSFCH is configured as sum of fields   |
| *sl-maxTransPower* over multiple resource pools, as specified in TS   |
| 38.101-1 \[15\].                                                      |
+-----------------------------------------------------------------------+
| ***sl-Alpha-PSSCH-PSCCH***                                            |
|                                                                       |
| Indicates alpha value for sidelink pathloss based power control for   |
| PSCCH/PSSCH when *sl-P0-PSSCH-PSCCH* is configured. When the field is |
| absent the UE applies the value 1.                                    |
+-----------------------------------------------------------------------+
| ***sl-P0-PSSCH-PSCCH***                                               |
|                                                                       |
| Indicates P0 value for sidelink pathloss based power control for      |
| PSCCH/PSSCH. If not configured, sidelink pathloss based power control |
| is disabled for PSCCH/PSSCH. When *sl-P0-PSSCH-PSCCH-r17* is          |
| configured, the UE ignores *sl-P0-PSSCH-PSCCH-r16*.                   |
+-----------------------------------------------------------------------+
| ***dl-Alpha-PSSCH-PSCCH***                                            |
|                                                                       |
| Indicates alpha value for downlink pathloss based power control for   |
| PSCCH/PSSCH when *dl-P0-PSSCH-PSCCH* is configured. When the field is |
| absent the UE applies the value 1.                                    |
+-----------------------------------------------------------------------+
| ***dl-P0-PSSCH-PSCCH***                                               |
|                                                                       |
| Indicates P0 value for downlink pathloss based power control for      |
| PSCCH/PSSCH. If not configured, downlink pathloss based power control |
| is disabled for PSCCH/PSSCH. When *dl-P0-PSSCH-PSCCH-r17* is          |
| configured, the UE ignores *dl-P0-PSSCH-PSCCH-r16*.                   |
|                                                                       |
| A Remote UE which is out of coverage, considers downlink pathloss     |
| based power control is disabled for PSCCH/PSSCH when                  |
| *dl-P0-PSSCH-PSCCH* is configured.                                    |
+-----------------------------------------------------------------------+
| ***dl-Alpha-PSFCH***                                                  |
|                                                                       |
| Indicates alpha value for downlink pathloss based power control for   |
| PSFCH when *dl-P0-PSFCH* is configured. When the field is absent the  |
| UE applies the value 1. For resource pools configured with PSFCH      |
| resources overlapping in time, this field is either not configured in |
| any of the resource pools or configured with the same value for all   |
| the resource pools.                                                   |
+-----------------------------------------------------------------------+
| ***dl-P0-PSFCH***                                                     |
|                                                                       |
| Indicates P0 value for downlink pathloss based power control for      |
| PSFCH. If not configured, downlink pathloss based power control is    |
| disabled for PSFCH. When *dl-P0-PSFCH-r17* is configured, the UE      |
| ignores *dl-P0-PSFCH-r16.* For resource pools configured with PSFCH   |
| resources overlapping in time, this field is either not configured in |
| any of the resource pools or configured with the same value for all   |
| the resource pools.                                                   |
|                                                                       |
| A Remote UE which is out of coverage, considers downlink pathloss     |
| based power control is disabled for PSFCH when *dl-P0-PSFCH* is       |
| configured.                                                           |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-MinMaxMCS-Config* field descriptions                              |
+-----------------------------------------------------------------------+
| ***sl-MaxMCS-PSSCH***                                                 |
|                                                                       |
| Indicates the maximum MCS value when using the associated MCS table.  |
| If no MCS is configured, UE autonomously selects MCS from the full    |
| range of values.                                                      |
+-----------------------------------------------------------------------+
| ***sl-MinMCS-PSSCH***                                                 |
|                                                                       |
| Indicates the minimum MCS value when using the associated MCS table.  |
| If no MCS is configured, UE autonomously selects MCS from the full    |
| range of values.                                                      |
+=======================================================================+

+-----------------------------------------------------------------------+
| *SL-CPE-StartingPositionsPSCCH-PSSCH* field descriptions              |
+-----------------------------------------------------------------------+
| ***sl-Priority***                                                     |
|                                                                       |
| Indicates L1 priority of PSSCH.                                       |
+-----------------------------------------------------------------------+
| ***sl-CPE-StartingPositions***                                        |
|                                                                       |
| Indicates a set of candidate CPE starting positions specified in      |
| Table 5.3.1-3 \[16, TS38.211\],                                       |
+=======================================================================+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *A2X*                The field is mandatory present in
                       *sl-BWP-PoolConfigA2X* and
                       *sl-BWP-PoolConfigCommonA2X*; otherwise the field
                       is optionally present, Need M.

  -----------------------------------------------------------------------

#### -- *SL-RLC-BearerConfig*

The IE *SL-RLC-BearerConfig* specifies the SL RLC bearer configuration
information for NR sidelink communication.

*SL-RLC-BearerConfig* information element

\-- ASN1START

\-- TAG-SL-RLC-BEARERCONFIG-START

SL-RLC-BearerConfig-r16 ::= SEQUENCE {

sl-RLC-BearerConfigIndex-r16 SL-RLC-BearerConfigIndex-r16,

sl-ServedRadioBearer-r16 SLRB-Uu-ConfigIndex-r16 OPTIONAL, \-- Cond
LCH-SetupOnly

sl-RLC-Config-r16 SL-RLC-Config-r16 OPTIONAL, \-- Cond LCH-Setup

sl-MAC-LogicalChannelConfig-r16 SL-LogicalChannelConfig-r16 OPTIONAL,
\-- Cond LCH-Setup

\...,

\[\[

sl-RLC-BearerConfigIndex-v1800 SL-RLC-BearerConfigIndex-v1800 OPTIONAL
\-- Need R

\]\]

}

\-- TAG-SL-RLC-BEARERCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-RLC-BearerConfig* field descriptions                              |
+-----------------------------------------------------------------------+
| ***sl-MAC-LogicalChannelConfig***                                     |
|                                                                       |
| The field is used to configure MAC SL logical channel parameters.     |
+-----------------------------------------------------------------------+
| ***sl-RLC-BearerConfigIndex***                                        |
|                                                                       |
| The index of the RLC bearer configuration. If the field               |
| *sl-RLC-BearerConfigIndex-v1800* is present, the UE shall ignore the  |
| *sl-RLC-BearerConfigIndex-r16* field.                                 |
+-----------------------------------------------------------------------+
| ***sl-RLC-Config***                                                   |
|                                                                       |
| Determines the RLC mode (UM, AM) and provides corresponding           |
| parameters.                                                           |
+-----------------------------------------------------------------------+
| ***sl-ServedRadioBearer***                                            |
|                                                                       |
| Associates the sidelink RLC Bearer with a sidelink DRB. It indicates  |
| the index of SL radio bearer configuration, which is corresponding to |
| the RLC bearer configuration.                                         |
+=======================================================================+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *LCH-Setup*          The field is mandatory present upon creation of a
                       new sidelink logical channel via the dedicated
                       signalling and in case of sidelink DRB
                       configuration via system information and
                       pre-configuration; otherwise the field is
                       optionally present, Need M.

  *LCH-SetupOnly*      This field is mandatory present upon creation of a
                       new sidelink logical channel via the dedicated
                       signalling and in case of sidelink DRB
                       configuration via system information and
                       pre-configuration. Otherwise, it is absent, Need
                       M.
  -----------------------------------------------------------------------

#### -- *SL-RLC-BearerConfigIndex*

The IE *SL-RLC-BearerConfigIndex* is used to identify a SL RLC bearer
configuration.

*SL-RLC-BearerConfigIndex* information element

\-- ASN1START

\-- TAG-SL-RLC-BEARERCONFIGINDEX-START

SL-RLC-BearerConfigIndex-r16 ::= INTEGER (1..maxSL-LCID-r16)

SL-RLC-BearerConfigIndex-v1800 ::= INTEGER
(maxSL-LCID-Plus1-r18..maxSL-LCID-r18)

\-- TAG-RLC-BEARERCONFIGINDEX-STOP

\-- ASN1STOP

#### -- *SL-RLC-ChannelConfig*

The IE *SL-RLC-ChannelConfig* specifies the configuration information
for PC5 Relay RLC channel between L2 U2N Relay UE and L2 U2N Remote UE,
or between L2 U2U Remote UE and L2 U2U Relay UE.

*SL-RLC-ChannelConfig* information element

\-- ASN1START

\-- TAG-SL-RLC-RLC-CHANNEL-CONFIG-START

SL-RLC-ChannelConfig-r17 ::= SEQUENCE {

sl-RLC-ChannelID-r17 SL-RLC-ChannelID-r17,

sl-RLC-Config-r17 SL-RLC-Config-r16 OPTIONAL, \-- Need M

sl-MAC-LogicalChannelConfig-r17 SL-LogicalChannelConfig-r16 OPTIONAL,
\-- Need M

sl-PacketDelayBudget-r17 INTEGER (0..1023) OPTIONAL, \-- Need M

\...}

\-- TAG-SL-RLC-CHANNEL-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-RLC-ChannelConfig* field descriptions                             |
+=======================================================================+
| ***sl-MAC-LogicalChannelConfig***                                     |
|                                                                       |
| The field is used to configure MAC SL logical channel parameters.     |
+-----------------------------------------------------------------------+
| ***sl-RLC-ChannelID***                                                |
|                                                                       |
| Indicates the PC5 Relay RLC channel in the link between L2 U2N Relay  |
| UE and L2 U2N Remote UE, or between L2 U2U Remote UE and L2 U2U Relay |
| UE.                                                                   |
+-----------------------------------------------------------------------+
| ***sl-RLC-Config***                                                   |
|                                                                       |
| Determines the RLC mode (UM, AM) and provides corresponding           |
| parameters.                                                           |
+-----------------------------------------------------------------------+
| ***sl-PacketDelayBudget***                                            |
|                                                                       |
| Indicates the Packet Delay Budget for a PC5 Relay RLC channel used in |
| L2 U2N relay operation. Upper bound value for the delay that a packet |
| may experience expressed in unit of 0.5ms.                            |
+-----------------------------------------------------------------------+

#### -- *SL-RLC-ChannelID*

The IE *SL-RLC-ChannelID* is used to identify a PC5 Relay RLC channel in
the link between L2 U2N Relay UE and L2 U2N Remote UE, or between L2 U2U
Relay UE and L2 U2U Remote UE.

*SL-RLC-ChannelID* information element

\-- ASN1START

\-- TAG-SL-RLC-CHANNELID-START

SL-RLC-ChannelID-r17 ::= INTEGER (1..maxSL-LCID-r16)

\-- TAG-SL-RLC-CHANNELID-STOP

\-- ASN1STOP

#### -- *SL-RLC-Config*

The IE *SL-RLC-Config* is used to specify the RLC configuration of
sidelink DRB. RLC AM configuration is only applicable to the unicast NR
sidelink communication.

*SL-RLC-Config* information element

\-- ASN1START

\-- TAG-SL-RLC-CONFIG-START

SL-RLC-Config-r16 ::= CHOICE {

sl-AM-RLC-r16 SEQUENCE {

sl-SN-FieldLengthAM-r16 SN-FieldLengthAM OPTIONAL, \-- Cond SLRBSetup

sl-T-PollRetransmit-r16 T-PollRetransmit,

sl-PollPDU-r16 PollPDU,

sl-PollByte-r16 PollByte,

sl-MaxRetxThreshold-r16 ENUMERATED { t1, t2, t3, t4, t6, t8, t16, t32 },

\...

},

sl-UM-RLC-r16 SEQUENCE {

sl-SN-FieldLengthUM-r16 SN-FieldLengthUM OPTIONAL, \-- Cond SLRBSetup

\...

},

\...

}

\-- TAG-SL-RLC-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-RLC-Config* field descriptions                                    |
+-----------------------------------------------------------------------+
| ***sl-MaxRetxThreshold***                                             |
|                                                                       |
| Parameter value of *maxRetxThreshold* for RLC AM for NR sidelink      |
| communications, see TS 38.322 \[4\]. Value *t1* corresponds to 1      |
| retransmission, value *t2* corresponds to 2 retransmissions and so    |
| on.                                                                   |
+-----------------------------------------------------------------------+
| ***sl-PollByte***                                                     |
|                                                                       |
| Parameter value of *pollByte* for RLC AM for NR sidelink              |
| communications, see TS 38.322 \[4\]. Value *kB25* corresponds to 25   |
| kBytes, value *kB50* corresponds to 50 kBytes and so on. *infinity*   |
| corresponds to an infinite amount of kBytes.                          |
+-----------------------------------------------------------------------+
| ***sl-PollPDU***                                                      |
|                                                                       |
| Parameter value of *pollPDU* for RLC AM for NR sidelink               |
| communications, seeTS 38.322 \[4\]. Value *p4* corresponds to 4 PDUs, |
| value *p8* corresponds to 8 PDUs and so on. *infinity* corresponds to |
| an infinite number of PDUs.                                           |
+-----------------------------------------------------------------------+
| ***sl-SN-FieldLength***                                               |
|                                                                       |
| This field indicates the RLC SN field size for NR sidelink            |
| communication, see TS 38.322 \[4\]. For groupcast and broadcast, only |
| value *size6* (6 bits) is configured for the field                    |
| *sl-SN-FieldLengthUM*.                                                |
+-----------------------------------------------------------------------+
| ***sl-T-PollRetransmit***                                             |
|                                                                       |
| Timer value of *t-PollRetransmit* for RLC AM for NR sidelink          |
| communications, see TS 38.322 \[4\], in milliseconds. Value *ms5*     |
| means 5 ms, value *ms10* means 10 ms and so on.                       |
+=======================================================================+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *SLRBSetup*          The field is mandatory present in case of sidelink
                       DRB setup via the dedicated signalling and in case
                       of sidelink DRB configuration via system
                       information and pre-configuration; otherwise the
                       field is optionally present, need M.

  -----------------------------------------------------------------------

#### -- *SL-ScheduledConfig*

The IE *SL-ScheduledConfig* specifies sidelink communication/positioning
configurations used for network scheduled NR sidelink
communication/positioning.

*SL-ScheduledConfig* information element

\-- ASN1START

\-- TAG-SL-SCHEDULEDCONFIG-START

SL-ScheduledConfig-r16 ::= SEQUENCE {

sl-RNTI-r16 RNTI-Value,

mac-MainConfigSL-r16 MAC-MainConfigSL-r16 OPTIONAL, \-- Need M

sl-CS-RNTI-r16 RNTI-Value OPTIONAL, \-- Need M

sl-PSFCH-ToPUCCH-r16 SEQUENCE (SIZE (1..8)) OF INTEGER (0..15) OPTIONAL,
\-- Need M

sl-ConfiguredGrantConfigList-r16 SL-ConfiguredGrantConfigList-r16
OPTIONAL, \-- Need M

\...,

\[\[

sl-DCI-ToSL-Trans-r16 SEQUENCE (SIZE (1..8)) OF INTEGER (1..32) OPTIONAL
\-- Need M

\]\],

\[\[

sl-ConfiguredGrantConfigDedicated-SL-PRS-RP-List-r18
SL-ConfiguredGrantConfigDedicated-SL-PRS-RP-List-r18 OPTIONAL, \-- Need
M

sl-PRS-RNTI-r18 RNTI-Value OPTIONAL, \-- Need M

sl-PRS-CS-RNTI-r18 RNTI-Value OPTIONAL \-- Need M

\]\]

}

MAC-MainConfigSL-r16 ::= SEQUENCE {

sl-BSR-Config-r16 BSR-Config OPTIONAL, \-- Need M

ul-PrioritizationThres-r16 INTEGER (1..16) OPTIONAL, \-- Need M

sl-PrioritizationThres-r16 INTEGER (1..8) OPTIONAL, \-- Need M

\...

}

SL-ConfiguredGrantConfigList-r16 ::= SEQUENCE {

sl-ConfiguredGrantConfigToReleaseList-r16 SEQUENCE (SIZE
(1..maxNrofCG-SL-r16)) OF SL-ConfigIndexCG-r16 OPTIONAL, \-- Need N

sl-ConfiguredGrantConfigToAddModList-r16 SEQUENCE (SIZE
(1..maxNrofCG-SL-r16)) OF SL-ConfiguredGrantConfig-r16 OPTIONAL \-- Need
N

}

SL-ConfiguredGrantConfigDedicated-SL-PRS-RP-List-r18 ::= SEQUENCE {

sl-ConfiguredGrantConfigDedicated-SL-PRS-RPToReleaseList-r18 SEQUENCE
(SIZE (1..maxNrofCG-SL-r16)) OF SL-ConfigIndexCG-r16

OPTIONAL, \-- Need N

sl-ConfiguredGrantConfigDedicated-SL-PRS-RPToAddModList-r18

SEQUENCE (SIZE (1..maxNrofCG-SL-r16)) OF
SL-ConfiguredGrantConfigDedicatedSL-PRS-RP-r18 OPTIONAL \-- Need N

}

\-- TAG-SL-SCHEDULEDCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-ScheduledConfig* field descriptions                               |
+-----------------------------------------------------------------------+
| ***sl-CS-RNTI***                                                      |
|                                                                       |
| Indicate the RNTI used to scramble CRC of DCI format 3_0, see TS      |
| 38.321 \[3\].                                                         |
+-----------------------------------------------------------------------+
| ***sl-DCI-ToSL-Trans***                                               |
|                                                                       |
| Indicate the time gap between DCI reception and the first sidelink    |
| transmission scheduled by the DCI (see TS 38.214 \[19\], clause       |
| 8.1.2.1). Value 1 included in this field corresponds to 1 slot, value |
| 2 corresponds to 2 slots and so on, based on the numerology of        |
| sidelink BWP.                                                         |
+-----------------------------------------------------------------------+
| ***sl-PRS-CS-RNTI***                                                  |
|                                                                       |
| Indicates the RNTI used to scramble CRC of DCI format 3_2 for         |
| configured grants.                                                    |
+-----------------------------------------------------------------------+
| ***sl-PRS-RNTI***                                                     |
|                                                                       |
| Indicates the SL-PRS-RNTI used for monitoring the network scheduling  |
| to transmit NR sidelink positioning reference signal (i.e. the        |
| mode 1) for dynamic grants.                                           |
+-----------------------------------------------------------------------+
| ***sl-PSFCH-ToPUCCH***                                                |
|                                                                       |
| For dynamic grant and configured grant type 2, this field configures  |
| the values (in number of slot lengths) of the PSFCH to PUCCH gap. The |
| field PSFCH-to-HARQ_feedback timing indicator in DCI format 3_0       |
| selects one of the configured values of the PSFCH to PUCCH gap.       |
+-----------------------------------------------------------------------+
| ***sl-RNTI***                                                         |
|                                                                       |
| Indicate the SL-RNTI used for monitoring the network scheduling to    |
| transmit NR sidelink communication (i.e. the mode 1).                 |
+=======================================================================+

+-----------------------------------------------------------------------+
| *MAC-MainConfigSL* field descriptions                                 |
+-----------------------------------------------------------------------+
| ***sl-BSR-Config***                                                   |
|                                                                       |
| This field is to configure the sidelink buffer status report.         |
+-----------------------------------------------------------------------+
| ***sl-PrioritizationThres***                                          |
|                                                                       |
| Indicates the SL priority threshold, which is used to determine       |
| whether SL TX is prioritized over UL TX, as specified in TS 38.321    |
| \[3\]. Network does not configure the *sl-PrioritizationThres* and    |
| the *ul-PrioritizationThres* to the UE separately.                    |
+-----------------------------------------------------------------------+
| ***ul-PrioritizationThres***                                          |
|                                                                       |
| Indicates the UL priority threshold, which is used to determine       |
| whether SL TX is prioritized over UL TX, as specified in TS 38.321    |
| \[3\]. Network does not configure the *sl-PrioritizationThres* and    |
| the *ul-PrioritizationThres* to the UE separately.                    |
+=======================================================================+

#### -- *SL-SDAP-Config*

The IE *SL-SDAP-Config* is used to set the configurable SDAP parameters
for a Sidelink DRB.

*SL-SDAP-Config* information element

\-- ASN1START

\-- TAG-SL-SDAP-CONFIG-START

SL-SDAP-Config-r16 ::= SEQUENCE {

sl-SDAP-Header-r16 ENUMERATED {present, absent},

sl-DefaultRB-r16 BOOLEAN,

sl-MappedQoS-Flows-r16 CHOICE {

sl-MappedQoS-FlowsList-r16 SEQUENCE (SIZE (1..maxNrofSL-QFIs-r16)) OF
SL-QoS-Profile-r16,

sl-MappedQoS-FlowsListDedicated-r16 SL-MappedQoS-FlowsListDedicated-r16

} OPTIONAL, \-- Need M

sl-CastType-r16 ENUMERATED {broadcast, groupcast, unicast, spare1}
OPTIONAL, \-- Need M

\...

}

SL-MappedQoS-FlowsListDedicated-r16 ::= SEQUENCE {

sl-MappedQoS-FlowsToAddList-r16 SEQUENCE (SIZE (1..maxNrofSL-QFIs-r16))
OF SL-QoS-FlowIdentity-r16 OPTIONAL, \-- Need N

sl-MappedQoS-FlowsToReleaseList-r16 SEQUENCE (SIZE
(1..maxNrofSL-QFIs-r16)) OF SL-QoS-FlowIdentity-r16 OPTIONAL \-- Need N

}

\-- TAG-SL-SDAP-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-SDAP-Config* field descriptions                                   |
+=======================================================================+
| ***sl-DefaultRB***                                                    |
|                                                                       |
| Indicates whether or not this is the default sidelink DRB for this NR |
| sidelink communication transmission destination. Among all configured |
| instances of *SL-SDAP-Config* for this destination, this field shall  |
| be set to *true* in at most one instance of *SL-SDAP-Config* and to   |
| *false* in all other instances.                                       |
+-----------------------------------------------------------------------+
| ***sl-MappedQoS-Flows***                                              |
|                                                                       |
| Indicates QoS flows to be mapped to the sidelink DRB. If the field is |
| included in dedicated signalling, it is set to                        |
| *sl-MappedQoS-FlowsListDedicated*; otherwise, it is set to            |
| *sl-MappedQoS-FlowsList*.                                             |
+-----------------------------------------------------------------------+
| ***sl-MappedQoS-FlowsList***                                          |
|                                                                       |
| Indicates the list of QoS profiles of the NR sidelink communication   |
| transmission destination mapped to this sidelink DRB.                 |
+-----------------------------------------------------------------------+
| ***sl-MappedQoS-FlowsToAddList***                                     |
|                                                                       |
| Indicates the list of SL QoS flows ID of the NR sidelink              |
| communication transmission destination to be additionally mapped to   |
| this sidelink DRB.                                                    |
+-----------------------------------------------------------------------+
| ***sl-MappedQoS-FlowsToReleaseList***                                 |
|                                                                       |
| Indicates the list of SL QoS flows ID of the NR sidelink              |
| communication transmission destination to be released from existing   |
| QoS flow to SLRB mapping of this sidelink DRB.                        |
+-----------------------------------------------------------------------+
| ***sl-SDAP-Header***                                                  |
|                                                                       |
| Indicates whether or not a SDAP header is present on this sidelink    |
| DRB. The field cannot be changed after a sidelink DRB is established. |
| This field is set to present if the field *sl-DefaultRB* is set to    |
| *true*.                                                               |
+-----------------------------------------------------------------------+

#### -- *SL-ServingCellInfo*

The IE *SL-ServingCellInfo* is used to indicate the L2 U2N Relay UE\'s
PCell/camping cell, which is considered as PCell/camping cell by the L2
U2N Remote UEs connecting with this L2 U2N Relay UE.

*SL-ServingCellInfo* information element

\-- ASN1START

\-- TAG-SL-SERVINGCELLINFO-START

SL-ServingCellInfo-r17 ::= SEQUENCE {

sl-PhysCellId-r17 PhysCellId,

sl-CarrierFreqNR-r17 ARFCN-ValueNR

}

\-- TAG-SL-SERVINGCELLINFO-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-ServingCellInfo* field descriptions                               |
+-----------------------------------------------------------------------+
| ***sl-CarrierFreqNR***                                                |
|                                                                       |
| Indicates the DL frequency of the cell indicated by *sl-PhysCellId*.  |
+-----------------------------------------------------------------------+
| ***sl-PhysCellId***                                                   |
|                                                                       |
| Indicates the PCI of the PCell.                                       |
+=======================================================================+

#### -- *SL-SourceIdentity*

The IE *SL-SourceIdentity* is used to identify a source of a NR sidelink
communication.

***SL-SourceIdentity* information element**

\-- ASN1START

\-- TAG-SL-SOURCEIDENTITY-START

SL-SourceIdentity-r17 ::= BIT STRING (SIZE (24))

\-- TAG-SL-SOURCEIDENTITY-STOP

\-- ASN1STOP

#### -- *SL-SRAP-Config*

The IE *SL-SRAP-Config* is used to set the configurable SRAP parameters
used by L2 U2N Relay UE and L2 U2N Remote UE as specified in TS 38.351
\[66\].

***SL-SRAP-Config* information element**

\-- ASN1START

\-- TAG-SL-SRAP-CONFIG-START

SL-SRAP-Config-r17 ::= SEQUENCE {

sl-LocalIdentity-r17 INTEGER (0..255) OPTIONAL, \-- Need M

sl-MappingToAddModList-r17 SEQUENCE (SIZE (1..maxLC-ID)) OF
SL-MappingToAddMod-r17 OPTIONAL, \-- Need N

sl-MappingToReleaseList-r17 SEQUENCE (SIZE (1..maxLC-ID)) OF
SL-RemoteUE-RB-Identity-r17 OPTIONAL, \-- Need N

\...

}

SL-MappingToAddMod-r17 ::= SEQUENCE {

sl-RemoteUE-RB-Identity-r17 SL-RemoteUE-RB-Identity-r17,

sl-EgressRLC-ChannelUu-r17 Uu-RelayRLC-ChannelID-r17 OPTIONAL, \-- Cond
L2RelayUE

sl-EgressRLC-ChannelPC5-r17 SL-RLC-ChannelID-r17 OPTIONAL, \-- Need N

\...

}

SL-RemoteUE-RB-Identity-r17 ::= CHOICE {

srb-Identity-r17 INTEGER (0..3),

drb-Identity-r17 DRB-Identity,

\...

}

\-- TAG-SL-SRAP-CONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-SRAP-Config* field descriptions                                   |
+=======================================================================+
| ***sl-LocalIdentity***                                                |
|                                                                       |
| Indicates the local UE ID of the L2 U2N Remote UE used in SRAP as     |
| specified in TS 38.351 \[66\].                                        |
+-----------------------------------------------------------------------+
| ***sl-MappingToAddModList***                                          |
|                                                                       |
| Indicates the list of mappings between the bearer identity of the L2  |
| U2N Remote UE and the egress RLC channel as specified in TS 38.351    |
| \[66\] to be added or modified.                                       |
+-----------------------------------------------------------------------+
| ***sl-MappingToReleaseList***                                         |
|                                                                       |
| Indicates the list of mappings between the bearer identity of the L2  |
| U2N Remote UE and the egress RLC channel as specified in TS 38.351    |
| \[66\] to be released.                                                |
+-----------------------------------------------------------------------+
| ***sl-RemoteUE-RB-Identity***                                         |
|                                                                       |
| Identity of the end-to-end Uu bearer identity of the L2 U2N Remote    |
| UE. The value 3 for the field *srb-identity-r17* (i.e., for           |
| configuring SRB3) is not supported in this version of the             |
| specification.                                                        |
+-----------------------------------------------------------------------+
| ***sl-EgressRLC-ChannelUu***                                          |
|                                                                       |
| Indicates the egress RLC channel on Uu Hop for uplink transmissions   |
| at the L2 U2N Relay UE.                                               |
+-----------------------------------------------------------------------+
| ***sl-EgressRLC-ChannelPC5***                                         |
|                                                                       |
| Indicates the egress RLC channel on PC5 Hop for downlink              |
| transmissions at the L2 U2N Relay UE and for uplink transmissions at  |
| the L2 U2N Remote UE.                                                 |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *L2RelayUE*          For L2 U2N Relay UE, the field is optionally
                       present, Need M. Otherwise, it is absent.

  -----------------------------------------------------------------------

#### -- *SL-SRAP-ConfigU2U*

The IE *SL*-*SRAP-ConfigU2U* is used to set the configurable SRAP
parameters used by L2 U2U Relay UE and L2 U2U Remote UE as specified in
TS 38.351 \[66\].

*SL-SRAP-ConfigU2U* information element

\-- ASN1START

\-- TAG-SL-SRAP-CONFIGU2U-START

SL-SRAP-ConfigU2U-r18 ::= SEQUENCE {

sl-MappingToAddMod-U2U-List-r18 SEQUENCE (SIZE (1..maxSL-LCID-r16)) OF
SL-MappingConfig-U2U-r18 OPTIONAL, \-- Need N

sl-MappingToRelease-U2U-List-r18 SEQUENCE (SIZE (1..maxSL-LCID-r16)) OF
SLRB-Uu-ConfigIndex-r16 OPTIONAL \-- Need N

}

SL-MappingConfig-U2U-r18 ::= SEQUENCE {

sl-RemoteUE-SLRB-Identity-r18 SLRB-Uu-ConfigIndex-r16,

sl-EgressRLC-ChannelPC5-r18 SL-RLC-ChannelID-r17,

\...

}

\-- TAG-SL-SRAP-CONFIGU2U-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-SRAP-ConfigU2U* field descriptions                                |
+=======================================================================+
| ***sl-MappingToAddMod-U2U-List***                                     |
|                                                                       |
| Indicates the list of mappings between the end-to-end sidelink DRB of |
| a given L2 U2U Remote UE and the egress PC5 Relay RLC channel used by |
| L2 U2U Remote UE and L2 U2U Relay UE when acting as Tx UE, as         |
| specified in TS 38.351 \[66\] to be added or modified.                |
+-----------------------------------------------------------------------+
| ***sl-MappingToRelease-U2U-List***                                    |
|                                                                       |
| Indicates the list of mappings between the end-to-end sidelink DRB of |
| a given L2 U2U Remote UE and the egress PC5 Relay RLC channel as      |
| specified in TS 38.351 \[66\] to be released.                         |
+-----------------------------------------------------------------------+
| ***sl-EgressRLC-ChannelPC5***                                         |
|                                                                       |
| Indicates the egress PC5 Relay RLC channel for sidelink transmissions |
| at the L2 U2U Relay UE and at the L2 U2U Remote UE.                   |
+-----------------------------------------------------------------------+
| ***sl-RemoteUE-SLRB-Identity***                                       |
|                                                                       |
| Identity of the end-to-end sidelink DRB of the L2 U2U Remote UE.      |
+-----------------------------------------------------------------------+

#### -- *SL-SyncConfig*

The IE *SL-SyncConfig* specifies the configuration information
concerning reception of synchronisation signals from neighbouring cells
as well as concerning the transmission of synchronisation signals for
sidelink communication.

*SL-SyncConfig* information element

\-- ASN1START

\-- TAG-SL-SYNCCONFIG-START

SL-SyncConfigList-r16 ::= SEQUENCE (SIZE (1..maxSL-SyncConfig-r16)) OF
SL-SyncConfig-r16

SL-SyncConfig-r16 ::= SEQUENCE {

sl-SyncRefMinHyst-r16 ENUMERATED {dB0, dB3, dB6, dB9, dB12} OPTIONAL,
\-- Need R

sl-SyncRefDiffHyst-r16 ENUMERATED {dB0, dB3, dB6, dB9, dB12, dBinf}
OPTIONAL, \-- Need R

sl-FilterCoefficient-r16 FilterCoefficient OPTIONAL, \-- Need R

sl-SSB-TimeAllocation1-r16 SL-SSB-TimeAllocation-r16 OPTIONAL, \-- Need
R

sl-SSB-TimeAllocation2-r16 SL-SSB-TimeAllocation-r16 OPTIONAL, \-- Need
R

sl-SSB-TimeAllocation3-r16 SL-SSB-TimeAllocation-r16 OPTIONAL, \-- Need
R

sl-SSID-r16 INTEGER (0..671) OPTIONAL, \-- Need R

txParameters-r16 SEQUENCE {

syncTxThreshIC-r16 SL-RSRP-Range-r16 OPTIONAL, \-- Need R

syncTxThreshOoC-r16 SL-RSRP-Range-r16 OPTIONAL, \-- Need R

syncInfoReserved-r16 BIT STRING (SIZE (2)) OPTIONAL \-- Need R

},

gnss-Sync-r16 ENUMERATED {true} OPTIONAL, \-- Need R

\...

}

SL-RSRP-Range-r16 ::= INTEGER (0..13)

SL-SSB-TimeAllocation-r16 ::= SEQUENCE {

sl-NumSSB-WithinPeriod-r16 ENUMERATED {n1, n2, n4, n8, n16, n32, n64}
OPTIONAL, \-- Need R

sl-TimeOffsetSSB-r16 INTEGER (0..1279) OPTIONAL, \-- Need R

sl-TimeInterval-r16 INTEGER (0..639) OPTIONAL \-- Need R

}

\-- TAG-SL-SYNCCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-SyncConfig* field descriptions                                    |
+=======================================================================+
| ***gnss-Sync***                                                       |
|                                                                       |
| If configured, the synchronization configuration is used for SLSS     |
| transmission/reception when the UE is synchronized to GNSS. If not    |
| configured, the synchronization configuration is used for SLSS        |
| transmission/reception when the UE is synchronized to eNB/gNB.        |
+-----------------------------------------------------------------------+
| ***sl-SyncRefMinHyst***                                               |
|                                                                       |
| Hysteresis when evaluating a SyncRef UE using absolute comparison.    |
+-----------------------------------------------------------------------+
| ***sl-SyncRefDiffHyst***                                              |
|                                                                       |
| Hysteresis when evaluating a SyncRef UE using relative comparison.    |
+-----------------------------------------------------------------------+
| ***sl-NumSSB-WithinPeriod***                                          |
|                                                                       |
| Indicates the number of sidelink SSB transmissions within one         |
| sidelink SSB period. The applicable values are related to the         |
| subcarrier spacing and frequency as follows:                          |
|                                                                       |
| FR1, SCS = 15 kHz: 1                                                  |
|                                                                       |
| FR1, SCS = 30 kHz: 1, 2                                               |
|                                                                       |
| FR1, SCS = 60 kHz: 1, 2, 4                                            |
|                                                                       |
| FR2, SCS = 60 kHz: 1, 2, 4, 8, 16, 32                                 |
|                                                                       |
| FR2, SCS = 120 kHz: 1, 2, 4, 8, 16, 32, 64                            |
|                                                                       |
| All values in *sl-NumSSB-WithinPeriod* in *sl-SSB-TimeAllocation1* is |
| set to be same across all carrier frequencies configured for UEs      |
| performing NR sidelink communication on multiple carrier frequencies, |
| if configured. All values in *sl-NumSSB-WithinPeriod* in              |
| *sl-SSB-TimeAllocation2* is set to be same across all carrier         |
| frequencies configured for UEs performing NR sidelink communication   |
| on multiple carrier frequencies, if configured. All values in         |
| *sl-NumSSB-WithinPeriod* in *sl-SSB-TimeAllocation3* is set to be     |
| same across all carrier frequencies configured for UEs performing NR  |
| sidelink communication on multiple carrier frequencies, if            |
| configured.                                                           |
+-----------------------------------------------------------------------+
| ***sl-TimeOffsetSSB***                                                |
|                                                                       |
| Indicates the slot offset from the start of sidelink SSB period to    |
| the first sidelink SSB. All values in *sl-TimeOffsetSSB* in           |
| *sl-SSB-TimeAllocation1* is set to be same across all carrier         |
| frequencies configured for UEs performing NR sidelink communication   |
| on multiple carrier frequencies, if configured. All values in         |
| *sl-TimeOffsetSSB* in *sl-SSB-TimeAllocation2* is set to be same      |
| across all carrier frequencies configured for UEs performing NR       |
| sidelink communication on multiple carrier frequencies, if            |
| configured. All values in *sl-TimeOffsetSSB* in                       |
| *sl-SSB-TimeAllocation3* is set to be same across all carrier         |
| frequencies configured for UEs performing NR sidelink communication   |
| on multiple carrier frequencies, if configured.                       |
+-----------------------------------------------------------------------+
| ***sl-TimeInterval***                                                 |
|                                                                       |
| Indicates the slot interval between neighboring sidelink SSBs. This   |
| value is applicable when there are more than one sidelink SSBs within |
| one sidelink SSB period. All values in *sl-TimeInterval* in           |
| *sl-SSB-TimeAllocation1* is set to be same across all carrier         |
| frequencies configured for UEs performing NR sidelink communication   |
| on multiple carrier frequencies, if configured. All values in         |
| *sl-TimeInterval* in *sl-SSB-TimeAllocation2* is set to be same       |
| across all carrier frequencies configured for UEs performing NR       |
| sidelink communication on multiple carrier frequencies, if            |
| configured. All values in *sl-TimeInterval* in                        |
| *sl-SSB-TimeAllocation3* is set to be same across all carrier         |
| frequencies configured for UEs performing NR sidelink communication   |
| on multiple carrier frequencies, if configured.                       |
+-----------------------------------------------------------------------+
| ***sl-SSID***                                                         |
|                                                                       |
| Indicates the ID of sidelink synchronization signal associated with   |
| different synchronization priorities.                                 |
+-----------------------------------------------------------------------+
| ***syncInfoReserved***                                                |
|                                                                       |
| Reserved for future use.                                              |
+-----------------------------------------------------------------------+
| ***syncTxThreshIC, syncTxThreshOoC***                                 |
|                                                                       |
| Indicates the thresholds used while in coverage and out of coverage,  |
| respectively. Value 0 corresponds to -infinity, value 1 to -115 dBm,  |
| value 2 to -110 dBm, and so on (i.e. in steps of 5 dBm) until value   |
| 12, which corresponds to -60 dBm, while value 13 corresponds to       |
| +infinity.                                                            |
+-----------------------------------------------------------------------+

#### -- *SL-Thres-RSRP-List*

IE *SL-Thres-RSRP-List* indicates a threshold used for sensing based UE
autonomous resource selection (see TS 38.215 \[9\]). A resource is
excluded if it is indicated or reserved by a decoded SCI and PSSCH/PSCCH
RSRP in the associated data resource is above the threshold defined by
IE *SL-Thres-RSRP-List*. A NR sidelink resource is excluded if the
corresponding PSFCH transmission occasions overlap with resources
indicated or reserved by the decoded EUTRA SCI in time domain and EUTRA
PSSCH RSRP in the associated data resource is above the threshold
defined by IE *sl-NRPSFCH-EUTRA-ThresRSRP-List*. A NR sidelink resource
is excluded if it is indicated or reserved by the decoded EUTRA SCI and
EUTRA PSSCH RSRP in the associated data resource is above the threshold
defined by IE *sl-NRPSSCH-EUTRA-ThresRSRP-List*. Value 0 corresponds to
minus infinity dBm, value 1 corresponds to -128dBm, value 2 corresponds
to -126dBm, value n corresponds to (-128 + (n-1)\*2) dBm and so on,
value 66 corresponds to infinity dBm.

*SL-Thres-RSRP-List* information element

\-- ASN1START

\-- TAG-SL-THRES-RSRP-LIST-START

SL-Thres-RSRP-List-r16 ::= SEQUENCE (SIZE (64)) OF SL-Thres-RSRP-r16

SL-Thres-RSRP-r16 ::= INTEGER (0..66)

\-- TAG-SL-THRES-RSRP-LIST-STOP

\-- ASN1STOP

#### -- *SL-TxPower*

The IE *SL-TxPower* is used to limit the UE\'s sidelink transmission
power on a carrier frequency. The unit is dBm. Value minusinfinity
corresponds to --infinity.

*SL-TxPower* information element

\-- ASN1START

\-- TAG-SL-TXPOWER-START

SL-TxPower-r16 ::= CHOICE{

minusinfinity-r16 NULL,

txPower-r16 INTEGER (-30..33)

}

\-- TAG-SL-TXPOWER-STOP

\-- ASN1STOP

#### -- *SL-TypeTxSync*

The IE *SL-TypeTxSync* indicates the synchronization reference type.

*SL-TypeTxSync* information element

\-- ASN1START

\-- TAG-SL-TYPETXSYNC-START

SL-TypeTxSync-r16 ::= ENUMERATED {gnss, gnbEnb, ue}

\-- TAG-SL-TYPETXSYNC-STOP

\-- ASN1STOP

#### -- *SL-UE-SelectedConfig*

IE *SL-UE-SelectedConfig* specifies sidelink communication/positioning
configurations used for UE autonomous resource selection.

*SL-UE-SelectedConfig* information element

\-- ASN1START

\-- TAG-SL-UE-SELECTEDCONFIG-START

SL-UE-SelectedConfig-r16 ::= SEQUENCE {

sl-PSSCH-TxConfigList-r16 SL-PSSCH-TxConfigList-r16 OPTIONAL, \-- Cond
SIB12

sl-ProbResourceKeep-r16 ENUMERATED {v0, v0dot2, v0dot4, v0dot6, v0dot8}
OPTIONAL, \-- Need R

sl-ReselectAfter-r16 ENUMERATED {n1, n2, n3, n4, n5, n6, n7, n8, n9}
OPTIONAL, \-- Need R

sl-CBR-CommonTxConfigList-r16 SL-CBR-CommonTxConfigList-r16 OPTIONAL,
\-- Need R

ul-PrioritizationThres-r16 INTEGER (1..16) OPTIONAL, \-- Need R

sl-PrioritizationThres-r16 INTEGER (1..8) OPTIONAL, \-- Need R

\...,

\[\[

sl-CBR-CommonTxDedicatedSL-PRS-RP-List-r18
SL-CBR-CommonTxDedicatedSL-PRS-RP-List-r18 OPTIONAL \-- Cond notSIB12

\]\]

}

\-- TAG-SL-UE-SELECTEDCONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-UE-SelectedConfig* field descriptions                             |
+=======================================================================+
| ***sl-PrioritizationThres***                                          |
|                                                                       |
| Indicates the SL priority threshold, which is used to determine       |
| whether SL TX is prioritized over UL TX, as specified in TS 38.321    |
| \[3\]. Network does not configure the *sl-PrioritizationThres* and    |
| the *ul-PrioritizationThres* to the UE separately.                    |
+-----------------------------------------------------------------------+
| ***sl-ProbResourceKeep***                                             |
|                                                                       |
| Indicates the probability with which the UE keeps the current         |
| resource when the resource reselection counter reaches zero for       |
| sensing based UE autonomous resource selection (see TS 38.321 \[3\]). |
+-----------------------------------------------------------------------+
| ***sl-PSSCH-TxConfigList***                                           |
|                                                                       |
| Indicates PSSCH TX parameters such as MCS, sub-channel number,        |
| retransmission number, associated to different UE absolute speeds and |
| different synchronization reference types for UE autonomous resource  |
| selection.                                                            |
+-----------------------------------------------------------------------+
| ***sl-ReselectAfter***                                                |
|                                                                       |
| Indicates the number of consecutive skipped transmissions before      |
| triggering resource reselection for sidelink communication (see TS    |
| 38.321 \[3\]).                                                        |
+-----------------------------------------------------------------------+
| ***ul-PrioritizationThres***                                          |
|                                                                       |
| Indicates the UL priority threshold, which is used to determine       |
| whether SL TX is prioritized over UL TX, as specified in TS 38.321    |
| \[3\]. Network does not configure the *sl-PrioritizationThres* and    |
| the *ul-PrioritizationThres* to the UE separately.                    |
+-----------------------------------------------------------------------+

  -----------------------------------------------------------------------
  Conditional Presence Explanation
  -------------------- --------------------------------------------------
  *SIB12*              This field is optional present if included within
                       *SIB12*, need R. Otherwise, the field is absent.

  *notSIB12*           The field is absent in *SIB12*. Otherwise, it is
                       optional present, Need R
  -----------------------------------------------------------------------

#### -- *SL-ZoneConfig*

The IE *SL-ZoneConfig* is used to configure the zone ID related
parameters.

*SL-ZoneConfig* information element

\-- ASN1START

\-- TAG-SL-ZONECONFIG-START

SL-ZoneConfig-r16 ::= SEQUENCE {

sl-ZoneLength-r16 ENUMERATED { m5, m10, m20, m30, m40, m50, spare2,
spare1},

\...

}

\-- TAG-SL-ZONECONFIG-STOP

\-- ASN1STOP

+-----------------------------------------------------------------------+
| *SL-ZoneConfig* field descriptions                                    |
+=======================================================================+
| ***sl-ZoneLength***                                                   |
|                                                                       |
| Indicates the length of each geographic zone.                         |
+-----------------------------------------------------------------------+

#### -- *SLRB-Uu-ConfigIndex*

The IE *SLRB-Uu-ConfigIndex* is used to identify a sidelink DRB
configuration from the network side, or to indicate an end-to-end
sidelink DRB by L2 U2U Relay UE in *SidelinkUEInformation* message.

*SLRB-Uu-ConfigIndex* information element

\-- ASN1START

\-- TAG-SLRB-UU-CONFIGINDEX-START

SLRB-Uu-ConfigIndex-r16 ::= INTEGER (1..maxNrofSLRB-r16)

\-- TAG-SLRB-UU-CONFIGINDEX-STOP

\-- ASN1STOP