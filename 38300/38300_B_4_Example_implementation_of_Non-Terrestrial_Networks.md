# B.4 Example implementation of Non-Terrestrial Networks

The following figure illustrates an example implementation of a
Non-Terrestrial Network for transparent NTN payload:

![](media/image121.emf)

Figure B.4-1: NTN based NG-RAN

The gNB depicted in Figure B.4-1 may be subdivided into non-NTN
infrastructure gNB functions and the NTN Service Link provisioning
system. The NTN infrastructure may be thought of being subdivided into
the NTN Service Link provisioning system and the NTN Control function.
The NTN Service Link provisioning system may consist of one or more NTN
payloads and NTN Gateways.

The NTN payload is embarked on a spaceborne (or airborne) vehicle,
providing a structure, power, commanding, telemetry, attitude control
for the satellite (resp. HAPS) and possibly an appropriate thermal
environment, radiation shielding.

The NTN Service Link provisioning system maps the NR-Uu radio protocol
over radio resources of the NTN infrastructure (e.g. beams, channels, Tx
power).

The NTN control function controls the spaceborne (or airborne) vehicles
as well as the radio resources of the NTN infrastructure (NTN payload(s)
& NTN Gateway(s)). It provides control data, e.g. Ephemeris, to the
non-NTN infrastructure gNB functions of the gNB.

Provision of NTN control data to the gNB is out of 3GPP scope.

NOTE: The transport of NR-Uu protocol between the NTN Service Link
provisioning system and the non-NTN infrastructure gNB functions is out
of 3GPP scope.

At least the following NTN related parameters are expected to be
provided by O&M to the gNB for its operation:

a\) Earth-fixed beams: for each beam provided by a given NTN-payload:

\- The Cell identifier (NG and Uu) mapped to the beam;

\- The Cell\'s reference location (e.g. cell\'s center and range).

b\) Quasi-Earth-fixed: for each beam provided by a given NTN payload:

> \- The Cell identifier (NG and Uu) and time window mapped to a beam;
>
> \- The Cell\'s/beam\'s reference location (e.g. cell\'s center and
> range);

\- The time window of the successive switch overs (feeder link, service
link);

\- The identifier and time window of all serving satellites (resp. HAPS)
and NTN Gateways.

c\) Earth moving beams: for each beam provided by a given NTN payload:

> \- The Uu Cell identifier mapped to a beam and mapping information to
> fixed geographical areas reported on NG, including information about
> the beams direction and motion of the beam\'s foot print on Earth;

\- Its elevation wrt NTN payload;

\- Schedule of successive serving NTN Gateways/gNBs;

\- Schedule of successive switch overs (feeder link, service link).

The NTN related parameters provided by O&M to the CN for UE location
verification is specified in TS 38.305 \[42\].