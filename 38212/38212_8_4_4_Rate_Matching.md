### 8.4.4 Rate Matching

For 2^nd^-stage SCI transmission on PSSCH with SL-SCH, the number of
coded modulation symbols generated for 2^nd^-stage SCI transmission
prior to duplication for the 2nd layer if present, denoted as
$Q_{SCI2}'$, is determined as follows:

$$Q_{SCI2}' = \text{min}\left\{ \left\lceil \frac{\left( O_{SCI2} + L_{SCI2} \right) \bullet \beta_{offset}^{SCI2}}{Q_{m}^{SCI2} \bullet R} \right\rceil,\ \left\lceil \alpha\sum_{l = 0}^{N_{symbol}^{PSSCH} - 1}{M_{sc}^{SCI2}(l)} \right\rceil \right\} + \gamma$$

where

\- $O_{SCI2}$ is the number of the 2^nd^-stage SCI bits

\- $L_{SCI2}$ is the number of CRC bits for the 2^nd^-stage SCI, which
is 24 bits.

\- $\beta_{offset}^{SCI2}$ is indicated in the corresponding 1^st^-stage
SCI.

\- $M_{sc}^{PSSCH}(l)$ is the number of allocated PRBs of PSSCH
transmission $n_{PRB}\ $according to clause 8.1.3.2 in \[6, TS 38.214\],
expressed as a number of subcarriers.

\- $M_{sc}^{PSCCH}(l)$ is the number of subcarriers in OFDM symbol $l$
that carry PSCCH and PSCCH DMRS associated with the PSSCH transmission.

\- $M_{sc}^{SCI2}(l)$ is the number of resource elements that can be
used for transmission of the 2^nd^-stage SCI in OFDM symbol $l$, for
$l = 0,1,2\cdots,N_{symbol}^{PSSCH} - 1$ and for
${N_{symbol}^{PSSCH} = N}_{symb}^{sh} - N_{symb}^{PSFCH} - N_{symb}^{SL\ PRS}$,
in PSSCH transmission, where $N_{symb}^{sh}$$N_{symb}^{slot}$ =
*sl-lengthSymbols* - 2, where *sl-lengthSymbols* is the number of
sidelink symbols within the slot provided by higher layers as defined in
\[6, TS 38.214\]. $N_{symb}^{SL\ PRS}$ is the number of symbols for SL
PRS provided by the higher layer parameter *numSym-SL-PRS-2ndStageSCI*
if the 2^nd^-stage SCI is SCI format 2-D, and $N_{symb}^{SL\ PRS}$ = 0
otherwise. If *sl-StartingSymbolFirst* and *sl-StartingSymbolSecond* are
provided for the SL-BWP, $N_{symb}^{sh}$$N_{symb}^{slot}$ =
*sl-NumRefSymbolLength* - 2, where *sl-NumRefSymbolLength* is provided
by higher layers. If higher layer parameter *sl-PSFCH-Period* = 2 or 4,
$N_{symb}^{PSFCH}$ = 3 if \"PSFCH overhead indication\" field of SCI
format 1-A indicates \"1\", and $N_{symb}^{PSFCH}$ = 0 otherwise. If
higher layer parameter *sl-PSFCH-Period* = 0, $N_{symb}^{PSFCH} = 0$. If
higher layer parameter *sl-PSFCH-Period* is 1, $N_{symb}^{PSFCH} = 3$.

\- $M_{sc}^{SCI2}(l)$ = $M_{sc}^{PSSCH}(l)$ - $M_{sc}^{PSCCH}(l)$

\- $\gamma$ is the number of vacant resource elements in the resource
block to which the last coded symbol of the 2^nd^-stage SCI belongs.

\- $R$ is the coding rate as indicated by \"Modulation and coding
scheme\" field in SCI format 1-A.

\- $\alpha$ is configured by higher layer parameter *sl-Scaling*.

The input bit sequence to rate matching is
$d_{0},\ d_{1},d_{2},d_{3},\ \cdots,d_{N - 1}$, where $N$ is the number
of coded bits.

Rate matching is performed according to Clause 5.4.1 by setting
$I_{BIL} = 1$.

The output bit sequence after rate matching is denoted as
$g_{0}^{SCI2},\ g_{1}^{SCI2},\ g_{2}^{SCI2},\ g_{3}^{SCI2},\cdots,\ g_{G^{SCI2} - 1}^{SCI2}$,
where $G^{SCI2} = Q_{SCI2}' \bullet \ Q_{m}^{SCI2}$ and $Q_{m}^{SCI2}$
is modulation order of the 2^nd^-stage SCI. A UE is not expected to
have$\ G^{SCI2} > 4096$.