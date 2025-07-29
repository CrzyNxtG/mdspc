# 13 UE procedure for monitoring Type0-PDCCH CSS sets

If during cell search a UE determines from *MIB* that a CORESET for
Type0-PDCCH CSS set is present, as described in clause 4.1, the UE
determines a number of consecutive resource blocks and a number of
consecutive symbols for the CORESET of the Type0-PDCCH CSS set from
*controlResourceSetZero* in *pdcch-ConfigSIB1*, as described in Tables
13-0 through 13-10, for operation without shared spectrum channel access
in FR1, FR2-1 and FR2-NTN, or as described in Tables 13-1A and 13-4A for
operation with shared spectrum channel access in FR1, or as described in
Table 13-10A for FR2-2, and determines PDCCH monitoring occasions from
*searchSpaceZero* in *pdcch-ConfigSIB1*, included in *MIB*, as described
in Tables 13-11 through 13-15A. ${SFN}_{c}$ and $n_{c}$ are the SFN and
slot index within a frame of the CORESET based on SCS of the CORESET and
${SFN}_{SSB,i}$ and $n_{SSB,i}$ are the SFN and slot index based on SCS
of the CORESET, respectively, where the SS/PBCH block with index $i$
overlaps in time with system frame ${SFN}_{SSB,i}$ and slot $n_{SSB,i}$.
The symbols of the CORESET associated with *pdcch-ConfigSIB1* in *MIB*
or with *searchSpaceSIB1* in *PDCCH-ConfigCommon* have normal cyclic
prefix. In Table 13-0, configurations with index 0 to 9 are applicable
when an associated SS/PBCH block is located according to Table 5.4.3.3-2
in \[8-1, TS 38.101-1\], configurations with index 10 to 11 are
applicable when an associated SS/PBCH block is located according to NOTE
12 of Table 5.4.3.3-1 in \[8-1, TS 38.101-1\], and non-interleaved
CCE-to-REG mapping applies for configurations with index 6 to 9. In
Table 13-1, the associated SS/PBCH block is not located according to
NOTE 12 of Table 5.4.3.3-1 in \[8-1, TS 38.101-1\].

For operation with shared spectrum channel access in FR2-2 and for
operation without shared spectrum channel access, a UE assumes that the
offset in Tables 13-0 through 13-10A is defined with respect to the SCS
of the CORESET for Type0-PDCCH CSS set from the smallest RB index of the
CORESET for Type0-PDCCH CSS set to the smallest RB index of the common
RB overlapping with the first RB of the corresponding SS/PBCH block,
after puncturing if any \[4, TS 38.211\]. The SCS of the CORESET for
Type0-PDCCH CSS set is provided by *subCarrierSpacingCommon* for FR1,
FR2-1 and FR2-NTN, and same as the SCS of the corresponding SS/PBCH
block for FR2-2. In Tables 13-7, 13-8, and 13-10, $k_{SSB}$ is defined
in \[4, TS 38.211\].

For operation with shared spectrum channel access in FR1, a UE
determines an offset from a smallest RB index of the CORESET for
Type0-PDCCH CSS set to a smallest RB index of the common RB overlapping
with a first RB of the corresponding SS/PBCH block

\- according to the offset in Table 13-1A or Table 13-4A, if the
frequency position of the SS/PBCH block corresponds to the GSCN of a
synchronization raster entry as defined in \[8-1, TS 38.101-1\], and

\- according to a sum of a first offset and a second offset if the
frequency position of the SS/PBCH block is provided by *ssbFrequency* in
a measurement configuration associated with a reporting configuration
providing *reportCGI* and does not correspond to the GSCN of a
synchronization raster entry as defined in \[8-1, TS 38.101-1\], where

\- the first offset is provided in Table 13-1A or Table 13-4A, and

\- the second offset is determined as the offset from a smallest RB
index of the common RB overlapping with the first RB of the SS/PBCH
block indicated in the measurement configuration to a smallest RB index
of the common RB overlapping with the first RB of a SS/PBCH block
hypothetically located at the GSCN of a synchronization raster entry,
where the single synchronization raster entry is located in the same
channel as the SS/PBCH block used for the shared spectrum channel access
procedure, as described in \[15, TS 37.213\]

where the offsets are defined with respect to the SCS of the CORESET for
Type0-PDCCH CSS set that is same as the SCS of the corresponding SS/PBCH
block.

For operation without shared spectrum channel access and for the SS/PBCH
block and CORESET multiplexing pattern 1, a UE monitors PDCCH in the
Type0-PDCCH CSS set over two slots. For SS/PBCH block with index $i$,
the UE determines an index of slot $n_{0}$ as
$n_{0} = \left( O \bullet 2^{\mu} + \left\lfloor i \bullet M \right\rfloor \right)modN_{slot}^{frame,\mu}\ $
that is in a frame with system frame number (SFN) ${SFN}_{C}$ satisfying
${SFN}_{c}mod2 = 0$ if
$\left\lfloor \frac{\left( O \bullet 2^{\mu} + \left\lfloor i \bullet M \right\rfloor \right)}{N_{slot}^{frame,\mu}} \right\rfloor mod2 = 0$,
or in a frame with SFN satisfying ${SFN}_{c}mod2 = 1$ if
$\left\lfloor \frac{\left( O \bullet 2^{\mu} + \left\lfloor i \bullet M \right\rfloor \right)}{N_{slot}^{frame,\mu}} \right\rfloor mod2 = 1$
where $\mu \in \left\{ 0,1,2,3,5,6 \right\}$ based on the SCS for PDCCH
receptions in the CORESET \[4, TS 38.211\].

\- For $\mu \in \{ 0,\ 1,\ 2,\ 3\}$ and for a SS/PBCH block index $i$,
the two slots including the associated Type0-PDCCH monitoring occasions
are slots $n_{0}$ and $n_{0} + 1$. $M$, $O$, and the index of the first
symbol of the CORESET in slots $n_{0}$ and $n_{0} + 1$ are provided by
Table 13-11 and Table 13-12.

\- For $\mu = 5$ and for a SS/PBCH block index $i$, the two slots
including the associated Type0-PDCCH monitoring occasions are slots
$n_{0}$ and $n_{0} + 4$. $M$, $O$, and the index of the first symbol of
the CORESET in slots $n_{0}$ and $n_{0} + 4$ are provided by Table
13-12A, where $X = 1.25$.

