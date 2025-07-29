## 16.4 UE procedure for transmitting PSCCH

A UE can be provided a number of symbols in a resource pool, by
*sl-TimeResourcePSCCH*, starting from

\- *sl*-*StartingSymbolFirst*+1 or *sl-StartingSymbolSecond*+1 in a slot
without PSFCH symbols, or *sl*-*StartingSymbolFirst*+1 in a slot with
PSFCH symbols, if *sl*-*StartingSymbolFirst* and
*sl*-*StartingSymbolSecond* are provided for the SL-BWP

\- *sl-StartSymbol*+1, otherwise

and a number of PRBs in the resource pool, by *sl-FreqResourcePSCCH*,
starting from the lowest PRB index of the lowest sub-channel index, in
an RB-set with a lowest index if applicable, of the associated PSSCH for
a PSCCH transmission with a SCI format 1-A. For operation with shared
spectrum channel access,

\- if *sl-TransmissionStructureForPSCCHandPSSCH* = *\'interlaceRB\'*,
the PRBs for PSCCH are within the sub-channel with the lowest index and
within the RB-set with the lowest index among the RB-set(s) for the
associated PSSCH transmission,

\- if *sl-TransmissionStructureForPSCCHandPSSCH* = *\'contiguousRB\'*,
the PRBs for PSCCH are within the sub-channel with the lowest index in
the RB-set with the lowest index among the RB-set(s) for the associated
PSSCH transmission, and all PRBs in the sub-channel overlapping with
intra-cell guard band \[6, TS 38.214\] are not used for PSCCH.

A UE that transmits a PSCCH with SCI format 1-A using sidelink resource
allocation mode 2 \[6, TS 38.214\] sets

\- \"Resource reservation period\" as an index in
*sl-ResourceReservePeriodList* corresponding to a reservation period
provided by higher layers \[11, TS 38.321\], if the UE is provided
*sl-MultiReserveResource*

\- the values of the frequency resource assignment field and the time
resource assignment field as described in \[6, TS 38.214\] to indicate
$N$ resources from a set $\left\{ R_{\text{y}} \right\}$ of resources
selected by higher layers as described in \[11, TS 38.321\] with $N$
smallest slot indices $y_{i}$ for $0 \leq i \leq N - 1$ such that
$y_{0} < y_{1} < \ldots < y_{N - 1} \leq y_{0} + 31$, where:

\- $N = \min\left( N_{selected},\ N_{max\_ reserve} \right)$, where
$N_{selected}$ is a number of resources in the set
$\left\{ R_{\text{y}} \right\}$ with slot indices $y_{j}$,
$0 \leq j \leq N_{selected} - 1$, such that
$y_{0} < y_{1} < \ldots < y_{N_{selected} - 1} \leq y_{0} + 31$, and
$N_{max\_ reserve}$ is provided by *sl-MaxNumPerReserve*

\- each resource, from the set of $\left\{ R_{\text{y}} \right\}$
resources, corresponds to $L_{\text{subCH}}$ contiguous sub-channels and
a slot in a set of slots $\{{t'}_{y}^{SL}\}$, where $L_{\text{subCH}}$
is the number of sub-channels available for PSSCH/PSCCH transmission in
a slot

\- $\left( {t'}_{0}^{SL},{t'}_{1}^{SL},{t'}_{2}^{SL},... \right)$ is a
set of slots in a sidelink resource pool \[6, TS 38.214\]

\- $y_{0}$ is an index of a slot where the PSCCH with SCI format 1-A is
transmitted.

A UE that transmits a PSCCH with SCI format 1-A using sidelink resource
allocation mode 1 \[6, TS 38.214\] sets

\- the values of the frequency resource assignment field and the time
resource assignment field for the SCI format 1-A transmitted in the
$m$-th resource for PSCCH/PSSCH transmission provided by a dynamic grant
or by a SL configured grant, where $m = \ \left\{ 1,\ldots,M \right\}$
and M is the total number of resources for PSCCH/PSSCH transmission
provided by a dynamic grant or the number of resources for PSCCH/PSSCH
transmission in a period provided by a SL configured grant type 1 or SL
configured grant type 2, as follows:

\- the frequency resource assignment field and time resource assignment
field indicate the $m$-th to $M$-th resources as described in \[6, TS
38.214\].

For decoding of a SCI format 1-A, a UE may assume that a number of bits
provided by *sl*-*NumReservedBits* can have any value as described in
\[4, TS 38.212\].