### 5.2.1 Polar coding

The input bit sequence to the code block segmentation is denoted by
![](media/image3.wmf), where ![](media/image26.wmf).

if ![](media/image27.wmf)

Number of code blocks: ![](media/image28.wmf);

else

Number of code blocks: ![](media/image29.wmf)

end if

![](media/image30.wmf);

for ![](media/image31.wmf) to ![](media/image32.wmf)

![](media/image33.wmf);

end for

for ![](media/image34.wmf) to ![](media/image35.wmf)

![](media/image36.wmf);

end for

![](media/image37.wmf);

for ![](media/image38.wmf) to ![](media/image39.wmf)

for ![](media/image40.wmf) to ![](media/image41.wmf)

![](media/image42.wmf);

![](media/image43.wmf);

end for

The sequence ![](media/image44.wmf) is used to calculate the CRC parity
bits ![](media/image45.wmf) according to Clause 5.1 with a generator
polynomial of length ![](media/image6.wmf).

for ![](media/image46.wmf) to ![](media/image47.wmf)

![](media/image48.wmf);

end for

end for

The value of ![](media/image49.wmf) is no larger than 1706.