\- For $\mu = 6$ and for a SS/PBCH block index $i$, the two slots
including the associated Type0-PDCCH monitoring occasions are slots
$n_{0}$ and $n_{0} + 8$. $M$, $O$, and the index of the first symbol of
the CORESET in slots $n_{0}$ and $n_{0} + 8$ are provided by Table
13-12A, where $X = 0.625$.

For operation with shared spectrum channel access and for the SS/PBCH
block and CORESET multiplexing pattern 1, a UE monitors PDCCH in the
Type0-PDCCH CSS set over slots that include Type0-PDCCH monitoring
occasions associated with SS/PBCH blocks that are quasi co-located with
the SS/PBCH block that provides a CORESET for Type0-PDCCH CSS set with
respect to average gain, quasi co-location \'typeA\' and \'typeD\'
properties, when applicable \[6, TS 38.214\]. For a candidate SS/PBCH
block index $\overline{i}$, where
$0 \leq \overline{i} \leq {\overline{L}}_{\max} - 1$, two slots include
the associated Type0-PDCCH monitoring occasions. The UE determines an
index of slot $n_{0}$ as
$n_{0} = \left( O \cdot 2^{\mu} + \left\lfloor \overline{i} \cdot M \right\rfloor \right)\ mod\ N_{slot}^{frame,\ \mu}$
that is in a frame with system frame number (SFN) ${SFN}_{C}$ satisfying
${SFN}_{C}\ mod\ 2 = 0$ if
$\left\lfloor \left( O \cdot 2^{\mu} + \left\lfloor \overline{i} \cdot M \right\rfloor \right)/N_{slot}^{frame,\ \mu} \right\rfloor\ mod\ 2 = 0$,
or in a frame with SFN satisfying ${SFN}_{C}\ mod\ 2 = 1$ if
$\left\lfloor \left( O \cdot 2^{\mu} + \left\lfloor \overline{i} \cdot M \right\rfloor \right)/N_{slot}^{frame,\ \mu} \right\rfloor\ mod\ 2 = 1$
where $\mu \in \{ 0,\ 1,3,5,6\}$ based on the SCS for PDCCH receptions
in the CORESET \[4, TS 38.211\].

\- For $\mu \in \{ 0,\ 1\}$ and for a candidate SS/PBCH block index
$\overline{i}$, the two slots including the associated Type0-PDCCH
monitoring occasions are slots $n_{0}$ and $n_{0} + 1$. $M$, $O$, and
the index of the first symbol of the CORESET in slots $n_{0}$ and
$n_{0} + 1$ are provided by Table 13-11. The UE does not expect to be
configured with $M = 1/2$, or with $M = 2$, when $N_{SSB}^{QCL} = 1$.

\- For $\mu = 3$ and for a candidate SS/PBCH block index $\overline{i}$,
the two slots including the associated Type0-PDCCH monitoring occasions
are slots $n_{0}$ and $n_{0} + 1$. $M$, $O$, and the index of the first
symbol of the CORESET in slots $n_{0}$ and $n_{0} + 1$ are provided by
Table 13-12.

\- For $\mu = 5$ and for a candidate SS/PBCH block index $\overline{i}$,
the two slots including the associated Type0-PDCCH monitoring occasions
are slots $n_{0}$ and $n_{0} + 4$. $M$, $O$, and the index of the first
symbol of the CORESET in slots $n_{0}$ and $n_{0} + 4$ are provided by
Table 13-12A, where $X = 1.25$.

\- For $\mu = 6$ and for a candidate SS/PBCH block index $\overline{i}$,
the two slots including the associated Type0-PDCCH monitoring occasions
are slots $n_{0}$ and $n_{0} + 8$. $M$, $O$, and the index of the first
symbol of the CORESET in slots $n_{0}$ and $n_{0} + 8$ are provided by
Table 13-12A, where $X = 0.625$.

For operation without shared spectrum channel access and for the SS/PBCH
block and CORESET multiplexing patterns 2 and 3, a UE monitors PDCCH in
the Type0-PDCCH CSS set over one slot with Type0-PDCCH CSS set
periodicity equal to the periodicity of SS/PBCH block. For a SS/PBCH
block with index $i$, the UE determines the slot index $n_{c}$ and
${SFN}_{c}$ based on parameters provided by Tables 13-13 through 13-15A.

For operation with shared spectrum channel access and for SS/PBCH block
and CORESET multiplexing pattern 3, a UE monitors PDCCH in the
Type0-PDCCH CSS set over slots that include Type0-PDCCH monitoring
occasions associated with SS/PBCH blocks that are quasi co-located with
the SS/PBCH block that provides a CORESET for Type0-PDCCH CSS set with
respect to average gain, quasi co-location \'typeA\' and \'typeD\'
properties, when applicable. For a candidate SS/PBCH block index
$\overline{i}$, where
$0 \leq \overline{i} \leq {\overline{L}}_{\max} - 1$, the periodicity of
the slot including the associated Type0-PDCCH monitoring occasion is
same as the periodicity of the candidate SS/PBCH block, and the UE
determines the slot index $n_{c}$ and ${SFN}_{c}$ based on parameters
provided by Tables 13-15 and 13-15A, where $i$ is replaced by
$\overline{i}$ for operation with shared spectrum channel access in
FR2-2.

For the SS/PBCH block and CORESET multiplexing patterns 2 and 3, if the
active DL BWP is the initial DL BWP, the UE is expected to be able to
perform radio link monitoring, as described in clause 5, and
measurements for radio resource management \[10, TS 38.133\] using a
SS/PBCH block that provides a CORESET for Type0-PDCCH CSS set.

Table 13-0: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {15, 15}
kHz for frequency bands with minimum channel bandwidth 3 MHz and channel
bandwidth 3 MHz or 5 MHz.

