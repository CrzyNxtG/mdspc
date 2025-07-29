### 7.2.1 UE behaviour

If a UE transmits a PUCCH on active UL BWP $b$ of carrier $f$ in the
primary cell $c$ using PUCCH power control adjustment state with index
$l$

\- if the UE is indicated a first *TCI-State* or *TCI-UL-State* and a
second *TCI-State* or *TCI-UL-State*, and is configured with
*multipanelSFN-Scheme*, and the UE determines to apply both the first
*TCI-State* or *TCI-UL-State* and the second *TCI-State* or
*TCI-UL-S*tate in PUCCH transmission occasion $i$, the UE determines the
PUCCH transmission power $P_{\text{PUCCH},b,f,c,\ k}(i,j,q_{d},l)$ for
the k-th indicated *TCI-State* or *TCI-UL-State* as

$P_{\text{PUCCH},b,f,c,k}\left( i,q_{u},q_{d},l \right) = \min\begin{Bmatrix}
P_{\text{CMAX},f,c,k}(i) \\
P_{O\_ PUCCH,b,f,c}(j) + 10\log_{10}\left( 2^{\mu} \bullet M_{RB,b,f,c}^{PUCCH}(i) \right) + {PL}_{b,f,c}\left( q_{d} \right) + \mathrm{\Delta}_{F\_ PUCCH}(F) + {\mathrm{\Delta}_{TF,b,f,c}(i) + g}_{b,f,c}(i,l)\ \ 
\end{Bmatrix}$ \[dBm\]

\- else, the UE determines the PUCCH transmission power
$P_{\text{PUCCH},b,f,c}(i,q_{u},q_{d},l)$ in PUCCH transmission occasion
$i$ as

$P_{\text{PUCCH},b,f,c}\left( i,q_{u},q_{d},l \right) = \min\begin{Bmatrix}
P_{\text{CMAX},f,c}(i) \\
P_{O\_ PUCCH,b,f,c}\left( q_{u} \right) + 10\log_{10}\left( 2^{\mu} \bullet M_{RB,b,f,c}^{PUCCH}(i) \right) + {PL}_{b,f,c}\left( q_{d} \right) + \mathrm{\Delta}_{F\_ PUCCH}(F) + {\mathrm{\Delta}_{TF,b,f,c}(i) + g}_{b,f,c}(i,l)\ \ 
\end{Bmatrix}$ \[dBm\]

where

\- $P_{\text{CMAX},f,c,k}(i)$ is the UE configured maximum output power
for the k-th indicated *TCI-State* or *TCI-UL-State* defined in \[8-2,
TS 38.101-2\] for carrier $f$ of serving cell $c$ in PUCCH transmission
occasion $i$ .

\- $P_{\text{CMAX},f,c}(i)$ is the UE configured maximum output power
defined in \[8-1, TS 38.101-1\], \[8-2, TS 38.101-2\], \[8-3, TS
38.101-3\] and \[8-5, TS 38.101-5\] for carrier $f$ of primary cell $c$
in PUCCH transmission occasion $i$

\- $P_{\text{O\_PUCCH},b,f,c}(q_{u})$ is a parameter composed of the sum
of a component $P_{\text{O\_NOMINAL,PUCCH}}$, provided by *p0-nominal*,
or $P_{\text{O\_NOMINAL,PUCCH}} = 0$ dBm if *p0-nominal* is not
provided, for carrier $f$ of primary cell $c$ and, if provided, a
component $P_{\text{O\_UE\_PUCCH}}(q_{u})$ provided by *p0-PUCCH-Value*
in *P0-PUCCH* for active UL BWP $b$ of carrier $f$ of primary cell $c$,
where $0 \leq q_{u} < Q_{u}$. $Q_{u}$ is a size for a set of
$P_{\text{O\_UE\_PUCCH}}$ values provided by *maxNrofPUCCH-P0-PerSet*.
The set of $P_{\text{O\_UE\_PUCCH}}$ values is provided by *p0-Set*. If
*p0-Set* is not provided to the UE, $P_{O\_ UE\_ PUCCH}(q_{u}) = 0$,
$0 \leq q_{u} < Q_{u}$

