## 4.1 Cell search

Cell search is the procedure for a UE to acquire time and frequency
synchronization with a cell and to detect the physical layer Cell ID of
the cell.

A UE receives the following synchronization signals (SS) in order to
perform cell search: the primary synchronization signal (PSS) and
secondary synchronization signal (SSS) as defined in \[4, TS 38.211\].

A UE assumes that reception occasions of a physical broadcast channel
(PBCH), PSS, and SSS are in consecutive symbols, as defined in \[4, TS
38.211\], and form a SS/PBCH block. The UE assumes that SSS, PBCH DM-RS,
and PBCH data have same EPRE. The UE may assume that the ratio of PSS
EPRE to SSS EPRE in a SS/PBCH block is either 0 dB or 3 dB. If the UE
has not been provided dedicated higher layer parameters, the UE may
assume that the ratio of PDCCH DMRS EPRE to SSS EPRE is within -8 dB and
8 dB when the UE monitors PDCCHs for a DCI format 1_0 with CRC scrambled
by SI-RNTI, P-RNTI, or RA-RNTI, or for a DCI format 2_7, or for a DCI
format 4_0.

For a half frame with SS/PBCH blocks, the first symbol indexes for
candidate SS/PBCH blocks are determined according to the SCS of SS/PBCH
blocks as follows, where index 0 corresponds to the first symbol of the
first slot in a half-frame.

\- Case A - 15 kHz SCS: the first symbols of the candidate SS/PBCH
blocks have indexes of $\left\{ 2,8 \right\} + 14 \cdot n$.

\- For operation without shared spectrum channel access:

\- For carrier frequencies smaller than or equal to 3 GHz, $n = 0,1$.

\- For carrier frequencies within FR1 larger than 3 GHz, $n = 0,1,2,3$.

\- For operation with shared spectrum channel access, as described in
\[15, TS 37.213\], $n = 0,\ 1,\ 2,\ 3,\ 4$.

\- Case B - 30 kHz SCS: the first symbols of the candidate SS/PBCH
blocks have indexes $\left\{ 4,8,16,20 \right\} + 28 \cdot n$. For
carrier frequencies smaller than or equal to 3 GHz, $n = 0$. For carrier
frequencies within FR1 larger than 3 GHz, $n = 0,1$.

\- Case C - 30 kHz SCS: the first symbols of the candidate SS/PBCH
blocks have indexes $\left\{ 2,8 \right\} + 14 \cdot n$.

\- For operation without shared spectrum channel access

\- For paired spectrum operation

\- For carrier frequencies smaller than or equal to 3 GHz, $n = 0,1$.
For carrier frequencies within FR1 larger than 3 GHz, $n = 0,1,2,3$.

\- For unpaired spectrum operation

\- For carrier frequencies smaller than 1.88 GHz, $n = 0,1$. For carrier
frequencies within FR1 equal to or larger than 1.88 GHz, $n = 0,1,2,3$.

\- For operation with shared spectrum channel access,
$n = 0,\ 1,\ 2,\ 3,\ 4,\ 5,\ 6,\ 7,\ 8,\ 9$.

\- Case D - 120 kHz SCS: the first symbols of the candidate SS/PBCH
blocks have indexes $\left\{ 4,8,16,20 \right\} + 28 \cdot n$. For
carrier frequencies within FR2 and FR2-NTN,
$n = 0,\ 1,\ 2,\ 3,\ 5,\ 6,\ 7,\ 8,\ 10,\ 11,\ 12,\ 13,\ 15,\ 16,\ 17,\ 18$.

\- Case E - 240 kHz SCS: the first symbols of the candidate SS/PBCH
blocks have indexes
$\left\{ 8,12,16,20,32,36,40,44 \right\} + 56 \cdot n$. For carrier
frequencies within FR2-1 and FR2-NTN,
$n = 0,\ 1,\ 2,\ 3,\ 5,\ 6,\ 7,\ 8$.

