### 5.3.1 OFDM baseband signal generation for all channels except PRACH and RIM-RS

The time-continuous signal ![](media/image95.wmf) on antenna port $p$
and subcarrier spacing configuration $\mu$ for OFDM symbol
![](media/image96.wmf) in a subframe for any physical channel or signal
except PRACH is defined by

$s_{l}^{(p,\mu)}(t) = \left\{ \begin{matrix}
{\overline{s}}_{l}^{(p,\mu)}(t) & t_{\text{start,}l}^{\mu} \leq t < t_{\text{start,}l}^{\mu} + T_{\text{symb,}l}^{\mu} \\
0 & \text{otherwise}
\end{matrix} \right.\ $
$${{\overline{s}}_{l}^{(p,\mu)}(t) = \sum_{k = 0}^{N_{\text{grid,}x}^{\text{size},\mu}N_{\text{sc}}^{\text{RB}} - 1}{a_{k,l}^{(p,\mu)}e^{j2\pi\left( k + k_{0}^{\mu} - \frac{N_{\text{grid,}x}^{\text{size},\mu}N_{\text{sc}}^{\text{RB}}}{2} \right)\Delta f\left( t - N_{\text{CP},l}^{\mu}T_{\text{c}} - t_{\text{start,}l}^{\mu} \right)}}
}{k_{0}^{\mu} = \left( N_{\text{grid,}x}^{\text{start},\mu} + \frac{N_{\text{grid,}x}^{\text{size},\mu}}{2} \right)N_{\text{sc}}^{\text{RB}} - \left( N_{\text{grid,}x}^{\text{start},\mu_{0}} + \frac{N_{\text{grid,}x}^{\text{size},\mu_{0}}}{2} \right)N_{\text{sc}}^{\text{RB}}2^{\mu_{0} - \mu}
}{T_{\text{symb,}l}^{\mu} = \left( N_{\text{u}}^{\mu} + N_{\text{CP},l}^{\mu} \right)T_{\text{c}}}$$

where $t = 0$ at the start of the subframe,

![](media/image97.wmf)

and

\- ![](media/image98.wmf) is given by clause 4.2;

\- ![](media/image99.wmf) is the subcarrier spacing configuration;

\- $\mu_{0}$ is the largest $\mu$ value among the subcarrier spacing
configurations by *scs-SpecificCarrierList* for each of uplink and
downlink and by *sl-SCS-SpecificCarrierList* for sidelink.

The starting position of OFDM symbol $l$ for subcarrier spacing
configuration $\mu$ in a subframe is given by

$t_{start,l}^{\mu} = \left\{ \begin{matrix}
0 & l = 0 \\
t_{start,l - 1}^{\mu} + T_{symb,l - 1}^{\mu} & otherwise
\end{matrix} \right.\ $

In case of cyclic prefix extension of the first OFDM symbol $l$
allocated for PUSCH, SRS, PUCCH, PSCCH/PSSCH, PSFCH, or S-SS/PSBCH block
transmission, the time-continuous signal $s_{\text{ext}}^{(p,\mu)}(t)$
for the interval
${t_{\text{start,}l}^{\mu} - T}_{\text{ext}} \leq t < t_{\text{start,}l}^{\mu}$
preceding the first OFDM symbol for PUSCH, SRS, PUCCH, PSCCH/PSSCH,
PSFCH, or S-SS/PSBCH block is given by

$$s_{\text{ext}}^{(p,\mu)}(t) = {\overline{s}}_{l}^{(p,\mu)}(t)$$

where $t < 0$ refers to the signal in the previous subframe and

\- for dynamically scheduled PUSCH, SRS, and PUCCH transmissions

$$T_{\text{ext}}\text{=min}\left( \text{max}\left( T_{\text{ext}}',0 \right),\ T_{\text{symb},(l - 1)\text{mod7∙}2^{\mu}}^{\mu} \right)$$

$$T_{\text{ext}}' = \sum_{k = 1}^{C_{i}}T_{symb,\ \ (l - k)mod\ 7 \bullet 2^{\mu}\ }^{\mu} - \Delta_{i}$$

where $\Delta_{i}$ is given by Table 5.3.1-1 with $C_{1} = 1$ for
$\mu \in \left\{ 0,1 \right\}$, $C_{1} = 2$ for $\mu = 2$, and $C_{2}$
and $C_{3}$ given by the higher-layer parameters *cp-ExtensionC2* and
*cp-ExtensionC3*, respectively, and $T_{\text{TA}}$ given by clause
4.3.1. For contention-based random access, or in absence of higher-layer
configuration of $C_{2}$ and $C_{3}$, the value of $C_{i}$shall be set
to the largest integer fulfilling
$T_{\text{ext}}' < T_{symb,\ \ (l - 1)\text{mod7∙}2^{\mu}\ }^{\mu}$ for
each of the values of $i \in \left\{ 2,3 \right\}$. *T~ext~* is applied
to the first UL transmission scheduled by the scheduling DCI.

\- for a PUSCH transmission using configured grant

$$T_{\text{ext}} = \sum_{k = 1}^{2^{\mu}}T_{symb,\ \ (l - k)mod\ 7 \bullet 2^{\mu}\ }^{\mu} - \Delta_{i}$$

where $\Delta_{i}$ is given by Table 5.3.1-2 with the index $i$ given by
the procedure in \[6, TS 38.214\].

\- for PSCCH/PSSCH, PSFCH, and S-SS/PSBCH block transmission

$$T_{ext} = max\left( \sum_{k = 1}^{C_{i}}T_{symb,\ \ (l - k)mod\ 7 \bullet 2^{\mu}\ }^{\mu} - \Delta_{i},\ 0 \right)$$

where $\Delta_{i}$ and $C_{i}$ are given by Table 5.3.1-3 with the index
$i$ given by the procedure in \[5, TS 38.213\] or \[6, TS 38.214\].

Table 5.3.1-1: The variables $\mathbf{C}_{\mathbf{i}}$ and
$\mathbf{\Delta}_{\mathbf{i}}$ for uplink cyclic prefix extension

  -------------------------------------------------------------------------------------------------------------------
  $\mathbf{T}_{\text{ext}}\mathbf{\ }$index   $$\mathbf{C}_{\mathbf{i}}$$   $$\mathbf{\Delta}_{\mathbf{i}}$$
  $\mathbf{i}$                                                              
  ------------------------------------------- ----------------------------- -----------------------------------------
  0                                           \-                            \-

  1                                           $$C_{1}$$                     $$25 \bullet 10^{- 6}$$

  2                                           $$C_{2}$$                     $$16 \bullet 10^{- 6} + T_{\text{TA}}$$

  3                                           $$C_{3}$$                     $$25 \bullet 10^{- 6} + T_{\text{TA}}$$
  -------------------------------------------------------------------------------------------------------------------

Table 5.3.1-2: The variable $\mathbf{\Delta}_{\mathbf{i}}$ for uplink
cyclic prefix extension with configured grants.

  -------------------------------------------------------------------------------------------------------------
  index $\mathbf{i}$             $$\mathbf{\Delta}_{\mathbf{i}}$$
  ------------------------------ ------------------------------------------------------------------------------
  0                              $$16 \bullet 10^{- 6}$$

  1                              $$25 \bullet 10^{- 6}$$

  2                              $$34 \bullet 10^{- 6}$$

  3                              $$43 \bullet 10^{- 6}$$

  4                              $$52 \bullet 10^{- 6}$$

  5                              $$61 \bullet 10^{- 6}$$

  6                              $$\sum_{k = 1}^{2^{\mu}}T_{symb,\ \ (l - k)mod\ 7 \bullet 2^{\mu}\ }^{\mu}$$
  -------------------------------------------------------------------------------------------------------------

Table 5.3.1-3: The variables $\mathbf{C}_{\mathbf{i}}$ and
$\mathbf{\Delta}_{\mathbf{i}}$ for sidelink cyclic prefix extension

+--------------+----------------------------------------------------------------+----------------------------------------------------------------+----------------------------------------------------------------+
| Index        | $$\mathbf{\mu}\mathbf{= 0}$$                                   | $$\mathbf{\mu}\mathbf{= 1}$$                                   | $$\mathbf{\mu}\mathbf{= 2}$$                                   |
| $\mathbf{i}$ |                                                                |                                                                |                                                                |
|              +-----------------------------+----------------------------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+
|              | $$\mathbf{C}_{\mathbf{i}}$$ | $$\mathbf{\Delta}_{\mathbf{i}}$$ | $$\mathbf{C}_{\mathbf{i}}$$ | $$\mathbf{\Delta}_{\mathbf{i}}$$ | $$\mathbf{C}_{\mathbf{i}}$$ | $$\mathbf{\Delta}_{\mathbf{i}}$$ |
+==============+=============================+==================================+=============================+==================================+=============================+==================================+
| 0            | \-                          | \-                               | \-                          | \-                               | \-                          | \-                               |
+--------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+
| 1            | 1                           | $$16 \bullet 10^{- 6}$$          | 1                           | $$16 \bullet 10^{- 6}$$          | 1                           | $$16 \bullet 10^{- 6}$$          |
+--------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+
| 2            | 1                           | $$25 \bullet 10^{- 6}$$          | 1                           | $$25 \bullet 10^{- 6}$$          | 2                           | $$16 \bullet 10^{- 6}$$          |
+--------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+
| 3            | 1                           | $$34 \bullet 10^{- 6}$$          | 2                           | $$16 \bullet 10^{- 6}$$          | 2                           | $$25 \bullet 10^{- 6}$$          |
+--------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+
| 4            | 1                           | $$43 \bullet 10^{- 6}$$          | 2                           | $$25 \bullet 10^{- 6}$$          | reserved                    | reserved                         |
+--------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+
| 5            | 1                           | $$52 \bullet 10^{- 6}$$          | 2                           | $$34 \bullet 10^{- 6}$$          | reserved                    | reserved                         |
+--------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+
| 6            | 1                           | $$61 \bullet 10^{- 6}$$          | 2                           | $$43 \bullet 10^{- 6}$$          | reserved                    | reserved                         |
+--------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+
| 7            | reserved                    | reserved                         | 2                           | $$52 \bullet 10^{- 6}$$          | reserved                    | reserved                         |
+--------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+
| 8            | reserved                    | reserved                         | 2                           | $$61 \bullet 10^{- 6}$$          | reserved                    | reserved                         |
+--------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+-----------------------------+----------------------------------+