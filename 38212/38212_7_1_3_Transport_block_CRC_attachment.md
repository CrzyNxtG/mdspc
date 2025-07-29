### 7.1.3 Transport block CRC attachment

Error detection is provided on BCH transport blocks through a Cyclic
Redundancy Check (CRC).

The entire transport block is used to calculate the CRC parity bits. The
input bit sequence is denoted by ![](media/image959.wmf), and the parity
bits by![](media/image4.wmf), where ![](media/image5.wmf) is the payload
size and ![](media/image6.wmf) is the number of parity bits.

The parity bits are computed and attached to the BCH transport block
according to Clause 5.1 by setting ![](media/image6.wmf) to 24 bits and
using the generator polynomial ![](media/image977.wmf), resulting in the
sequence![](media/image18.wmf), where ![](media/image19.wmf).

The bit sequence ![](media/image18.wmf) is the input bit sequence
![](media/image714.wmf) to the channel encoder, where
![](media/image978.wmf) for ![](media/image979.wmf) and
![](media/image980.wmf).