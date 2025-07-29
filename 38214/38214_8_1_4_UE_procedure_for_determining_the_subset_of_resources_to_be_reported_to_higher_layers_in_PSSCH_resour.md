### 8.1.4 UE procedure for determining the subset of resources to be reported to higher layers in PSSCH resource selection in sidelink resource allocation mode 2

In resource allocation mode 2, the higher layer can request the UE to
determine a subset of resources from which the higher layer will select
resources for PSSCH/PSCCH transmission for a carrier. To trigger this
procedure, in slot *n* for this carrier*,* the higher layer provides the
following parameters for this PSSCH/PSCCH transmission:

\- the resource pool from which the resources are to be reported;

\- L1 priority, $prio_{TX}$;

\- the remaining packet delay budget;

\- number of sub-channels, $L_{\text{subCH}}$: If the higher layer
parameter *sl-TransmissionStructureForPSCCHandPSSCH* is not provided,
the number of sub-channels to be used for the PSSCH/PSCCH transmission
in a slot is $L_{\text{subCH}}$. If the higher layer parameter
*sl-TransmissionStructureForPSCCHandPSSCH* is set to \'contiguousRB\',
$L_{\text{subCH}}$ corresponds to the number of sub-channels within all
used RB sets to be used for the PSCCH/PSSCH transmission in a slot. If
the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH* is
set to \'interlaceRB\', $L_{\text{subCH}}$ corresponds to the number of
sub-channels to be used for the PSSCH/PSCCH transmission in a slot in
each RB set,

\- If the higher layer parameter
*sl-TransmissionStructureForPSCCHandPSSCH* is set to \'interlaceRB\',
the number of used RB sets for one PSCCH/PSSCH transmission, L~RBset~.

\- optionally, the number of consecutive slots for multi-consecutive
slots transmission, $N_{slot,MCSt}$.

\- optionally, the resource reservation interval, $P_{\text{rsvp\_TX}}$,
in units of msec.

