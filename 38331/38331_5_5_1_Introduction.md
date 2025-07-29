### 5.5.1 Introduction

The network may configure an RRC_CONNECTED UE to perform measurements.
The network may configure the UE to report them in accordance with the
measurement configuration or perform conditional reconfiguration
evaluation in accordance with the conditional reconfiguration. The
measurement configuration is provided by means of dedicated signalling
i.e. using the *RRCReconfiguration* or *RRCResume.*

The network may configure the UE to perform the following types of
measurements:

\- NR measurements;

\- Inter-RAT measurements of E-UTRA frequencies;

\- Inter-RAT measurements of UTRA-FDD frequencies;

\- NR sidelink measurements of L2 U2N Relay UEs.

The network may configure the UE to report the following measurement
information based on SS/PBCH block(s):

\- Measurement results per SS/PBCH block;

\- Measurement results per cell based on SS/PBCH block(s);

\- SS/PBCH block(s) indexes.

The network may configure the UE to report the following measurement
information based on CSI-RS resources:

\- Measurement results per CSI-RS resource;

\- Measurement results per cell based on CSI-RS resource(s);

\- CSI-RS resource measurement identifiers.

The network may configure the UE to perform the following types of
measurements for NR sidelink and V2X sidelink:

\- CBR measurements.

The network may configure the UE to report the following CLI measurement
information based on SRS resources:

\- Measurement results per SRS resource;

\- SRS resource(s) indexes.

The network may configure the UE to report the following CLI measurement
information based on CLI-RSSI resources:

\- Measurement results per CLI-RSSI resource;

\- CLI-RSSI resource(s) indexes.

The network may configure the UE to report the following Rx-Tx time
difference measurement information based on CSI-RS for tracking or PRS:

\- UE Rx-Tx time difference measurement result.

The measurement configuration includes the following parameters:

**1. Measurement objects:** A list of objects on which the UE shall
perform the measurements.

\- For intra-frequency and inter-frequency measurements a measurement
object indicates the frequency/time location and subcarrier spacing of
reference signals to be measured. Associated with this measurement
object, the network may configure a list of cell specific offsets, a
list of \'exclude-listed\' cells and a list of \'allow-listed\' cells.
Exclude-listed cells are not applicable in event evaluation or
measurement reporting. Allow-listed cells are the only ones applicable
in event evaluation or measurement reporting.

\- The *measObjectId* of the MO which corresponds to each serving cell
is indicated by *servingCellMO* within the serving cell configuration.

\- For inter-RAT E-UTRA measurements a measurement object is a single
E-UTRA carrier frequency. Associated with this E-UTRA carrier frequency,
the network can configure a list of cell specific offsets and a list of
\'exclude-listed\' cells. Exclude-listed cells are not applicable in
event evaluation or measurement reporting.

\- For inter-RAT UTRA-FDD measurements a measurement object is a set of
cells on a single UTRA-FDD carrier frequency.

\- For NR sidelink measurements of L2 U2N Relay UEs, a measurement
object is a single NR sidelink frequency to be measured.

\- For CBR measurement of NR sidelink communication, a measurement
object is a set of transmission resource pool(s) on a single carrier
frequency for NR sidelink communication.

\- For CBR measurement of NR sidelink discovery, a measurement object is
a set of discovery dedicated resource pool(s) or transmission resource
pool(s) also used for NR sidelink discovery on a single carrier
frequency for NR sidelink discovery.

\- For CBR measurement of NR sidelink positioning, a measurement object
is a set of positioning dedicated resource pool(s) or transmission
resource pool(s) also used for NR sidelink positioning on a single
carrier frequency for NR sidelink positioning.

\- For CLI measurements a measurement object indicates the
frequency/time location of SRS resources and/or CLI-RSSI resources, and
subcarrier spacing of SRS resources to be measured.

**2. Reporting configurations:** A list of reporting configurations
where there can be one or multiple reporting configurations per
measurement object. Each measurement reporting configuration consists of
the following:

\- Reporting criterion: The criterion that triggers the UE to send a
measurement report. This can either be periodical or a single event
description.

\- RS type: The RS that the UE uses for beam and cell measurement
results (SS/PBCH block or CSI-RS).

\- Reporting format: The quantities per cell and per beam that the UE
includes in the measurement report (e.g. RSRP) and other associated
information such as the maximum number of cells and the maximum number
beams per cell to report.

