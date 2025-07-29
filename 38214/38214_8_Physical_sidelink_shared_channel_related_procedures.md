# 8 Physical sidelink shared channel related procedures

A UE can be configured by higher layers with one or more sidelink
resource pools. A sidelink resource pool can be for transmission of
PSSCH, as described in Clause 8.1, and/or SL PRS, as described in Clause
8.2.4, or for reception of PSSCH, as described in Clause 8.3, and/or SL
PRS, as described in Clause 8.4.4, and can be associated with either
sidelink resource allocation mode 1 or sidelink resource allocation mode
2.

A sidelink resource pool which can be used for transmission of both SL
PRS and PSSCH will be referred to as shared SL PRS resource pool.

A sidelink resource pool which can be used for transmission of SL PRS
and cannot be used for transmission of PSSCH will be referred to as
dedicated SL PRS resource pool.

In the frequency domain,

\- If the higher layer parameter
*sl-TransmissionStructureForPSCCHandPSSCH* is not provided, or it is set
to \'contiguousRB\', a sidelink resource pool consists of
*sl-NumSubchannel* contiguous sub-channels. A sub-channel consists of
*sl-SubchannelSize* contiguous PRBs, where *sl-NumSubchannel* and
*sl-SubchannelSize* are higher layer parameters.

\- If the higher layer parameter
*sl-TransmissionStructureForPSCCHandPSSCH* is set to \'interlaceRB\', in
the frequency domain, each RB set of a sidelink resource pool consists
of integer number of sub-channels, where each sub-channel consists of
*sl-NumInterlacePerSubchannel* interlaces having contiguous interlace
indices.

For operation with shared spectrum channel access for frequency range 1,
a sidelink resource pool can be (pre-)configured to include integer
number of RB sets, and the lowest RB of the sidelink resource pool is
aligned with the lowest RB of lowest RB set in the resource pool, and
the highest RB of the sidelink resource pool is aligned with the highest
RB of highest RB set in the resource pool. A UE can be provided with
intra-cell guard bands according to the higher layer parameter
*sl-IntraCellGuardBandsSL-List* or according to the nominal intra-cell
guard band and RB set pattern as specified in \[8, TS 38.101-1\] when
the higher layer parameter *sl-intraCellGuardBandsSL-List* is not
configured. The intra-cell guard band PRBs between any two adjacent RB
sets can be used only for PSSCH transmission, if and only if, the UE has
successfully performed channel access procedure in both adjacent RB
sets, and the UE uses both of these RB sets for PSSCH transmission. If
the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH* is
set to 'contiguousRB\', and if more than 1 sub-channel is used for PSSCH
transmission, when the highest sub-channel of PSSCH overlaps with a
single RB set and the highest PRB in the highest sub-channel overlaps
with intra-cell guard band PRBs, the UE can transmit PSSCH on the PRBs
belonging to the allocated sub-channel(s) except for the intra-cell
guard band PRBs within the highest sub-channel. If the higher layer
parameter *sl-TransmissionStructureForPSCCHandPSSCH* is set to
'contiguousRB\', and if more than 1 sub-channel is used for PSSCH
transmission, when the highest sub-channel(s) of PSSCH overlaps with
intra-cell guard band PRBs only, the UE can transmit PSSCH on the PRBs
belonging to the allocated sub-channel(s) except for the intra-cell
guard band PRBs overlapping with the highest sub-channel(s).

The set of slots that may belong to a sidelink resource pool is denoted
by $(t_{0}^{SL},t_{1}^{SL},\cdots,t_{T_{\max} - 1}^{SL})$ where

\- ${0 \leq t}_{i}^{SL} < 10240 \times 2^{\mu},\ 0 \leq i < T_{\max},$

\- the slot index is relative to slot#0 of the radio frame corresponding
to SFN 0 of the serving cell or DFN 0,

\- the set includes all the slots except the following slots,

\- $N_{S - SSB}$ slots in which S-SS/PSBCH block (S-SSB) or additional
transmission occasion for S-SSB is configured,

\- $N_{nonSL}$ slots in each of which at least one of *Y-th*,
*(Y+1)-th*, ..., *(Y+X-1)-th* OFDM symbols are not semi-statically
configured as UL as per the higher layer parameter
*tdd-UL-DL-ConfigurationCommon* of the serving cell if provided or
*sl-TDD-Configuration* if provided or *sl-TDD-Config* of the received
PSBCH if provided, where *X* is set by the higher layer parameters
*sl-LengthSymbols*; and *Y* is set by the higher layer parameter
*sl-StartingSymbolFirst* when *sl-StartingSymbolFirst* and
*sl-StartingSymbolSecond* are provided for a SL-BWP, or *Y* is set by
the higher layer parameter *sl-StartSymbol* otherwise.

