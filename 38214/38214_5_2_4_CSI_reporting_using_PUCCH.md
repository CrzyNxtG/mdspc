### 5.2.4 CSI reporting using PUCCH

A UE is semi-statically configured by higher layers to perform periodic
CSI Reporting on the PUCCH. A UE can be configured by higher layers for
multiple periodic CSI Reports corresponding to multiple higher layer
configured CSI Reporting Settings, where the associated CSI Resource
Settings are higher layer configured. For a Reporting Setting for which
the *CSI-ReportConfig* contains a list of sub-configurations provided by
*csi-ReportSubConfigToAddModList*, CSI reporting is provided for all the
sub-configurations in each corresponding reporting instance. Periodic
CSI reporting on PUCCH formats 2, 3, 4 supports Type I CSI with wideband
granularity.

A UE shall perform semi-persistent CSI reporting on the PUCCH applied
starting from the first slot that is after slot
$n + {3N}_{slot}^{subframe,µ}$ when the UE would transmit a PUCCH with
HARQ-ACK information in slot *n* corresponding to the PDSCH carrying the
activation command described in clause 6.1.3.16 of \[10, TS 38.321\]
where *μ* is the SCS configuration for the PUCCH. The activation command
will contain one or more Reporting Settings, with or without containing
one or more sub-configurations for each Reporting Setting for which the
*CSI-ReportConfig* contains a list of sub-configurations provided by
*csi-ReportSubConfigToAddModList*, where the associated CSI Resource
Settings are configured. Semi-persistent CSI reporting on the PUCCH
supports Type I CSI. Semi-persistent CSI reporting on the PUCCH format 2
supports Type I CSI with wideband frequency granularity. Semi-persistent
CSI reporting on PUCCH formats 3 or 4 supports Type I CSI with wideband
and sub-band frequency granularities and Type II CSI Part 1.

When the PUCCH carry Type I CSI with wideband frequency granularity, the
CSI payload carried by the PUCCH format 2 and PUCCH formats 3, or 4 are
identical and the same irrespective of RI (if reported), CRI (if
reported). A CSI-ReportConfig with *codebookType* set to
\'typeI-SinglePanel\' and the corresponding CSI-RS Resource Set for
channel measurement configured with two Resource Groups and $N$ Resource
Pairs can be configured with wideband frequency granularity only with
*csi-ReportMode* set to \'Mode1\' and *numberOfSingleTRP-CSI-Mode1* set
to $X = 0$. For type I CSI sub-band reporting on PUCCH formats 3, or 4,
the payload is split into two parts. The first part contains RI (if
reported), CRI (if reported), CQI for the first codeword. The second
part contains PMI (if reported), LI (if reported) and contains the CQI
for the second codeword (if reported) when RI \> 4. For a
*CSI-ReportConfig* configured with subband reporting, *codebookType* set
to \'typeI-SinglePanel\' and the corresponding CSI-RS Resource Set for
channel measurement configured with two Resource Groups and $N$ Resource
Pairs, Part 1 contains RI(s), CRI(s), CQI(s) for the first codeword and
is zero padded to a fixed payload size (if needed). Part 2 contains the
CQI(s) for the second codeword (if reported) when RI is larger than 4,
LIs (if reported) and PMI(s). For a *CSI-ReportConfig* containing a list
of sub-configurations provided by *csi-ReportSubConfigToAddModList*, and
configured with subband reporting, for Type I CSI for one or more of the
sub-configurations, Part 1 for a sub-configuration contains
corresponding RI (if reported), CRI (if reported) and CQI for the first
codeword (if reported). Part 2 for a sub-configuration contains the
corresponding CQI for the second codeword (if reported) when RI is
larger than 4, LI (if reported) and PMI (if reported).

A semi-persistent report carried on the PUCCH formats 3 or 4 supports
Type II CSI feedback, but only Part 1 of Type II CSI feedback (See
Clause 5.2.2 and 5.2.3). Supporting Type II CSI reporting on the PUCCH
formats 3 or 4 is a UE capability *type2-SP-CSI-Feedback-LongPUCCH*. A
Type II CSI report (Part 1 only) carried on PUCCH formats 3 or 4 shall
be calculated independently of any Type II CSI reports carried on the
PUSCH (see Clause 5.2.3).

When the UE is configured with CSI Reporting on PUCCH formats 2, 3 or 4,
each PUCCH resource is configured for each candidate UL BWP.

If the UE is in an active semi-persistent CSI reporting configuration on
PUCCH and has not received a deactivation command, the CSI reporting
takes place when the BWP in which the reporting is configured to take
place is the active BWP, otherwise the CSI reporting is suspended.

A UE is not expected to report CSI with a total number of UCI bits and
CRC bits larger than 115 bits when configured with PUCCH format 4. For
CSI reports transmitted on a PUCCH, if all CSI reports consist of one
part, the UE may omit a portion of CSI reports. Omission of CSI is
according to the priority order determined from the
Pri~i,CSI~(*y,k,c,s*) value as defined in Clause 5.2.5. CSI report is
omitted beginning with the lowest priority level until the CSI report
code rate is less or equal to the one configured by the higher layer
parameter *maxCodeRate*.

If any of the CSI reports consist of two parts, the UE may omit a
portion of Part 2 CSI. Omission of Part 2 CSI is according to the
priority order shown in Table 5.2.3-1. For a Reporting Setting for which
the *CSI-ReportConfig* contains a list of sub-configurations provided by
*csi-ReportSubConfigToAddModList*, for a given CSI report which contains
one or more CSI sub-reports, omission of Part 2 CSI is defined in Clause
5.2.3. Part 2 CSI is omitted beginning with the lowest priority level
until the Part 2 CSI code rate is less or equal to the one configured by
higher layer parameter *maxCodeRate*.