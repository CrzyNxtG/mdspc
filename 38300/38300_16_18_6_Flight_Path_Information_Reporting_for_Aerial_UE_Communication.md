### 16.18.6 Flight Path Information Reporting for Aerial UE Communication

NG-RAN can request the Aerial UE to report flight path information based
on the indication from the Aerial UE that flight path information is
available or without such indication from the Aerial UE. Flight path
information consists of a number of waypoints defined as 3D locations,
as defined in TS 37.355 \[43\]. Aerial UE reports up to a configured
number of waypoints if flight path information is available at the UE.
The report can also contain a time stamp per waypoint if configured by
the NG-RAN and if available at the UE.

The flight path information can be also provided by the source gNB to
the target gNB during handover. If configured by the NG-RAN and if the
associated distance- or time-based condition (see
*flightPathUpdateDistanceThr* and *flightPathUpdateTimeThr* in TS 38.331
\[12\], respectively) for indication reporting are met for any of the
waypoints, the Aerial UE indicates the availability of the updated
flight path information. The Aerial UE can also indicate the
availability of the updated flight path information if a new waypoint
has been added or if a future waypoint has been removed from the flight
path information.