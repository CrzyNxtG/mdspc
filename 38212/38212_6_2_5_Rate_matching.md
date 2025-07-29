### 6.2.5 Rate matching

Coded bits for each code block, denoted as ![](media/image401.wmf), are
delivered to the rate match block, where ![](media/image67.wmf) is the
code block number, and ![](media/image403.wmf) is the number of encoded
bits in code block number ![](media/image67.wmf). The total number of
code blocks is denoted by ![](media/image400.wmf) and each code block is
individually rate matched according to Clause 5.4.2 by setting
![](media/image404.wmf) if higher layer parameter *rateMatching* is set
to *limitedBufferRM* and by setting ![](media/image405.wmf) otherwise,
if *numberOfSlotsTBoMS* is not present in the resource allocation table,
or if *numberOfSlotsTBoMS* is present in the resource allocation table
and the value of *numberOfSlotsTBoMS* in the row indicated by the Time
domain resource assignment field in DCI is equal to 1. When the value of
*numberOfSlotsTBoMS* in the row indicated by the Time domain resource
assignment field in DCI is larger than 1, each code block is
individually rate matched per slot according to Clause 5.4.2 by setting:

\- $I_{LBRM} = 1$ if higher layer parameter *rateMatching* is set to
*limitedBufferRM* and by setting $I_{LBRM} = 0\ $otherwise;

\- $G$ as the total number of coded bits available for transmission of
the transport block in the slot;

\- $k_{0}$ as given by Table 5.4.2.1-2 according to the value of
${rv}_{id}$ and LDPC base graph if the slot is the first slot within the
$N_{s}$ slots allocated for the transmission of TB processing over
multiple slots, and setting
$k_{0} = \left( k_{0}' + H + \tau \right)modN_{cb}\ $if the slot is a
slot except for the first one within the $N_{s}$ slots, where $N_{s}$ is
the value of *numberOfSlotsTBoMS* in the row indicated by the Time
domain resource assignment field in DCI, $k_{0}'$ denotes the index of
starting coded bit in the previous slot within the $N_{s}$ slots, $H$ is
the total number of coded bits available for transmission of the
transport block in the previous slot within the $N_{s}$ slots assuming
no UCI multiplexing, and $\tau$ denotes the number of skipped filler
bits if any in the previous slot within the $N_{s}$ slots according to
Clause 5.4.2.1 by assuming no UCI multiplexing.

After rate matching, the bits are denoted by![](media/image406.wmf),
where![](media/image407.wmf) is the number of rate matched bits for code
block number ![](media/image67.wmf).