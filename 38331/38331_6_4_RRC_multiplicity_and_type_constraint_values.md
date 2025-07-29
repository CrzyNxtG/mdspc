## 6.4 RRC multiplicity and type constraint values

### -- Multiplicity and type constraint definitions

\-- ASN1START

\-- TAG-MULTIPLICITY-AND-TYPE-CONSTRAINT-DEFINITIONS-START

maxAdditionalRACH-r17 INTEGER ::= 256 \-- Maximum number of additional
RACH configurations.

maxAI-DCI-PayloadSize-r16 INTEGER ::= 128 \--Maximum size of the DCI
payload scrambled with ai-RNTI

maxAI-DCI-PayloadSize-1-r16 INTEGER ::= 127 \--Maximum size of the DCI
payload scrambled with ai-RNTI minus 1

maxBandComb INTEGER ::= 65536 \-- Maximum number of DL band combinations

maxBandComb-MUSIM-r18 INTEGER ::= 64 \-- Maximum number of MUSIM bands
and/or band combinations

maxBandsUTRA-FDD-r16 INTEGER ::= 64 \-- Maximum number of bands listed
in UTRA-FDD UE caps

maxCandidateBandIndex-r18 INTEGER ::= 8 \-- Maximum number of band entry
index for MUSIM capability

maxBH-RLC-ChannelID-r16 INTEGER ::= 65536 \-- Maximum value of BH RLC
Channel ID

maxBT-IdReport-r16 INTEGER ::= 32 \-- Maximum number of Bluetooth IDs to
report

maxBT-Name-r16 INTEGER ::= 4 \-- Maximum number of Bluetooth name

maxCAG-Cell-r16 INTEGER ::= 16 \-- Maximum number of NR CAG cell ranges
in SIB3, SIB4

maxTwoPUCCH-Grp-ConfigList-r16 INTEGER ::= 32 \-- Maximum number of
supported configuration(s) of {primary PUCCH group

\-- config, secondary PUCCH group config}

maxTwoPUCCH-Grp-ConfigList-r17 INTEGER ::= 16 \-- Maximum number of
supported configuration(s) of {primary PUCCH group

\-- config, secondary PUCCH group config} for PUCCH cell switching

maxCBR-Config-r16 INTEGER ::= 8 \-- Maximum number of CBR range
configurations for sidelink communication

\-- congestion control

maxCBR-Config-1-r16 INTEGER ::= 7 \-- Maximum number of CBR range
configurations for sidelink communication

\-- congestion control minus 1

maxCBR-Level-r16 INTEGER ::= 16 \-- Maximum number of CBR levels

maxCBR-Level-1-r16 INTEGER ::= 15 \-- Maximum number of CBR levels minus
1

maxCellATG-r18 INTEGER ::= 8 \-- Maximum number of ATG neighbour cells
for which assistance information is

\-- provided

maxCellExcluded INTEGER ::= 16 \-- Maximum number of NR exclude-listed
cell ranges in SIB3, SIB4

maxCellGroupings-r16 INTEGER ::= 32 \-- Maximum number of cell groupings
for NR-DC

maxCellHistory-r16 INTEGER ::= 16 \-- Maximum number of visited PCells
reported

maxPSCellHistory-r17 INTEGER ::= 16 \-- Maximum number of visited
PSCells across all reported PCells

maxCellInter INTEGER ::= 16 \-- Maximum number of inter-Freq cells
listed in SIB4

maxCellIntra INTEGER ::= 16 \-- Maximum number of intra-Freq cells
listed in SIB3

maxCellMeasEUTRA INTEGER ::= 32 \-- Maximum number of cells in E-UTRAN

maxCellMeasIdle-r16 INTEGER ::= 8 \-- Maximum number of cells per
carrier for idle/inactive measurements

maxCellMeasUTRA-FDD-r16 INTEGER ::= 32 \-- Maximum number of cells in
FDD UTRAN

maxCellNTN-r17 INTEGER ::= 4 \-- Maximum number of NTN neighbour cells
for which assistance information is

\-- provided

maxCarrierTypePairList-r16 INTEGER ::= 16 \-- Maximum number of
supported carrier type pair of (carrier type on which

\-- CSI measurement is performed, carrier type on which CSI reporting is

\-- performed) for CSI reporting cross PUCCH group

maxCellAllowed INTEGER ::= 16 \-- Maximum number of NR allow-listed cell
ranges in SIB3, SIB4

maxEARFCN INTEGER ::= 262143 \-- Maximum value of E-UTRA carrier
frequency

maxEUTRA-CellExcluded INTEGER ::= 16 \-- Maximum number of E-UTRA
exclude-listed physical cell identity ranges

\-- in SIB5

maxEUTRA-NS-Pmax INTEGER ::= 8 \-- Maximum number of NS and P-Max values
per band

maxFeatureCombPreamblesPerRACHResource-r17 INTEGER ::= 256 \-- Maximum
number of feature combination preambles.

maxLogMeasReport-r16 INTEGER ::= 520 \-- Maximum number of entries for
logged measurements

maxMultiBands INTEGER ::= 8 \-- Maximum number of additional frequency
bands that a cell belongs to

maxNARFCN INTEGER ::= 3279165 \-- Maximum value of NR carrier frequency

maxNR-NS-Pmax INTEGER ::= 8 \-- Maximum number of NS and P-Max values
per band

maxFreqIdle-r16 INTEGER ::= 8 \-- Maximum number of carrier frequencies
for idle/inactive measurements

maxNrofServingCells INTEGER ::= 32 \-- Max number of serving cells
(SpCells + SCells)

maxNrofServingCells-1 INTEGER ::= 31 \-- Max number of serving cells
(SpCells + SCells) minus 1

maxNrofAggregatedCellsPerCellGroup INTEGER ::= 16

maxNrofAggregatedCellsPerCellGroupMinus4-r16 INTEGER ::= 12

maxNrofAperiodicFwdTimeResource-r18 INTEGER ::= 112 \-- Max number of
aperiodic fowarding time resources for NCR

maxNrofAperiodicFwdTimeResource-1-r18 INTEGER ::= 111 \-- Max number of
aperiodic fowarding time resources for NCR minus 1

maxNrofDUCells-r16 INTEGER ::= 512 \-- Max number of cells configured on
the collocated IAB-DU

maxNrofAppLayerMeas-r17 INTEGER ::= 16 \-- Max number of simultaneous
application layer measurements

maxNrofAppLayerMeas-1-r17 INTEGER ::= 15 \-- Max number of simultaneous
application layer measurements minus 1

maxNrofAppLayerReports-r18 INTEGER ::= 16 \-- Max number of application
layer measurement reports with the same

\-- measConfigAppLayerId included in the same

\-- MeasurementReportAppLayerMessage

maxNrofAvailabilityCombinationsPerSet-r16 INTEGER ::= 512 \-- Max number
of AvailabilityCombinationId used in the DCI format 2_5

maxNrofAvailabilityCombinationsPerSet-1-r16 INTEGER ::= 511 \-- Max
number of AvailabilityCombinationId used in the DCI format 2_5 minus 1

maxNrofIABResourceConfig-r17 INTEGER ::= 65536 \-- Max number of
IAB-ResourceConfigID used in MAC CE

