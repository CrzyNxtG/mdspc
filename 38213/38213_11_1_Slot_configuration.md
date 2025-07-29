## 11.1 Slot configuration

A slot format includes downlink symbols, uplink symbols, and flexible
symbols.

The following are applicable for each serving cell.

If a UE is provided *tdd-UL-DL-ConfigurationCommon*, the UE sets the
slot format per slot over a number of slots as indicated by
*tdd-UL-DL-ConfigurationCommon*.

The *tdd-UL-DL-ConfigurationCommon* provides

\- a reference SCS configuration
![](media/image136.wmf){width="0.3020833333333333in"
height="0.22916666666666666in"} by *referenceSubcarrierSpacing*

\- a *pattern1*.

The *pattern1* provides

\- a slot configuration period of
![](media/image137.wmf){width="0.19791666666666666in"
height="0.15625in"} msec by *dl-UL-TransmissionPeriodicity*

\- a number of slots
![](media/image138.wmf){width="0.3020833333333333in" height="0.21875in"}
with only downlink symbols by *nrofDownlinkSlots*

\- a number of downlink symbols
![](media/image139.wmf){width="0.3020833333333333in"
height="0.22916666666666666in"} by *nrofDownlinkSymbols*

\- a number of slots
![](media/image140.wmf){width="0.3020833333333333in"
height="0.22916666666666666in"} with only uplink symbols by
*nrofUplinkSlots*

\- a number of uplink symbols
![](media/image141.wmf){width="0.2604166666666667in"
height="0.2604166666666667in"} by *nrofUplinkSymbols*

A value *P* =0.625 msec is valid only for ${\ \mu}_{ref} = 3$,
${\ \mu}_{ref} = 5\ {or\ \mu}_{ref} = 6$. A value *P* =1.25 msec is
valid only for ${\ \mu}_{ref} = 2,\ {\ \mu}_{ref} = 3$,
${\ \mu}_{ref} = 5\ {or\ \mu}_{ref} = 6$. A value *P* =2.5 msec is valid
only
for${\ \mu}_{ref} = 1,\ {\ \mu}_{ref} = 2,\ {\ \mu}_{ref} = 3$,${\ \mu}_{ref} = 5\ {or\ \mu}_{ref} = 6$.
A value *P* =10 msec is valid only for ${\ \mu}_{ref} = 0$,
${\ \mu}_{ref} = 1,\ {\ \mu}_{ref} = 2,\ {\ \mu}_{ref} = 3$ or
${\ \mu}_{ref} = 5\ $.

A slot configuration period of
![](media/image137.wmf){width="0.19791666666666666in"
height="0.17708333333333334in"} msec includes
![](media/image142.wmf){width="0.6145833333333334in"
height="0.20833333333333334in"} slots with SCS configuration
![](media/image143.wmf){width="0.3020833333333333in"
height="0.2604166666666667in"}. From the
![](media/image144.wmf){width="0.19791666666666666in"
height="0.17708333333333334in"} slots, a first
![](media/image145.wmf){width="0.3020833333333333in"
height="0.2604166666666667in"} slots include only downlink symbols and a
last ![](media/image140.wmf){width="0.3020833333333333in"
height="0.2604166666666667in"} slots include only uplink symbols. The
![](media/image146.wmf){width="0.3020833333333333in"
height="0.2604166666666667in"} symbols after the first
![](media/image145.wmf){width="0.3020833333333333in"
height="0.2604166666666667in"} slots are downlink symbols. The
![](media/image141.wmf){width="0.2604166666666667in"
height="0.2604166666666667in"} symbols before the last
![](media/image140.wmf){width="0.3020833333333333in"
height="0.2604166666666667in"} slots are uplink symbols. The remaining
![](media/image147.wmf){width="1.8020833333333333in"
height="0.2604166666666667in"} are flexible symbols.

The first symbol every
![](media/image148.wmf){width="0.3020833333333333in"
height="0.19791666666666666in"} periods is a first symbol in an even
frame.

If *tdd-UL-DL-ConfigurationCommon* provides both *pattern1* and
*pattern2*, the UE sets the slot format per slot over a first number of
slots as indicated by *pattern1* and the UE sets the slot format per
slot over a second number of slots as indicated by *pattern2*.

The *pattern2* provides

\- a slot configuration period of
![](media/image149.wmf){width="0.17708333333333334in"
height="0.19791666666666666in"} msec by *dl-UL-TransmissionPeriodicity*

