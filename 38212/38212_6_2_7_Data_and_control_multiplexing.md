### 6.2.7 Data and control multiplexing

In case where there are more than one UL-SCH transport blocks for the
PUSCH transmission, the UCI information is multiplexed only on the
UL-SCH transport block with highest *I~MCS~* value for the initial
PUSCH, where *I~MCS~* is as defined in Clause 6.1.4.1 in \[6, TS
38.214\]. In case the two transport blocks have the same *I~MCS~* value
for the initial PUSCH, the UCI information is multiplexed with data only
on the first transport block. The PUSCH for UCI multiplexing in this
Clause refers to the UL-SCH transport block for UCI multiplexing.

If the higher layer parameter *nrofBitsInUTO-UCI* is configured, the
procedure in this clause 6.2.7 applies by replacing CG‑UCI with UTO-UCI
in all the notations and texts, and replacing \"when higher layer
parameter *cg-UCI-Multiplexing* is configured\" with \"when UTO-UCI and
HARQ-ACK are transmitted on a PUSCH\".

Denote the coded bits for UL-SCH as ![](media/image410.wmf).

Denote the coded bits for HARQ-ACK or jointly coded bits for HARQ-ACK
and CG-UCI when the high layer parameter *cg-UCI-Multiplexing* is
configured, if any, as ![](media/image411.wmf).

Denote the coded bits for CSI part 1, if any, as
![](media/image412.wmf).

Denote the coded bits for CSI part 2, if any, as
![](media/image413.wmf).

Denote the coded bits for CG-UCI without HARQ-ACK, if any, as
$g_{0}^{CG - UCI},\ \ g_{1}^{CG - UCI},\ \ g_{2}^{CG - UCI},\ g_{3}^{CG - UCI},\ \ldots,\ g_{G^{CG - UCI} - 1}^{CG - UCI}$.

Denote the multiplexed data and control coded bit sequence as
![](media/image408.wmf).

Denote ![](media/image414.wmf) as the OFDM symbol index of the PUSCH
transmission, starting from 0 to ![](media/image415.wmf), where
![](media/image416.wmf) is the total number of OFDM symbols of the
PUSCH, including all OFDM symbols used for DMRS.

Denote ![](media/image417.wmf) as the subcarrier index of the PUSCH
transmission, starting from 0 to ![](media/image418.wmf), where
![](media/image419.wmf) is expressed as a number of subcarriers.

Denote ![](media/image420.wmf) as the set of resource elements, in
ascending order of indices ![](media/image417.wmf), available for
transmission of data in OFDM symbol ![](media/image414.wmf), for
![](media/image421.wmf).

Denote ![](media/image422.wmf) as the number of elements in set
![](media/image420.wmf). Denote ![](media/image423.wmf) as the
![](media/image424.wmf)-th element in ![](media/image420.wmf).

Denote ![](media/image425.wmf) as the set of resource elements, in
ascending order of indices ![](media/image417.wmf), available for
transmission of UCI in OFDM symbol ![](media/image414.wmf), for
![](media/image421.wmf). Denote ![](media/image426.wmf) as the number of
elements in set ![](media/image425.wmf). Denote ![](media/image427.wmf)
as the ![](media/image424.wmf)-th element in ![](media/image425.wmf).
For any OFDM symbol that carries DMRS of the PUSCH,
![](media/image428.wmf). For any OFDM symbol that does not carry DMRS of
the PUSCH, ![](media/image429.wmf).

If frequency hopping is configured for the PUSCH,

\- denote ![](media/image430.wmf) as the OFDM symbol index of the first
OFDM symbol after the first set of consecutive OFDM symbol(s) carrying
DMRS in the first hop;

\- denote ![](media/image431.wmf) as the OFDM symbol index of the first
OFDM symbol after the first set of consecutive OFDM symbol(s) carrying
DMRS in the second hop;

\- denote ![](media/image432.wmf) as the OFDM symbol index of the first
OFDM symbol that does not carry DMRS in the first hop;

\- denote ![](media/image433.wmf) as the OFDM symbol index of the first
OFDM symbol that does not carry DMRS in the second hop;

\- if HARQ-ACK is present for transmission on the PUSCH with UL-SCH or
if both HARQ-ACK and CG-UCI are present on the same PUSCH with UL-SCH,
let:

\- ![](media/image434.wmf) and ![](media/image435.wmf);

\- if CSI is present for transmission on the PUSCH with UL-SCH, let:

\- ![](media/image436.wmf);

\- ![](media/image437.wmf);

\- ![](media/image438.wmf); and

\- ![](media/image439.wmf);

\- if CG-UCI is present for transmission on the PUSCH with UL-SCH and
without HARQ-ACK, let:

