## 16.1 Synchronization procedures

A UE receives the following SL synchronization signals in order to
perform synchronization procedures based on S-SS/PSBCH blocks: SL
primary synchronization signals (S-PSS) and SL secondary synchronization
signals (S-SSS) \[4, TS 38.211\].

A UE assumes that reception occasions of a physical sidelink broadcast
channel (PSBCH), S-PSS, and S-SSS are in consecutive symbols \[4, TS
38.211\] and form a S-SS/PSBCH block.

For reception of a S-SS/PSBCH block,

\- for operation without shared spectrum channel access, or for
operation with shared spectrum channel access and when
*sl-NumOfSSSBRepetition* is not provided and for RB-set $j$, a UE
assumes a frequency location corresponding to the subcarrier with index
66 in the S-SS/PSBCH block \[4, TS 38.211\], is provided by

\- *sl-AbsoluteFrequencySSB*, for operation without shared spectrum
channel access or when RB-set $j$ is the anchor RB-set that is the RB
set that includes the S-SS/PSBCH block

\- a corresponding value in *sl-AbsoluteFrequencySSB-NonAnchorList* when
RB-set $j$ is a non-anchor RB-set

\- for operation with shared spectrum channel access when
*sl-NumOfSSSBRepetition* is provided and in RB-set $j$, a UE assumes a
frequency location corresponding to the subcarrier with index 66 in the
S-SS/PSBCH block \[4, TS 38.211\] is provided by
$f_{start,j}^{S - SSB}$+$\ k_{S - SSB,j} \cdot \left( N_{gap,j}^{S - SSB} + M_{RB}^{S - SSB} \right) \cdot 12 \cdot 2^{\mu} \bullet 15\ kHz$,
where

\- $f_{start,\ j}^{S - SSB}$ is a frequency location of a lowest
S-SS/PSBCH block in RB-set $j$, where $f_{start,\ j}^{S - SSB}$ is
provided by

\- *sl-AbsoluteFrequencySSB* when RB-set *j* is the anchor RB-set,

\- a corresponding value in *sl-AbsoluteFrequencySSB-NonAnchorList* when
RB-set $j$ is a non-anchor RB-set

\- $k_{S - SSB,j}$ is an index of an S-SS/PSBCH block from repeated
S-SS/PSBCH blocks in the frequency domain and within the RB-set $j$,
where $0 \leq k_{S - SSB,j} \leq N_{repetition,j}^{S - SSB} - 1$, and
$N_{repetition,j}^{S - SSB}$ is provided by a value in
*sl-NumOfSSSBRepetition* corresponding to RB-set $j$;

\- $N_{gap,j}^{S - SSB}$ is a number of resource blocks, provided by
*sl-GapBetweenSSSBRepetition*, for a gap between two adjacent repeated
S-SS/PSBCH blocks;

\- $M_{RB}^{S - SSB} = 11$ is a number of resource blocks for a
S-SS/PSBCH block transmission with SCS configuration $\mu$.

For operation with shared spectrum channel access, a UE attempts to
transmit at least S-SS/PSBCH blocks in the slots including S-SS/PSBCH
blocks in the anchor RB set. The UE may attempt to transmit S-SS/PSBCH
blocks only in the non-anchor RB set(s) associated with the resource
pool, if the channel access procedure \[15, TS 37.213\] for transmitting
the S-SS/PSBCH blocks fails on the channel including the anchor RB set.
The UE applies CP extension to the first symbol of an S-SS/PSBCH block
and within the first symbol before the first symbol of the S-SS/PSBCH
block according to an index \[4, TS 38.211\] provided by
*sl-CPE-StartingPositionS-SSB*. The UE assumes PRB(s) in an intra-cell
guard band \[6, TS 38.214\] are not used for transmission of S-SS/PSBCH
blocks.

The UE assumes that a S-PSS symbol, a S-SSS symbol, and a PSBCH symbol
have a same transmission power. The UE assumes a same numerology of the
S-SS/PSBCH block as for a SL BWP of the S-SS/PSBCH block reception, and
that a bandwidth of the S-SS/PSBCH block is within a bandwidth of the SL
BWP. The UE assumes the subcarrier with index 0 in the S-SS/PSBCH block
is aligned with a subcarrier with index 0 in an RB of the SL BWP.

