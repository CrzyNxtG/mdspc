### 21.2.4 QoE Measurement Handling in RRC_IDLE and RRC_INACTIVE States

If the UE enters RRC_INACTIVE, the UE AS configuration for the QoE is
stored in the UE Inactive AS context.

If the UE enters RRC_IDLE state, the UE releases all application layer
measurement configurations except the application layer configurations
explicitly indicated by the gNB as applicable in RRC_IDLE and
RRC_INACTIVE states.

For QoE measurement sessions pertaining to data flows received via MBS
broadcast, QoE measurement collection may continue during the
RRC_INACTIVE and RRC_IDLE.

Upon UE\'s transition from RRC_IDLE to RRC_CONNECTED, the gNB serving
the UE should ensure that it does not release an already configured
signalling-based QoE measurement configuration for the sake of
configuring a new management-based QoE measurement configuration.

QoE measurements for ongoing sessions should be continued when switching
between 5GC Shared MBS traffic delivery and 5GC Individual MBS traffic
delivery modes for MBS multicast.

When the UE resumes the connection with a gNB that does not support QMC,
the UE releases all configured application layer measurement
configurations.

For application measurement configurations applicable in RRC_IDLE and
RRC_INACTIVE states, the UE continues on-going QoE measurement
collection when entering RRC_IDLE or RRC_INACTIVE state, and also when
returning to RRC_CONNECTED state. The UE may also start QoE collection
according to the stored QoE configuration while in RRC_IDLE or
RRC_INACTIVE state. The UE keeps the application layer measurement
configurations but does not start new QoE measurement sessions when it
is outside of the area scope for QoE configurations in RRC_IDLE and/or
RRC_INACTIVE state. The UE stores the application layer measurement
reports generated while in RRC_IDLE and/or RRC_INACTIVE state in the AS
layer. The gNB can retrieve the application layer measurement
reports/configurations and session status indication by configuring SRB4
or SRB5 after it receives an indication of application layer measurement
report/configuration availability. The UE can send to the gNB the
application layer measurement reports buffered when in RRC_IDLE and/or
RRC_INACTIVE state, only when the UE has moved to RRC_CONNECTED state
due to other reasons. The UE should not transit from RRC_IDLE or
RRC_INACTIVE state to RRC_CONNECTED state for the sole purpose of
sending stored application layer measurement reports.

For the application measurement configurations applicable in RRC_IDLE
state (i.e. for MBS broadcast service), the gNB that configures the QoE
measurement collection also indicates to the UE the QoE reference, MCE
ID, service type, area scope, QMC assistance information (i.e.,
*appLayerMeasPriority* in TS 38.331 \[12\]), QoE measurement type
(signalling-based or management-based measurement), and available RVQoE
metrics, per QoE reference. The UE stores the received information
including the QoE reference, measurement configuration application layer
ID, MCE ID, service type, area scope, QMC assistance information (i.e.,
*appLayerMeasPriority* in TS 38.331 \[12\]), QoE measurement type, and
available RVQoE metrics, per QoE reference when entering RRC_IDLE. Upon
UE\'s transition from RRC_IDLE to RRC_CONNECTED, the UE indicates the
stored information to the new serving gNB, and the new serving gNB can
use the information when managing the QoE configurations including
configuring, releasing, updating the QoE configuration, and receiving
and forwarding the QoE reports buffered in RRC_IDLE.