## 10.1 Basic Scheduler Operation

In order to utilise radio resources efficiently, MAC in gNB includes
dynamic resource schedulers that allocate physical layer resources for
the downlink and the uplink. In this clause, an overview of the
scheduler is given in terms of scheduler operation, signalling of
scheduler decisions, and measurements.

Scheduler Operation:

\- Taking into account the UE buffer status and the QoS requirements of
each UE and associated radio bearers, schedulers assign resources
between UEs;

\- Schedulers may assign resources taking account the radio conditions
at the UE identified through measurements made at the gNB and/or
reported by the UE;

\- Resource assignment consists of radio resources (resource blocks).

Signalling of Scheduler Decisions:

\- UEs identify the resources by receiving a scheduling (resource
assignment) channel.

Measurements to Support Scheduler Operation:

\- Uplink buffer status reports (measuring the data that is buffered in
the logical channel queues in the UE) are used to provide support for
QoS-aware packet scheduling;

\- Power headroom reports (measuring the difference between the nominal
UE maximum transmit power and the estimated power for uplink
transmission) are used to provide support for power aware packet
scheduling.