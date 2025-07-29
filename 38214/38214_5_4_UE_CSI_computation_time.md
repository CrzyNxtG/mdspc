## 5.4 UE CSI computation time

When the *CSI request* field on a DCI triggers a CSI report(s) on PUSCH,
the UE shall provide a valid CSI report for the *n*-th triggered report,

\- if the first uplink symbol to carry the corresponding CSI report(s)
including the effect of the timing advance, starts no earlier than at
symbol *Z~ref~*, and

\- if the first uplink symbol to carry the *n*-th CSI report including
the effect of the timing advance, starts no earlier than at symbol
*Z\'~ref~(n),*

where *Z~ref~* is defined as the next uplink symbol with its CP starting
![](media/image698.wmf) after the end of the last symbol of the PDCCH
triggering the CSI report(s), and where *Z\'~ref~(n),* is defined as the
next uplink symbol with its CP starting ![](media/image699.wmf)after the
end of the last symbol in time of the latest of: aperiodic CSI-RS
resource for channel measurements, aperiodic CSI-IM used for
interference measurements, and aperiodic NZP CSI-RS for interference
measurement for a *CSI-ReportConfig,* or for all triggered
sub-configurations if *CSI-ReportConfig* contains multiple
sub-configurations, when aperiodic CSI-RS is used for channel
measurement for the *n*-th triggered CSI report, and where *T~switch~*
is defined in clause 6.4 and is applied only if $Z_{1}$ of table 5.4-1
is applied.

If the PUSCH indicated by the DCI is overlapping with another PUCCH or
PUSCH, then the CSI report(s) are multiplexed following the procedure in
clause 9.2.5 of \[6, TS 38.213\] and clause 5.2.5 when applicable,
otherwise the CSI report(s) are transmitted on the PUSCH indicated by
the DCI.

When the *CSI request* field on a DCI triggers a CSI report(s) on PUSCH,
if the first uplink symbol to carry the corresponding CSI report(s)
including the effect of the timing advance, starts earlier than at
symbol *Z~ref~*,

\- the UE may ignore the scheduling DCI if no HARQ-ACK or transport
block is multiplexed on the PUSCH.

When the *CSI request* field on a DCI triggers a CSI report(s) on PUSCH,
if the first uplink symbol to carry the *n*-th CSI report including the
effect of the timing advance, starts earlier than at symbol
*Z\'~ref~(n),*

\- the UE may ignore the scheduling DCI if the number of triggered
reports is one and no HARQ-ACK or transport block is multiplexed on the
PUSCH

\- Otherwise, the UE is not required to update the CSI for the *n*-th
triggered CSI report.

When the PDCCH reception includes two PDCCH candidates from two
respective search space sets, as described in clause 10.1 of \[6, TS
38.213\], for the purpose of determining the last symbol of the PDCCH
triggering the CSI report(s), the PDCCH candidate that ends later in
time is used.

*Z,* *Z\'* and *µ* are defined as:

