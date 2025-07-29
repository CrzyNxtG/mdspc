### 21.2.2 QoE Measurement Collection Deactivation

The QoE Measurement Collection deactivation permanently stops all or
some of the QoE measurement collection configurations at a UE, resulting
in the release of the corresponding QoE measurement configuration(s) in
the UE. QoE Measurement Collection deactivation is initiated by the OAM
towards the gNB (via the core network in case of a signalling-based QoE
measurement configuration). For a signalling-based QoE measurement
configuration, the deactivation of QoE measurement collection is
supported by using UE-associated NGAP signalling. A list of QoE
references is used to deactivate the corresponding QoE measurement
collection(s).

Upon reception of the QoE release message for an application layer
measurement configuration, the UE deletes the application layer
measurement configuration at the application layer and the associated
parameters in the UE Access Stratum and discards any unsent application
layer measurement reports corresponding to the released application
layer configuration. The UE discards the reports received from the
application layer when it has no associated application layer
measurement configuration configured.

The network can replace a QoE measurement configuration with another one
by releasing an existing QoE measurement configuration and configuring
another QoE measurement configuration. The network is not expected to
release a signalling-based QoE measurement configuration for the sake of
configuring a new management-based QoE measurement configuration.