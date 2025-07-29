### 16.3.0 UE procedure for transmitting PSFCH with control information

A UE can be indicated by an SCI format scheduling a PSSCH reception to
transmit a PSFCH with HARQ-ACK information in response to the PSSCH
reception. The UE provides HARQ-ACK information that includes ACK or
NACK, or only NACK.

A UE can be provided, by *sl-PSFCH-Period*, a number of slots in a
resource pool for a period of PSFCH transmission occasion resources. If
the number is zero, PSFCH transmissions from the UE in the resource pool
are disabled.

A UE can be enabled, by *sl-InterUE-CoordinationScheme2*, to transmit a
PSFCH with conflict information in a resource pool. The UE can
determine, based on an indication by a SCI format 1-A, a set of
resources that includes one or more slots and resource blocks that are
reserved for PSSCH transmission. If the UE determines a conflict for a
reserved resource for PSSCH transmission, the UE provides conflict
information in a PSFCH.

A UE expects that a slot ${t'}_{k}^{SL}$ $(0 \leq k < {T'}_{\max}$) has
a PSFCH transmission occasion resource if
$k\ mod\ N_{\text{PSSCH}}^{\text{PSFCH}} = 0$, where ${t'}_{k}^{SL}$ is
defined in \[6, TS 38.214\], ${T'}_{\max}$ is a number of slots that
belong to the resource pool within 10240 msec according to \[6, TS
38.214\], and $N_{\text{PSSCH}}^{\text{PSFCH}}$ is provided by
*sl-PSFCH-Period*.

A UE may be indicated by higher layers to not transmit a PSFCH that
includes HARQ-ACK information in response to a PSSCH reception \[11, TS
38.321\].

If a UE receives a PSSCH in a resource pool and the HARQ feedback
enabled/disabled indicator field in an associated SCI format 2-A/2-B/2-C
has value 1 \[5, TS 38.212\], the UE provides the HARQ-ACK information
in a PSFCH transmission in the resource pool. For operation without
shared spectrum channel access, the UE transmits the PSFCH in a first
slot that includes PSFCH resources and is at least a number of slots,
provided by *sl-MinTimeGapPSFCH*, of the resource pool after a last slot
of the PSSCH reception. For operation with shared spectrum channel
access, the UE can attempt to transmit the PSFCH over a number of first
$N_{occasion}^{PSFCH}$ slots, provided by *sl-NumPSFCH-Occasions* and
indexed from 1 to $N_{occasion}^{PSFCH}$ in ascending order in time,
that include PSFCH resources and are at least a number of slots,
provided by *sl-MinTimeGapPSFCH*, of the resource pool after a last slot
of the PSSCH reception. The UE attempts to transmit PSFCH in a slot only
when the UE fails to transmit PSFCH associated with the PSSCH in all
previous slots for PSFCH within the $N_{occasion}^{PSFCH}$ slots.

For operation without shared spectrum channel access, a UE is provided
by *sl-PSFCH-RB-Set* a set of $M_{\text{PRB, }set}^{\text{PSFCH}}$ PRBs
in a resource pool for PSFCH transmission with HARQ-ACK information in a
PRB of the resource pool. A UE can be provided by *sl-RB-SetPSFCH* a set
of $M_{\text{PRB, }set}^{\text{PSFCH}}$ PRBs in a resource pool for
PSFCH transmission with conflict information in a PRB of the resource
pool. A UE expects that different PRBs are (pre)configured for conflict
information and HARQ-ACK information. For a number of $N_{\text{subch}}$
sub-channels for the resource pool, provided by *sl-NumSubchannel*, and
a number of PSSCH slots associated with a PSFCH slot that is less than
or equal to $N_{\text{PSSCH}}^{\text{PSFCH}}$, the UE allocates the
$\left\lbrack \left( i + j \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right) \cdot M_{\text{subch, }slot}^{\text{PSFCH}},\ \left( i + 1 + j \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right) \cdot M_{\text{subch, }slot}^{\text{PSFCH}} - 1 \right\rbrack$
PRBs from the $M_{\text{PRB, }set}^{\text{PSFCH}}$ PRBs to slot $i$
among the PSSCH slots associated with the PSFCH slot and sub-channel
$j$, where
$M_{\text{subch, }slot}^{\text{PSFCH}} = \frac{M_{\text{PRB, }set}^{\text{PSFCH}}}{\left( N_{\text{subch}} \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right)}$,
$0 \leq i < N_{\text{PSSCH}}^{\text{PSFCH}}$,
$0 \leq j < N_{\text{subch}}$, and the allocation starts in an ascending
order of $i$ and continues in an ascending order of $j$. The UE expects
that $M_{\text{PRB, }set}^{\text{PSFCH}}$ is a multiple of
$N_{\text{subch}} \bullet N_{\text{PSSCH}}^{\text{PSFCH}}$*.*

For operation with shared spectrum channel access, when
*sl-TransmissionStructureForPSFCH* is not provided and within RB-set
$k$, for the $n$-th candidate PSFCH transmission occasion,
$1 \leq n \leq N_{occasion}^{PSFCH}$, a UE determines a set of
$M_{\text{PRB, }set,\ \ k}^{\text{PSFCH,n}}$ PRBs in a resource pool
based on the $n$-th indication provided by *sl-PSFCH-RB-SetList* or
*sl-IUC-RB-SetList* for PSFCH transmission with HARQ-ACK information or
conflict information, respectively. The UE expects that different PRBs
are (pre)configured for conflict information and HARQ-ACK information.
For a number of $N_{\text{subch}}^{k}$ sub-channels where all PRBs of
each sub-channel are located in RB-set $k$ and a number of PSSCH slots
associated with a PSFCH slot that is less than or equal to
$N_{\text{PSSCH}}^{\text{PSFCH}}$, the UE allocates the
$\left\lbrack \left( i + j \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right) \cdot M_{\text{subch, }slot,k}^{\text{PSFCH,n}},\ \left( i + 1 + j \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right) \cdot M_{\text{subch, }slot,k}^{\text{PSFCH,n}} - 1 \right\rbrack$
PRBs from the $M_{\text{PRB, }set,\ \ k}^{\text{PSFCH,n}}$ PRBs to slot
$i$ among the PSSCH slots associated with the PSFCH slot and sub-channel
$j$, where
$M_{\text{subch, }slot,k}^{\text{PSFCH,n}} = \frac{M_{\text{PRB, }set,k}^{\text{PSFCH,n}}}{\left( N_{\text{subch}}^{k} \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right)}$,
$0 \leq i < N_{\text{PSSCH}}^{\text{PSFCH}}$,
$0 \leq j < N_{\text{subch}}^{k}$, and the allocation starts in an
ascending order of $i$ and continues in an ascending order of $j$. The
UE expects that $M_{\text{PRB, }set,\ \ k}^{\text{PSFCH,n}}$ is a
multiple of
$N_{\text{subch}}^{k} \bullet N_{\text{PSSCH}}^{\text{PSFCH}}$*.*

For operation with shared spectrum channel access, when
*sl-TransmissionStructureForPSFCH =* \' dedicatedInterlace \' and within
RB-set $k$, a UE determines, based on *sl-PSFCH-RB-SetList*, all PRBs of
an interlace for one PSFCH transmission with HARQ-ACK information in the
resource pool. Within RB-set $k$, the UE determines, based on
*sl-IUC-RB-SetList*, all PRBs of an interlace for one PSFCH transmission
with conflict information in the resource pool. For the $n$-th candidate
PSFCH transmission occasion, $1 \leq n \leq N_{occasion}^{PSFCH}$, the
UE determines a set of interlaces that includes a number
$M_{\text{interlace,k}}^{\text{PSFCH,n}}$ of interlaces based on the
$n$-th indication provided by *sl-PSFCH-RB-SetList* or
*sl-IUC-RB-SetList* for HARQ-ACK information or conflict information,
respectively. The UE expects that different interlaces are determined
for conflict information and HARQ-ACK information. The set of interlaces
are indexed in an ascending order of interlace indexes. For each
interlace of the set of interlaces, all PRBs in the interlace are
available for PSFCH transmission*.* For a number of
$N_{\text{subch}}^{k}$ sub-channels in RB-set $k$ and a number of PSSCH
slots that is not larger than $N_{\text{PSSCH}}^{\text{PSFCH}}$ and is
associated with a slot for PSFCH transmission, the UE allocates the
$\left\lbrack \left( i + j \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right) \cdot M_{\text{subch, }slot,k}^{\text{PSFCH,n}},\ \left( i + 1 + j \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right) \cdot M_{\text{subch, }slot,k}^{\text{PSFCH,n}} - 1 \right\rbrack$
interlaces from the $M_{\text{interlace,k}}^{\text{PSFCH,n}}$ interlaces
to slot $i$ and sub-channel $j$, where
$M_{\text{subch, }slot,k}^{\text{PSFCH,n}} = \frac{M_{\text{interlace,k}}^{\text{PSFCH,n}}}{\left( N_{\text{subch}}^{k} \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right)}$,
$0 \leq i < N_{\text{PSSCH}}^{\text{PSFCH}}$,
$0 \leq j < N_{\text{subch}}^{k}$. The allocation starts in an ascending
order of $i$ and continues in an ascending order of $j$. The UE expects
that $M_{\text{interlace,k}}^{\text{PSFCH,n}}$ is a multiple of
$N_{\text{subch}}^{k} \bullet N_{\text{PSSCH}}^{\text{PSFCH}}$*.*

For operation with shared spectrum channel access, when
*sl-TransmissionStructureForPSFCH =* \' commonInterlace\' and within
RB-set $k$, a UE determines a subset of PRBs in a first interlace and,
based on *sl-PSFCH-RB-SetList*, a subset of $N_{PRB}^{PSFCH}$ PRBs in a
second interlace for a PSFCH transmission with HARQ-ACK information in a
resource pool, or based on *sl-IUC-RB-SetList*, a subset of
$N_{PRB}^{PSFCH}$ PRBs in a second interlace for a PSFCH transmission
with conflict information in a resource pool. An index of the first
interlace is provided by *sl-PSFCH-CommonInterlaceIndex*. The
$N_{PRB}^{PSFCH}$ PRBs in the second interlace are provided by
*sl-NumDedicatedPRBs-ForPSFCH* where, for the $n$-th candidate PSFCH
transmission occasion, $1 \leq n \leq N_{occasion}^{PSFCH}$, and for
each interlace $l$, the UE determines
$M_{\text{PRB,k, l}}^{\text{PSFCH,n}}$ PRBs based on the $n$-th
indication provided by *sl-PSFCH-RB-SetList* or *sl-IUC-RB-SetList* for
HARQ-ACK information or conflict information, respectively. The UE
expects that different subsets of $N_{PRB}^{PSFCH}$ PRBs are determined
for conflict information and HARQ-ACK information. The UE expects that
$M_{\text{PRB,k,l}}^{\text{PSFCH,n}}$ is a multiple of
$N_{PRB}^{PSFCH}$. For interlace $l$, the UE determines a PRB subset
with index $s$ to include PRBs
$\left\{ N_{PRB}^{PSFCH} \cdot s,\ N_{PRB}^{PSFCH} \cdot s + 1,\ \ldots,\ N_{PRB}^{PSFCH} \cdot (s + 1) - 1 \right\}$,
$0 \leq s \leq M_{\text{PRB,k,l}}^{\text{PSFCH,n}}/N_{PRB}^{PSFCH} - 1$.
The UE determines the $M_{\text{subset,k}}^{\text{PSFCH,n}}$ PRB subsets
by ordering the PRB subsets first in an ascending order of PRB subset
index within an interlace and second in ascending order of interlace
index, where
$M_{\text{subset,k}}^{\text{PSFCH,n}} = \sum_{l}^{}{M_{\text{PRB,k,l}}^{\text{PSFCH,n}}/N_{PRB}^{PSFCH}}$.
For a number of $N_{\text{subch}}^{k}$ sub-channels in RB-set $k$ and a
number of slots for PSSCH transmissions that is not larger than
$N_{\text{PSSCH}}^{\text{PSFCH}}$ and is associated with a slot for
PSFCH transmission, the UE allocates the
$\left\{ \left( i + j \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right) \cdot M_{\text{subch, }slot,k}^{\text{PSFCH,n}},\ \left( i + j \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right) \cdot M_{\text{subch, }slot,k}^{\text{PSFCH,n}} + 1,\ \ldots,\ \left( i + 1 + j \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right) \cdot M_{\text{subch, }slot,k}^{\text{PSFCH,n}} - 1 \right\}$
PRB subsets from the $M_{\text{subset,k}}^{\text{PSFCH,n}}$ PRB subsets
to slot $i$ among the slots for PSSCH transmissions that are associated
with the slot and sub-channel $j$ for PSFCH transmissions, where
$M_{\text{subch, }slot,k}^{\text{PSFCH,n}} = \frac{M_{\text{subset,k}}^{\text{PSFCH,n}}}{\left( N_{\text{subch}}^{k} \cdot N_{\text{PSSCH}}^{\text{PSFCH}} \right)}$
and $0 \leq i < N_{\text{PSSCH}}^{\text{PSFCH}}$,
$0 \leq j < N_{\text{subch}}^{k}$. The allocation starts in an ascending
order of $i$ and continues in an ascending order of $j$. The UE expects
that $M_{\text{subset,k}}^{\text{PSFCH,n}}$ is a multiple of
$N_{\text{subch}}^{k} \bullet N_{\text{PSSCH}}^{\text{PSFCH}}$*.*

The second OFDM symbol $l'$ of PSFCH transmission in a slot is defined
as $l' = slStartingSymbolFirst + slLengthSymbols - 2$ when
*sl-StartingSymbolFirst* and *sl-StartingSymbolSecond* are provided for
a SL-BWP, or $l' = slStartSymbol + slLengthSymbols - 2$ otherwise.

For operation without shared spectrum channel access, a UE determines a
number of PSFCH resources available for multiplexing HARQ-ACK or
conflict information in a PSFCH transmission as
$R_{\text{PRB, }CS}^{\text{PSFCH}} = {N_{\text{type }}^{\text{PSFCH}} \cdot M}_{\text{subch, }slot}^{\text{PSFCH}} \cdot N_{\text{CS}}^{\text{PSFCH}}$
where $N_{\text{CS}}^{\text{PSFCH}}$ is a number of cyclic shift pairs
for the resource pool provided by *sl-NumMuxCS-Pair* and, based on an
indication by *sl-PSFCH-CandidateResourceType*,

\- if *sl-PSFCH-CandidateResourceType* is configured as *startSubCH*,
$N_{\text{type }}^{\text{PSFCH}} = 1$ and the
$M_{\text{subch, }slot}^{\text{PSFCH}}$ PRBs are associated with the
starting sub-channel of the corresponding PSSCH

\- if *sl-PSFCH-CandidateResourceType* is configured as *allocSubCH*,
$N_{\text{type }}^{\text{PSFCH}} = N_{\text{subch }}^{\text{PSSCH}}$ and
the
${N_{\text{subch }}^{\text{PSSCH}} \cdot M}_{\text{subch, }slot}^{\text{PSFCH}}$
PRBs are associated with the $N_{\text{subch }}^{\text{PSSCH}}$
sub-channels of the corresponding PSSCH

\- for conflict information, the corresponding PSSCH is determined based
on *sl-PSFCH-Occasion*

The PSFCH resources are first indexed according to an ascending order of
the PRB index, from the
${N_{\text{type }}^{\text{PSFCH}} \cdot M}_{\text{subch, }slot}^{\text{PSFCH}}$
PRBs, and then according to an ascending order of the cyclic shift pair
index from the $N_{\text{CS}}^{\text{PSFCH}}$ cyclic shift pairs.

For operation with shared spectrum channel access and for the $n$-th
candidate PSFCH transmission occasion, a UE determines a number of PSFCH
resources available for multiplexing HARQ-ACK or conflict information in
a PSFCH transmission as
$R_{\text{PRB, }CS}^{\text{PSFCH}} = N_{\text{type }}^{\text{PSFCH}} \cdot M \cdot N_{\text{CS}}^{\text{PSFCH}}$
where $N_{\text{CS}}^{\text{PSFCH}}$ is a number of cyclic shift pairs
for the resource pool provided by *sl-NumMuxCS-Pair* and, based on an
indication by *sl-PSFCH-CandidateResourceType*

\- if *sl-PSFCH-CandidateResourceType* is indicated as *startSubCH*,
$N_{\text{type }}^{\text{PSFCH}} = 1$,
$M = M_{\text{subch, }slot,k}^{\text{PSFCH,n}}$, and when
*sl-TransmissionStructureForPSFCH* is provided, the
$N_{\text{type }}^{\text{PSFCH}} \cdot M$ interlaces or PRB subsets are
associated with the lowest sub-channel index within the RB-set with
smallest index of the corresponding PSSCH, or when
*sl-TransmissionStructureForPSFCH* is not provided, the
$N_{type\ }^{PSFCH} \cdot M$ PRBs are associated with the starting
sub-channel of the corresponding PSSCH

\- if *sl-PSFCH-CandidateResourceType* is indicated as *allocSubCH*,
when *sl-TransmissionStructureForPSFCH* is provided,
$N_{\text{type }}^{\text{PSFCH}} = N_{\text{subch }}^{\text{PSSCH}}$ and
$M = \sum_{k}^{}M_{\text{subch, }slot,k}^{\text{PSFCH,n}}$ where the sum
is over all RB-sets including resources for the corresponding PSSCH, and
the $N_{\text{type }}^{\text{PSFCH}} \cdot M$ combinations of interlaces
and RB-sets or PRB subsets are associated with the
$N_{\text{subch }}^{\text{PSSCH}}$ sub-channels of the corresponding
PSSCH, or when *sl-TransmissionStructureForPSFCH* is not provided,
$N_{type\ }^{PSFCH} \cdot M = \sum_{k}^{}{(N_{subch,\text{k }}^{PSSCH} \cdot M_{subch,\ slot,k}^{PSFCH,n})}$
PRBs where the sum is over all RB-sets including resources for the
corresponding PSSCH, and the $N_{type\ }^{PSFCH} \cdot M$ PRBs are
associated with $\sum_{k}^{}{(N_{subch,k\ }^{PSSCH})}$ sub-channels of
the corresponding PSSCH where the $N_{subch,k\ }^{PSSCH}$ is a number of
sub-channels of the corresponding PSSCH in RB-set $k$

\- for conflict information, the corresponding PSSCH is determined based
on *sl-PSFCH-Occasion*

When *sl-TransmissionStructureForPSFCH* is provided, the PSFCH resources
are first indexed according to an ascending order of the interlace or
PRB subset index, second according to an ascending order of the RB-set
index, and then according to an ascending order of the cyclic shift pair
index from the $N_{\text{CS}}^{\text{PSFCH}}$ cyclic shift pairs. When
*sl-TransmissionStructureForPSFCH* is not provided, the PSFCH resources
are first indexed according to an ascending order of the PRB index, from
the $N_{\text{type }}^{\text{PSFCH}} \cdot M$ PRBs, and then according
to an ascending order of the cyclic shift pair index from the
$N_{\text{CS}}^{\text{PSFCH}}$ cyclic shift pairs. The UE applies CP
extension to the first symbol of a PSFCH and within the first symbol
before the first symbol of the PSFCH according to an index \[4, TS
38.211\] provided by *sl-CPE-StartingPositionPSFCH*.

A UE determines an index of a PSFCH resource for a PSFCH transmission
with HARQ-ACK information in response to a PSSCH reception or with
conflict information corresponding to a reserved resource as
$\left( P_{\text{ID}} + M_{ID} \right)modR_{\text{PRB, }CS}^{\text{PSFCH}}$
where $P_{\text{ID}}$ is a physical layer source ID provided by SCI
format 2-A/2-B/2-C \[5, TS 38.212\] scheduling the PSSCH reception, or
by SCI format 2-A/2-B/2-C with corresponding SCI format 1-A reserving
the resource from another UE to be provided with the conflict
information. For HARQ-ACK information, $M_{\text{ID}}$ is the identity
of the UE receiving the PSSCH as indicated by higher layers if the UE
detects a SCI format 2-A with Cast type indicator field value of \"01\";
otherwise, $M_{\text{ID}}$ is zero. For conflict information,
$M_{\text{ID}}$ is zero.

For operation with shared spectrum channel access, when
*sl-TransmissionStructureForPSFCH = \'*commonInterlace*\'*, a PRB
$s_{1}$ in the first interlace is excluded from the resources for a
PSFCH transmission, if ${|s}_{1} - s_{2}| \leq 5$ for $\mu = 0$ or
${|s}_{1} - s_{2}| \leq 2$ for $\mu = 1$ for any PRB $s_{2}$ in the PRB
subset when the PRB subset is selected for PSFCH transmission, and
$\left( s_{high} - s_{low} \right) \geq 88$ for $\mu = 0$ or
$\left( s_{high} - s_{low} \right) \geq 44$ for $\mu = 1$, where PRB
$s_{high}$ and PRB $s_{low}$ are the largest and smallest PRB indexes,
respectively, in the resources for the PSFCH transmission assuming PRB
$s_{1}$ is excluded.

For a PSFCH transmission with HARQ-ACK information or conflict
information, a UE determines a $m_{\text{0}}$ value, for computing a
value of cyclic shift $\alpha$ \[4, TS 38.211\], from a cyclic shift
pair index corresponding to a PSFCH resource index and from
$N_{\text{CS}}^{\text{PSFCH}}$ using Table 16.3-1.

Table 16.3-1: Set of cyclic shift pairs

+-------------------------------------------+-----------------------------------------------------------------------------+
| $$\mathbf{N}_{\text{CS}}^{\text{PSFCH}}$$ | $$\mathbf{m}_{\text{0}}$$                                                   |
|                                           +------------+------------+------------+------------+------------+------------+
|                                           | **Cyclic   | **Cyclic   | **Cyclic   | **Cyclic   | **Cyclic   | **Cyclic   |
|                                           | Shift Pair | Shift Pair | Shift Pair | Shift Pair | Shift Pair | Shift Pair |
|                                           | Index 0**  | Index 1**  | Index 2**  | Index 3**  | Index 4**  | Index 5**  |
+:=========================================:+:==========:+:==========:+:==========:+:==========:+:==========:+:==========:+
| 1                                         | 0          | \-         | \-         | \-         | \-         | \-         |
+-------------------------------------------+------------+------------+------------+------------+------------+------------+
| 2                                         | 0          | 3          | \-         | \-         | \-         | \-         |
+-------------------------------------------+------------+------------+------------+------------+------------+------------+
| 3                                         | 0          | 2          | 4          | \-         | \-         | \-         |
+-------------------------------------------+------------+------------+------------+------------+------------+------------+
| 6                                         | 0          | 1          | 2          | 3          | 4          | 5          |
+-------------------------------------------+------------+------------+------------+------------+------------+------------+

For a PSFCH transmission with HARQ-ACK information, a UE determines a
$m_{\text{cs}}$ value, for computing a value of cyclic shift $\alpha$
\[4, TS 38.211\], as in Table 16.3-2 if the UE detects a SCI format 2-A
with Cast type indicator field value of \"01\" or \"10\" or a SCI format
2-C, or as in Table 16.3-3 if the UE detects a SCI format 2-B or a SCI
format 2-A with Cast type indicator field value of \"11\". For a PSFCH
transmission with conflict information, a UE determines a
$m_{\text{cs}}$ value for computing a value of cyclic shift $\alpha$
\[4, TS 38.211\] as in Table 16.3-4. The UE applies one cyclic shift
from a cyclic shift pair to a sequence used for the PSFCH transmission
\[4, TS 38.211\].

Table 16.3-2: Mapping of HARQ-ACK information bit values to a cyclic
shift, from a cyclic shift pair, of a sequence for a PSFCH transmission
when HARQ-ACK information includes ACK or NACK

  ---------------------------- ------------------- ----------------------
  HARQ-ACK Value               0 (NACK)            1 (ACK)

  **Sequence cyclic shift**    0                   6
  ---------------------------- ------------------- ----------------------

Table 16.3-3: Mapping of HARQ-ACK information bit values to a cyclic
shift, from a cyclic shift pair, of a sequence for a PSFCH transmission
when HARQ-ACK information includes only NACK

  ---------------------------- ------------------- ----------------------
  HARQ-ACK Value               0 (NACK)            1 (ACK)

  **Sequence cyclic shift**    0                   N/A
  ---------------------------- ------------------- ----------------------

Table 16.3-4: Mapping of conflict information bit values to a cyclic
shift, from a cyclic shift pair, of a sequence for a PSFCH transmission

  --------------------- -------------------------------------------------
  Conflict information  Conflict information for a next in time reserved
                        resource indicated in SCI

  **Sequence cyclic     0
  shift**               
  --------------------- -------------------------------------------------

A first UE determines a second UE for providing the conflict information
to in a PSFCH as follows

\- if the first UE is an intended receiver of the second UE for a
reserved resource of a PSSCH transmission in a slot,

\- does not expect to perform reception on the sidelink due to
half-duplex operation in the slot,

\- the PSFCH occasion for resource conflict information of the second UE
is not passed,

\- the conflict information receiver flag in SCI format 1-A from the
second UE is set to 1, if *sl-IndicationUE-B* = \'enabled\', and

\- determines to transmit to the second UE the PSFCH with the conflict
information.

A first UE determines a UE for providing the conflict information to in
a PSFCH as follows

\- if, for a resource pool, *sl-TypeUE-A* is not provided, the first UE
has been indicated a first reserved resource and a second reserved
resource as resources for PSSCH reception or, if for a resource pool
*sl-TypeUE-A* is provided, has been indicated at least the first
reserved resource or the second reserved resource for PSSCH reception,

\- detects a first SCI format 1-A that includes a first priority value,
$p_{1}$, and the first reserved resource for PSSCH transmission from a
second UE,

\- detects a second SCI format 1-A that includes a second priority
value, $p_{2} < p_{1}$, and the second reserved resource for PSSCH
transmission from a third UE, and

\- determines that the first and second resources overlap in time and
frequency

\- the PSFCH occasions for resource conflict information of the second
UE and the third UE are not passed

\- the conflict information receiver flag in SCI Format 1-A from the
second UE and the third UE is set to 1, if *sl-IndicationUE-B* =
\'enabled\'

\- determines the first SCI format 1-A and the second SCI format 1-A are
not received later than *sl-MinTimeGapPSFCH* before the PSFCH occasion
for conflict information

\- determines to transmit to the second UE the PSFCH with the conflict
information

\- determines to transmit to either the second UE or the third UE the
PSFCH with the conflict information, if $p_{2} = p_{1}$

The first UE can be provided conditions by *sl-OptionForCondition2-A-1*
to determine conflict of reserved resources in a resource pool

\- if *sl-OptionForCondition2-A-1* = \'0\', the first UE can be provided
by, *sl-Thres-RSRP-List* $Th\left( p_{i},p_{j} \right)$, a list of RSRP
thresholds for each priority combination $\left( p_{i},p_{j} \right)$
\[6, TS 38.214\]

\- if the first UE is an intended receiver for PSSCH in a reserved
resource of the second UE, the first UE determines a resource conflict
if the RSRP \[6, TS 38.214\] of the third UE is above a
threshold$\ Th\left( p_{2},p_{1} \right)$

\- if the first UE is an intended receiver for PSSCH in a reserved
resource of the third UE, the first UE determines a resource conflict if
the RSRP of the second UE is above a
threshold$\ Th\left( p_{1},p_{2} \right)$

\- if *sl-OptionForCondition2-A-1* = \'1\', the first UE can be provided
a value $deltaRSRPThresh$ by *sl-DeltaRSRP-Thresh*

\- if the first UE is an intended receiver for PSSCH in a reserved
resource of the second UE, the first UE determines a resource conflict
if $RSRP_{2} > RSRP_{1} + deltaRSRPThresh$, where $RSRP_{1}$ and
$RSRP_{2}$ are the RSRP measurements from the first UE for the second UE
and the third UE, respectively

\- if the first UE is an intended receiver for PSSCH in a reserved
resource of the third UE, the first UE determines a resource conflict if
$RSRP_{1} > RSRP_{2} + deltaRSRPThresh$

If a UE transmits a PSFCH with conflict information corresponding to a
reserved resource indicated in an SCI format 1-A, the UE transmits the
PSFCH in the resource pool in a slot determined based on
*sl-PSFCH-Occasion*

\- If *sl-PSFCH-Occasion* = \'0\',

\- for operation without shared spectrum channel access, the UE
transmits the PSFCH in a first slot that includes PSFCH resources and is
at least a number of slots, provided by *sl-MinTimeGapPSFCH*, of the
resource pool after a slot of a PSCCH reception that provides the SCI
format 1-A. The PSFCH resource is in a slot that is at least $T_{3}$
slots \[6, TS 38.214\] before the resource associated with the conflict
information; otherwise, the UE does not transmit the PSFCH with conflict
information.

\- for operation with shared spectrum channel access, the UE can attempt
to transmit the PSFCH over a number of first $N_{occasion}^{PSFCH}$
slots, provided by *sl-NumPSFCH-Occasions* and indexed from 1 to
$N_{occasion}^{PSFCH}$ in ascending order in time, that include PSFCH
resources and are at least a number of slots, provided by
*sl-MinTimeGapPSFCH*, of the resource pool after a last slot of a PSCCH
reception that provides the SCI format 1-A. If the PSFCH resource is in
a slot within the $N_{occasion}^{PSFCH}$ slots that is at least $T_{3}$
slots before the resource associated with conflict information, the UE
can attempt to transmit the PSFCH with conflict information in the slot;
otherwise, the UE does not transmit the PSFCH with conflict information
in the slot.

\- If *sl-PSFCH-Occasion* = \'1\',

\- for operation without shared spectrum channel access, the UE
transmits the PSFCH in a latest slot that includes PSFCH resources and
is at least $T_{3}$ slots of the resource pool before a slot of the
resource associated with conflict information. The PSFCH resource is in
a slot that is at least *sl-MinTimeGapPSFCH* slots after a slot of a
PSCCH reception that provides the SCI format 1-A; otherwise, the UE does
not transmit the PSFCH with conflict information.

\- for operation with shared spectrum channel access, the UE can attempt
to transmit the PSFCH over a latest number of $N_{occasion}^{PSFCH}$
slots, provided by *sl-NumPSFCH-Occasions* and indexed from 1 to
$N_{occasion}^{PSFCH}$ in ascending order in time, that include PSFCH
resources and are at least $T_{3}$ slots of the resource pool before a
slot of the resource associated with conflict information. If the PSFCH
resource is in a slot that is at least *sl-MinTimeGapPSFCH* slots after
a slot of a PSCCH reception that provides the SCI format 1-A, the UE can
attempt to transmit the PSFCH with conflict information in the slot;
otherwise, the UE does not transmit the PSFCH with conflict information
in the slot.