\- a number of slots ![](media/image150.wmf){width="0.375in"
height="0.2604166666666667in"} with only downlink symbols by
*nrofDownlinkSlots*

\- a number of downlink symbols ![](media/image151.wmf){width="0.375in"
height="0.2604166666666667in"} by *nrofDownlinkSymbols*

\- a number of slots
![](media/image152.wmf){width="0.3854166666666667in"
height="0.2604166666666667in"} with only uplink symbols by
*nrofUplinkSlots*

\- a number of uplink symbols
![](media/image153.wmf){width="0.3020833333333333in"
height="0.2604166666666667in"} by *nrofUplinkSymbols*

The applicable values of
![](media/image154.wmf){width="0.17708333333333334in"
height="0.19791666666666666in"} are same as the applicable values for
![](media/image137.wmf){width="0.19791666666666666in"
height="0.17708333333333334in"}.

A slot configuration period of
![](media/image155.wmf){width="0.3854166666666667in"
height="0.19791666666666666in"} msec includes first
![](media/image156.wmf){width="0.6145833333333334in"
height="0.19791666666666666in"} slots and second
![](media/image157.wmf){width="0.6979166666666666in" height="0.21875in"}
slots.

From the ![](media/image158.wmf){width="0.125in"
height="0.19791666666666666in"} slots, a first
![](media/image159.wmf){width="0.375in" height="0.2604166666666667in"}
slots include only downlink symbols and a last
![](media/image152.wmf){width="0.3854166666666667in"
height="0.2604166666666667in"} include only uplink symbols. The
![](media/image160.wmf){width="0.3229166666666667in"
height="0.2604166666666667in"} symbols after the first
![](media/image159.wmf){width="0.375in" height="0.2604166666666667in"}
slots are downlink symbols. The
![](media/image161.wmf){width="0.3020833333333333in"
height="0.2604166666666667in"} symbols before the last
![](media/image152.wmf){width="0.3854166666666667in"
height="0.2604166666666667in"} slots are uplink symbols. The remaining
![](media/image162.wmf){width="1.9791666666666667in"
height="0.2604166666666667in"} are flexible symbols.

A UE expects that ![](media/image155.wmf){width="0.3854166666666667in"
height="0.20833333333333334in"} divides 20 msec.

The first symbol every
![](media/image163.wmf){width="0.6979166666666666in"
height="0.19791666666666666in"} periods is a first symbol in an even
frame.

A UE expects that the reference SCS configuration
![](media/image164.wmf){width="0.3020833333333333in" height="0.21875in"}
is smaller than or equal to a SCS configuration
![](media/image165.wmf){width="0.19791666666666666in"
height="0.17708333333333334in"} for any configured DL BWP or UL BWP.
Each slot provided by *pattern1* or *pattern2* is applicable to
![](media/image166.wmf){width="0.3854166666666667in"
height="0.19791666666666666in"} consecutive slots in the active DL BWP
or the active UL BWP where the first slot starts at a same time as a
first slot for the reference SCS configuration
![](media/image164.wmf){width="0.3020833333333333in" height="0.21875in"}
and each downlink or flexible or uplink symbol for the reference SCS
configuration ![](media/image164.wmf){width="0.3020833333333333in"
height="0.21875in"} corresponds to
![](media/image167.wmf){width="0.3854166666666667in"
height="0.19791666666666666in"} consecutive downlink or flexible or
uplink symbols for the SCS configuration
![](media/image165.wmf){width="0.19791666666666666in"
height="0.17708333333333334in"}.

If the UE is additionally provided *tdd-UL-DL-ConfigurationDedicated*,
the parameter *tdd-UL-DL-ConfigurationDedicated* overrides only flexible
symbols per slot over the number of slots as provided by
*tdd-UL-DL-ConfigurationCommon*.

The *tdd-UL-DL-ConfigurationDedicated* provides

\- a set of slot configurations by
*slotSpecificConfigurationsToAddModList*

\- for each slot configuration from the set of slot configurations

\- a slot index for a slot provided by *slotIndex*

\- a set of symbols for a slot by *symbols* where

\- if *symbols* = *allDownlink*, all symbols in the slot are downlink

\- if *symbols* = *allUplink*, all symbols in the slot are uplink

