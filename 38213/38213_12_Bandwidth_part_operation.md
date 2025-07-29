# 12 Bandwidth part operation

If the UE is configured with a SCG, the UE shall apply the procedures
described in this clause for both MCG and SCG

\- When the procedures are applied for MCG, the terms \'secondary
cell\', \'secondary cells\', \'serving cell\', \'serving cells\' in this
clause refer to secondary cell, secondary cells, serving cell, serving
cells belonging to the MCG respectively.

\- When the procedures are applied for SCG, the terms \'secondary
cell\', \'secondary cells\', \'serving cell\', \'serving cells\' in this
clause refer to secondary cell, secondary cells (not including PSCell),
serving cell, serving cells belonging to the SCG respectively. The term
\'primary cell\' in this clause refers to the PSCell of the SCG.

A UE configured for operation in bandwidth parts (BWPs) of a serving
cell, is configured by higher layers for the serving cell a set of at
most four bandwidth parts (BWPs) for receptions by the UE (DL BWP set)
in a DL bandwidth by parameter *BWP-Downlink* or by parameter
*initialDownlinkBWP* with a set of parameters configured by
*BWP-DownlinkCommon* and *BWP-DownlinkDedicated*, and a set of at most
four BWPs for transmissions by the UE (UL BWP set) in an UL bandwidth by
parameter *BWP-Uplink* or by parameter *initialUplinkBWP* with a set of
parameters configured by *BWP-UplinkCommon* and *BWP-UplinkDedicated*.

For operation with shared spectrum channel access, a UE expects that the
BWP configured by the parameter *initialUplinkBWP* provided in
*UplinkConfigCommonSIB* is mapped to only a single RB set.

If a UE is not provided *initialDownlinkBWP*, an initial DL BWP is
defined by a location and number of contiguous PRBs, starting from a PRB
with the lowest index and ending at a PRB with the highest index among
PRBs of a CORESET for Type0-PDCCH CSS set, after puncturing if any \[4,
TS 38.211\], and a SCS and a cyclic prefix for PDCCH reception in the
CORESET for Type0-PDCCH CSS set; otherwise, the initial DL BWP is
provided by *initialDownlinkBWP*. For operation on the primary cell or
on a secondary cell, a UE is provided an initial UL BWP by
*initialUplinkBWP*. If the UE is configured with a supplementary UL
carrier, the UE can be provided an initial UL BWP on the supplementary
UL carrier by *initialUplinkBWP*.

If a UE has dedicated BWP configuration, the UE can be provided by
*firstActiveDownlinkBWP-Id* a first active DL BWP for receptions and by
*firstActiveUplinkBWP-Id* a first active UL BWP for transmissions on a
carrier of the primary cell.

For each DL BWP or UL BWP in a set of DL BWPs or UL BWPs, respectively,
the UE is provided the following parameters for the serving cell as
defined in \[4, TS 38.211\] or \[6, TS 38.214\]:

\- a SCS by *subcarrierSpacing*

\- a cyclic prefix by *cyclicPrefix*

\- a common RB $N_{BWP}^{start} = O_{carrier} + {RB}_{start}$ and a
number of contiguous RBs $N_{BWP}^{size} = L_{RB}$ provided by
*locationAndBandwidth* that indicates an offset ${RB}_{start}$ and a
length $L_{RB}$ as RIV according to \[6, TS 38.214\], setting
$N_{BWP}^{size} = 275$, and a value $O_{carrier}$ provided by
*offsetToCarrier* for the *subcarrierSpacing*

\- an index in the set of DL BWPs or UL BWPs by respective *BWP-Id*

\- a set of BWP-common and a set of BWP-dedicated parameters by
*BWP-DownlinkCommon* and *BWP-DownlinkDedicated* for the DL BWP, or
*BWP-UplinkCommon* and *BWP-UplinkDedicated* for the UL BWP \[12, TS
38.331\]

For unpaired spectrum operation, a DL BWP from the set of configured DL
BWPs with index provided by *BWP-Id* is linked with an UL BWP from the
set of configured UL BWPs with index provided by *BWP-Id* when the DL
BWP index and the UL BWP index are same. For unpaired spectrum
operation, a UE does not expect to receive a configuration where the
center frequency for a DL BWP is different than the center frequency for
an UL BWP when the *BWP-Id* of the DL BWP is same as the *BWP-Id* of the
UL BWP.