+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| **Index** | **SS/PBCH block and    | **Number of RBs**                             | **Number of Symbols**                           | **Offset (RBs)**  |
|           | CORESET multiplexing   | $\mathbf{N}_{\mathbf{RB}}^{\mathbf{CORESET}}$ | $\mathbf{N}_{\mathbf{symb}}^{\mathbf{CORESET}}$ |                   |
|           | pattern**              |                                               |                                                 |                   |
+:=========:+:======================:+:=============================================:+:===============================================:+:=================:+
| 0         | 1                      | 12                                            | 2                                               | 0                 |
+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 1         | 1                      | 12                                            | 3                                               | 0                 |
+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 2         | 1                      | 24                                            | 2                                               | 0                 |
+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 3         | 1                      | 24                                            | 2                                               | 2                 |
+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 4         | 1                      | 24                                            | 3                                               | 0                 |
+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 5         | 1                      | 24                                            | 3                                               | 2                 |
+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 6         | 1                      | 24                                            | 2                                               | 0                 |
+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 7         | 1                      | 24                                            | 2                                               | 2                 |
+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 8         | 1                      | 24                                            | 3                                               | 0                 |
+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 9         | 1                      | 24                                            | 3                                               | 2                 |
+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 10        | 1                      | 24                                            | 2                                               | 0                 |
+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 11        | 1                      | 24                                            | 3                                               | 0                 |
+-----------+------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 12        | Reserved                                                                                                                                     |
+-----------+----------------------------------------------------------------------------------------------------------------------------------------------+
| 13        | Reserved                                                                                                                                     |
+-----------+----------------------------------------------------------------------------------------------------------------------------------------------+
| 14        | Reserved                                                                                                                                     |
+-----------+----------------------------------------------------------------------------------------------------------------------------------------------+
| 15        | Reserved                                                                                                                                     |
+-----------+----------------------------------------------------------------------------------------------------------------------------------------------+

Table 13-1: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {15, 15}
kHz for frequency bands with minimum channel bandwidth 5 MHz or 10 MHz
or with minimum channel bandwidth 3 MHz and channel bandwidth larger
than 3 MHz

+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| Index | SS/PBCH block and        | Number of RBs                                 | Number of Symbols                               | Offset (RBs)      |
|       | CORESET multiplexing     | $\mathbf{N}_{\mathbf{RB}}^{\mathbf{CORESET}}$ | $\mathbf{N}_{\mathbf{symb}}^{\mathbf{CORESET}}$ |                   |
|       | pattern                  |                                               |                                                 |                   |
+=======+==========================+===============================================+=================================================+===================+
| 0     | 1                        | 24                                            | 2                                               | 0                 |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 1     | 1                        | 24                                            | 2                                               | 2                 |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 2     | 1                        | 24                                            | 2                                               | 4                 |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 3     | 1                        | 24                                            | 3                                               | 0                 |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 4     | 1                        | 24                                            | 3                                               | 2                 |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 5     | 1                        | 24                                            | 3                                               | 4                 |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 6     | 1                        | 48                                            | 1                                               | 12                |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 7     | 1                        | 48                                            | 1                                               | 16                |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 8     | 1                        | 48                                            | 2                                               | 12                |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 9     | 1                        | 48                                            | 2                                               | 16                |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 10    | 1                        | 48                                            | 3                                               | 12                |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 11    | 1                        | 48                                            | 3                                               | 16                |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 12    | 1                        | 96                                            | 1                                               | 38                |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 13    | 1                        | 96                                            | 2                                               | 38                |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 14    | 1                        | 96                                            | 3                                               | 38                |
+-------+--------------------------+-----------------------------------------------+-------------------------------------------------+-------------------+
| 15    | Reserved                                                                                                                                       |
+-------+------------------------------------------------------------------------------------------------------------------------------------------------+

Table 13-1A: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {15, 15}
kHz for frequency bands operated with shared spectrum channel access

+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| Index | SS/PBCH block and        | Number of RBs                             | Number of Symbols                           | Offset (RBs)      |
|       | CORESET multiplexing     | $\mathbf{N}_{\text{RB}}^{\text{CORESET}}$ | $\mathbf{N}_{\text{symb}}^{\text{CORESET}}$ |                   |
|       | pattern                  |                                           |                                             |                   |
+=======+==========================+===========================================+=============================================+===================+
| 0     | 1                        | 96                                        | 1                                           | 10                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 1     | 1                        | 96                                        | 1                                           | 12                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 2     | 1                        | 96                                        | 1                                           | 14                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 3     | 1                        | 96                                        | 1                                           | 16                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 4     | 1                        | 96                                        | 2                                           | 10                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 5     | 1                        | 96                                        | 2                                           | 12                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 6     | 1                        | 96                                        | 2                                           | 14                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 7     | 1                        | 96                                        | 2                                           | 16                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 8     | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 9     | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 10    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 11    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 12    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 13    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 14    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 15    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+

Table 13-2: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {15, 30}
kHz for frequency bands with minimum channel bandwidth 5 MHz or 10 MHz

+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| Index | SS/PBCH block and        | Number of RBs                             | Number of Symbols                           | Offset (RBs)      |
|       | CORESET multiplexing     | $\mathbf{N}_{\text{RB}}^{\text{CORESET}}$ | $\mathbf{N}_{\text{symb}}^{\text{CORESET}}$ |                   |
|       | pattern                  |                                           |                                             |                   |
+=======+==========================+===========================================+=============================================+===================+
| 0     | 1                        | 24                                        | 2                                           | 5                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 1     | 1                        | 24                                        | 2                                           | 6                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 2     | 1                        | 24                                        | 2                                           | 7                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 3     | 1                        | 24                                        | 2                                           | 8                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 4     | 1                        | 24                                        | 3                                           | 5                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 5     | 1                        | 24                                        | 3                                           | 6                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 6     | 1                        | 24                                        | 3                                           | 7                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 7     | 1                        | 24                                        | 3                                           | 8                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 8     | 1                        | 48                                        | 1                                           | 18                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 9     | 1                        | 48                                        | 1                                           | 20                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 10    | 1                        | 48                                        | 2                                           | 18                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 11    | 1                        | 48                                        | 2                                           | 20                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 12    | 1                        | 48                                        | 3                                           | 18                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 13    | 1                        | 48                                        | 3                                           | 20                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 14    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 15    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+

Table 13-3: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {30, 15}
kHz for frequency bands with minimum channel bandwidth 5 MHz or 10 MHz
except for the frequency bands defined by note 17 of Table 5.2-1 in
\[8-1, TS 38.101-1\]

