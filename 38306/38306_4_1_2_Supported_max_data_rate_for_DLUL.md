### 4.1.2 Supported max data rate for DL/UL

For NR, the approximate data rate for a given number of aggregated
carriers in a band or band combination is computed as follows.

![](media/image3.wmf)

wherein

J is the number of aggregated component carriers in a band or band
combination

R~max~ = 948/1024

For the j-th CC,

![](media/image4.wmf){width="0.3333333333333333in" height="0.28125in"}
is the maximum number of supported layers given by
*maxNumberMIMO-LayersPDSCH* for downlink and maximum of
*maxNumberMIMO-LayersCB-PUSCH* and *maxNumberMIMO-LayersNonCB-PUSCH* for
uplink.

![](media/image5.wmf) is the maximum supported modulation order given by
*supportedModulationOrderDL* for downlink and
*supportedModulationOrderUL* for uplink.

![](media/image6.wmf)is the scaling factor given by *scalingFactor* or
*scalingFactor-1024QAM-FR1* and can take the values 1, 0.8, 0.75, and
0.4.

![](media/image7.wmf) is the numerology (as defined in TS 38.211 \[6\])

![](media/image8.wmf) is the average OFDM symbol duration in a subframe
for numerology ![](media/image7.wmf), i.e. ![](media/image9.wmf). Note
that normal cyclic prefix is assumed.

![](media/image10.wmf) is the maximum RB allocation in bandwidth
![](media/image11.wmf) with numerology ![](media/image7.wmf), as defined
in 5.3 TS 38.101-1 \[2\], 5.3 TS 38.101-2 \[3\], and 5.3 TS 38.101-5
\[34\], where ![](media/image11.wmf) is the UE supported maximum
bandwidth in the given band or band combination.

![](media/image12.wmf)is the overhead and takes the following values

> 0.14, for frequency range FR1 for DL
>
> 0.18, for frequency range FR2 for DL
>
> 0.08, for frequency range FR1 for UL
>
> 0.10, for frequency range FR2 for UL

NOTE 1: Only one of the UL or SUL carriers (the one with the higher data
rate) is counted for a cell operating SUL.

NOTE 2: For UL Tx switching between carriers, only the supported MIMO
layer combination across carriers that results in the highest combined
data rate is counted for the carriers in the supported maximum UL data
rate.

The approximate maximum data rate can be computed as the maximum of the
approximate data rates computed using the above formula for each of the
supported band or band combinations. For the CCs where UE supports
*pdsch-1024QAM-2MIMO-FR1-r17* for the concerned band, data rate shall be
derived as maximum what UE would support if using 1024 QAM (when
*mcs-Table-r17* or *mcs-TableDCI-1-2-r17* is configured) or 256 QAM.

For single carrier NR SA operation and except for UEs supporting
*supportOfERedCap-r18*, the UE shall support a data rate for the carrier
that is no smaller than the data rate computed using the above formula,
with $J = 1\ CC$ and component
$v_{Layers}^{(j)} \cdot Q_{m}^{(j)} \cdot f_{}^{(j)}$ is no smaller than
4.

NOTE 3: As an example, the value 4 in the component above can correspond
to $v_{Layers}^{(j)} = 1$, $Q_{m}^{(j)} = \ 4$ and $f_{}^{(j)} = 1$.

For single carrier NR SA operation and for UEs supporting
*supportOfERedCap-r18*, the UE shall support a data rate for the carrier
that is the data rate computed using the above formula, with $J = 1\ CC$
and:

if the UE supports *eRedCapNotReducedBB-BW-r18:*

\- component $v_{Layers}^{(j)} \cdot Q_{m}^{(j)} \cdot f_{}^{(j)}$ is
0.75 if $v_{Layers}^{(j)} = 1$, or;

\- component $v_{Layers}^{(j)} \cdot Q_{m}^{(j)} \cdot f_{}^{(j)}$ is
0.8 if $v_{Layers}^{(j)} = 2$;

else:

\- component $v_{Layers}^{(j)} \cdot Q_{m}^{(j)} \cdot f_{}^{(j)}$ is
3.2, and;;

\- ![](media/image10.wmf) is 25 if μ = 0 or, 12 if μ = 1;

For EUTRA in case of MR-DC, the approximate data rate for a given number
of aggregated carriers in a band or band combination is computed as
follows.

> Data rate (in Mbps) =
> $10^{- 3}*\sum_{j = 1}^{J}{TBS_{j\ \ }}$![](media/image13.wmf)

wherein

J is the number of aggregated EUTRA component carriers in MR-DC band
combination

$TBS_{j\ \ }$is the total maximum number of DL-SCH transport block bits
received or the total maximum number of UL-SCH transport block bits
transmitted, within a 1ms TTI for j-th CC, as derived from TS 36.213
\[19\] based on the UE supported maximum MIMO layers for the j-th CC,
and based on the maximum modulation order for the j-th CC and number of
PRBs based on the bandwidth of the j-th CC according to indicated UE
capabilities.

The approximate maximum data rate can be computed as the maximum of the
approximate data rates computed using the above formula for each of the
supported band or band combinations.

For MR-DC, the approximate maximum data rate is computed as the sum of
the approximate maximum data rates from NR and EUTRA.