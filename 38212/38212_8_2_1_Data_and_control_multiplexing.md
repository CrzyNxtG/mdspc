### 8.2.1 Data and control multiplexing

Denote the coded bits for SL-SCH
as${\ g}_{0}^{SL - SCH},\ g_{1}^{SL - SCH},\ g_{2}^{SL - SCH},\ g_{3}^{SL - SCH},\cdots,\ g_{G^{SL - SCH} - 1}^{SL - SCH}$.

Denote the coded bits for the 2^nd^-stage SCI, as
$g_{0}^{SCI2},\ g_{1}^{SCI2},\ g_{2}^{SCI2},\ g_{3}^{SCI2},\cdots,\ g_{G^{SCI2} - 1}^{SCI2}$.

Denote the multiplexed data and control coded bit sequence as
$g_{0},g_{1},\cdots,g_{G - 1}$, where *G* is the total number of coded
bits for transmission.

Assuming that $N_{L}$ is the number of layers onto which the SL-SCH
transport block is mapped, the multiplexed data and control coded bit
sequence $g_{0},g_{1},\cdots,g_{G - 1}$ is obtained as follows:

Denote $Q_{m}^{SCI2}$ is modulation order of the 2^nd^-stage SCI.

if $N_{L} = 1$,

for $i = 0$ to $G^{SCI2} + G^{SL - SCH} - 1$

if $0 \leq i < G^{SCI2}$

$g_{i} = g_{i}^{SCI2}$

end if

if $G^{SCI2} \leq i \leq G^{SCI2} + G^{SL - SCH} - 1$

$g_{i} = g_{i - G^{SCI2}}^{SL - SCH}$

end if

end for

end if

if $N_{L} = 2$,

let $M_{count,SCI2}^{RE} = G^{SCI2}/Q_{m}^{SCI2}$

set $m_{count}^{RE} = 0$

for $\ i = 0$ to $M_{count,SCI2}^{RE} - 1$

for $v = 0$ to $N_{L} - 1$

for $\ q = 0$ to $Q_{m}^{SCI2} - 1$

if $v = 0$

$g_{m_{count}^{RE}} = g_{i \bullet Q_{m}^{SCI2} + q}^{SCI2}$

else

$g_{m_{count}^{RE}} = x$ // placeholder bit

end if

$m_{count}^{RE} = m_{count}^{RE} + 1$

end for

end for

end for

> for $\ i = 0$ to $G^{SL - SCH} - 1$

$g_{m_{count}^{RE}} = g_{i}^{SL - SCH}$

$m_{count}^{RE} = m_{count}^{RE} + 1$

> end for

end if