+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| Index | SS/PBCH block and        | Number of RBs                             | Number of Symbols                           | Offset (RBs)      |
|       | CORESET multiplexing     | $\mathbf{N}_{\text{RB}}^{\text{CORESET}}$ | $\mathbf{N}_{\text{symb}}^{\text{CORESET}}$ |                   |
|       | pattern                  |                                           |                                             |                   |
+=======+==========================+===========================================+=============================================+===================+
| 0     | 1                        | 48                                        | 1                                           | 2                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 1     | 1                        | 48                                        | 1                                           | 6                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 2     | 1                        | 48                                        | 2                                           | 2                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 3     | 1                        | 48                                        | 2                                           | 6                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 4     | 1                        | 48                                        | 3                                           | 2                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 5     | 1                        | 48                                        | 3                                           | 6                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 6     | 1                        | 96                                        | 1                                           | 28                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 7     | 1                        | 96                                        | 2                                           | 28                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 8     | 1                        | 96                                        | 3                                           | 28                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 9     | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 10    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 11    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 12    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 13    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 14    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 15    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+

Table 13-4: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {30, 30}
kHz for frequency bands with minimum channel bandwidth 5 MHz or 10 MHz
except for the frequency bands defined by note 17 of Table 5.2-1 in
\[8-1, TS 38.101-1\]

  ----------------------------------------------------------------------------------------------------------------------------------------
  Index   SS/PBCH block and CORESET   Number of RBs                               Number of Symbols                             Offset
          multiplexing pattern        $\mathbf{N}_{\text{RB}}^{\text{CORESET}}$   $\mathbf{N}_{\text{symb}}^{\text{CORESET}}$   (RBs)
  ------- --------------------------- ------------------------------------------- --------------------------------------------- ----------
  0       1                           24                                          2                                             0

  1       1                           24                                          2                                             1

  2       1                           24                                          2                                             2

  3       1                           24                                          2                                             3

  4       1                           24                                          2                                             4

  5       1                           24                                          3                                             0

  6       1                           24                                          3                                             1

  7       1                           24                                          3                                             2

  8       1                           24                                          3                                             3

  9       1                           24                                          3                                             4

  10      1                           48                                          1                                             12

  11      1                           48                                          1                                             14

  12      1                           48                                          1                                             16

  13      1                           48                                          2                                             12

  14      1                           48                                          2                                             14

  15      1                           48                                          2                                             16
  ----------------------------------------------------------------------------------------------------------------------------------------

Table 13-4A: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {30, 30}
kHz for frequency bands operated with shared spectrum channel access

+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| Index | SS/PBCH block and        | Number of RBs                             | Number of Symbols                           | Offset (RBs)      |
|       | CORESET multiplexing     | $\mathbf{N}_{\text{RB}}^{\text{CORESET}}$ | $\mathbf{N}_{\text{symb}}^{\text{CORESET}}$ |                   |
|       | pattern                  |                                           |                                             |                   |
+=======+==========================+===========================================+=============================================+===================+
| 0     | 1                        | 48                                        | 1                                           | 0                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 1     | 1                        | 48                                        | 1                                           | 1                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 2     | 1                        | 48                                        | 1                                           | 2                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 3     | 1                        | 48                                        | 1                                           | 3                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 4     | 1                        | 48                                        | 2                                           | 0                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 5     | 1                        | 48                                        | 2                                           | 1                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 6     | 1                        | 48                                        | 2                                           | 2                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 7     | 1                        | 48                                        | 2                                           | 3                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 8     | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 9     | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 10    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 11    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 12    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 13    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 14    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 15    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+

Table 13-5: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {30, 15}
kHz for frequency bands with minimum channel bandwidth 40MHz or for the
frequency bands defined by note 17 of Table 5.2-1 in \[8-1, TS
38.101-1\]

+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| Index | SS/PBCH block and     | Number of RBs                             | Number of Symbols                           | Offset (RBs)      |
|       | CORESET multiplexing  | $\mathbf{N}_{\text{RB}}^{\text{CORESET}}$ | $\mathbf{N}_{\text{symb}}^{\text{CORESET}}$ |                   |
|       | pattern               |                                           |                                             |                   |
+=======+=======================+===========================================+=============================================+===================+
| 0     | 1                     | 48                                        | 1                                           | 4                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 1     | 1                     | 48                                        | 2                                           | 4                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 2     | 1                     | 48                                        | 3                                           | 4                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 3     | 1                     | 96                                        | 1                                           | 0                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 4     | 1                     | 96                                        | 1                                           | 56                |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 5     | 1                     | 96                                        | 2                                           | 0                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 6     | 1                     | 96                                        | 2                                           | 56                |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 7     | 1                     | 96                                        | 3                                           | 0                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 8     | 1                     | 96                                        | 3                                           | 56                |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 9     | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+
| 10    | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+
| 11    | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+
| 12    | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+
| 13    | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+
| 14    | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+
| 15    | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+

Table 13-6: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {30, 30}
kHz for frequency bands with minimum channel bandwidth 40MHz or for the
frequency bands defined by note 17 of Table 5.2-1 in \[8-1, TS
38.101-1\]

+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| Index | SS/PBCH block and     | Number of RBs                             | Number of Symbols                           | Offset (RBs)      |
|       | CORESET multiplexing  | $\mathbf{N}_{\text{RB}}^{\text{CORESET}}$ | $\mathbf{N}_{\text{symb}}^{\text{CORESET}}$ |                   |
|       | pattern               |                                           |                                             |                   |
+=======+=======================+===========================================+=============================================+===================+
| 0     | 1                     | 24                                        | 2                                           | 0                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 1     | 1                     | 24                                        | 2                                           | 4                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 2     | 1                     | 24                                        | 3                                           | 0                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 3     | 1                     | 24                                        | 3                                           | 4                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 4     | 1                     | 48                                        | 1                                           | 0                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 5     | 1                     | 48                                        | 1                                           | 28                |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 6     | 1                     | 48                                        | 2                                           | 0                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 7     | 1                     | 48                                        | 2                                           | 28                |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 8     | 1                     | 48                                        | 3                                           | 0                 |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 9     | 1                     | 48                                        | 3                                           | 28                |
+-------+-----------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 10    | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+
| 11    | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+
| 12    | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+
| 13    | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+
| 14    | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+
| 15    | Reserved                                                                                                                            |
+-------+-------------------------------------------------------------------------------------------------------------------------------------+

