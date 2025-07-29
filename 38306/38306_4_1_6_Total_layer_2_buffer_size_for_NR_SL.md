### 4.1.6 Total layer 2 buffer size for NR SL

The total layer 2 buffer size for NR sidelink communication is defined
as the sum of the number of bytes that the UE is capable of storing in
the RLC transmission windows and RLC reception and reassembly windows
and also in PDCP reordering windows for all radio bearers for NR
sidelink communication.

The required total layer 2 buffer size for NR sidelink communication is
the maximum value of the calculated values based on the following
equations:

*MaxSLtxDataRate* \* *RLC RTT* + *MaxSLrxDataRate* \* *RLC RTT*.

NOTE: Additional L2 buffer required for preprocessing of data is not
taken into account in above formula.

The required total layer 2 buffer size for NR sidelink communication is
determined as the maximum total layer 2 buffer size of all the
calculated ones for each band combination and the applicable Feature Set
combination in the supported NR sidelink band combinations. The RLC RTT
for NR sidelink communication corresponds to the smallest SCS numerology
supported in the band combination and the applicable Feature Set
combination.

wherein

> RLC RTT for NR sidelink communication is defined in Table 4.1.6-1

Table 4.1.6-1: RLC RTT for NR sidelink communication per SCS

  -----------------------------------------------------------------------
                 SCS (kHz)                         RLC RTT (ms)
  --------------------------------------- -------------------------------
                   15KHz                                200

                   30KHz                                100

                   60KHz                                50

                  120KHz                                25
  -----------------------------------------------------------------------