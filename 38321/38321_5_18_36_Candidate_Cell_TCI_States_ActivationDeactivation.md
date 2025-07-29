### 5.18.36 Candidate Cell TCI States Activation/Deactivation

The network may activate and deactivate the TCI states of LTM candidate
cell(s) configured in *CandidateTCI-State and CandidateTCI-UL-State* by
sending the Candidate Cell TCI States Activation/Deactivation MAC CE
described in clause 6.1.3.76. The network deactivates the TCI state(s)
for one LTM candidate cell by not including the corresponding TCI state
ID field(s) in the Candidate Cell TCI States Activation/Deactivation MAC
CE. The configured candidate cell TCI states are initially deactivated
upon (re-)configuration by upper layer and after reconfiguration with
sync that is not triggered by LTM.

The MAC entity shall:

1\> if the MAC entity receives a Candidate Cell TCI States
Activation/Deactivation MAC CE on a Serving Cell:

2\> indicate to lower layers the information regarding the Candidate
Cell TCI States Activation/Deactivation MAC CE.