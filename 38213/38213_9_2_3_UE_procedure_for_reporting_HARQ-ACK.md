### 9.2.3 UE procedure for reporting HARQ-ACK

In this clause, for the purpose of determining a PUCCH resource for a
PUCCH transmission in a slot using a PUCCH resource indicator field in a
DCI format that schedules a PDSCH reception, and for the purpose of
determining the slot for the PUCCH transmission

\- a UE is assumed to generate HARQ-ACK information regardless of
whether or not the PDSCH reception provides a transport block for a HARQ
process with disabled HARQ-ACK information as indicated by
*downlinkHARQ-FeedbackDisabled*, if provided

\- a UE is assumed to not generate HARQ-ACK information associated with
a G-RNTI for multicast or a G-CS-RNTI with disabled HARQ-ACK information
as described in clause 18.

The UE determines a number of HARQ-ACK information bits $O_{\text{ACK}}$
as described in clauses 9.1 through 9.1.5 and a corresponding set of
PUCCH resources as described in clause 9.2.1. If $O_{\text{ACK}} = 0$,
the UE does not transmit a PUCCH that only includes HARQ-ACK information
bits.

A UE does not expect to transmit more than one PUCCH with HARQ-ACK
information in a slot per priority index, if the UE is not provided
*ackNackFeedbackMode = separate*.

For DCI format 1_0, the PDSCH-to-HARQ_feedback timing indicator field
values map to {1, 2, 3, 4, 5, 6, 7, 8} for SCS configuration of PUCCH
transmission $\mu \leq 3$, to {7, 8, 12, 16, 20, 24, 28, 32} for
$\mu = 5$, and to {13, 16, 24, 32, 40, 48, 56, 64} for $\mu = 6$. For a
unicast DCI format, other than DCI format 1_0, the
PDSCH-to-HARQ_feedback timing indicator field values, if present, map to
values for a set of number of slots provided by *dl-DataToUL-ACK*,
*dl-DataToUL-ACK-r16*, or *dl-DataToUL-ACK-DCI-1-2*, or
*dl-DataToUL-ACK-r17,* or *dl-DataToUL-ACK-DCI-1-2-r17*, or
*dl-DataToUL-ACK-v1700* as defined in Table 9.2.3-1. If the DCI format
indicates a cell for the PUCCH transmission, as described in clause 9.A,
the PDSCH-to-HARQ_feedback timing indicator field value maps to slots of
the active UL BWP of the cell; otherwise, the PDSCH-to-HARQ_feedback
timing indicator field value maps to slots of the active UL BWP of the
PCell. For DCI format 4_1, the PDSCH-to-HARQ_feedback timing indicator
field values are provided by *dl-DataToUL-ACK-MulticastDCI-Format4-1*
or, if *dl-DataToUL-ACK-MulticastDCI-Format4-1* is not provided, by {1,
2, 3, 4, 5, 6, 7, 8}. For DCI format 4_2, the PDSCH-to-HARQ_feedback
timing indicator field values are provided by *dl-DataToUL-ACK* from
*pucch-ConfigMulticast1/pucch-ConfigurationListMulticast1* or
*pucch-ConfigMulticast2/pucch-ConfigurationListMulticast2* if provided;
otherwise, from *pucch-Config/pucch-ConfigurationList.*

The following apply to the PCell if the UE is provided
*pucch-sSCellPattern*; otherwise, the following apply to the serving
cell of the PUCCH transmission. If the UE is provided
*subslotLengthForPUCCH*, $n$ is the last UL slot for PUCCH transmission
that overlaps with a PDSCH reception or with a PDCCH reception providing
a DCI format having associated HARQ-ACK information without scheduling a
PDSCH reception; otherwise, $n$ is the last UL slot for PUCCH
transmission that overlaps with the DL slot $n_{D}$ for the PDSCH
reception or with the DL slot $n_{D}\ $for the PDCCH reception in case
of a DCI format that triggers a HARQ-ACK information report and does not
schedule a PDSCH reception.

For a SPS PDSCH reception ending in DL slot $n_{D}$, the UE transmits
the PUCCH in UL slot $n + k$ where $k$ is provided by the
PDSCH-to-HARQ_feedback timing indicator field, if present, in a DCI
format activating the SPS PDSCH reception.