\- if *symbols* = *explicit*, *nrofDownlinkSymbols* provides a number of
downlink first symbols in the slot and *nrofUplinkSymbols* provides a
number of uplink last symbols in the slot. If *nrofDownlinkSymbols* is
not provided, there are no downlink first symbols in the slot and if
*nrofUplinkSymbols* is not provided, there are no uplink last symbols in
the slot. The remaining symbols in the slot are flexible

For each slot having a corresponding index provided by *slotIndex*, the
UE applies a format provided by a corresponding *symbols*. The UE does
not expect *tdd-UL-DL-ConfigurationDedicated* to indicate as uplink or
as downlink a symbol that *tdd-UL-DL-ConfigurationCommon* indicates as a
downlink or as an uplink symbol, respectively.

For each slot configuration provided by
*tdd-UL-DL-ConfigurationDedicated*, a reference SCS configuration is the
reference SCS configuration
![](media/image168.wmf){width="0.25277777777777777in"
height="0.21944444444444444in"} provided by
*tdd-UL-DL-ConfigurationCommon*.

A slot configuration period and a number of downlink symbols, uplink
symbols, and flexible symbols in each slot of the slot configuration
period are determined from *tdd-UL-DL-ConfigurationCommon* and
*tdd-UL-DL-ConfigurationDedicated* and are common to each configured
BWP.

A UE considers symbols in a slot indicated as downlink by
*tdd-UL-DL-ConfigurationCommon*, or *tdd-UL-DL-ConfigurationDedicated*
to be available for receptions and considers symbols in a slot indicated
as uplink by *tdd-UL-DL-ConfigurationCommon*, or by
*tdd*-*UL-DL-ConfigurationDedicated* to be available for transmissions.

If a UE is not configured to monitor PDCCH for DCI format 2_0, for a set
of symbols of a slot that are indicated as flexible by
*tdd-UL-DL-ConfigurationCommon* and *tdd*-*UL-DL-ConfigurationDedicated*
if provided, or when *tdd-UL-DL-ConfigurationCommon* and
*tdd*-*UL-DL-ConfigurationDedicated* are not provided to the UE

\- the UE receives PDSCH or CSI-RS in the set of symbols of the slot if
the UE receives a corresponding indication by a DCI format

\- the UE transmits PUSCH, PUCCH, PRACH, or SRS in the set of symbols of
the slot if the UE receives a corresponding indication by a DCI format,
a RAR UL grant, fallbackRAR UL grant, or successRAR

For operation on a single carrier in unpaired spectrum, if a UE is
configured by higher layers to receive a PDCCH, or a PDSCH, or a CSI-RS,
or a DL PRS in a set of symbols of a slot, the UE receives the PDCCH,
the PDSCH, the CSI-RS, or the DL PRS if the UE does not detect a DCI
format that indicates to the UE to transmit a PUSCH, a PUCCH, a PRACH,
or a SRS in at least one symbol of the set of symbols of the slot;
otherwise, the UE does not receive the PDCCH, or the PDSCH, or the
CSI-RS, or the DL PRS in the set of symbols of the slot.

For a UE operation with shared spectrum channel access in FR1, or in
FR2-2 when the UE is provided *ChannelAccessMode2* = \'*enabled*\', if
the UE is provided *csi-RS-ValidationWithDCI*, is not provided
*CO-DurationsPerCell*, and is not provided
*SlotFormatCombinationsPerCell*, and if the UE is configured by higher
layers to receive a CSI-RS in a set of symbols of a slot, the UE cancels
the CSI-RS reception in the set of symbols of the slot if the UE does
not detect a DCI format indicating an aperiodic CSI-RS reception or
scheduling a PDSCH reception in the set of symbols of the slot.

If a UE is provided *channelAccessMode =\'dynamic\'* and is provided
*availableRB-SetsToAddModList* and *availableRB-SetsToReleaseList*, the
UE expects to be provided *co-DurationsPerCellToAddModList* and
*co-DurationsPerCellToReleaseList* and/or *slotFormatCombToAddModList*
and *slotFormatCombToReleaseList*.

For operation on a single carrier in unpaired spectrum, if a UE is
configured by higher layers to transmit SRS, or PUCCH, or PUSCH, or
PRACH in a set of symbols of a slot and the UE detects a DCI format
indicating to the UE to receive CSI-RS or PDSCH in a subset of symbols
from the set of symbols, then