\- Case F -- 480 kHz SCS: the first symbols of the candidate SS/PBCH
blocks have indexes $\left\{ 2,\ 9 \right\} + 14 \cdot n$. For carrier
frequencies within FR2-2,
$n = 0,\ 1,\ 2,\ 3,\ 4,\ 5,\ 6,\ 7,\ 8,\ 9,\ 10,\ 11,\ 12,\ 13,\ 14,\ 15,\ 16,\ 17,\ 18,\ 19,\ 20,\ 21,\ 22,\ 23,\ 24,\ 25,\ 26,\ 27,\ 28,\ 29,\ 30,\ 31.$

\- Case G -- 960 kHz SCS: the first symbols of the candidate SS/PBCH
blocks have indexes $\left\{ 2,\ 9 \right\} + 14 \cdot n$. For carrier
frequencies within FR2-2,
$n = 0,\ 1,\ 2,\ 3,\ 4,\ 5,\ 6,\ 7,\ 8,\ 9,\ 10,\ 11,\ 12,\ 13,\ 14,\ 15,\ 16,\ 17,\ 18,\ 19,\ 20,\ 21,\ 22,\ 23,\ 24,\ 25,\ 26,\ 27,\ 28,\ 29,\ 30,\ 31.$

From the above cases, if the SCS of SS/PBCH blocks is not provided by
*ssbSubcarrierSpacing*, the applicable cases for a cell depend on a
respective frequency band, as provided in \[8-1, TS 38.101-1\], \[8-2,
TS 38.101-2\] and \[8-5, TS 38.101-5\]. A same case applies for all
SS/PBCH blocks on the cell. If a 30 kHz SS/PBCH block SCS is indicated
by *ssbSubcarrierSpacing*, Case B applies for frequency bands with only
15 kHz SS/PBCH block SCS as specified in \[8-1, TS 38.101-1\] and \[8-5,
TS 38.101-5\], and the case specified for 30 kHz SS/PBCH block SCS in
\[8-1, TS 38.101-1\] and \[8-5, TS 38.101-5\] applies for frequency
bands with 30 kHz SS/PBCH block SCS or both 15 kHz and 30 kHz SS/PBCH
block SCS as specified in \[8-1, TS 38.101-1\] and \[8-5, TS 38.101-5\].
For a UE configured to operate with carrier aggregation over a set of
cells in a frequency band of FR2 or with frequency-contiguous carrier
aggregation over a set of cells in a frequency band of FR1, if the UE is
provided SCS values by *ssbSubcarrierSpacing* for receptions of SS/PBCH
blocks on any cells from the set of cells, the UE expects the SCS values
to be same.

The candidate SS/PBCH blocks in a half frame are indexed in an ascending
order in time from 0 to ${\overline{L}}_{\max} - 1$, where
${\overline{L}}_{\max}$ is determined according to SS/PBCH block
patterns for Cases A through G. $L_{\max}$ is a maximum number of
SS/PBCH block indexes in a cell, and the maximum number of transmitted
SS/PBCH blocks within a half frame is $L_{\max}$.

\- For operation without shared spectrum channel access in FR1 and FR2,
and for operation with shared spectrum channel access in FR2-2,
$L_{\max} = {\overline{L}}_{\max}$

\- For operation with shared spectrum channel access in FR1,
$L_{\max} = 8$ for ${\overline{L}}_{\max} = 10$ and 15 kHz SCS of
SS/PBCH blocks and for ${\overline{L}}_{\max} = 20$ and 30 kHz SCS of
SS/PBCH blocks

For ${\overline{L}}_{\max} = 4$, a UE determines the 2 LSB bits of a
candidate SS/PBCH block index per half frame from a one-to-one mapping
with an index of the DM-RS sequence transmitted in the PBCH as described
in \[4, TS 38.211\].

For ${\overline{L}}_{\max} > 4$, a UE determines the 3 LSB bits of a
candidate SS/PBCH block index per half frame from a one-to-one mapping
with an index of the DM-RS sequence transmitted in the PBCH as described
in \[4, TS 38.211\]

