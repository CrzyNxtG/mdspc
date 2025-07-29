### 6.2.3 Code block segmentation and code block CRC attachment

The bits input to the code block segmentation are denoted by
![](media/image18.wmf) where ![](media/image396.wmf) is the number of
bits in the transport block (including CRC).

Code block segmentation and code block CRC attachment are performed
according to Clause 5.2.2.

The bits after code block segmentation are denoted
by![](media/image397.wmf), where ![](media/image67.wmf) is the code
block number and ![](media/image398.wmf) is the number of bits for code
block number ![](media/image67.wmf) according to Clause 5.2.2.

When the value of *numberOfSlotsTBoMS* in the row indicated by the Time
domain resource assignment field in DCI is larger than 1, the value of
*B* is no larger than 3840 if $R \leq 0.25$ and no larger than 8448
otherwise, where coding rate $R$ is indicated by the MCS index according
to Clause 6.1.4.1 in \[6, TS 38.214\].