\- The reserved slots which are determined by the following steps.

1\) the remaining slots excluding $N_{S - SSB}$ slots and $N_{nonSL}$
slots from the set of all the slots are denoted by
$(l_{0},l_{1},\cdots,l_{(10240 \times 2^{\mu} - N_{S - SSB} - N_{nonSL} - 1)})$
arranged in increasing order of slot index.

2\) a slot
$l_{r}\ (0 \leq r < 10240 \times 2^{\mu} - N_{S - SSB} - N_{nonSL})$
belongs to the reserved slots if
$r = \left\lfloor \frac{m \bullet (10240 \times 2^{\mu} - N_{S - SSB} - N_{nonSL})}{N_{reserved}} \right\rfloor$,
here $m = 0,1,\cdots,N_{reserved} - 1$ and
$N_{reserved} = \left( 10240 \times 2^{\mu} - N_{S - SSB} - N_{nonSL} \right)\ mod\ L_{bitmap}$
where $L_{bitmap}$ denotes the length of bitmap configured by higher
layers.

\- The slots in the set are arranged in increasing order of slot index.

The UE determines the set of logical slots assigned to a sidelink
resource pool as follows:

\- a bitmap $\left( b_{0},b_{1},\ldots,b_{L_{bitmap} - 1} \right)$
associated with the resource pool is used where $L_{bitmap}$ the length
of the bitmap is configured by higher layers.

\- a slot
$t_{k}^{SL}\ (0 \leq k < 10240 \times 2^{\mu} - N_{S - SSB} - N_{nonSL} - N_{reserved})$
belongs to the set if $b_{k'} = 1$ where $k' = k\ mod\ L_{bitmap}$.

\- The slots in the set are re-indexed such that the subscripts *i* of
the remaining slots ${t'}_{i}^{SL}$ are successive {0, 1, ...,
${T'}_{\max} - 1\}$ where ${T'}_{\max}$ is the number of the slots
remaining in the set.

The UE determines the set of resource blocks assigned to a sidelink
resource pool as follows:

> \- The resource block pool consists of $N_{PRB}$ PRBs.
>
> \- If the higher layer parameter
> *sl-TransmissionStructureForPSCCHandPSSCH* is not provided, or is set
> to \'contiguousRB\', the sub-channel *m* for
> $m = 0,1,\cdots,numSubchannel - 1$ consists of a set of
> $n_{subCHsize}$ contiguous resource blocks with the physical resource
> block number
> $n_{PRB} = n_{subCHRBstart} + m \bullet n_{subCHsize} + j$ for
> $j = 0,1,\cdots,n_{subCHsize} - 1$, where $n_{subCHRBstart}$,
> $n_{subCHsize}$ and *numSubchannel* are given by higher layer
> parameters *sl-StartRB-Subchannel*, *sl-SubchannelSize* and
> *sl-NumSubchannel*, respectively.

\- If the higher layer parameter
*sl-TransmissionStructureForPSCCHandPSSCH* is set to \'interlaceRB\',
the sub-channel *m* for $m = 0,1,\cdots,numSubchannel - 1$ consists of a
set of *sl-NumInterlacePerSubchannel* contiguous interlaces, where each
interlace consists of at least 10 resource blocks as defined in clause
4.4.4.6 of \[4, TS 38.211\], *numSubchannel* is equal to the number of
interlaces within one RB set divided by *sl-NumInterlacePerSubchannel*,
and *sl-NumInterlacePerSubchannel* is given by higher layer parameter
*sl-NumInterlacePerSubchannel*. The sub-channel *m* is indexed per RB
set and is periodically indexed across multiple RB sets within the
resource pool. The sub-channel with the same index is mapped to the set
of *sl-NumInterlacePerSubchannel* interlace(s) with the same index(s) in
different RB sets. The sub-channel#0 is mapped to interlaces 0 to
*sl-NumInterlacePerSubchannel-1,* the subchannel #1 is mapped to
interlaces *sl-NumInterlacePerSubchannel* to
*sl-NumInterlacePerSubchannel\*2-1*, and so on.

If the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH*
is not provided, or is set to 'contiguousRB', a UE is not expected to
use the last $N_{PRB}\ \text{mod}\ n_{subCHsize}$ PRBs in the resource
pool, except when the resource pool is a dedicated SL PRS resource pool.

In case of dynamic co-channel coexistence of LTE sidelink and NR
sidelink, the UE expects to be (pre-)configured with 15 kHz SCS or 30
kHz SCS for a SL BWP, for NR sidelink transmissions in 30kHz SCS, the UE
expects that the start of the first symbol of the earlier overlapping NR
SL slot is aligned with the start of the first symbol of the overlapping
LTE SL subframe.