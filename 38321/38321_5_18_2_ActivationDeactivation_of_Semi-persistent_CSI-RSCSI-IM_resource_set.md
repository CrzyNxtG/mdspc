### 5.18.2 Activation/Deactivation of Semi-persistent CSI-RS/CSI-IM resource set

The network may activate and deactivate the configured Semi-persistent
CSI-RS/CSI-IM resource sets of a Serving Cell by sending the SP
CSI-RS/CSI-IM Resource Set Activation/Deactivation MAC CE described in
clause 6.1.3.12. The configured Semi-persistent CSI-RS/CSI-IM resource
sets are initially deactivated upon (re-)configuration by upper layers
and after reconfiguration with sync.

The MAC entity shall:

1\> if the MAC entity receives an SP CSI-RS/CSI-IM Resource Set
Activation/Deactivation MAC CE on a Serving Cell:

2\> indicate to lower layers the information regarding the SP
CSI-RS/CSI-IM Resource Set Activation/Deactivation MAC CE.