maxNrofIABResourceConfig-1-r17 INTEGER ::= 65535 \-- Max number of
IAB-ResourceConfigID used in MAC CE minus 1

maxNrofPeriodicFwdResourceSet-r18 INTEGER ::= 32 \-- Max number of
periodic fowarding resource sets for NCR

maxNrofPeriodicFwdResourceSet-1-r18 INTEGER ::= 31 \-- Max number of
periodic fowarding resource sets for NCR minus 1

maxNrofPeriodicFwdResource-r18 INTEGER ::= 1024 \-- Max number of
periodic fowarding resources for NCR

maxNrofPeriodicFwdResource-1-r18 INTEGER ::= 1023 \-- Max number of
periodic fowarding resources for NCR minus 1

maxNrofSemiPersistentFwdResourceSet-r18 INTEGER ::= 32 \-- Max number of
semi-persistent fowarding resource sets for NCR

maxNrofSemiPersistentFwdResourceSet-1-r18 INTEGER ::= 31 \-- Max number
of semi-persistent fowarding resource sets for NCR minus 1

maxNrofSemiPersistentFwdResource-r18 INTEGER ::= 128 \-- Max number of
semi-persistent fowarding resources for NCR

maxNrofSemiPersistentFwdResource-1-r18 INTEGER ::= 127 \-- Max number of
semi-persistent fowarding resources for NCR minus 1

maxNrofSCellActRS-r17 INTEGER ::= 255 \-- Max number of RS
configurations per SCell for SCell activation

maxNrofSCells INTEGER ::= 31 \-- Max number of secondary serving cells
per cell group

maxNrofCellMeas INTEGER ::= 32 \-- Maximum number of entries in each of
the cell lists in a measurement object

maxNrofCRS-IM-InterfCell-r17 INTEGER ::= 8 \-- Maximum number of LTE
interference cells for CRS-IM per UE

maxNrofRelayMeas-r17 INTEGER ::= 32 \-- Maximum number of L2 U2N Relay
UEs to measure for each measurement object

\-- on sidelink frequency

maxNrofCG-SL-r16 INTEGER ::= 8 \-- Max number of sidelink configured
grant

maxNrofCG-SL-1-r16 INTEGER ::= 7 \-- Max number of sidelink configured
grant minus 1

maxSL-GC-BC-DRX-QoS-r17 INTEGER ::= 16 \-- Max number of sidelink DRX
configurations for NR

\-- sidelink groupcast/broadcast communication

maxNrofSL-RxInfoSet-r17 INTEGER ::= 4 \-- Max number of sidelink DRX
configuration sets in sidelink DRX assistant

\-- information

maxNrofSS-BlocksToAverage INTEGER ::= 16 \-- Max number for the (max)
number of SS blocks to average to determine cell measurement

maxNrofCondCells-r16 INTEGER ::= 8 \-- Max number of conditional
candidate SpCells

maxNrofCondCells-1-r17 INTEGER ::= 7 \-- Max number of conditional
candidate SpCells minus 1

maxNrofCSI-RS-ResourcesToAverage INTEGER ::= 16 \-- Max number for the
(max) number of CSI-RS to average to determine cell measurement

maxNrofDL-Allocations INTEGER ::= 16 \-- Maximum number of PDSCH time
domain resource allocations

maxNrofDL-AllocationsExt-r17 INTEGER ::= 64 \-- Maximum number of PDSCH
time domain resource allocations for multi-PDSCH

\-- scheduling

maxNrofDL-Allocations-1-r18 INTEGER ::= 15 \-- Maximum number of PDSCH
time domain resource allocations minus 1

maxNrofPDU-Sessions-r17 INTEGER ::= 256 \-- Maximum number of PDU
Sessions

maxNrofSR-ConfigPerCellGroup INTEGER ::= 8 \-- Maximum number of SR
configurations per cell group

maxNrofLCGs-r18 INTEGER ::= 8 \-- Maximum number of LCGs

maxLCG-ID INTEGER ::= 7 \-- Maximum value of LCG ID

maxLCG-ID-IAB-r17 INTEGER ::= 255 \-- Maximum value of LCG ID for IAB-MT

maxLC-ID INTEGER ::= 32 \-- Maximum value of Logical Channel ID

maxLC-ID-Iab-r16 INTEGER ::= 65855 \-- Maximum value of BH Logical
Channel ID extension

maxLTE-CRS-Patterns-r16 INTEGER ::= 3 \-- Maximum number of additional
LTE CRS rate matching patterns

maxNrOfLinkedSRS-CarriersInactive-1-r18 INTEGER ::= 2 \-- Maximum number
of carriers for positioning SRS CA in RRC_INACTIVE minus 1

maxNrofTAGs INTEGER ::= 4 \-- Maximum number of Timing Advance Groups

maxNrofTAGs-1 INTEGER ::= 3 \-- Maximum number of Timing Advance Groups
minus 1

maxNrofBWPs INTEGER ::= 4 \-- Maximum number of BWPs per serving cell

maxNrofCombIDC INTEGER ::= 128 \-- Maximum number of reported MR-DC
combinations for IDC

maxNrofSymbols-1 INTEGER ::= 13 \-- Maximum index identifying a symbol
within a slot (14 symbols, indexed from 0..13)

maxNrofSlots INTEGER ::= 320 \-- Maximum number of slots in a 10 ms
period

maxNrofSlots-1 INTEGER ::= 319 \-- Maximum number of slots in a 10 ms
period minus 1

maxNrofPhysicalResourceBlocks INTEGER ::= 275 \-- Maximum number of PRBs

maxNrofPhysicalResourceBlocks-1 INTEGER ::= 274 \-- Maximum number of
PRBs minus 1

maxNrofPhysicalResourceBlocksPlus1 INTEGER ::= 276 \-- Maximum number of
PRBs plus 1

maxNrofControlResourceSets INTEGER ::= 12 \-- Max number of CoReSets
configurable on a serving cell

maxNrofControlResourceSets-1 INTEGER ::= 11 \-- Max number of CoReSets
configurable on a serving cell minus 1

maxNrofControlResourceSets-1-r16 INTEGER ::= 15 \-- Max number of
CoReSets configurable on a serving cell extended in minus 1

maxNrofCoresetPools-r16 INTEGER ::= 2 \-- Maximum number of CORESET
pools

maxCoReSetDuration INTEGER ::= 3 \-- Max number of OFDM symbols in a
control resource set

maxNrofSearchSpaces-1 INTEGER ::= 39 \-- Max number of Search Spaces
minus 1

maxNrofSearchSpacesLinks-1-r17 INTEGER ::= 39 \-- Max number of Search
Space links minus 1

maxNrofBFDResourcePerSet-r17 INTEGER ::= 64 \-- Max number of reference
signal in one BFD set

maxSFI-DCI-PayloadSize INTEGER ::= 128 \-- Max number payload of a DCI
scrambled with SFI-RNTI

maxSFI-DCI-PayloadSize-1 INTEGER ::= 127 \-- Max number payload of a DCI
scrambled with SFI-RNTI minus 1

maxIAB-IP-Address-r16 INTEGER ::= 32 \-- Max number of assigned IP
addresses

maxINT-DCI-PayloadSize INTEGER ::= 126 \-- Max number payload of a DCI
scrambled with INT-RNTI

