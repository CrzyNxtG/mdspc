### 9.2.4 Measurements

In RRC_CONNECTED, the UE measures multiple beams (at least one) of a
cell and the measurements results (power values) are averaged to derive
the cell quality. In doing so, the UE is configured to consider a subset
of the detected beams. Filtering takes place at two different levels: at
the physical layer to derive beam quality and then at RRC level to
derive cell quality from multiple beams. Cell quality from beam
measurements is derived in the same way for the serving cell(s) and for
the non-serving cell(s). Measurement reports may contain the measurement
results of the *X* best beams if the UE is configured to do so by the
gNB.

The corresponding high-level measurement model is described below:

![](media/image50.emf)

Figure 9.2.4-1: Measurement Model

NOTE 1: K beams correspond to the measurements on SSB or CSI-RS
resources configured for L3 mobility by gNB and detected by UE at L1.

\- **A**: measurements (beam specific samples) internal to the physical
layer.

\- **Layer 1 filtering**: internal layer 1 filtering of the inputs
measured at point A. Exact filtering is implementation dependent. How
the measurements are actually executed in the physical layer by an
implementation (inputs A and Layer 1 filtering) is not constrained by
the standard.

\- **A^1^**: measurements (i.e. beam specific measurements) reported by
layer 1 to layer 3 after layer 1 filtering.

**- Beam Consolidation/Selection**: beam specific measurements are
consolidated to derive cell quality. The behaviour of the Beam
consolidation/selection is standardised and the configuration of this
module is provided by RRC signalling. Reporting period at B equals one
measurement period at A^1^.

**- B**: a measurement (i.e. cell quality) derived from beam-specific
measurements reported to layer 3 after beam consolidation/selection.

\- **Layer 3 filtering for cell quality**: filtering performed on the
measurements provided at point B. The behaviour of the Layer 3 filters
is standardised and the configuration of the layer 3 filters is provided
by RRC signalling. Filtering reporting period at C equals one
measurement period at B.

\- **C**: a measurement after processing in the layer 3 filter. The
reporting rate is identical to the reporting rate at point B. This
measurement is used as input for one or more evaluation of reporting
criteria.

\- **Evaluation of reporting criteria**: checks whether actual
measurement reporting is necessary at point D. The evaluation can be
based on more than one flow of measurements at reference point C e.g. to
compare between different measurements. This is illustrated by input C
and C^1^. The UE shall evaluate the reporting criteria at least every
time a new measurement result is reported at point C, C^1^. The
reporting criteria are standardised and the configuration is provided by
RRC signalling (UE measurements).

\- **D**: measurement report information (message) sent on the radio
interface.

\- **L3 Beam filtering**: filtering performed on the measurements (i.e.
beam specific measurements) provided at point A^1^. The behaviour of the
beam filters is standardised and the configuration of the beam filters
is provided by RRC signalling. Filtering reporting period at E equals
one measurement period at A^1^.

\- **E**: a measurement (i.e. beam-specific measurement) after
processing in the beam filter. The reporting rate is identical to the
reporting rate at point A^1^. This measurement is used as input for
selecting the X measurements to be reported.

\- **Beam Selection for beam reporting**: selects the X measurements
from the measurements provided at point E. The behaviour of the beam
selection is standardised and the configuration of this module is
provided by RRC signalling.

\- **F**: beam measurement information included in measurement report
(sent) on the radio interface.

Layer 1 filtering introduces a certain level of measurement averaging.
How and when the UE exactly performs the required measurements is
implementation specific to the point that the output at B fulfils the
performance requirements set in TS 38.133 \[13\]. Layer 3 filtering for
cell quality and related parameters used are specified in TS 38.331
\[12\] and do not introduce any delay in the sample availability between
B and C. Measurement at point C, C^1^ is the input used in the event
evaluation. L3 Beam filtering and related parameters used are specified
in TS 38.331 \[12\] and do not introduce any delay in the sample
availability between A^1^ and E.

Measurement reports are characterized by the following:

\- Measurement reports include the measurement identity of the
associated measurement configuration that triggered the reporting;

\- Cell and beam measurement quantities to be included in measurement
reports are configured by the network;

\- The number of non-serving cells to be reported can be limited through
configuration by the network;

\- Cells belonging to an exclude-list configured by the network are not
used in event evaluation and reporting, and conversely when an
allow-list is configured by the network, only the cells belonging to the
allow-list are used in event evaluation and reporting;

\- Beam measurements to be included in measurement reports are
configured by the network (beam identifier only, measurement result and
beam identifier, or no beam reporting).

Intra-frequency neighbour (cell) measurements and inter-frequency
neighbour (cell) measurements are defined as follows:

\- SSB based intra-frequency measurement: a measurement is defined as an
SSB based intra-frequency measurement provided the SSB frequency
configured in the measurement object associated with the serving cell
and the center frequency of the SSB of the neighbour cell are the same,
and the subcarrier spacing of the two SSBs is also the same.

\- SSB based inter-frequency measurement: a measurement is defined as an
SSB based inter-frequency measurement provided the center frequency of
the SSB of the serving cell and the center frequency of the SSB of the
neighbour cell are different, or the subcarrier spacing of the two SSBs
is different.

NOTE 2: For SSB based measurements, one measurement object corresponds
to one SSB and the UE considers different SSBs as different cells.

NOTE 2a: If a UE is configured to perform serving cell measurements
based on an NCD-SSB configured in its active BWP, this NCD-SSB is
considered as the SSB of the serving cell in the definition of
intra-frequency and inter-frequency measurements as above.

\- CSI-RS based intra-frequency measurement: a measurement is defined as
a CSI-RS based intra-frequency measurement provided that:

\- The subcarrier spacing of CSI-RS resources on the neighbour cell
configured for measurement is the same as the SCS of CSI-RS resources on
the serving cell indicated for measurement; and

\- For 60kHz subcarrier spacing, the CP type of CSI-RS resources on the
neighbour cell configured for measurement is the same as the CP type of
CSI-RS resources on the serving cell indicated for measurement; and

\- The centre frequency of CSI-RS resources on the neighbour cell
configured for measurement is the same as the centre frequency of CSI-RS
resource on the serving cell indicated for measurement.

\- CSI-RS based inter-frequency measurement: a measurement is defined as
a CSI-RS based inter-frequency measurement if it is not a CSI-RS based
intra-frequency measurement.

NOTE 3: Extended CP for CSI-RS based measurement is not supported in
this release.

Whether a measurement is non-gap-assisted or gap-assisted depends on the
capability of the UE, the active BWP of the UE and the current operating
frequency:

\- For SSB based inter-frequency measurement, if the measurement gap
requirement information is reported by the UE, a measurement gap
configuration may be provided according to the information. Otherwise, a
measurement gap configuration is always provided in the following cases:

\- If the UE only supports per-UE measurement gaps;

\- If the UE supports per-FR measurement gaps and any of the serving
cells are in the same frequency range of the measurement object.

\- For SSB based intra-frequency measurement, if the measurement gap
requirement information is reported by the UE, a measurement gap
configuration may be provided according to the information. Otherwise, a
measurement gap configuration is always provided in the following case:

\- If the serving cell is associated with SSB, other than the initial
BWP, if any of the UE configured BWPs do not contain the frequency
domain resources of the SSB associated to the initial DL BWP, and are
not configured with NCD-SSB for serving cell measurement;

\- If the serving cell is not associated with SSB (i.e. SSB-less SCell),
if the initial BWP or any of the UE configured BWPs do not contain the
SSB frequency configured in the measurement object associated with the
serving cell, and are not configured with NCD-SSB for serving cell
measurement.

\- For CSI-RS based intra-frequency measurement, no measurement gap is
needed;

\- For CSI-RS based inter-frequency measurement, a measurement gap
configuration is always provided in the following cases:

\- If the UE only supports per-UE measurement gaps;

\- If the UE supports per-FR measurement gaps and any of the serving
cells are in the same frequency range of the measurement object.

In non-gap-assisted scenarios, the UE shall be able to carry out such
measurements without measurement gaps. In gap-assisted scenarios, the UE
cannot be assumed to be able to carry out such measurements without
measurement gaps.

Network may request the UE to measure NR and/or E-UTRA carriers in
RRC_IDLE or RRC_INACTIVE via system information or via dedicated
measurement configuration in *RRCRelease*. If the UE was configured to
perform measurements of NR and/or E-UTRA carriers while in RRC_IDLE or
in RRC_INACTIVE, it may provide an indication of the availability of
corresponding measurement results to the gNB in the *RRCSetupComplete*
message. The network may request the UE to report those measurements
after security activation. The request for the measurements can be sent
by the network immediately after transmitting the Security Mode Command
(i.e. before the reception of the Security Mode Complete from the UE).

If the UE was configured to perform measurements of NR and/or E-UTRA
carriers while in RRC_INACTIVE, the gNB can request the UE to provide
corresponding measurement results in the *RRCResume* message and then
the UE can include the available measurement results in the
*RRCResumeComplete* message. Alternatively, the UE may provide an
indication of the availability of the measurement results to the gNB in
the *RRCResumeComplete* message and the gNB can then request the UE to
provide these measurement results.