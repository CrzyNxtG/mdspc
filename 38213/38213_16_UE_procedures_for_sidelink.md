# 16 UE procedures for sidelink

For a carrier, a UE is provided by *SL-BWP-Config* or
*SL-BWP-ConfigCommon* a BWP for SL transmissions (SL BWP) with
numerology and resource grid determined as described in \[4, TS
38.211\].

For a resource pool within the SL BWP,

\- for operation without shared spectrum channel access, or for
operation with shared spectrum channel access and when
*sl-TransmissionStructureForPSCCHandPSSCH* = \'contiguousRB\', the UE is
provided by *sl-NumSubchannel* a number of sub-channels where each
sub-channel includes a number of contiguous RBs provided by
*sl-SubchannelSize*. The first RB of the first sub-channel in the SL BWP
is indicated by *sl-StartRB-Subchannel*

\- for operation with shared spectrum channel access and when
*sl-TransmissionStructureForPSCCHandPSSCH* = \'interlaceRB\'*,* the UE
is provided a number of sub-channels in each RB set which is equal to
the number of interlaces in each RB set divided by the number of
interlaces per sub-channel, provided by *sl-NumInterlacePerSubchannel*,
and the interlaces have contiguous interlace indexes

Available slots for a resource pool are provided by *sl-TimeResource*
and occur with a periodicity of 10240 ms. For operation without shared
spectrum channel access and for an available slot without S-SS/PSBCH
blocks, SL transmissions can start from a first symbol indicated by
*sl-StartSymbol* and be within a number of consecutive symbols indicated
by *sl-LengthSymbols*. For operation with shared spectrum channel access
and for an available slot without S-SS/PSBCH blocks, SL transmissions
can start from a first symbol indicated by *sl-StartingSymbolFirst* and
be within a number of consecutive symbols indicated by
*sl-LengthSymbols*, or from a second symbol indicated by
*sl-StartingSymbolSecond* \[6, TS 38.214\], where the ending symbol of
SL transmissions starting from the first symbol is same as the ending
symbol of SL transmissions starting from the second symbol. For an
available slot with S-SS/PSBCH blocks, the first symbol and the number
of consecutive symbols are predetermined.

The UE expects to use a same numerology in the SL BWP and in an active
UL BWP in a same carrier of a same cell. If the active UL BWP numerology
is different than the SL BWP numerology, the SL BWP is deactivated.

A priority of a PSSCH according to NR radio access or according to
E-UTRA radio access is indicated by a priority field in a respective
scheduling SCI format. A priority of a PSSS/SSSS/PSBCH according to
E-UTRA radio access is provided by *sl-SSB-PriorityEUTRA* \[13, TS
36.213\]. A priority of an S-SS/PSBCH block is provided by
*sl-SSB-PriorityNR*. A priority of a PSFCH is determined as described in
clause 16.2.4.2.

A UE does not expect to be provided search space sets associated with
CORESETs on more than one cell to monitor PDCCH for detection of DCI
format 3_0 or DCI format 3_1 or DCI format 3_2.