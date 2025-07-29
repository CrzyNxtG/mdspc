## 9.3 UCI reporting in physical uplink shared channel

Offset values are defined for a UE to determine a number of resources
for multiplexing HARQ-ACK information and for multiplexing CSI reports
in a PUSCH. Offset values are also defined for multiplexing CG-UCI or
UTO-UCI \[5, TS 38.212\] in a CG-PUSCH. The offset values are signalled
to a UE either by a DCI format scheduling the PUSCH transmission or by
higher layers.

If a DCI format that does not include a beta_offset indicator field
schedules the PUSCH transmission from the UE and the UE is provided
*betaOffsets = \'semiStatic\'* or *betaOffsetsDCI-0-2 =
\'semiStaticDCI-0-2\'*, the UE applies the
$\beta_{offset}^{HARQ - ACK}$, $\beta_{offset}^{CSI - 1}$, and
$\beta_{offset}^{CSI - 2}$ values that are provided by *betaOffsets =
\'semiStatic\'* for DCI formats 0_0/0_1/0_3 or by *betaOffsetsDCI-0-2 =
\'semiStaticDCI-0-2\'* for DCI format 0_2 for the corresponding HARQ-ACK
information, Part 1 CSI reports and Part 2 CSI reports. If the PUSCH
transmission has priority 0 or priority 1 and the UE is configured by
*uci-MuxWithDiffPrio* to multiplex HARQ-ACK information of priority 1 or
priority 0, respectively, and if the UE multiplexes HARQ-ACK information
of priority 1 or priority 0, the UE applies corresponding
$\beta_{offset}^{HARQ - ACK,1}$ or $\beta_{offset}^{HARQ - ACK,0}$
provided by *betaOffsetsCrossPri1* *= \'semiStatic\'* for DCI formats
0_0/0_1/0_3 and by *betaOffsetsCrossPri1DCI-0-2= \'semiStatic\'* for DCI
format 0_2, or by *betaOffsetsCrossPri0 = \'semiStatic\'* for DCI format
0_0/0_1/0_3 and by *betaOffsetsCrossPri0DCI-0-2= \'semiStatic\'* for DCI
format 0_2, respectively.

If the PUSCH transmission is with a configured grant and the UE is
provided *CG-UCI-OnPUSCH= \'semiStatic\'*, the UE applies the
$\beta_{offset}^{HARQ - ACK}$, $\beta_{offset}^{CSI - 1}$, and
$\beta_{offset}^{CSI - 2}$ values that are provided by *CG-UCI-OnPUSCH =
\'semiStatic\'* for the corresponding HARQ-ACK information, Part 1 CSI
reports and Part 2 CSI reports. If the PUSCH transmission has priority 0
or priority 1 and the UE is configured by *uci-MuxWithDiffPrio* to
multiplex HARQ-ACK information of priority 1 or priority 0,
respectively, and if the UE multiplexes HARQ-ACK information of priority
1 or priority 0, the UE applies corresponding
$\beta_{offset}^{HARQ - ACK,1}$ or $\beta_{offset}^{HARQ - ACK,0}$
provided by *cg-betaOffsetsCrossPri1* *= \'semiStatic\'* or
*cg-betaOffsetsCrossPri0 = \'semiStatic\'*, respectively.

If the PUSCH transmission is scheduled by DCI format 0_0 and the UE is
provided *betaOffsets = \'dynamic\'*, the UE applies the
$\beta_{offset}^{HARQ - ACK}$, $\beta_{offset}^{CSI - 1}$, and
$\beta_{offset}^{CSI - 2}$ values that are determined from the first
value of *betaOffsets = \'dynamic\'*. If the UE is configured by
*uci-MuxWithDiffPrio* to multiplex HARQ-ACK information of priority 1,
the UE applies corresponding $\beta_{offset}^{HARQ - ACK,1}$ provided by
the first value of *betaOffsetsCrossPri1* *= \'dynamic\'*.