\- if the higher layer requests the UE to determine a subset of
resources from which the higher layer will select resources for
PSSCH/PSCCH transmission as part of re-evaluation or pre-emption
procedure, the higher layer provides a set of resources
$(r_{0},r_{1},r_{2},\ldots)\ $which may be subject to re-evaluation and
a set of resources $(r_{0}',r_{1}',r_{2}',\ldots)\ $which may be subject
to pre-emption.

\- it is up to UE implementation to determine the subset of resources as
requested by higher layers before or after the slot $r_{i}^{''}$ -
$T_{3}$, where $r_{i}^{''}$ is the slot with the smallest slot index
among $(r_{0},r_{1},r_{2},\ldots)\ $and
$(r_{0}',r_{1}',r_{2}',\ldots)\ $, and $T_{3}$ is equal to
$T_{proc,1}^{SL}$, where $T_{proc,1}^{SL}\ $* *is defined in slots in
Table 8.1.4-2 where $\mu_{SL}$ is the SCS configuration of the SL BWP.

\- Each of the resource(s) in $\left( r_{0},r_{1},r_{2},\ldots \right)$
and/or $\left( r_{0}',r_{1}',r_{2}',\ldots \right)$ corresponds to
$N_{slot,MCSt}$ consecutive slots if $N_{slot,MCSt}\ $is provided with a
value larger than 1.

\- Optionally, the indication of resource selection mechanism.

\- Optionally, *rbSetsWithConsecutiveLBTFailure*, which indicates the RB
sets where consistent LBT failure has been indicated.

The following higher layer parameters affect this procedure:

*- sl-SelectionWindowList*: internal parameter $T_{2min}$ is set to the
corresponding value from higher layer parameter *sl-SelectionWindowList*
for the given value of $prio_{TX}$.

*- sl-Thres-RSRP-List*: this higher layer parameter provides an RSRP
threshold for each combination $\left( p_{i},\, p_{j} \right)$, where
$p_{i}$ is the value of the priority field in a received SCI format 1-A
and $p_{j}$ is the priority of the transmission of the UE selecting
resources; for a given invocation of this procedure,
$p_{j}\  = \ prio_{TX}$.

*- sl-RS-ForSensing* selects if the UE uses the PSSCH-RSRP or PSCCH-RSRP
measurement, as defined in clause 8.4.2.1.

*- sl-ResourceReservePeriodList*

*- sl-SensingWindow*: internal parameter $T_{0}$ is defined as the
number of slots corresponding to *sl-SensingWindow* msec

*- sl-TxPercentageList*: internal parameter $X$ for a given $prio_{TX}$
is defined as *sl-TxPercentageList (*$prio_{TX}$*)* converted from
percentage to ratio

\- *sl-PreemptionEnable*: if *sl-PreemptionEnable* is provided, and if
it is not equal to \'enabled\', internal parameter $prio_{pre}$ is set
to the higher layer provided parameter *sl-PreemptionEnable.*

\- Optionally, minimum number of *Y* slots as $Y_{\min}$
(*sl*-*MinNumCandidateSlotsPeriodic*), which indicates the minimum
number of *Y* slots that are included in the candidate resources
corresponding to periodic-based partial sensing and contiguous partial
sensing for resource (re)selection triggered by periodic transmission
($P_{\text{rsvp\_TX}} \neq 0$).

\- Optionally, minimum number of $Y'$ slots as ${Y'}_{{min\ }\ }$
(*sl*-*MinNumCandidateSlotsAperiodic*), which indicates the minimum
number of $Y'$ slots that are included in the candidate resources
corresponding to periodic-based partial sensing and/or contiguous
partial sensing results (if available) for resource (re)selection
triggered by aperiodic transmission ($P_{\text{rsvp\_TX}} = 0$).

\- Optionally, sensing occasion as *sl-PBPS-OccasionReservePeriodList,*
which indicates the subset of periodicity values from
*sl-ResourceReservePeriodList* used to determine periodic sensing
occasions in periodic-based partial sensing. If not configured, all
periodicity values from *sl-ResourceReservePeriodList* are used to
determine periodic sensing occasions in periodic-based partial sensing.

\- Optionally, additional sensing occasions as
*sl-Additional-PBPS-Occasion*, which indicates that UE additionally
monitors periodic sensing occasions that correspond to a set of values.
The possible values of the set at least includes the most recent sensing
occasion before the first slot of the candidate slots subject to
processing time restriction as specified below for a given reservation
periodicity and the last periodic sensing occasion prior to the most
recent one for the given reservation periodicity. If not
(pre-)configured, the UE monitors the most recent sensing occasion
before the first slot of the candidate slots subject to processing time
restriction as specified below for the given periodicity used to
determine periodic sensing occasions in periodic-based partial sensing.

> \- Optionally, indication of the size in logical slots of contiguous
> partial sensing window for periodic transmissions as defined by the
> parameter *sl-CPS-WindowPeriodic*.
>
> Optionally, indication of the size in logical slots of contiguous
> partial sensing window for aperiodic transmissions as defined by the
> parameter *sl-CPS-WindowAperiodic.*
>
> \- Optionally, indication of whether UE is required to perform SL
> reception of PSCCH and RSRP measurement for partial sensing on slots
> in SL DRX inactive time as *sl-PartialSensingInactiveTime.*

In case of dynamic co-channel coexistence of LTE sidelink and NR
sidelink, that is coexistence over time and frequency resources that are
shared between NR sidelink and LTE sidelink:

\- *sl-NRPSSCH-EUTRA-ThresRSRP-List*: this higher layer parameter
provides an RSRP threshold for each combination
$\left( p_{i},\, p_{j} \right)$, where $p_{i}$ is the value of the
priority field in a received LTE SCI format 1, and $p_{j}$ is the
priority of the transmission of the UE selecting resources; for a given
invocation of this procedure, $p_{j}\  = \ prio_{TX}$.

\- *sl-NRPSFCH-EUTRA-ThresRSRP-List*: this higher layer parameter, if
provided, provides an RSRP threshold for each combination
$\left( p_{i},\, p_{j} \right)$, where $p_{i}$ is the value of the
priority field in a received LTE SCI format 1, and $p_{j}$ is the
priority of the transmission of the UE selecting resources; for a given
invocation of this procedure, $p_{j}\  = \ prio_{TX}$.

The resource reservation interval, $P_{\text{rsvp\_TX}}$, if provided,
is converted from units of msec to units of logical slots, resulting in
$P_{\text{rsvp\_TX}}'$ according to clause 8.1.7.

When the resource pool is (pre-)configured with
*sl-AllowedResourceSelectionConfig* including full sensing, and full
sensing is configured in the UE by higher layers, the UE performs full
sensing.

When periodic reservation for another TB (*sl-MultiReserveResource*) is
enabled for the resource pool, the resource pool is (pre-)configured
with *sl-AllowedResourceSelectionConfig* including partial sensing, and
partial sensing is configured by higher layer, the UE performs
periodic-based partial sensing, unless other conditions state otherwise
in the specification.

When a UE is triggered by higher layer to report resources for resource
(re-)selection in a mode 2 Tx pool, the resource pool is
(pre-)configured with *sl-AllowedResourceSelectionConfig* including
partial sensing, and partial sensing is configured by higher layer, the
UE performs contiguous partial sensing, unless stated otherwise in the
specification.

Notation:

$\left( {t'}_{0}^{SL},\ {t'}_{1}^{SL},\ {t'}_{2}^{SL},\ldots \right)$
denotes the set of slots which belongs to the sidelink resource pool and
is defined in Clause 8.

For dynamic co-channel coexistence of LTE sidelink and NR sidelink,
$\left( t_{0}^{LTESL},t_{1}^{LTESL},\ldots,t_{T_{\max} - 1}^{LTESL} \right)$
denotes the set of subframes that may belong to an LTE sidelink resource
pool as defined in clause 14.1.5 of \[19, TS 36.213\].

The following steps are used:

1\) If a number of consecutive slots $N_{slot,MCSt}\ $is provided with a
value larger than 1, the candidate multi-slot resource definition is
applied. Otherwise, the candidate single-slot resource definition is
applied.

If the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH*
is set to \'contiguousRB\', a candidate multi-slot resource
$R_{\text{x,y}}$ is defined as a set of $L_{\text{subCH}}$ contiguous
sub-channels starting from sub-channel $x$ in $N_{slot,MCSt}$
consecutive slots starting from slot ${t'}_{y}^{SL}$, when the set of
$N_{slot,MCSt}$ slots that are consecutive in physical slots.

If the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH*
is set to \'interlaceRB\', a candidate multi-slot resource
$R_{\text{x,y,z}}$ is defined as a set of $L_{\text{subCH}}$ contiguous
sub-channels starting from sub-channel $x$ in $N_{slot,MCSt}$
consecutive slots starting from slot ${t'}_{y}^{SL}$ in
$L_{\text{RBset}}$ contiguous RB sets starting from RB set z, when the
set of $N_{slot,MCSt}$ slots that are consecutive in physical slots. A
candidate single-slot resource $R_{\text{x,y,z}}$ is defined as a set of
$L_{\text{subCH}}$ contiguous sub-channels starting from sub-channel $x$
in slot ${t'}_{y}^{SL}$ in $L_{\text{RBset}}$ contiguous RB sets
starting from RB set z.

If the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH*
is not provided or if the higher layer parameter
*sl-TransmissionStructureForPSCCHandPSSCH* is set to 'contiguousRB', a
candidate single-slot resource for transmission $R_{\text{x,y}}$ is
defined as a set of $L_{\text{subCH}}$ contiguous sub-channels with
sub-channel *x+j* in slot ${t'}_{y}^{SL}$ where
$j = 0,...,L_{\text{subCH}} - 1$.

The UE shall assume that any set of $L_{\text{subCH}}$ contiguous
sub-channels or $L_{\text{subCH}}$ contiguous sub-channels in
$L_{\text{RBset}}$ contiguous RB sets included in the corresponding
resource pool within the time interval
$\lbrack n + T_{1},n + T_{2}\rbrack$ correspond to one candidate
single-slot resource or the UE shall assume that any set of
$L_{\text{subCH}}$ contiguous sub-channels or $L_{\text{subCH}}$
contiguous sub-channels in $L_{\text{RBset}}$ contiguous RB sets in
$N_{slot,MCSt}$ consecutive slots included in the corresponding resource
pool within the time interval
$\left\lbrack n + T_{1},n + T_{2} \right\rbrack$ correspond to one
candidate multi-slot resource for UE performing full sensing. The UE
shall assume that any set of $L_{\text{subCH}}$ contiguous sub-channels
or $L_{\text{subCH}}$ contiguous sub-channels in $L_{\text{RBset}}$
contiguous RB sets included in the corresponding resource pool in a set
of *Y* candidate slots within the time interval
$\left\lbrack n + T_{1},n + T_{2} \right\rbrack$ correspond to one
candidate single-slot resource or the UE shall assume that any set of
$L_{\text{subCH}}$ contiguous sub-channels or $L_{\text{subCH}}$
contiguous sub-channels in $L_{\text{RBset}}$ contiguous RB sets in
$N_{slot,MCSt}$ consecutive slots included in the corresponding resource
pool in a set of *Y* candidate slots within the time interval
$\left\lbrack n + T_{1},n + T_{2} \right\rbrack$ correspond to one
candidate multi-slot resource for UE performing periodic-based partial
sensing together with contiguous partial sensing and resource
(re)selection triggered by periodic transmission
($P_{\text{rsvp\_TX}} \neq 0$), or the UE shall assume that any set of
$L_{\text{subCH}}$ contiguous sub-channels or $L_{\text{subCH}}$
contiguous sub-channels in $L_{\text{RBset}}$ contiguous RB sets
included in the corresponding resource pool in a set of *Y\'* candidate
slots within the time interval $\lbrack n + T_{1},n + T_{2}\rbrack$
correspond to one candidate single-slot resource or the UE shall assume
that any set of $L_{\text{subCH}}$ contiguous sub-channels or
$L_{\text{subCH}}$ contiguous sub-channels in $L_{\text{RBset}}$
contiguous RB sets in $N_{slot,MCSt}$ consecutive slots included in the
corresponding resource pool in a set of *Y\'* candidate slots within the
time interval $\lbrack n + T_{1},n + T_{2}\rbrack$ correspond to one
candidate multi-slot resource for UE performing at least contiguous
partial sensing and resource (re)selection triggered by aperiodic
transmission ($P_{\text{rsvp\_TX}} = 0$), where

\- selection of $T_{1}$ is up to UE implementation under
$0\  \leq \ T_{1} \leq$ $T_{proc,1}^{SL}\ $ , where $T_{proc,1}^{SL}\ $
is defined in slots in Table 8.1.4-2 where $\mu_{SL}$ is the SCS
configuration of the SL BWP;

\- if ${\ T}_{2min}$ is shorter than the remaining packet delay budget
(in slots) then $T_{2}\ $is up to UE implementation subject to
$T_{2min}\  \leq \ T_{2}$ $\leq$ remaining packet delay budget (in
slots); otherwise $T_{2}\ $is set to the remaining packet delay budget
(in slots).

\- $Y$ is selected by UE where $Y \geq Y_{\min}$.

\- $Y'$ is selected by UE where $Y' \geq Y_{\min}'$. When the UE
performs at least contiguous partial sensing and if
$P_{\text{rsvp\_TX}} = 0$, the UE selects a set of $Y'$ candidate slots
with corresponding PBPS and/or CPS results (if available). If the number
of candidate slots $Y'$ is smaller than $Y_{\min}'$, it is up to UE
implementation to include other candidate slots.

If the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH*
is set to \'contiguousRB\', the UE shall exclude candidate single-slot
or candidate multi-slot resources with the sub-channel with the smallest
index including resource blocks of the intra-cell guardband PRBs,
configured by higher layer parameter, *sl-IntraCellGuardBandsSL-List*,
or determined according to the nominal intra-cell guard band and RB set
pattern as specified in \[8, TS 38.101-1\] when higher layer parameter,
*sl-IntraCellGuardBandsSL-List*, is not configured.

If *rbSetsWithConsecutiveLBTFailure* is provided, the UE shall exclude
candidate single-slot resources or candidate multi-slot resources, whose
associated one or more RB set(s) is included in the
*rbSetsWithConsecutiveLBTFailure* parameter.

The total number of remaining candidate single-slot resources or
candidate multi-slot resources is denoted by $M_{\text{total}}$.

2\) The sensing window is defined by the range of slots
\[$n\, –T_{0},n–T_{proc,0}^{SL}$), when the UE performs full sensing,
where $T_{0}$ is defined above and $T_{proc,0}^{SL}$ is defined in slots
in Table 8.1.4-1 where $\mu_{SL}$ is the SCS configuration of the SL
BWP. The UE shall monitor slots which belongs to a sidelink resource
pool within the sensing window except for those in which its own
transmissions occur. The UE shall perform the behaviour in the following
steps based on PSCCH decoded and RSRP measured in these slots.

When the UE performs periodic-based partial sensing, the UE shall
monitor slots at $t_{y - k \times P_{reserve}'}^{'SL}$, where
${t'}_{y}^{SL}$ is a slot of the selected candidate slots and
$P_{reserve}'$ is $P_{reserve}$ converted to units of logical slot
according to clause 8.1.7. The UE shall perform the behaviour in the
following steps based on PSCCH decoded and RSRP measured in these slots.

The value of $P_{reserve}$ corresponds to
*sl-PBPS-OccasionReservePeriodList* if (pre-)configured, otherwise, the
values correspond to all periodicity from
*sl-ResourceReservePeriodList.*

The UE monitors sensing occasion(s) determined by
*sl-Additional-PBPS-Occasion*, as previously described, and not earlier
than $n\, –T_{0}$. For a given periodicity $P_{reserve}$, the values of
*k* correspond to the most recent sensing occasion earlier than
${t'}_{y0}^{SL} - {(T}_{proc,0}^{SL} + T_{proc,1}^{SL}\ )\ $if
*sl-Additional-PBPS-Occasion* is not (pre-)configured, and additionally
includes the value of *k* corresponding to the last periodic sensing
occasion prior to the most recent one if *sl-Additional-PBPS-Occasion*
is (pre-)configured. ${t'}_{y0}^{SL}$ is the first slot of the selected
*Y* candidate slots of PBPS.

When the UE performs periodic-based partial sensing and contiguous
partial sensing with periodic reservation for another TB
(*sl-MultiReserveResource*) enabled and $P_{\text{rsvp\_TX}} \neq 0$,
the contiguous partial sensing window is defined by the range of slots
$\lbrack n + T_{A},\ n + T_{B}\rbrack$. *n*+*T*~A~ is *M* consecutive
logical slots earlier than slot ${t'}_{y0}^{SL}$, and *n*+*T*~B~ is
$T_{proc,0}^{SL} + T_{proc,1}^{SL}$ slots earlier than ${t'}_{y0}^{SL}$,
where ${t'}_{y0}^{SL}$ is the first slot of the selected *Y* candidate
slots of PBPS, and $T_{proc,0}^{SL}$, $T_{proc,1}^{SL}$ are in units of
physical time/slots. The value of *M* is (pre-)configured with the
*sl-CPS-WindowPeriodic*. The UE shall perform the behaviour in the
following steps based on PSCCH decoded and RSRP measured in these slots.
If *sl-CPS-WindowPeriodic* is not (pre-)configured, *M* equals to 31.

When the UE performs at least contiguous partial sensing and if
$P_{\text{rsvp\_TX}} = 0$, the contiguous partial sensing window is
defined by the range of slots $\lbrack n + T_{A},\ n + T_{B}\rbrack$.
$T_{A}$ and $T_{B}$ are both selected such that the UE has sensing
results starting at least *M* consecutive logical slots before
${t'}_{y0}^{SL}$ and ending at $T_{proc,0}^{SL} + T_{proc,1}^{SL}$ slots
earlier than ${t'}_{y0}^{SL}$, where ${t'}_{y0}^{SL}$ is the first slot
of the selected $Y'$candidate slots. The value of *M* is
(pre-)configured with the *sl-CPS-WindowAperiodic*. The UE shall perform
the behaviour in the following steps based on PSCCH decoded and RSRP
measured in these slots. If *sl-CPS-WindowAperiodic* is not
(pre-)configured, *M* equals to 31. When the minimum *M* slots for CPS
cannot be guaranteed and when $P_{{rsvp}_{TX}} = 0$, it is up to UE
implementation to either continue with step 3) or perform random
selection.

Whether the UE is required to performs SL reception of PSCCH and RSRP
measurement for partial sensing on slots in SL DRX inactive time is
enabled/disabled by higher layer parameter
*sl-PartialSensingInactiveTime.* When it is enabled, if UE performs
periodic-based partial sensing on the slots in SL DRX inactive time for
a given periodicity corresponding to $P_{\text{reserve}}$, UE monitors
only the default periodic sensing occasions (most recent sensing
occasion) from the slots; if UE performs contiguous partial sensing on
the slots in SL DRX inactive time, UE monitors a minimum of *M* slots
from the slots.

2LTE1) In case of dynamic co-channel coexistence of LTE sidelink and NR
sidelink: The UE uses information determined by the E-UTRA radio access
within the range of LTE subframes \[$n_{LTE,start},n_{LTE,end}$\], where
$n_{LTE,start}\ $is an LTE subframe no later than LTE subframe
$n_{LTE}\, –T_{start},n_{LTE,end}$ is the LTE subframe
$n_{LTE}–T_{end}$, $n_{LTE}$ is the LTE subframe which overlaps slot
*n*, $T_{start}$ is 1100 msec and $T_{end}$ is up to UE implementation
under $T_{end} \leq \ T_{proc,2}^{SL}$; $T_{proc,2}^{SL}$is 4+T msec,
where T ≤ 4 msec. The UE shall perform the procedures in 5LTE1, 5LTE3
and 6LTE based on the information for these LTE subframes which is known
to the NR radio access at the latest *T* msec prior to slot *n*.

2LTE2) In case of dynamic co-channel coexistence of LTE sidelink and NR
sidelink: The UE shall perform the procedures in 5LTE2 based on the
information determined by the E-UTRA radio access, which is known by the
NR radio access at the latest *T* msec prior to slot *n*.

3\) The internal parameter $Th(p_{i},p_{j})\ $ is set to the
corresponding value of RSRP threshold indicated by the *i*-th field in
*sl-Thres-RSRP-List*, where $i = p_{i} + \left( p_{j} - 1 \right)*8$.

3LTE) In case of dynamic co-channel coexistence of LTE sidelink and NR
sidelink:

\- The internal parameter $ThLTE\left( p_{i},p_{j} \right)$ is set to
the corresponding value of RSRP threshold indicated by the *i*-th field
in *sl-NRPSSCH-EUTRA-ThresRSRP-List*, where
$i = p_{i} + \left( p_{j} - 1 \right)*8$.

\- The internal parameter $ThLTEPSFCH\left( p_{i},p_{j} \right)$ is set
to the corresponding value of RSRP threshold indicated by the *i*-th
field in *sl-NRPSFCH-EUTRA-ThresRSRP-List*, if provided, where
$i = p_{i} + \left( p_{j} - 1 \right)*8$. If
*sl-NRPSFCH-EUTRA-ThresRSRP-List* is not provided then each element of
$ThLTEPSFCH\left( p_{i},p_{j} \right)$ is set to minus Infinity dBm.

4\) The set $S_{A}$ is initialized to the set of all the remaining
candidate single-slot resources or candidate multi-slot resources
identified in step 1.

5\) The UE shall exclude any candidate single-slot resource $R_{x,y}$ or
$R_{\text{x,y,z}}$, or candidate multi-slot resource $R_{\text{x,y}}$ or
$R_{\text{x,y,z}}$ from the set $S_{A}$ if it meets all the following
conditions:

\- the UE has not monitored slot ${t'}_{m}^{SL}$ in Step 2.

\- for any periodicity value allowed by the higher layer parameter
*sl-ResourceReservePeriodList* and a hypothetical SCI format 1-A
received in slot ${t'}_{m}^{SL}$ with \'*Resource reservation period*\'
field set to that periodicity value and indicating all subchannels of
the resource pool in this slot, condition c in step 6 would be met.

5LTE1) In case of dynamic co-channel coexistence of LTE sidelink and NR
sidelink: The UE shall exclude any candidate single-slot resource
$R_{\text{x,y}}$ from the set $S_{A}$ if all the following conditions
are met:

\- the resource pool overlaps with an LTE sidelink resource pool;

\- the UE has not monitored LTE subframe $t_{m}^{LTESL}$ .

\- for any periodicity value allowed by the LTE higher layer parameter
*restrictResourceReservationPeriod* and a hypothetical LTE SCI format 1
received in LTE subframe $t_{m}^{LTESL}$ with \'*Resource reservation\'*
field set to that periodicity value and indicating all subchannels of
the LTE sidelink resource pool in this LTE subframe, condition c in step
6LTE would be met.

5LTE2) In case of dynamic co-channel coexistence of LTE sidelink and NR
sidelink: The UE shall exclude any candidate single-slot resource
$R_{x,y}$ from the set $S_{A}$ if all the following conditions are met:

\- the UE has a selected sidelink grant for LTE V2X sidelink according
to \[19, TS 36.321\] .

\- the selected sidelink grant for LTE V2X sidelink determines the set
of LTE resource blocks and LTE subframes which overlaps in time with
$R_{x,y + j \times P_{rsvp_{TX}}'}$ for *j=*0, 1, ..., $C_{resel} - 1$;

\- the priority value associated with the selected sidelink grant for
LTE V2X sidelink is lower than $prio_{TX}$; It is up to UE
implementation whether or not to apply this exclusion step if the
priority value associated with selected sidelink grant for LTE V2X
sidelink is higher than or equal to $prio_{TX}$.

5LTE3) In case of dynamic co-channel coexistence of LTE sidelink and NR
sidelink: The UE shall exclude any candidate single-slot resource
$R_{x,y}$ from the set $S_{A}$ if all the following conditions are met:

a\) the resource pool is configured with PSFCH resources;

b\) an LTE SCI format 1 is received in LTE subframe $t_{m}^{LTESL}$, and
the \'*Resource reservation\'* field and \'*Priority*\' field in the
received LTE SCI format 1 indicate the values $P_{{rsvp}_{RX}}$ and
$prio_{RX}$, respectively according to Clause 14.2.1 in \[19, TS
36.213\], where LTE subframes are indexed according to Clause 14.1.5 in
\[19, TS 36.213\];

c\) the LTE PSSCH-RSRP measurement according to the received LTE SCI
format 1 is higher than $ThLTEPSFCH\left( prio_{RX},prio_{TX} \right);$

d\) the SCI format received in LTE subframe $t_{m}^{LTESL}\ $or the same
SCI format which is assumed to be received in LTE subframe(s)
$t_{m + q \times P_{{rsvp}_{RX}}'}^{LTESL}$ determines according to
clause 14.1.1.4C or clause 14.2.4 in \[19, TS 36.213\] the set of LTE
subframes which overlaps with PSFCH slots associated with
$R_{x,y + j \times P_{rsvp_{TX}}'}$ for *q*=1, 2, ..., *Q* and *j=*0, 1,
..., $C_{resel} - 1\ ,\ $where the PSFCH association is according to
\[6, TS 38.213\]. $P_{rsvp_{RX}}'\ $and *Q* are determined as in
condition c) of step 6LTE.

5a) If the number of candidate single-slot resources $R_{\text{x,y}}$ or
$R_{\text{x,y,z}}$, or the number of candidate multi-slot resource
$R_{\text{x,y}}$ or $R_{\text{x,y,z}}$ remaining in the set $S_{A}$ is
smaller than $X \cdot M_{\text{total}}$, the set $S_{A}$ is initialized
to the set of all the candidate single-slot resources or candidate
multi-slot resources as in step 4.

6\) The UE shall exclude any candidate single-slot resource $R_{x,y}$ or
$R_{\text{x,y,z}}$, or candidate multi-slot resource $R_{\text{x,y}}$ or
$R_{\text{x,y,z}}$ from the set $S_{A}$ if it meets all the following
conditions:

a\) the UE receives an SCI format 1-A in slot ${t'}_{m}^{SL}$, and
\'*Resource reservation period\'* field, if present, and \'*Priority*\'
field in the received SCI format 1-A indicate the values
$P_{{rsvp}_{RX}}$ and $prio_{RX}$, respectively according to Clause 16.4
in \[6, TS 38.213\];

b\) the RSRP measurement performed, according to clause 8.4.2.1 for the
received SCI format 1-A, is higher than
$Th\left( prio_{RX},prio_{TX} \right);$

