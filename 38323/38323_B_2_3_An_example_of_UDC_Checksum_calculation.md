## B.2.3 An example of UDC Checksum calculation

The current UDC compression/decompression buffer has the following
binary values for example:

Header
\<1,1,0,0,0,1,0,1,0,0,1,1,1,1,1,1,0,0,0,1,1,0,0,1,0,1,0,1,0,0,0,1,
......,
0,1,1,1,1,1,0,1,1,0,0,0,1,0,1,0,1,0,0,1,1,1,1,1,1,0,0,1,1,1,0,0\> Tail

The sum of the first 4 bytes and the last 4 bytes can be calculated:

1100+0101+0011+1111+0001+1001+0101+0001+0111+1101+1000+1010+1001+1111+1001+1100
= 10000110;

And checksum value will be one\'s complement of the right-most 4 bits
(i.e. 4 LSB) of the above sum. Hence checksum is 1001.