\- If the UE does not indicate the capability of
*partialCancellationPUCCH-PUSCH-PRACH-TX*, the UE does not expect to
cancel the transmission of the PUCCH or PUSCH or PRACH in the set of
symbols if the first symbol in the set occurs within $T_{proc,2\ }$
relative to a last symbol of a PDCCH reception where the UE detects the
DCI format; otherwise, the UE cancels the PUCCH, or the PUSCH, or an
actual repetition of the PUSCH \[6, TS 38.214\], determined from clauses
9, 9.2.5 and 9.2.6 or clause 6.1 of \[6, TS 38.214\], or the PRACH
transmission in the set of symbols.

\- If the UE indicates the capability of
*partialCancellationPUCCH-PUSCH-PRACH-TX*, the UE does not expect to
cancel the transmission of the PUCCH or PUSCH or PRACH in symbols from
the set of symbols that occur within $T_{proc,2}$ relative to a last
symbol of a PDCCH reception where the UE detects the DCI format. The UE
cancels the PUCCH, or the PUSCH, or an actual repetition of the PUSCH
\[6, TS 38.214\], determined from clauses 9, 9.2.5 and 9.2.6 or clause
6.1 of \[6, TS 38.214\], or the PRACH transmission in remaining symbols
from the set of symbols.

\- The UE does not expect to cancel the transmission of SRS in symbols
from the subset of symbols that occur within $T_{proc,2}$ relative to a
last symbol of a PDCCH reception where the UE detects the DCI format.
The UE cancels the SRS transmission in remaining symbols from the subset
of symbols.

$T_{proc,2}$ is the PUSCH preparation time for the corresponding UE
processing capability \[6, TS 38.214\] assuming $d_{2,1} = 1$ and $\mu$
corresponds to the smallest SCS configuration between the SCS
configuration of the PDCCH carrying the DCI format and the SCS
configuration of the SRS, PUCCH, PUSCH or $\mu_{r}$, where $\mu_{r}$
corresponds to the SCS configuration of the PRACH if it is 15kHz or
higher; otherwise $\mu_{r} = 0$.

For a set of symbols of a slot that are indicated to a UE as uplink by
*tdd-UL-DL-ConfigurationCommon*, or *tdd-UL-DL-ConfigurationDedicated*,
the UE does not receive PDCCH, PDSCH, or CSI-RS when the PDCCH, PDSCH,
or CSI-RS overlaps, even partially, with the set of symbols of the slot.

For a set of symbols of a slot that are indicated to a UE as uplink by
*tdd-UL-DL-ConfigurationCommon*, or *tdd-UL-DL-ConfigurationDedicated*,
the UE does not receive DL PRS in the set of symbols of the slot, if the
UE is not provided with a measurement gap.

For a set of symbols of a slot that are indicated to a UE as downlink by
*tdd-UL-DL-ConfigurationCommon*, or *tdd-UL-DL-ConfigurationDedicated*,
the UE does not transmit PUSCH, PUCCH, PRACH, or SRS when the PUSCH,
PUCCH, PRACH, or SRS overlaps, even partially, with the set of symbols
of the slot.

For a set of symbols of a slot that are indicated to a UE as flexible by
*tdd-UL-DL-ConfigurationCommon*, and *tdd-UL-DL-ConfigurationDedicated*
if provided, the UE does not expect to receive both dedicated higher
layer parameters configuring transmission from the UE in the set of
symbols of the slot and dedicated higher layer parameters configuring
reception by the UE in the set of symbols of the slot.

For operation on a single carrier in unpaired spectrum, for a set of
symbols of a slot indicated to a UE for reception of SS/PBCH blocks by
*ssb-PositionsInBurst* in *SIB1* or by *ssb-PositionsInBurst* in
*ServingCellConfigCommon* or, if the UE is not provided
*dl-OrJointTCI-StateList*, by *ssb-PositionsInBurst* in
*SSB-MTCAdditionalPCI* associated to physical cell ID with active TCI
states for PDCCH or PDSCH, or for a set of symbols of a slot
corresponding to SS/PBCH blocks configured for L1 beam
measurement/reporting, the UE does not transmit PUSCH, PUCCH, PRACH in
the slot if a transmission would overlap with any symbol from the set of
symbols and the UE does not transmit SRS in the set of symbols of the
slot. The UE does not expect the set of symbols of the slot to be
indicated as uplink by *tdd-UL-DL-ConfigurationCommon*, or
*tdd-UL-DL-ConfigurationDedicated*, when provided to the UE.

If a UE

