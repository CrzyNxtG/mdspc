### 4.1.5 Supported max data rate for SL

For NR sidelink, the approximate data rate is computed as follows.

$$\text{data rate }(\text{in Mbps}) = 10^{- 6} \cdot v_{Layers} \cdot Q_{m} \cdot f \cdot R_{\max} \cdot \frac{N_{PRB}^{BW,\mu} \cdot 12}{T_{s}^{\mu}} \cdot (1 - OH)$$

wherein

R~max~ = 948/1024,

> $v_{Layers}$ is the the maximum number of supported layers for
> sidelink transmission (or reception) given by UE capability on
> supporting rank 2 PSSCH transmission and *rankTwoReception*,
>
> $Q_{m}$ is the maximum supported modulation order between 6 or 8 given
> by *sl-Tx-256QAM* and *sl-Rx-256QAM*,
>
> $f$ is the scaling factor for sidelink transmission and reception
> given by *scalingFactorTxSidelink* and *scalingFactorRxSidelink*
> respectively, as specified in TS 36.331 \[17\] and TS 38.331 \[9\],
> and can take the values 1, 0.8, 0.75, and 0.4.

![](media/image7.wmf) is the numerology (as defined in TS 38.211 \[6\])

> ![](media/image8.wmf) is the average OFDM symbol duration in a
> subframe for numerology ![](media/image7.wmf), i.e.
> ![](media/image9.wmf). Note that normal cyclic prefix is assumed.
>
> $N_{PRB}^{BW,\mu}$ is the maximum possible RB allocation in bandwidth
> BW for PSSCH, where BW is the UE supported maximum bandwidth in the
> given band or band combination,

$OH$ is the overhead and takes the following values

> 0.217, for frequency range FR1 for SL
>
> 0.25, for frequency range FR2 for SL