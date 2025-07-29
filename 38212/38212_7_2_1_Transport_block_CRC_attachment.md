### 7.2.1 Transport block CRC attachment

Error detection is provided on each transport block through a Cyclic
Redundancy Check (CRC).

The entire transport block is used to calculate the CRC parity bits.
Denote the bits in a transport block delivered to layer 1
by![](media/image3.wmf), and the parity bits by![](media/image4.wmf),
where ![](media/image5.wmf) is the payload size and
![](media/image6.wmf) is the number of parity bits. The lowest order
information bit ![](media/image386.wmf) is mapped to the most
significant bit of the transport block as defined in Clause 6.1.1 of
\[TS38.321\].

The parity bits are computed and attached to the DL-SCH transport block
according to Clause 5.1, by setting ![](media/image6.wmf) to 24 bits and
using the generator polynomial ![](media/image387.wmf) if
![](media/image388.wmf); and by setting ![](media/image6.wmf) to 16 bits
and using the generator polynomial ![](media/image389.wmf) otherwise.

The bits after CRC attachment are denoted by ![](media/image18.wmf),
where ![](media/image19.wmf).