maxINT-DCI-PayloadSize-1 INTEGER ::= 125 \-- Max number payload of a DCI
scrambled with INT-RNTI minus 1

maxNrofRateMatchPatterns INTEGER ::= 4 \-- Max number of rate matching
patterns that may be configured

maxNrofRateMatchPatterns-1 INTEGER ::= 3 \-- Max number of rate matching
patterns that may be configured minus 1

maxNrofRateMatchPatternsPerGroup INTEGER ::= 8 \-- Max number of rate
matching patterns that may be configured in one group

maxNrofCSI-ReportConfigurations INTEGER ::= 48 \-- Maximum number of
report configurations

maxNrofCSI-ReportConfigurations-1 INTEGER ::= 47 \-- Maximum number of
report configurations minus 1

maxNrofCSI-ResourceConfigurations INTEGER ::= 112 \-- Maximum number of
resource configurations

maxNrofCSI-ResourceConfigurations-1 INTEGER ::= 111 \-- Maximum number
of resource configurations minus 1

maxNrofAP-CSI-RS-ResourcesPerSet INTEGER ::= 16

maxNrOfCSI-AperiodicTriggers INTEGER ::= 128 \-- Maximum number of
triggers for aperiodic CSI reporting

maxNrofReportConfigPerAperiodicTrigger INTEGER ::= 16 \-- Maximum number
of report configurations per trigger state for aperiodic reporting

maxNrofNZP-CSI-RS-Resources INTEGER ::= 192 \-- Maximum number of
Non-Zero-Power (NZP) CSI-RS resources

maxNrofNZP-CSI-RS-Resources-1 INTEGER ::= 191 \-- Maximum number of
Non-Zero-Power (NZP) CSI-RS resources minus 1

maxNrofNZP-CSI-RS-ResourcesPerSet INTEGER ::= 64 \-- Maximum number of
NZP CSI-RS resources per resource set

maxNrofNZP-CSI-RS-ResourcesPerSet-1-r18 INTEGER ::= 63 \-- Maximum
number of NZP CSI-RS resources per resource set minus 1

maxNrofNZP-CSI-RS-ResourceSets INTEGER ::= 64 \-- Maximum number of NZP
CSI-RS resource sets per cell

maxNrofNZP-CSI-RS-ResourceSets-1 INTEGER ::= 63 \-- Maximum number of
NZP CSI-RS resource sets per cell minus 1

maxNrofNZP-CSI-RS-ResourceSetsPerConfig INTEGER ::= 16 \-- Maximum
number of resource sets per resource configuration

maxNrofNZP-CSI-RS-ResourcesPerConfig INTEGER ::= 128 \-- Maximum number
of resources per resource configuration

maxNrofZP-CSI-RS-Resources INTEGER ::= 32 \-- Maximum number of
Zero-Power (ZP) CSI-RS resources

maxNrofZP-CSI-RS-Resources-1 INTEGER ::= 31 \-- Maximum number of
Zero-Power (ZP) CSI-RS resources minus 1

maxNrofZP-CSI-RS-ResourceSets-1 INTEGER ::= 15

maxNrofZP-CSI-RS-ResourcesPerSet INTEGER ::= 16

maxNrofZP-CSI-RS-ResourceSets INTEGER ::= 16

maxNrofCSI-IM-Resources INTEGER ::= 32 \-- Maximum number of CSI-IM
resources

maxNrofCSI-IM-Resources-1 INTEGER ::= 31 \-- Maximum number of CSI-IM
resources minus 1

maxNrofCSI-IM-ResourcesPerSet INTEGER ::= 8 \-- Maximum number of CSI-IM
resources per set

maxNrofCSI-IM-ResourceSets INTEGER ::= 64 \-- Maximum number of NZP
CSI-IM resource sets per cell

maxNrofCSI-IM-ResourceSets-1 INTEGER ::= 63 \-- Maximum number of NZP
CSI-IM resource sets per cell minus 1

maxNrofCSI-IM-ResourceSetsPerConfig INTEGER ::= 16 \-- Maximum number of
CSI IM resource sets per resource configuration

maxNrofCSI-SSB-ResourcePerSet INTEGER ::= 64 \-- Maximum number of SSB
resources in a resource set

maxNrofCSI-SSB-ResourceSets INTEGER ::= 64 \-- Maximum number of CSI SSB
resource sets per cell

maxNrofCSI-SSB-ResourceSets-1 INTEGER ::= 63 \-- Maximum number of CSI
SSB resource sets per cell minus 1

maxNrofCSI-SSB-ResourceSetsPerConfig INTEGER ::= 1 \-- Maximum number of
CSI SSB resource sets per resource configuration

maxNrofCSI-SSB-ResourceSetsPerConfigExt INTEGER ::= 2 \-- Maximum number
of CSI SSB resource sets per resource configuration

\-- extended

maxNrofFailureDetectionResources INTEGER ::= 10 \-- Maximum number of
failure detection resources

maxNrofFailureDetectionResources-1 INTEGER ::= 9 \-- Maximum number of
failure detection resources minus 1

maxNrofFailureDetectionResources-1-r17 INTEGER ::= 63 \-- Maximum number
of the enhanced failure detection resources minus 1

maxNrofFreqSL-r16 INTEGER ::= 8 \-- Maximum number of carrier frequency
for NR sidelink communication

maxNrofFreqSL-1-r18 INTEGER ::= 7 \-- Maximum number of carrier
frequency for NR sidelink communication minus 1

maxNrofSL-BWPs-r16 INTEGER ::= 4 \-- Maximum number of BWP for NR
sidelink communication

maxNrofSL-CarrierSetConfig-r18 INTEGER ::= 96 \-- Maximum number of SCCH
carrier set configuration for NR sidelink

\-- communication

maxFreqSL-EUTRA-r16 INTEGER ::= 8 \-- Maximum number of EUTRA anchor
carrier frequency for NR sidelink

\-- communication

maxNrofSL-MeasId-r16 INTEGER ::= 64 \-- Maximum number of sidelink
measurement identity (RSRP) per destination

maxNrofSL-ObjectId-r16 INTEGER ::= 64 \-- Maximum number of sidelink
measurement objects (RSRP) per destination

maxNrofSL-ReportConfigId-r16 INTEGER ::= 64 \-- Maximum number of
sidelink measurement reporting configuration(RSRP) per destination

maxNrofSL-PoolToMeasureNR-r16 INTEGER ::= 8 \-- Maximum number of
resource pool for NR sidelink measurement to measure

\-- for each measurement object (for CBR)

maxNrofDedicatedSL-PRS-PoolToMeas-r18 INTEGER ::= 8 \-- Maximum number
of SL-PRS dedicated resource pool for positioning

\-- measurement to measure for each measurement object (for SL-PRS CBR)

maxFreqSL-NR-r16 INTEGER ::= 8 \-- Maximum number of NR anchor carrier
frequency for NR sidelink communication

maxNrofSL-QFIs-r16 INTEGER ::= 2048 \-- Maximum number of QoS flow for
NR sidelink communication per UE

maxNrofSL-QFIsPerDest-r16 INTEGER ::= 64 \-- Maximum number of QoS flow
per destination for NR sidelink communication

maxNrofObjectId INTEGER ::= 64 \-- Maximum number of measurement objects