If the PUSCH transmission is a configured grant Type 2 PUSCH and the UE
is provided *CG-UCI-OnPUSCH* =*\'dynamic\'*, the UE applies the
$\beta_{offset}^{HARQ - ACK}$, $\beta_{offset}^{CSI - 1}$, and
$\beta_{offset}^{CSI - 2}$ values that are determined from the first
value of *CG-UCI-OnPUSCH = \'dynamic\'*. If the PUSCH transmission has
priority 0 or priority 1 and the UE is configured by
*uci-MuxWithDiffPrio* to multiplex HARQ-ACK information of priority 1 or
priority 0, respectively, and if the UE multiplexes HARQ-ACK information
of priority 1 or priority 0, the UE applies corresponding
$\beta_{offset}^{HARQ - ACK,1}$ or $\beta_{offset}^{HARQ - ACK,0}$
provided by the first value of *cg-betaOffsetsCrossPri1* *= \'dynamic\'*
or *cg-betaOffsetsCrossPri0* *= \'dynamic\'*, respectively.

HARQ-ACK information offsets $\beta_{offset}^{HARQ - ACK}$ are
configured to values according to Table 9.3-1. The
*betaOffsetACK-Index1*, *betaOffsetACK-Index2*, and
*betaOffsetACK-Index3* respectively provide indexes
$I_{offset,0}^{HARQ - ACK}$, $I_{offset,1}^{HARQ - ACK}$, and
$I_{offset,2}^{HARQ - ACK}$ for the UE to use if the UE multiplexes up
to 2 HARQ-ACK information bits, more than 2 and up to 11 HARQ-ACK
information bits, and more than 11 bits in the PUSCH, respectively.

Offsets $\beta_{offset}^{HARQ - ACK,0}$ for multiplexing HARQ-ACK
information with priority 0 in a PUSCH transmission with priority 1 are
configured to values according to Table 9.3-1. The first, second and
third values provided by any of *betaOffsetsCrossPri0*,
*betaOffsetsCrossPri0DCI-0-2*, or *cg-betaOffsetsCrossPri0* respectively
provide indexes $I_{offset,0}^{HARQ - ACK,0}$,
$I_{offset,1}^{HARQ - ACK,0}$, and $I_{offset,2}^{HARQ - ACK,0}$ for the
UE to use if the UE multiplexes up to 2 bits, more than 2 and up to 11
bits, and more than 11 bits of HARQ-ACK information with priority 0 in
the PUSCH transmission with priority 1, respectively.

Offsets $\beta_{offset}^{HARQ - ACK,1}$ for multiplexing HARQ-ACK
information with priority 1 in a PUSCH transmission with priority 0 are
configured to values according to Table 9.3-1. The first, second and
third values provided by any of *betaOffsetsCrossPri1,
betaOffsetsCrossPri1DCI-0-2, or* *cg-betaOffsetsCrossPri1* respectively
provide indexes $I_{offset,0}^{HARQ - ACK,1}$,
$I_{offset,1}^{HARQ - ACK,1}$, and $I_{offset,2}^{HARQ - ACK,1}$ for the
UE to use if the UE multiplexes up to 2 bits, more than 2 and up to 11
bits, and more than 11 bits of HARQ-ACK information with priority 1 in
the PUSCH transmission with priority 0, respectively.

Part 1 CSI report and Part 2 CSI report offsets
$\beta_{offset}^{CSI - 1}$ and $\beta_{offset}^{CSI - 2}$, respectively,
are configured to values according to Table 9.3-2. The
*betaOffsetCSI-Part1-Index1* and *betaOffsetCSI-Part2-Index1*
respectively provide indexes $I_{offset,0}^{CSI - 1}$ and
$I_{offset,0}^{CSI - 2}$ for the UE to use if the UE multiplexes up to
11 bits for Part 1 CSI reports or Part 2 CSI reports in the PUSCH. The
*betaOffsetCSI-Part1-Index2* and *betaOffsetCSI-Part2-Index2*
respectively provide indexes $I_{offset,1}^{CSI - 1}$ or
$I_{offset,1}^{CSI - 2}$ for the UE to use if the UE multiplexes more
than 11 bits for Part 1 CSI reports or Part 2 CSI reports in the PUSCH.

