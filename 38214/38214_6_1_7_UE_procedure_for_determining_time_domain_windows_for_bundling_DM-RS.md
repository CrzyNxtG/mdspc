### 6.1.7 UE procedure for determining time domain windows for bundling DM-RS

For PUSCH transmissions of PUSCH repetition Type A scheduled by DCI
format 0_1, 0_2 or 0_3, PUSCH repetition Type A with a configured grant,
PUSCH repetition Type B and TB processing over multiple slots, when
*pusch-DMRS-Bundling* is enabled, and for PUCCH transmissions of PUCCH
repetition, when *PUCCH-DMRS-Bundling* is enabled, the UE determines one
or multiple nominal TDWs, as follows:

\- For PUSCH transmissions of repetition Type A, PUSCH repetition Type B
and TB processing over multiple slots, the duration of each nominal TDW
except the last nominal TDW, in number of consecutive slots, is:

\- Given by *pusch-TimeDomainWindowLength*, if configured.

\- Computed as min (*maxDurationDMRS-Bundling*, M), if
*pusch-TimeDomainWindowLength* is not configured, where
*maxDurationDMRS-Bundling* is maximum duration for a nominal TDW subject
to UE capability \[13, TS 38.306\], M is the time duration in
consecutive slots of $N \bullet K$ PUSCH transmissions, and where:

\- For PUSCH transmissions of PUSCH repetition Type A, N=1 and K is the
number of repetitions, as defined in Clause 6.1.2.1 or in Clause
6.1.2.3.

\- For PUSCH transmissions of PUSCH repetition Type B, N=1 and K is the
number of nominal repetitions, as defined in Clause 6.1.2.1 or in Clause
6.1.2.3.

\- For PUSCH transmissions of TB processing over multiple slots, N is
the number of slots used for TBS determination and K is the number of
repetitions of the number of slots N used for TBS determination, as
defined in Clause 6.1.2.1 or in Clause 6.1.2.3.

\- For PUCCH transmissions of PUCCH repetition, the duration of each
nominal TDW except the last nominal TDW, in number of consecutive slots,
is:

\- Given by *pucch-TimeDomainWindowLength*, if configured.

\- Computed as min (*maxDurationDMRS-Bundling*, M), if
*pucch-TimeDomainWindowLength* is not configured, where
*maxDurationDMRS-Bundling* is maximum duration for a nominal TDW subject
to UE capability \[13, TS 38.306\], M is the time duration in
consecutive slots from the first slot determined for PUCCH transmissions
of PUCCH repetition to the last slot determined for PUCCH transmissions
of PUCCH repetition according to clause 9.2.6 of \[6, TS 38.213\].

\- For PUSCH transmission of a PUSCH repetition Type A scheduled by DCI
format 0_1, 0_2 or 0_3 and PUSCH repetition Type A with a configured
grant, when *AvailableSlotCounting* is enabled, and for TB processing
over multiple slots:

\- The start of the first nominal TDW is the first slot determined for
the first PUSCH transmission.

\- The end of the last nominal TDW is the last slot determined for the
last PUSCH transmission.

\- The start of any other nominal TDWs is the first slot determined for
PUSCH transmission after the last slot determined for PUSCH transmission
of a previous nominal TDW.

\- For PUSCH transmissions of a PUSCH repetition type A scheduled by DCI
format 0_1, 0_2 or 0_3 and PUSCH repetition Type A with a configured
grant, when the UE is not configured with *AvailableSlotCounting* and
for PUSCH repetition type B:

\- The start of the first nominal TDW is the first slot for the first
PUSCH transmission.

\- The end of the last nominal TDW is the last slot for the last PUSCH
transmission.

\- The start of any other nominal TDWs is the first slot after the last
slot of a previous nominal TDW.

\- For PUCCH transmissions of a PUCCH repetition:

\- The start of the first nominal TDW is the first slot determined for
the first PUCCH transmission.

\- The end of the last nominal TDW is the last slot determined for the
last PUCCH transmission.

\- The start of any other nominal TDWs is the first slot determined for
PUCCH transmission after the last slot determined for PUCCH transmission
of a previous nominal TDW.

For PUSCH transmissions of a PUSCH repetition Type A scheduled by DCI
format 0_1, 0_2 or 0_3, PUSCH repetition Type A with a configured grant,
PUSCH repetition Type B and TB processing over multiple slots, a nominal
TDW consists of one or multiple actual TDWs. The UE determines the
actual TDWs as follows:

