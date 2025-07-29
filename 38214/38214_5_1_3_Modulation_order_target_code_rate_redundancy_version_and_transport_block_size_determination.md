### 5.1.3 Modulation order, target code rate, redundancy version and transport block size determination

To determine the modulation order, target code rate, and transport block
size(s) in the physical downlink shared channel, the UE shall first

\- read the 5-bit modulation and coding scheme field (*I~MCS~*) in the
DCI to determine the modulation order (*Q~m~*) and target code rate
(*R*) based on the procedure defined in Clause 5.1.3.1, and

\- read \'*redundancy version\'* field (*rv*) in the DCI to determine
the redundancy version.

and second

\- the UE shall use the number of layers (ʋ), the total number of
allocated PRBs before rate matching (*n~PRB~*) to determine to the
transport block size based on the procedure defined in Clause 5.1.3.2.

The UE may skip decoding a transport block in an initial transmission if
the effective channel code rate is higher than 0.95, where the effective
channel code rate is defined as the number of downlink information bits
(including CRC bits) divided by the number of physical channel bits on
PDSCH.

When the UE is scheduled with multiple PDSCHs on a serving cell by a
DCI, as described in clause 5.1.2.1, the bits of *rv* field and NDI
field, respectively, in the DCI are one-to-one mapped to the scheduled
PDSCH(s) indicated by the TDRA information field with the corresponding
transport block(s) in the scheduled order, where the LSB bits of the
*rv* field and NDI field, respectively, correspond to the last scheduled
PDSCH indicated by the TDRA information field.

The UE is not expected to handle any transport blocks (TBs) in a 14
consecutive-symbol duration for normal CP (or 12 for extended CP) ending
at the last symbol of the latest PDSCH transmission within an active BWP
on a serving cell whenever

$$2^{max(0,\mu - \mu')}.\sum_{i \in S}^{}{\left\lfloor \frac{C_{i}'}{L_{i}} \right\rfloor x_{i}.F_{i}} > \left\lceil \frac{X}{4} \right\rceil.\frac{1}{R_{LBRM}}.TBS_{LBRM}$$

where, for the serving cell,

\- S is the set of TBs belonging to PDSCH(s) that are partially or fully
contained in the consecutive-symbol duration

\- for the *i*th TB

*- C~i~\'* is the number of scheduled code blocks for as defined in \[5,
38.212\].

*- L~i~* is the number of OFDM symbols assigned to the PDSCH

*- x~i~* is the number of OFDM symbols of the PDSCH contained in the
consecutive-symbol duration

\-
$F_{i} = \max_{j = 0,...,J - 1}{(\min{(k_{0,i}^{j} + E_{i}^{j},\ N_{cb,i})})}$
based on the values defined in Clause 5.4.2.1 \[5, TS 38.212\]

\- $k_{0,i}^{j}$ is the starting location of RV for the $j$th
transmission

\- $E_{i\ }^{j} = \min{(E_{r})\ }$of the scheduled code blocks for the
$jth$ transmission

\- $N_{cb,i}$ is the circular buffer length

\- $J - 1$ is the current (re)transmission for the *i*th TB

\- $\mu'$ corresponds to the subcarrier spacing of the BWP (across all
configured BWPs of a carrier) that has the largest configured number of
PRBs

\- in case there is more than one BWP corresponding to the largest
configured number of PRBs, *µ\'* follows the BWP with the largest
subcarrier spacing.

\- $\mu$ corresponds to the subcarrier spacing of the active BWP

\- R~LBRM~ = 2/3 as defined in Clause 5.4.2.1 \[5, TS 38.212\]

> \- TBS~LBRM~ as defined based on the parameters for unicast in Clause
> 5.4.2.1 \[5, TS 38.212\]

\- X as defined for downlink max MIMO layer for unicast in Clause
5.4.2.1 \[5, TS 38.212\].

If the UE skips decoding, the physical layer indicates to higher layer
that the transport block is not successfully decoded.

