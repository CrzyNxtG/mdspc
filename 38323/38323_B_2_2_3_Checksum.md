### B.2.2.3 Checksum

Length: 4 bits

This field contains the validation bits for the compression buffer
content: The checksum is calculated by the content of current
compression buffer before the current packet is put into buffer.

The checksum is derived from the values of the first 4 bytes and the
last 4 bytes in the whole compression buffer. The calculation is
described as follows:

\- Each byte is divided into two 4-bit numbers.

\- The 16 4-bit numbers are added together to obtain a sum;

\- The checksum is one\'s complement of the right-most 4 bits (i.e. 4
LSB) of the sum.

An example of checksum calculation is shown in Annex B.2.3.