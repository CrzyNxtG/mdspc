### 5.3.2 OFDM baseband signal generation for PRACH

The time-continuous signal ![](media/image100.wmf) on antenna port $p$
for PRACH is defined by

$${s_{l}^{(p,\mu)}(t) = \sum_{k = 0}^{L_{\text{RA}} - 1}a_{k}^{(p,\text{RA})}e^{j2\pi\left( k + Kk_{1} + \overline{k} \right)\Delta f_{\text{RA}}\left( t - N_{\text{CP},l}^{\text{RA}}T_{\text{c}} - t_{\text{start}}^{\text{RA}} \right)}
}{K = \frac{\Delta f}{\Delta f_{\text{RA}}}
}{k_{1} = k_{0}^{\mu} + \left( N_{\text{BWP},i}^{\text{start}} - N_{\text{grid}}^{\text{start,}\mu} \right)N_{\text{sc}}^{\text{RB}} - N_{\text{grid}}^{\text{size,}\mu}\frac{N_{\text{sc}}^{\text{RB}}}{2} + n_{\text{RA}}^{\text{start}}N_{\text{sc}}^{\text{RB}} + \left\{ \begin{matrix}
n_{\text{RA}}N_{\text{RB}}^{\text{RA}}N_{\text{sc}}^{\text{RB}} & \text{if }L_{\text{RA}} \in \left\{ 139,\ 839 \right\} \\
n_{\text{RA}}N_{\text{RB}}^{\text{RA}}N_{\text{sc}}^{\text{RB}} & \text{if}\text{ }L_{\text{RA}} \in \left\{ 571,\ 1151 \right\}\ \text{in FR2-2} \\
\left( N_{{\text{RB,UL},n}_{0} + n_{\text{RA}}}^{\text{start},\mu} - N_{{\text{RB,UL},n}_{0}}^{\text{start},\mu} \right)N_{sc}^{RB} & \text{if }L_{\text{RA}} \in \left\{ 571,\ 1151 \right\}\text{ }\text{in FR1}
\end{matrix} \right.\ 
}{k_{0}^{\mu} = \left( N_{\text{grid}}^{\text{start,}\mu} + \frac{N_{\text{grid}}^{\text{size,}\mu}}{2} \right)N_{\text{sc}}^{\text{RB}} - \left( N_{\text{grid}}^{\text{start,}\mu_{0}} + \frac{N_{\text{grid}}^{\text{size,}\mu_{0}}}{2} \right)N_{\text{sc}}^{\text{RB}}2^{\mu_{0} - \mu}}$$

where ![](media/image101.wmf) and

\- ![](media/image102.wmf) is given by clause 6.3.3;

\- $\Delta f$ is the subcarrier spacing of the initial uplink bandwidth
part during initial access. If the PRACH transmission is for a candidate
cell $\Delta f$ is provided by *ltm-PRACH-SubcarrierSpacing* in
*EarlyUL-SyncConfig*. Otherwise, ![](media/image98.wmf) is the
subcarrier spacing of the active uplink bandwidth part;

\- $\mu_{0}$ is the largest $\mu$ value among the subcarrier spacing
configurations by the higher-layer parameter *scs-SpecificCarrierList*;

\- $N_{BWP,i}^{start}$ is the lowest numbered resource block of the
initial uplink bandwidth part and is derived by the higher-layer
parameter *initialUplinkBWP* or *initialUplinkBWP-RedCap* during initial
access and from the higher-layer parameters *bwp-GenericParameters* in
*EarlyUL-SyncConfig* if the PRACH transmission is for a candidate cell.
Otherwise, $N_{BWP,i}^{start}$ is the lowest numbered resource block of
the active uplink bandwidth part and is derived by the higher-layer
parameter *BWP-Uplink*;

\- $n_{\text{RA}}^{\text{start}}$ is the frequency offset of the lowest
PRACH transmission occasion in frequency domain with respect to physical
resource block 0 of the active uplink bandwidth part. The quantity
$n_{\text{RA}}^{\text{start}}$ is given by the higher-layer parameter
*msgA-RO-FrequencyStart* if configured and a type-2 random-access
procedure is initiated as described in clause 8.1 of \[5, TS 38.213\],
otherwise by *msg1-FrequencyStart* as described in clause 8.1 of \[5 TS
38.213\];

\- ![](media/image103.wmf){width="0.2604166666666667in"
height="0.20833333333333334in"} is the PRACH transmission occasion index
in frequency domain for a given PRACH transmission occasion in one time
instance as given by clause 6.3.3.2;

\- ![](media/image104.wmf){width="0.3125in"
height="0.23958333333333334in"} is the number of resource blocks
occupied and is given by the parameter allocation expressed in number of
RBs for PUSCH in Table 6.3.3.2-1.

\- $N_{\text{RB,UL},n}^{\text{start},\mu}$ is the start CRB index of
uplink RB set $n$ corresponding to the quantity
${RB}_{n,UL}^{start,\mu}$. The UE assumes that the RB set is defined as
when the UE is not provided *IntraCellGuardBandsPerSCS* for an UL
carrier as described in Clause 7 of \[6, TS 38.214\]

\- $n_{0}$ is the index of the RB set which contains the lowest PRACH
transmission occasion in frequency domain indicated by
$n_{\text{RA}}^{\text{start}}$. The UE may assume that
$n_{\text{RA}}^{\text{start}}$ is configured such that each PRACH
transmission occasion is fully contained within an RB set.

\- ![](media/image105.wmf) and ![](media/image106.wmf) are given by
clause 6.3.3

\-
$N_{\text{CP},l}^{\text{RA}} = N_{\text{CP}}^{\text{RA}} + n \bullet 16\kappa$
where

\- for ![](media/image107.wmf), $n = 0$

\- for
$\Delta f_{\text{RA}} \in \left\{ 15,30,60,120,480,960 \right\}$kHz, $n$
is the number of times the interval
$\left\lbrack t_{\text{start}}^{\text{RA}},\left. \ t_{\text{start}}^{\text{RA}} + \left( N_{\text{u}}^{\text{RA}} + N_{\text{CP}}^{\text{RA}} \right)T_{\text{c}} \right) \right.\ $
overlaps with either time instance 0 or time instance
![](media/image108.wmf) in a subframe