In case of conditional reconfiguration, each configuration consists of
the following:

\- Execution criteria: The criteria the UE uses for conditional
reconfiguration execution.

\- RS type: The RS that the UE uses for obtaining beam and cell
measurement results (SS/PBCH block-based or CSI-RS-based), used for
evaluating conditional reconfiguration execution condition.

**3. Measurement identities:** For measurement reporting, a list of
measurement identities where each measurement identity links one
measurement object with one reporting configuration. By configuring
multiple measurement identities, it is possible to link more than one
measurement object to the same reporting configuration, as well as to
link more than one reporting configuration to the same measurement
object. The measurement identity is also included in the measurement
report that triggered the reporting, serving as a reference to the
network. For conditional reconfiguration triggering, one measurement
identity links to exactly one conditional reconfiguration trigger
configuration. And up to 2 measurement identities can be linked to one
conditional reconfiguration execution condition.

**4. Quantity configurations:** The quantity configuration defines the
measurement filtering configuration used for all event evaluation and
related reporting, and for periodical reporting of that measurement. For
NR measurements, the network may configure up to 2 quantity
configurations with a reference in the NR measurement object to the
configuration that is to be used. In each configuration, different
filter coefficients can be configured for different measurement
quantities, for different RS types, and for measurements per cell and
per beam.

**5. Measurement gaps:** Periods that the UE may use to perform
measurements.

**6. Effective measurement window:** Periods that the UE may use to
perform inter RAT measurements.

A UE in RRC_CONNECTED maintains a measurement object list, a reporting
configuration list, and a measurement identities list according to
signalling and procedures in this specification. The measurement object
list possibly includes NR measurement object(s), CLI measurement
object(s), inter-RAT objects, and L2 U2N Relay objects. Similarly, the
reporting configuration list includes NR, inter-RAT, and L2 U2N Relay
reporting configurations. Any measurement object can be linked to any
reporting configuration of the same RAT type. Some reporting
configurations may not be linked to a measurement object. Likewise, some
measurement objects may not be linked to a reporting configuration.

The measurement procedures distinguish the following types of cells:

1\. The NR serving cell(s) -- these are the SpCell and one or more
SCells.

2\. Listed cells -- these are cells listed within the measurement
object(s).

3\. Detected cells -- these are cells that are not listed within the
measurement object(s) but are detected by the UE on the SSB
frequency(ies) and subcarrier spacing(s) indicated by the measurement
object(s).

For NR measurement object(s), the UE measures and reports on the serving
cell(s)/serving Relay UE (for L2 U2N Remote UE), listed cells and/or
detected cells. For inter-RAT measurements object(s) of E-UTRA, the UE
measures and reports on listed cells and detected cells and, for RSSI
and channel occupancy measurements, the UE measures and reports on the
configured resources on the indicated frequency. For inter-RAT
measurements object(s) of UTRA-FDD, the UE measures and reports on
listed cells. For CLI measurement object(s), the UE measures and reports
on configured measurement resources (i.e. SRS resources and/or CLI-RSSI
resources). For L2 U2N Relay object(s), the UE measures and reports on
the serving NR cell(s), as well as the discovered L2 U2N Relay UEs.

Whenever the procedural specification, other than contained in clause
5.5.2, refers to a field it concerns a field included in the
*VarMeasConfig* unless explicitly stated otherwise i.e. only the
measurement configuration procedure covers the direct UE action related
to the received *measConfig*.

In NR-DC, the UE may receive two independent *measConfig*:

\- a *measConfig*, associated with MCG, that is included in the
*RRCReconfiguration* message received via SRB1; and

\- a *measConfig*, associated with SCG, that is included in the
*RRCReconfiguration* message received via SRB3, or, alternatively,
included within a *RRCReconfiguration* message embedded in a
*RRCReconfiguration* message received via SRB1.

In this case, the UE maintains two independent *VarMeasConfig* and
*VarMeasReportList*, one associated with each *measConfig*, and
independently performs all the procedures in clause 5.5 for each
*measConfig* and the associated *VarMeasConfig* and *VarMeasReportList*,
unless explicitly stated otherwise.

The configurations related to CBR measurements are only included in the
*measConfig* associated with MCG.

The configurations related to Rx-Tx time difference measurement are only
included in the *measConfig* associated with MCG.