\- for ${\overline{L}}_{\max} = 10$, the UE determines the 1 MSB bit of
the candidate SS/PBCH block index from PBCH payload bit
${\bar{a}}_{\bar{A} + 7}$ as described in \[5, TS 38.212\]

\- for ${\overline{L}}_{\max} = 20$, the UE determines the 2 MSB bits of
the candidate SS/PBCH block index from PBCH payload bits
${\bar{a}}_{\bar{A} + 6},{\bar{a}}_{\bar{A} + 7}$ as described in \[5,
TS 38.212\]

\- for ${\overline{L}}_{\max} = 64$, the UE determines the 3 MSB bits of
the candidate SS/PBCH block index from PBCH payload bits
${\bar{a}}_{\bar{A} + 5},{\bar{a}}_{\bar{A} + 6},{\bar{a}}_{\bar{A} + 7}$
as described in \[5, TS 38.212\]

A UE can be provided per serving cell by *ssb-periodicityServingCell* a
periodicity of the half frames for reception of the SS/PBCH blocks for
the serving cell. If the UE is not configured a periodicity of the half
frames for receptions of the SS/PBCH blocks, the UE assumes a
periodicity of a half frame. A UE assumes that the periodicity is same
for all SS/PBCH blocks in the serving cell.

For initial cell selection, a UE may assume that half frames with
SS/PBCH blocks occur with a periodicity of 2 frames.

For operation without shared spectrum channel access, an SS/PBCH block
index is same as a candidate SS/PBCH block index.

For operation with shared spectrum channel access, a UE assumes that
transmission of SS/PBCH blocks in a half frame is within a discovery
burst transmission window that starts from the first symbol of the first
slot in a half-frame. The UE can be provided per serving cell by
*discoveryBurstWindowLength* a duration of the discovery burst
transmission window. If *discoveryBurstWindowLength* is not provided,
the UE assumes that the duration of the discovery burst transmission
window is a half frame. For a serving cell, the UE assumes that a
periodicity of the discovery burst transmission window is same as a
periodicity of half frames for receptions of SS/PBCH blocks in the
serving cell. The UE assumes that one or more SS/PBCH blocks indicated
by *ssb-PositionsInBurst* may be transmitted within the discovery burst
transmission window and have candidate SS/PBCH blocks indexes
corresponding to SS/PBCH block indexes provided by
*ssb-PositionsInBurst*. If MSB $k$, $k \geq 1$, of
*ssb-PositionsInBurst* is set to 1, the UE assumes that SS/PBCH block(s)
within the discovery burst transmission window with candidate SS/PBCH
block index(es) corresponding to SS/PBCH block index equal to $k - 1$
may be transmitted; if MSB $k$ is set to 0, the UE assumes that the
SS/PBCH block(s) are not transmitted. If MSB $k$, $k \geq 1$, of
*inOneGroup* is set to 1, and MSB $m$, $m \geq 1$, of *groupPresence* is
set to 1, the UE assumes that SS/PBCH block(s) within the discovery
burst transmission window with candidate SS/PBCH block index(es)
corresponding to SS/PBCH block index determined by $k$ and $m$ may be
transmitted; otherwise, the UE assumes that the SS/PBCH block(s) are not
transmitted.

For operation with shared spectrum channel access in FR1, a UE assumes
that SS/PBCH blocks in a serving cell that are within a same discovery
burst transmission window or across discovery burst transmission windows
are quasi co-located with respect to average gain, quasi co-location
\'typeA\' and \'typeD\' properties, when applicable \[6, TS 38.214\], if
a value of $\left( N_{DM - RS}^{PBCH}{mod}N_{SSB}^{QCL} \right)$ is same
among the SS/PBCH blocks. $N_{DM - RS}^{PBCH}$ is an index of a DM-RS
sequence transmitted in a PBCH of a corresponding SS/PBCH block, and
$N_{SSB}^{QCL}$ is either provided by *ssb-PositionQCL* or, if
*ssb-PositionQCL* is not provided, obtained from a *MIB* provided by a
SS/PBCH block according to Table 4.1-1 with $k_{SSB} < 24$ \[4, TS
38.211\]. The UE can determine an SS/PBCH block index according to
$\left( N_{DM - RS}^{PBCH}{mod}N_{SSB}^{QCL} \right)$, or according to
$\left( \overline{i}\ {mod}N_{SSB}^{QCL} \right)$ where $\overline{i}$
is the candidate SS/PBCH block index. The UE assumes that within a
discovery burst transmission window, a number of transmitted SS/PBCH
blocks on a serving cell is not larger than $N_{SSB}^{QCL}$ and a number
of transmitted SS/PBCH blocks with a same SS/PBCH block index is not
larger than one.

