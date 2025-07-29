### 16.3.1 General Principles and Requirements

In this clause, the general principles and requirements related to the
realization of network slicing in the NG-RAN for NR connected to 5GC and
for E-UTRA connected to 5GC are given.

A network slice always consists of a RAN part and a CN part. The support
of network slicing relies on the principle that traffic for different
slices is handled by different PDU sessions. Network can realise the
different network slices by scheduling and also by providing different
L1/L2 configurations.

Each network slice is uniquely identified by a S-NSSAI, as defined in TS
23.501 \[3\]. NSSAI (Network Slice Selection Assistance Information)
includes one or a list of S-NSSAIs (Single NSSAI) where a S-NSSAI is a
combination of:

\- mandatory SST (Slice/Service Type) field, which identifies the slice
type and consists of 8 bits (with range is 0-255);

\- optional SD (Slice Differentiator) field, which differentiates among
Slices with same SST field and consist of 24 bits.

The list includes at most 8 S-NSSAI(s).

The UE provides NSSAI (Network Slice Selection Assistance Information)
for network slice selection in *RRCSetupComplete*, if it has been
provided by NAS (see clause 9.2.1.3). While the network can support
large number of slices (hundreds), the UE need not support more than 8
slices simultaneously. A BL UE or a NB-IoT UE supports a maximum of 8
slices simultaneously.

Network Slicing is a concept to allow differentiated treatment depending
on each customer requirements. With slicing, it is possible for Mobile
Network Operators (MNO) to consider customers as belonging to different
tenant types with each having different service requirements that govern
in terms of what slice types each tenant is eligible to use based on
Service Level Agreement (SLA) and subscriptions.

The following key principles apply for support of Network Slicing in
NG-RAN:

**RAN awareness of slices**

\- NG-RAN supports a differentiated handling of traffic for different
network slices which have been pre-configured. How NG-RAN supports the
slice enabling in terms of NG-RAN functions (i.e. the set of network
functions that comprise each slice) is implementation dependent.

**Selection of RAN part of the network slice**

\- NG-RAN supports the selection of the RAN part of the network slice,
by NSSAI provided by the UE or the 5GC which unambiguously identifies
one or more of the pre-configured network slices in the PLMN.

**Resource management between slices**

\- NG-RAN supports policy enforcement between slices as per service
level agreements. It should be possible for a single NG-RAN node to
support multiple slices. The NG-RAN should be free to apply the best RRM
policy for the SLA in place to each supported slice.

**Support of QoS**

\- NG-RAN supports QoS differentiation within a slice, and per
Slice-Maximum Bit Rate may be enforced per UE, if feasible. How NG-RAN
enables UE-Slice-MBR enforcement and rate limitation (see TS 23.501
\[3\]) is up to network implementation.

**RAN selection of CN entity**

\- For initial attach, the UE may provide NSSAI to support the selection
of an AMF. If available, NG-RAN uses this information for routing the
initial NAS to an AMF. If the NG-RAN is unable to select an AMF using
this information or the UE does not provide any such information the
NG-RAN sends the NAS signalling to one of the default AMFs.

\- For subsequent accesses, the UE provides a Temp ID, which is assigned
to the UE by the 5GC, to enable the NG-RAN to route the NAS message to
the appropriate AMF as long as the Temp ID is valid (NG-RAN is aware of
and can reach the AMF which is associated with the Temp ID). Otherwise,
the methods for initial attach applies.

**Resource isolation between slices**

\- The NG-RAN supports resource isolation between slices. NG-RAN
resource isolation may be achieved by means of RRM policies and
protection mechanisms that should avoid that shortage of shared
resources in one slice breaks the service level agreement for another
slice. It should be possible to fully dedicate NG-RAN resources to a
certain slice. Some RACH resources can be associated to specific
NSAG(s). Other aspects how NG-RAN supports resource isolation is
implementation dependent.

**Access control**

\- By means of the unified access control (see clause 7.4),
operator-defined access categories can be used to enable differentiated
handling for different slices. NG-RAN may broadcast barring control
information (i.e. a list of barring parameters associated with
operator-defined access categories) to minimize the impact of congested
slices.

**Slice Availability and Support**

\- Some slices may be available only in part of the network. A slice is
considered available in a cell if it is supported by the TA comprising
the cell and the slice is not configured with zero resources, as
specified in TS 23.501 \[3\]. A slice is supported within a TA if the
NG-RAN has been configured to support the S-NSSAI in the TA. All
supported slices are included in the slice support list for the TA
signalled from the NG-RAN to the AMF. The NG-RAN supported S-NSSAI(s),
NSAG(s) and NSAG related information such as NSAG associated Cell
Reselection Priority and/or NSAG associated RACH resources are
configured by OAM. Awareness in the NG-RAN of the slices supported in
the cells of its neighbours may be beneficial for inter-frequency
mobility in connected mode. In order to support the NSAG, the NG-RAN
provides the AMF with the NSAG information per TA in the appropriate NG
interface management procedures, as specified in TS 38.413 \[26\].
Awareness in the NG-RAN of the NSAG information supported in the list(s)
of neighbour cells may be configured by OAM, or exchanged with neighbour
NG-RAN nodes.

\- The NG-RAN and the 5GC are responsible to handle a service request
for a slice that may or may not be available in a given area. Admission
or rejection of access to a slice may depend by factors such as support
for the slice, availability of resources, support of the requested
service by NG-RAN.

\- The NG-RAN may be signalled with the Partially Allowed NSSAI from the
AMF as specified in TS 23.501 \[3\]. The NG-RAN may decide to use the
Partially Allowed NSSAI for mobility decision.

\- Support for Network Slices with Network Slice Area of Service not
matching deployed Tracking Areas is specified in TS 23.501 \[3\]. NG-RAN
cells that are outside the Area of Service may be configured with zero
resources for the concerned slice(s). The concerned slice(s) cannot use
any dedicated, prioritized nor any shared resources of that cell.
Awareness of zero resources configured for a slice in one or more cells
may be exchanged with neighbour NG-RAN nodes for mobility reasons.

**Support for UE associating with multiple network slices
simultaneously**

\- In case a UE is associated with multiple slices simultaneously, only
one signalling connection is maintained and for intra-frequency cell
reselection, the UE always tries to camp on the best cell. For
inter-frequency cell reselection, dedicated priorities can be used to
control the frequency on which the UE camps.

**Granularity of slice awareness**

\- Slice awareness in NG-RAN is introduced at PDU session level, by
indicating the S-NSSAI corresponding to the PDU Session, in all
signalling containing PDU session resource information.

**Validation of the UE rights to access a network slice**

\- It is the responsibility of the 5GC to validate that the UE has the
rights to access a network slice. Prior to receiving the Initial Context
Setup Request message, the NG-RAN may be allowed to apply some
provisional/local policies, based on awareness of which slice the UE is
requesting access to. During the initial context setup, the NG-RAN is
informed of the slice for which resources are being requested.

**Network slice replacement**

\- NG-RAN may support network slice replacement for a PDU session as
defined in TS 23.501 \[3\].

NOTE: The resources used to serve the alternative slice may be subject
to subsequent O&M adjustments to take into account the additional load
generated by remapping of one or more slices into the alternative
S-NSSAI, if this alternative slice is not member of the same
*RRMPolicyRatio* (see TS 28.541 \[49\]) as the original slice.