> c\) the SCI format received in slot ${t'}_{m}^{SL}\ $or the same SCI
> format which, if and only if the \'*Resource reservation period*\'
> field is present in the received SCI format 1-A, is assumed to be
> received in slot(s) ${t'}_{m + q \times P_{r{svp}_{RX}}'}^{SL}$
> determines according to clause 8.1.5 the set of resource blocks and
> slots which overlaps with $R_{x,y + j \times P_{rsvp_{TX}}'}$ or
> $R_{x,y + j \times P_{rsvp_{TX}}',z}$ for *q*=1, 2, ..., *Q* and
> *j=*0, 1, ..., $C_{resel} - 1$. Here, $P_{rsvp\text{\_}RX}'$ is
> $P_{\text{rsvp\_RX}}$ converted to units of logical slots according to
> clause 8.1.7,
> $Q = \left\lceil \frac{T_{scal}}{P_{{rsvp}_{RX}}} \right\rceil\ $ if
> $P_{{rsvp}_{RX}} < \ T_{scal}$ and $\ n' - m \leq P_{{rsvp}_{RX}}'$,
> where if the UE is configured with full sensing by its higher layer,
> ${t'}_{n'}^{SL}\  = \ n$ if slot *n* belongs to the set
> $\left( {t'}_{0}^{SL},{t'}_{1}^{SL},...,{t'}_{{T'}_{\max} - 1}^{SL} \right)$,
> otherwise slot ${t'}_{n'}^{SL}$ is the first slot after slot *n*
> belonging to the set
> $\left( {t'}_{0}^{SL},{t'}_{1}^{SL},...,{t'}_{{T'}_{\max} - 1}^{SL} \right)$;
> If UE is configured with partial sensing by its higher layer,
> ${t'}_{n'}^{SL} = {t'}_{y_{i}}^{SL} - T_{proc,1}^{SL}$ if slot
> ${t'}_{y_{i}}^{SL} - T_{proc,1}^{SL}$ belongs to the set
> $\left( {t'}_{0}^{SL},{t'}_{1}^{SL},...,{t'}_{{T'}_{\max} - 1}^{SL} \right)$,
> otherwise, slot ${t'}_{n'}^{SL}$ is the first slot after slot
> ${t'}_{y_{i}}^{SL} - T_{proc,1}^{SL}$ belonging to the set
> $\left( {t'}_{0}^{SL},{t'}_{1}^{SL},...,{t'}_{{T'}_{\max} - 1}^{SL} \right)$.
> Otherwise $Q = 1$. If the UE is configured with full sensing by its
> higher layer, $T_{scal}$ is set to selection window size *T~2~*
> converted to units of msec. If UE is configured with partial sensing
> by its higher layer,
> $T_{scal} = {t'}_{y_{L}}^{SL} - ({t'}_{y_{i}}^{SL} - T_{proc,1}^{SL})$
> shall be converted to milliseconds, where slot ${t'}_{y_{L}}^{SL}$ is
> the last slot of the $Y$ or $Y'$ candidate slots. The slot
> ${t'}_{y_{i}}^{SL}$ is the first slot of the selected/remaining set of
> $Y$ or $Y'$ candidate slots.

6LTE) In case of dynamic co-channel coexistence of LTE sidelink and NR
sidelink: The UE shall exclude any candidate single-slot resource
$R_{x,y}$ from the set $S_{A}$ if all the following conditions are met:

a\) an LTE SCI format 1 is received in LTE subframe $t_{m}^{LTESL}$, and
the \'*Resource reservation\'* field and \'*Priority*\' field in the
received LTE SCI format 1 indicate the values $P_{{rsvp}_{RX}}$ and
$prio_{RX}$, respectively according to Clause 14.2.1 in \[19, TS
36.213\], where LTE subframes are indexed according to Clause 14.1.5 in
\[19, TS 36.213\];

b\) the LTE PSSCH-RSRP measurement according to the received LTE SCI
format 1 is higher than $ThLTE\left( prio_{RX},prio_{TX} \right);$

