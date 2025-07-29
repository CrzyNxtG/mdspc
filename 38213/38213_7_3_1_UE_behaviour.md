### 7.3.1 UE behaviour

If a UE transmits SRS based on a configuration by *SRS-ResourceSet* on
active UL BWP $b$ of carrier $f$ of serving cell $c$ using SRS power
control adjustment state with index $l$, the UE determines the SRS
transmission power $P_{\text{SRS},b,f,c}(i,q_{s},l)$ of each SRS
resource in SRS transmission occasion $i$ as

![](media/image17.wmf){width="5.791666666666667in"
height="0.5104166666666666in"} \[dBm\]

where,

\- $P_{\text{CMAX},f,c}(i)$ is the UE configured maximum output power
defined in \[8, TS 38.101-1\], \[8-2, TS 38.101-2\], \[TS 38.101-3\] and
\[8-5, TS 38.101-5\] for carrier $f$ of serving cell $c$ in SRS
transmission occasion $i$

\- $P_{\text{O\_SRS},b,f,c}(q_{s})$ is provided by *p0* for active UL
BWP $b$ of carrier $f$ of serving cell $c$ and SRS resource set $q_{s}$
provided by *SRS-ResourceSet* and *SRS-ResourceSetId*

\- $M_{\text{SRS},b,f,c}(i)$ is a SRS bandwidth expressed in number of
resource blocks for SRS transmission occasion $i$ on active UL BWP $b$
of carrier $f$ of serving cell $c$ and $\mu$ is a SCS configuration
defined in \[4, TS 38.211\]

\- $\alpha_{\text{SRS},b,f,c}(q_{s})$ is provided by *alpha* for active
UL BWP $b$ of carrier $f$ of serving cell $c$ and SRS resource set
$q_{s}$

\- ${PL}_{b,f,c}(q_{d})$ is a downlink pathloss estimate in dB
calculated by the UE using RS resource index $q_{d}$ as described in
clause 7.1.1 for the active DL BWP of serving cell $c$ and SRS resource
set $q_{s}$ \[6, TS 38.214\]. The RS resource index $q_{d}$ is provided
by *pathlossReferenceRS* associated with the SRS resource set $q_{s}$
and is either an *ssb-Index* providing a SS/PBCH block index or a
*csi-RS-Index* providing a CSI-RS resource index. If the UE is provided
*enablePL-RS-UpdateForPUSCH-SRS*, a MAC CE \[11, TS 38.321\] can provide
by *SRS-PathlossReferenceRS-Id* a corresponding RS resource index
$q_{d}$ for aperiodic or semi-persistent SRS resource set $q_{s}$

\- If the UE is not provided *pathlossReferenceRS* or
*SRS-PathlossReferenceRS-Id* and if the UE is not provided
*enableDefaultBeamPL-ForSRS*, or before the UE is provided dedicated
higher layer parameters, the UE calculates ${PL}_{b,f,c}(q_{d})$ using a
RS resource obtained from an SS/PBCH block with same SS/PBCH block index
as the one the UE uses to obtain *MIB*, or using the SS/PBCH block the
UE acquired the time and frequency synchronization for a secondary cell.

\- If the UE is provided *pathlossReferenceLinking*, the RS resource is
on a serving cell indicated by a value of *pathlossReferenceLinking*

\- If the UE

\- is not provided *pathlossReferenceRS* or
*SRS-PathlossReferenceRS-Id*,

\- is not provided *spatialRelationInfo*, and

\- is provided *enableDefaultBeamPL-ForSRS*, and

\- is not provided *coresetPoolIndex* value of 1 for any CORESET, or is
provided *coresetPoolIndex* value of 1 for all CORESETs, in
*ControlResourceSet* and no codepoint of a TCI field, if any, in a DCI
format of any search space set maps to two TCI states \[5, TS 38.212\]

the UE determines a RS resource index $q_{d}$ providing a periodic RS
resource configured with *qcl-Type* set to \'typeD\' in

\- the TCI state or the QCL assumption of a CORESET with the lowest
index in the active DL BWP, if CORESETs are provided in the active DL
BWP of serving cell $c$. If the CORESET has two activated TCI states, as
described in clause 10.1, the UE determines the RS resource index
$q_{d}$ based on the first TCI state.