For each DL BWP in a set of DL BWPs of the PCell, a UE can be configured
CORESETs for every type of CSS sets and for USS as described in clause
10.1. The UE does not expect to be configured without a CSS set on the
PCell in the active DL BWP.

If a UE is provided *controlResourceSetZero* and *searchSpaceZero* in
*PDCCH-ConfigSIB1* or *PDCCH-ConfigCommon*, the UE determines a CORESET
for a search space set from *controlResourcesetZero* as described in
clause 13 and for Tables 13-0 through 13-10, and determines
corresponding PDCCH monitoring occasions as described in clause 13 and
for Tables 13-11 through 13-15. If the active DL BWP is not the initial
DL BWP, the UE determines PDCCH monitoring occasions for the search
space set only if the CORESET bandwidth is within the active DL BWP and
the active DL BWP has same SCS configuration and same cyclic prefix as
the initial DL BWP.

For each UL BWP in a set of UL BWPs of the PCell, or of the PUCCH-SCell,
or of the PUCCH-sSCell the UE is configured resource sets for PUCCH
transmissions as described in clause 9.2.1.

A UE receives PDCCH and PDSCH in a DL BWP according to a configured SCS
and CP length for the DL BWP. A UE transmits PUCCH and PUSCH in an UL
BWP according to a configured SCS and CP length for the UL BWP.

If a bandwidth part indicator field is configured in a DCI format, the
bandwidth part indicator field value indicates the active DL BWP, from
the configured DL BWP set, for DL receptions as described in \[5, TS
38.212\]. If a bandwidth part indicator field is configured in a DCI
format, the bandwidth part indicator field value indicates the active UL
BWP, from the configured UL BWP set, for UL transmissions as described
in \[5, TS 38.212\].

If a bandwidth part indicator field is provided by a DCI format 0_3/1_3,

\- the UE applies for a serving cell the value of the bandwidth part
indicator field, if

\- the UE is scheduled by the DCI format 0_3/1_3 to transmit
PUSCH/receive PDSCH, respectively, on the serving cell, and

\- the serving cell includes a configured UL/DL BWP with index
corresponding to the value of the bandwidth part indicator field, and

\- *resourceAllocation* = *resourceAllocationType0* and not all bits of
a block of the frequency domain resource assignment field associated
with the serving cell in the DCI format 0_3/1_3 are equal to 0, or

\- *resourceAllocation* = *resourceAllocationType1* and not all bits of
a block of the frequency domain resource assignment field associated
with the serving cell in the DCI format 0_3/1_3 are equal to 1, or

\- *resourceAllocation = dynamicSwitch* and not all bits of a block of
the frequency domain resource assignment field associated with the
serving cell in the DCI format 0_3/1_3 are equal to either 0 or 1, or

\- *useInterlacePUCCH-PUSCH* is provided and not all bits of a block of
the frequency domain resource assignment field associated with the
serving cell in the DCI format 0_3 are equal to 1 for $\mu = 0$ or not
all bit[s of the block]{.underline} are equal to 0 for $\mu = 1$

\- otherwise, the UE does not apply for the serving cell the value of
the bandwidth part indicator field.

The UE does not expect to be scheduled by a DCI format 0_3/1_3 to
transmit/receive a PUSCH/PDSCH on an activated SCell, if:

\- the DCI format 0_3/1_3 indicates an active DL BWP provided by
*dormantBWP-Id* for the activated SCell, and

\- *resourceAllocation* = *resourceAllocationType0* and not all bits of
a block of the frequency domain resource assignment field associated
with the activated SCell in the DCI format 0_3/1_3 are equal to 0, or

\- *resourceAllocation* = *resourceAllocationType1* and not all bits of
a block of the frequency domain resource assignment field associated
with the activated SCell in the DCI format 0_3/1_3 are equal to 1, or

\- *resourceAllocation = dynamicSwitch* and not all bits of a block of
the frequency domain resource assignment field associated with the
activated SCell in the DCI format 0_3/1_3 are equal to either 0 or 1, or

\- *useInterlacePUCCH-PUSCH* is provided and not all bits of a block of
the frequency domain resource assignment field associated with the
serving cell in the DCI format 0_3 are equal to 1 for $\mu = 0$ or not
all bits of the block are equal to 0 for $\mu = 1$.