If a DCI format that includes a beta_offset indicator field with one bit
or two bits, as configured by *UCI-OnPUSCH* for DCI format 0_1/0_3 or
*UCI-OnPUSCH-DCI-0-2* for DCI format 0_2, schedules the PUSCH
transmission from the UE, the UE is provided by each of
{*betaOffsetACK-Index1*, *betaOffsetACK-Index2*,
*betaOffsetACK-Index3*}, the {first, second, third} values provided by
*betaOffsetsCrossPri0*, or *betaOffsetsCrossPri0DCI-0-2,* and the
{first, second, third} values provided by *betaOffsetsCrossPri1*, or
*betaOffsetsCrossPri1DCI-0-2*, a set of two or four
$I_{offset}^{HARQ - ACK},\ I_{offset}^{HARQ - ACK,0},\ and\ I_{offset}^{HARQ - ACK,1}\ $
indexes from Table 9.3-1 for multiplexing HARQ-ACK information in the
PUSCH transmission and by each of {*betaOffsetCSI-Part1-Index1*,
*betaOffsetCSI-Part1-Index2*} a set of two or four
$I_{offset}^{CSI - 1}$ indexes, and by each of
{*betaOffsetCSI-Part2-Index1*, *betaOffsetCSI-Part2-Index2*} a set of
two or four $I_{offset}^{CSI - 2}$ indexes from Table 9.3-2,
respectively, for multiplexing Part 1 CSI reports and Part 2 CSI
reports, respectively, in the PUSCH transmission. The beta_offset
indicator field indicates a $I_{offset}^{HARQ - ACK}$ value and/or a
$I_{offset}^{HARQ - ACK,0}$ value, and/or a $I_{offset}^{HARQ - ACK,1}$
value, a $I_{offset}^{CSI - 1}$ value and a $I_{offset}^{CSI - 2}$ value
from the respective sets of values, with the mapping defined in Table
9.3-3 and in Table 9.3-3A. If the PUSCH transmission has priority 0 or
priority 1, and the UE is provided *uci-MuxWithDiffPrio*, and the UE
multiplexes HARQ-ACK information of priority 1 or priority 0 in the
PUSCH, the UE applies the {first, second, third} values provided by
*betaOffsetsCrossPri1* *= \'dynamic\'* for DCI format 0_1/0_3,
*betaOffsetsCrossPri1DCI-0-2= \'dynamic\'* for DCI format 0_2, or
applies the {first, second, third} values provided by
*betaOffsetsCrossPri0 = \'dynamic\'* for DCI format 0_1/0_3,
*betaOffsetsCrossPri0DCI-0-2= \'dynamic\'* for DCI format 0_2.

For a PUSCH transmission that is configured by a *ConfiguredGrantConfig*
and includes CG-UCI, the UE multiplexes the CG-UCI in the PUSCH
transmission using a $I_{\text{offset}}^{\text{CG-UCI}}$ value provided
by *betaOffsetCG-UCI* with the mapping defined in Table 9.3-1. The
CG-UCI has same priority value as the PUSCH. If the UE is provided
*cg-UCI-Multiplexing* and multiplexes HARQ-ACK information of same
priority value as the CG-UCI in the PUSCH transmission, as described in
clauses 9 and 9.2.5, the UE jointly encodes the HARQ-ACK information and
the CG-UCI \[5, TS 38.212\] and determines a number of resources for
multiplexing the combined information in a PUSCH using
$\beta_{offset}^{HARQ - ACK}$ which provides indexes
$I_{offset,1}^{HARQ - ACK}$ and $I_{offset,2}^{HARQ - ACK}$ for the UE
to use if the UE multiplexes up to 11, and more than 11 combined
information bits, respectively.

For a PUSCH transmission that is configured by a *ConfiguredGrantConfig*
and includes UTO-UCI, the UE multiplexes the UTO-UCI in the PUSCH
transmission using a $I_{\text{offset}}^{\text{UTO-UCI}}$ value provided
by *betaOffsetUTO-UCI* with the mapping defined in Table 9.3-1. The
UTO-UCI has same priority value as the PUSCH. If the UE multiplexes
HARQ-ACK information of same priority value as the UTO-UCI in the PUSCH
transmission, as described in clauses 9 and 9.2.5, the UE jointly
encodes the HARQ-ACK information and the UTO-UCI and determines a number
of resources for multiplexing the combined information in the PUSCH
using $\beta_{offset}^{HARQ - ACK}$ which provides indexes
$I_{offset,1}^{HARQ - ACK}$ and $I_{offset,2}^{HARQ - ACK}$ for the UE
to use if the UE multiplexes up to 11, and more than 11 combined
information bits, respectively.