\- the active PDSCH TCI state with lowest ID \[6, TS 38.214\] in the
active DL BWP, if CORESETs are not provided in the active DL BWP of
serving cell $c$

\- For the SRS power control adjustment state for active UL BWP $b$ of
carrier $f$ of serving cell $c$ and SRS transmission occasion $i$

\- $h_{b,f,c}(i,l) = f_{b,f,c}(i,l)$, where $f_{b,f,c}(i,l)$ is the
current PUSCH power control adjustment state as described in clause
7.1.1, if *srs-PowerControlAdjustmentStates* indicates a same power
control adjustment state for SRS transmissions and PUSCH transmissions;
or

\- ![](media/image18.wmf){width="2.222916666666667in"
height="0.3840277777777778in"} if the UE is not configured for PUSCH
transmissions on active UL BWP $b$ of carrier $f$ of serving cell $c$,
or if *srs-PowerControlAdjustmentStates* indicates separate power
control adjustment states between SRS transmissions and PUSCH
transmissions, and if *tpc-Accumulation* is not provided, where

\- The $\delta_{SRS,b,f,c}$ values are given in Table 7.1.1-1

\- $\delta_{SRS,b,f,c}(m)$ is jointly coded with other TPC commands in a
PDCCH with DCI format 2_3, as described in clause 11.4

\-
$\sum_{m = 0}^{\text{C}\left( S_{i} \right) - 1}{\delta_{SRS,b,f,c}(m)}$
is a sum of TPC command values in a set $S_{i}$ of TPC command values
with cardinality $\text{C}\left( S_{i} \right)$ that the UE receives
between $K_{SRS}\left( i - i_{0} \right) - 1$ symbols before SRS
transmission occasion $i - i_{0}$ and $K_{SRS}(i)$ symbols before SRS
transmission occasion $i$ on active UL BWP $b$ of carrier $f$ of serving
cell $c$ for SRS power control adjustment state, where $i_{0} > 0$ is
the smallest integer for which $K_{SRS}(i - i_{0})$ symbols before SRS
transmission occasion $i - i_{0}$ is earlier than $K_{SRS}(i)$ symbols
before SRS transmission occasion $i$

\- if the SRS transmission is aperiodic, $K_{SRS}(i)$ is a number of
symbols for active UL BWP $b$ of carrier $f$ of serving cell $c$ after a
last symbol of a corresponding PDCCH triggering the SRS transmission and
before a first symbol of the SRS transmission

\- if the SRS transmission is semi-persistent or periodic, $K_{SRS}(i)$
is a number of $K_{SRS,min}$ symbols equal to the product of a number of
symbols per slot, $N_{symb}^{slot}$, and the minimum of the values
provided by *k2* in *PUSCH-ConfigCommon* for active UL BWP $b$ of
carrier $f$ of serving cell $c$

\- If the first symbol of the SRS transmission occasion occurs within
$T_{proc,2}$ after a last symbol of a PDCCH reception where the UE
detects the DCI format providing the TPC command, the UE may postpone
the application of the TPC until the above condition is not valid.
$T_{proc,2}$ is the PUSCH preparation time for the corresponding UE
processing capability \[6, TS 38.214\] assuming $d_{2,1} = 0$, and $\mu$
corresponds to the smallest SCS configuration between the SCS
configuration of the PDCCH carrying the DCI format and the SCS
configuration of the SRS.

\- If the UE has reached maximum power for active UL BWP $b$ of carrier
$f$ of serving cell $c$ at SRS transmission occasion $i - i_{0}$ and
$\sum_{m = 0}^{\text{C}\left( S_{i} \right) - 1}{\delta_{SRS,b,f,c}(m)} \geq 0$,
then $h_{b,f,c}(i) = h_{b,f,c}\left( i - i_{0} \right)$

\- If UE has reached minimum power for active UL BWP $b$ of carrier $f$
of serving cell $c$ at SRS transmission occasion $i - i_{0}$ and
$\sum_{m = 0}^{\text{C}\left( S_{i} \right) - 1}{\delta_{SRS,b,f,c}(m)} \leq 0$,
then $h_{b,f,c}(i) = h_{b,f,c}\left( i - i_{0} \right)$

