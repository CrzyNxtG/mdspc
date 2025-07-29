### 5.18.8 Activation/Deactivation of spatial relation of PUCCH resource

The network may activate and deactivate a spatial relation for a PUCCH
resource of a Serving Cell by sending the PUCCH spatial relation
Activation/Deactivation MAC CE described in clause 6.1.3.18. The network
may also activate and deactivate a spatial relation for a PUCCH resource
or a PUCCH resource group of a Serving Cell by sending the Enhanced
PUCCH spatial relation Activation/Deactivation MAC CE described in
clause 6.1.3.25. The configured spatial relation for a PUCCH resource is
initially deactivated upon (re-)configuration by upper layers and after
reconfiguration with sync. The network may also activate and deactivate
the two spatial relations for a PUCCH resource or a PUCCH resource group
of a Serving Cell by sending the PUCCH spatial relation
Activation/Deactivation for multiple TRP PUCCH repetition MAC CE
described in clause 6.1.3.45.

The MAC entity shall:

1\> if the MAC entity receives a PUCCH spatial relation
Activation/Deactivation MAC CE on a Serving Cell:

2\> indicate to lower layers the information regarding the PUCCH spatial
relation Activation/Deactivation MAC CE.

1\> if the MAC entity receives an Enhanced PUCCH spatial relation
Activation/Deactivation MAC CE on a Serving Cell:

2\> indicate to lower layers the information regarding the Enhanced
PUCCH spatial relation Activation/Deactivation MAC CE.

1\> if the MAC entity receives a PUCCH spatial relation
Activation/Deactivation for multiple TRP PUCCH repetition MAC CE on a
Serving Cell:

2\> indicate to lower layers the information regarding the PUCCH spatial
relation Activation/Deactivation for multiple TRP PUCCH repetition MAC
CE.