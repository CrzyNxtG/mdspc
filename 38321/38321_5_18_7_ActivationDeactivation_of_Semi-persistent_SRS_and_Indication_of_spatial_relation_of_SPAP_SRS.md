### 5.18.7 Activation/Deactivation of Semi-persistent SRS and Indication of spatial relation of SP/AP SRS

The network may activate and deactivate the configured Semi-persistent
SRS resource sets of a Serving Cell by sending the SP SRS
Activation/Deactivation MAC CE described in clause 6.1.3.17. The network
may also activate and deactivate the configured Semi-persistent SRS
resource sets of a Serving Cell by sending the Enhanced SP/AP SRS
Spatial Relation Indication MAC CE described in clause 6.1.3.26. The
network may also activate and deactivate the configured Semi-persistent
SRS resource sets of a Serving Cell by sending the SP/AP SRS TCI State
Indication MAC CE described in clause 6.1.3.59. The configured
Semi-persistent SRS resource sets are initially deactivated upon
(re-)configuration by upper layers and after reconfiguration with sync.
The network may indicate the spatial relation info of SP/AP SRS resource
sets of a Serving Cell by sending the Enhanced SP/AP SRS spatial
relation Indication MAC CE described in clause 6.1.3.26.

The MAC entity shall:

1\> if the MAC entity receives an SP SRS Activation/Deactivation MAC CE
on a Serving Cell:

2\> indicate to lower layers the information regarding the SP SRS
Activation/Deactivation MAC CE.

1\> if the MAC entity receives an Enhanced SP/AP SRS Spatial Relation
Indication MAC CE on a Serving Cell:

2\> indicate to lower layers the information regarding the Enhanced
SP/AP SRS Spatial Relation Indication MAC CE.

1\> if the MAC entity receives an SP/AP SRS TCI State Indication MAC CE
on a Serving Cell:

2\> indicate to lower layers the information regarding the SP/AP SRS TCI
State Indication MAC CE.