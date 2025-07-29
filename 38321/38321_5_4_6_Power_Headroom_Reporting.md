### 5.4.6 Power Headroom Reporting

The Power Headroom reporting procedure is used to provide the serving
gNB with the following information:

\- Type 1 power headroom: the difference between the nominal UE maximum
transmit power and the estimated power for UL-SCH transmission per
activated Serving Cell;

\- Type 2 power headroom: the difference between the nominal UE maximum
transmit power and the estimated power for UL-SCH and PUCCH transmission
on SpCell of the other MAC entity (i.e. E-UTRA MAC entity in EN-DC,
NE-DC, and NGEN-DC cases);

\- Type 3 power headroom: the difference between the nominal UE maximum
transmit power and the estimated power for SRS transmission per
activated Serving Cell;

\- MPE P-MPR: the power backoff to meet the MPE FR2 requirements for a
Serving Cell operating on FR2;

\- DPC: the adjustment to maximum output power for a given power class
for a Serving Cell operating on FR1;

\- DPC~BC~: the adjustment to maximum output power for a given power
class for a Band Combination operating on FR1.

RRC controls Power Headroom reporting by configuring the following
parameters:

\- *dpc-Reporting-FR1*;

\- *phr-AssumedPUSCH-Reporting*;

\- *phr-PeriodicTimer*;

\- *phr-ProhibitTimer*;

\- *phr-Tx-PowerFactorChange*;

\- *phr-Type2OtherCell*;

\- *phr-ModeOtherCG*;

\- *multiplePHR*;

\- *mpe-Reporting-FR2*;

\- *mpe-ProhibitTimer*;

\- *mpe-Threshold*;

\- *numberOfN*;

\- *mpe-ResourcePoolToAddModList*;

\- *twoPHRMode*.

A Power Headroom Report (PHR) shall be triggered if any of the following
events occur:

\- *phr-ProhibitTimer* expires or has expired and the path loss has
changed more than *phr-Tx-PowerFactorChange* dB for at least one RS used
as pathloss reference for one activated Serving Cell of any MAC entity
of which the active DL BWP is not dormant BWP since the last
transmission of a PHR in this MAC entity when the MAC entity has UL
resources for new transmission;

NOTE 1: The path loss variation for one cell assessed above is between
the pathloss measured at present time on the current pathloss reference
and the pathloss measured at the transmission time of the last
transmission of PHR on the pathloss reference in use at that time,
irrespective of whether the pathloss reference has changed in between.
The current pathloss reference for this purpose does not include any
pathloss reference configured using *pathlossReferenceRS-Pos* in TS
38.331 \[5\].

\- *phr-PeriodicTimer* expires;

\- upon configuration or reconfiguration of the power headroom reporting
functionality by upper layers, which is not used to disable the
function;

\- activation of an SCell of any MAC entity with configured uplink of
which *firstActiveDownlinkBWP-Id* is not set to dormant BWP;

\- activation of an SCG;

\- addition of the PSCell except if the SCG is deactivated (i.e. PSCell
is newly added or changed);

\- *phr-ProhibitTimer* expires or has expired, when the MAC entity has
UL resources for new transmission, and the following is true for any of
the activated Serving Cells of any MAC entity with configured uplink:

\- there are UL resources allocated for transmission or there is a PUCCH
transmission on this cell, and the required power backoff due to power
management (as allowed by P-MPR~c~ as specified in TS 38.101-1 \[14\],
TS 38.101-2 \[15\], and TS 38.101-3 \[16\]) for this cell has changed
more than *phr-Tx-PowerFactorChange* dB since the last transmission of a
PHR when the MAC entity had UL resources allocated for transmission or
PUCCH transmission on this cell.

\- Upon switching of activated BWP from dormant BWP to non-dormant DL
BWP of an SCell of any MAC entity with configured uplink;

\- if *dpc-Reporting-FR1* is configured, ΔP~PowerClass~
/ΔP~PowerClass,\ CA~/ΔP~PowerClass,\ EN-DC~/ΔP~PowerClass,\ NR-DC~
reporting is triggered upon uplink duty cycle exceedance or upon return
to the power class after the duty cycle exceedance, as specified in TS
38.101-1 \[14\] and TS 38.101-3 \[16\]).

\- if *mpe-Reporting-FR2* is configured, and *mpe-ProhibitTimer* is not
running:

