# 18 Multicast Broadcast Services

This clause is applicable only for PDCCH receptions, PDSCH receptions,
and PUCCH transmissions for MBS on a serving cell. DCI formats with CRC
scrambled by Multicast MCCH-RNTI for multicast PDSCH receptions in
RRC_INACTIVE state, G-RNTI for multicast, or G-CS-RNTI scheduling PDSCH
receptions are referred to as multicast DCI formats and the PDSCH
receptions are referred to as multicast PDSCH receptions. DCI formats
with CRC scrambled by MCCH-RNTI or G-RNTI for broadcast scheduling PDSCH
receptions are referred to as broadcast DCI formats and the PDSCH
receptions are referred to as broadcast PDSCH receptions. HARQ-ACK
information associated with multicast DCI formats or multicast PDSCH
receptions in RRC_CONNECTED state is referred to as multicast HARQ-ACK
information.

A UE can be provided one or more G-RNTIs for multicast per serving cell
for scrambling the CRC of multicast DCI formats for scheduling PDSCH
receptions. The UE can be provided one or more G-CS-RNTI per serving
cell for scrambling the CRC of multicast DCI formats providing
activation/release/scheduling retransmission for SPS PDSCH receptions in
RRC_CONNECTED state.

A UE can be configured by *cfr-ConfigMCCH-MTCH* or
*cfr-ConfigMCCH-MTCH-RedCap* an MBS frequency resource for PDCCH and
PDSCH receptions providing broadcast MCCH and broadcast MTCH \[12, TS
38.331\]; otherwise, the MBS frequency resource is same as for the
CORESET with index 0 that is associated with the Type0-PDCCH CSS set for
PDCCH and PDSCH receptions providing broadcast MCCH and broadcast MTCH.
The SCS and CP of MBS frequency resource for broadcast are same as the
initial DL BWP. A UE monitors PDCCH for scheduling PDSCH receptions for
broadcast MCCH or broadcast MTCH as described in clause 10.1.

