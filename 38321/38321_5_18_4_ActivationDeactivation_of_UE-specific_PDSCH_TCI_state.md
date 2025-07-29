### 5.18.4 Activation/Deactivation of UE-specific PDSCH TCI state

The network may activate and deactivate the configured TCI states for
PDSCH of a Serving Cell or a set of Serving Cells configured in
*simultaneousTCI-UpdateList1* or *simultaneousTCI-UpdateList2* by
sending the TCI States Activation/Deactivation for UE-specific PDSCH MAC
CE described in clause 6.1.3.14. The network may activate and deactivate
the configured TCI states for a codepoint of the DCI *Transmission
configuration indication* field as specified in TS 38.212 \[9\] for
PDSCH of a Serving Cell by sending the Enhanced TCI States
Activation/Deactivation for UE-specific PDSCH MAC CE described in clause
6.1.3.24. The configured TCI states for PDSCH are initially deactivated
upon (re-)configuration by upper layers and after reconfiguration with
sync.

The MAC entity shall:

1\> if the MAC entity receives a TCI States Activation/Deactivation for
UE-specific PDSCH MAC CE on a Serving Cell:

2\> indicate to lower layers the information regarding the TCI States
Activation/Deactivation for UE-specific PDSCH MAC CE.

1\> if the MAC entity receives an Enhanced TCI States
Activation/Deactivation for UE-specific PDSCH MAC CE on a Serving Cell:

2\> indicate to lower layers the information regarding the Enhanced TCI
States Activation/Deactivation for UE-specific PDSCH MAC CE.