maxNrofPageRec INTEGER ::= 32 \-- Maximum number of page records

maxNrofPCI-Ranges INTEGER ::= 8 \-- Maximum number of PCI ranges

maxPLMN INTEGER ::= 12 \-- Maximum number of PLMNs broadcast and
reported by UE at establishment

maxTAC-r17 INTEGER ::= 12 \-- Maximum number of Tracking Area Codes to
which a cell belongs to

maxNrofCSI-RS-ResourcesRRM INTEGER ::= 96 \-- Maximum number of CSI-RS
resources per cell for an RRM measurement object

maxNrofCSI-RS-ResourcesRRM-1 INTEGER ::= 95 \-- Maximum number of CSI-RS
resources per cell for an RRM measurement object

\-- minus 1.

maxNrofMeasId INTEGER ::= 64 \-- Maximum number of configured
measurements

maxNrofQuantityConfig INTEGER ::= 2 \-- Maximum number of quantity
configurations

maxNrofCSI-RS-CellsRRM INTEGER ::= 96 \-- Maximum number of cells with
CSI-RS resources for an RRM measurement object

maxNrofSL-Dest-r16 INTEGER ::= 32 \-- Maximum number of destination for
NR sidelink communication and discovery

maxNrofSL-Dest-1-r16 INTEGER ::= 31 \-- Highest index of destination for
NR sidelink communication and discovery

maxNrofSL-PRS-PerDest-r18 INTEGER ::= 8 \-- Max number of SL-PRS
transmission supported per destination UE

maxNrofSLRB-r16 INTEGER ::= 512 \-- Maximum number of radio bearer for
NR sidelink communication per UE without duplication

maxSL-LCID-Plus1-r18 INTEGER ::= 513 \-- Maximum number of RLC bearer
for NR sidelink communication per UE without duplication plus 1

maxSL-LCID-r18 INTEGER ::= 1024 \-- Maximum number of RLC bearer for NR
sidelink communication per UE with duplication

maxSL-NonAnchorRBsets INTEGER ::= 4 \-- Maximum number of non-anchor RB
sets

maxSL-LCID-r16 INTEGER ::= 512 \-- Maximum number of RLC bearer for NR
sidelink communication per UE

maxSL-SyncConfig-r16 INTEGER ::= 16 \-- Maximum number of sidelink Sync
configurations

maxNrofRXPool-r16 INTEGER ::= 16 \-- Maximum number of Rx resource pool
for NR sidelink communication and

\-- discovery

maxNrofTXPool-r16 INTEGER ::= 8 \-- Maximum number of Tx resource pool
for NR sidelink communication and

\-- discovery

maxNrofPoolID-r16 INTEGER ::= 16 \-- Maximum index of resource pool for
NR sidelink communication and

\-- discovery

maxNrofSRS-PathlossReferenceRS-r16 INTEGER ::= 64 \-- Maximum number of
RSs used as pathloss reference for SRS power control.

maxNrofSRS-PathlossReferenceRS-1-r16 INTEGER ::= 63 \-- Maximum number
of RSs used as pathloss reference for SRS power control

\-- minus 1.

maxNrofSRS-ResourceSets INTEGER ::= 16 \-- Maximum number of SRS
resource sets in a BWP.

maxNrofSRS-ResourceSets-1 INTEGER ::= 15 \-- Maximum number of SRS
resource sets in a BWP minus 1.

maxNrofSRS-PosResourceSets-r16 INTEGER ::= 16 \-- Maximum number of SRS
Positioning resource sets in a BWP.

maxNrofSRS-PosResourceSets-1-r16 INTEGER ::= 15 \-- Maximum number of
SRS Positioning resource sets in a BWP minus 1.

maxNrofSRS-Resources INTEGER ::= 64 \-- Maximum number of SRS resources.

maxNrofSRS-Resources-1 INTEGER ::= 63 \-- Maximum number of SRS
resources minus 1.

maxNrofSRS-PosResources-r16 INTEGER ::= 64 \-- Maximum number of SRS
Positioning resources.

maxNrofSRS-PosResources-1-r16 INTEGER ::= 63 \-- Maximum number of SRS
Positioning resources minus 1.

maxNrofSRS-ResourcesPerSet INTEGER ::= 16 \-- Maximum number of SRS
resources in an SRS resource set

maxNrofSRS-TriggerStates-1 INTEGER ::= 3 \-- Maximum number of SRS
trigger states minus 1, i.e., the largest code point.

maxNrofSRS-TriggerStates-2 INTEGER ::= 2 \-- Maximum number of SRS
trigger states minus 2.

maxRAT-CapabilityContainers INTEGER ::= 8 \-- Maximum number of
interworking RAT containers (incl NR and MRDC)

maxSimultaneousBands INTEGER ::= 32 \-- Maximum number of simultaneously
aggregated bands

maxSimultaneousBands-2-r18 INTEGER ::= 30 \-- Maximum number of
simultaneously aggregated bands minus 2.

maxULTxSwitchingBandPairs INTEGER ::= 32 \-- Maximum number of band
pairs supporting dynamic UL Tx switching in a band

\-- combination.

maxULTxSwitchingBetweenBandPairs-r18 INTEGER ::= 32 \-- Maximum number
of combinations of a band pair and another band pair/band

\-- between which dynamic UL Tx switching requires additional switching

\-- period.

maxSchedulingBandCombination-r18 INTEGER ::= 32 \-- Maximum number of
combinations of scheduling cell and co-scheduled cells

\-- have same or different carrier type.

maxNrofSlotFormatCombinationsPerSet INTEGER ::= 512 \-- Maximum number
of Slot Format Combinations in a SF-Set.

maxNrofSlotFormatCombinationsPerSet-1 INTEGER ::= 511 \-- Maximum number
of Slot Format Combinations in a SF-Set minus 1.

maxNrofTrafficPattern-r16 INTEGER ::= 8 \-- Maximum number of Traffic
Pattern for NR sidelink communication.

maxNrofPUCCH-Resources INTEGER ::= 128

maxNrofPUCCH-Resources-1 INTEGER ::= 127

maxNrofPUCCH-ResourceSets INTEGER ::= 4 \-- Maximum number of PUCCH
Resource Sets

maxNrofPUCCH-ResourceSets-1 INTEGER ::= 3 \-- Maximum number of PUCCH
Resource Sets minus 1.

maxNrofPUCCH-ResourcesPerSet INTEGER ::= 32 \-- Maximum number of PUCCH
Resources per PUCCH-ResourceSet

maxNrofPUCCH-P0-PerSet INTEGER ::= 8 \-- Maximum number of P0-pucch
present in a p0-pucch set

maxNrofPUCCH-PathlossReferenceRSs INTEGER ::= 4 \-- Maximum number of
RSs used as pathloss reference for PUCCH power control.

maxNrofPUCCH-PathlossReferenceRSs-1 INTEGER ::= 3 \-- Maximum number of
RSs used as pathloss reference for PUCCH power control

\-- minus 1.

maxNrofPUCCH-PathlossReferenceRSs-r16 INTEGER ::= 64 \-- Maximum number
of RSs used as pathloss reference for PUCCH power control

\-- extended.

maxNrofPUCCH-PathlossReferenceRSs-1-r16 INTEGER ::= 63 \-- Maximum
number of RSs used as pathloss reference for PUCCH power control

