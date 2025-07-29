## 21.3 QoE Measurement Continuity for Mobility

QoE measurement collection continuity for intra-system
intra-RAT/inter-RAT handover is supported, with the Area Scope
parameters configured by the OAM, where the network is responsible for
keeping track of whether the UE is inside or outside the area scope. A
UE continues an ongoing QoE measurement even if it leaves the area
scope, unless the network indicates to the UE to release the application
layer measurement configuration.

For handover, the source gNB may transmit the information related to one
or more application layer measurement configurations of the UE to the
target gNB via XnAP or NGAP. For signalling-based QoE, the service type
indication, the QoE reference, and, optionally, the container for
application layer measurement configuration, MCE IP address, measurement
configuration application layer ID, MDT alignment information, area
scope, slice support list for QMC, available RAN visible QoE metrics,
QoE measurement session status, MBS communication service type, and
assistance information for QoE measurement are passed to the target gNB.
For management-based QoE, the QoE reference, service type indication,
and, optionally, the measurement configuration application layer ID, the
MCE IP address, area scope, slice support list for QMC, MBS
communication service type, assistance information for QoE measurement
and QoE measurement session status are passed to the target gNB. For
RRC_INACTIVE state mobility, QoE measurement configuration(s) of a
specific UE can be retrieved from the gNB hosting the UE context when
the UE resumes to the RRC_CONNECTED state.

For signalling-based QoE, at handover to a target gNB that supports QoE
measurement collection, the target gNB decides which of the application
layer measurement configurations should be kept and which should be
released, e.g., based on application layer measurement configuration
information received from the source gNB in Xn/NG signalling.

When the UE is handed over to a target gNB that does not support QMC,
the UE releases all configured application layer measurement
configurations.

The continuity of QoE measurement configuration and reporting in NR-DC
scenario is supported as specified in TS 37.340 \[21\].

QoE measurement collection continuity for intra-system inter-RAT
handover is supported.

For intra-5GC handover from a source gNB to a target ng-eNB,
measurements continuity for only one QoE measurement configuration can
be supported when the UE connects to the target ng-eNB. The source gNB
decides which QoE measurement to keep and sends the information about
this QoE measurement to the target ng-eNB. The UE releases all NR QoE
configuration(s) and it applies the LTE QoE configuration, if received
from the target ng-eNB.

For intra-5GC handover from a source ng-eNB to a target gNB, the UE
releases the LTE QoE configuration and it applies the NR QoE
configuration(s), if received from the target gNB.