\- is configured with multiple serving cells and is provided with
*directionalCollisionHandling-r16* = \'enabled\' for a set of serving
cell(s) among the multiple serving cells, and

\- indicates support of *half-DuplexTDD-CA-SameSCS-r16* capability, and

\- is not configured to monitor PDCCH for detection of DCI format 2_0 on
any of the multiple serving cells,

for a set of symbols of a slot that are indicated to the UE for
reception of SS/PBCH blocks in a first cell of the multiple serving
cells by *ssb-PositionsInBurst* in *SystemInformationBlockType1* or by
*ssb-PositionsInBurst* in *ServingCellConfigCommon* or, if the UE is not
provided *dl-OrJointTCI-StateList*, by *ssb-PositionsInBurst* in
*SSB-MTCAdditionalPCI* associated to physical cell ID with active TCI
states for PDCCH or PDSCH, or for a set of symbols of a slot
corresponding to SS/PBCH blocks configured for L1 beam
measurement/reporting, the UE does not transmit PUSCH, PUCCH, or PRACH
in the slot if a transmission would overlap with any symbol from the set
of symbols, and the UE does not transmit SRS in the set of symbols of
the slot in

\- any of the multiple serving cells if the UE is not capable of
simultaneous transmission and reception as indicated by
*simultaneousRxTxInterBandCA* among the multiple serving cells, and

\- any one of the cells corresponding to the same band as the first
cell, irrespective of any capability indicated by
*simultaneousRxTxInterBandCA*.

For a set of symbols of a slot corresponding to a valid PRACH occasion
and ![](media/image169.wmf){width="0.28125in"
height="0.22916666666666666in"} symbols before the valid PRACH occasion,
as described in clause 8.1, the UE does not receive PDCCH, PDSCH, or
CSI-RS in the slot if a reception would overlap with any symbol from the
set of symbols. The UE does not expect the set of symbols of the slot to
be indicated as downlink by *tdd-UL-DL-ConfigurationCommon* or
*tdd-UL-DL-ConfigurationDedicated*.

For a set of symbols of a slot indicated to a UE by *pdcch-ConfigSIB1*
in *MIB* for a CORESET for Type0-PDCCH CSS set, the UE does not expect
the set of symbols to be indicated as uplink by
*tdd-UL-DL-ConfigurationCommon*, or *tdd-UL-DL-ConfigurationDedicated*.

If a UE is scheduled by a DCI format to receive PDSCH over multiple
slots, and if *tdd-UL-DL-ConfigurationCommon*, or
*tdd-UL-DL-ConfigurationDedicated*, indicate that, for a slot from the
multiple slots, at least one symbol from a set of symbols where the UE
is scheduled PDSCH reception in the slot is an uplink symbol, the UE
does not receive the PDSCH in the slot.

If a UE is scheduled by a DCI format to transmit PUSCH over multiple
slots, and if *tdd-UL-DL-ConfigurationCommon*, or
*tdd-UL-DL-ConfigurationDedicated*, indicates that, for a slot from the
multiple slots, at least one symbol from a set of symbols where the UE
is scheduled PUSCH transmission in the slot is a downlink symbol, the UE
does not transmit the PUSCH in the slot.

If a UE

\- is configured with multiple serving cells and is provided with
*directionalCollisionHandling-r16* = \'enabled\' for a set of serving
cell(s) among the configured multiple serving cells, and

\- indicates support of *half-DuplexTDD-CA-SameSCS-r16* capability, and

\- is not configured to monitor PDCCH for detection of DCI format 2_0 on
any of the multiple serving cells,

the UE determines a reference cell for a symbol as an active cell with
the smallest cell index among

\- the configured multiple serving cells if the UE is not capable of
simultaneous transmission and reception as indicated by
*simultaneousRxTxInterBandCA* among the multiple serving cells, and

\- the cells of each band respectively if the UE is capable of
simultaneous transmission and reception by *simultaneousRxTxInterBandCA*
for the configured multiple serving cells,

where the symbol is configured by higher layers as

\- downlink, or uplink, as indicated by *tdd-UL-DL-ConfigurationCommon*
or *tdd-UL-DL-ConfigurationDedicated*

\- uplink, if the symbol is flexible and the UE is configured by higher
layers to transmit SRS, PUCCH, PUSCH, or PRACH on the symbol

\- downlink, if the symbol is flexible and the UE is configured by
higher layers to receive PDCCH, PDSCH or CSI-RS on the symbol.

