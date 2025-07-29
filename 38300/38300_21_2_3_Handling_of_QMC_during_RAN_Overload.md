### 21.2.3 Handling of QMC during RAN Overload

The QoE measurement reporting pause/resume procedure is used to
pause/resume reporting of one or multiple QoE measurement configurations
in a UE in RAN overload situation.

The gNB can use the *RRCReconfiguration* message to temporarily stop the
UE from sending application layer measurement reports associated with
one or multiple application layer measurement configurations. When the
UE receives the QoE measurement reporting pause indication, the UE
temporarily stores application layer measurement reports in the AS
layer. When the UE receives the QoE measurement reporting resume
indication, the UE sends the stored application layer measurement
reports to the gNB.

For a QoE measurement configuration, the assistance information provided
by the OAM may be considered by the gNB for deciding whether to
pause/resume the QoE measurement reporting for certain QoE measurement
configurations in case of RAN overload.