Table 13-7: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {120,
60} kHz

+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| Index | SS/PBCH block and       | Number of RBs                             | Number of Symbols                           | Offset (RBs)      |
|       | CORESET multiplexing    | $\mathbf{N}_{\text{RB}}^{\text{CORESET}}$ | $\mathbf{N}_{\text{symb}}^{\text{CORESET}}$ |                   |
|       | pattern                 |                                           |                                             |                   |
+=======+=========================+===========================================+=============================================+===================+
| 0     | 1                       | 48                                        | 1                                           | 0                 |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 1     | 1                       | 48                                        | 1                                           | 8                 |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 2     | 1                       | 48                                        | 2                                           | 0                 |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 3     | 1                       | 48                                        | 2                                           | 8                 |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 4     | 1                       | 48                                        | 3                                           | 0                 |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 5     | 1                       | 48                                        | 3                                           | 8                 |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 6     | 1                       | 96                                        | 1                                           | 28                |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 7     | 1                       | 96                                        | 2                                           | 28                |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 8     | 2                       | 48                                        | 1                                           | -41 if            |
|       |                         |                                           |                                             | $k_{SSB} = 0$     |
|       |                         |                                           |                                             |                   |
|       |                         |                                           |                                             | -42 if            |
|       |                         |                                           |                                             | $k_{SSB} > 0$     |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 9     | 2                       | 48                                        | 1                                           | 49                |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 10    | 2                       | 96                                        | 1                                           | -41 if            |
|       |                         |                                           |                                             | $k_{SSB} = 0$     |
|       |                         |                                           |                                             |                   |
|       |                         |                                           |                                             | -42 if            |
|       |                         |                                           |                                             | $k_{SSB} > 0$     |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 11    | 2                       | 96                                        | 1                                           | 97                |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 12    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 13    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 14    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 15    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+

Table 13-8: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {120,
120} kHz for FR2-1 and FR2-NTN

+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| Index | SS/PBCH block and       | Number of RBs                             | Number of Symbols                           | Offset (RBs)      |
|       | CORESET multiplexing    | $\mathbf{N}_{\text{RB}}^{\text{CORESET}}$ | $\mathbf{N}_{\text{symb}}^{\text{CORESET}}$ |                   |
|       | pattern                 |                                           |                                             |                   |
+=======+=========================+===========================================+=============================================+===================+
| 0     | 1                       | 24                                        | 2                                           | 0                 |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 1     | 1                       | 24                                        | 2                                           | 4                 |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 2     | 1                       | 48                                        | 1                                           | 14                |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 3     | 1                       | 48                                        | 2                                           | 14                |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 4     | 3                       | 24                                        | 2                                           | -20 if            |
|       |                         |                                           |                                             | $k_{SSB} = 0$     |
|       |                         |                                           |                                             |                   |
|       |                         |                                           |                                             | -21 if            |
|       |                         |                                           |                                             | $k_{SSB} > 0$     |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 5     | 3                       | 24                                        | 2                                           | 24                |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 6     | 3                       | 48                                        | 2                                           | -20 if            |
|       |                         |                                           |                                             | $k_{SSB} = 0$     |
|       |                         |                                           |                                             |                   |
|       |                         |                                           |                                             | -21 if            |
|       |                         |                                           |                                             | $k_{SSB} > 0$     |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 7     | 3                       | 48                                        | 2                                           | 48                |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 8     | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 9     | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 10    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 11    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 12    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 13    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 14    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 15    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+

Table 13-9: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {240,
60} kHz

+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| Index | SS/PBCH block and        | Number of RBs                             | Number of Symbols                           | Offset (RBs)      |
|       | CORESET multiplexing     | $\mathbf{N}_{\text{RB}}^{\text{CORESET}}$ | $\mathbf{N}_{\text{symb}}^{\text{CORESET}}$ |                   |
|       | pattern                  |                                           |                                             |                   |
+=======+==========================+===========================================+=============================================+===================+
| 0     | 1                        | 96                                        | 1                                           | 0                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 1     | 1                        | 96                                        | 1                                           | 16                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 2     | 1                        | 96                                        | 2                                           | 0                 |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 3     | 1                        | 96                                        | 2                                           | 16                |
+-------+--------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 4     | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 5     | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 6     | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 7     | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 8     | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 9     | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 10    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 11    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 12    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 13    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 14    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+
| 15    | Reserved                                                                                                                               |
+-------+----------------------------------------------------------------------------------------------------------------------------------------+

Table 13-10: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {240,
120} kHz

+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| Index | SS/PBCH block and       | Number of RBs                             | Number of Symbols                           | Offset (RBs)      |
|       | CORESET multiplexing    | $\mathbf{N}_{\text{RB}}^{\text{CORESET}}$ | $\mathbf{N}_{\text{symb}}^{\text{CORESET}}$ |                   |
|       | pattern                 |                                           |                                             |                   |
+=======+=========================+===========================================+=============================================+===================+
| 0     | 1                       | 48                                        | 1                                           | 0                 |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 1     | 1                       | 48                                        | 1                                           | 8                 |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 2     | 1                       | 48                                        | 2                                           | 0                 |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 3     | 1                       | 48                                        | 2                                           | 8                 |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 4     | 2                       | 24                                        | 1                                           | -41 if            |
|       |                         |                                           |                                             | $k_{SSB} = 0$     |
|       |                         |                                           |                                             |                   |
|       |                         |                                           |                                             | -42 if            |
|       |                         |                                           |                                             | $k_{SSB} > 0$     |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 5     | 2                       | 24                                        | 1                                           | 25                |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 6     | 2                       | 48                                        | 1                                           | -41 if            |
|       |                         |                                           |                                             | $k_{SSB} = 0$     |
|       |                         |                                           |                                             |                   |
|       |                         |                                           |                                             | -42 if            |
|       |                         |                                           |                                             | $k_{SSB} > 0$     |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 7     | 2                       | 48                                        | 1                                           | 49                |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+-------------------+
| 8     | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 9     | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 10    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 11    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 12    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 13    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 14    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+
| 15    | Reserved                                                                                                                              |
+-------+---------------------------------------------------------------------------------------------------------------------------------------+

