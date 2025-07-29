### 16.14.10 Verification of UE location

The core network may trigger a network verification procedure for a UE
in RRC_CONNECTED to verify it is consistent with the network-based
assessed location. It is up to network implementation how to handle UEs
which does not support the location verification.

For UE location verification based on multi-RTT with single satellite in
NTN, at least the following UE and gNB measurements specified in TS
38.215 \[59\] are reported: gNB receive-transmit time difference at the
uplink time synchronization reference point, UE receive-transmit time
difference, UE receive-transmit time difference subframe offset and DL
timing drift.

The assistance information provided to the CN may include ephemeris
information including accurate satellite position and velocity at the
time of multi-RTT measurement, and common TA parameters (*ta-Common*,
*ta-CommonDrift*, *ta-CommonDriftVariant*), and Epoch time.