### 5.2.2 Low density parity check coding

The input bit sequence to the code block segmentation is denoted by
![](media/image50.wmf), where ![](media/image51.wmf). If
![](media/image52.wmf) is larger than the maximum code block size
![](media/image53.wmf), segmentation of the input bit sequence is
performed and an additional CRC sequence of ![](media/image54.wmf) bits
is attached to each code block.

For LDPC base graph 1, the maximum code block size is:

\- ![](media/image55.wmf).

For LDPC base graph 2, the maximum code block size is:

\- ![](media/image56.wmf).

Total number of code blocks *C* is determined by:

if ![](media/image57.wmf)

![](media/image58.wmf)

Number of code blocks: ![](media/image59.wmf)

![](media/image60.wmf)

else

![](media/image61.wmf)

Number of code blocks: ![](media/image62.wmf).

![](media/image63.wmf)

end if

The bits output from code block segmentation are denoted
by![](media/image64.wmf) , where ![](media/image65.wmf) is the code
block number, and ![](media/image66.wmf) is the number of bits for the
code block number ![](media/image67.wmf).

The number of bits ![](media/image68.wmf) in each code block is
calculated as:

![](media/image69.wmf);

For LDPC base graph 1,

![](media/image70.wmf).

For LDPC base graph 2,

if ![](media/image71.wmf)

![](media/image72.wmf);

elseif ![](media/image73.wmf)

![](media/image74.wmf);

elseif ![](media/image75.wmf)

![](media/image76.wmf);

else

![](media/image77.wmf);

end if

find the minimum value of ![](media/image78.wmf) in all sets of lifting
sizes in Table 5.3.2-1, denoted as ![](media/image79.wmf), such that
![](media/image80.wmf), and set ![](media/image81.wmf) for LDPC base
graph 1 and ![](media/image82.wmf) for LDPC base graph 2;

The bit sequence ![](media/image83.wmf) is calculated as:

![](media/image37.wmf);

for ![](media/image38.wmf) to ![](media/image39.wmf)

for ![](media/image40.wmf) to ![](media/image84.wmf)

![](media/image85.wmf);

![](media/image43.wmf);

end for

if ![](media/image86.wmf)

The sequence ![](media/image87.wmf) is used to calculate the CRC parity
bits ![](media/image45.wmf) according to Clause 5.1 with the generator
polynomial ![](media/image88.wmf).

for ![](media/image89.wmf) to ![](media/image90.wmf)

![](media/image91.wmf);

end for

end if

for ![](media/image92.wmf) to ![](media/image93.wmf) \-- Insertion of
filler bits

![](media/image94.wmf);

end for

end for