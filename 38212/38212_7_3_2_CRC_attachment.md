### 7.3.2 CRC attachment

Error detection is provided on DCI transmissions through a Cyclic
Redundancy Check (CRC).

The entire payload is used to calculate the CRC parity bits. Denote the
bits of the payload by![](media/image3.wmf), and the parity bits
by![](media/image4.wmf), where ![](media/image5.wmf) is the payload size
and ![](media/image6.wmf) is the number of parity bits. Let
![](media/image1042.wmf) be a bit sequence such that
![](media/image1043.wmf) for ![](media/image1044.wmf) and
![](media/image1045.wmf) for ![](media/image1046.wmf). The parity bits
are computed with input bit sequence ![](media/image1042.wmf) and
attached according to Clause 5.1 by setting ![](media/image6.wmf) to 24
bits and using the generator polynomial ![](media/image1047.wmf). The
output bit ![](media/image1048.wmf) is

![](media/image22.wmf) for ![](media/image23.wmf)

![](media/image24.wmf) for ![](media/image25.wmf),

where ![](media/image1049.wmf).

After attachment, the CRC parity bits are scrambled with the
corresponding RNTI ![](media/image1050.wmf) , where
![](media/image1051.wmf) corresponds to the MSB of the RNTI, to form the
sequence of bits ![](media/image1052.wmf). The relation between *c~k~*
and *b~k~* is:

![](media/image1053.wmf) for *k* = 0, 1, 2, ...,
![](media/image1054.wmf)

![](media/image1055.wmf) for *k* = ![](media/image1056.wmf),
![](media/image1057.wmf),![](media/image1058.wmf),\...,
![](media/image1059.wmf).