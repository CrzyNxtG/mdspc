## 11.2 Interrupted transmission indication

If a UE is provided *DownlinkPreemption*, the UE is configured with an
INT-RNTI provided by *int-RNTI* for monitoring PDCCH conveying DCI
format 2_1 \[5, TS 38.212\]. The UE is additionally configured with

\- a set of serving cells by *int-ConfigurationPerServingCell* that
includes a set of serving cell indexes provided by corresponding
*servingCellId* and a corresponding set of locations for fields in DCI
format 2_1 by *positionInDCI*

\- an information payload size for DCI format 2_1 by *dci-PayloadSize*

\- an indication granularity for time-frequency resources by
*timeFrequencySet*

If a UE detects a DCI format 2_1 for a serving cell from the configured
set of serving cells, the UE may assume that no transmission to the UE
is present in PRBs and in symbols that are indicated by the DCI format
2_1, from a set of PRBs and a set of symbols of the last monitoring
period. The indication by the DCI format 2_1 is not applicable to
receptions of SS/PBCH blocks.

The set of PRBs is equal to the active DL BWP as defined in clause 12
and includes ![](media/image173.wmf){width="0.3020833333333333in"
height="0.19791666666666666in"} PRBs.

If a UE detects a DCI format 2_1 in a PDCCH reception in a slot, the set
of symbols is the last
![](media/image174.wmf){width="1.1041666666666667in"
height="0.2604166666666667in"} symbols prior to the first symbol of the
PDCCH reception in the slot where
![](media/image175.wmf){width="0.3020833333333333in"
height="0.19791666666666666in"} is the PDCCH monitoring periodicity
provided by the value of *monitoringSlotPeriodicityAndOffset,* as
described in clause 10.1,
![](media/image176.wmf){width="0.3854166666666667in"
height="0.2604166666666667in"} is the number of symbols per slot,
![](media/image177.wmf){width="0.125in" height="0.17708333333333334in"}
is the SCS configuration for a serving cell with mapping to a respective
field in the DCI format 2_1,
![](media/image178.wmf){width="0.2604166666666667in"
height="0.19791666666666666in"} is the SCS configuration of the DL BWP
where the UE receives the PDCCH with the DCI format 2_1. If the UE is
provided *tdd-UL-DL-ConfigurationCommon*, symbols indicated as uplink by
*tdd-UL-DL-ConfigurationCommon* are excluded from the last
![](media/image179.wmf){width="1.1041666666666667in"
height="0.2604166666666667in"} symbols prior to the first symbol of the
PDCCH reception in the slot. The resulting set of symbols includes a
number of symbols that is denoted as
![](media/image180.wmf){width="0.3020833333333333in"
height="0.19791666666666666in"}.

The UE does not expect to be provided values of
![](media/image177.wmf){width="0.125in" height="0.17708333333333334in"},
![](media/image181.wmf){width="0.28125in"
height="0.19791666666666666in"}, and
![](media/image175.wmf){width="0.3020833333333333in"
height="0.19791666666666666in"} resulting to a value of
![](media/image182.wmf){width="1.1041666666666667in"
height="0.2604166666666667in"} that is not an integer. The UE does not
expect to be configured by *monitoringSymbolsWithinSlot* with more than
one PDCCH monitoring occasion for DCI format 2_1 in a slot.

A UE is provided the indication granularity for the set of PRBs and for
the set of symbols by *timeFrequencySet*.

If the value of *timeFrequencySet* is \'set0\', 14 bits from MSB of a
field in DCI format 2_1 have a one-to-one mapping with 14 groups of
consecutive symbols from the set of symbols where each of the first
![](media/image183.wmf){width="1.1979166666666667in"
height="0.19791666666666666in"} symbol groups includes
![](media/image184.wmf){width="0.6145833333333334in"
height="0.20833333333333334in"} symbols, each of the last
![](media/image185.wmf){width="1.5104166666666667in"
height="0.19791666666666666in"} symbol groups includes
![](media/image186.wmf){width="0.6145833333333334in"
height="0.19791666666666666in"} symbols, a bit value of 0 indicates
transmission to the UE in the corresponding symbol group and a bit value
of 1 indicates no transmission to the UE in the corresponding symbol
group.

If the value of *timeFrequencySet* is \'set1\', 7 pairs of bits from MSB
of a field in the DCI format 2_1 have a one-to-one mapping with 7 groups
of consecutive symbols where each of the first
![](media/image187.wmf){width="1.1041666666666667in"
height="0.19791666666666666in"} symbol groups includes
![](media/image188.wmf){width="0.6145833333333334in"
height="0.19791666666666666in"} symbols, each of the last
![](media/image189.wmf){width="1.3020833333333333in"
height="0.19791666666666666in"} symbol groups includes
![](media/image190.wmf){width="0.6145833333333334in"
height="0.19791666666666666in"} symbols, a first bit in a pair of bits
for a symbol group is applicable to the subset of first
![](media/image191.wmf){width="0.6145833333333334in"
height="0.19791666666666666in"} PRBs from the set of
![](media/image173.wmf){width="0.3020833333333333in"
height="0.19791666666666666in"} PRBs, a second bit in the pair of bits
for the symbol group is applicable to the subset of last
![](media/image192.wmf){width="0.5104166666666666in"
height="0.19791666666666666in"} PRBs from the set of
![](media/image173.wmf){width="0.3020833333333333in"
height="0.19791666666666666in"} PRBs, a bit value of 0 indicates
transmission to the UE in the corresponding symbol group and subset of
PRBs, and a bit value of 1 indicates no transmission to the UE in the
corresponding symbol group and subset of PRBs.