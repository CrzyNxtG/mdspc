### 6.1.4 Modulation order, redundancy version and transport block size determination

To determine the modulation order, target code rate, redundancy version
and transport block size for the physical uplink shared channel, the UE
shall first

\- read the 5-bit modulation and coding scheme field
![](media/image740.wmf)in the DCI scheduling PUSCH or provided in a DCI
activating a configured grant Type 2 PUSCH, or as provided by
*mcsAndTBS* as described in Clause 6.1.2.3 for a configured grant Type 1
PUSCH to determine the modulation order ![](media/image741.wmf) and
target code rate (*R*) based on the procedure defined in Clause 6.1.4.1

\- read redundancy version field (*rv*) in the DCI to determine the
redundancy version for PUSCH scheduled by DCI, or determine the
redundancy version according to Clause 6.1.2.3.1 for configured grant
Type 1 and Type 2 PUSCH,

and second

\- use the number of layers ![](media/image742.wmf), the total number of
allocated PRBs ![](media/image743.wmf) to determine the transport block
size based on the procedure defined in Clause 6.1.4.2.

When the UE is scheduled with multiple PUSCHs on a serving cell by a
DCI, as described in clause 6.1.2.1, the bits of *rv* field and NDI
field, respectively, in the DCI are one to one mapped to the scheduled
PUSCH(s) indicated by the TDRA information field with the corresponding
transport block(s) in the scheduled order where the LSB bits of the *rv*
field and NDI field, respectively, correspond to the last scheduled
PUSCH indicated by the TDRA information field.

Within a cell group, a UE is not required to handle PUSCH(s)
transmissions in slot *s~j~* in serving cell-*j*, and for *j* = 0,1,2..
*J-1*, slot *s~j~* overlapping with any given point in time, if the
following condition is not satisfied at that point in time:

$\sum_{j = 0}^{J - 1}\frac{\sum_{m = 0}^{M - 1}V_{j,m}}{T_{slot}^{\mu(j)}} \leq DataRate$,

where

*- J* is the number of configured serving cells belong to a frequency
range

\- for the *j-th* serving cell,

*- M* is the number of TB(s) transmitted in slot-*s~j~*. For PUSCH
repetition Type B, each actual repetition is counted separately.

*- T~slot~^μ(j)^* =10^-3^/2^*μ(j*)^, where *μ(j)* is the numerology for
PUSCH(s) in slot *s~j~* of the *j*-th serving cell.

\- for the *m*-th TB,
$V_{j,m} = C' \bullet \left\lfloor \frac{A}{C} \right\rfloor$

*- A* is the number of bits in the transport block as defined in Clause
6.2.1 \[5, TS 38.212\]

*- C* is the total number of code blocks for the transport block defined
in Clause 5.2.2 \[5, TS 38.212\].$\ $

\- $C'$is the number of scheduled code blocks for the transport block as
defined in Clause 5.4.2.1 \[5, TS 38.212\]

\- $DataRate$ \[Mbps\] is computed as the maximum data rate summed over
all the carriers in the frequency range for any signaled band
combination and feature set consistent with the configured servings
cells, where the data rate value is given by the formula in Clause 4.1.2
in \[13, TS 38.306\], including the scaling factor *f(i).*

For a *j*-th serving cell, if higher layer parameter
*processingType2Enabled* of *PUSCH-ServingCellConfig* is configured for
the serving cell and set to \'enable\'*,* or if at least one *I~MCS~ \>
W* for a PUSCH, where *W* = 28 for MCS tables 5.1.3.1-1 and 5.1.3.1-3,
and *W* = 27 for MCS tables 5.1.3.1-2, 6.1.4.1-1, and 6.1.4.1-2, or if
it is an actual repetition for PUSCH repetition Type B, the UE is not
required to handle PUSCH transmissions, if the following condition is
not satisfied:

$$\frac{\sum_{m = 0}^{M - 1}V_{j,m}}{L \times T_{s}^{\mu}} \leq DataRateCC$$

where

\- $L\ $is the number of symbols assigned to the PUSCH

\- *M* is the number of TB in the PUSCH

\- $T_{s}^{\mu} = \frac{10^{- 3}}{{2^{\mu} \bullet N}_{symb}^{slot}}$
where μ is the numerology of the PUSCH

\- for the *m*-th TB,
$V_{j,m} = C' \bullet \left\lfloor \frac{A}{C} \right\rfloor$

\- *A* is the number of bits in the transport block as defined in Clause
6.2.1 \[5, TS 38.212\]

\- *C* is the total number of code blocks for the transport block
defined in Clause 5.2.2 \[5, TS 38.212\]

\- $C'$ is the number of scheduled code blocks for the transport block
as defined in Clause 5.4.2.1 \[5, TS 38.212\]

\- $DataRateCC$ \[Mbps\] is computed as the maximum data rate for a
carrier in the frequency band of the serving cell for any signaled band
combination and feature set consistent with the serving cell, where the
data rate value is given by the formula in Clause 4.1.2 in \[13, TS
38.306\], including the scaling factor *f(i)*

\- each actual repetition for PUSCH repetition type B is treated as one
PUSCH*.*