> c\) the SCI format received in LTE subframe $t_{m}^{LTESL}\ $or the
> same SCI format which is assumed to be received in LTE subframe(s)
> $t_{m + q \times P_{{rsvp}_{RX}}'}^{LTESL}$ determines according to
> clause 14.1.1.4C or clause 14.2.4 in \[19, TS 36.213\] the set of LTE
> resource blocks and LTE subframes which overlaps with
> $R_{x,y + j \times P_{rsvp_{TX}}'}$ for *q*=1, 2, ..., *Q* and *j=*0,
> 1, ..., $C_{resel} - 1$. Here, $P_{rsvp\text{\_}RX}'$ is
> $P_{step} \times P_{rsvp\_ RX}$with $P_{step}$ determined according to
> Table 14.1.1-1 in \[19, TS 36.213\],
> $Q = \left\lceil \frac{T_{scal}}{{100 \times P}_{{rsvp}_{RX}}} \right\rceil\ $
> if ${100 \times P}_{rsvp_{RX}} < \ T_{scal}$ and
> $\ {\ n}' - m \leq P_{{rsvp}_{RX}}'$, where
> $t_{n'}^{LTESL}\  = \ n_{LTE}\ $if subframe $n_{LTE}$ belongs to the
> set
> $\left( t_{0}^{LTESL},t_{1}^{LTESL},\ldots,t_{T_{\max} - 1}^{LTESL} \right)$,
> otherwise subframe $t_{n'}^{LTESL}$ is the first subframe after
> subframe $n_{LTE}\ $belonging to the set
> $\left( t_{0}^{LTESL},t_{1}^{LTESL},\ldots,t_{T_{\max} - 1}^{LTESL} \right)$;
> Otherwise $Q = 1$. $T_{scal}$ is set to selection window size *T~2~*
> converted to units of msec.

6a) This step is executed only if the procedure in clause 8.1.4A is
triggered.

6b) This step is executed only if the procedure in clause 8.1.4C is
triggered.

> 7\) If the number of candidate single-slot resources or candidate
> multi-slot resources remaining in the set $S_{A}$ is smaller than
> $X \cdot M_{\text{total}}$, then $Th\left( p_{i},p_{j} \right)$ and
> $ThLTE\left( p_{i},p_{j} \right)$, if set, is increased by 3 dB for
> each combination $\left( p_{i},p_{j} \right)$ and the procedure
> continues with step 4.
>
> 7a) If sidelink DRX active time of RX UE is provided by the higher
> layer and there is no candidate single-slot or multi-slot resource
> remained within the sidelink DRX active time in the set $S_{A}$, the
> UE based on its implementation additionally selects and includes at
> least one candidate single-slot resource or at least one candidate
> multi-slot resource within the sidelink DRX active time in the set
> $S_{A}$.