If the UE detects a DCI format that does not include a
PDSCH-to-HARQ_feedback timing indicator field and schedules a PDSCH
reception or activates a SPS PDSCH reception ending in DL slot $n_{D}$,
the UE provides corresponding HARQ-ACK information in a PUCCH
transmission within UL slot $n + k$ where $k$ is provided by
*dl-DataToUL-ACK*, or *dl-DataToUL-ACK-r16*, or
*dl-DataToUL-ACK-DCI-1-2*, or *dl-DataToUL-ACK-r17*, or
*dl-DataToUL-ACK-DCI-1-2-r17*, or *dl-DataToUL-ACK-v1700*.

If the UE detects a DCI format scheduling a number of PDSCH receptions
ending in DL slot $n_{D}$ or if the UE detects a DCI format generating a
HARQ-ACK information bit and does not schedule a PDSCH reception through
a PDCCH reception ending in DL slot $n_{D}$, the UE provides
corresponding HARQ-ACK information in a PUCCH transmission within UL
slot $n + k$, where $k$ is a number of slots and is indicated by the
PDSCH-to-HARQ_feedback timing indicator field in the DCI format, if
present, or provided by *dl-DataToUL-ACK*, *dl-DataToUL-ACK-r16*, or
*dl-DataToUL-ACK-DCI-1-2*, or *dl-DataToUL-ACK-r17*, or
*dl-DataToUL-ACK-DCI-1-2-r17*, or *dl-DataToUL-ACK-v1700*.

A PUCCH transmission with HARQ-ACK information is subject to the
limitations for UE transmissions described in clause 11.1, clause 11.1.1
and clause 17.2.

Table 9.2.3-1: Mapping of PDSCH-to-HARQ_feedback timing indicator field
values to numbers of slots

