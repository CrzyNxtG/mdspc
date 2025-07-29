### 5.2.3 Low-PAPR sequence generation type 2

The low-PAPR sequence $r_{u,v}^{(\alpha,\delta)}(n)$ is defined by a
base sequence ${\overline{r}}_{u,v}(n)$ according to

$$r_{u,v}^{(\alpha,\delta)}(n) = {\overline{r}}_{u,v}(n),\ \ \ \ \ \ \ \ \ \ 0 \leq n < M$$

where $M = \frac{mN_{\text{sc}}^{\text{RB}}}{2^{\delta}}$ is the length
of the sequence.

Base sequences ${\overline{r}}_{u,v}(n)$ are divided into groups, where
$u \in \left\{ 0,1,\ldots,29 \right\}$ is the group number and $v$ is
the base sequence number within the group, such that each group contains
one base sequence ($v = 0$) of length
$M = \frac{mN_{\text{sc}}^{\text{RB}}}{2^{\delta}}$,
$\frac{1}{2 \leq \frac{m}{2^{\delta}}}$. The sequence
${\overline{r}}_{u,v}(0),\ldots,{\overline{r}}_{u,v}(M - 1)$ is defined
by

$${{\overline{r}}_{u,v}(n) = \frac{1}{\sqrt{M}}\sum_{i = 0}^{M - 1}{{\widetilde{r}}_{u,v}(i)e^{- j\frac{2\pi in}{M}}}
}{n = 0,\ldots,M - 1}$$

where the definition of ${\widetilde{r}}_{u,v}(i)$ depends on the
sequence length.