\-- minus 1 extended.

maxNrofPUCCH-PathlossReferenceRSs-1-r17 INTEGER ::= 7 \-- Maximum number
of RSs used as pathloss reference for PUCCH power control

\-- minus 1.

maxNrofPUCCH-PathlossReferenceRSsDiff-r16 INTEGER ::= 60 \-- Difference
between the extended maximum and the non-extended maximum

maxNrofPUCCH-ResourceGroups-r16 INTEGER ::= 4 \-- Maximum number of
PUCCH resources groups.

maxNrofPUCCH-ResourcesPerGroup-r16 INTEGER ::= 128 \-- Maximum number of
PUCCH resources in a PUCCH group.

maxNrofPowerControlSetInfos-r17 INTEGER ::= 8 \-- Maximum number of
PUCCH power control set infos

maxNrofMultiplePUSCHs-r16 INTEGER ::= 8 \-- Maximum number of multiple
PUSCHs in PUSCH TDRA list

maxNrofP0-PUSCH-AlphaSets INTEGER ::= 30 \-- Maximum number of
P0-pusch-alpha-sets (see TS 38.213 \[13\], clause 7.1)

maxNrofP0-PUSCH-AlphaSets-1 INTEGER ::= 29 \-- Maximum number of
P0-pusch-alpha-sets minus 1 (see TS 38.213 \[13\], clause 7.1)

maxNrofPUSCH-PathlossReferenceRSs INTEGER ::= 4 \-- Maximum number of
RSs used as pathloss reference for PUSCH power control.

maxNrofPUSCH-PathlossReferenceRSs-1 INTEGER ::= 3 \-- Maximum number of
RSs used as pathloss reference for PUSCH power control

\-- minus 1.

maxNrofPUSCH-PathlossReferenceRSs-r16 INTEGER ::= 64 \-- Maximum number
of RSs used as pathloss reference for PUSCH power control

\-- extended

maxNrofPUSCH-PathlossReferenceRSs-1-r16 INTEGER ::= 63 \-- Maximum
number of RSs used as pathloss reference for PUSCH power control

\-- extended minus 1

maxNrofPUSCH-PathlossReferenceRSsDiff-r16 INTEGER ::= 60 \-- Difference
between maxNrofPUSCH-PathlossReferenceRSs-r16 and

\-- maxNrofPUSCH-PathlossReferenceRSs

maxNrofPathlossReferenceRSs-r17 INTEGER ::= 64 \-- Maximum number of RSs
used as pathloss reference for PUSCH, PUCCH, SRS

\-- power control for unified TCI state operation

maxNrofPathlossReferenceRSs-1-r17 INTEGER ::= 63 \-- Maximum number of
RSs used as pathloss reference for PUSCH, PUCCH, SRS

\-- power control for unified TCI state operation minus 1

maxNrofNAICS-Entries INTEGER ::= 8 \-- Maximum number of supported NAICS
capability set

maxBands INTEGER ::= 1024 \-- Maximum number of supported bands in UE
capability.

maxBandsMRDC INTEGER ::= 1280

maxBandsEUTRA INTEGER ::= 256

maxCellReport INTEGER ::= 8

maxDRB INTEGER ::= 29 \-- Maximum number of DRBs (that can be added in
DRB-ToAddModList).

maxFreq INTEGER ::= 8 \-- Max number of frequencies.

maxFreqLayers INTEGER ::= 4 \-- Max number of frequency layers.

maxFreqPlus1 INTEGER ::= 9 \-- Max number of frequencies for Slicing.

maxFreqIDC-r16 INTEGER ::= 128 \-- Max number of frequencies for IDC
indication.

maxCombIDC-r16 INTEGER ::= 128 \-- Max number of reported UL CA for IDC
indication.

maxFreqIDC-MRDC INTEGER ::= 32 \-- Maximum number of candidate NR
frequencies for MR-DC IDC indication

maxNrofCandidateBeams INTEGER ::= 16 \-- Max number of
PRACH-ResourceDedicatedBFR in BFR config.

maxNrofCandidateBeams-r16 INTEGER ::= 64 \-- Max number of candidate
beam resources in BFR config.

maxNrofCandidateBeamsExt-r16 INTEGER ::= 48 \-- Max number of
PRACH-ResourceDedicatedBFR in the CandidateBeamRSListExt

maxNrofPCIsPerSMTC INTEGER ::= 64 \-- Maximum number of PCIs per SMTC.

maxNrofQFIs INTEGER ::= 64

maxNrofResourceAvailabilityPerCombination-r16 INTEGER ::= 256

maxNrOfSemiPersistentPUSCH-Triggers INTEGER ::= 64 \-- Maximum number of
triggers for semi persistent reporting on PUSCH

maxNrofSR-Resources INTEGER ::= 8 \-- Maximum number of SR resources per
BWP in a cell.

maxNrofSlotFormatsPerCombination INTEGER ::= 256

maxNrofSpatialRelationInfos INTEGER ::= 8

maxNrofSpatialRelationInfos-plus-1 INTEGER ::= 9

maxNrofSpatialRelationInfos-r16 INTEGER ::= 64

maxNrofSpatialRelationInfosDiff-r16 INTEGER ::= 56 \-- Difference
between maxNrofSpatialRelationInfos-r16 and maxNrofSpatialRelationInfos

maxNrofIndexesToReport INTEGER ::= 32

maxNrofIndexesToReport2 INTEGER ::= 64

maxNrofSSBs-r16 INTEGER ::= 64 \-- Maximum number of SSB resources in a
resource set.

maxNrofSSBs-1 INTEGER ::= 63 \-- Maximum number of SSB resources in a
resource set minus 1.

maxNrofS-NSSAI INTEGER ::= 8 \-- Maximum number of S-NSSAI.

maxNrofTCI-StatesPDCCH INTEGER ::= 64

maxNrofTCI-States INTEGER ::= 128 \-- Maximum number of TCI states.

maxNrofTCI-States-1 INTEGER ::= 127 \-- Maximum number of TCI states
minus 1.

maxUL-TCI-r17 INTEGER ::= 64 \-- Maximum number of TCI states.

maxUL-TCI-1-r17 INTEGER ::= 63 \-- Maximum number of TCI states minus 1.

maxNrofAdditionalPCI-r17 INTEGER ::= 7 \-- Maximum number of additional
PCI

maxNrofAdditionalPRACHConfigs-r18 INTEGER ::= 7 \-- Maximum number of
additional PRACH configurations for 2TA

maxNrofdelayD-r18 INTEGER ::= 4 \-- Maximum number of delayD values.

maxMPE-Resources-r17 INTEGER ::= 64 \-- Maximum number of pooled MPE
resources

maxNrofUL-Allocations INTEGER ::= 16 \-- Maximum number of PUSCH time
domain resource allocations.

maxQFI INTEGER ::= 63

maxRA-CSIRS-Resources INTEGER ::= 96

maxRA-OccasionsPerCSIRS INTEGER ::= 64 \-- Maximum number of RA
occasions for one CSI-RS

maxRA-Occasions-1 INTEGER ::= 511 \-- Maximum number of RA occasions in
the system

maxRA-SSB-Resources INTEGER ::= 64

maxSCSs INTEGER ::= 5

