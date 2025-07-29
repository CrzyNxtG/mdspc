## 7.5 UE Capability Retrieval framework

The UE reports its UE radio access capabilities which are static at
least when the network requests. The gNB can request what capabilities
for the UE to report based on band information. The UE capability can be
represented by a capability ID, which may be exchanged in NAS signalling
over the air and in network signalling instead of the UE capability
structure.

In IAB, it is optional for an IAB-MT to support UE capability Retrieval
framework and the related signalling. In case IAB-MT does not support UE
capability Retrieval framework, IAB-MT capabilities are assumed to be
known to the network by other means, e.g. OAM.