Table 13-10A: Set of resource blocks and slot symbols of CORESET for
Type0-PDCCH search space set when {SS/PBCH block, PDCCH} SCS is {120,
120} kHz, {480, 480} kHz, or {960, 960} kHz for FR2-2

+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| Index | SS/PBCH block and       | Number of RBs                             | Number of Symbols                           | Offset (RBs)  |
|       | CORESET multiplexing    | $\mathbf{N}_{\text{RB}}^{\text{CORESET}}$ | $\mathbf{N}_{\text{symb}}^{\text{CORESET}}$ |               |
|       | pattern                 |                                           |                                             |               |
+=======+=========================+===========================================+=============================================+===============+
| 0     | 1                       | 24                                        | 2                                           | 0             |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 1     | 1                       | 24                                        | 2                                           | 4             |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 2     | 1                       | 48                                        | 1                                           | 0             |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 3     | 1                       | 48                                        | 1                                           | 14            |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 4     | 1                       | 48                                        | 1                                           | 28            |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 5     | 1                       | 48                                        | 2                                           | 0             |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 6     | 1                       | 48                                        | 2                                           | 14            |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 7     | 1                       | 48                                        | 2                                           | 28            |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 8     | 1                       | 96                                        | 1                                           | 0             |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 9     | 1                       | 96                                        | 1                                           | 76            |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 10    | 1                       | 96                                        | 2                                           | 0             |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 11    | 1                       | 96                                        | 2                                           | 76            |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 12    | 3                       | 24                                        | 2                                           | -20 if        |
|       |                         |                                           |                                             | $k_{SSB} = 0$ |
|       |                         |                                           |                                             |               |
|       |                         |                                           |                                             | -21 if        |
|       |                         |                                           |                                             | $k_{SSB} > 0$ |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 13    | 3                       | 24                                        | 2                                           | 24            |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 14    | 3                       | 48                                        | 2                                           | -20 if        |
|       |                         |                                           |                                             | $k_{SSB} = 0$ |
|       |                         |                                           |                                             |               |
|       |                         |                                           |                                             | -21 if        |
|       |                         |                                           |                                             | $k_{SSB} > 0$ |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+
| 15    | 3                       | 48                                        | 2                                           | 48            |
+-------+-------------------------+-------------------------------------------+---------------------------------------------+---------------+

Table 13-11: Parameters for PDCCH monitoring occasions for Type0-PDCCH
CSS set - SS/PBCH block and CORESET multiplexing pattern 1 and FR1

  ----------------------------------------------------------------------------------------------------------
  Index   $$\mathbf{O}$$   Number of search space    $$\mathbf{M}$$   **First symbol index**
                           sets per slot                              
  ------- ---------------- ------------------------- ---------------- --------------------------------------
  0       0                1                         1                0

  1       0                2                         1/2              {0, if $i$ is even},
                                                                      {$N_{\text{symb}}^{\text{CORESET}}$,
                                                                      if $i$ is odd}

  2       2                1                         1                0

  3       2                2                         1/2              {0, if $i$ is even},
                                                                      {$N_{\text{symb}}^{\text{CORESET}}$,
                                                                      if $i$ is odd}

  4       5                1                         1                0

  5       5                2                         1/2              {0, if $i$ is even},
                                                                      {$N_{\text{symb}}^{\text{CORESET}}$,
                                                                      if $i$ is odd}

  6       7                1                         1                0

  7       7                2                         1/2              {0, if $i$ is even},
                                                                      {$N_{\text{symb}}^{\text{CORESET}}$,
                                                                      if $i$ is odd}

  8       0                1                         2                0

  9       5                1                         2                0

  10      0                1                         1                1

  11      0                1                         1                2

  12      2                1                         1                1

  13      2                1                         1                2

  14      5                1                         1                1

  15      5                1                         1                2
  ----------------------------------------------------------------------------------------------------------

Table 13-12: Parameters for PDCCH monitoring occasions for Type0-PDCCH
CSS set - SS/PBCH block and CORESET multiplexing pattern 1 and FR2-1, or
SS/PBCH block and CORESET multiplexing pattern 1 and FR2-NTN, or SS/PBCH
block and CORESET multiplexing pattern 1 and {SS/PBCH block, PDCCH} SCS
{120, 120} kHz in FR2-2

+-------+-------------------+------------------------+-------------------+--------------------------------------+
| Index | $$\mathbf{O}$$    | Number of search space | $$\mathbf{M}$$    | **First symbol index**               |
|       |                   | sets per slot          |                   |                                      |
+=======+===================+========================+===================+======================================+
| 0     | 0                 | 1                      | 1                 | 0                                    |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 1     | 0                 | 2                      | 1/2               | {0, if $i$ is even}, {7, if $i$ is   |
|       |                   |                        |                   | odd}                                 |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 2     | 2.5               | 1                      | 1                 | 0                                    |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 3     | 2.5               | 2                      | 1/2               | {0, if $i$ is even}, {7, if $i$ is   |
|       |                   |                        |                   | odd}                                 |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 4     | 5                 | 1                      | 1                 | 0                                    |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 5     | 5                 | 2                      | 1/2               | {0, if $i$ is even}, {7, if $i$ is   |
|       |                   |                        |                   | odd}                                 |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 6     | 0                 | 2                      | 1/2               | {0, if $i$ is even},                 |
|       |                   |                        |                   | {$N_{\text{symb}}^{\text{CORESET}}$, |
|       |                   |                        |                   | if $i$ is odd}                       |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 7     | 2.5               | 2                      | 1/2               | {0, if $i$ is even},                 |
|       |                   |                        |                   | {$N_{\text{symb}}^{\text{CORESET}}$, |
|       |                   |                        |                   | if $i$ is odd}                       |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 8     | 5                 | 2                      | 1/2               | {0, if $i$ is even},                 |
|       |                   |                        |                   | {$N_{\text{symb}}^{\text{CORESET}}$, |
|       |                   |                        |                   | if $i$ is odd}                       |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 9     | 7.5               | 1                      | 1                 | 0                                    |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 10    | 7.5               | 2                      | 1/2               | {0, if $i$ is even}, {7, if $i$ is   |
|       |                   |                        |                   | odd}                                 |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 11    | 7.5               | 2                      | 1/2               | {0, if $i$ is even},                 |
|       |                   |                        |                   | {$N_{\text{symb}}^{\text{CORESET}}$, |
|       |                   |                        |                   | if $i$ is odd}                       |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 12    | 0                 | 1                      | 2                 | 0                                    |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 13    | 5                 | 1                      | 2                 | 0                                    |
+-------+-------------------+------------------------+-------------------+--------------------------------------+
| 14    | Reserved                                                                                              |
+-------+-------------------------------------------------------------------------------------------------------+
| 15    | Reserved                                                                                              |
+-------+-------------------------------------------------------------------------------------------------------+

