## 9.1 Overview

Load balancing is achieved in NR with handover, redirection mechanisms
upon RRC release and through the usage of inter-frequency and inter-RAT
absolute priorities and inter-frequency Qoffset parameters.

Measurements to be performed by a UE for connected mode mobility are
classified in at least four measurement types:

\- Intra-frequency NR measurements;

\- Inter-frequency NR measurements;

\- Inter-RAT measurements for E-UTRA;

\- Inter-RAT measurements for UTRA.

For each measurement type one or several measurement objects can be
defined (a measurement object defines e.g. the carrier frequency to be
monitored).

For each measurement object one or several reporting configurations can
be defined (a reporting configuration defines the reporting criteria).
Three reporting criteria are used: event triggered reporting, periodic
reporting and event triggered periodic reporting.

The association between a measurement object and a reporting
configuration is created by a measurement identity (a measurement
identity links together one measurement object and one reporting
configuration of the same RAT). By using several measurement identities
(one for each measurement object, reporting configuration pair) it is
then possible to:

\- Associate several reporting configurations to one measurement object
and;

\- Associate one reporting configuration to several measurement objects.

The measurements identity is used as well when reporting results of the
measurements.

Measurement quantities are considered separately for each RAT.

Measurement commands are used by NG-RAN to order the UE to start, modify
or stop measurements.

Handover can be performed within the same RAT and/or CN, or it can
involve a change of the RAT and/or CN.

Inter system fallback towards E-UTRAN is performed when 5GC does not
support emergency services, voice services, for load balancing etc.
Depending on factors such as CN interface availability, network
configuration and radio conditions, the fallback procedure results in
either RRC_CONNECTED state mobility (handover procedure) or RRC_IDLE
state mobility (redirection), see TS 23.501 \[3\] and TS 38.331 \[12\].

SRVCC from 5G to UTRAN, if supported by both the UE and the network, may
be performed to handover a UE with an ongoing voice call from NR to
UTRAN. The overall procedure is described in TS 23.216 \[34\]. See also
TS 38.331 \[12\] and TS 38.413 \[26\].

In the NG-C signalling procedure, the AMF based on support for emergency
services, voice service, any other services or for load balancing etc,
may indicate the target CN type as EPC or 5GC to the gNB node. When the
target CN type is received by gNB, the target CN type is also conveyed
to the UE in *RRCRelease* Message.

Inter-gNB CSI-RS based mobility, i.e. handover, is supported between two
neighbour gNBs by enabling that neighbour gNBs can exchange and forward
their own CSI-RS configurations and on/off status.