Within a cell group, a UE is not required to handle PDSCH(s)
transmissions including unicast and/or multicast/broadcast in slot
*s~j~* in serving cell-*j*, and for *j* = 0,1,2.. *J-1*, slot *s~j~*
overlapping with any given point in time, if the following condition is
not satisfied at that point in time:

$$\sum_{j = 0}^{J - 1}\frac{\sum_{m = 0}^{M - 1}V_{j,m}}{T_{slot}^{\mu(j)}} \leq DataRate$$

where,

\- *J* is the number of configured serving cells belonging to a
frequency range

\- for the *j-th* serving cell,

*- M* is the number of TB(s) transmitted in slot *s~j~*. If there are
two PDSCH transmission occasions of the same TB (in time domain or in
frequency domain) in the slot *s~j~*, each transmission occasion is
counted separately.

*- T~slot~^μ(j)^* =10^-3^/2*^μ(j)^*, where *μ(j)* is the numerology for
PDSCH(s) in slot *s~j~* of the *j*-th serving cell.

\- for the *m*-th TB,
$V_{j,m} = C' \bullet \left\lfloor \frac{A}{C} \right\rfloor$

*- A* is the number of bits in the transport block as defined in Clause
7.2.1 \[5, TS 38.212\]

*- C* is the total number of code blocks for the transport block defined
in Clause 5.2.2 \[5, TS 38.212\].$\ $

*-* $C'$ is the number of scheduled code blocks for the transport block
as defined in Clause 5.4.2.1 \[5, TS 38.212\]

\- $DataRate$ \[Mbps\] is computed as the maximum data rate summed over
all the carriers in the frequency range for any signaled band
combination and feature set consistent with the configured servings
cells, where the data rate value is given by the formula in Clause 4.1.2
in \[13, TS 38.306\], including the scaling factor *f(i).*

For a *j-*th serving cell, if higher layer parameter
*processingType2Enabled* of *PDSCH-ServingCellConfig* is configured for
the serving cell and set to \'*enable\',* or if at least one *I~MCS~ \>*
*W* for a PDSCH for unicast or multicast, where *W* = 28 for MCS tables
5.1.3.1-1 and 5.1.3.1-3, and *W* = 27 for MCS table 5.1.3.1-2, and *W* =
26 for MCS table 5.1.3.1-4, or for a j-th serving cell where UE supports
FDM-ed unicast and MBS PDSCH, the UE is not required to handle PDSCH
transmissions, if the following condition is not satisfied:

$$\frac{\sum_{m = 0}^{M - 1}V_{j,m}}{L \times T_{s}^{\mu}} \leq DataRateCC$$

where

\- $L\ $is the number of symbols assigned to the PDSCH(s). For a PDSCH
that consists of two PDSCH transmission occasions in time domain in one
slot, $L$ is the number of symbols of one transmission occasion. For
FDMed unicast and MBS PDSCHs in one slot, $L$ is the total number of
symbols of the unicast and MBS PDSCHs with fully or partially-overlapped
in time domain.

\- M is the number of TB(s) in the PDSCH(s)

\- $T_{s}^{\mu} = \frac{10^{- 3}}{{2^{\mu} \bullet N}_{symb}^{slot}}$
where *μ* is the numerology of the PDSCH(s)

\- for the *m*-th TB,
$V_{j,m} = C' \bullet \left\lfloor \frac{A}{C} \right\rfloor$

*- A* is the number of bits in the transport block as defined in Clause
7.2.1 \[5, TS 38.212\]

*- C* is the total number of code blocks for the transport block defined
in Clause 5.2.2 \[5, TS 38.212\]

*-* $C'$ is the number of scheduled code blocks for the transport block
as defined in Clause 5.4.2.1 \[5, TS 38.212\]

\- $DataRateCC$ \[Mbps\] is computed as the maximum data rate for a
carrier in the frequency band of the serving cell for any signaled band
combination and feature set consistent with the serving cell, where the
data rate value is given by the formula in Clause 4.1.2 in \[13, TS
38.306\], including the scaling factor *f(i).*