The UE shall report set $S_{A}$ to higher layers.

If a resource $r_{i}$ from the set $(r_{0},r_{1},r_{2},\ldots)$ is not a
member of $S_{A}$, then the UE shall report re-evaluation of the
resource $r_{i}$ to higher layers.

If a resource $r_{i}'$ from the set $(r_{0}',r_{1}',r_{2}',\ldots)$
meets the conditions below then the UE shall report pre-emption of the
resource $r_{i}'$ to higher layers.

\- $r_{i}'$ is not a member of $S_{A}$, and

\- $r_{i}'$ meets the conditions for exclusion in step 6, with
$Th\left( prio_{RX},prio_{TX} \right)$ set to the final threshold after
executing steps 1)-7), i.e. including all necessary increments for
reaching $X \cdot M_{total}$, or for exclusion in step 6LTE, with
$ThLTE\left( prio_{RX},prio_{TX} \right)$ set to the final threshold
after executing steps 1-7, i.e. including all necessary increments for
reaching $X \cdot M_{total}$, or for exclusion in step 5LTE3, and

\- the associated priority $prio_{RX},$ satisfies one of the following
conditions:

\- *sl-PreemptionEnable* is provided and is equal to \'enabled\' and
$prio_{TX} > prio_{RX}$

\- *sl-PreemptionEnable* is provided and is not equal to \'enabled\',
and $prio_{RX} < prio_{pre}$ and $prio_{TX} > prio_{RX}$