maxSecondaryCellGroups INTEGER ::= 3

maxNrofServingCellsEUTRA INTEGER ::= 32

maxMBSFN-Allocations INTEGER ::= 8

maxNrofMultiBands INTEGER ::= 8

maxCellSFTD INTEGER ::= 3 \-- Maximum number of cells for SFTD reporting

maxReportConfigId INTEGER ::= 64

maxNrofCodebooks INTEGER ::= 16 \-- Maximum number of codebooks
supported by the UE

maxNrofCSI-RS-ResourcesExt-r16 INTEGER ::= 16 \-- Maximum number of
codebook resources supported by the UE for eType2/Codebook combo

maxNrofCSI-RS-ResourcesExt-r17 INTEGER ::= 8 \-- Maximum number of
codebook resources for fetype2R1 and fetype2R2

maxNrofCSI-RS-Resources INTEGER ::= 7 \-- Maximum number of codebook
resources supported by the UE

maxNrofCSI-RS-ResourcesAlt-r16 INTEGER ::= 512 \-- Maximum number of
alternative codebook resources supported by the UE

maxNrofCSI-RS-ResourcesAlt-1-r16 INTEGER ::= 511 \-- Maximum number of
alternative codebook resources supported by the UE minus 1

maxNrofSRI-PUSCH-Mappings INTEGER ::= 16

maxNrofSRI-PUSCH-Mappings-1 INTEGER ::= 15

maxSIB INTEGER::= 32 \-- Maximum number of SIBs

maxSI-Message INTEGER::= 32 \-- Maximum number of SI messages

maxSIB-MessagePlus1-r17 INTEGER::= 33 \-- Maximum number of SIB messages
plus 1

maxPO-perPF INTEGER ::= 4 \-- Maximum number of paging occasion per
paging frame

maxPEI-perPF-r17 INTEGER ::= 4 \-- Maximum number of PEI occasion per
paging frame

maxAccessCat-1 INTEGER ::= 63 \-- Maximum number of Access Categories
minus 1

maxBarringInfoSet INTEGER ::= 8 \-- Maximum number of access control
parameter sets

maxCellEUTRA INTEGER ::= 8 \-- Maximum number of E-UTRA cells in SIB
list

maxEUTRA-Carrier INTEGER ::= 8 \-- Maximum number of E-UTRA carriers in
SIB list

maxPLMNIdentities INTEGER ::= 8 \-- Maximum number of PLMN identities in
RAN area configurations

maxDownlinkFeatureSets INTEGER ::= 1024 \-- (for NR DL) Total number of
FeatureSets (size of the pool)

maxUplinkFeatureSets INTEGER ::= 1024 \-- (for NR UL) Total number of
FeatureSets (size of the pool)

maxEUTRA-DL-FeatureSets INTEGER ::= 256 \-- (for E-UTRA) Total number of
FeatureSets (size of the pool)

maxEUTRA-UL-FeatureSets INTEGER ::= 256 \-- (for E-UTRA) Total number of
FeatureSets (size of the pool)

maxFeatureSetsPerBand INTEGER ::= 128 \-- (for NR) The number of feature
sets associated with one band.

maxPerCC-FeatureSets INTEGER ::= 1024 \-- (for NR) Total number of
CC-specific FeatureSets (size of the pool)

maxFeatureSetCombinations INTEGER ::= 1024 \-- (for MR-DC/NR)Total
number of Feature set combinations (size of the pool)

maxInterRAT-RSTD-Freq INTEGER ::= 3

maxGIN-r17 INTEGER ::= 24 \-- Maximum number of broadcast GINs

maxHRNN-Len-r16 INTEGER ::= 48 \-- Maximum length of HRNNs

maxNPN-r16 INTEGER ::= 12 \-- Maximum number of NPNs broadcast and
reported by UE at establishment

maxSNPN-ConfigCellId-r18 INTEGER ::= 32 \-- Maximum number of Cell ID
subject for SNPNS for MDT scope

maxSNPN-ConfigID-r18 INTEGER ::= 16 \-- Maximum number of SNPNs subject
for MDT scope

maxSNPN-ConfigTAI-r18 INTEGER ::= 8 \-- Maximum number of TA subject for
MDT scope

maxNrOfMinSchedulingOffsetValues-r16 INTEGER ::= 2 \-- Maximum number of
min. scheduling offset (K0/K2) configurations

maxK0-SchedulingOffset-r16 INTEGER ::= 16 \-- Maximum number of slots
configured as min. scheduling offset (K0)

maxK2-SchedulingOffset-r16 INTEGER ::= 16 \-- Maximum number of slots
configured as min. scheduling offset (K2)

maxK0-SchedulingOffset-r17 INTEGER ::= 64 \-- Maximum number of slots
configured as min. scheduling offset (K0)

maxK2-SchedulingOffset-r17 INTEGER ::= 64 \-- Maximum number of slots
configured as min. scheduling offset (K2)

maxDCI-2-6-Size-r16 INTEGER ::= 140 \-- Maximum size of DCI format 2-6

maxDCI-2-7-Size-r17 INTEGER ::= 43 \-- Maximum size of DCI format 2-7

maxDCI-2-6-Size-1-r16 INTEGER ::= 139 \-- Maximum DCI format 2-6 size
minus 1

maxDCI-2-9-Size-r18 INTEGER ::= 140 \-- Maximum DCI format 2-9 size

maxDCI-2-9-Size-1-r18 INTEGER ::= 139 \-- Maximum DCI format 2-9 size
minus 1

maxNrofUL-Allocations-r16 INTEGER ::= 64 \-- Maximum number of PUSCH
time domain resource allocations

maxNrofUL-Allocations-1-r18 INTEGER ::= 63 \-- Maximum number of PUSCH
time domain resource allocations minus 1

maxNrofP0-PUSCH-Set-r16 INTEGER ::= 2 \-- Maximum number of P0 PUSCH
set(s)

maxOnDemandSIB-r16 INTEGER ::= 8 \-- Maximum number of SIB(s) that can
be requested on-demand

maxOnDemandPosSIB-r16 INTEGER ::= 32 \-- Maximum number of posSIB(s)
that can be requested on-demand

maxCI-DCI-PayloadSize-r16 INTEGER ::= 126 \-- Maximum number of the DCI
size for CI

maxCI-DCI-PayloadSize-1-r16 INTEGER ::= 125 \-- Maximum number of the
DCI size for CI minus 1

maxUu-RelayRLC-ChannelID-r17 INTEGER ::= 32 \-- Maximum value of Uu
Relay RLC channel ID

maxWLAN-Id-Report-r16 INTEGER ::= 32 \-- Maximum number of WLAN IDs to
report

maxWLAN-Name-r16 INTEGER ::= 4 \-- Maximum number of WLAN name

maxRAReport-r16 INTEGER ::= 8 \-- Maximum number of RA procedures
information to be included in the RA report

maxTxConfig-r16 INTEGER ::= 64 \-- Maximum number of sidelink
transmission parameters configurations

maxTxConfig-1-r16 INTEGER ::= 63 \-- Maximum number of sidelink
transmission parameters configurations minus 1

maxPSSCH-TxConfig-r16 INTEGER ::= 16 \-- Maximum number of PSSCH TX
configurations

