### 5.18.5 Indication of TCI state for UE-specific PDCCH

The network may indicate a TCI state for PDCCH reception for a CORESET
of a Serving Cell or a set of Serving Cells configured in
*simultaneousTCI-UpdateList1* or *simultaneousTCI-UpdateList2* by
sending the TCI State Indication for UE-specific PDCCH MAC CE described
in clause 6.1.3.15 or the cross-RRH TCI State Indication for UE-specific
PDCCH MAC CE described in clause 6.1.3.77. The network may also indicate
two TCI states for PDCCH reception for a CORESET of a Serving Cell or a
set of Serving Cells configured in *simultaneousTCI-UpdateList1* or
*simultaneousTCI-UpdateList2* by sending the Enhanced TCI States
Indication for UE-specific PDCCH MAC CE described in clause 6.1.3.44.

The MAC entity shall:

1\> if the MAC entity receives a TCI State Indication for UE-specific
PDCCH MAC CE on a Serving Cell:

2\> indicate to lower layers the information regarding the TCI State
Indication for UE-specific PDCCH MAC CE.

1\> if the MAC entity receives an Enhanced TCI States Indication for
UE-specific PDCCH MAC CE on a Serving Cell:

2\> indicate to lower layers the information regarding the Enhanced TCI
States Indication for UE-specific PDCCH MAC CE.

1\> if the MAC entity receives a cross-RRH TCI State Indication for
UE-specific PDCCH MAC CE on a Serving Cell:

2\> indicate to lower layers the information regarding the cross-RRH TCI
State Indication for UE-specific PDCCH MAC CE.