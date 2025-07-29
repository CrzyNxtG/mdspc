### 16.22.2 Identification, access and camping restrictions

A UE capability indicates that the UE is a 2Rx XR UE. A 2Rx XR UE does
not identify itself in Msg1 or Msg3 during RACH procedure.

Network indicates whether access to a cell by 2Rx XR UEs is barred via
system information. For a cell that operates in a frequency band where
4Rx antenna ports are mandated, presence of this indication in its
system information indicates that the cell does not allow 2Rx XR UEs. In
addition, an IFRI specific for 2Rx XR UEs can be provided in system
information. Information on which neighbour frequencies 2Rx XR UEs are
allowed to access can be provided in system information.

NOTE: It is up to the E-UTRA network, if possible, to avoid handover
attempts of a 2Rx XR UE to a target NR cell not allowing 2Rx XR UEs as
specified in TS 36.300 \[2\]. It is up to UE implementation, if
possible, to recover from handover attempts to a target NR cell not
allowing 2Rx XR UEs.