$Z = \max_{m = 0,\ldots,M - 1}{(Z(m))}$ and
$Z' = \max_{m = 0,\ldots,M - 1}{(Z'(m))}$, where *M* is the number of
updated CSI report(s) according to Clause 5.2.1.6, $(Z(m),Z'(m))$
corresponds to the *m*-th updated CSI report and is defined as

\- $(Z_{1},Z_{1}')$ of the table 5.4-1 if max{ *µ~PDCCH~*, *µ~CSI-RS~,
µ~UL~*} ≤ 3 and if the CSI is triggered without a PUSCH with either
transport block or HARQ-ACK or both when *L* = 0 CPUs are occupied
(according to Clause 5.2.1.6) and the CSI to be transmitted is a single
CSI and corresponds to wideband frequency-granularity where the CSI
corresponds to at most 4 CSI-RS ports in a single resource without CRI
report and where *CodebookType* is set to \'typeI-SinglePanel\' or where
*reportQuantity* is set to \'cri-RI-CQI\', or

\- $(Z_{1},Z_{1}')$ of the table 5.4-2 if the CSI to be transmitted
corresponds to wideband frequency-granularity where the CSI corresponds
to at most 4 CSI-RS ports in a single resource without CRI report and
where *CodebookType* is set to \'typeI-SinglePanel\' or where
*reportQuantity* is set to \'cri-RI-CQI\', or

\- $(Z_{1},Z_{1}')$ of the table 5.4-2 if the CSI to be transmitted
corresponds to wideband frequency-granularity where the *reportQuantity*
is set to \'ssb-Index-SINR\', \'cri-SINR\', \'ssb-Index-SINR- Index \',
or \'cri-SINR- Index \', or

\- $(Z_{3},Z_{3}')$ of the table 5.4-2 if *reportQuantity* is set to
\'cri-RSRP\', \'ssb-Index-RSRP\', \'cri-RSRP- Index\' or
\'ssb-Index-RSRP- Index \', $\ where\ Xµ\ $is according to UE reported
capability *beamReportTiming* and *KB~l~* is according to UE reported
capability *beamSwitchTiming* as defined in \[13, TS 38.306\], or if the
CSI report is configured with *ltm-CSI-ReportConfig* for L1-RSRP
measurement, or

\- $(Z_{2},Z_{2}')$ or $(Z_{2} + Z_{2}',{2Z}_{2}')$, according to UE
reported capability, with $(Z_{2},Z_{2}')$ of table 5.4-2, if
*codebookType* is set to \'typeII-CJT-r18\' or
\'typeII-CJT-PortSelection-r18\' and the corresponding
*NZP-CSI-RS-ResourceSet* for channel measurement is configured with
$1 < N_{TRP} \leq 4$ resources, or

\- $(Z_{2} + 14(K - 1)m,Z_{2}')$, with $(Z_{2},Z_{2}')$ of table 5.4-2,
if the CSI report is configured with $N_{4} = 1$, *codebookType* is set
to \'typeII-Doppler-r18\' or \'typeII-Doppler-PortSelection-r18\' and
the corresponding *NZP-CSI-RS-ResourceSet* for channel measurement is
aperiodic with $K$ CSI-RS resources, or

\- $(Z_{2} + w,Z_{2}')$, with $(Z_{2},Z_{2}')$ of table 5.4-2, where
$w$=56.(*K~P~* --1) or 56.*K~P~* symbols, according to the reported UE
capability, where the value of 𝐾~𝑃~ ∈{1,2,4} is indicated by UE
capability, if the CSI report is configured with $N_{4} = 1$,
*codebookType* is set to \'typeII-Doppler-r18\' or
\'typeII-Doppler-PortSelection-r18\' and the corresponding
*NZP-CSI-RS-ResourceSet* for channel measurement is periodic or
semi-persistent with a single CSI-RS resource, or

\- $(Z_{2} + 14(K - 1)m,Z_{2}')$ or
$(Z_{2} + 14(K - 1)m + Z_{2}',2Z_{2}')$, according to UE reported
capability, with $(Z_{2},Z_{2}')$ of table 5.4-2, if the CSI report is
configured with $N_{4} > 1$, *codebookType* is set to
\'typeII-Doppler-r18\' and the corresponding *NZP-CSI-RS-ResourceSet*
for channel measurement is aperiodic with $K$ CSI-RS resources, or

\- $(Z_{2} + w,Z_{2}')$ or $(Z_{2} + w + Z_{2}',{2Z}_{2}')$, according
to UE reported capability, with $(Z_{2},Z_{2}')$ of table 5.4-2, if the
CSI report is configured with $N_{4} > 1$, *codebookType* is set to
\'typeII-Doppler-r18\' and the corresponding *NZP-CSI-RS-ResourceSet*
for channel measurement is periodic or semi-persistent with a single
CSI-RS resource, or

\- $(Z_{2},Z_{2}')$ of table 5.4-2 otherwise.

*- µ* of table 5.4-1 and table 5.4-2 corresponds to the min (*µ~PDCCH~*,
*µ~CSI-RS~, µ~UL~*) where the *µ~PDCCH~* corresponds to the subcarrier
spacing of the PDCCH with which the DCI was transmitted and *µ~UL~*
corresponds to the subcarrier spacing of the PUSCH with which the CSI
report is to be transmitted and *µ~CSI-RS~* corresponds to the minimum
subcarrier spacing of the aperiodic CSI-RS triggered by the DCI

Table 5.4-1: CSI computation delay requirement 1

+-------------------------+---------------------------------------------------------------+
| ![](media/image700.wmf) | *Z~1~* \[symbols\]                                            |
|                         +-------------------------------+-------------------------------+
|                         | *Z~1~*                        | *Z\'~1~*                      |
+=========================+===============================+===============================+
| 0                       | 10                            | 8                             |
+-------------------------+-------------------------------+-------------------------------+
| 1                       | 13                            | 11                            |
+-------------------------+-------------------------------+-------------------------------+
| 2                       | 25                            | 21                            |
+-------------------------+-------------------------------+-------------------------------+
| 3                       | 43                            | 36                            |
+-------------------------+-------------------------------+-------------------------------+

Table 5.4-2: CSI computation delay requirement 2

+-------------------------+---------------------+-----------------------+----------------------------------------------------------+
| ![](media/image700.wmf) | *Z~1~* \[symbols\]  | *Z~2~* \[symbols\]    | *Z~3~* \[symbols\]                                       |
|                         +----------+----------+-----------+-----------+------------------------------------------+---------------+
|                         | *Z~1~*   | *Z\'~1~* | *Z~2~*    | *Z\'~2~*  | *Z~3~*                                   | *Z\'~3~*      |
+=========================+==========+==========+===========+===========+==========================================+===============+
| 0                       | 22       | 16       | 40        | 37        | 22                                       | *X*~0~        |
+-------------------------+----------+----------+-----------+-----------+------------------------------------------+---------------+
| 1                       | 33       | 30       | 72        | 69        | 33                                       | *X*~1~        |
+-------------------------+----------+----------+-----------+-----------+------------------------------------------+---------------+
| 2                       | 44       | 42       | 141       | 140       | [min(44,]{.underline}${\ X}_{3}$[*X*~2~+ | *X*~2~        |
|                         |          |          |           |           | KB~1~)]{.underline}                      |               |
+-------------------------+----------+----------+-----------+-----------+------------------------------------------+---------------+
| 3                       | 97       | 85       | 152       | 140       | [min(97, *X*~3~+ KB~2~)]{.underline}     | *X*~3~        |
+-------------------------+----------+----------+-----------+-----------+------------------------------------------+---------------+
| 5                       | 388      | 340      | 608       | 560       | [min(388, X5+ KB3) ]{.underline}         | *X5 *         |
+-------------------------+----------+----------+-----------+-----------+------------------------------------------+---------------+
| 6                       | 776      | 680      | 1216      | 1120      | [min(776, X6+ KB4) ]{.underline}         | *X6 *         |
+-------------------------+----------+----------+-----------+-----------+------------------------------------------+---------------+

For a CSI report corresponding to a *CSI-ReportConfig* that contains a
list of sub-configurations, provided by
*csi-ReportSubConfigToAddModList*, only $(Z_{2},Z_{2}')$ of table 5.4-2
is applicable.