Table 8.1.4-1: $\mathbf{T}_{\mathbf{proc,0}}^{\mathbf{SL}}$ depending on
sub-carrier spacing

  ----------------------------------------------------------------------------------
    $$\mathbf{\mu}_{\mathbf{SL}}$$     $\mathbf{T}_{\mathbf{proc,0}}^{\mathbf{SL}}$
                                                      **\[slots\]**
  ----------------------------------- ----------------------------------------------
                   0                                        1

                   1                                        1

                   2                                        2

                   3                                        4
  ----------------------------------------------------------------------------------

Table 8.1.4-2: $\mathbf{T}_{\mathbf{proc,1}}^{\mathbf{SL}}$ depending on
sub-carrier spacing

  ----------------------------------------------------------------------------------
    $$\mathbf{\mu}_{\mathbf{SL}}$$     $\mathbf{T}_{\mathbf{proc,1}}^{\mathbf{SL}}$
                                                      **\[slots\]**
  ----------------------------------- ----------------------------------------------
                   0                                        3

                   1                                        5

                   2                                        9

                   3                                        17
  ----------------------------------------------------------------------------------

When the UE performs periodic-based partial sensing and contiguous
partial sensing, and when the UE is triggered to perform re-evaluation
and/or pre-emption checking, and if $P_{\text{rsvp\_TX}} \neq 0$,