\-
$G^{CG - UCI}(1) = N_{L} \bullet Q_{m} \bullet \left\lfloor \frac{G^{CG - UCI}}{\left( 2{\bullet N}_{L} \bullet Q_{m} \right)} \right\rfloor$
and
$G^{CG - UCI}(2) = N_{L} \bullet Q_{m} \bullet \left\lceil \frac{G^{CG - UCI}}{\left( 2{\bullet N}_{L} \bullet Q_{m} \right)} \right\rceil$

\- if only HARQ-ACK and CSI part 1 are present for transmission on the
PUSCH without UL-SCH, let:

\- ![](media/image440.wmf);

\- ![](media/image441.wmf);

\- ![](media/image442.wmf); and

\- ![](media/image443.wmf);

\- if HARQ-ACK, CSI part 1 and CSI part 2 are present for transmission
on the PUSCH without UL-SCH, let:

\- ![](media/image444.wmf);

\- ![](media/image441.wmf);

\- if the number of HARQ-ACK information bits is more than
2,![](media/image445.wmf); otherwise, ![](media/image446.wmf)

\- ![](media/image443.wmf);

\- ![](media/image447.wmf) if the number of HARQ-ACK information bits is
no more than 2, and ![](media/image448.wmf) otherwise; and

\- ![](media/image449.wmf) if the number of HARQ-ACK information bits is
no more than 2, and ![](media/image450.wmf) otherwise;

\- if only CSI part 1 and CSI part 2 are present for transmission on the
PUSCH without UL-SCH, let:

\- ![](media/image451.wmf);

\- ![](media/image443.wmf);

\- ![](media/image447.wmf); and

\- ![](media/image449.wmf);

\- let ![](media/image452.wmf), and denote ![](media/image453.wmf),
![](media/image454.wmf) as the number of OFDM symbols of the PUSCH in
the first and second hop, respectively;

\- ![](media/image455.wmf) is the number of transmission layers of the
PUSCH;

\- ![](media/image456.wmf) is the modulation order of the PUSCH;

\- ![](media/image457.wmf);

\- ![](media/image458.wmf);

\- ![](media/image459.wmf).

If frequency hopping is not configured for the PUSCH,

\- denote ![](media/image430.wmf) as the OFDM symbol index of the first
OFDM symbol after the first set of consecutive OFDM symbol(s) carrying
DMRS;

\- denote ![](media/image460.wmf) as the OFDM symbol index of the first
OFDM symbol that does not carry DMRS;

\- if HARQ-ACK is present for transmission on the PUSCH or if both
HARQ-ACK and CG-UCI are present on the same PUSCH with UL-SCH, let
![](media/image461.wmf);

\- if CSI is present for transmission on the PUSCH, let
![](media/image462.wmf) and ![](media/image463.wmf);

\- if CG-UCI is present for transmission on the PUSCH without HARQ-ACK,
let $G^{CG - UCI}(1) = G^{CG - UCI}$;

\- let ![](media/image464.wmf) and ![](media/image465.wmf).

The multiplexed data and control coded bit sequence
![](media/image408.wmf) is obtained according to the following:

**[Step 1:]{.underline}**

Set ![](media/image466.wmf) for ![](media/image421.wmf);

Set ![](media/image467.wmf) for ![](media/image421.wmf);

Set ![](media/image468.wmf) for ![](media/image421.wmf);

Set ![](media/image469.wmf) for ![](media/image421.wmf);

if the number of HARQ-ACK information bits to be transmitted on PUSCH is
0, 1 or 2 bits and without CG-UCI:

the number of reserved resource elements for potential HARQ-ACK
transmission is calculated according to Clause 6.3.2.4.2.1, by setting
![](media/image470.wmf);

denote ![](media/image471.wmf) as the number of coded bits for potential
HARQ-ACK transmission using the reserved resource elements;

if frequency hopping is configured for the PUSCH, let
![](media/image472.wmf) and ![](media/image473.wmf);

if frequency hopping is not configured for the PUSCH, let
![](media/image474.wmf);

denote ![](media/image475.wmf) as the set of reserved resource elements
for potential HARQ-ACK transmission, in OFDM symbol
![](media/image414.wmf), for ![](media/image421.wmf);

Set ![](media/image476.wmf);

Set ![](media/image477.wmf);

![](media/image478.wmf) for ![](media/image421.wmf);

for ![](media/image479.wmf) to ![](media/image480.wmf)

![](media/image481.wmf);

while ![](media/image482.wmf)

if ![](media/image483.wmf)

if ![](media/image484.wmf)

![](media/image485.wmf);

