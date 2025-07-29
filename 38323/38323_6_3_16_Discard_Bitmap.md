### 6.3.16 Discard Bitmap

Length: Variable. The length of the discard bitmap field can be 0.

This field indicates which SDUs are discarded and which SDUs are not
discarded in the transmitting PDCP entity. The bit position of the N^th^
bit in the Discard Bitmap is N, i.e., the bit position of the first bit
in the Discard Bitmap is 1.

Table 6.3.16-1 Discard Bitmap

  -----------------------------------------------------------------------
   Bit   Description
  ------ ----------------------------------------------------------------
    0    PDCP SDU with COUNT = (FDC + bit position) modulo 2^32^ is not
         discarded.

    1    PDCP SDU with COUNT = (FDC + bit position) modulo 2^32^ is
         discarded.
  -----------------------------------------------------------------------