And if another cell among the cells configured with
*directionalCollisionHandling-r16* operates in the same frequency band
as the reference cell, the UE does not expect

\- a symbol to be indicated as downlink or uplink on the reference cell
and as uplink or downlink on another cell, respectively, by
*tdd-UL-DL-ConfigurationCommon* or by
*tdd-UL-DL-ConfigurationDedicated*,

\- *tdd-UL-DL-ConfigurationCommon* or *tdd-UL-DL-ConfigurationDedicated*
to indicate a symbol as downlink on the reference cell and to detect a
DCI format scheduling a transmission on the symbol on another cell, and

\- to be configured by higher layers to receive PDCCH, PDSCH, or CSI-RS
on a flexible symbol on the reference cell and to detect a DCI format
scheduling a transmission on the symbol on another cell,

if the reference cell and another cell among the cells configured with
*directionalCollisionHandling-r16* operate in different frequency bands,

the UE

\- assumes symbol as flexible, is not required to receive higher layer
configured PDCCH, PDSCH, or CSI-RS and not expected to transmit higher
layer configured SRS, PUCCH, PUSCH, or PRACH, when
*tdd-UL-DL-ConfigurationCommon* or *tdd-UL-DL-ConfigurationDedicated*
indicates symbol as downlink or uplink on another cell and as uplink or
downlink for the reference cell, respectively,

\- transmits a signal/channel scheduled by a DCI format on a symbol of
another cell when the symbol is indicated as downlink by
*tdd-UL-DL-ConfigurationCommon* or *tdd-UL-DL-ConfigurationDedicated*
for the reference cell,

\- is not required to receive a higher layer configured PDCCH, PDSCH, or
CSI-RS on flexible symbols on the reference cell in a set of symbols, if
the UE detects a DCI format scheduling a transmission on one or more
symbols in the set of symbols on another cell,

and regardless of whether the reference cell and another cell operate in
same or different frequency bands,

the UE

\- does not expect *tdd-UL-DL-ConfigurationCommon* or
*tdd-UL-DL-ConfigurationDedicated* for the reference cell to indicate a
symbol as uplink and to detect a DCI format scheduling a reception on
the symbol on another cell

\- does not expect to be configured by higher layers to transmit SRS,
PUCCH, PUSCH, or PRACH on a flexible symbol on the reference cell and to
detect a DCI format scheduling a reception on the symbol on another cell

\- does not transmit a PUCCH, PUSCH or PRACH that is configured by
higher layers on a set of symbols on another cell if at least one symbol
from the set of symbols is indicated as downlink by
*tdd-UL-DL-ConfigurationCommon* or *tdd-UL-DL-ConfigurationDedicated* or
is a symbol corresponding to a PDCCH, PDSCH, or CSI-RS reception that is
configured by higher layers on the reference cell

\- does not transmit a SRS that is configured by higher layers on a set
of symbols on another cell if the set of symbols is indicated as
downlink by *tdd-UL-DL-ConfigurationCommon* or
*tdd-UL-DL-ConfigurationDedicated* or corresponds to a PDCCH, PDSCH or
CSI-RS reception that is configured by higher layers on the reference
cell

\- does not receive a PDCCH, PDSCH or CSI-RS that is configured by
higher layers on a set of symbols on another cell if at least one symbol
from the set of symbols is indicated as uplink by
*tdd-UL-DL-ConfigurationCommon* or *tdd-UL-DL-ConfigurationDedicated* or
is a symbol corresponding to a SRS, PUCCH, PUSCH, or PRACH transmission
that is configured by higher layers on the reference cell

\- assumes a symbol indicated as downlink or uplink by
*tdd-UL-DL-ConfigurationCommon* or *tdd-UL-DL-ConfigurationDedicated* on
another cell to be flexible, if the UE is respectively configured by
higher layers to transmit SRS, PUCCH, PUSCH, or PRACH or to receive
PDCCH, PDSCH, or CSI-RS on the reference cell

\- does not expect to detect a first DCI format scheduling a
transmission or reception on a symbol on a first cell and a second DCI
format scheduling a reception or transmission on the symbol on a second
cell, respectively.

After the UE applies the procedures described above for directional
collision handling within the set of cells that have been configured
with *directionalCollisionHandling-r16*, the UE does not expect any
directional collision among the serving cells that the UE is not capable
of simultaneous transmission and reception.