+-------------+-------------+-------------+------------------------------------------+
| PDSCH-to-HARQ_feedback timing indicator | Number of slots $\mathbf{k}$             |
+-------------+-------------+-------------+------------------------------------------+
| 1 bit       | 2 bits      | 3 bits      |                                          |
+-------------+-------------+-------------+------------------------------------------+
| \'0\'       | \'00\'      | \'000\'     | 1^st^ value provided by                  |
|             |             |             | *dl-DataToUL-ACK*,                       |
|             |             |             | *dl-DataToUL-ACK-r16*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2*,               |
|             |             |             | *dl-DataToUL-ACK-r17*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2-r17*,           |
|             |             |             | *dl-DataToUL-ACK-v1700*, or              |
|             |             |             | *dl-DataToUL-ACK-MulticastDCI-Format4-1* |
+-------------+-------------+-------------+------------------------------------------+
| \'1\'       | \'01\'      | \'001\'     | 2^nd^ value provided by                  |
|             |             |             | *dl-DataToUL-ACK*,                       |
|             |             |             | *dl-DataToUL-ACK-r16*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2*,               |
|             |             |             | *dl-DataToUL-ACK-r17*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2-r17*,           |
|             |             |             | *dl-DataToUL-ACK-v1700*, or              |
|             |             |             | *dl-DataToUL-ACK-MulticastDCI-Format4-1* |
+-------------+-------------+-------------+------------------------------------------+
|             | \'10\'      | \'010\'     | 3^rd^ value provided by                  |
|             |             |             | *dl-DataToUL-ACK*,                       |
|             |             |             | *dl-DataToUL-ACK-r16*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2*,               |
|             |             |             | *dl-DataToUL-ACK-r17*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2-r17*,           |
|             |             |             | *dl-DataToUL-ACK-v1700*, or              |
|             |             |             | *dl-DataToUL-ACK-MulticastDCI-Format4-1* |
+-------------+-------------+-------------+------------------------------------------+
|             | \'11\'      | \'011\'     | 4^th^ value provided by                  |
|             |             |             | *dl-DataToUL-ACK*,                       |
|             |             |             | *dl-DataToUL-ACK-r16*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2*,               |
|             |             |             | *dl-DataToUL-ACK-r17*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2-r17*,           |
|             |             |             | *dl-DataToUL-ACK-v1700*, or              |
|             |             |             | *dl-DataToUL-ACK-MulticastDCI-Format4-1* |
+-------------+-------------+-------------+------------------------------------------+
|             |             | \'100\'     | 5^th^ value provided by                  |
|             |             |             | *dl-DataToUL-ACK*,                       |
|             |             |             | *dl-DataToUL-ACK-r16*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2*,               |
|             |             |             | *dl-DataToUL-ACK-r17*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2-r17*,           |
|             |             |             | *dl-DataToUL-ACK-v1700*, or              |
|             |             |             | *dl-DataToUL-ACK-MulticastDCI-Format4-1* |
+-------------+-------------+-------------+------------------------------------------+
|             |             | \'101\'     | 6^th^ value provided by                  |
|             |             |             | *dl-DataToUL-ACK*,                       |
|             |             |             | *dl-DataToUL-ACK-r16*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2*,               |
|             |             |             | *dl-DataToUL-ACK-r17*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2-r17*,           |
|             |             |             | *dl-DataToUL-ACK-v1700*, or              |
|             |             |             | *dl-DataToUL-ACK-MulticastDCI-Format4-1* |
+-------------+-------------+-------------+------------------------------------------+
|             |             | \'110\'     | 7^th^ value provided by                  |
|             |             |             | *dl-DataToUL-ACK*,                       |
|             |             |             | *dl-DataToUL-ACK-r16*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2*,               |
|             |             |             | *dl-DataToUL-ACK-r17*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2-r17*,           |
|             |             |             | *dl-DataToUL-ACK-v1700*, or              |
|             |             |             | *dl-DataToUL-ACK-MulticastDCI-Format4-1* |
+-------------+-------------+-------------+------------------------------------------+
|             |             | \'111\'     | 8^th^ value provided by                  |
|             |             |             | *dl-DataToUL-ACK*,                       |
|             |             |             | *dl-DataToUL-ACK-r16*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2*,               |
|             |             |             | *dl-DataToUL-ACK-r17*,                   |
|             |             |             | *dl-DataToUL-ACK-DCI-1-2-r17*,           |
|             |             |             | *dl-DataToUL-ACK-v1700*, or              |
|             |             |             | *dl-DataToUL-ACK-MulticastDCI-Format4-1* |
+-------------+-------------+-------------+------------------------------------------+

For a PUCCH transmission with HARQ-ACK information, a UE determines a
PUCCH resource on the cell of the PUCCH transmission, as described in
clause 9.A, after determining a set of PUCCH resources for
$O_{\text{UCI}}$ HARQ-ACK information bits, as described in clause
9.2.1. The PUCCH resource determination is based on a PUCCH resource
indicator field \[5, TS 38.212\], if present, in a last DCI format,
excluding the SPS activation DCI, among the DCI formats that have a
value of a PDSCH-to-HARQ_feedback timing indicator field, if present, or
a value of *dl-DataToUL-ACK*, or *dl-DataToUL-ACK-r16*, or
*dl-DataToUL-ACK-DCI-1-2*, or *dl-DataToUL-ACK-r17,* or
*dl-DataToUL-ACK-DCI-1-2-r17*, or
*dl-DataToUL-ACK-MulticastDCI-Format4-1*, or *dl-DataToUL-ACK-v1700*,
indicating a same slot for the PUCCH transmission, that the UE detects
and for which the UE transmits corresponding HARQ-ACK information in the
PUCCH.

The PUCCH resource indicator field values map to values of a set of
PUCCH resource indexes, as defined in Table 9.2.3-2 for a PUCCH resource
indicator field of 3 bits, provided by *resourceList* for PUCCH
resources from a set of PUCCH resources provided by *PUCCH-ResourceSet*
with a maximum of eight PUCCH resources. If the PUCCH resource indicator
field includes 1 bit or 2 bits, the values map to the first two values
or the first four values, respectively, of Table 9.2.3-2. If the last
DCI format does not include a PUCCH resource indicator field, the first
value of Table 9.2.3-2 is used.

