### 5.18.6 Activation/Deactivation of Semi-persistent CSI reporting on PUCCH

The network may activate and deactivate the configured Semi-persistent
CSI reporting on PUCCH of a Serving Cell by sending the SP CSI reporting
on PUCCH Activation/Deactivation MAC CE described in clause 6.1.3.16 or
the Enhanced SP CSI reporting on PUCCH Activation/Deactivation MAC CE
described in clause 6.1.3.80. The network may activate and deactivate at
least one of the configured sub-configuration of a configured
Semi-Persistent CSI reporting on PUCCH of a Serving Cell by sending the
Enhanced SP CSI reporting on PUCCH Activation/Deactivation MAC CE
described in clause 6.1.3.80. For each Semi-persistent CSI reporting on
PUCCH configuration configured with *csi-ReportSubConfigToAddModList*,
the network may deactivate all configured sub-configurations by sending
the SP CSI reporting on PUCCH Activation/Deactivation MAC CE. The
configured Semi-persistent CSI reporting on PUCCH is initially
deactivated upon (re-)configuration by upper layers and after
reconfiguration with sync.

The MAC entity shall:

1\> if the MAC entity receives an SP CSI reporting on PUCCH
Activation/Deactivation MAC CE or an Enhanced SP CSI reporting on PUCCH
Activation/Deactivation MAC CE on a Serving Cell:

2\> indicate to lower layers the information regarding the SP CSI
reporting on PUCCH Activation/Deactivation MAC CE or the Enhanced SP CSI
reporting on PUCCH Activation/Deactivation MAC CE.