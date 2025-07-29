### 16.2.0 S-SS/PSBCH blocks

A UE determines a power $P_{\text{S-SSB}}(i)$ for an S-SS/PSBCH block
transmission occasion in slot $i$, in the anchor RB-set if applicable,
on active SL BWP $b$ of carrier $f$ as

$P_{\text{S-SSB}}(i) = \min\left( P_{\text{CMAX}} - P_{offset},P_{\text{O},S - SSB} + 10\log_{10}\left( 2^{\mu} \bullet M_{RB}^{S - SSB} \right) + \alpha_{S - SSB} \cdot PL \right)$
\[dBm\]

where

\- $P_{\text{CMAX}}$ is defined in \[8-1, TS 38.101-1\]

\- $P_{\text{O},S - SSB}$ is a value of *dl-P0-PSBCH-r17* if using the
parameter is supported by the UE and the parameter is provided; else
*dl-P0-PSBCH-r16* if provided; otherwise,
$P_{\text{S-SSB}}(i) = P_{\text{CMAX}} - P_{offset}$

\- $\alpha_{S - SSB}$ is a value of *dl-Alpha-PSBCH*, if provided; else,
$\alpha_{S - SSB} = 1$

\- $PL = PL_{b,f,c}(q_{d})$ when the active SL BWP is on a serving cell
$c$, as described in clause 7.1.1 except that

\- the RS resource is the one the UE uses for determining a power of a
PUSCH transmission scheduled by a DCI format 0_0 in serving cell $c$
when the UE is configured to monitor PDCCH for detection of DCI format
0_0 in serving cell $c$

\- the RS resource is the one corresponding to the SS/PBCH block the UE
uses to obtain MIB when the UE is not configured to monitor PDCCH for
detection of DCI format 0_0 in serving cell $c$

\- $M_{RB}^{S - SSB} = 11$ is a number of resource blocks for a
S-SS/PSBCH block transmission with SCS configuration $\mu$

\- $P_{offset}$ is a value of *sl-SSSBPowerOffsetOfAnchorRBSet*, if
provided; otherwise, $P_{offset} = 0$.

For operation with shared spectrum channel access, after allocating
power $P_{\text{S-SSB}}(i)$ for transmission of each S-SS/PSBCH block in
the anchor RB-set, the UE equally allocates power
${P'}_{\text{S-SSB}}(i)$ remaining from $P_{\text{CMAX}}$, if any, for
transmission of each S-SS/PSBCH block in all non-anchor RB-sets within
the SL BWP

\- if *dl-P0-PSBCH* is not provided, a power
${P^{''}}_{\text{S-SSB}}(i)$ for transmission of each S-SS/PSBCH block
in a non-anchor RB-set is
${P^{''}}_{\text{S-SSB}}(i) = {P'}_{\text{S-SSB}}(i)$

\- otherwise, a power ${P^{''}}_{\text{S-SSB}}(i)$ for transmission of
each S-SS/PSBCH block in a non-anchor RB-set is
${P^{''}}_{\text{S-SSB}}(i) = \min\left( {P'}_{\text{S-SSB}}(i),P_{0,\ S - SSB} + 10\log_{10}{{(2}^{\mu} \cdot M_{RB}^{S - SSB}) + \alpha_{S - SSB} \cdot PL} \right)$.