\- The start of the first actual TDW is the first symbol of the first
PUSCH transmission in a slot for PUSCH transmission of PUSCH repetition
type A scheduled by DCI format 0_1, 0_2 or 0_3, or PUSCH repetition Type
A with a configured grant, or PUSCH repetition type B or TB processing
over multiple slots within the nominal TDW.

\- The end of an actual TDW is

\- The last symbol of the last PUSCH transmission in a slot for PUSCH
transmission of PUSCH repetition type A scheduled by DCI format 0_1, 0_2
or 0_3, or PUSCH repetition Type A with a configured grant, or PUSCH
repetition type B or TB processing over multiple slots within the
nominal TDW, if the actual TDW reaches the end of the last PUSCH
transmission within the nominal TDW.

\- The last symbol of a PUSCH transmission before the event, if an event
occurs which causes power consistency and phase continuity not to be
maintained across PUSCH transmissions of PUSCH repetition type A
scheduled by DCI format 0_1, 0_2 or 0_3, or PUSCH repetition Type A with
a configured grant, or PUSCH repetition type B or TB processing over
multiple slots within the nominal TDW, and the PUSCH transmission is in
a slot for PUSCH transmission of PUSCH repetition type A scheduled by
DCI format 0_1, 0_2 or 0_3, or PUSCH repetition Type A with a configured
grant, or PUSCH repetition type B or TB processing over multiple slots.

\- When *pusch-WindowRestart* is enabled, the start of a new actual TDW
is the first symbol of the PUSCH transmission after the event which
causes power consistency and phase continuity not to be maintained
across PUSCH transmissions of PUSCH repetition type A scheduled by DCI
format 0_1, 0_2 or 0_3, or PUSCH repetition Type A with a configured
grant, or PUSCH repetition type B or TB processing over multiple slots
within the nominal TDW, and the PUSCH transmission is in a slot for
PUSCH transmission of PUSCH repetition type A scheduled by DCI format
0_1, 0_2 or 0_3, or PUSCH repetition Type A with a configured grant, or
PUSCH repetition type B or TB processing over multiple slots.

For PUCCH transmissions of PUCCH repetition, a nominal TDW consists of
one or multiple actual TDWs. The UE determines the actual TDWs as
follows:

\- The start of the first actual TDW is the first symbol of the first
PUCCH transmission in a slot determined for PUCCH transmission within
the nominal TDW.

\- The end of an actual TDW is

\- The last symbol of the last PUCCH transmission in a slot determined
for transmission of the PUCCH within the nominal TDW, if the actual TDW
reaches the end of the last PUCCH transmission within the nominal TDW.

\- The last symbol of a PUCCH transmission before the event, if an event
occurs which causes power consistency and phase continuity not be
maintained across PUCCH transmissions of PUCCH repetition within the
nominal TDW, and the PUCCH transmission is in a slot determined for
transmission of the PUCCH.

\- When *pucch-WindowRestart* is enabled, the start of a new actual TDW
is the first symbol of the PUCCH transmission after the event which
causes power consistency and phase continuity not to be maintained
across PUCCH transmissions of PUCCH repetition within the nominal TDW,
and the PUCCH transmission is in a slot determined for transmission of
the PUCCH.

Events which cause power consistency and phase continuity not to be
maintained across PUSCH transmissions of PUSCH repetition type A
scheduled by DCI format 0_1, 0_2 or 0_3, or PUSCH repetition Type A with
a configured grant, or PUSCH repetition type B or TB processing over
multiple slots, or PUCCH transmissions of PUCCH repetition, within the
nominal TDW, are:

\- A downlink slot or downlink reception or downlink monitoring based on
*tdd-UL-DL-ConfigurationCommon*
and *tdd-UL-DL-ConfigurationDedicated* for unpaired spectrum.

\- For the UE indicating the capability *dmrs-BundlingNonBackToBackTX*
or *dmrs-BundlingNonBackToBackTX-PerBC* in \[13, TS 38.306\], the gap
between any two consecutive PUSCH transmissions, or the gap between any
two consecutive PUCCH transmissions, exceeds 13 symbols for normal
cyclic prefix or exceeds 11 symbols for extended cyclic prefix.