\- If the UE is provided *PUCCH-SpatialRelationInfo*, the UE obtains a
mapping, by an index provided by *p0-PUCCH-Id*, between a set of
*pucch-SpatialRelationInfoId* values and a set of *p0-PUCCH-Value*
values. If the UE is provided more than one values for
*pucch-SpatialRelationInfoId* and the UE receives an activation command
\[11, TS 38.321\] indicating a value of *pucch-SpatialRelationInfoId*,
the UE determines the *p0-PUCCH-Value* value through the link to a
corresponding *p0-PUCCH-Id* index. The UE applies the activation command
in the first slot that is after slot
$k + 3 \cdot N_{slot}^{subframe,\mu}$ where $k$ is the slot where the UE
would transmit a PUCCH with HARQ-ACK information for the PDSCH providing
the activation command and $\mu$ is the SCS configuration for the PUCCH

\- If the UE is provided more than one sets of power control parameters
for operation in FR1, and the UE receives an activation command \[11, TS
38.321\] indicating one or two of the more than one sets of power
control parameters, the UE determines *p0-PUCCH-Value* value according
to the corresponding one or two sets of power control parameters. The UE
applies the activation command in the first slot that is after slot
$k + 3 \cdot N_{slot}^{subframe,\mu}$ where $k$ is the slot where the UE
would transmit a PUCCH with HARQ-ACK information for the PDSCH providing
the activation command and $\mu$ is the SCS configuration for the PUCCH.

\- If the UE is not provided *PUCCH-SpatialRelationInfo* and is not
provided more than one sets of power control parameters for operation in
FR1, the UE obtains the *p0-PUCCH-Value* value from the *P0-PUCCH* with
*p0-PUCCH-Id* value equal to the minimum *p0-PUCCH-Id* value in *p0-Set*

\- $M_{RB,b,f,c}^{PUCCH}(i)$ is a bandwidth of the PUCCH resource
assignment expressed in number of resource blocks for PUCCH transmission
occasion $i$ on active UL BWP $b$ of carrier $f$ of primary cell $c$ and
$\mu$ is a SCS configuration defined in \[4, TS 38.211\]

\- ${PL}_{b,f,c}(q_{d})$ is a downlink pathloss estimate in dB
calculated by the UE using RS resource index $q_{d}$ as described in
clause 7.1.1 for the active DL BWP $b$ of carrier $f$ of the primary
cell $c$ as described in clause 12

\- If the UE is not provided *pathlossReferenceRSs* and
*enableDefaultBeamPL-ForPUCCH*, or before the UE is provided dedicated
higher layer parameters, the UE calculates ${PL}_{b,f,c}(q_{d})$ using a
RS resource obtained from an SS/PBCH block with same SS/PBCH block index
as the one the UE uses to obtain *MIB*, or using the SS/PBCH block the
UE acquired the time and frequency synchronization for a secondary cell.

\- If the UE is provided a number of RS resource indexes, the UE
calculates ${PL}_{b,f,c}(q_{d})$ using RS resource with index $q_{d}$,
where $0 \leq q_{d} < Q_{d}$. $Q_{d}$ is a size for a set of RS
resources provided by *maxNrofPUCCH-PathlossReferenceRSs*. The set of RS
resources is provided by *pathlossReferenceRSs*. The set of RS resources
can include one or both of a set of SS/PBCH block indexes, each provided
by *ssb-Index* in *PUCCH-PathlossReferenceRS* when a value of a
corresponding *pucch-PathlossReferenceRS-Id* maps to a SS/PBCH block
index, and a set of CSI-RS resource indexes, each provided by
*csi-RS-Index* when a value of a corresponding
*pucch-PathlossReferenceRS-Id* maps to a CSI-RS resource index. The UE
identifies a RS resource in the set of RS resources to correspond either
to a SS/PBCH block index or to a CSI-RS resource index as provided by
*pucch-PathlossReferenceRS-Id* in *PUCCH-PathlossReferenceRS*