For the first set of PUCCH resources and when the size
$R_{\text{PUCCH}}$ of *resourceList* is larger than eight, when a UE
provides HARQ-ACK information in a PUCCH transmission in response to
detecting a last DCI format in a PDCCH reception, excluding the SPS
activation DCI, among DCI formats with a value of the
PDSCH-to-HARQ_feedback timing indicator field, if present, or a value of
*dl-DataToUL-ACK*, or *dl-DataToUL-ACK-r16*, or
*dl-DataToUL-ACK-DCI-1-2*, or *dl-DataToUL-ACK-r17,* or
*dl-DataToUL-ACK-DCI-1-2-r17*, or
*dl-DataToUL-ACK-MulticastDCI-Format4-1*, or *dl-DataToUL-ACK-v1700*,
indicating a same slot for the PUCCH transmission, the UE determines a
PUCCH resource with index $r_{\text{PUCCH}}$,
${0 \leq r}_{\text{PUCCH}} \leq R_{\text{PUCCH}} - 1$, as

![](media/image66.wmf){width="4.895833333333333in"
height="0.8958333333333334in"}

where $N_{\text{CCE,p}}$ is a number of CCEs in CORESET $p$ of the PDCCH
reception for the DCI format as described in clause 10.1,
$n_{\text{CCE,p}}$ is the index of a first CCE for the PDCCH reception,
and $\mathrm{\Delta}_{PRI}$ is a value of the PUCCH resource indicator
field in the DCI format. When the PDCCH reception includes first and
second PDCCH candidates from respective first and second search space
sets, as described in clause 10.1, the CORESET is associated with the
search space set having the smaller index. If

\- the first search space set has larger index than the second search
space set and includes the first PDCCH candidate and a third PDCCH
candidate that have same first CCE index and CCE aggregation levels 8
and 16, or 16 and 8, respectively,

\- the second search space set includes the second PDCCH candidate that
has same index and same CCE aggregation level as the first PDCCH
candidate, and a fourth PDCCH candidate that has same index and same CCE
aggregation level as the third PDCCH candidate,

\- the CORESET associated with the first search space set has
*cce-REG-MappingType* = \'*nonInterleaved*\' and has duration of one
symbol, and

\- the second PDCCH candidate has different first CCE index than the
fourth PDCCH candidate

the UE determines $n_{CCE,0}$ from the PDCCH candidate with CCE
aggregation level 16 among the second PDCCH candidate and the fourth
PDCCH candidate.

If the DCI format does not include a PUCCH resource indicator field,
$\mathrm{\Delta}_{PRI} = 0$.

Table 9.2.3-2: Mapping of PUCCH resource indication field values to a
PUCCH resource in a PUCCH resource set with maximum 8 PUCCH resources

+------------+------------+------------+-----------------------------------------+
| PUCCH resource indicator             | PUCCH resource                          |
+------------+------------+------------+-----------------------------------------+
| 1 bit      | 2 bits     | 3 bits     |                                         |
+------------+------------+------------+-----------------------------------------+
| \'0\'      | \'00\'     | \'000\'    | 1^st^ PUCCH resource provided by        |
|            |            |            | *pucch-ResourceId* obtained from the    |
|            |            |            | 1^st^ value of *resourceList*           |
+------------+------------+------------+-----------------------------------------+
| \'1\'      | \'01\'     | \'001\'    | 2^nd^ PUCCH resource provided by        |
|            |            |            | *pucch-ResourceId* obtained from the    |
|            |            |            | 2^nd^ value of *resourceList*           |
+------------+------------+------------+-----------------------------------------+
|            | \'10\'     | \'010\'    | 3^rd^ PUCCH resource provided by        |
|            |            |            | *pucch-ResourceId* obtained from the    |
|            |            |            | 3^rd^ value of *resourceList*           |
+------------+------------+------------+-----------------------------------------+
|            | \'11\'     | \'011\'    | 4^th^ PUCCH resource provided by        |
|            |            |            | *pucch-ResourceId* obtained from the    |
|            |            |            | 4^th^ value of *resourceList*           |
+------------+------------+------------+-----------------------------------------+
|            |            | \'100\'    | 5^th^ PUCCH resource provided by        |
|            |            |            | *pucch-ResourceId* obtained from the    |
|            |            |            | 5^th^ value of *resourceList*           |
+------------+------------+------------+-----------------------------------------+
|            |            | \'101\'    | 6^th^ PUCCH resource provided by        |
|            |            |            | *pucch-ResourceId* obtained from the    |
|            |            |            | 6^th^ value of *resourceList*           |
+------------+------------+------------+-----------------------------------------+
|            |            | \'110\'    | 7^th^ PUCCH resource provided by        |
|            |            |            | *pucch-ResourceId* obtained from the    |
|            |            |            | 7^th^ value of *resourceList*           |
+------------+------------+------------+-----------------------------------------+
|            |            | \'111\'    | 8^th^ PUCCH resource provided by        |
|            |            |            | *pucch-ResourceId* obtained from the    |
|            |            |            | 8^th^ value of *resourceList*           |
+------------+------------+------------+-----------------------------------------+