\- If a configuration for a $P_{O\_ SRS,b,f,c}(q_{s})$ value or for a
$\alpha_{SRS,b,f,c}(q_{s})$ value for a corresponding SRS power control
adjustment state $l$ for active UL BWP $b$ of carrier $f$ of serving
cell $c$ is provided by higher layers

> \- $h_{b,f,c}(k) = 0,\ k = 0,1,\ldots,i$
>
> \- else

\- $h_{b,f,c}(0) = \ \Delta P_{rampup,b,f,c} + \delta_{b,f,c}$

where

$\delta_{b,f,c}$ is

\- the TPC command value indicated in the random access response grant
corresponding to a PRACH transmission according to Type-1 random access
procedure, or in a random access response grant corresponding to MsgA
transmissions according to Type-2 random access procedure with RAR
message(s) for fallbackRAR, or

\- the TPC command value indicated in a successRAR corresponding to MsgA
transmissions for Type-2 random access procedure,

and

$\mathrm{\Delta}P_{rampup,b,f,c} = min\left\lbrack \max\left( 0,P_{CMAX,f,c} - \left( P_{\text{O\_SRS},b,f,c}\left( q_{s} \right) + 10\log_{10}\left( 2^{\mu} \cdot M_{\text{SRS},b,f,c}(i) \right) + \alpha_{SRS,b,f,c}\left( q_{s} \right) \cdot {PL}_{b,f,c}(q_{d}) \right) \right),\mathrm{\Delta}P_{rampup\_ requested,b,f,c} \right\rbrack$;

> where ${\mathrm{\Delta}P}_{rampup\_ requested,b,f,c}$ is provided by
> higher layers and corresponds to the total power ramp-up requested by
> higher layers from the first to the last preamble for active UL BWP
> $b$ of carrier $f$ of serving cell $c$.

\- $h_{b,f,c}(i) = \delta_{SRS,b,f,c}(i)$ if the UE is not configured
for PUSCH transmissions on active UL BWP $b$ of carrier $f$ of serving
cell $c$, or if *srs-PowerControlAdjustmentStates* indicates separate
power control adjustment states between SRS transmissions and PUSCH
transmissions, and *tpc-Accumulation* is provided, and the UE detects a
DCI format 2_3 $K_{SRS,min}$ symbols before a first symbol of SRS
transmission occasion $i$, where absolute values of $\delta_{SRS,b,f,c}$
are provided in Table 7.1.1-1

\- if *srs-PowerControlAdjustmentStates* indicates a same power control
adjustment state for SRS transmissions and PUSCH transmissions, the
update of the power control adjustment state for SRS transmission
occasion $i$ occurs at the beginning of each SRS resource in the SRS
resource set $q_{s}$; otherwise, the update of the power control
adjustment state SRS transmission occasion $i$ occurs at the beginning
of the first transmitted SRS resource in the SRS resource set $q_{s}$.

If a UE transmits SRS based on a configuration by *SRS-PosResourceSet*
on active UL BWP $b$ of carrier $f$ of serving cell $c$, the UE
determines the SRS transmission power
$P_{SRS,b,f,c}\left( i,q_{s} \right)$ in SRS transmission occasion $i$
as

![](media/image19.wmf){width="5.020833333333333in"
height="0.5104166666666666in"} \[dBm\]

where,

\- $P_{O\_ SRS,b,f,c}\left( q_{s} \right)$ and
$\alpha_{SRS,b,f,c}\left( q_{s} \right)$ are provided by *p0-r16* and
*alpha-r16* respectively, for active UL BWP $b$ of carrier $f$ of
serving cell $c$, and SRS resource set $q_{s}$ is indicated by
*SRS-PosResourceSetId* from *SRS-PosResourceSet*, and