\- If the UE is provided *pathlossReferenceRSs* and
*PUCCH-SpatialRelationInfo*, the UE obtains a mapping, by indexes
provided by corresponding values of *pucch-PathlossReferenceRS-Id*,
between a set of *pucch-SpatialRelationInfoId* values and a set of
*referenceSignal* values provided by *PUCCH-PathlossReferenceRS*. If the
UE is provided more than one values for *pucch-SpatialRelationInfoId*
and the UE receives an activation command \[11, TS 38.321\] indicating a
value of *pucch-SpatialRelationInfoId*, the UE determines the
*referenceSignal* value in *PUCCH-PathlossReferenceRS* through the link
to a corresponding *pucch-PathlossReferenceRS-Id* index. The UE applies
the activation command in the first slot that is after slot
$k + 3 \cdot N_{slot}^{subframe,\mu}$ where $k$ is the slot where the UE
would transmit a PUCCH with HARQ-ACK information for the PDSCH providing
the activation command and $\mu$ is the SCS configuration for the PUCCH

\- If *PUCCH-SpatialRelationInfo* includes *servingCellId* indicating a
serving cell, the UE receives the RS for resource index $q_{d}$ on the
active DL BWP of the serving cell

\- If the UE is provided *pathlossReferenceRSs* and more than one sets
of power control parameters for operation in FR1, and the UE receives an
activation command \[11, TS 38.321\] indicating one or two of the more
than one sets of power control parameters, the UE determines the
*referenceSignal* values in *PUCCH-PathlossReferenceRS* that are
indicated in the one or two sets of power control parameter

\- If the UE is provided *pathlossReferenceRSs* and is not provided
*PUCCH-SpatialRelationInfo* and is not provided more than one sets of
power control parameters for operation in FR1, the UE obtains the
*referenceSignal* value in *PUCCH-PathlossReferenceRS* from the
*pucch-PathlossReferenceRS-Id* with index 0 in
*PUCCH-PathlossReferenceRS* where the RS resource is either on the
primary cell or, if provided, on a serving cell indicated by a value of
*pathlossReferenceLinking*

\- If the UE

\- is not provided *pathlossReferenceRSs*, and

\- is not provided *PUCCH-SpatialRelationInfo,* and

\- is provided *enableDefaultBeamPL-ForPUCCH*, and

\- is not provided *coresetPoolIndex* value of 1 for any CORESET, or is
provided *coresetPoolIndex* value of 1 for all CORESETs, in
*ControlResourceSet* and no codepoint of a TCI field, if any, in a DCI
format of any search space set maps to two TCI states \[5, TS 38.212\]

the UE determines a RS resource index $q_{d}$ providing a periodic RS
resource configured with *qcl-Type* set to \'typeD\' in the TCI state or
the QCL assumption of a CORESET with the lowest index in the active DL
BWP of the primary cell. If the CORESET has two activated TCI states, as
described in clause 10.1, the UE determines the RS resource index
$q_{d}$ based on the first activated TCI state. For a PUCCH transmission
over multiple slots, a same $q_{d}$ applies to the PUCCH transmission in
each of the multiple slots.

\- The parameter $\Delta_{\text{F\_PUCCH}}(F)$ is a value of
*deltaF-PUCCH-f0* for PUCCH format 0, *deltaF-PUCCH-f1* for PUCCH format
1, *deltaF-PUCCH-f2* for PUCCH format 2, *deltaF-PUCCH-f3* for PUCCH
format 3, and *deltaF-PUCCH-f4* for PUCCH format 4, if provided;
otherwise $\Delta_{\text{F\_PUCCH}}(F) = 0$.

\- $\mathrm{\Delta}_{TF,b,f,c}(i)$ is a PUCCH transmission power
adjustment component on active UL BWP $b$ of carrier $f$ of primary cell
$c$

\- For a PUCCH transmission using PUCCH format 0 or PUCCH format 1,
$\mathrm{\Delta}_{TF,b,f,c}(i) = 10\log_{10}\left( \frac{N_{ref}^{PUCCH}}{N_{symb}^{PUCCH}(i)} \right) + \mathrm{\Delta}_{UCI}(i)$
where

\- $N_{symb}^{PUCCH}(i)$ is a number of PUCCH format 0 symbols or PUCCH
format 1 symbols for the PUCCH transmission as described in clause 9.2.

\- $N_{ref}^{PUCCH} = 2$ for PUCCH format 0

\- $N_{ref}^{PUCCH} = N_{symb}^{slot}$ for PUCCH format 1