A UE is provided, by *sl-NumSSB-WithinPeriod*, a number
$N_{period}^{S - SSB}$ of S-SS/PSBCH blocks in a period of 16 frames.
The UE assumes that a transmission of the S-SS/PSBCH blocks in the
period is with a periodicity of 16 frames. The UE determines indexes of
slots that include S-SS/PSBCH block as
$N_{offset}^{S - SSB}$+$\left( N_{interval}^{S - SSB} + 1 \right) \cdot i_{S - SSB}$,
where

\- index 0 corresponds to a first slot in a frame with SFN of the
serving cell satisfying $(SFN\ mod\ 16) = 0$ or DFN satisfying (DFN mod
16) = 0

\- $i_{S - SSB}$ is a S-SS/PSBCH block index within the number of
S-SS/PSBCH blocks in the period, with
$0 \leq i_{S - SSB} \leq N_{period}^{S - SSB} - 1$

\- $N_{offset}^{S - SSB}$ is a slot offset from a start of the period to
the first slot including S-SS/PSBCH block, provided by
*sl-TimeOffsetSSB*

\- $N_{interval}^{S - SSB}$ is a slot interval between S-SS/PSBCH
blocks, provided by *sl-TimeInterval*

For operation with shared spectrum channel access and for each slot that
includes S-SS/PSBCH blocks, a UE is provided, by
*sl-NumOfAdditionalSSSBOccasion*, a number $N_{additional}^{S - SSB}$ of
additional candidate S-SS/PSBCH block transmission occasions. When the
UE determines to transmit S-SS/PSBCH blocks on additional candidate
S-SS/PSBCH block transmission occasions, the UE attempts to transmit
S-SS/PSBCH blocks at least in the anchor RB set. The UE may attempt to
transmit S-SS/PSBCH blocks only in the non-anchor RB set(s) associated
with the resource pool, if the channel access procedure \[15, TS
37.213\] for transmitting the S-SS/PSBCH blocks fails on the channel
including the anchor RB set. When $N_{additional}^{S - SSB} > 0$, for
S-SS/PSBCH block with index $i_{S - SSB}$, the UE determines indexes of
slots that include the additional candidate S-SS/PSBCH block
transmission occasions as
$N_{offset}^{S - SSB}$+$\left( N_{interval}^{S - SSB} + 1 \right) \cdot i_{S - SSB}$
+$(\ N_{gap}^{S - SSB} + 1) \cdot ({\overline{i}}_{S - SSB} + 1)$, where

\- $N_{gap}^{S - SSB}$ is a slot gap, provided by
*sl-GapOfAdditionalSSSB-Occasion*, for determining the additional
candidate S-SS/PSBCH block transmission occasions, and

\- ${\overline{i}}_{S - SSB}$ is an index of the additional candidate
S-SS/PSBCH block transmission occasions, with
${0 \leq \overline{i}}_{S - SSB} \leq N_{additional}^{S - SSB} - 1$.

For paired spectrum, an S-SS/PSBCH block can be transmitted/received
only in a slot of an UL carrier. For unpaired spectrum, an S-SS/PSBCH
block can be transmitted/received only in a slot of which all OFDM
symbols are configured as UL by *tdd-UL-DL-ConfigurationCommon* of the
serving cell if provided or *sl-TDD-Configuration* if provided or
*sl-TDD-Config* of the received PSBCH if provided. If
*tdd-UL-DL-ConfigurationCommon* and *sl-TDD-Configuration* are not
provided for a spectrum indicated with only PC5 interface in Table
5.2E.1-1 in \[TS 38.101-1\], an S-SS/PSBCH block can be
transmitted/received in any slot of the spectrum.

For transmission of an S-SS/PSBCH block, a UE includes a bit sequence
$a_{0},\ a_{1},\ a_{2},\ a_{3},\ \ldots,\ a_{11}$ in the PSBCH payload
to indicate *sl-TDD-Config* and provide a slot format over a number of
slots.

For paired spectrum, or if *tdd-UL-DL-ConfigurationCommon* and
*sl-TDD-Configuration* are not provided for a spectrum indicated with
only PC5 interface in Table 5.2E.1-1 in \[TS 38.101-1\],

