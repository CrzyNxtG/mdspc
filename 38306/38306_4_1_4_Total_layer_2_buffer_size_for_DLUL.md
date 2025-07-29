### 4.1.4 Total layer 2 buffer size for DL/UL

The total layer 2 buffer size is defined as the sum of the number of
bytes that the UE is capable of storing in the RLC transmission windows
and RLC reception and reassembly windows and also in PDCP reordering
windows for all radio bearers.

The required total layer 2 buffer size in MR-DC is the maximum value of
the calculated values based on the following equations:

\- *MaxULDataRate_MN* \* *RLCRTT_MN* + *MaxULDataRate_SN* \*
*RLCRTT_SN* + *MaxDLDataRate_SN* \* *RLCRTT_SN* + *MaxDLDataRate_MN*
*\** (*RLCRTT_SN* + *X2/Xn delay* + *Queuing in SN*)

\- *MaxULDataRate_MN* \* *RLCRTT_MN* + *MaxULDataRate_SN* \*
*RLCRTT_SN* + *MaxDLDataRate_MN* \* *RLCRTT_MN* + *MaxDLDataRate_SN*
*\** (*RLCRTT_MN* + *X2/Xn delay* + *Queuing in MN*)

Otherwise it is calculated by *MaxDLDataRate \* RLC RTT + MaxULDataRate
\* RLC RTT*.

NOTE: Additional L2 buffer required for preprocessing of data is not
taken into account in above formula.

The required total layer 2 buffer size is determined as the maximum
total layer 2 buffer size of all the calculated ones for each band
combination and the applicable Feature Set combination in the supported
MR-DC or NR band combinations. The RLC RTT for NR cell group corresponds
to the smallest SCS numerology supported in the band combination and the
applicable Feature Set combination.

wherein

> X2/Xn delay + Queuing in SN = 25ms if SCG is NR, and 55ms if SCG is
> EUTRA
>
> X2/Xn delay + Queuing in MN = 25ms if MCG is NR, and 55ms if MCG is
> EUTRA
>
> RLC RTT for EUTRA cell group = 75ms
>
> RLC RTT for NR cell group is defined in Table 4.1.4-1

Table 4.1.4-1: RLC RTT for NR cell group per SCS

  -----------------------------------------------------------------------
                 SCS (kHz)                         RLC RTT (ms)
  --------------------------------------- -------------------------------
                   15KHz                                50

                   30KHz                                40

                   60KHz                                30

                  120KHz                                20

                  480KHz                                20

                  960KHz                                20
  -----------------------------------------------------------------------