### 5.18.23 Unified TCI States Activation/Deactivation MAC CE

The network may activate and deactivate the configured unified TCI
states of a Serving Cell or a set of Serving Cells configured in
*simultaneousU-TCI-UpdateList1*, *simultaneousU-TCI-UpdateList2*,
*simultaneousU-TCI-UpdateList3* or *simultaneousU-TCI-UpdateList4* by
sending the Unified TCI States Activation/Deactivation MAC CE described
in clause 6.1.3.47. The configured unified TCI states are initially
deactivated upon (re-)configuration by upper layers and after
reconfiguration with sync.

The MAC entity shall:

1\> if the MAC entity receives a Unified TCI States
Activation/Deactivation MAC CE on a Serving Cell:

2\> indicate to lower layers the information regarding the Unified TCI
States Activation/Deactivation MAC CE.