### 8.4.4 SL PRS reception procedure

The UE may be configured to measure and report one or more of the SL
RSTD, SL Rx-Tx time difference, SL RTOA, SL PRS-RSRPP, for the first
detected path and up to 8 additional detected paths, and SL PRS-RSRP
measurements. The UE may be configured to measure and report one or more
of the SL AoA, SL PRS-RSRPP for the first path and up to 2 additional
detected paths, and SL PRS-RSRP measurement.

The UE may report an ARP ID associated with the reported measurements.
The UE may provide the ARP location information via *ARP-LocationInfo*.

The UE uses the same ARP for both the transmission and reception of
sidelink positioning reference signals while performing an SL Rx-Tx time
difference measurement.

The UE may include SL PRS resource ID(s) when it reports one or more of
the SL RSTD, SL Rx-Tx time difference, SL RTOA, SL AoA, SL PRS-RSRP, and
SL PRS-RSRPP measurements.

For the SL RSTD, SL Rx-Tx time difference, SL RTOA, SL AoA, SL PRS-RSRP,
and SL PRS-RSRPP measurements, the UE reports an associated SL PRS
reception timestamp via higher layer parameter *sl-TimeStamp*. For SL
Rx-Tx time difference, the UE may report an associated SL PRS
transmission timestamp via higher layer parameter *tx-TimeInfo* and the
UE may be configured to report a SL PRS transmission timestamp via
*associatedSL-PRS-TxTimeStampRequest*. The timestamp includes the SFN,
slot number, and optionally *nr-PhysCellID*, *nr-ARFCN*,
*nr-CellGlobalID*, or the timestamp includes DFN, slot number, and
optionally *syncSourceType*.

The UE may be configured to report up to N Rx-Tx time difference
measurements for the same SL PRS transmission associated with N
different SL PRS receptions for the same pair of UE(s). The UE may be
configured to report up to N Rx-Tx time difference measurements for the
same SL PRS reception associated with N different SL PRS transmissions
for the same pair of UE(s).

The UE may report, LoS/NLoS indicator(s) via *los-NLOS-Indicator*
associated with each SL RSTD, SL Rx-Tx time difference, SL RTOA, SL AoA,
SL PRS-RSRP, and SL PRS-RSRPP measurements.

The UE may report synchronization source type via *syncSourceType*
and/or relative time difference with the associated quality metric, via
*sl-RTD-Info*. If reported *syncSourceType* is *gNB-eNB*, the UE may
report cell identity information.

The UE may be provided with synchronization source type of a UE and/or
the relative time difference with the associated quality metric, via
*syncSourceType* and *sl-RTD-Info, respectively*.

For the SL RSTD measurement, the UE may report a reference UE
information.

For SL RTOA measurement, SFN or DFN initialization time may be provided
to the UE by a UE or the network.

The UE may be provided with the location information of other UEs via
*anchorUE-LocationInformation*. The UE may report the location
information of the UE to the network.

The UE may be provided with expected SL AoA and uncertainty range of the
expected SL AoA via *expectedSL-AzimuthAoA, expectedSL-ElevationAoA,
expectedSL-AzimuthAoA-Uncertainty,* and
*expectedSL-ElevationAoA-Uncertainty*.

The UE may report quality metric *sl-TimingQuality* corresponding to the
SL RSTD, SL RTOA or SL Rx-Tx time difference measurements. The UE may
report quality metric *sl-AngleQuality* corresponding to the SL AoA
measurement.

If the *\'SL PRS request\'* field in the SCI associated with the
received SL PRS is set to 1 then this request for SL PRS transmission is
reported to higher layers.