The starting position $t_{\text{start}}^{\text{RA}}$ of the PRACH
preamble in a subframe (for ![](media/image109.wmf)) or in a 60 kHz slot
(for $\Delta f_{\text{RA}} \in \left\{ 60,120,480,960 \right\}$kHz) is
given by

![](media/image110.wmf)

where

\- the subframe or 60 kHz slot is assumed to start at $t = 0$;

\- a timing advance value $N_{\text{TA}} = 0$ shall be assumed;

\- $N_{\text{u}}^{\mu}$ and $N_{\text{CP,}l - 1}^{\mu}$ are given by
clause 5.3.1;

\- ![](media/image111.wmf){width="0.375in"
height="0.19791666666666666in"} shall be assumed for
$\mathrm{\Delta}f_{\text{RA}} \in \left\{ 1.25,\ 5 \right\}$ kHz,
otherwise the value of $\mu$ corresponds to
$\mathrm{\Delta}f_{\text{RA}} \in \left\{ 15,\ 30,\ 60,\ 120,\ 480,\ 960 \right\}$
kHz and the symbol position ![](media/image112.wmf){width="9.375e-2in"
height="0.19791666666666666in"} is given by

$l = l_{0} + n_{t}^{\text{RA}}N_{\text{dur}}^{\text{RA}} + 14n_{\text{slot}}^{\text{RA}}$

where

\- ![](media/image113.wmf){width="0.125in" height="0.21875in"} is given
by the parameter \"starting symbol\" in Tables 6.3.3.2-2 to 6.3.3.2-4;

\- ![](media/image114.wmf){width="0.2604166666666667in"
height="0.22916666666666666in"} is the PRACH transmission occasion
within the PRACH slot, numbered in increasing order from 0 to
![](media/image115.wmf){width="0.625in" height="0.22916666666666666in"}
within a RACH slot where
![](media/image116.wmf){width="0.4583333333333333in"
height="0.22916666666666666in"} is given Tables 6.3.3.2-2 to 6.3.3.2-4
for $L_{\text{RA}} \in \left\{ 139,571,1151 \right\}$ and fixed to 1 for
![](media/image117.wmf);

\- ![](media/image118.wmf){width="0.3020833333333333in"
height="0.22916666666666666in"} is given by Tables 6.3.3.2-2 to
6.3.3.2-4;

\- ![](media/image119.wmf){width="0.2604166666666667in"
height="0.22916666666666666in"} is given by

\- if
$\mathrm{\Delta}f_{\text{RA}} \in \left\{ 1.25,\ 5,\ 15,\ 60 \right\}$
kHz, then ![](media/image120.wmf){width="0.4895833333333333in"
height="0.22916666666666666in"}

\- if $\mathrm{\Delta}f_{\text{RA}} \in \left\{ 30,\ 120 \right\}$ kHz
and either of \"Number of PRACH slots within a subframe\" in Tables
6.3.3.2-2 to 6.3.3.2-3 or \"Number of PRACH slots within a 60 kHz slot\"
in Table 6.3.3.2-4 is equal to 1, then
$n_{\text{slot}}^{\text{RA}} = 1$, otherwise
$n_{\text{slot}}^{\text{RA}} \in \left\{ 0,1 \right\}$

\- if $\mathrm{\Delta}f_{\text{RA}} \in \left\{ 480,\ 960 \right\}$ kHz
and

\- the \"Number of PRACH slots within a 60 kHz slot\" in Table 6.3.3.2-4
is equal to 1, then $n_{\text{slot}}^{\text{RA}} = 7$ for
$\mathrm{\Delta}f_{\text{RA}} = 480$ kHz and
$n_{\text{slot}}^{\text{RA}} = 15$ for
$\mathrm{\Delta}f_{\text{RA}} = 960\ $kHz, or

\- the \"Number of PRACH slots within a 60 kHz slot\" in Table 6.3.3.2-4
is equal to 2, then
$n_{\text{slot}}^{\text{RA}} \in \left\{ 3,7 \right\}$ for
$\mathrm{\Delta}f_{\text{RA}} = 480\ $kHz and
$n_{\text{slot}}^{\text{RA}} \in \left\{ 7,15 \right\}$ for
$\mathrm{\Delta}f_{\text{RA}} = 960\ $kHz.

If the preamble format given by Tables 6.3.3.2-2 to 6.3.3.2-4 is A1/B1,
A2/B2 or A3/B3, then

\- if $n_{t}^{\text{RA}} = N_{t}^{\text{RA,slot}} - 1$, then the PRACH
preamble with the corresponding PRACH preamble format from B1, B2 and B3
is transmitted in the PRACH transmission occasion;

\- otherwise the PRACH preamble with the corresponding PRACH preamble
format from A1, A2 and A3 is transmitted in the PRACH transmission
occasion