Table 9.3-1: Mapping of beta_offset values for HARQ-ACK information,
CG-UCI, or UTO-UCI and the index signalled by higher layers

  -----------------------------------------------------------------------------------------------------------------
  $\mathbf{I}_{\text{offset,0}}^{\text{HARQ-ACK}}$ or  $\mathbf{\beta}_{\mathbf{offset}}^{\mathbf{HARQ - ACK}}$ or
  $\mathbf{I}_{\text{offset,1}}^{\text{HARQ-ACK}}$ or  $\mathbf{\beta}_{\mathbf{offset}}^{\mathbf{CG - UCI}}$ or
  $\mathbf{I}_{\text{offset,2}}^{\text{HARQ-ACK}}$ or  $\mathbf{\beta}_{\mathbf{offset}}^{\mathbf{UTO - UCI}}$ or
  $\mathbf{I}_{\text{offset}}^{\text{CG-UCI}}$ or      $\mathbf{\beta}_{\mathbf{offset}}^{\mathbf{HARQ - ACK,0}}$
  $\mathbf{I}_{\text{offset}}^{\text{UTO-UCI}}$ or     or
  $\mathbf{I}_{\text{offset,0}}^{\text{HARQ-ACK,0}}$   $\mathbf{\beta}_{\mathbf{offset}}^{\mathbf{HARQ - ACK,1}}$
  or                                                   
  $\mathbf{I}_{\text{offset,1}}^{\text{HARQ-ACK,0}}$   
  or                                                   
  $\mathbf{I}_{\text{offset,2}}^{\text{HARQ-ACK,0}}$   
  or                                                   
  $\mathbf{I}_{\text{offset,0}}^{\text{HARQ-ACK,1}}$   
  or                                                   
  $\mathbf{I}_{\text{offset,1}}^{\text{HARQ-ACK,1}}$   
  or                                                   
  $\mathbf{I}_{\text{offset,2}}^{\text{HARQ-ACK,1}}$   
  ---------------------------------------------------- ------------------------------------------------------------
  0                                                    1.000

  1                                                    2.000

  2                                                    2.500

  3                                                    3.125

  4                                                    4.000

  5                                                    5.000

  6                                                    6.250

  7                                                    8.000

  8                                                    10.000

  9                                                    12.625

  10                                                   15.875

  11                                                   20.000

  12                                                   31.000

  13                                                   50.000

  14                                                   80.000

  15                                                   126.000

  16                                                   0.6

  17                                                   0.4

  18                                                   0.2

  19                                                   0.1

  20                                                   0.05

  21                                                   Reserved

  22                                                   Reserved

  23                                                   Reserved

  24                                                   Reserved

  25                                                   Reserved

  26                                                   Reserved

  27                                                   Reserved

  28                                                   Reserved

  29                                                   Reserved

  30                                                   Reserved

  31                                                   Reserved
  -----------------------------------------------------------------------------------------------------------------

Table 9.3-2: Mapping of beta_offset values for CSI and the index
signalled by higher layers

+-----------------------------------------------+---------------------------------------------------------+
| $\mathbf{I}_{\text{offset,0}}^{\text{CSI-1}}$ | $$\mathbf{\beta}_{\mathbf{offset}}^{\mathbf{CSI - 1}}$$ |
| or                                            |                                                         |
| $\mathbf{I}_{\text{offset,1}}^{\text{CSI-1}}$ | $$\mathbf{\beta}_{\mathbf{offset}}^{\mathbf{CSI - 2}}$$ |
|                                               |                                                         |
| $\mathbf{I}_{\text{offset,0}}^{\text{CSI-2}}$ |                                                         |
| or                                            |                                                         |
| $\mathbf{I}_{\text{offset,1}}^{\text{CSI-2}}$ |                                                         |
+===============================================+=========================================================+
| 0                                             | 1.125                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 1                                             | 1.250                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 2                                             | 1.375                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 3                                             | 1.625                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 4                                             | 1.750                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 5                                             | 2.000                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 6                                             | 2.250                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 7                                             | 2.500                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 8                                             | 2.875                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 9                                             | 3.125                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 10                                            | 3.500                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 11                                            | 4.000                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 12                                            | 5.000                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 13                                            | 6.250                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 14                                            | 8.000                                                   |
+-----------------------------------------------+---------------------------------------------------------+
| 15                                            | 10.000                                                  |
+-----------------------------------------------+---------------------------------------------------------+
| 16                                            | 12.625                                                  |
+-----------------------------------------------+---------------------------------------------------------+
| 17                                            | 15.875                                                  |
+-----------------------------------------------+---------------------------------------------------------+
| 18                                            | 20.000                                                  |
+-----------------------------------------------+---------------------------------------------------------+
| 19                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+
| 20                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+
| 21                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+
| 22                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+
| 23                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+
| 24                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+
| 25                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+
| 26                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+
| 27                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+
| 28                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+
| 29                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+
| 30                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+
| 31                                            | Reserved                                                |
+-----------------------------------------------+---------------------------------------------------------+

