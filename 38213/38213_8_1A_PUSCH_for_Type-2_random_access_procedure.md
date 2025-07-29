## 8.1A PUSCH for Type-2 random access procedure

For a Type-2 random access procedure, a UE transmits a PUSCH, when
applicable, after transmitting a PRACH. The UE encodes a transport block
provided for the PUSCH transmission using redundancy version number 0.
The PUSCH transmission is after the PRACH transmission by at least $N$
symbols where $N = 2$ for $\mu = 0$ or $\mu = 1$, $N = 4$ for $\mu = 2$
or $\mu = 3$, $N = 16$ for $\mu = 5$, $N = 32$ for $\mu = 6$, and $\mu$
is the SCS configuration for the active UL BWP.

A UE does not transmit a PUSCH in a PUSCH occasion if the PUSCH occasion
associated with a DMRS resource is not mapped to a preamble of valid
PRACH occasions or if the associated PRACH preamble is not transmitted
as described in clause 7.5 or clause 11.1 or clause 15 or clause 17.2. A
UE can transmit a PRACH preamble in a valid PRACH occasion if the PRACH
preamble is not mapped to a valid PUSCH occasion.

A mapping between one or multiple PRACH preambles and a PUSCH occasion
associated with a DMRS resource is per PUSCH configuration provided by
*MsgA-PUSCH-Resource*.

A UE determines time resources and frequency resources for PUSCH
occasions in an active UL BWP from *msgA-PUSCH-Config* or
*separateMsgA-PUSCH-Config* for the active UL BWP. If the active UL BWP
is not the initial UL BWP and *msgA-PUSCH-Config* or
*separateMsgA-PUSCH-Config* is not provided for the active UL BWP, the
UE uses the *msgA-PUSCH-Config* or *separateMsgA-PUSCH-Config* provided
for the initial UL BWP.

A UE determines a first interlace or first RB for a first PUSCH occasion
in an active UL BWP respectively from *interlaceIndexFirstPO-MsgA-PUSCH*
or from *frequencyStartMsgA-PUSCH* that provides an offset, in number of
RBs in the active UL BWP, from a first RB of the active UL BWP. A PUSCH
occasion includes a number of interlaces or a number of RBs provided by
*nrofInterlacesPerMsgA-PO* or by *nrofPRBs-perMsgA-PO*, respectively.
Consecutive PUSCH occasions in the frequency domain of an UL BWP are
separated by a number of RBs provided by *guardBandMsgA-PUSCH*. A number
$N_{f}\mathbf{\ }$of PUSCH occasions in the frequency domain of an UL
BWP is provided by *nrofMsgA-PO-FDM*.

For operation with shared spectrum channel access, if the PUSCH occasion
is provided by higher layer parameters *frequencyStartMsgA-PUSCH* and
*nrofPRBs-perMsgA-PO*, the UE expects a PUSCH occasion to be confined
within the same RB set as the corresponding PRACH transmission.

For operation with shared spectrum channel access, if the PUSCH occasion
is provided by higher layer parameters
*interlaceIndexFirstPO-MsgA-PUSCH* and *nrofInterlacesPerMsgA-PO*, the
RB set for the PUSCH occasion in the active UL BWP is the same RB set as
the corresponding PRACH transmission. The UE assumes that the RB set is
defined as when the UE is not provided *intraCellGuardBandsPerSCS* for
an UL carrier as described in clause 7 of \[6, TS 38.214\].

If a UE does not have dedicated RRC configuration, or has an initial UL
BWP as an active UL BWP, or is not provided
*startSymbolAndLengthMsgA-PO*, *msgA-PUSCH-timeDomainAllocation*
provides a SLIV and a PUSCH mapping type for a PUSCH transmission by
indicating

\- one of the first *maxNrofUL-Allocations* values from
*PUSCH-TimeDomainResourceAllocationList*, if
*PUSCH-TimeDomainResourceAllocationList* is provided in
*PUSCH-ConfigCommon*

\- one of the entries from table 6.1.2.1.1-2 or table 6.1.2.1.1-3 in
\[6, TS 38.214\], if *PUSCH-TimeDomainResourceAllocationList* is not
provided in *PUSCH-ConfigCommon*

else, the UE is provided a SLIV by *startSymbolAndLengthMsgA-PO*, and a
PUSCH mapping type by *mappingTypeMsgA-PUSCH* for a PUSCH transmission.

For mapping one or multiple preambles of a PRACH slot to a PUSCH
occasion associated with a DMRS resource, a UE determines a first slot
for a first PUSCH occasion in an active UL BWP from
*msgA-PUSCH-TimeDomainOffset* that provides an offset, in number of
slots in the active UL BWP, relative to the start of a PUSCH slot
including the start of each PRACH slot. The UE does not expect to have a
PRACH preamble transmission and a PUSCH transmission with a msgA in a
PRACH slot or in a PUSCH slot, or to have overlapping msgA PUSCH
occasions for a MsgA PUSCH configuration. The UE expects that a first
PUSCH occasion in each slot has a same SLIV for a PUSCH transmission
that is provided by *startSymbolAndLengthMsgA-PO* or
*msgA-PUSCH-timeDomainAllocation* \[6, TS 38.214\].

