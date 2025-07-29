## 5.1 Waveform, numerology and frame structure

The downlink transmission waveform is conventional OFDM using a Cyclic
Prefix. The uplink transmission waveform is conventional OFDM using a CP
with a transform precoding function performing DFT spreading that can be
disabled or enabled. For operation with shared spectrum channel access
in FR1, the uplink transmission waveform subcarrier mapping can map to
subcarriers in one or more PRB interlaces.

![](media/image19.emf)

Figure 5.1-1: Transmitter block diagram for CP-OFDM with optional
DFT-spreading

The numerology is based on exponentially scalable sub-carrier spacing
*∆f* = 2*^µ^* × 15 kHz with *µ*={0,1,3,4,5,6} for PSS, SSS and PBCH and
*µ*={0,1,2,3,5,6} for other channels. Normal CP is supported for all
sub-carrier spacings, Extended CP is supported for *µ*=2. 12 consecutive
sub-carriers form a Physical Resource Block (PRB). Up to 275 PRBs are
supported on a carrier.

Table 5.1-1: Supported transmission numerologies.

  -------------------------------------------------------------------------------------------------------------------------------------------------
  ![](media/image20.wmf){width="0.15625in"   ![](media/image21.wmf){width="1.0520833333333333in"   CP              Supported for   Supported for
  height="0.1875in"}                         height="0.23958333333333334in"}                                       data            synch
  ------------------------------------------ ----------------------------------------------------- --------------- --------------- ----------------
  0                                          15                                                    Normal          Yes             Yes

  1                                          30                                                    Normal          Yes             Yes

  2                                          60                                                    Normal,         Yes             No
                                                                                                   Extended                        

  3                                          120                                                   Normal          Yes             Yes

  4                                          240                                                   Normal          No              Yes

  5                                          480                                                   Normal          Yes             Yes

  6                                          960                                                   Normal          Yes             Yes
  -------------------------------------------------------------------------------------------------------------------------------------------------

The UE may be configured with one or more bandwidth parts on a given
component carrier, of which only one can be active at a time, as
described in clauses 7.8 and 6.10 respectively. The active bandwidth
part defines the UE\'s operating bandwidth within the cell\'s operating
bandwidth. For initial access, and until the UE\'s configuration in a
cell is received, initial bandwidth part detected from system
information is used.

Downlink and uplink transmissions are organized into frames with 10 ms
duration, consisting of ten 1 ms subframes. Each frame is divided into
two equally-sized half-frames of five subframes each. The slot duration
is 14 symbols with Normal CP and 12 symbols with Extended CP, and scales
in time as a function of the used sub-carrier spacing so that there is
always an integer number of slots in a subframe.

Timing Advance *TA* is used to adjust the uplink frame timing relative
to the downlink frame timing.

![](media/image22.emf)

Figure 5.1-2: Uplink-downlink timing relation

Operation on both paired and unpaired spectrum is supported.