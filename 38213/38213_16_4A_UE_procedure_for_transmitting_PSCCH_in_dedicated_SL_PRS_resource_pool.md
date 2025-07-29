## 16.4A UE procedure for transmitting PSCCH in dedicated SL PRS resource pool

For a dedicated SL PRS resource pool, a UE can be provided a number of
symbols in the resource pool, by *timeResourcePSCCH-DedicatedSL-PRS-RP*,
starting from a second symbol that is available for SL transmissions in
a slot, and a number of PRBs in the resource pool, by
*freqResourcePSCCH-DedicatedSL-PRS-RP*, starting from a PRB with lowest
index for a sub-channel determined according to an index of an
associated SL PRS resource, for a PSCCH transmission with a SCI format
1-B.

A UE that transmits a PSCCH with SCI format 1-B using SL PRS resource
allocation mode 2 \[6, TS 38.214\] sets

\- \"Source ID\" as indicated by higher layers

\- \"Destination ID\" as indicated by high layers

\- \"Cast type indicator\" as indicated by higher layers

\- \"Resource reservation period\" as an index in
*sl-PRS-ResourceReservePeriodList* corresponding to a reservation period
provided by higher layers \[11, TS 38.321\], if the UE is provided
*sl-PRS-ResourceReservePeriodList*

\- the values of the time resource assignment field and of the resource
ID indication field as described in \[6, TS 38.214\] to indicate $N$
resources from a set $\left\{ R_{\text{y}} \right\}$ of resources
selected by higher layers as described in \[11, TS 38.321\] with $N$
smallest slot indices $y_{i}$ for $0 \leq i \leq N - 1$ such that
$y_{0} < y_{1} < \ldots < y_{N - 1} \leq y_{0} + 31$, where:

\- $N = \min\left( N_{selected},\ N_{max\_ reserve} \right)$, where
$N_{selected}$ is a number of resources in the set
$\left\{ R_{\text{y}} \right\}$ with slot indices $y_{j}$,
$0 \leq j \leq N_{selected} - 1$, such that
$y_{0} < y_{1} < \ldots < y_{N_{selected} - 1} \leq y_{0} + 31$, and
$N_{max\_ reserve}$ is provided by
*sl-MaxNumPerReserveDedicatedSL-PRS-RP*

\- each resource, from the set of $\left\{ R_{\text{y}} \right\}$
resources, corresponds to a SL PRS resource and the corresponding PSCCH,
and a slot in a set of slots $\{{t'}_{y}^{SL}\}$

\- $\left( {t'}_{0}^{SL},{t'}_{1}^{SL},{t'}_{2}^{SL},... \right)$ is a
set of slots in a sidelink resource pool \[6, TS 38.214\]

\- $y_{0}$ is an index of a slot where the PSCCH with SCI format 1-B is
transmitted.

\- \"SL PRS request\" as indicated by higher layers

A UE that transmits a PSCCH with SCI format 1-B using SL PRS resource
allocation mode 1 \[6, TS 38.214\] sets

\- \"Source ID\" as indicated by higher layers

\- \"Destination ID\" as indicated by high layers

\- \"Cast type indicator\" as indicated by higher layers

\- the values of the resource ID indication field and the time resource
assignment field for the SCI format 1-B transmitted in the $m$-th
resource for SL PRS and the corresponding PSCCH transmission provided by
a dynamic grant or by a SL configured grant, where
$m = \ \left\{ 1,\ldots,M \right\}$ and M is the total number of
resources for SL PRS and the corresponding PSCCH transmission provided
by a dynamic grant or the number of resources for SL PRS transmission in
a period provided by a SL configured grant type 1 or SL configured grant
type 2, as follows:

\- the resource ID indication field and time resource assignment field
indicate the $m$-th to $M$-th resources as described in \[6, TS
38.214\].

\- \"SL PRS request\" as indicated by higher layers

For decoding of a SCI format 1-B, a UE may assume that a number of bits
provided by *sl-NumReservedBitsSCI1B-DedicatedSL-PRS-RP* can have any
value as described in \[4, TS 38.212\].