Consecutive PUSCH occasions within each slot are separated by
*guardPeriodMsgA-PUSCH* symbols and have same duration. A number $N_{t}$
of time domain PUSCH occasions in each slot is provided by
*nrofMsgA-PO-perSlot* and a number $N_{s}$ of consecutive slots that
include PUSCH occasions is provided by *nrofSlotsMsgA-PUSCH*.

A UE is provided a DMRS configuration for a PUSCH transmission in a
PUSCH occasion in an active UL BWP by *msgA-DMRS-Config*.

A UE is provided an MCS for data information in a PUSCH transmission for
a PUSCH occasion by *msgA-MCS*.

For a PUSCH transmission with frequency hopping in a slot, when
indicated by *msgA-intraSlotFrequencyHopping* for the active UL BWP, the
frequency offset for the second hop \[6, TS 38.214\] is determined as
described in clause 8.3, Table 8.3-1 using *msgA-HoppingBits* instead of
$N_{UL,hop}$. If *guardPeriodMsgA-PUSCH* is provided, a first symbol of
the second hop is separated by *guardPeriodMsgA-PUSCH* symbols from the
end of a last symbol of the first hop; otherwise, there is no time
separation of the PUSCH transmission before and after frequency hopping.
If a UE is provided with *useInterlacePUCCH-PUSCH* in
*BWP-UplinkCommon*, the UE shall transmit PUSCH without frequency
hopping. A PUSCH transmission uses a same spatial filter as an
associated PRACH transmission.

A UE determines whether or not to apply transform precoding for a PUSCH
transmission as described in \[6, TS 38.214\].

A PUSCH occasion for PUSCH transmission is defined by a frequency
resource and a time resource, and is associated with a DMRS resource.
The DMRS resources are provided by *msgA-DMRS-Config*.

Each consecutive number of $N_{\text{preamble}}$ preamble indexes from
valid PRACH occasions in a PRACH slot

\- first, in increasing order of preamble indexes within a single PRACH
occasion

\- second, in increasing order of frequency resource indexes for
frequency multiplexed PRACH occasions

\- third, in increasing order of time resource indexes for time
multiplexed PRACH occasions within a PRACH slot

are mapped to a valid PUSCH occasion and the associated DMRS resource

\- first, in increasing order of frequency resource indexes $f_{id}$ for
frequency multiplexed PUSCH occasions

\- second, in increasing order of DMRS resource indexes within a PUSCH
occasion, where a DMRS resource index $DMRS_{id}$ is determined first in
an ascending order of a DMRS port index and second in an ascending order
of a DMRS sequence index \[4, TS 38.211\]

\- third, in increasing order of time resource indexes $t_{id}$ for time
multiplexed PUSCH occasions within a PUSCH slot

\- fourth, in increasing order of indexes for $N_{s}$ PUSCH slots

where
$N_{\text{preamble}} = ceil\left( \frac{T_{\text{preamble}}}{T_{\text{PUSCH}}} \right)$,
$T_{\text{preamble}}$ is a total number of valid PRACH occasions per
association pattern period multiplied by the number of preambles per
valid PRACH occasion provided by *rach-ConfigCommonTwoStepRA*, and
$T_{\text{PUSCH}}$ is a total number of valid PUSCH occasions per PUSCH
configuration per association pattern period multiplied by the number of
DMRS resource indexes per valid PUSCH occasion provided by
*msgA-DMRS-Config*.

A PUSCH occasion is valid if it does not overlap in time and frequency
with any valid PRACH occasion associated with either a Type-1 random
access procedure or a Type-2 random access procedure. Additionally, for
unpaired spectrum and for SS/PBCH blocks with indexes provided by
*ssb-PositionsInBurst* in *SIB1* or by *ServingCellConfigCommon*

\- if a UE is not provided *tdd-UL-DL-ConfigurationCommon*, a PUSCH
occasion is valid if the PUSCH occasion

\- does not precede a SS/PBCH block in the PUSCH slot, and

\- starts at least $N_{\text{gap}}$ symbols after a last SS/PBCH block
symbol, where $N_{\text{gap}}$ is provided in Table 8.1-2 and, if
*channelAccessMode* = \"*semiStatic*\" is provided, does not overlap
with a set of consecutive symbols before the start of a next channel
occupancy time where the UE does not transmit \[15, TS 37.213\].

\- if a UE is provided *tdd-UL-DL-ConfigurationCommon*, a PUSCH occasion
is valid if the PUSCH occasion

\- is within UL symbols, or

\- does not precede a SS/PBCH block in the PUSCH slot, and

\- starts at least $N_{\text{gap}}$ symbols after a last downlink symbol
and at least $N_{\text{gap}}$ symbols after a last SS/PBCH block symbol,
where $N_{\text{gap}}$ is provided in Table 8.1-2 and, if
*channelAccessMode* = \"*semiStatic*\" is provided, does not overlap
with a set of consecutive symbols before the start of a next channel
occupancy time where the UE does not transmit \[15, TS 37.213\].