\-
$a_{0},\ a_{1},\ a_{2},\ a_{3},a_{4}{,\ a}_{5},\ a_{6},\ a_{7},a_{8},\ a_{9},\ a_{10},\ a_{11}$
are set to \'1\';

else

\- $a_{0} = 0$ if *pattern1* is provided by *sl-TDD-Configuration* or
*tdd-UL-DL-ConfigurationCommon*; $a_{0} = 1$ if both *pattern1* and
*pattern2* are provided by *sl-TDD-Configuration* or
*tdd-UL-DL-ConfigurationCommon* as described in clause 11.1

\- $a_{1},\ a_{2},\ a_{3},a_{4}$ are determined based on

\- $P$ in *pattern1* as described in Table 16.1-1 for $a_{0} = 0$

\- $P$ in *pattern1* and $P_{2}$ *in pattern2* as described in Table
16.1-2 for $a_{0} = 1$

where $P$ and $P_{2}$ are as described in clause 11.1

\- $a_{5},\ a_{6},\ a_{7},a_{8},\ a_{9},\ a_{10},\ a_{11}$ are the 7th
to 1st LSBs of $u_{slots}^{SL}$, respectively

\- for $a_{0} = 0$,
$u_{slots}^{SL} = u_{slots}*2^{\mu - \mu_{ref}} + \left\lfloor \frac{u_{sym}*2^{\mu - \mu_{ref}}}{L} \right\rfloor + I_{1}$

\- for $a_{0} = 1$,
$u_{slots}^{SL} = \left\lfloor \frac{u_{slots,2}*2^{\mu - \mu_{ref}} + \left\lfloor \frac{u_{sym,2}*2^{\mu - \mu_{ref}}}{L} \right\rfloor + I_{2}}{w} \right\rfloor*\left\lceil \frac{{P*2}^{\mu} + 1}{w} \right\rceil + \left\lfloor \frac{u_{slots}*2^{\mu - \mu_{ref}} + \left\lfloor \frac{u_{sym}*2^{\mu - \mu_{ref}}}{L} \right\rfloor + I_{1}}{w} \right\rfloor$

> where

\- $L$ is the number of symbols in a slot: $L = 12$ if *cyclicPrefix* =
\"ECP\"; else, $L = 14$

\- $I_{1}$ is 1 if $u_{sym}*2^{\mu - \mu_{ref}}\ mod\ L \geq \ L - Y$,
else $I_{1}$ is 0

\- $I_{2}$ is 1 if $u_{sym,2}*2^{\mu - \mu_{ref}}\ mod\ L \geq L - Y$,
else $I_{2}$ is 0

\- $Y$ is the sidelink starting symbol index provided by
*sl-StartingSymbolFirst* when *sl-StartingSymbolFirst* and
*sl-StartingSymbolSecond* are provided for a SL-BWP, or provided by
*sl-StartSymbol* otherwise

\- $w$ is the granularity of slots indication as described in Table
16.1-2

\- $\mu_{ref}$, $u_{slots}$, $u_{sym}$, $u_{slots,2}$, $u_{sym,2}$ are
the parameters of *tdd-UL-DL-ConfigurationCommon* as described in clause
11.1, or the parameters of *sl-TDD-Configuration* as defined in \[12, TS
38.331\]

\- $\mu = 0,\ 1,\ 2,\ 3$ corresponds to SL SCS as defined in \[4, TS
38.211\]

Table 16.1-1: Slot configuration period when one pattern is indicated

+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------+
| $$\mathbf{a}_{\mathbf{1}}\mathbf{,\ }\mathbf{a}_{\mathbf{2}}\mathbf{,\ }\mathbf{a}_{\mathbf{3}}\mathbf{,}\mathbf{a}_{\mathbf{4}}$$ | Slot configuration period of *pattern1*          |
|                                                                                                                                    |                                                  |
|                                                                                                                                    | $\mathbf{P}$ (msec)                              |
+====================================================================================================================================+==================================================+
| 0, 0, 0, 0                                                                                                                         | 0.5                                              |
+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------+
| 0, 0, 0, 1                                                                                                                         | 0.625                                            |
+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------+
| 0, 0, 1, 0                                                                                                                         | 1                                                |
+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------+
| 0, 0, 1, 1                                                                                                                         | 1.25                                             |
+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------+
| 0, 1, 0, 0                                                                                                                         | 2                                                |
+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------+
| 0, 1, 0, 1                                                                                                                         | 2.5                                              |
+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------+
| 0, 1, 1, 0                                                                                                                         | 4                                                |
+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------+
| 0, 1, 1, 1                                                                                                                         | 5                                                |
+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------+
| 1, 0, 0, 0                                                                                                                         | 10                                               |
+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------+
| Reserved                                                                                                                           | Reserved                                         |
+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------+