maxNrofCLI-RSSI-Resources-r16 INTEGER ::= 64 \-- Maximum number of
CLI-RSSI resources for UE

maxNrofCLI-RSSI-Resources-1-r16 INTEGER ::= 63 \-- Maximum number of
CLI-RSSI resources for UE minus 1

maxNrofCLI-SRS-Resources-r16 INTEGER ::= 32 \-- Maximum number of SRS
resources for CLI measurement for UE

maxCLI-Report-r16 INTEGER ::= 8

maxNrofCC-Group-r17 INTEGER ::= 16 \-- Maximum number of CC groups for
DC location report

maxNrofConfiguredGrantConfig-r16 INTEGER ::= 12 \-- Maximum number of
configured grant configurations per BWP

maxNrofConfiguredGrantConfig-1-r16 INTEGER ::= 11 \-- Maximum number of
configured grant configurations per BWP minus 1

maxNrofCG-Type2DeactivationState INTEGER ::= 16 \-- Maximum number of
deactivation state for type 2 configured grants per BWP

maxNrofConfiguredGrantConfigMAC-1-r16 INTEGER ::= 31 \-- Maximum number
of configured grant configurations per MAC entity minus 1

maxNrofCSI-ReportSubconfigPerCSI-ReportConfig-r18 INTEGER ::= 8 \--
Maximum number of CSI report subconfigurations per CSI report

\-- configuration

maxNrofCSI-ReportSubconfigPerCSI-ReportConfig-1-r18 INTEGER ::= 7 \--
Maximum number of CSI report subconfigurations per CSI report

\-- configuration minus 1

maxNrofSPS-Config-r16 INTEGER ::= 8 \-- Maximum number of SPS
configurations per BWP

maxNrofSPS-Config-1-r16 INTEGER ::= 7 \-- Maximum number of SPS
configurations per BWP minus 1

maxNrofSPS-DeactivationState INTEGER ::= 16 \-- Maximum number of
deactivation state for SPS per BWP

maxNrofPPW-Config-r17 INTEGER ::= 4 \-- Maximum number of Preconfigured
PRS processing windows per DL BWP

maxNrofPPW-ID-1-r17 INTEGER ::= 15 \-- Maximum number of Preconfigured
PRS processing windows minus 1

maxNrOfTxTEGReport-r17 INTEGER ::= 256 \-- Maximum number of UE Tx
Timing Error Group Report

maxNrOfTxTEG-ID-1-r17 INTEGER ::= 7 \-- Maximum number of UE Tx Timing
Error Group ID minus 1

maxNrofPagingSubgroups-r17 INTEGER ::= 8 \-- Maximum number of paging
subgroups per paging occasion

maxNrofPUCCH-ResourceGroups-1-r16 INTEGER ::= 3

maxNrofReqComDC-Location-r17 INTEGER ::= 128 \-- Maximum number of
requested carriers/BWPs combinations for DC location

\-- report

maxNrofServingCellsTCI-r16 INTEGER ::= 32 \-- Maximum number of serving
cells in simultaneousTCI-UpdateList

maxNrofTxDC-TwoCarrier-r16 INTEGER ::= 64 \-- Maximum number of UL Tx DC
locations reported by the UE for 2CC uplink CA

maxNrofRB-SetGroups-r17 INTEGER ::= 8 \-- Maximum number of RB set
groups

maxNrofRB-Sets-r17 INTEGER ::= 8 \-- Maximum number of RB sets

maxNrofEnhType3HARQ-ACK-r17 INTEGER ::= 8 \-- Maximum number of enhanced
type 3 HARQ-ACK codebook

maxNrofEnhType3HARQ-ACK-1-r17 INTEGER ::= 7 \-- Maximum number of
enhanced type 3 HARQ-ACK codebook minus 1

maxNrofPRS-ResourcesPerSet-r17 INTEGER ::= 64 \-- Maximum number of PRS
resources for one set

maxNrofPRS-ResourcesPerSet-1-r17 INTEGER ::= 63 \-- Maximum number of
PRS resources for one set minus 1

maxNrofPRS-ResourceOffsetValue-1-r17 INTEGER ::= 511

maxNrofGapId-r17 INTEGER ::= 8 \-- Maximum number of measurement gap ID

maxNrofPreConfigPosGapId-r17 INTEGER ::= 16 \-- Maximum number of
preconfigured positioning measurement gap

maxNrOfGapPri-r17 INTEGER ::= 16 \-- Maximum number of gap priority
level

maxCEFReport-r17 INTEGER ::= 4 \-- Maximum number of CEF reports by the
UE

maxNrofMultiplePDSCHs-r17 INTEGER ::= 8 \-- Maximum number of PDSCHs in
PDSCH TDRA list

maxSliceInfo-r17 INTEGER ::= 8 \-- Maximum number of NSAGs

maxCellSlice-r17 INTEGER ::= 16 \-- Maximum number of cells supporting
the NSAG

maxNrofTRS-ResourceSets-r17 INTEGER ::= 64 \-- Maximum number of TRS
resource sets

maxNrofSearchSpaceGroups-1-r17 INTEGER ::= 2 \-- Maximum number of
search space groups minus 1

maxNrofRemoteUE-r17 INTEGER ::= 32 \-- Maximum number of connected L2
U2N Remote UEs

maxDCI-4-2-Size-r17 INTEGER ::= 140 \-- Maximum size of DCI format 4-2

maxFreqMBS-r17 INTEGER ::= 16 \-- Maximum number of MBS frequencies
reported in MBSInterestIndication

maxNrofDRX-ConfigPTM-r17 INTEGER ::= 64 \-- Max number of DRX
configuration for PTM provided in MBS broadcast in a

\-- cell

maxNrofDRX-ConfigPTM-1-r17 INTEGER ::= 63 \-- Max number of DRX
configuration for PTM provided in MBS broadcast in a

\-- cell minus 1

maxNrofMBS-ServiceListPerUE-r17 INTEGER ::= 16 \-- Maximum number of
services which the UE can include in the MBS interest

\-- indication

maxNrofMBS-Session-r17 INTEGER ::= 1024 \-- Maximum number of MBS
sessions provided in MBS broadcast or multicast in

\-- a cell

maxNrofMTCH-SSB-MappingWindow-r17 INTEGER ::= 16 \-- Maximum number of
MTCH to SSB beam mapping pattern

maxNrofMTCH-SSB-MappingWindow-1-r17 INTEGER ::= 15 \-- Maximum number of
MTCH to SSB beam mapping pattern minus 1

maxNrofMRB-Broadcast-r17 INTEGER ::= 4 \-- Maximum number of broadcast
MRBs configured for one MBS broadcast service

maxNrofPageGroup-r17 INTEGER ::= 32 \-- Maximum number of paging groups
in a paging message

maxNrofPDSCH-ConfigPTM-r17 INTEGER ::= 16 \-- Maximum number of PDSCH
configuration groups for PTM

maxNrofPDSCH-ConfigPTM-1-r17 INTEGER ::= 15 \-- Maximum number of PDSCH
configuration groups for PTM minus 1

maxG-RNTI-r17 INTEGER ::= 16 \-- Maximum number of G-RNTI that can be
configured for a UE.

maxG-RNTI-1-r17 INTEGER ::= 15 \-- Maximum number of G-RNTI that can be
configured for a UE minus 1.

