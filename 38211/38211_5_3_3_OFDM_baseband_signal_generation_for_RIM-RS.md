### 5.3.3 OFDM baseband signal generation for RIM-RS

The time-continuous signal $s_{l}^{(p,\mu)}(t)$ on antenna port $p$ for
RIM-RS is defined by

> $s_{l}^{(p,\mu)}(t) = \sum_{k = 0}^{L_{\text{RIM}} - 1}a_{k}^{(p,\text{RIM})}e^{j2\pi\left( k + k_{1} \right)\Delta f_{\text{RIM}}\left( t - N_{\text{CP}}^{\text{RIM}}T_{\text{c}} - t_{\text{start,}l_{0}}^{\mu} \right)}$

where

$$t_{\text{start,}l_{0}}^{\text{RIM}} \leq t < t_{\text{start,}l_{0}}^{\text{RIM}} + \left( N_{\text{u}}^{\text{RIM}} + N_{\text{CP}}^{\text{RIM}} \right)T_{\text{c}}$$

$$N_{\text{u}}^{\text{RIM}} = 2 \cdot 2048\kappa \cdot 2^{- \mu}$$

$$N_{\text{CP}}^{\text{RIM}} = N_{\text{CP,}l_{0}}^{\text{RIM}} + N_{\text{CP,}\overline{l}}^{\text{RIM}}$$

$$\overline{l} = \left\{ \begin{matrix}
0 & \text{if }l_{0} = N_{\text{symb}}^{\text{slot}} - 1 \\
l_{0} + 1 & \text{otherwise}
\end{matrix} \right.\ $$

and

\- $\Delta f_{\text{RIM}} = 15 \cdot 2^{\mu}\text{ kHz}$ where
$\mu \in \left\{ 0,1 \right\}$ is the subcarrier spacing configuration
for the RIM-RS;

\- $k_{1}$ is the starting frequency offset of the RIM-RS as given by
clause 7.4.1.6.4.3;

\- $L_{\text{RIM}} = 12N_{\text{RB}}^{\text{RIM}}$ is the length of the
RIM-RS sequence where $N_{\text{RB}}^{\text{RIM}}$ is the bandwidth of
the RIM-RS in resource blocks;

\- $l_{0}$ is the starting symbol given by clause 7.4.1.6.3;

\- $t_{\text{start,}l_{0}}^{\text{RIM}} = t_{\text{start,}l}^{\mu}$ is
given by clause 5.3.1 with ${l = l}_{0}$;

\- $N_{\text{CP,}l_{0}}^{\text{RIM}} = N_{\text{CP,}l}^{\mu}$ is given
by clause 5.3.1 with ${l = l}_{0}$.