If a bandwidth part indicator field is configured in a DCI format and
indicates an UL BWP or a DL BWP different from the active UL BWP or DL
BWP, respectively, the UE shall

\- for each information field in the DCI format

\- if the size of the information field is smaller than the one required
for the DCI format interpretation for the UL BWP or DL BWP that is
indicated by the bandwidth part indicator, the UE prepends zeros to the
information field until its size is the one required for the
interpretation of the information field for the UL BWP or DL BWP prior
to interpreting the DCI format information fields, respectively

\- if the size of the information field is larger than the one required
for the DCI format interpretation for the UL BWP or DL BWP that is
indicated by the bandwidth part indicator, the UE uses a number of least
significant bits of the DCI format equal to the one required for the UL
BWP or DL BWP indicated by bandwidth part indicator prior to
interpreting the DCI format information fields, respectively

\- for a DCI format 0_3, or for a DCI format 1_3, and for an information
field that includes a number of blocks \[5, TS 38.212\], the above
procedures apply separately for each block of the information field

\- set the active UL BWP or DL BWP to the UL BWP or DL BWP indicated by
the bandwidth part indicator in the DCI format

If a bandwidth part indicator field is configured in a DCI format
0_1/0_3 and indicates an active UL BWP with different SCS configuration
$\mu$, or with different number $N_{RB - set,UL}^{BWP}$ of RB sets for a
serving cell, than a current active UL BWP for the serving cell, the UE
determines an uplink frequency domain resource allocation Type 2 for the
serving cell based on $X'$ bits and $Y'$ bits that are generated by
independently truncating or padding the $X$ MSBs and the $Y$ LSBs \[6,
TS 38.214\] of the frequency domain resource assignment field of DCI
format 0_1, or the block of the frequency domain resource assignment
field in DCI format 0_3 corresponding to the serving cell, where
truncation starts from the MSBs of the X bits or the Y bits,
zero-padding prepends zeros to the X bits or the Y bits, and

\- if the indicated active UL BWP for the serving cell has SCS
configuration $\mu = 1$ and the current active BWP for the serving cell
has SCS configuration $\mu = 0$, the $X$ MSBs are truncated to
$X' = X - 1$ bits, or

\- if the indicated active UL BWP for the serving cell has SCS
configuration $\mu = 0$ and the current active BWP for the serving cell
has SCS configuration $\mu = 1$, the $X$ MSBs are zero-padded to
$X' = X + 1$ bits

\- otherwise, the $X$ MSBs are unchanged

and

\- the $Y$ LSBs are truncated or zero-padded to
$Y' = \left\lceil \text{log}_{2}\left( \frac{N_{RB - set,UL}^{BWP}\left( N_{RB - set,UL}^{BWP} + 1 \right)}{2} \right) \right\rceil$
bits where $N_{RB - set,UL}^{BWP}$ is a number of RB sets configured for
the indicated active UL BWP for the serving cell.

A UE does not expect to detect a DCI format with a BWP indicator field
that indicates an active DL BWP or an active UL BWP change with the
corresponding time domain resource assignment field providing a slot
offset value for a PDSCH reception or PUSCH transmission that is smaller
than a delay required by the UE for an active DL BWP change or UL BWP
change, respectively \[10, TS 38.133\].

If a UE detects a DCI format with a BWP indicator field that indicates
an active DL BWP change for a cell, the UE is not required to receive or
transmit in the cell during a time duration from the end of the third
symbol of a slot where the UE receives the PDCCH that includes the DCI
format in a scheduling cell until the beginning of a slot indicated by
the slot offset value of the time domain resource assignment field in
the DCI format or determined by the slot offset value corresponding to
the first PDSCH of the more than one PDSCH scheduled by the DCI format
for the cell.

If a UE detects a DCI format with SCell dormancy indication that
indicates an active DL BWP change for an SCell in slot *n* of primary
cell, the UE is not required to receive or transmit in the SCell during
a time duration specified in \[10, TS 38.133\].

