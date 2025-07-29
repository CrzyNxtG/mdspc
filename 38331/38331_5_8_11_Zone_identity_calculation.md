### 5.8.11 Zone identity calculation

The UE shall determine an identity of the zone (i.e. Zone_id) in which
it is located using the following formulae, if *sl-ZoneConfig* is
configured:

*x*~1~= Floor (*x* / *L*) Mod 64;

*y*~1~= Floor (*y* / *L*) Mod 64;

Zone_id = *y*~1~ \* 64 + *x*~1~.

The parameters in the formulae are defined as follows:

**L** is the value of *sl-ZoneLength* included in *sl-ZoneConfig*;

**x** is the geodesic distance in longitude between UE\'s current
location and geographical coordinates (0, 0) according to WGS84 model
\[58\] and it is expressed in meters;

**y** is the geodesic distance in latitude between UE\'s current
location and geographical coordinates (0, 0) according to WGS84 model
\[58\] and it is expressed in meters.

NOTE: How the calculated zone_id is used is specified in TS 38.321
\[3\].