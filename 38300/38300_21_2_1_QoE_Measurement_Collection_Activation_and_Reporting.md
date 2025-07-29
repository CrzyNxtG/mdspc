### 21.2.1 QoE Measurement Collection Activation and Reporting

The feature is activated in the gNB either by direct configuration from
the OAM system (management-based activation), or by signalling from the
OAM via the 5GC (signalling-based activation), containing UE-associated
QoE configuration. One or more QoE measurement collection configurations
can be activated at a UE per service type, and each QoE measurement
configuration is uniquely identified by a QoE reference.

For signalling-based QoE measurements, the OAM initiates the QMC
activation for a specific UE via the 5GC, and the gNB receives one or
more QoE measurement configurations by means of UE-associated
signalling. The QoE measurement configuration for signalling-based QMC
activation includes an application layer measurement configuration list
and the corresponding information for QoE measurement collection, e.g.,
QoE reference, service type, MCE IP address, slice scope, area scope,
MDT alignment information, the indication of available RAN visible QoE
metrics and assistance information.

For management-based QMC activation, the OAM sends one or more QoE
measurement configurations directly to the gNB. The QoE measurement
configuration for management-based QMC activation also includes an
application layer measurement configuration list and the corresponding
information for QoE measurement collection. The gNB selects UE(s) that
have the required QoE measurement capability, and that meet the
measurement collection criteria related to area scope and slice scope.

An application layer measurement configuration received by the gNB from
the OAM or from the 5GC is encapsulated in a transparent container,
which is forwarded to a UE as *measConfigAppLayerContainer* in the
*RRCReconfiguration* message (there can be multiple configurations in
the same message). Application layer measurement reports received from
UE\'s application layer are encapsulated in a transparent container and
sent to the network in the *MeasurementReportAppLayer* message, as
specified in TS 38.331 \[12\]. The UE can send multiple application
layer measurement reports to the gNB in one *MeasurementReportAppLayer*
message. In order to allow the transmission of application layer
measurement reports which exceed the maximum PDCP SDU size, segmentation
of the *MeasurementReportAppLayer* message may be enabled by the gNB. A
measurement configuration application layer ID conveyed in the RRC
signalling is used to identify the application layer measurement
configuration and report between the gNB and the UE. The measurement
configuration application layer ID is mapped to the QoE reference in the
gNB, and the gNB forwards the application layer measurement report to
MCE together with the QoE reference. The gNB can release one or multiple
application layer measurement configurations from the UE in one
*RRCReconfiguration* message at any time. The UE may additionally be
configured by the gNB to indicate to the gNB when a QoE measurement
session starts or stops for a certain application layer measurement
configuration.

For a QoE measurement configuration, assistance information provided by
OAM can be considered by the gNB for configuring a UE with a priority
value. The priority value can be used by the UE to discard QoE
measurement reports, as specified in TS 38.331 \[12\].