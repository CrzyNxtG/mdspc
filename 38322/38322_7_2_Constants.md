## 7.2 Constants

a\) AM_Window_Size

This constant is used by both the transmitting side and the receiving
side of each AM RLC entity. AM_Window_Size = 2048 when a 12 bit SN is
used, AM_Window_Size = 131072 when an 18 bit SN is used.

b\) UM_Window_Size

This constant is used by the receiving UM RLC entity to define SNs of
those UMD SDUs that can be received without causing an advancement of
the receiving window. UM_Window_Size = 32 when a 6 bit SN is configured,
UM_Window_Size = 2048 when a 12 bit SN is configured.