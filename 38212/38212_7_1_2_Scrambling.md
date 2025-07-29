### 7.1.2 Scrambling

For PBCH transmission in a frame, the bit sequence ![](media/image3.wmf)
is scrambled into a bit sequence ![](media/image959.wmf), where
![](media/image960.wmf) for ![](media/image961.wmf) and
![](media/image962.wmf) is generated according to the following:

![](media/image963.wmf);

![](media/image964.wmf);

while ![](media/image965.wmf)

if ![](media/image966.wmf) corresponds to any one of the bits belonging
to the candidate SS/PBCH block index, the half frame index, and 2^nd^
and 3^rd^ least significant bits of the system frame number

![](media/image967.wmf);

else

![](media/image968.wmf);

![](media/image969.wmf);

end if

![](media/image970.wmf);

end while

The scrambling sequence ![](media/image971.wmf) is given by Clause
5.2.1of \[4, TS38.211\] and initialized with ![](media/image972.wmf) at
the start of each SFN satisfying ![](media/image973.wmf);
![](media/image974.wmf) for ${\overline{L}}_{\max} = 4$ or
${\overline{L}}_{\max} = 8$, $M = A - 4$ for
${\overline{L}}_{\max} = 10$, $M = A - 5$ for
${\overline{L}}_{\max} = 20$, and ![](media/image975.wmf) for
${\overline{L}}_{\max} = 64$, where ${\overline{L}}_{\max}$ is the
number of candidate SS/PBCH blocks in a half frame according to Clause
4.1 of \[5, TS38.213\]; and ![](media/image976.wmf) is determined
according to Table 7.1.2-1 using the 3^rd^ and 2^nd^ LSB of the SFN in
which the PBCH is transmitted.

Table 7.1.2-1: Value of ![](media/image976.wmf) for PBCH scrambling

  --------------------------------------------------------------------------------
  *(3^rd^ LSB of SFN, 2^nd^ LSB of SFN)*                 *Value of*
                                                         ![](media/image976.wmf)
  ------------------------------------------------------ -------------------------
  (0, 0)                                                 0

  (0, 1)                                                 1

  (1, 0)                                                 2

  (1, 1)                                                 3
  --------------------------------------------------------------------------------