\- For PUCCH format 0, $\mathrm{\Delta}_{UCI}(i) = 0$

\- For PUCCH format 1

\- if the PUCCH transmission provides multicast HARQ-ACK information
according to the second HARQ-ACK reporting mode as described in clause
18, $\mathrm{\Delta}_{UCI}(i) = 0$

\- otherwise,
$\mathrm{\Delta}_{UCI}(i) = 10\log_{10}\left( O_{UCI}(i) \right)$, where
$O_{UCI}(i)$ is a number of UCI bits in PUCCH transmission occasion $i$

\- For a PUCCH transmission using PUCCH format 2 or PUCCH format 3 or
PUCCH format 4 and for a number of UCI bits smaller than or equal to 11,
$\mathrm{\Delta}_{TF,b,f,c}(i) = 10\log_{10}\left( K_{1} \cdot \frac{\left( n_{HARQ - ACK}(i) + O_{SR}(i) + O_{CSI}(i) \right)}{N_{RE}(i)} \right)$,
where

\- $K_{1} = 6$

\- $n_{HARQ - ACK}(i)$ is a number of HARQ-ACK information bits that the
UE determines as described in clause 9.1.2.1 or 16.5.1.1 for Type-1
HARQ-ACK codebook and as described in clause 9.1.3.1 or 9.1.3.3 or
16.5.2.1 for Type-2 HARQ-ACK codebook, or as described in clause 9.1.5
for HARQ-ACK codebook retransmission, or as described in clause 9.2.5.4
for deferring HARQ-ACK for SPS PDSCH. $n_{HARQ - ACK}(i)$ is the same as
$O_{ACK}(i)$ as described in clause 9.1.4 for Type-3 HARQ-ACK codebook.
If the UE is not provided any of *pdsch-HARQ-ACK-Codebook*,
*pdsch-HARQ-ACK-Codebook-r16*, or *pdsch-HARQ-ACK-OneShotFeedback*,
$n_{HARQ - ACK}(i) = 1$ if the UE includes a HARQ-ACK information bit in
the PUCCH transmission; otherwise, $n_{HARQ - ACK}(i) = 0$

\- $O_{SR}(i)$ is a number of SR information bits that the UE determines
as described in clause 9.2.5.1

\- $O_{CSI}(i)$ is a number of CSI information bits that the UE
determines as described in clause 9.2.5.2

\- $N_{RE}(i)$ is a number of resource elements determined as
$N_{RE}(i) = M_{RB,b,f,c}^{PUCCH}(i) \cdot N_{sc,ctrl}^{RB}(i){\cdot N}_{symb - UCI,b,f,c}^{PUCCH}(i)$,
where $N_{sc,ctrl}^{RB}(i)$ is a number of subcarriers per resource
block excluding subcarriers used for DM-RS transmission, and
$N_{symb - UCI,b,f,c}^{PUCCH}(i)$ is a number of symbols excluding
symbols used for DM-RS transmission, as defined in clause 9.2.5.2, for
PUCCH transmission occasion $i$ on active UL BWP $b$ of carrier $f$ of
primary cell $c$

\- For a PUCCH transmission using PUCCH format 2 or PUCCH format 3 or
PUCCH format 4 and for a number of UCI bits larger than 11,
$\mathrm{\Delta}_{TF,b,f,c}(i) = 10\log_{10}\left( 2^{BPRE \cdot K_{2}} - 1 \right)$,
where

\- $K_{2} = 2.4$

\-
$BPRE(i) = \frac{\left( O_{ACK}(i) + O_{SR}(i) + O_{CSI}(i) + O_{CRC}(i) \right)}{N_{RE}}(i)$

\- $O_{ACK}(i)$ is a number of HARQ-ACK information bits that the UE
determines as described in clause 9.1.2.1 or 16.5.1.1 for Type-1
HARQ-ACK codebook and as described in clause 9.1.3.1 or 9.1.3.3 or
16.5.2.1 for Type-2 HARQ-ACK codebook, or as described in clause 9.1.4
for Type-3 HARQ-ACK codebook, or as described in clause 9.1.5 for
HARQ-ACK codebook retransmission, or as described in clause 9.2.5.4 for
deferring HARQ-ACK for SPS PDSCH. If the UE is not provided any of
*pdsch-HARQ-ACK-Codebook*, *pdsch-HARQ-ACK-Codebook-r16*, or
*pdsch-HARQ-ACK-OneShotFeedback*, $O_{ACK} = 1$ if the UE includes a
HARQ-ACK information bit in the PUCCH transmission; otherwise,
$O_{ACK} = 0$