\- the measured P-MPR applied to meet FR2 MPE requirements as specified
in TS 38.101-2 \[15\] is equal to or larger than *mpe-Threshold* for at
least one activated FR2 Serving Cell since the last transmission of a
PHR in this MAC entity; or

\- the measured P-MPR applied to meet FR2 MPE requirements as specified
in TS 38.101-2 \[15\] has changed more than *phr-Tx-PowerFactorChange*
dB for at least one activated FR2 Serving Cell since the last
transmission of a PHR due to the measured P-MPR applied to meet MPE
requirements being equal to or larger than *mpe-Threshold* in this MAC
entity.

in which case the PHR is referred below to as \'MPE P-MPR report\'.

NOTE 2: The MAC entity should avoid triggering a PHR when the required
power backoff due to power management decreases only temporarily (e.g.
for up to a few tens of milliseconds) and it should avoid reflecting
such temporary decrease in the values of P~CMAX,f,c~/PH when a PHR is
triggered by other triggering conditions.

NOTE 3: If a HARQ process is configured with *cg-RetransmissionTimer*
and if the PHR is already included in a MAC PDU for transmission on
configured grant by this HARQ process, but not yet transmitted by lower
layers, it is up to UE implementation how to handle the PHR content.

If the MAC entity has UL resources allocated for a new transmission the
MAC entity shall:

1\> if it is the first UL resource allocated for a new transmission
since the last MAC reset:

2\> start *phr-PeriodicTimer*.

1\> if the Power Headroom reporting procedure determines that at least
one PHR has been triggered and not cancelled; and

1\> if the allocated UL resources can accommodate the MAC CE for PHR
which the MAC entity is configured to transmit, plus its subheader, as a
result of LCP as defined in clause 5.4.3.1:

2\> if *multiplePHR* with value *true* is configured:

3\> for each activated Serving Cell with configured uplink associated
with any MAC entity of which the active DL BWP is not dormant BWP; and

3\> for each activated Serving Cell with configured uplink associated
with E-UTRA MAC entity:

4\> if this MAC entity is configured with *twoPHRMode*:

5\> if this Serving Cell is configured with *multipanelSchemeSDM* or
*multipanelSchemeSFN* and the MAC entity this Serving Cell belongs to is
configured with *twoPHRMode*:

6\> if the UE supports *mTRP-PUSCH-PHR-Type1-Reporting-r17*:

7\> obtain two values of the Type 1 power headroom for the corresponding
uplink carrier as specified in clause 7.7 of TS 38.213 \[6\] for NR
Serving Cell.

6\> else:

7\> obtain two values of the Type 1 power headroom for the corresponding
uplink carrier as specified in clause 7.7 of TS 38.213 \[6\] for NR
Serving Cell.

5\> else if this Serving Cell is configured with multiple TRP PUSCH
repetition (i.e., not configured with *multipanelSchemeSDM* or
*multipanelSchemeSFN*) and the MAC entity this Serving Cell belongs to
is configured with *twoPHRMode*:

> 6\> obtain two values of the Type 1 or the value of Type 3 power
> headroom for the corresponding uplink carrier as specified in clause
> 7.7 of TS 38.213 \[6\] for NR Serving Cell.

5\> else:

> 6\> obtain the value of the Type 1 or Type 3 power headroom for the
> corresponding uplink carrier as specified in clause 7.7 of TS 38.213
> \[6\] for NR Serving Cell and clause 5.1.1.2 of TS 36.213 \[17\] for
> E-UTRA Serving Cell.

4\> else (i.e. this MAC entity is not configured with *twoPHRMode*):

5\> if this Serving Cell is configured with multiple TRP PUSCH
repetition or *multipanelSchemeSDM* or *multipanelSchemeSFN* and if the
MAC entity this Serving Cell belongs to is configured with *twoPHRMode*:

6\> if there is at least one real PUSCH transmission at the slot where
the PHR MAC CE is transmitted:

7\> if this Serving Cell is configured with *multipanelSchemeSDM* or
*multipanelSchemeSFN*:

8\> if the first *TCI-State* or *TCI-UL-State* is applied for a real
PUSCH transmission:

9\> obtain the value of the Type 1 power headroom of the real PUSCH
transmission associated with the first *TCI-State* or *TCI-UL-State* for
the corresponding uplink carrier as specified in clause 7.7 of TS
38.213\[6\] for NR Serving Cell.

8\> else:

9\> obtain the value of the Type 1 power headroom of the real PUSCH
transmission associated with the second *TCI-State* or *TCI-UL-State*
for the corresponding uplink carrier as specified in clause 7.7 of TS
38.213\[6\] for NR Serving Cell.

7\> else if this Serving Cell is configured with multiple TRP PUSCH
repetition:

8\> obtain the value of the Type 1 power headroom of the first real
transmission of the corresponding uplink carrier as specified in clause
7.7 of TS 38.213\[6\] for NR Serving Cell.

6\> else if there is no real PUSCH transmission at the slot where the
PHR MAC CE is transmitted:

7\> if this Serving Cell is configured with *multipanelSchemeSDM* or
*multipanelSchemeSFN*:

8\> obtain the value of the Type 1 power headroom of the reference PUSCH
transmission associated with the first *TCI-State* or *TCI-UL-State* for
the corresponding uplink carrier as specified in clause 7.7 of TS
38.213\[6\] for NR Serving Cell.

7\> else if this Serving Cell is configured with multiple TRP PUSCH
repetition:

8\> if the UE supports *mTRP-PUSCH-PHR-Type1-Reporting-r17*:

9\> obtain the value of the Type 1 power headroom of the reference PUSCH
transmission associated with the *SRS-ResourceSet* with a lower
*SRS-resourceSetID* for the corresponding uplink carrier as specified in
clause 7.7 of TS 38.213\[6\] for NR Serving Cell.

8\> else:

9\> obtain the value of the Type 1 power headroom of the reference PUSCH
transmission associated with the *SRS-ResourceSet* with a lower
*SRS-resourceSetID* or the value of the Type 3 power headroom for the
corresponding uplink carrier as specified in clause 7.7 of TS
38.213\[6\] for NR Serving Cell.

5\> else:

6\> obtain the value of the Type 1 or Type 3 power headroom for the
corresponding uplink carrier as specified in clause 7.7 of TS 38.213
\[6\] for NR Serving Cell and clause 5.1.1.2 of TS 36.213 \[17\] for
E-UTRA Serving Cell.

4\> if this MAC entity is configured with *phr-AssumedPUSCH-Reporting*:

5\> if this MAC entity has UL resources allocated for transmission on
this Serving Cell; or

5\> if the other MAC entity, if configured, has UL resources allocated
for transmission on this Serving Cell and *phr-ModeOtherCG* is set to
*real* by upper layers:

6\> if *dynamicTransformPrecoderFieldPresenceDCI-0-1-r18* or
*dynamicTransformPrecoderFieldPresenceDCI-0-2-r18* is set to *enabled*
in the active BWP of this Serving Cell:

7\> obtain the value for the corresponding P~CMAX,f,c~ field for assumed
PUSCH from the physical layer if available, as specified in clause 7.7
of TS 38.213 \[6\].

6\> obtain the value for the corresponding P~CMAX,f,c~ field from the
physical layer.

6\> if *mpe-Reporting-FR2* is configured and this Serving Cell operates
on FR2 and this Serving Cell is associated to this MAC entity:

7\> obtain the value for the corresponding MPE field from the physical
layer.

4\> else (i.e. if this MAC entity is not configured with
*phr-AssumedPUSCH-Reporting*):

5\> if this MAC entity is configured with *twoPHRMode* and any Serving
Cell belonging to this MAC entity is configured with
*multipanelSchemeSDM* or *multipanelSchemeSFN*; and

5\> if this Serving Cell is configured with *multipanelSchemeSDM* or
*multipanelSchemeSFN* and the MAC entity this Serving Cell belongs to is
configured with *twoPHRMode*:

6\> obtain two values for the corresponding P~CMAX,f,c,k~ fields from
the physical layer.

6\> if *mpe-Reporting-FR2* is configured for the MAC entity this Serving
Cell belongs to and this Serving Cell operates on FR2:

7\> obtain two values for the corresponding MPE~k~ fields from the
physical layer.

5\> else if this MAC entity is not configured with *twoPHRmode*, or if
this MAC entity is configured with *twoPHRMode* and any Serving Cell
belonging to this MAC entity is configured with multiple TRP PUSCH
repetition; and

5\> if this Serving Cell is configured with *multipanelSchemeSDM* or
*multipanelSchemeSFN* and the MAC entity this Serving Cell belongs to is
configured with *twoPHRMode*:

6\> if the first *TCI-State* or *TCI-UL-State* is applied for a real
PUSCH transmission at the slot where the PHR MAC CE is transmitted:

7\> obtain the value for the P~CMAX,f,c~ field for the PUSCH
transmission associated to the first *TCI-State* or *TCI-UL-State* from
the physical layer.

7\> if *mpe-Reporting-FR2* is configured for the MAC entity this Serving
Cell belongs to and this Serving Cell operates on FR2:

8\> obtain the value for the corresponding MPE field for the PUSCH
transmission associated to the first *TCI-State* or *TCI-UL-State* from
the physical layer.

6\> else if the second *TCI-State* or *TCI-UL-State* is applied for a
real PUSCH transmission at the slot where the PHR MAC CE is transmitted:

7\> obtain the value for the P~CMAX,f,c~ field for the PUSCH
transmission associated to the second *TCI-State* or *TCI-UL-State* from
the physical layer.

7\> if *mpe-Reporting-FR2* is configured for the MAC entity this Serving
Cell belongs to and this Serving Cell operates on FR2:

8\> obtain the value for the corresponding MPE field for the PUSCH
transmission associated to the second *TCI-State* or *TCI-UL-State* from
the physical layer.

5\> else:

6\> if this MAC entity has UL resources allocated for transmission on
this Serving Cell; or

6\> if the other MAC entity, if configured, has UL resources allocated
for transmission on this Serving Cell and *phr-ModeOtherCG* is set to
*real* by upper layers:

7\> obtain the value for the corresponding P~CMAX,f,c~ field from the
physical layer.

7\> if *mpe-Reporting-FR2* is configured and this Serving Cell operates
on FR2 and this Serving Cell is associated to this MAC entity:

8\> obtain the value for the corresponding MPE field from the physical
layer.

7\> if *mpe-Reporting-FR2-r17* is configured and this Serving Cell
operates on FR2 and this Serving Cell is associated to this MAC entity:

8\> obtain the value for the corresponding MPE~i~ field from the
physical layer;

8\> obtain the value for the corresponding Resource~i~ field from the
physical layer.

7\> if *dpc-Reporting-FR1* is configured and ΔP~PowerClass~
/ΔP~PowerClass,\ CA~/ΔP~PowerClass,\ EN-DC~/ΔP~PowerClass,\ NR-DC~
reporting is triggered and this Serving Cell operates on FR1 and this
Serving Cell is associated to this MAC entity:

8\> obtain the value for the corresponding DPC field(s) from the
physical layer.

3\> if *phr-Type2OtherCell* with value *true* is configured:

4\> if the other MAC entity is E-UTRA MAC entity:

5\> obtain the value of the Type 2 power headroom for the SpCell of the
other MAC entity (i.e. E-UTRA MAC entity);

5\> if *phr-ModeOtherCG* is set to *real* by upper layers:

6\> obtain the value for the corresponding P~CMAX,f,c~ field for the
SpCell of the other MAC entity (i.e. E-UTRA MAC entity) from the
physical layer.

3\> if this MAC entity is configured with *mpe-Reporting-FR2-r17*:

4\> instruct the Multiplexing and Assembly procedure to generate and
transmit the Enhanced Multiple entry PHR as defined in clause 6.1.3.49
based on the values reported by the physical layer.

3\> else if this MAC entity is configured with *twoPHRMode* and any
Serving Cell belonging to this MAC entity is configured with
*multipanelSchemeSDM* or *multipanelSchemeSFN*:

4\> instruct the Multiplexing and Assembly procedure to generate and
transmit the Enhanced Multiple Entry PHR for multiple TRP STx2P MAC CE
as defined in clause 6.1.3.82 based on the values reported by the
physical layer.

3\> else if this MAC entity is configured with *twoPHRMode* and any
Serving Cell belonging to this MAC entity is configured with multiple
TRP PUSCH repetition:

4\> instruct the Multiplexing and Assembly procedure to generate and
transmit the Enhanced Multiple Entry PHR for multiple TRP MAC CE as
defined in clause 6.1.3.51 based on the values reported by the physical
layer.

3\> else if this MAC entity is configured with
*phr-AssumedPUSCH-Reporting*:

4\> instruct the Multiplexing and Assembly procedure to generate and
transmit the Multiple Entry PHR with assumed PUSCH MAC CE as defined in
clause 6.1.3.79 based on the values reported by the physical layer.

3\> else:

4\> instruct the Multiplexing and Assembly procedure to generate and
transmit the Multiple Entry PHR MAC CE as defined in clause 6.1.3.9
based on the values reported by the physical layer.