In clauses referring to a higher layer parameter value provided by
*PDCCH-ConfigCommon* or *PDSCH-ConfigMCCH*/*PDSCH-ConfigMTCH* for
broadcast, when applicable a corresponding higher layer parameter value
for broadcast MCCH/broadcast MTCH PDCCH receptions or PDSCH receptions,
respectively, is provided as described in \[12, TS 38.331\].

A UE can be configured by *cfr-ConfigMCCH-MTCH-r18* an MBS frequency
resource for PDCCH and PDSCH receptions providing multicast MCCH and
multicast MTCH in RRC_INACTIVE state \[12, TS 38.331\]; otherwise, the
MBS frequency resource is same as for the CORESET with index 0 that is
associated with the Type0-PDCCH CSS set for PDCCH and PDSCH receptions
providing multicast MCCH and multicast MTCH in RRC_INACTIVE state. A UE
monitors PDCCH for scheduling PDSCH receptions for multicast MCCH or
multicast MTCH in RRC_INACTIVE state as described in clause 10.1.

In clauses referring to a higher layer parameter value provided by
*PDCCH-ConfigCommon* or *PDSCH-ConfigMCCH/PDSCH-ConfigMTCH* for
multicast in RRC_INACTIVE state, when applicable a corresponding higher
layer parameter value for multicast MCCH/multicast MTCH PDCCH receptions
or PDSCH receptions in RRC_INACTIVE state, respectively, is provided as
described in \[12, TS 38.331\].

A UE can be configured, per DL BWP by *cfr-ConfigMulticast*, an MBS
frequency resource within the DL BWP for PDCCH and PDSCH receptions \[4,
TS 38.211\]. If *cfr-ConfigMulticast* does not include
*locationAndBandwidthMulticast*, the MBS frequency resource is the DL
BWP. The SCS and CP of MBS frequency resource provided by
*CFR-ConfigMulticast* are same as the associated DL BWP. In clauses
referring to a higher layer parameter value provided by *PDCCH-Config*
or *PDSCH-Config* or *SPS-Config* for a DL BWP, when applicable a
corresponding higher layer parameter value for multicast PDCCH, PDSCH,
or SPS PDSCH receptions is provided as described in \[12, TS 38.331\].

In clauses referring to a higher layer parameter value provided by a
first or second *PUCCH-Config*, when applicable a corresponding higher
layer parameter value for PUCCH transmissions associated with multicast
PDCCH or PDSCH receptions is provided as described in \[12, TS 38.331\].
In clauses referring to a higher layer parameter value provided by
*n1-PUCCH-AN* or *SPS-PUCCH-AN-List*, when applicable a corresponding
higher layer parameter value for PUCCH transmissions associated with
multicast SPS PDSCH receptions is provided as described in \[12, TS
38.331\]. In clauses referring to a higher layer parameter value
provided by *pdsch-HARQ-ACK-Codebook* or *pdsch-HARQ-ACK-CodebookList*,
when applicable a corresponding higher layer parameter value for
HARQ-ACK codebooks associated with multicast HARQ-ACK information is
provided as described in \[12, TS 38.331\].

A UE monitors PDCCH for scheduling PDSCH receptions or for
activation/release of SPS PDSCH receptions for a corresponding SPS PDSCH
configuration as described in clause 10.1.

A UE can be configured by *harq-FeedbackOptionMulticast,* for a G-RNTI
for multicast or for a G-CS-RNTI, to provide HARQ-ACK information for a
transport block reception associated with the G-RNTI for multicast or
with the G-CS-RNTI, according to the first HARQ-ACK reporting mode if
*harq-FeedbackOptionMulticast* is set to \'*ack-nack*\' or according to
the second HARQ-ACK reporting mode if *harq-FeedbackOptionMulticast* is
set to \'*nack-only*\'. The UE determines a priority for a PUCCH
transmission with multicast HARQ-ACK information according to any
HARQ-ACK reporting mode as described in clause 9 for a PUCCH
transmission with unicast HARQ-ACK information.

For the first HARQ-ACK reporting mode, the UE generates HARQ-ACK
information with ACK value when a UE correctly decodes a transport
block; otherwise, the UE generates HARQ-ACK information with NACK value,
as described in clauses 9 and 9.1 through 9.3. The UE determines a PUCCH
or a PUSCH to provide the HARQ-ACK information as described in clause
9.2.

For the second HARQ-ACK reporting mode, the UE does not transmit a PUCCH
that would include only HARQ-ACK information with ACK values. The second
HARQ-ACK reporting mode is not applicable for the first SPS PDSCH
reception after activation of SPS PDSCH receptions for a SPS
configuration.

For the second HARQ-ACK reporting mode, when a number of HARQ-ACK
information bits is one, a UE transmits a PUCCH only when the HARQ-ACK
information bit has NACK value. The UE determines a PUCCH to provide the
HARQ-ACK information as described in clause 9.2.1 or 9.2.3 when UE is
not provided *moreThanOneNackOnlyMode*, or as the first PUCCH in Table
18-1 when UE is provided *moreThanOneNackOnlyMode.* For a PUCCH resource
associated with PUCCH format 0, the UE transmits the PUCCH as described
in \[4, TS 38.211\] by obtaining $m_{0}$ as described for HARQ-ACK
information in clause 9.2.3 and by setting $m_{cs} = 0$. For a PUCCH
resource associated with PUCCH format 1, the UE transmits the PUCCH as
described in \[4, TS 38.211\] by setting $b(0) = 0$.

A UE that is indicated \'*nack-only*\' by
*harq-FeedbackOptionMulticast*, and for the case when the UE reports
more than one HARQ-ACK information bits, the UE can be indicated to
provide the HARQ-ACK information bits in a PUCCH either according to the
first HARQ-ACK reporting mode when the UE is not provided
*moreThanOneNackOnlyMode* or, for only one G-RNTI or only one G-CS-RNTI,
according to the second HARQ-ACK reporting mode by selecting a PUCCH
resource from a set of PUCCH resources for the PUCCH transmission based
on the values of the HARQ-ACK information bits as described in Table
18-1 when the UE is provided *moreThanOneNackOnlyMode*. The UE generates
HARQ-ACK information bits for the second HARQ-ACK reporting mode
according to a Type-2 HARQ-ACK codebook as described in clause 9.1.3.1.
For a PUCCH resource associated with PUCCH format 0, the UE transmits
the PUCCH as described in \[4, TS 38.211\] by obtaining $m_{0}$ as
described for HARQ-ACK information in clause 9.2.3 and by setting
$m_{cs} = 0$. For a PUCCH resource associated with PUCCH format 1, the
UE transmits the PUCCH as described in \[4, TS 38.211\] by setting
$b(0) = 0$.

For a UE that is indicated the second HARQ-ACK reporting mode, the UE
does not expect to be provided *pdsch-HARQ-ACK-Codebook = semi-static*
for multicast HARQ-ACK information.

For a UE that is indicated the second HARQ-ACK reporting mode and
*moreThanOneNackOnlyMode*, all PUCCH resources associated with the
second HARQ-ACK reporting mode have same starting symbol and same number
of symbols and, when PUCCH resources in Table 18-1 are located in more
than one PRBs, the more than one PRBs are adjacent and are associated
with a same MPR value \[8-1, TS 38.101-1\], \[8-5, TS 38.101-5\].

Table 18-1: Mapping of values of HARQ-ACK information bits to PUCCH
resources for the second HARQ-ACK reporting mode

+------------+------------+------------+------------+------------------------------------------------------+
| Value of HARQ-ACK information bits                | PUCCH resource                                       |
+------------+------------+------------+------------+------------------------------------------------------+
| {0}        | {0,0}      | {0,0,0}    | {0,0,0,0}  | 1^st^ PUCCH resource from                            |
|            |            |            |            | *resourceList/n1PUCCH-AN/sps-PUCCH-AN-ListMulticast* |
+------------+------------+------------+------------+------------------------------------------------------+
|            | {1,0}      | {1,0,0}    | {1,0,0,0}  | 2^nd^ PUCCH resource from                            |
|            |            |            |            | *resourceList/sps-PUCCH-AN-ListMulticast*            |
+------------+------------+------------+------------+------------------------------------------------------+
|            | {0,1}      | {0,1,0}    | {0,1,0,0}  | 3^rd^ PUCCH resource from                            |
|            |            |            |            | *resourceList/sps-PUCCH-AN-ListMulticast*            |
+------------+------------+------------+------------+------------------------------------------------------+
|            |            | {1,1,0}    | {1,1,0,0}  | 4^th^ PUCCH resource from *resourceList*             |
+------------+------------+------------+------------+------------------------------------------------------+
|            |            | {0,0,1}    | {0,0,1,0}  | 5^th^ PUCCH resource from *resourceList*             |
+------------+------------+------------+------------+------------------------------------------------------+
|            |            | {1,0,1}    | {1,0,1,0}  | 6^th^ PUCCH resource from *resourceList*             |
+------------+------------+------------+------------+------------------------------------------------------+
|            |            | {0,1,1}    | {0,1,1,0}  | 7^th^ PUCCH resource from *resourceList*             |
+------------+------------+------------+------------+------------------------------------------------------+
|            |            |            | {1,1,1,0}  | 8^th^ PUCCH resource from *resourceList*             |
+------------+------------+------------+------------+------------------------------------------------------+
|            |            |            | {0,0,0,1}  | 9^th^ PUCCH resource from *resourceList*             |
+------------+------------+------------+------------+------------------------------------------------------+
|            |            |            | {1,0,0,1}  | 10^th^ PUCCH resource from *resourceList*            |
+------------+------------+------------+------------+------------------------------------------------------+
|            |            |            | {0,1,0,1}  | 11^th^ PUCCH resource from *resourceList*            |
+------------+------------+------------+------------+------------------------------------------------------+
|            |            |            | {1,1,0,1}  | 12^th^ PUCCH resource from *resourceList*            |
+------------+------------+------------+------------+------------------------------------------------------+
|            |            |            | {0,0,1,1}  | 13^th^ PUCCH resource from *resourceList*            |
+------------+------------+------------+------------+------------------------------------------------------+
|            |            |            | {1,0,1,1}  | 14^th^ PUCCH resource from *resourceList*            |
+------------+------------+------------+------------+------------------------------------------------------+
|            |            |            | {0,1,1,1}  | 15^th^ PUCCH resource from *resourceList*            |
+------------+------------+------------+------------+------------------------------------------------------+

If a UE is provided *pucch-ConfigurationListMulticast1* or
*pucch-ConfigurationListMulticast2* for PUCCH transmissions with a
priority value, the UE transmits a PUCCH with the priority value
according to *pucch-ConfigurationListMulticast1* or
*pucch-ConfigurationListMulticast2* for each G-RNTI for multicast or
G-CS-RNTI that the UE provides associated HARQ-ACK information according
to the first HARQ-ACK reporting mode or the second HARQ-ACK reporting
mode, respectively. For HARQ-ACK information associated only with the
second HARQ-ACK reporting mode and for more than one HARQ-ACK
information bit, when the UE is not provided *moreThanOneNackOnlyMode*
and the UE provides the HARQ-ACK information according to the first
HARQ-ACK reporting mode, the UE determines a PUCCH resource from
*pucch-ConfigMulticast1/pucch-ConfigurationListMulticast1*, if provided;
otherwise, the UE determines a PUCCH resource from
*pucch-Config/pucch-ConfigurationList* as described in clause 9.2.3.

A PDSCH reception providing an initial transmission of a transport block
is scheduled only by a multicast DCI format. For the first HARQ-ACK
reporting mode, a PDSCH reception providing a retransmission of the
transport block can be scheduled either by a multicast DCI format using
a same G-RNTI for multicast as the G-RNTI for multicast of the initial
transmission of the transport block, or by a unicast DCI format using a
C-RNTI \[6, TS 38.214\].

An activation for SPS PDSCH receptions using a G-CS-RNTI for a
corresponding SPS PDSCH configuration is provided only by a multicast
DCI format as described in clause 10.2 by replacing CS-RNTI with the
G-CS-RNTI. A release for SPS PDSCH receptions using a G-CS-RNTI for a
corresponding SPS PDSCH configuration is provided by a multicast DCI
format as described in clause 10.2 by replacing CS-RNTI with the
G-CS-RNTI, or by a DCI format with CRC scrambled by CS-RNTI. For the
first HARQ-ACK reporting mode and for a transport block that a UE
received in a SPS PDSCH, a PDSCH reception providing a retransmission of
the transport block can be scheduled either by a unicast DCI format
using a CS-RNTI or by a multicast DCI format using a same G-CS-RNTI as
the G-CS-RNTI of the initial transmission of the transport block \[6, TS
38.214\].

For a DCI format indicating SPS PDSCH release, the UE provides the
associated HARQ-ACK information as described in clause 9.1.

A UE can be configured per G-RNTI for multicast or per G-CS-RNTI, by
*harq-FeedbackEnablerMulticast* with value set to \'enabled\', to
provide HARQ-ACK information for PDSCH receptions. When the UE is not
provided *harq-FeedbackEnablerMulticast* for a G-RNTI for multicast or
G-CS-RNTI and *pdsch-HARQ-ACK-Codebook = dynamic* for multicast HARQ-ACK
information, the UE does not provide HARQ-ACK information for respective
PDSCH receptions. If a UE is provided *harq-FeedbackEnablerMulticast*
with value set to \'dci-enabler\' for a G-RNTI for multicast or a
G-CS-RNTI, the UE provides HARQ-ACK information for PDSCH receptions
scheduled by multicast DCI format 4_1 associated with the G-RNTI or the
G-CS-RNTI, and determines whether or not to provide the HARQ-ACK
information for PDSCH receptions scheduled or activated by multicast DCI
format 4_2 based on an indication by the multicast DCI format 4_2
associated with the G-RNTI for multicast or the G-CS-RNTI \[4, TS
38.212\]. If a UE is provided *pdsch-HARQ-ACK-Codebook = semi-static*
for multicast HARQ-ACK information, the UE does not expect to be
provided *harq-FeedbackEnablerMulticast* with value set to
\'dci-enabler\' for a G-RNTI for multicast or a G-CS-RNTI.

If a UE would multiplex second multicast HARQ-ACK information according
to the second HARQ-ACK reporting mode with first multicast HARQ-ACK
information according to the first HARQ-ACK reporting mode, or unicast
HARQ-ACK information, or CSI reports in a first PUCCH or in a PUSCH, as
described in clauses 9 and 9.2.5, the UE provides the second HARQ-ACK
information according to the first HARQ-ACK reporting mode. If the UE
would multiplex the second multicast HARQ-ACK information, for resolving
an overlapping among a second PUCCH with the second HARQ-ACK information
and other PUCCHs or PUSCHs prior to multiplexing the second HARQ-ACK
information in a PUCCH or PUSCH, the UE considers that the UE would
transmit the second PUCCH when all values of the HARQ-ACK information
are \'ACK\'. If the UE would multiplex the second multicast HARQ-ACK
information, for resolving an overlapping among a second PUCCH with the
second HARQ-ACK information and other PUCCHs or PUSCHs prior to
multiplexing the second HARQ-ACK information in a PUCCH or PUSCH when
the UE is provided *moreThanOneNackOnlyMode*, the UE considers that the
UE would transmit the second PUCCH using any PUCCH resource from the
PUCCH resources associated with the second HARQ-ACK reporting mode when
all values of the second HARQ-ACK information are \'ACK\'.

If a UE would only transmit a first PUCCH with only positive SR and a
second PUCCH with HARQ-ACK information according to the second HARQ-ACK
reporting mode, where the first and second PUCCHs would overlap in time
in a slot and have same priority index, it is up to UE implementation
for the UE to transmit either the first PUCCH or the second PUCCH.

If a UE is provided multiple G-RNTIs for multicast or G-CS-RNTIs, a
configuration for a HARQ-ACK codebook type applies to all G-RNTIs for
multicast or G-CS-RNTIs.

If a UE is provided *pdsch-HARQ-ACK-Codebook = semi-static* for
multicast HARQ-ACK information, the UE generates a Type-1 HARQ-ACK
codebook as described in clauses 9.1.2, 9.1.2.1, and 9.1.2.2.

If a UE is provided *pdsch-HARQ-ACK-Codebook = dynamic* for multicast
HARQ-ACK information, the UE generates a Type-2 HARQ-ACK codebook as
described in clauses 9.1.3.1 and 9.1.3.2.

If a UE would report unicast HARQ-ACK information and multicast HARQ-ACK
information with same priority index in a slot, the UE multiplexes the
unicast HARQ-ACK information and the multicast HARQ-ACK information
following the procedures in this clause and in clauses 9.1.2, 9.1.3, and
9.1.4.

If, for unicast and multicast HARQ-ACK information of same priority
value, a UE

\- is provided

\- either *pdsch-HARQ-ACK-Codebook* = *dynamic* or
*pdsch-HARQ-ACK-Codebook-r16* for unicast HARQ-ACK information and
*pdsch-HARQ-ACK-Codebook* = *semi-static* for multicast HARQ-ACK
information,

\- or *pdsch-HARQ-ACK-Codebook* = *semi-static* or
*pdsch-HARQ-ACK-Codebook-r16* for unicast HARQ-ACK information and
*pdsch-HARQ-ACK-Codebook* = *dynamic* for multicast HARQ-ACK
information, and

\- would multiplex the unicast and multicast HARQ-ACK information in a
same PUCCH or PUSCH

the UE

\- appends the HARQ-ACK codebooks for the multicast HARQ-ACK information
to the HARQ-ACK codebooks for the unicast HARQ-ACK information

\- if $O_{ACK} + O_{SR} + O_{CSI} \leq 11$, the UE determines
$n_{HARQ - ACK}$ for obtaining a power of a PUCCH transmission with the
HARQ-ACK information, as described in clause 7.2.1, as a sum of the
$n_{HARQ - ACK}$ value from clause 9.1.3.1 or clause 9.1.3.3 and the
$n_{HARQ - ACK}$ value from clause 9.1.2.1 or as a sum of the
$n_{HARQ - ACK}$ value from clause 9.1.2.1 or clause 9.1.3.3 and the
$n_{HARQ - ACK}$ value from clause 9.1.3.1.

A UE determines a PUCCH resource for a PUCCH transmission with HARQ-ACK
information as described in clauses 9.2 and 9.2.1 through 9.2.5.

If a UE multiplexes in a PUCCH HARQ-ACK information of same priority
associated with unicast DCI formats and with multicast DCI formats in a
same PUCCH, the last DCI format that the UE uses to determine the PUCCH
resource from *pucch-Config/pucch-ConfigurationList*, as described in
clause 9.2.3, is a last unicast DCI format.

If the UE multiplexes in a PUCCH only multicast HARQ-ACK information of
same priority that is according to both the first and second HARQ-ACK
reporting modes, the last DCI format that the UE uses to determine the
PUCCH resource from
*pucch-ConfigMulticast1/pucch-ConfigurationListMulticast1*, if provided;
otherwise, from *pucch-Config/pucch-ConfigurationList*, as described in
clause 9.2.3, is a last DCI format associated with multicast HARQ-ACK
information that is according to the first HARQ-ACK reporting mode.

If a UE multiplexes in a PUCCH only first HARQ-ACK information
associated with multicast SPS PDSCH receptions and second HARQ-ACK
information associated with multicast DCI formats and having same
priority value as the first HARQ-ACK information, and both the first and
second HARQ-ACK information are according to the first HARQ-ACK
reporting mode, the UE determines the PUCCH resource based on the last
multicast DCI format from
*pucch-ConfigMulticast1/pucch-ConfigurationListMulticast1,* if provided;
otherwise, from *pucch-Config/pucch-ConfigurationList*, as described in
clause 9.2.3.

If a UE multiplexes in a PUCCH only first HARQ-ACK information
associated with multicast SPS PDSCH receptions and second HARQ-ACK
information associated with multicast DCI formats and having same
priority value as the first HARQ-ACK information, and the first and
second HARQ-ACK information are indicated by
*harq-FeedbackOptionMulticast* different HARQ-ACK reporting modes, the
UE determines the PUCCH resource based on:

*- sps-PUCCH-AN-ListMulticast*, or *sps-PUCCH-AN-List* if
*sps-PUCCH-AN-ListMulticast* is not provided, if the first HARQ-ACK
information is according to the first HARQ-ACK reporting mode or

\- the last multicast DCI format, as described in clause 9.2.3, if the
second HARQ-ACK information is according to the first HARQ-ACK reporting
mode.

If a UE multiplexes in a PUCCH first HARQ-ACK information associated
with unicast SPS PDSCH receptions and second HARQ-ACK information
associated with multicast DCI formats and having same priority value as
the first HARQ-ACK information in a same PUCCH, the UE determines the
PUCCH resource from

\- if provided, *SPS-PUCCH-AN-List* for unicast SPS PDSCH receptions as
described in clause 9.2.1;

\- else, if provided, *PUCCH-Config/PUCCH-ConfigurationList* for
multicast PDSCH receptions;

\- else, *PUCCH-Config/PUCCH-ConfigurationList* for unicast PDSCH
receptions.

If a UE multiplexes in a PUCCH first HARQ-ACK information associated
with unicast SPS PDSCH receptions and second HARQ-ACK information
associated with multicast SPS PDSCH receptions and having same priority
value as the first HARQ-ACK information in a same PUCCH, the UE
determines the PUCCH resource from *SPS-PUCCH-AN-List* for unicast SPS
PDSCH receptions as described in clause 9.2.1.

If a UE multiplexes in a PUCCH only HARQ-ACK information associated with
multicast SPS PDSCHs receptions of same priority that is according to
the first HARQ-ACK reporting mode and is not provided
*sps-PUCCH-AN-ListMulticast*, the UE determines the PUCCH resource from
the *sps-PUCCH-AN-List* provided for unicast SPS PDSCH reception as
described in clause 9.2.1*.*

If a UE multiplexes in a PUCCH multicast HARQ-ACK information only
according to second HARQ-ACK reporting modes and CSI reports and, if
any, SR, the UE determines a PUCCH resource as described in clause
9.2.5.2 for multiplexing CSI reports with HARQ-ACK information that is
in response to PDSCH receptions without corresponding PDCCHs.

A UE is not required to multiplex in a PUCCH multicast HARQ-ACK
information of a priority and unicast UCI of the priority if the UE is
provided *subslotLengthForPUCCH* for PUCCH transmissions with unicast
UCI of the priority.