\- $O_{SR}(i)$ is a number of SR information bits that the UE determines
as described in clause 9.2.5.1

\- $O_{CSI}(i)$ is a number of CSI information bits that the UE
determines as described in clause 9.2.5.2

\- $O_{CRC}(i)$ is a number of CRC bits that the UE determines as
described in clause 9.2

\- $N_{RE}(i)$ is a number of resource elements that the UE determines
as
$N_{RE}(i) = M_{RB,b,f,c}^{PUCCH}(i) \cdot N_{sc,ctrl}^{RB}(i){\cdot N}_{symb - UCI,b,f,c}^{PUCCH}(i)$,
where $N_{sc,ctrl}^{RB}(i)$ is a number of subcarriers per resource
block excluding subcarriers used for DM-RS transmission, and
$N_{symb - UCI,b,f,c}^{PUCCH}(i)$ is a number of symbols excluding
symbols used for DM-RS transmission, as defined in clause 9.2.5.2, for
PUCCH transmission occasion $i$ on active UL BWP $b$ of carrier $f$ of
primary cell $c$.

\- For the PUCCH power control adjustment state $g_{b,f,c}(i,l)$ for
active UL BWP $b$ of carrier $f$ of primary cell $c$ and PUCCH
transmission occasion $i$

\- $\delta_{PUCCH,b,f,c}(i,l)$ is a TPC command value included in a DCI
format associated with the PUCCH transmission for active UL BWP $b$ of
carrier $f$ of the primary cell $c$ that the UE detects for PUCCH
transmission occasion $i$, or is jointly coded with other TPC commands
in a DCI format 2_2 with CRC scrambled by TPC-PUCCH-RNTI \[5, TS
38.212\], as described in clause 11.3

\- $l \in \left\{ 0,1 \right\}$ if the UE is provided
*twoPUCCH-PC-AdjustmentStates* and *PUCCH-SpatialRelationInfo*, or more
than one sets of power control parameters for operation in FR1, $l = 0$
if the UE is not provided *twoPUCCH-PC-AdjustmentStates* or
*PUCCH-SpatialRelationInfo* and more than one sets of power control
parameters, and $l = 0$ if the PUCCH transmission provides only
multicast HARQ-ACK information

\- If the UE obtains a TPC command value from a DCI format associated
with the PUCCH transmission and if the UE is provided
*PUCCH-SpatialRelationInfo*, the UE obtains a mapping, by an index
provided by *p0-PUCCH-Id*, between a set of
*pucch-SpatialRelationInfoId* values and a set of values for
*closedLoopIndex* that provide the $l$ value(s). If the UE receives an
activation command indicating a value of *pucch-SpatialRelationInfoId*,
the UE determines the value *closedLoopIndex* that provides the value of
$l$ through the link to a corresponding *p0-PUCCH-Id* index

\- If the UE obtains a TPC command value from a DCI format associated
with the PUCCH transmission, and if the UE is provided more than one
sets of power control parameters for operation in FR1, and if the UE
receives an activation command \[11, TS 38.321\] indicating one or two
sets of the more than one sets of power control parameters, the UE
determines the value of $l$ based on the *closedLoopIndex* value in the
one or two sets of power control parameters

\- If the UE obtains a TPC command from a DCI format 2_2 with CRC
scrambled by a TPC-PUCCH-RNTI, the $l$ value is provided by the closed
loop indicator field in DCI format 2_2

\- If the UE transmits the PUCCH with
$N_{\text{PUCCH}}^{\text{repeat}} > 1$ repetitions, as described in
clause 9.2.6, and the UE is provided *twoPUCCH-PC-AdjustmentStates* by
*pucch-PowerControl*

\- If the DCI format includes two TPC command values and the PUCCH
resource of the PUCCH transmission is associated with $l = 0$ and
$l = 1$, the UE applies the first TPC command value for $l = 0$ and
applies the second TPC command value for $l = 1$

