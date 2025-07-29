## 21.4 RAN Visible QoE Measurements

RAN visible QoE measurements are configured at the UE by the gNB, where
a subset of configured QoE metrics is reported from the UE to the gNB as
an explicit IE readable by the gNB. The RAN visible QoE measurements can
be used by the gNB for network optimization. The RAN visible QoE
measurements are supported for the DASH streaming and VR services. The
gNB configures the RAN visible QoE measurement of all or some of the
available RAN visible QoE metrics, where the indication of metric
availability is received by the gNB as part of the management-based or
the signalling-based QoE configuration. The set of available RAN visible
QoE metrics is a subset of the metrics configured as part of QoE
measurement configuration encapsulated in the application layer
measurement configuration container. RAN visible QoE measurements and
encapsulated QoE measurements can be configured together or separately.
RAN visible QoE measurements can only be configured if there is a
corresponding QoE measurement configuration for the same service type
configured at the UE. The gNB may modify a RAN visible QoE configuration
by releasing it and configuring the UE with a new RAN visible QoE
configuration pertaining to the same QoE reference. In this case, the
new RAN visible QoE configuration applies immediately, i.e., even during
the same application session.

Multiple simultaneous RAN visible QoE measurement configurations and
reports can be supported for RAN visible QoE measurements, and each RAN
visible QoE measurement configuration and report is identified by the
same measurement configuration application layer ID as the corresponding
QoE measurement configuration and measurement report. After receiving
the RAN visible QoE measurement configuration, the UE AS layer forwards
the configuration to the application layer, indicating the service type,
the measurement configuration application layer ID and, optionally, the
reporting periodicity for RAN visible QoE. The application layer sends
the RAN visible QoE measurement report associated with the measurement
configuration application layer ID to the UE\'s AS layer. The PDU
session ID(s) and QoS Flow ID(s) per PDU session ID corresponding to the
service that is subject to QoE measurements can also be reported by the
UE along with the RAN visible QoE measurement results.

The RAN visible QoE measurements can be reported with a reporting
periodicity different from the one of the corresponding encapsulated QoE
measurements, when a dedicated RAN visible QoE reporting periodicity is
configured by the gNB. The UE application layer can measure the RAN
visible QoE metrics based on this reporting periodicity. If there is no
reporting periodicity defined in the RAN visible QoE configuration, the
UE sends both RAN visible QoE measurement reports and the QoE
measurement reports to the gNB in the same *MeasurementReportAppLayer*
message, except when QoE measurement reporting pause indication is
received (e.g., in case of RAN overload). When a QoE measurement
reporting is paused, if there is no reporting periodicity defined in the
RAN visible QoE configuration, the encapsulated QoE reports are stored
at the UE\'s AS layer, but the RAN visible QoE reports continue to be
reported to the gNB with the reporting periodicity configured for
encapsulated QoE reporting.

The gNB can release one or multiple RAN visible QoE measurement
configurations from the UE in one *RRCReconfiguration* message at any
time. If the encapsulated QoE configuration is released, the
corresponding RAN visible QoE configuration is released as well.

The RAN visible QoE configuration can be transferred from the source gNB
to the target gNB upon mobility and from the old gNB to the new gNB
during context retrieval. The target gNB or the new gNB can generate a
new RAN visible QoE configuration based on the available RAN visible QoE
metrics received and it can send the new RAN visible QoE configuration
to the UE during handover or the RRC resume procedure.