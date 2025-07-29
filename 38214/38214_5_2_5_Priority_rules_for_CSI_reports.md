### 5.2.5 Priority rules for CSI reports

For two overlapping PUSCHs, the priority rules in this clause are
applied for physical channels with same priority index according to
clause 9 in \[6, TS 38.213\] if a UE is not configured with *sTx-2Panel*
or a UE is configured by higher layer parameter *PDCCH-Config* that
contains two different values of *coresetPoolIndex* in different
*ControlResourceSet* in the active DL BWP and the UE is configured with
*sTx-2Panel* and the two overlapping PUSCHs are associated with same
value of *coresetPoolIndex*.

CSI reports are associated with a priority value
${Pri}_{iCSI}(y,k,c,s) = 2 \bullet N_{cells} \bullet M_{s} \bullet y + N_{cells} \bullet M_{s} \bullet k + M_{s} \bullet c + s$
where

\- ![](media/image688.wmf) for aperiodic CSI reports to be carried on
PUSCH ![](media/image689.wmf) for semi-persistent CSI reports to be
carried on PUSCH, ![](media/image690.wmf) for semi-persistent CSI
reports to be carried on PUCCH and ![](media/image691.wmf) for periodic
CSI reports to be carried on PUCCH;

\- ![](media/image692.wmf) for CSI reports carrying L1-RSRP or L1-SINR
and ![](media/image693.wmf) for CSI reports not carrying L1-RSRP or
L1-SINR;

\- *c* is the serving cell index and $N_{cells}$ is the value of the
higher layer parameter *maxNrofServingCells*;

\- for a CSI report configured with *ltm-CSI-ReportConfig*, *c* is the
serving cell index value where the report configuration is configured.

> \- *s* is the *reportConfigID* and ![](media/image694.wmf)is the value
> of the higher layer parameter *maxNrofCSI-ReportConfigurations.*

\- for a CSI report configured with *ltm-CSI-ReportConfig*, *s* is the
*ltm-CSI-ReportConfigId* and *Ms* is the value of the higher layer
parameter *maxNrofLTM-CSI-ReportConfigurations*

A first CSI report is said to have priority over second CSI report if
the associated ![](media/image695.wmf) value is lower for the first
report than for the second report.

Two CSI reports are said to collide if the time occupancy of the
physical channels scheduled to carry the CSI reports overlap in at least
one OFDM symbol and are transmitted on the same carrier. When a UE is
configured to transmit two colliding CSI reports,

\- if *y* values are different between the two CSI reports, the
following rules apply except for the case when one of the *y* value is 2
and the other *y* value is 3 (for CSI reports transmitted on PUSCH, as
described in Clause 5.2.3; for CSI reports transmitted on PUCCH, as
described in Clause 5.2.4):

\- The CSI report with higher $\text{Pri}_{iCSI}^{}(y,k,c,s)$ value
shall not be sent by the UE.

\- otherwise, the two CSI reports are multiplexed or either is dropped
based on the priority values, as described in Clause 9.2.5.2 in \[6, TS
38.213\].

A CSI report configured with *ltm-CSI-ReportConfig* has a higher
priority over all CSI report(s) configured with *CSI-ReportConfig*
irrespective of $\text{Pri}_{iCSI}^{}(y,k,c,s)$ value in case of
collision with CSI report(s) configured with *CSI-ReportConfig.*

If a semi-persistent CSI report to be carried on PUSCH overlaps in time
with PUSCH data transmission in one or more symbols on the same carrier,
and if the earliest symbol of these PUSCH channels starts no earlier
than N~2~+d~2,1~ symbols after the last symbol of the DCI scheduling the
PUSCH where d~2,1~ is the maximum of the d~2,1~ associated with the
PUSCH carrying semi-persistent CSI report and the PUSCH with data
transmission, the CSI report shall not be transmitted by the UE.
Otherwise, if the timeline requirement is not satisfied this is an error
case.

If a UE would transmit a first PUSCH that includes semi-persistent CSI
reports and a second PUSCH that includes an UL-SCH on the same carrier,
and the first PUSCH transmission would overlap in time with the second
PUSCH transmission, the UE does not transmit the first PUSCH and
transmits the second PUSCH. The UE expects that the first and second
PUSCH transmissions satisfy the above timing conditions for PUSCH
transmissions that overlap in time when at least one of the first or
second PUSCH transmissions is in response to a DCI format detection by
the UE.