If a UE determines a first resource for a PUCCH transmission with
HARQ-ACK information corresponding only to a PDSCH reception without a
corresponding PDCCH or detects a first DCI format indicating a first
resource for a PUCCH transmission with corresponding HARQ-ACK
information in a slot and also detects at a later time a second DCI
format indicating a second resource for a PUCCH transmission with
corresponding HARQ-ACK information in the slot, the UE does not expect
to multiplex HARQ-ACK information corresponding to the second DCI format
in a PUCCH resource in the slot if the PDCCH reception that includes the
second DCI format is not earlier than
$N_{3} \bullet (2048 + 144) \bullet \kappa \bullet 2^{- \mu} \bullet T_{c}$
from the beginning of a first symbol of the first resource for PUCCH
transmission in the slot where, $\kappa$ and $T_{c}$ are defined in
clause 4.1 of \[4, TS 38.211\] and $\mu$ corresponds to the smallest SCS
configuration among the SCS configurations of the PDCCHs providing the
DCI formats and the SCS configuration of the PUCCH. If
*processingType2Enabled* of *PDSCH-ServingCellConfig* is set to *enable*
for the serving cell with the second DCI format and for all serving
cells with corresponding HARQ-ACK information multiplexed in the PUCCH
transmission in the slot, $N_{3} = 3$ for $\mu = 0$, $N_{3} = 4.5$ for
$\mu = 1$, $N_{3} = 9$ for $\mu = 2$; otherwise, $N_{3} = 8$ for
$\mu = 0$, $N_{3} = 10$ for $\mu = 1$, $N_{3} = 17$ for $\mu = 2$,
$N_{3} = 20$ for $\mu = 3$, $N_{3} = 80$ for $\mu = 5$, and
$N_{3} = 160$ for $\mu = 6$.

If a UE is not provided *SPS-PUCCH-AN-List* and transmits HARQ-ACK
information corresponding only to a PDSCH reception without a
corresponding PDCCH, which includes the first SPS PDSCH reception
associated with the corresponding activation DCI, a PUCCH resource for
corresponding PUCCH transmission with HARQ-ACK information is provided
by *n1PUCCH-AN*.

If a UE transmits a PUCCH with HARQ-ACK information using PUCCH format
0, the UE determines values $m_{0}$ and $m_{CS}$ for computing a value
of cyclic shift $\alpha$ \[4, TS 38.211\] where $m_{0}$ is provided by
*initialCyclicShift* of *PUCCH-format0* or, if *initialCyclicShift* is
not provided, by the initial cyclic shift index as described in clause
9.2.1 and $m_{CS}$ is determined from the value of one HARQ-ACK
information bit or from the values of two HARQ-ACK information bits as
in Table 9.2.3-3 and Table 9.2.3-4, respectively.

Table 9.2.3-3: Mapping of values for one HARQ-ACK information bit to
sequences for PUCCH format 0

  ------------------------------- ------------------- -------------------
  HARQ-ACK Value                  0                   1

  **Sequence cyclic shift**       $$m_{CS} = 0$$      $$m_{CS} = 6$$
  ------------------------------- ------------------- -------------------

