## 5.4 Modulation and upconversion

Modulation and upconversion to the carrier frequency
![](media/image121.wmf) of the complex-valued OFDM baseband signal for
antenna port $p$, subcarrier spacing configuration $\mu$, and OFDM
symbol ![](media/image122.wmf) in a subframe assumed to start at
![](media/image123.wmf) is given by

\- for PRACH

$\text{Re}\left\{ s_{l}^{(p,\mu)}(t)e^{j2\pi f_{0}t} \right\}$

\- for RIM-RS

$\text{Re}\left\{ s_{l}^{(p,\mu)}(t)e^{j2\pi f_{0}^{\text{RIM}}\left( t - t_{{\text{start},l}_{0}}^{\mu} - N_{\text{CP}}^{\text{RIM}}T_{\text{c}} \right)} \right\}$

where $f_{0}^{\text{RIM}}$ is the configured reference point for RIM-RS;

\- for all other channels and signals

![](media/image124.wmf)

NOTE: For the uplink, the signal $s_{l}^{(p,\mu)}(t)$ and the baseband
signals part thereof should be filtered per UE implementation, as
required, to meet the minimum requirements as specified in \[14,
38.101-1\], \[15, 38.101-2\], and \[16, 38.101-5\] for the respective
frequency range.