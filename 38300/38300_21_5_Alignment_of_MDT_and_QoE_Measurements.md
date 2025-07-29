## 21.5 Alignment of MDT and QoE Measurements

The radio-related measurements may be collected via immediate MDT for
all types of supported services for the purpose of QoE analysis. The
MCE/TCE performs the correlation of the immediate MDT measurement
results and the QoE measurement results collected at the same UE.

The following is supported:

\- Alignment between a signalling-based QoE measurement and a
signalling-based MDT measurement. In this case, the signalling-based QoE
configuration sent to the gNB includes the NG-RAN Trace ID of the
signalling-based MDT measurement.

\- Alignment between a management-based QoE measurement and a
management-based MDT measurement.

The UE configured with QoE measurements sends an indication to inform
the gNB about the start or the stop of a QoE measurement session of
configured QoE measurements. The gNB can activate the MDT measurements
that are to be aligned with the QoE measurements performed by the UE
upon/after receiving the QoE measurement session start indication from
the UE. The gNB may activate the MDT measurements upon/after receiving
the MDT activation message from the OAM. The gNB can deactivate the
aligned MDT measurements according to an OAM command which may, e.g., be
triggered by the session stop indication.

The gNB includes time stamp information to the QoE measurement reports
to enable the correlation of corresponding measurement results of MDT
and QoE at the MCE/TCE. In addition, the gNB includes the MDT session
identifiers (Trace Reference and Trace Recording Session Reference) in
the corresponding QoE measurement report.

21.6 QoE Measurement Collection in High Mobility Scenarios

QoE measurements can be confined to high mobility state of the UE and/or
to HSDN cells.

21.7 Void