![](media/image486.wmf);

end if

if ![](media/image487.wmf)

![](media/image488.wmf);

![](media/image489.wmf);

end if

for ![](media/image490.wmf) to ![](media/image491.wmf)

![](media/image492.wmf)

![](media/image493.wmf);

end for

end if

![](media/image494.wmf);

end while

end for

else

![](media/image478.wmf) for ![](media/image421.wmf);

end if

Denote ![](media/image495.wmf) as the number of elements in
![](media/image496.wmf).

**Step 2:**

if HARQ-ACK is present for transmission on the PUSCH and the number of
HARQ-ACK information bits is more than 2 or if both HARQ-ACK and CG-UCI
are present on the same PUSCH with UL-SCH:

Set ![](media/image476.wmf);

Set ![](media/image477.wmf);

Set ![](media/image497.wmf);

for ![](media/image498.wmf) to ![](media/image499.wmf)

![](media/image481.wmf);

while ![](media/image500.wmf)

if ![](media/image483.wmf)

if ![](media/image501.wmf)

![](media/image485.wmf);

![](media/image502.wmf);

end if

if ![](media/image503.wmf)

![](media/image504.wmf);

![](media/image505.wmf);

end if

for ![](media/image490.wmf) to ![](media/image491.wmf)

![](media/image506.wmf);

for ![](media/image507.wmf) to ![](media/image508.wmf)

> ![](media/image509.wmf);
>
> ![](media/image510.wmf);
>
> ![](media/image511.wmf);

end for

end for

![](media/image512.wmf);

for ![](media/image490.wmf) to ![](media/image491.wmf)

![](media/image513.wmf);

end for

![](media/image514.wmf);

![](media/image515.wmf);

![](media/image469.wmf);

![](media/image467.wmf);

end if

![](media/image494.wmf);

end while

end for

end if

**Step 2A:**

If CG-UCI is present for transmission on the PUSCH without HARQ-ACK:

Set $m_{count}^{CG - UCI}(1) = 0$;

Set $m_{count}^{CG - UCI}(2) = 0$;

Set $m_{count,all}^{CG - UCI} = 0$;

for $i = 1$ to $N_{hop}^{PUSCH}$

$l = l^{(i)}$;

while $m_{count}^{CG - UCI}(i) < G^{CG - UCI}$($i$)

if ${\overline{M}}_{sc}^{UCI}(l) > 0$

if
${G^{CG - UCI}(i)\  - m}_{count}^{CG - UCI}(1) \geq {\overline{M}}_{sc}^{UCI}(l).N_{L}.Q_{m}$

$d = 1$;

$m_{count}^{RE} = {\overline{M}}_{sc}^{UCI}(l)$;

end if

if
${G^{CG - UCI}(i)\  - m}_{count}^{CG - UCI}(1) < {\overline{M}}_{sc}^{UCI}(l).N_{L}.Q_{m}$

$d = \left\lfloor \frac{{\overline{M}}_{sc}^{UCI}(l).N_{L}.Q_{m}}{\left( {G^{CG - UCI}(i)\  - m}_{count}^{CG - UCI}(i) \right)} \right\rfloor$;

$m_{count}^{RE} = \left\lceil \frac{\left( {G^{CG - UCI}(i)\  - m}_{count}^{CG - UCI}(i) \right)}{\left( N_{L}.Q_{m} \right)} \right\rceil$;

end if

for $j = 0$ to $m_{count}^{RE} - 1$

$k = {\overline{\Phi}}_{l}^{UCI}(j.d)$;

for $v = 0$ to $N_{L}.Q_{m} - 1$

${\overline{g}}_{l,k,v} = g_{m_{count,all}^{CG - UCI}}^{CG - UCI}$;

$m_{count,all}^{CG - UCI} = m_{count,all}^{CG - UCI} + 1$;

$m_{count}^{CG - UCI}(i) = m_{count}^{CG - UCI}(i) + 1$;

end for

end for

${\overline{\Phi}}_{l,tmp}^{UCI} = \varnothing$;

for $j = 0$ to $m_{count}^{RE} - 1$

${\overline{\Phi}}_{l,tmp}^{UCI} = {\overline{\Phi}}_{l,tmp}^{UCI} \cup {\overline{\Phi}}_{l}^{UCI}(j.d)$;

end for

${\overline{\Phi}}_{l}^{UCI} = {\overline{\Phi}}_{l}^{UCI}\backslash{\overline{\Phi}}_{l,tmp}^{UCI}$;

${\overline{\Phi}}_{l}^{UL - SCH} = {\overline{\Phi}}_{l}^{UL - SCH}\backslash{\overline{\Phi}}_{l,tmp}^{UCI}$;