\- If the DCI format includes two TPC command values and the PUCCH
resource of the PUCCH transmission is associated with $l = 0$, the UE
applies the first TPC command value for $l = 0$ and ignores the second
TPC command value

\- If the DCI format includes two TPC command values and the PUCCH
resource of the PUCCH transmission is associated with $l = 1$, the UE
applies the second TPC command value for $l = 1$ and ignores the first
TPC command value

\- If the DCI format includes one TPC command value, the UE applies the
TPC command value for all $l$ associated with the PUCCH resource of the
PUCCH transmission

\-
$g_{b,f,c}(i,l) = g_{b,f,c}\left( i - i_{0},l \right) + \sum_{m = 0}^{\text{C}\left( C_{i} \right) - 1}{\delta_{PUCCH,b,f,c}(m,l)}$
is the current PUCCH power control adjustment state $l$ for active UL
BWP $b$ of carrier $f$ of primary cell $c$ and PUCCH transmission
occasion $i$, where

\- The $\delta_{PUCCH,b,f,c}$ values are given in Table 7.1.2-1

\-
$\sum_{m = 0}^{\text{C}\left( C_{i} \right) - 1}{\delta_{PUCCH,b,f,c}(m,l)}$
is a sum of TPC command values in a set $C_{i}$ of TPC command values
with cardinality $\text{C}\left( C_{i} \right)$ that the UE receives
between $K_{PUCCH}\left( i - i_{0} \right) - 1$ symbols before PUCCH
transmission occasion $i - i_{0}$ and
![](media/image16.wmf){width="0.6145833333333334in"
height="0.19791666666666666in"} symbols before PUCCH transmission
occasion $i$ on active UL BWP $b$ of carrier $f$ of primary cell $c$ for
PUCCH power control adjustment state, where $i_{0} > 0$ is the smallest
integer for which $K_{PUCCH}\left( i - i_{0} \right)$ symbols before
PUCCH transmission occasion $i - i_{0}$ is earlier than $K_{PUCCH}(i)$
symbols before PUCCH transmission occasion $i$

\- If the PUCCH transmission is in response to a detection by the UE of
a DCI format, $K_{PUCCH}(i)$ is a number of symbols for active UL BWP
$b$ of carrier $f$ of primary cell $c$ after a last symbol of a
corresponding PDCCH reception and before a first symbol of the PUCCH
transmission

\- If the PUCCH transmission is not in response to a detection by the UE
of a DCI format, $K_{PUCCH}(i)$ is a number of $K_{PUCCH,min}$ symbols
equal to the product of a number of symbols per slot, $N_{symb}^{slot}$,
and the minimum of the values provided by *k2* in *PUSCH-ConfigCommon*
for active UL BWP $b$ of carrier $f$ of primary cell $c$

> \- If the first symbol of the PUCCH transmission occasion occurs
> within $T_{proc,2}$ after a last symbol of a PDCCH reception where the
> UE detects the DCI format providing the TPC command, the UE may
> postpone the application of the TPC command until the above condition
> is not valid. $T_{proc,2}$ is the PUSCH preparation time for the
> corresponding UE processing capability \[6, TS 38.214\] assuming
> $d_{2,1} = 0$, and $\mu$ corresponds to the smallest SCS configuration
> between the SCS configuration of the PDCCH carrying the DCI format and
> the SCS configuration of the PUCCH.

\- If the UE has reached maximum power for active UL BWP $b$ of carrier
$f$ of primary cell $c$ at PUCCH transmission occasion $i - i_{0}$ and
$\sum_{m = 0}^{\text{C}\left( C_{i} \right) - 1}{\delta_{PUCCH,b,f,c}(m,l)} \geq 0$,
then $g_{b,f,c}(i,l) = g_{b,f,c}\left( i - i_{0},l \right)$

\- If UE has reached minimum power for active UL BWP $b$ of carrier $f$
of primary cell $c$ at PUCCH transmission occasion $i - i_{0}$ and
$\sum_{m = 0}^{\text{C}\left( C_{i} \right) - 1}{\delta_{PUCCH,b,f,c}(m,l)} \leq 0$,
then $g_{b,f,c}(i,l) = g_{b,f,c}\left( i - i_{0},l \right)$