Table 13-12A: Parameters for PDCCH monitoring occasions for Type0-PDCCH
CSS set - SS/PBCH block and CORESET multiplexing pattern 1 and {SS/PBCH
block, PDCCH} SCS {480, 480} kHz or {960, 960} kHz in FR2-2

+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| Index | $$\mathbf{O}$$    | Number of search space   | $$\mathbf{M}$$    | **First symbol index**               |
|       |                   | sets per slot            |                   |                                      |
+=======+===================+==========================+===================+======================================+
| 0     | 0                 | 1                        | 1                 | 0                                    |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 1     | 0                 | 2                        | 1/2               | {0, if $i$ is even}, {7, if $i$ is   |
|       |                   |                          |                   | odd}                                 |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 2     | X                 | 1                        | 1                 | 0                                    |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 3     | X                 | 2                        | 1/2               | {0, if $i$ is even}, {7, if $i$ is   |
|       |                   |                          |                   | odd}                                 |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 4     | 5                 | 1                        | 1                 | 0                                    |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 5     | 5                 | 2                        | 1/2               | {0, if $i$ is even}, {7, if $i$ is   |
|       |                   |                          |                   | odd}                                 |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 6     | 0                 | 2                        | 1/2               | {0, if $i$ is even},                 |
|       |                   |                          |                   | {$N_{\text{symb}}^{\text{CORESET}}$, |
|       |                   |                          |                   | if $i$ is odd}                       |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 7     | X                 | 2                        | 1/2               | {0, if $i$ is even},                 |
|       |                   |                          |                   | {$N_{\text{symb}}^{\text{CORESET}}$, |
|       |                   |                          |                   | if $i$ is odd}                       |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 8     | 5                 | 2                        | 1/2               | {0, if $i$ is even},                 |
|       |                   |                          |                   | {$N_{\text{symb}}^{\text{CORESET}}$, |
|       |                   |                          |                   | if $i$ is odd}                       |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 9     | 5+X               | 1                        | 1                 | 0                                    |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 10    | 5+X               | 2                        | 1/2               | {0, if $i$ is even}, {7, if $i$ is   |
|       |                   |                          |                   | odd}                                 |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 11    | 5+X               | 2                        | 1/2               | {0, if $i$ is even},                 |
|       |                   |                          |                   | {$N_{\text{symb}}^{\text{CORESET}}$, |
|       |                   |                          |                   | if $i$ is odd}                       |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 12    | 0                 | 1                        | 2                 | 0                                    |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 13    | 5                 | 1                        | 2                 | 0                                    |
+-------+-------------------+--------------------------+-------------------+--------------------------------------+
| 14    | Reserved                                                                                                |
+-------+---------------------------------------------------------------------------------------------------------+
| 15    | Reserved                                                                                                |
+-------+---------------------------------------------------------------------------------------------------------+

Table 13-13: PDCCH monitoring occasions for Type0-PDCCH CSS set -
SS/PBCH block and CORESET multiplexing pattern 2 and {SS/PBCH block,
PDCCH} SCS {120, 60} kHz

+-------+------------------------------------+---------------------------------+
| Index | PDCCH monitoring occasions (SFN    | **First symbol index**          |
|       | and slot number)                   |                                 |
|       |                                    | **(*k* = 0, 1, ... 15)**        |
+=======+:==================================:+:===============================:+
| 0     | $${SFN}_{c} = {SFN}_{SSB,i}$$      | 0, 1, 6, 7 for                  |
|       |                                    |                                 |
|       | $n_{c} = n_{SSB,i}$                | $i = 4k$, $i = 4k + 1$,         |
|       |                                    | $i = 4k + 2$, $i = 4k + 3$      |
+-------+------------------------------------+---------------------------------+
| 1     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 2     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 3     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 4     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 5     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 6     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 7     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 8     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 9     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 10    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 11    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 12    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 13    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 14    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 15    | Reserved                                                             |
+-------+----------------------------------------------------------------------+

Table 13-14: PDCCH monitoring occasions for Type0-PDCCH CSS set -
SS/PBCH block and CORESET multiplexing pattern 2 and {SS/PBCH block,
PDCCH} SCS {240, 120} kHz

+-------+---------------------------------+-----------------------------------------+
| Index | PDCCH monitoring occasions (SFN | **First symbol index**                  |
|       | and slot number)                |                                         |
|       |                                 | **(*k* = 0, 1, ..., 7)**                |
+=======+:===============================:+:=======================================:+
| 0     | $${SFN}_{c} = {SFN}_{SSB,i}$$   | 0, 1, 2, 3, 0, 1 in $i = 8k$,           |
|       |                                 | $i = 8k + 1$, $i = 8k + 2$,             |
|       | $n_{c} = n_{SSB,i}$ or          | $i = 8k + 3$, $i = 8k + 6$,             |
|       | $n_{c} = n_{SSB,i} - 1$         | $i = 8k + 7$ ($n_{c} = n_{SSB,i}$)      |
|       |                                 |                                         |
|       |                                 | 12, 13 in $i = 8k + 4$, $i = 8k + 5$    |
|       |                                 | ($n_{c} = n_{SSB,i} - 1$)               |
+-------+---------------------------------+-----------------------------------------+
| 1     | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 2     | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 3     | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 4     | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 5     | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 6     | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 7     | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 8     | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 9     | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 10    | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 11    | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 12    | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 13    | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 14    | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+
| 15    | Reserved                                                                  |
+-------+---------------------------------------------------------------------------+

Table 13-15: PDCCH monitoring occasions for Type0-PDCCH CSS set -
SS/PBCH block and CORESET multiplexing pattern 3 and {SS/PBCH block,
PDCCH} SCS {120, 120} kHz