Table 16.1-2: Slot configuration period and granularity when two
patterns are indicated

+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+-----------------------------------------------+
| $$\mathbf{a}_{\mathbf{1}}\mathbf{,\ }\mathbf{a}_{\mathbf{2}}\mathbf{,\ }\mathbf{a}_{\mathbf{3}}\mathbf{,}\mathbf{a}_{\mathbf{4}}$$ | Slot          | Slot configuration period | Granularity $\mathbf{w}$ in slots with        |
|                                                                                                                                    | configuration | of *pattern2*             | different SCS                                 |
|                                                                                                                                    | period of     |                           |                                               |
|                                                                                                                                    | *pattern1*    | $\mathbf{P}_{\mathbf{2}}$ |                                               |
|                                                                                                                                    |               | (msec)                    |                                               |
|                                                                                                                                    | $\mathbf{P}$  |                           |                                               |
|                                                                                                                                    | (msec)        |                           |                                               |
|                                                                                                                                    |               |                           +-----------+-----------+-----------+-----------+
|                                                                                                                                    |               |                           | 15kHz     | 30 kHz    | 60 kHz    | 120 kHz   |
+====================================================================================================================================+===============+===========================+===========+===========+===========+===========+
| 0, 0, 0, 0                                                                                                                         | 0.5           | 0.5                       | 1                                             |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+                                               |
| 0, 0, 0, 1                                                                                                                         | 0.625         | 0.625                     |                                               |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+                                               |
| 0, 0, 1, 0                                                                                                                         | 1             | 1                         |                                               |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+                                               |
| 0, 0, 1, 1                                                                                                                         | 0.5           | 2                         |                                               |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+                                               |
| 0, 1, 0, 0                                                                                                                         | 1.25          | 1.25                      |                                               |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+                                               |
| 0, 1, 0, 1                                                                                                                         | 2             | 0.5                       |                                               |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+-----------------------------------+-----------+
| 0, 1, 1, 0                                                                                                                         | 1             | 3                         | 1                                 | 2         |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+                                   |           |
| 0, 1, 1, 1                                                                                                                         | 2             | 2                         |                                   |           |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+                                   |           |
| 1, 0, 0, 0                                                                                                                         | 3             | 1                         |                                   |           |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+                                   |           |
| 1, 0, 0, 1                                                                                                                         | 1             | 4                         |                                   |           |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+                                   |           |
| 1, 0, 1, 0                                                                                                                         | 2             | 3                         |                                   |           |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+                                   |           |
| 1, 0, 1, 1                                                                                                                         | 2.5           | 2.5                       |                                   |           |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+                                   |           |
| 1, 1, 0, 0                                                                                                                         | 3             | 2                         |                                   |           |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+                                   |           |
| 1, 1, 0, 1                                                                                                                         | 4             | 1                         |                                   |           |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+-----------------------+-----------+-----------+
| 1, 1, 1, 0                                                                                                                         | 5             | 5                         | 1                     | 2         | 4         |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+-----------+-----------+-----------+-----------+
| 1, 1, 1, 1                                                                                                                         | 10            | 10                        | 1         | 2         | 4         | 8         |
+------------------------------------------------------------------------------------------------------------------------------------+---------------+---------------------------+-----------+-----------+-----------+-----------+

If a UE would transmit or receive an S-SS/PSBCH block, and the
transmission or reception would overlap in time with transmissions or
receptions on the sidelink using E-UTRA radio access, the UE transmits
or receives the signal/channel with the higher priority.

If a UE would transmit or receive sidelink synchronization signals for
E-UTRA radio access, and the transmission or reception would overlap in
time with sidelink transmissions or receptions using NR radio access,
the UE transmits or receives the signal/channel with the higher
priority.