Table 4.1-1: Mapping between the combination of
*subCarrierSpacingCommon* and LSB of *ssb-SubcarrierOffset* to
$\mathbf{N}_{\mathbf{SSB}}^{\mathbf{QCL}}$ for operation with shared
spectrum channel access in FR1

  -----------------------------------------------------------------------------------------------------------
  *subCarrierSpacingCommon*   LSB of *ssb-SubcarrierOffset*    $$\mathbf{N}_{\mathbf{SSB}}^{\mathbf{QCL}}$$
  --------------------------- -------------------------------- ----------------------------------------------
  scs15or60                   0                                1

  scs15or60                   1                                2

  scs30or120                  0                                4

  scs30or120                  1                                8
  -----------------------------------------------------------------------------------------------------------

For operation with shared spectrum channel access in FR2-2, a UE assumes
that SS/PBCH blocks in a serving cell that are within a same discovery
burst transmission window or across discovery burst transmission windows
are quasi co-located with respect to average gain, quasi co-location
\'typeA\' and \'typeD\' properties, when applicable, if a value of
$\left( \overline{i}{mod}N_{SSB}^{QCL} \right)$ is same among the
SS/PBCH blocks, where $\overline{i}$ is the candidate SS/PBCH block
index. $N_{SSB}^{QCL}$ is either provided by *ssb-PositionQCL* or, if
*ssb-PositionQCL* is not provided, obtained from a *MIB* provided by a
SS/PBCH block according to Table 4.1-2. The UE can determine an SS/PBCH
block index according to
$\left( \overline{i}\ {mod}N_{SSB}^{QCL} \right)$. The UE assumes that
within a discovery burst transmission window, a number of transmitted
SS/PBCH blocks on a serving cell is not larger than $N_{SSB}^{QCL}$ and
a number of transmitted SS/PBCH blocks with a same SS/PBCH block index
is not larger than one.

Table 4.1-2: Mapping between *subCarrierSpacingCommon* to
$\mathbf{N}_{\mathbf{SSB}}^{\mathbf{QCL}}$ for operation with shared
spectrum channel access in FR2-2

  -------------------------------------------------------------------------------------------
  *subCarrierSpacingCommon*                    $$\mathbf{N}_{\mathbf{SSB}}^{\mathbf{QCL}}$$
  -------------------------------------------- ----------------------------------------------
  scs15or60                                    32

  scs30or120                                   64
  -------------------------------------------------------------------------------------------

For operation without shared spectrum channel access in FR2-2, a UE
expects a MIB in a SS/PBCH block to provide *subCarrierSpacingCommon* =
\'scs30or120\'.

Upon detection of a SS/PBCH block, the UE determines from *MIB* that a
CORESET for Type0-PDCCH CSS set, as described in clause 13, is present
if $k_{SSB} < 24$ \[4, TS 38.211\] for FR1 or if $k_{SSB} < 12$ for FR2.
The UE determines from *MIB* that a CORESET for Type0-PDCCH CSS set is
not present if $k_{SSB} > 23$ for FR1 or if $k_{SSB} > 11$ for FR2; the
CORESET for Type0-PDCCH CSS set may be provided by *PDCCH-ConfigCommon*.

For a serving cell without transmission of SS/PBCH blocks, a UE acquires
time and frequency synchronization with the serving cell based on
receptions of SS/PBCH blocks on the PCell, or on the PSCell, or on an
SCell if applicable as described in \[10, TS 38.133\], of the cell group
for the serving cell.