If a UE detects a DCI format indicating an active UL BWP change for a
cell, the UE is not required to receive or transmit in the cell during a
time duration from the end of the third symbol of a slot where the UE
receives the PDCCH that includes the DCI format in the scheduling cell
until the beginning of a slot indicated by the slot offset value of the
time domain resource assignment field in the DCI format or determined by
the slot offset value corresponding to the first PUSCH of the more than
one PUSCH scheduled by the DCI format for the cell.

A UE does not expect to detect a DCI format indicating an active DL BWP
change or an active UL BWP change for a scheduled cell within FR1 (or
FR2) in a slot other than the first slot of a set of slots for the DL
SCS of the scheduling cell that overlaps with a time duration where the
UE is not required to receive or transmit, respectively, for an active
BWP change in a different cell from the scheduled cell within FR1 (or
FR2).

A UE expects to detect a DCI format with a BWP indicator field that
indicates an active UL BWP change or an active DL BWP change only if a
corresponding PDCCH is received within the first 3 symbols of a slot. If
the UE detects the DCI format from two PDCCH receptions in search space
sets $s_{i}$ and $s_{j}$ that include *searchSpaceLinkingId* with same
value, as described in clause 10.1, the UE considers the PDCCH reception
where the UE detects the DCI format to be the one from the two PDCCH
receptions that ends later.

For a serving cell, a UE can be provided by *defaultDownlinkBWP-Id* a
default DL BWP among the configured DL BWPs. If a UE is not provided a
default DL BWP by *defaultDownlinkBWP-Id*, the default DL BWP is the
initial DL BWP.

If a UE is provided by *bwp-InactivityTimer* a timer value for the
serving cell \[11, TS 38.321\] and the timer is running, the UE
decrements the timer at the end of a subframe for FR1 or at the end of a
half subframe for FR2 if the restarting conditions in \[11, TS 38.321\]
are not met during the interval of the subframe for FR1 or of the half
subframe for FR2.

For a cell where a UE changes an active DL BWP due to a BWP inactivity
timer expiration and for accommodating a delay in the active DL BWP
change or the active UL BWP change required by the UE \[10, TS 38.133\],
the UE is not required to receive or transmit in the cell during a time
duration from the beginning of a subframe for FR1, or of half of a
subframe for FR2, that is immediately after the BWP inactivity timer
expires until the beginning of a slot where the UE can receive or
transmit.

When a UE\'s BWP inactivity timer for a cell within FR1 (or FR2) expires
within a time duration where the UE is not required to receive or
transmit for an active UL/DL BWP change in the cell or in a different
cell within FR1 (or FR2), the UE delays the active UL/DL BWP change
triggered by the BWP inactivity timer expiration until a subframe for
FR1 or half a subframe for FR2 that is immediately after the UE
completes the active UL/DL BWP change in the cell or in the different
cell within FR1 (or FR2).

If a UE is provided by *firstActiveDownlinkBWP-Id* a first active DL BWP
and by *firstActiveUplinkBWP-Id* a first active UL BWP on a carrier of a
secondary cell, the UE uses the indicated DL BWP and the indicated UL
BWP as the respective first active DL BWP on the secondary cell and
first active UL BWP on the carrier of the secondary cell.

If a UE is provided *NonCellDefiningSSB* in *BWP-DownlinkDedicated* for
an active DL BWP, the UE assumes that the active DL BWP includes the
SS/PBCH blocks provided by *NonCellDefiningSSB*. The SS/PBCH blocks
provided by *NonCellDefiningSSB* and the SS/PBCH blocks that the UE used
to obtain SIB1 have same QCL properties if they have a same index*.*
Unless otherwise stated, handling of overlapping between downlink
receptions or uplink transmissions and the SS/PBCH blocks provided by
*NonCellDefiningSSB* is same as handling of overlapping between downlink
receptions or uplink transmissions and the SS/PBCH blocks provided by
*ssb-PositionsInBurst* in *SIB1* or in *ServingCellConfigCommon*. The
SS/PBCH blocks in Clause 11.1 for resolving directional collisions for a
set of serving cells among multiple serving cells, when the UE is
provided *directionalCollisionHandling* and indicates support of
*half-DuplexTDD-CA-SameSCS*, correspond to the SS/PBCH blocks the UE
used to obtain SIB1.

A UE does not expect to monitor PDCCH when the UE performs RRM
measurements \[10, TS 38.133\] over a bandwidth that is not within the
active DL BWP for the UE.