Table 9.3-3: Mapping of four beta_offset indicator values to offset
indexes

+--------------+-------------------------------------------------------+
| beta_offset  | ($\mathbf{I}_{\text{offset,0}}^{\text{HARQ-ACK}}$ or  |
| indicator    | $\mathbf{I}_{\text{offset,1}}^{\text{HARQ-ACK}}$ or   |
|              | $\mathbf{I}_{\text{offset,2}}^{\text{HARQ-ACK}}$),    |
|              |                                                       |
|              | ($\mathbf{I}_{\text{offset,0}}^{\text{HARQ-ACK,0}}$   |
|              | or $\mathbf{I}_{\text{offset,1}}^{\text{HARQ-ACK,0}}$ |
|              | or                                                    |
|              | $\mathbf{I}_{\text{offset,2}}^{\text{HARQ-ACK,0}}$),  |
|              |                                                       |
|              | ($\mathbf{I}_{\text{offset,0}}^{\text{HARQ-ACK,1}}$   |
|              | or $\mathbf{I}_{\text{offset,1}}^{\text{HARQ-ACK,1}}$ |
|              | or                                                    |
|              | $\mathbf{I}_{\text{offset,2}}^{\text{HARQ-ACK,1}}$),  |
|              |                                                       |
|              | ($\mathbf{I}_{\text{offset,0}}^{\text{CSI-1}}$ or     |
|              | $\mathbf{I}_{\text{offset,1}}^{\text{CSI-1}}$),       |
|              | ($\mathbf{I}_{\text{offset,0}}^{\text{CSI-2}}$ or     |
|              | $\mathbf{I}_{\text{offset,1}}^{\text{CSI-2}}$)        |
+--------------+-------------------------------------------------------+
| \'00\'       | 1^st^ offset index provided by higher layers          |
+--------------+-------------------------------------------------------+
| \'01\'       | 2^nd^ offset index provided by higher layers          |
+--------------+-------------------------------------------------------+
| \'10\'       | 3^rd^ offset index provided by higher layers          |
+--------------+-------------------------------------------------------+
| \'11\'       | 4^th^ offset index provided by higher layers          |
+--------------+-------------------------------------------------------+

Table 9.3-3A: Mapping of two beta_offset indicator values to offset
indexes

+:-------------:+:------------------------------------------------------:+
| **beta_offset | **(**$\mathbf{I}_{\text{offset,0}}^{\text{HARQ-ACK}}$  |
| indicator**   | **or**                                                 |
|               | $\mathbf{I}_{\text{offset,1}}^{\text{HARQ-ACK}}$       |
|               | **or**                                                 |
|               | $\mathbf{I}_{\text{offset,2}}^{\text{HARQ-ACK}}$**),** |
|               |                                                        |
|               | ($\mathbf{I}_{\text{offset,0}}^{\text{HARQ-ACK,0}}$ or |
|               | $\mathbf{I}_{\text{offset,1}}^{\text{HARQ-ACK,0}}$ or  |
|               | $\mathbf{I}_{\text{offset,2}}^{\text{HARQ-ACK,0}}$),   |
|               |                                                        |
|               | ($\mathbf{I}_{\text{offset,0}}^{\text{HARQ-ACK,1}}$ or |
|               | $\mathbf{I}_{\text{offset,1}}^{\text{HARQ-ACK,1}}$ or  |
|               | $\mathbf{I}_{\text{offset,2}}^{\text{HARQ-ACK,1}}$),   |
|               |                                                        |
|               | **(**$\mathbf{I}_{\text{offset,0}}^{\text{CSI-1}}$     |
|               | **or**                                                 |
|               | $\mathbf{I}_{\text{offset,1}}^{\text{CSI-1}}$**),      |
|               | (**$\mathbf{I}_{\text{offset,0}}^{\text{CSI-2}}$       |
|               | **or**                                                 |
|               | $\mathbf{I}_{\text{offset,1}}^{\text{CSI-2}}$**)**     |
+---------------+--------------------------------------------------------+
| \'0\'         | 1^st^ offset index provided by higher layers           |
+---------------+--------------------------------------------------------+
| \'1\'         | 2^nd^ offset index provided by higher layers           |
+---------------+--------------------------------------------------------+