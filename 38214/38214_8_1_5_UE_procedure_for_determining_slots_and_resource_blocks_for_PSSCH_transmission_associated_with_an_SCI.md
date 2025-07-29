### 8.1.5 UE procedure for determining slots and resource blocks for PSSCH transmission associated with an SCI format 1-A

The set of slots and resource blocks for PSSCH transmission is
determined by the resource used for the PSCCH transmission containing
the associated SCI format 1-A, and fields \'*Frequency resource
assignment*\', \'*Time resource assignment*\' of the associated SCI
format 1-A as described below.

\'*Time resource assignment*\' carries logical slot offset indication of
N = 1 or 2 actual resources when *sl-MaxNumPerReserve* is 2, and N = 1
or 2 or 3 actual resources when *sl-MaxNumPerReserve* is 3, in a form of
time RIV (TRIV) field which is determined as follows:

if $N = 1$

$TRIV = 0$

elseif $N = 2$

$TRIV = t_{1}$

else

if $\left( t_{2} - t_{1} - 1 \right) \leq 15$

$TRIV = 30\left( t_{2} - t_{1} - 1 \right) + t_{1} + 31$

else

$TRIV = 30\left( 31 - t_{2} + t_{1} \right) + 62 - t_{1}$

end if

end if

where the first resource is in the slot where SCI format 1-A was
received, and $t_{i}$ denotes i-th resource time offset in logical slots
of a resource pool with respect to the first resource where for N = 2,
$1 \leq t_{1} \leq 31$; and for N = 3, $1 \leq t_{1} \leq 30$,
$t_{1} < t_{2} \leq 31$.

The starting sub-channel $n_{subCH,0}^{start}$ of the first resource is
determined according to clause 8.1.2.2. The number of contiguously
allocated sub-channels for each of the N resources
$L_{\text{subCH}} \geq 1$ and the starting sub-channel indexes of
resources indicated by the received SCI format 1-A, except the resource
in the slot where SCI format 1-A was received, are determined from
\"Frequency resource assignment\" which is equal to a frequency RIV
(FRIV) where.

If *sl-MaxNumPerReserve* is 2 then

$FRIV = n_{subCH,1}^{start} + \sum_{i = 1}^{L_{\text{subCH}} - 1}\left( N_{\text{ subchannel}}^{\text{ }SL} + 1 - i \right)$

If *sl-MaxNumPerReserve* is 3 then

$FRIV = n_{subCH,1}^{start} + n_{subCH,2}^{start} \cdot \left( N_{\text{ subchannel}}^{\text{ }SL} + 1 - L_{\text{subCH}} \right) + \sum_{i = 1}^{L_{\text{subCH}} - 1}\left( N_{\text{ subchannel}}^{\text{ }SL} + 1 - i \right)^{2}$

where

\- $n_{subCH,1}^{start}$ denotes the starting sub-channel index for the
second resource

\- $n_{subCH,2}^{start}$ denotes the starting sub-channel index for the
third resource

\- $N_{\text{ subchannel}}^{\text{ }SL}$ is the number of sub-channels
in a resource pool provided according to the higher layer parameter
*sl-NumSubchannel*, or if the higher layer parameter
*sl-TransmissionStructureForPSCCHandPSSCH* is set to \'interlaceRB\',
the number of sub-channels in each RB set which is equal to the number
of interlaces in each RB set divided by the number of interlace(s) per
sub-channel provided according to the higher layer parameter
*sl-NumInterlacePerSubchannel*

If the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH*
is set to \'interlaceRB\', the applied interlace index(s) in different
RB sets are the same.

If the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH*
is set to \'interlaceRB\', the starting RB set $n_{RBset,0}^{start}$ of
the first resource is determined according to the clause 8.1.2.2. The
number of contiguously allocated RB sets for each of the N resources
L~RBset~≥1 and the starting RB set indexes of resources indicated by the
received SCI format 1-A, except the resource in the slot where SCI
format 1-A was received, are determined from \"Frequency resource
assignment\" which is equal to a frequency RIV (FRIV), where

If sl-MaxNumPerReserve is 2 then

$$FRIV_{RBset} = n_{RBset,1}^{start} + \sum_{i = 1}^{L_{RBset} - 1}\left( N_{RBset} + 1 - i \right)$$

If sl-MaxNumPerReserve is 3 then

$$FRIV_{RBset} = n_{RBset,1}^{start} + n_{RBset,2}^{start} \cdot \left( N_{RBset} + 1 - L_{RBset} \right) + \sum_{i = 1}^{L_{RBset} - 1}\left( N_{RBset} + 1 - i \right)^{2}$$

where

\- $n_{RBset,1}^{start}$ denotes the starting RB set index for the
second resource,

\- $n_{RBset,2}^{start}$ denotes the starting RB set index for the third
resource,

\- $N_{RBset}$ is the number of RB sets in a resource pool,

\- $L_{RBset}$ is the number of RB sets for each of the indicated
resources,

\- for FRIV indication, within the resource pool, RB sets are numbered
in increasing order from 0 to $N_{RBset} - 1$ from lowest frequency
location to highest frequency location.

If the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH*
is set to \'interlaceRB\', the resource is determined by an intersection
of the interlaces corresponding to the indicated sub-channel(s) and the
union of the indicated set of RB sets and intra-cell guard bands between
the indicated RB sets, if any.

If TRIV indicates *N* \< *sl-MaxNumPerReserve*,

\- if the higher layer parameter
*sl-TransmissionStructureForPSCCHandPSSCH* is set to \'interlaceRB\',
the starting sub-channel indexes and the starting RB set indexes
corresponding to *sl-MaxNumPerReserve* minus *N* last resources are not
used.

\- otherwise, the starting sub-channel indexes corresponding to
*sl-MaxNumPerReserve* minus *N* last resources are not used.

The number of slots in one set of the time and frequency resources for
transmission opportunities of PSSCH is given by $C_{resel}$ where
$C_{resel}$= 10\*SL_RESOURCE_RESELECTION_COUNTER \[10, TS 38.321\] if
configured else $C_{resel}$ is set to 1.

If a set of sub-channels in slot ${t'}_{m}^{SL}$ is determined as the
time and frequency resource for PSSCH transmission corresponding to the
selected sidelink grant (described in \[10, TS 38.321\]), the same set
of sub-channels in slots ${t'}_{m + j \times P_{rsvp\_ TX}'}^{SL}$ are
also determined for PSSCH transmissions corresponding to the same
sidelink grant where *j=*1, 2,*...,* $C_{resel} - 1$,
$P_{\text{rsvp\_TX}}$, if provided, is converted from units of msec to
units of logical slots, resulting in $P_{\text{rsvp\_TX}}'$ according to
clause 8.1.7, and
$\left( {t'}_{0}^{SL},\ {t'}_{1}^{SL},\ {t'}_{2}^{SL},\ldots \right)$ is
determined by Clause 8. Here, $P_{\text{rsvp\_TX}}$ is the resource
reservation interval indicated by higher layers.