\- For the UE not indicating either of the capabilities
*dmrs-BundlingNonBackToBackTX* or *dmrs-BundlingNonBackToBackTX-PerBC*
in \[13, TS 38.306\], a non-zero symbol gap is scheduled between any two
consecutive PUSCH transmissions or between any two consecutive PUCCH
transmissions.

\- The gap between any two consecutive PUSCH transmissions, or the gap
between any two consecutive PUCCH transmissions, does not exceed 13
symbols but other uplink transmissions are scheduled between the two
consecutive PUSCH transmissions or the two consecutive PUCCH
transmissions.

\- For PUSCH transmissions of PUSCH repetition type A, or PUSCH
repetition type B or TB processing over multiple slots, a dropping or
cancellation of a PUSCH transmission according to clause 9, clause 11.1
and clause 11.2A of \[6, TS 38.213\] or due to cell DRX operation.

\- For PUCCH transmissions of PUCCH repetition, a dropping or
cancellation of a PUCCH transmission according to clause 9, clause 9.2.6
and clause 11.1 of \[6, TS 38.213\] or due to cell DRX operation.

\- For any two consecutive PUSCH transmissions of PUSCH repetition type
A, or PUSCH repetition type B, and when neither *multipanelSchemeSDM*
nor *multipanelSchemeSFN* is configured and two SRS resource sets are
configured in *srs-ResourceSetToAddModList* or
*srs-ResourceSetToAddModListDCI-0-2* with higher layer parameter *usage*
in *SRS-ResourceSet* set to \'codebook\' or \'nonCodebook\', a different
SRS resource set association is used for the two PUSCH transmissions of
PUSCH repetition type A, or PUSCH repetition type B, according to Clause
6.1.2.1.

\- For any two consecutive PUCCH transmissions of PUCCH repetition, and
when a PUCCH resource used for repetitions of a PUCCH transmission by a
UE includes first and second spatial relations or first and second sets
of power control parameters, as described in \[10, TS 38.321\] and in
clause 7.2.1 of \[6, TS 38.213\], different spatial relations or
different power control parameters are used for the two PUCCH
transmissions of PUCCH repetition, according to Clause 9.2.6 of \[6, TS
38.213\].

\- Uplink timing adjustment in response to a timing advance command
according to clause 4.2 of \[6, TS 38.213\].

\- Frequency hopping.

\- For reduced capability half-duplex UEs,

\- a dropping or cancellation of a PUSCH or PUCCH transmission according
to clause 17.2 of \[6, TS 38.213\] or

\- an overlapping of the gap between two consecutive PUSCH or two
consecutive PUCCH transmissions and any symbol of downlink reception or
downlink monitoring

The UE shall maintain power consistency and phase continuity within an
actual TDW, across PUSCH transmissions of PUSCH repetition Type A
scheduled by DCI format 0_1, 0_2 or 0_3, or PUSCH repetition Type A with
a configured grant, or PUSCH repetition type B or TB processing over
multiple slots, or across PUCCH transmissions of PUCCH repetition, in
case the actual TDW is created in response to frequency hopping, or in
response to the use of a different SRS resource set association for the
two PUSCH transmissions of PUSCH repetition type A, or PUSCH repetition
type B, or in response to the use of different spatial relations or
different power control parameters for the two PUCCH transmissions of
PUCCH repetition, or in response to any event not triggered by DCI or
MAC-CE. The UE maintains power consistency and phase continuity within
an actual TDW, across PUSCH transmissions of PUSCH repetition Type A
scheduled by DCI format 0_1, 0_2 or 0_3, or PUSCH repetition Type A with
a configured grant, or PUSCH repetition type B or TB processing over
multiple slots, or across PUCCH transmissions of PUCCH repetition, in
case the actual TDW is created in response to an event triggered by DCI
other than frequency hopping or the use of a different SRS resource set
association for the two PUSCH transmissions of PUSCH repetition type A,
or PUSCH repetition type B, or the use of different spatial relations or
different power control parameters for the two PUCCH transmissions of
PUCCH repetition, or in response to an event triggered by MAC-CE,
subject to UE capability. of *dmrs-BundlingRestart* \[13, TS 38.306\]
and when *pusch-WindowRestart* or *pucch-WindowRestart* is enabled.