Table 9.2.3-4: Mapping of values for two HARQ-ACK information bits to
sequences for PUCCH format 0

  ---------------- ---------------- ---------------- ---------------- ----------------
  HARQ-ACK Value   {0, 0}           {0, 1}           {1, 1}           {1, 0}

  **Sequence       $$m_{CS} = 0$$   $$m_{CS} = 3$$   $$m_{CS} = 6$$   $$m_{CS} = 9$$
  cyclic shift**                                                      
  ---------------- ---------------- ---------------- ---------------- ----------------

If a UE transmits a PUCCH with HARQ-ACK information using PUCCH format
1, the UE is provided a value for
![](media/image67.wmf){width="0.19791666666666666in" height="0.21875in"}
by *initialCyclicShift* of *PUCCH-format1* or, if *initialCyclicShift*
is not provided, by the initial cyclic shift index as described in
clause 9.2.1.

If a UE transmits a PUCCH with $O_{ACK}$ HARQ-ACK information bits and
$O_{CRC}$ bits using PUCCH format 2 or PUCCH format 3 in a PUCCH
resource that includes $M_{RB}^{\text{PUCCH}}$ PRBs, the UE determines a
number of PRBs $M_{RB,min}^{\text{PUCCH}}$ for the PUCCH transmission to
be the minimum number of PRBs, that is smaller than or equal to a number
of PRBs $M_{RB}^{\text{PUCCH}}$ provided respectively by *nrofPRBs* of
*PUCCH-format2* or *nrofPRBs* of *PUCCH-format3* and start from the
first PRB from the number of PRBs, that results to
$\left( O_{\text{ACK}} + O_{\text{CRC}} \right) \leq M_{RB,min}^{\text{PUCCH}} \cdot N_{\text{sc,ctrl}}^{\text{RB}} \cdot N_{\text{symb-UCI}}^{\text{PUCCH}} \cdot Q_{m} \cdot r$
and, if $M_{RB}^{\text{PUCCH}} > 1$,
$\left( O_{\text{ACK}} + O_{\text{CRC}} \right) > \left( M_{RB,min}^{\text{PUCCH}} - 1 \right) \cdot N_{\text{sc,ctrl}}^{\text{RB}} \cdot N_{\text{symb-UCI}}^{\text{PUCCH}} \cdot Q_{m} \cdot r$,
where $N_{\text{sc,ctrl}}^{\text{RB}}$,
$N_{\text{symb-UCI}}^{\text{PUCCH}}$, $Q_{m}$, and $r$ are defined in
clause 9.2.5.2. For PUCCH format 3, if $M_{RB,min}^{\text{PUCCH}}$ is
not equal $2^{\alpha_{2}} \cdot 3^{\alpha_{3}} \cdot 5^{\alpha_{5}}$
according to \[4, TS 38.211\], $M_{RB,min}^{\text{PUCCH}}$ is increased
to the nearest allowed value of *nrofPRBs* \[12, TS 38.331\]. If
$\left( O_{\text{ACK}} + O_{\text{CRC}} \right) > \left( M_{RB}^{\text{PUCCH}} - 1 \right) \cdot N_{\text{sc,ctrl}}^{\text{RB}} \cdot N_{\text{symb-UCI}}^{\text{PUCCH}} \cdot Q_{m} \cdot r$,
the UE transmits the PUCCH over $M_{RB}^{\text{PUCCH}}$ PRBs.

If a UE is provided a first interlace of
$M_{\text{Interlace,0}}^{\text{PUCCH}}$ PRBs by *interlace0* in
*InterlaceAllocation* and transmits a PUCCH with $O_{\text{ACK}}$
HARQ-ACK information bits and $O_{\text{CRC}}$ bits using PUCCH format 2
or PUCCH format 3, the UE transmits the PUCCH over the first interlace
if
$\left( O_{\text{ACK}} + O_{\text{CRC}} \right) \leq M_{\text{Interlace,0}}^{\text{PUCCH}} \cdot N_{\text{sc,ctrl}}^{\text{RB}} \cdot N_{\text{symb-UCI}}^{\text{PUCCH}} \cdot Q_{m} \cdot r$;
otherwise, if the UE is provided a second interlace by *interlace1* in
*PUCCH-format2* or *PUCCH-format3*, the UE transmits the PUCCH over the
first and second interlaces.