\- ${PL}_{b,f,c}\left( q_{d} \right)$ is a downlink pathloss estimate in
dB calculated by the UE, as described in clause 7.1.1 in case of an
active DL BWP of a serving cell $c$, using RS resource indexed $q_{d}$
in a serving or non-serving cell for SRS resource set $q_{s}$ \[6, TS
38.214\]. A configuration for RS resource index $q_{d}$ associated with
SRS resource set $q_{s}$ is provided by *pathlossReferenceRS-Pos*

\- if a *ssb-IndexServing* is provided, *referenceSignalPower* is
provided by *ss-PBCH-BlockPower*

\- if a *ssb-Ncell* is provided, *referenceSignalPower* is provided by
*ss-PBCH-BlockPower-r16*

\- if a *dl-PRS* is provided, *referenceSignalPower* is provided by
*dl-PRS-ResourcePower*

If the UE is in the RRC_CONNECTED state and determines that the UE is
not able to accurately measure ${PL}_{b,f,c}\left( q_{d} \right)$, or
the UE is not provided with *pathlossReferenceRS-Pos*, the UE calculates
${PL}_{b,f,c}\left( q_{d} \right)$ using a RS resource obtained from the
SS/PBCH block of the serving cell that the UE uses to obtain *MIB*. If
the UE is in the RRC_INACTIVE state, is not provided
*SRS-PosRRC-InactiveValidityAreaConfig*, and determines that the UE is
not able to accurately measure ${PL}_{b,f,c}\left( q_{d} \right)$, the
UE does not transmit SRS for the SRS resource set.

The UE may indicate a capability for a number of pathloss estimates that
the UE can simultaneously maintain for all SRS resource sets provided by
*SRS-PosResourceSet* in addition to the up to four pathloss estimates
that the UE maintains per serving cell for PUSCH/PUCCH transmissions and
for SRS transmissions configured by *SRS-Resource*.

If a UE transmits SRS based on a configuration by *SRS-PosResourceSet*
outside initial UL BWP of carrier *f* of serving cell *c* in
RRC_INACTIVE state, the active UL BWP *b* refers to the BWP
configuration provided by *bwp-NUL* or *bwp-SUL* in
*SRS-PosRRC-InactiveConfig* for the corresponding carrier.

If a UE transmits SRS on multiple SRS resources for positioning
bandwidth aggregation according to *linkage* \[6, TS 38.214\], the UE
calculates $P_{SRS,b,f,c}\left( i,q_{s} \right)$ using the same values
of $P_{O\_ SRS,b,f,c}\left( q_{s} \right)$,
$\alpha_{SRS,b,f,c}\left( q_{s} \right)$, and
${PL}_{b,f,c}\left( q_{d} \right)$ for each of the multiple SRS
resources.

If a UE transmits SRS based on a configuration by *SRS-PosResourceSet*
in *SRS-PosRRC-InactiveValidityAreaConfig* in RRC_INACTIVE state \[12,
TS 38.331\], the active UL BWP *b* refers to the BWP provided by
*bwp-NUL* or *bwp-SUL* in *SRS-PosRRC-InactiveValidityAreaConfig*. If
the UE is not provided *pathlossReferenceRS-Pos* in
*SRS-PosResourceSet*, or if the UE is provided *pathlossReferenceRS-Pos*
in *SRS-PosResourceSet* and the UE cannot accurately measure the
pathloss RS provided in *pathlossReferenceRS-Pos*, the UE calculates
${PL}_{b,f,c}(q_{d})$ using an RS resource from an SS/PBCH block with
same index as the one the UE used to obtain *MIB*; otherwise, the UE
uses the RS indicated by *pathlossReferenceRS-Pos* to calculate
${PL}_{b,f,c}(q_{d})$.

If a RedCap UE transmits SRS with frequency hopping outside the active
UL BWP of carrier $f$ of serving cell $c$ in RRC_CONNECTED state based
on a configuration by *SRS-PosResourceSet*, the active UL BWP $b$ refers
to the BWP provided by *bwp* in *SRS-PosTx-Hopping*.

If a RedCap UE transmits SRS with frequency hopping outside the initial
UL BWP of carrier $f$ of serving cell $c$ in RRC_INACTIVE state based on
a configuration by *SRS-PosResourceSet*, the active UL BWP $b$ refers to
the BWP provided by *bwp* in *SRS-PosTx-Hopping*.