${\overline{M}}_{sc}^{UCI}(l) = \left| {\overline{\Phi}}_{l}^{UCI} \right|$;

${\overline{M}}_{sc}^{UL - SCH}(l) = \left| {\overline{\Phi}}_{l}^{UL - SCH} \right|$;

end if

$l = l + 1$;

end while

end for

end if

**Step 3:**

if CSI is present for transmission on the PUSCH:

Set ![](media/image516.wmf);

Set ![](media/image517.wmf);

Set ![](media/image518.wmf);

for ![](media/image519.wmf) to ![](media/image520.wmf)

![](media/image521.wmf);

while ![](media/image522.wmf)

![](media/image523.wmf);

end while

while ![](media/image524.wmf)

if ![](media/image525.wmf)

if ![](media/image526.wmf)

![](media/image485.wmf);

![](media/image527.wmf);

end if

if ![](media/image528.wmf)

![](media/image529.wmf);

![](media/image530.wmf);

end if

![](media/image531.wmf);

for ![](media/image490.wmf) to ![](media/image491.wmf)

![](media/image532.wmf);

for ![](media/image507.wmf) to ![](media/image508.wmf)

> ![](media/image533.wmf);
>
> ![](media/image534.wmf);
>
> ![](media/image535.wmf);

end for

end for

![](media/image512.wmf);

for ![](media/image490.wmf) to ![](media/image491.wmf)

![](media/image536.wmf);

end for

![](media/image514.wmf);

![](media/image515.wmf);

![](media/image469.wmf);

![](media/image467.wmf);

end if

![](media/image494.wmf);

end while

end for

Set ![](media/image537.wmf);

Set ![](media/image538.wmf);

Set ![](media/image539.wmf);

for ![](media/image540.wmf) to ![](media/image541.wmf)

![](media/image521.wmf);

while ![](media/image542.wmf)

![](media/image543.wmf);

end while

while ![](media/image544.wmf)

if ![](media/image545.wmf)

if ![](media/image546.wmf)

![](media/image485.wmf);

![](media/image547.wmf);

end if

if ![](media/image548.wmf)

![](media/image549.wmf);

![](media/image550.wmf);

end if

for ![](media/image490.wmf) to ![](media/image491.wmf)

![](media/image551.wmf);

for ![](media/image507.wmf) to ![](media/image508.wmf)

> ![](media/image552.wmf);
>
> ![](media/image553.wmf);
>
> ![](media/image554.wmf);

end for

end for

![](media/image512.wmf);

for ![](media/image490.wmf) to ![](media/image491.wmf)

![](media/image513.wmf);

end for

![](media/image514.wmf);

![](media/image515.wmf);

![](media/image469.wmf);

![](media/image467.wmf);

end if

![](media/image494.wmf);

end while

end for

end if

**Step 4:**

if UL-SCH is present for transmission on the PUSCH:

Set ![](media/image555.wmf);

for ![](media/image556.wmf) to ![](media/image557.wmf)

if ![](media/image558.wmf)

for ![](media/image490.wmf) to ![](media/image559.wmf)

![](media/image560.wmf);

for ![](media/image507.wmf) to ![](media/image508.wmf)

![](media/image561.wmf);

![](media/image562.wmf);

end for

end for

end if

end for

end if

**Step 5:**

if HARQ-ACK is present for transmission on the PUSCH without CG-UCI and
the number of HARQ-ACK information bits is no more than 2:

Set ![](media/image476.wmf);

Set ![](media/image477.wmf);

Set ![](media/image497.wmf);

for ![](media/image563.wmf) to ![](media/image564.wmf)

![](media/image481.wmf);

while ![](media/image500.wmf)

if ![](media/image565.wmf)

if ![](media/image566.wmf)

![](media/image485.wmf);

![](media/image567.wmf);

end if

if ![](media/image568.wmf)

![](media/image569.wmf);

![](media/image570.wmf);

end if

for ![](media/image490.wmf) to ![](media/image491.wmf)

![](media/image571.wmf);

for ![](media/image507.wmf) to ![](media/image508.wmf)

> ![](media/image509.wmf);
>
> ![](media/image510.wmf);
>
> ![](media/image511.wmf);

end for

end for

end if

![](media/image494.wmf);

end while

end for

end if

**Step 6:**

Set ![](media/image572.wmf);

for ![](media/image556.wmf) to ![](media/image557.wmf)

for ![](media/image490.wmf) to ![](media/image573.wmf)

![](media/image574.wmf);

for ![](media/image507.wmf) to ![](media/image508.wmf)

![](media/image575.wmf);

![](media/image576.wmf);

end for

end for

end for