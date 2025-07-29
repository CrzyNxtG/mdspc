### 16.14.7 O&M Requirements

The following NTN related parameters shall be provided by O&M to the gNB
providing NTN access:

\- Ephemeris information describing the orbital trajectory information
or coordinates for the NTN payload. This information is provided on a
regular basis or upon demand to the gNB;

\- Two different sets of ephemeris format shall be supported:

\- Set 1: NTN payload position and velocity state vectors:

\- Position;

\- Velocity.

\- Set 2: At least the following parameters in orbital parameter
ephemeris format, as specified in NIMA TR 8350.2 \[51\]:

\- Semi-major axis;

\- Eccentricity;

\- Argument of periapsis;

\- Longitude of ascending node;

\- Inclination;

\- Mean anomaly at epoch time.

\- The explicit epoch time associated to ephemeris data;

\- The location of the NTN Gateways;

NOTE 1: The ephemeris of the NTN payloads and the location of the NTN
Gateways, are used at least for the Uplink timing and frequency
synchronization. It may also be used for the random access and the
mobility management purposes.

\- Additional information to enable gNB operation for feeder/service
link switch overs.

NOTE 2: The NTN related parameters provided by O&M to the gNB may depend
on the type of supported service links, i.e., Earth-fixed,
quasi-Earth-fixed, or Earth-moving.