2\> else (i.e. Single Entry PHR format is used):

3\> if this MAC entity is configured with *twoPHRMode* for multiple TRP
PUSCH repetition or *multipanelSchemeSDM* or *multipanelSchemeSFN*:

4\> obtain two values of the Type 1 power headroom from the physical
layer for the corresponding uplink carrier of the PCell.

3\> else:

4\> obtain the value of the Type 1 power headroom from the physical
layer for the corresponding uplink carrier of the PCell.

3\> if this MAC entity is configured with *phr-AssumedPUSCH-Reporting*:

4\> if *dynamicTransformPrecoderFieldPresenceDCI-0-1-r18* or
*dynamicTransformPrecoderFieldPresenceDCI-0-2-r18* is set to *enabled*
in the active BWP of this Serving Cell:

5\> obtain the value for the corresponding P~CMAX,f,c~ field for assumed
PUSCH from the physical layer, if available, as specified in clause 7.7
of TS 38.213 \[6\].

> 3\> if this MAC entity is configured with *twoPHRMode* and if this
> Serving Cell is configured with *multipanelSchemeSDM* or
> *multipanelSchemeSFN*:

4\> obtain two values for the corresponding P~CMAX,f,c,k~ fields from
the physical layer.

4\> if *mpe-Reporting-FR2* is configured and this Serving Cell operates
on FR2 and this Serving Cell is associated to this MAC entity:

5\> obtain two values for the corresponding MPE~k~ fields from the
physical layer.

3\> else:

4\> obtain the value for the corresponding P~CMAX,f,c~ field from the
physical layer;

4\> if *mpe-Reporting-FR2* is configured and this Serving Cell operates
on FR2:

5\> obtain the value for the corresponding MPE field from the physical
layer.

4\> if *mpe-Reporting-FR2-r17* is configured and this Serving Cell
operates on FR2 and this Serving Cell is associated to this MAC entity:

5\> obtain the value for the corresponding MPE~i~ field from the
physical layer;

5\> obtain the value for the corresponding Resource~i~ field from the
physical layer.

4\> if *dpc-Reporting-FR1* is configured and this Serving Cell operates
on FR1:

5\> obtain the value for the corresponding DPC field from the physical
layer.

3\> if this MAC entity is configured with *mpe-Reporting-FR2-r17*:

4\> instruct the Multiplexing and Assembly procedure to generate and
transmit the Enhanced Single entry PHR as defined in clause 6.1.3.48
based on the values reported by the physical layer.

3\> else if this MAC entity is configured with *twoPHRMode* and this
Serving Cell is configured with *multipanelSchemeSDM* or
*multipanelSchemeSFN*:

4\> instruct the Multiplexing and Assembly procedure to generate and
transmit the Enhanced Single Entry PHR for multiple TRP STx2P MAC CE as
defined in clause 6.1.3.81 based on the values reported by the physical
layer.

3\> else if this MAC entity is configured with *twoPHRMode* and this
Serving Cell is configured with multiple TRP PUSCH repetition:

4\> instruct the Multiplexing and Assembly procedure to generate and
transmit the Enhanced Single Entry PHR for multiple TRP MAC CE as
defined in clause 6.1.3.50 based on the values reported by the physical
layer.

3\> else if this MAC entity is configured with
*phr-AssumedPUSCH-Reporting*:

4\> instruct the Multiplexing and Assembly procedure to generate and
transmit the Single Entry PHR with assumed PUSCH MAC CE as defined in
clause 6.1.3.78 based on the values reported by the physical layer.

3\> else:

4\> instruct the Multiplexing and Assembly procedure to generate and
transmit the Single Entry PHR MAC CE as defined in clause 6.1.3.8 based
on the values reported by the physical layer.

2\> if this PHR report is an MPE P-MPR report:

3\> start or restart the *mpe-ProhibitTimer*;

3\> cancel triggered MPE P-MPR reporting for Serving Cells included in
the PHR MAC CE.

2\> start or restart *phr-PeriodicTimer*;

2\> start or restart *phr-ProhibitTimer*;

2\> cancel all triggered PHR(s).

All triggered PHRs shall be cancelled when there is an ongoing SDT
procedure as in clause 5.27 and the UL grant(s) can accommodate all
pending data available for transmission but is not sufficient to
additionally accommodate the PHR MAC CE plus its subheader.