\- During the *q*^th^ reservation period (*q*=0,1,2,..., *Cresel*-1),
candidate resource set (*S~A~*) is initialized to the remaining *Y*
candidate slots starting from slot ${t'}_{yi}^{SL}$ and ending at the
last slot of the *Y* candidate slots, where the slot indices of the
remaining *Y* candidate slots are equal to
${t'}_{y + q \times P_{rsvp\text{\_}TX}'}^{SL}$, where ${t'}_{y}^{SL}$
is a slot index of *Y* candidate slots used in the initial resource
(re)selection.

\- ${t'}_{yi}^{SL}$ is the first candidate slot starting from slot
*n+T~3~*.

\- The UE performs PBPS for the remaining *Y* candidate slots according
to $t_{y' - k \times P_{reserve}'}^{'SL}$ except for those in which its
own transmissions occur, where${t'}_{\mathbf{y'}}^{SL}$ is a slot
belonging to the remaining *Y* candidate slots, and *k* and *P~reserve~*
are the same as resource (re)selection, where the values of *k*
correspond to the most recent sensing occasion earlier than
${t'}_{yi}^{SL} - {(T}_{proc,0}^{SL} + T_{proc,1}^{SL}\ )\ $if
*sl-Additional-PBPS-Occasion* is not (pre-)configured, and additionally
includes the value of *k* corresponding to the last periodic sensing
occasion prior to the most recent one if *sl-Additional-PBPS-Occasion*
is (pre-)configured.

\- The UE performs CPS starting from *M* logical slots earlier than
${t'}_{yi}^{SL}$ to $T_{proc,0}^{SL} + T_{proc,1}^{SL}$ slots earlier
than ${t'}_{yi}^{SL}$ except for those in which its own transmissions
occur.

\- By default, *M* is 31 unless (pre-)configured with another value by
*sl-CPS-WindowPeriodic*.

When the UE is triggered to perform re-evaluation and/or pre-emption
checking, performs at least contiguous partial sensing, and if
$P_{\text{rsvp\_TX}} = 0$,

\- Candidate resource set (*S~A~*) is initialized to the remaining *Y\'*
candidate slots starting from slot ${t'}_{yi}^{SL}$ and ending at the
last slot of the *Y\'* candidate slots, where ${t'}_{yi}^{SL}$ is the
first candidate slot starting from slot *n+T~3~*.

\- It is up to UE implementation that UE may perform PBPS for periodic
sensing occasions after the resource (re)selection when higher layer
parameter *sl-MultiReserveResource* is enabled.

\- UE performs CPS starting from at least *M* consecutive logical slots
earlier than ${t'}_{yi}^{SL}$ to $T_{proc,0}^{SL} + T_{proc,1}^{SL}$
slots earlier than ${t'}_{yi}^{SL}$ except for those in which its own
transmissions occur.

\- For minimum size *M* of the contiguous partial sensing window
$\lbrack n + T_{A},\ n + T_{B}\rbrack$, by default, *M* is 31 unless
(pre-)configured with another value, by *sl-CPS-WindowAperiodic*.

> When the minimum *M* slots for CPS cannot be guaranteed, UE senses in
> all available slots starting from the resource (re)selection trigger
> slot of the same TB to $T_{proc,0}^{SL} + T_{proc,1}^{SL}$ slots
> earlier than ${t'}_{yi}^{SL}$. The UE re-evaluation and pre-emption
> checking is based on all available sensing results after $n\, –T_{0}$.