\- If a configuration of a
$P_{\text{O\_PUCCH},b,f,c}\left( q_{u} \right)$ value for a
corresponding PUCCH power control adjustment state $l$ for active UL BWP
$b$ of carrier $f$ of primary cell $c$ is provided by higher layers,

\- $g_{b,f,c}(k,l) = 0,\ \ k = 0,1,\ldots,i$

\- if the UE is provided *PUCCH-SpatialRelationInfo*, the UE determines
the value of $l$ from the value of $q_{u}$ based on a
*pucch-SpatialRelationInfoId* value associated with the *p0-PUCCH-Id*
value corresponding to $q_{u}$ and with the *closedLoopIndex* value
corresponding to $l$;

\- else, if the UE is provided more than one sets of power control
parameters for operation in FR1, and if the UE receives an activation
command for a PUCCH resource that indicates one or two sets of the more
than one sets of power control parameters, the UE determines the value
of $l$ based on the *closedLoopIndex* value in the one or two sets of
power control parameters;

\- else, $l = 0$

\- Else,

\-
$g_{b,f,c}(0,l) = {\mathrm{\Delta}P_{rampup,b,f,c} + \delta}_{b,f,c}$,
where $l = 0$, and $\delta_{b,f,c}$ is

\- the TPC command value indicated in a random access response grant
corresponding to a PRACH transmission according to Type-1 random access
procedure, or in a random access response grant corresponding to MsgA
transmissions according to Type-2 random access procedure with RAR
message(s) for fallbackRAR, or

\- the TPC command value indicated in a successRAR corresponding to MsgA
transmissions for Type-2 random access procedure, or

\- the TPC command value in a DCI format with CRC scrambled by C-RNTI or
MCS-C-RNTI that the UE detects in a first PDCCH reception in a search
space set provided by *recoverySearchSpaceId* if the PUCCH transmission
is a first PUCCH transmission after 28 symbols from a last symbol of the
first PDCCH reception,

> and, if the UE transmits PUCCH on active UL BWP $b$ of carrier $f$ of
> primary cell $c$,

$\mathrm{\Delta}P_{rampup,b,f,c} = min\left\lbrack \max\left( 0,P_{CMAX,f,c} - \left( P_{\text{O\_PUCCH},b,f,c} + {PL}_{b,f,c}(q_{d}) + \mathrm{\Delta}_{F\_ PUCCH} + \mathrm{\Delta}_{TF,b,f,c} + \delta_{b,f,c} \right) \right),\mathrm{\Delta}P_{rampup\_ requested,b,f,c} \right\rbrack$;

otherwise,

$\mathrm{\Delta}P_{rampup,b,f,c} = min\left\lbrack \max\left( 0,P_{CMAX,f,c} - \left( P_{\text{O\_PUCCH},b,f,c} + {PL}_{b,f,c}(q_{d}) \right) \right),\mathrm{\Delta}P_{rampup\_ requested,b,f,c} \right\rbrack$
where $\mathrm{\Delta}P_{rampup\_ requested,b,f,c}$ is provided by
higher layers and corresponds to the total power ramp-up requested by
higher layers from the first to the last preamble for active UL BWP $b$
of carrier $f$ of primary cell $c$, and $\mathrm{\Delta}_{F\_ PUCCH}$
corresponds to PUCCH format 0 or PUCCH format 1

Table 7.2.1-1: Mapping of TPC Command Field in a DCI format to
accumulated
$\mathbf{\delta}_{\mathbf{PUCCH}\mathbf{,b}\mathbf{,}\mathbf{f}\mathbf{,}\mathbf{c}}$
values

  ----------------------------------------------------------------------------------------------------------------------
  TPC Command Field              Accumulated
                                 $\mathbf{\delta}_{\mathbf{PUCCH}\mathbf{,b}\mathbf{,}\mathbf{f}\mathbf{,}\mathbf{c}}$
                                 \[dB\]
  ------------------------------ ---------------------------------------------------------------------------------------
  0                              -1

  1                              0

  2                              1

  3                              3
  ----------------------------------------------------------------------------------------------------------------------