maxG-CS-RNTI-r17 INTEGER ::= 8 \-- Maximum number of G-CS-RNTI that can
be configured for a UE.

maxG-CS-RNTI-1-r17 INTEGER ::= 7 \-- Maximum number of G-CS-RNTI that
can be configured for a UE minus 1.

maxMRB-r17 INTEGER ::= 32 \-- Maximum number of multicast MRBs (that can
be added in MRB-ToAddModLIst)

maxFSAI-MBS-r17 INTEGER ::= 64 \-- Maximum number of MBS frequency
selection area identities

maxNeighCellMBS-r17 INTEGER ::= 8 \-- Maximum number of MBS broadcast
neighbour cells

maxNrofPdcch-BlindDetectionMixed-1-r16 INTEGER ::= 7 \-- Maximum number
of combinations of mixed Rel-16 and Rel-15 PDCCH

\-- monitoring capabilities minus 1

maxNrofPdcch-BlindDetection-r17 INTEGER ::= 16 \-- Maximum number of
combinations of PDCCH blind detection monitoring

\-- capabilities

maxNrofAltitudeRanges-r18 INTEGER ::= 8 \-- Maximum number of altitude
ranges for altitude-based measurement configurations

maxWayPoint-r18 INTEGER ::= 20 \-- Maximum number of flight path
information waypoints

maxAltitude-r18 INTEGER ::= 10000 \-- Maximum altitude in meters

minAltitude-r18 INTEGER ::= -420 \-- Minimum altitude in meters

maxMeasSequence-r18 INTEGER ::= 64 \-- Maximum number of configured
sequence for measurement

maxNrofHops-1-r18 INTEGER ::= 5 \-- Maximum number of Hops that can be
configured for Positioning SRS Transmission

maxNrOfCellsInVA-r18 INTEGER ::= 16 \-- Maximum number of cells in
validity area for Positioning SRS

maxNrOfCellsInVA-Ext-r18 INTEGER ::= 16 \-- Maximum number of additional
cells in validity area for Positioning SRS

maxNrOfLinkedSRS-PosResourceSet-r18 INTEGER ::= 3 \-- Maximum number of
linked SRSPosResourceSets that can be aggregated across

\-- CCs

maxNrOfLinkedSRS-PosResSetComb-r18 INTEGER ::= 32 \-- Maximum number of
combinations of linked SRSPosResourceSets that can be

\-- aggregated in RRC_CONNECTED state

maxNrOfLinkedSRS-PosResSetCombInactive-r18 INTEGER ::= 16 \-- Maximum
number of combinations of linked SRSPosResourceSets that can be

\-- aggregated in RRC_INACTIVE state

maxCBR-ConfigDedSL-PRS-1-r18 INTEGER ::= 7 \-- Maximum number of CBR
ranges for dedicated SL PRS resource pool

maxCBR-LevelDedSL-PRS-1-r18 INTEGER ::= 15 \-- Maximum number of CBR
levels for dedicated SL PRS resource pool

maxNrofSL-PRS-TxPool-r18 INTEGER ::= 8 \-- Maximum number of Tx
dedicated SL-PRS resource pool for NR sidelink positioning

maxNrofSL-PRS-TxConfig-r18 INTEGER ::= 64 \-- Maximum number of SL PRS
transmission parameter configurations

maxNrOfVA-r18 INTEGER ::= 16 \-- Maximum number of validity area

maxNrofLTM-Configs-r18 INTEGER ::= 8 \-- Maximum number of LTM candidate
cells

maxNrofLTM-Configs-plus1-r18 INTEGER ::= 9 \-- Maximum number of LTM
candidate cells plus 1

maxNrofLTM-CSI-ReportConfigurations-r18 INTEGER ::= 48 \-- Maximum
number of LTM CSI reporting configurations

maxNrofLTM-CSI-ReportConfigurations-1-r18 INTEGER ::= 47 \-- Maximum
number of LTM CSI reporting configurations minus 1

maxNrofLTM-CSI-SSB-ResourcesPerSet-r18 INTEGER ::= 512 \-- Maximum
number of LTM CSI SSB resource per set

maxNrofLTM-CSI-ResourceConfigurations-r18 INTEGER ::= 112 \-- Maximum
number of LTM CSI resource configurations

maxNrofLTM-CSI-ResourceConfigurations-1-r18 INTEGER ::= 111 \-- Maximum
number of LTM CSI resource configurations minus 1

maxNrofCandidateTCI-State-r18 INTEGER ::= 128 \-- Maximum number of LTM
TCI states

maxNrofCandidateUL-TCI-r18 INTEGER ::= 64 \-- Maximum number of LTM UL
TCI states

maxSecurityCellSet-r18 INTEGER ::= 9 \-- Maximum number of cell sets for
subsequent CPAC.

maxSK-Counter-r18 INTEGER ::= 8 \-- Maximum number of SK-counters
configured for a cell set for subsequent CPAC.

maxNrofThresholdMBS-r18 INTEGER ::= 8 \-- Max number of thresholds of
MBS sessions for RRC connection resume for a

\-- UE receiving multicast in RRC_INACTIVE

maxNrofThresholdMBS-1-r18 INTEGER ::= 7 \-- Max number of thresholds of
MBS sessions for RRC connection resume for a

\-- UE receiving multicast in RRC_INACTIVE minus 1

maxTN-AreaInfo-r18 INTEGER ::= 32 \-- Maximum number of TN coverage
areas for which assistance info is

\-- provided in an NTN cell

maxNrofSetsOfCells-r18 INTEGER ::= 4 \-- Maximum number of sets of cells
for multi-cell PDSCH/PUSCH scheduling

maxNrofSetsOfCells-1-r18 INTEGER ::= 3 \-- Maximum number of sets of
cells for multi-cell PDSCH/PUSCH scheduling

\-- minus 1

maxNrofCellsInSet-r18 INTEGER ::= 4 \-- Maximum number of cells
configured in a set of cells for multi-cell

\-- PDSCH/PUSCH scheduling

maxNrofCellsInSet-1-r18 INTEGER ::= 3 \-- Maximum number of cells
configured in a set of cells for multi-cell

\-- PDSCH/PUSCH scheduling minus 1

maxNrofCellCombos-r18 INTEGER ::= 16 \-- Maximum number of combinations
of co-scheduled cells for multi-cell

\-- PDSCH/PUSCH scheduling

maxNrofBWPsInSetOfCells-r18 INTEGER ::= 16 \-- Maximum number of BWPs
configured in a set of cells for multi-cell

\-- PDSCH/PUSCH scheduling

maxLowerMSD-r18 INTEGER ::= 256 \-- Maximum number of lower MSD
capability sets for a victim band

maxLowerMSDInfo-r18 INTEGER ::= 64 \-- Maximum number of lower MSD
capability sets for a band combination

maxNrofIntraEndc-Components-r17 INTEGER ::= 4 \-- Maximum number of
intra-band (NG)EN-DC band components in an inter-band

\-- (NG)EN-DC band combination

\-- TAG-MULTIPLICITY-AND-TYPE-CONSTRAINT-DEFINITIONS-STOP

\-- ASN1STOP

### -- End of NR-RRC-Definitions

\-- ASN1START

END

\-- ASN1STOP