### 9.3.1 UE procedure for reporting UTO-UCI

If the UE is provided *nrofBitsInUTO-UCI* with value equal to
$O^{UTO - UCI}$ in *configuredGrantConfig* of a CG-PUSCH configuration,
the UE multiplexes UTO-UCI represented by a bitmap of $O^{UTO - UCI}$
bits in each CG-PUSCH transmission for the CG-PUSCH configuration. The
$O^{UTO - UCI}$ bits of UTO-UCI,
${\widetilde{o}}_{0}^{UTO - UCI},\ {\widetilde{o}}_{1}^{UTO - UCI},\ \ldots,\ {\widetilde{o}}_{O^{UTO - UCI} - 1}^{UTO - UCI}$,
have a one-to-one mapping to $O^{UTO - UCI}$ subsequent CG-PUSCH TOs of
the CG-PUSCH configuration in ascending order of start time. For
unpaired spectrum operation, the $O^{UTO - UCI}$ subsequent CG-PUSCH TOs
exclude invalid ones where a UE does not transmit a PUSCH due to
collision of the PUSCH with DL symbol(s) indicated by
*tdd-UL-DL-ConfigurationCommon* or *tdd-UL-DL-ConfigurationDedicated* if
provided, or with symbol(s) of an SS/PBCH block with index provided by
*ssb-PositionsInBurst*, based on the procedures in Clause 11.1. A bit
value of \'0\' indicates that the UE may transmit CG-PUSCH, and a bit
value of \'1\' indicates that the UE will not transmit CG-PUSCH, in a
corresponding CG-PUSCH TO. When the UE indicates by UTO-UCI a value of
\'1\' for a CG-PUSCH TO, the UE continues to indicate the value of \'1\'
for the CG-PUSCH TO by UTO-UCI multiplexed in subsequent CG-PUSCH
transmissions, and the UE does not transmit CG-PUSCH in the CG-PUSCH TO.