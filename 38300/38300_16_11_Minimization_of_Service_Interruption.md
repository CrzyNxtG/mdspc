## 16.11 Minimization of Service Interruption

In case of a disaster, a radio access network can experience outage,
which can result in that UEs belonging to the network experience service
interruptions. For this scenario, another network not affected by the
disaster, which during non-disaster situations is considered by the UEs
as a forbidden network, can allow roaming of the UEs belonging to the
network experiencing such disaster service interruptions. Such roaming
is referred to as disaster roaming. This is further described in clause
5.40 of TS 23.501 \[3\] and 3.10 of TS 23.122 \[47\].

To allow such disaster roaming, a cell can broadcast a list of PLMNs
with disaster conditions for which disaster roaming is offered. Disaster
roaming service is provided only for the area that covers the area with
disaster condition.

Further, to be able to control the load that disaster roaming UEs put on
a cell, the cell can broadcast access control parameters applicable
specifically for disaster roaming UEs. Access attempts of disaster
roaming UEs are based on Access Identity 3. The network can for example
set the access control parameters for Access Identity 3 so that access
attempts of disaster roaming UEs are more likely to be barred compared
to non-disaster roaming UEs.