+-------+------------------------------------+---------------------------------+
| Index | PDCCH monitoring occasions (SFN    | **First symbol index**          |
|       | and slot number)                   |                                 |
|       |                                    | **(*k* = 0, 1, ... 15)**        |
+=======+:==================================:+:===============================:+
| 0     | $${SFN}_{c} = {SFN}_{SSB,i}$$      | 4, 8, 2, 6 in                   |
|       |                                    |                                 |
|       | $n_{c} = n_{SSB,i}$                | $i = 4k$, $i = 4k + 1$,         |
|       |                                    | $i = 4k + 2$, $i = 4k + 3$      |
+-------+------------------------------------+---------------------------------+
| 1     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 2     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 3     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 4     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 5     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 6     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 7     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 8     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 9     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 10    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 11    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 12    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 13    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 14    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 15    | Reserved                                                             |
+-------+----------------------------------------------------------------------+

Table 13-15A: PDCCH monitoring occasions for Type0-PDCCH CSS set -
SS/PBCH block and CORESET multiplexing pattern 3 and {SS/PBCH block,
PDCCH} SCS {480, 480} kHz or {960, 960} kHz

+-------+------------------------------------+---------------------------------+
| Index | PDCCH monitoring occasions (SFN    | **First symbol index**          |
|       | and slot number)                   |                                 |
|       |                                    | **(*k* = 0, 1, ... 31)**        |
+=======+:==================================:+:===============================:+
| 0     | $${SFN}_{c} = {SFN}_{SSB,i}$$      | 2, 9 in                         |
|       |                                    |                                 |
|       | $$n_{c} = n_{SSB,i}$$              | $i = 2k$, $i = 2k + 1$          |
+-------+------------------------------------+---------------------------------+
| 1     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 2     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 3     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 4     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 5     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 6     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 7     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 8     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 9     | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 10    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 11    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 12    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 13    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 14    | Reserved                                                             |
+-------+----------------------------------------------------------------------+
| 15    | Reserved                                                             |
+-------+----------------------------------------------------------------------+

If a UE detects a first SS/PBCH block and determines that a CORESET for
Type0-PDCCH CSS set is not present, and for $24 \leq k_{SSB} \leq 29$
for FR1 or for $12 \leq k_{SSB} \leq 13$ for FR2, the UE may determine
the nearest (in the corresponding frequency direction) global
synchronization channel number (GSCN) of a second SS/PBCH block having a
CORESET for an associated Type0-PDCCH CSS set as
$N_{GSCN}^{Reference} + N_{GSCN}^{Size} \cdot N_{GSCN}^{Offset}$.
$N_{GSCN}^{Reference}$ is the GSCN of the first SS/PBCH block,
$N_{GSCN}^{Size} = 1$ in FR1, FR2-1 and FR2-NTN, $N_{GSCN}^{Size} =$ 3
in FR2-2, and $N_{GSCN}^{Offset}$ is a GSCN offset provided by Table
13-16 for FR1 and Table 13-17 for FR2. If the UE detects the second
SS/PBCH block and the second SS/PBCH block does not provide a CORESET
for Type0-PDCCH CSS set, as described in clause 4.1, the UE may ignore
the information related to GSCN of SS/PBCH block locations for
performing cell search.

If a UE detects a SS/PBCH block and determines that a CORESET for
Type0-PDCCH CSS set is not present, and for $k_{SSB} = 31$ for FR1 or
for $k_{SSB} = 15$ for FR2, the UE determines that there is no SS/PBCH
block having an associated Type0-PDCCH CSS set within a GSCN range
$\left\lbrack {N_{GSCN}^{Reference} - N_{GSCN}^{Start},\ N}_{GSCN}^{Reference} + N_{GSCN}^{End} \right\rbrack$.
$N_{GSCN}^{Start}$and $N_{GSCN}^{End}$ are respectively determined by
*controlResourceSetZero* and *searchSpaceZero* in *pdcch-ConfigSIB1*. If
the GSCN range is
$\left\lbrack {N_{GSCN}^{Reference},\ N}_{GSCN}^{Reference} \right\rbrack$,
the UE determines that there is no information for a second SS/PBCH
block with a CORESET for an associated Type0-PDCCH CSS set on the
detected SS/PBCH block.

If a UE does not detect any SS/PBCH block providing a CORESET for
Type0-PDCCH CSS set, as described in clause 4.1, within a time period
determined by the UE, the UE may ignore the information related to GSCN
of SS/PBCH locations in performing cell search.

Table 13-16: Mapping between the combination of
$\mathbf{k}_{\mathbf{SSB}}$ and *controlResourceSetZero* and
*searchSpaceZero* in *pdcch-ConfigSIB1* to
$\mathbf{N}_{\mathbf{GSCN}}^{\mathbf{Offset}}$ for FR1

  ----------------------------------------------------------------------------
   $$k_{SSB}$$    *16×controlResourceSetZero       $$N_{GSCN}^{Offset}$$
                      +searchSpaceZero*       
  -------------- ---------------------------- --------------------------------
        24              0, 1, ..., 255                 1, 2, ..., 256

        25              0, 1, ..., 255               257, 258, ..., 512

        26              0, 1, ..., 255              513, 514, ...., 768

        27              0, 1, ..., 255               -1, -2, ..., -256

        28              0, 1, ..., 255             -257, -258, ..., -512

        29              0, 1, ..., 255             -513, -514, ...., -768

        30              0, 1, ..., 255            Reserved, Reserved, ...,
                                                          Reserved
  ----------------------------------------------------------------------------

Table 13-17: Mapping between the combination of
$\mathbf{k}_{\mathbf{SSB}}$ and *controlResourceSetZero* and
*searchSpaceZero* in *pdcch-ConfigSIB1* to
$\mathbf{N}_{\mathbf{GSCN}}^{\mathbf{Offset}}$ for FR2

  ----------------------------------------------------------------------------
   $$k_{SSB}$$    *16×controlResourceSetZero       $$N_{GSCN}^{Offset}$$
                      +searchSpaceZero*       
  -------------- ---------------------------- --------------------------------
        12              0, 1, ..., 255                 1, 2, ..., 256

        13              0, 1, ..., 255               -1, -2, ..., -256

        14              0, 1, ..., 255            Reserved, Reserved, ...,
                                                          Reserved
  ----------------------------------------------------------------------------