### 5.28.2 Behaviour of UE receiving SL-SCH Data

When SL DRX is configured, the Active Time includes the time while:

\- *sl-drx-onDurationTimer*/*sl-DRX-GC-BC-OnDurationTimer* or
*sl-drx-InactivityTimer*/*sl-DRX-GC-InactivityTimer* is running; or

\- *sl-drx-RetransmissionTimer*/*sl-DRX-GC-RetransmissionTimer* is
running; or

\- period of *sl-LatencyBoundCSI-Report* configured by RRC in case
SL-CSI reporting MAC CE is not received; or

\- the time between the transmission of the request of SL-CSI reporting
and the reception of the SL-CSI reporting MAC CE in case SL-CSI
reporting MAC CE is received; or

\- Slot(s) associated with the announced periodic transmission(s) by the
UE transmitting SL-SCH Data; or

\- the time between transmission/reception of Direct Link Establishment
Request message (TS 24.587 \[28\]) or ProSe Direct Link Establishment
Request message (TS 24.554 \[29\]) and reception of
*RRCReconfigurationSidelink* message including initial DRX configuration
or the link establishment procedure being aborted by upper layer; or

\- the time between transmission of *RRCReconfigurationSidelink* message
including initial DRX configuration and reception of corresponding
*RRCReconfigurationCompleteSidelink* or
*RRCReconfigurationFailureSidelink* message.

When one or multiple SL DRX is configured, the MAC entity shall, for
each Destination Layer-2 ID associated to groupcast or broadcast:

1\> if a single *sl-DRX-GC-BC-Cycle* that is mapped with one or multiple
*SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List* or a single
*sl-DRX-GC-BC-Cycle* that is configured in *sl-DefaultDRX-GC-BC* and
none of the QoS profiles associated to the Destination Layer-2 ID can be
mapped with any *SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List*:

2\> select the *sl-DRX-GC-BC-Cycle* that is mapped with one or multiple
*SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List* or the
*sl-DRX-GC-BC-Cycle* configured in *sl-DefaultDRX-GC-BC*.

1\> else if multiple *sl-DRX-GC-BC-Cycle* that include one or multiple
*sl-DRX-GC-BC-Cycle* that are mapped with one or multiple
*SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List* and, if applicable, one
*sl-DRX-GC-BC-Cycle* that is configured in *sl-DefaultDRX-GC-BC* and at
least one QoS profile associated to the Destination Layer-2 ID cannot be
mapped with any *SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List*:

2\> select the *sl-DRX-GC-BC-Cycle* whose length is the shortest one
among multiple *sl-DRX-GC-BC-Cycle* that are mapped with one or multiple
*SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List* and, if applicable,
*sl-DRX-GC-BC-Cycle* configured in *sl-DefaultDRX-GC-BC*.

1\> if a single *sl-DRX-GC-BC-OnDurationTimer* that is mapped with one
or multiple *SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List* or a single
*sl-DRX-GC-BC-OnDurationTimer* that is configured in
*sl-DefaultDRX-GC-BC* and none of the QoS profiles associated to the
Destination Layer-2 ID can be mapped with any *SL-QoS-Profile* in
*sl-DRX-GC-BC-PerQoS-List*:

2\> select the *sl-DRX-GC-BC-OnDurationTimer* that is mapped with one or
multiple *SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List* or the
*sl-DRX-GC-BC-OnDurationTimer* configured in *sl-DefaultDRX-GC-BC*.

1\> else if multiple *sl-DRX-GC-BC-OnDurationTimer* that include one or
multiple *sl-DRX-GC-BC-OnDurationTimer* that are mapped with one or
multiple *SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List* and, if
applicable, one *sl-DRX-GC-BC-OnDurationTimer* that is configured in
*sl-DefaultDRX-GC-BC* and at least one QoS profile associated to the
Destination Layer-2 ID cannot be mapped with any *SL-QoS-Profile* in
*sl-DRX-GC-BC-PerQoS-List*:

2\> select the *sl-DRX-GC-BC-OnDurationTimer* whose length is the
longest one among multiple *sl-DRX-GC-BC-OnDurationTimer* that are
mapped with one or multiple *SL-QoS-Profile* in
*sl-DRX-GC-BC-PerQoS-List* and, if applicable, *sl-DRX-GC-BC-Cycle*
configured in *sl-DefaultDRX-GC-BC*.

1\> if a single *sl-DRX-GC-InactivityTimer* that is mapped with one or
multiple *SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List* or a single
*sl-DRX-GC-InactivityTimer* that is configured in *sl-DefaultDRX-GC-BC*
and none of the QoS profiles associated to the Destination Layer-2 ID
can be mapped with any *SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List*
and the associated cast type is groupcast:

2\> select the *sl-DRX-GC-InactivityTimer* that is mapped with one or
multiple *SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List* or the
*sl-DRX-GC-InactivityTimer* configured in *sl-DefaultDRX-GC-BC*.

1\> else if multiple *sl-DRX-GC-InactivityTimer* that include one or
multiple *sl-DRX-GC-InactivityTimer* that are mapped with one or
multiple *SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List* and, if
applicable, one *sl-DRX-GC-InactivityTimer* that is configured in
*sl-DefaultDRX-GC-BC* and at least one QoS profile associated to the
Destination Layer-2 ID cannot be mapped with any *SL-QoS-Profile* in
*sl-DRX-GC-BC-PerQoS-List* and the associated cast type is groupcast:

2\> select *sl-DRX-GC-InactivityTimer* whose length is the longest one
among multiple *sl-DRX-GC-InactivityTimer* that are mapped with one or
multiple *SL-QoS-Profile* in *sl-DRX-GC-BC-PerQoS-List* and, if
applicable, *sl-DRX-GC-InactivityTimer* configured in
*sl-DefaultDRX-GC-BC*.

The MAC entity shall:

1\> if an *sl-drx-HARQ-RTT-Timer* expires:

2\> if the data of the corresponding Sidelink process was not
successfully decoded or if the HARQ feedback (i.e., negative
acknowledgement) is not transmitted for unicast due to UL/SL
prioritization:

> 3\> start the
> *sl-drx-RetransmissionTimer*/*sl-DRX-GC-RetransmissionTimer* for the
> corresponding Sidelink process in the first slot after the expiry of
> *sl-drx-HARQ-RTT-Timer*.

When the cast type is groupcast or broadcast as indicated by upper
layer, or the cast type is unicast for the reception of Direct Link
Establishment Request message \[28\] or ProSe Direct Link Establishment
Request message \[29\] as indicated by upper layer, or for the reception
of discovery message \[26\], the *sl-drx-StartOffset* and
*sl-drx-SlotOffset* are derived from the following equations:

> *sl-drx-StartOffset* (ms) = Destination Layer-2 ID modulo
> *sl-DRX-GC-BC-Cycle* (ms).
>
> *sl-drx-SlotOffset* (ms) = (Destination Layer-2 ID modulo the number
> of slots in one subframe)\
> / (the number of slots in one subframe) (ms).

The MAC entity shall:

1\> if the SL DRX cycle is used, and \[(DFN × 10) + subframe number\]
modulo (*sl-drx-Cycle* or *sl-DRX-GC-BC-Cycle*) = *sl-drx-StartOffset*:

2\> start *sl-drx-onDurationTimer*/*sl-DRX-GC-BC-OnDurationTimer* after
*sl-drx-SlotOffset* from the beginning of the subframe.

1\> if an SL DRX is in Active Time:

2\> monitor the SCI (i.e., 1^st^ stage SCI and 2^nd^ stage SCI).

2\> if the SCI indicates a new SL transmission:

3\> if Source Layer-1 ID of the SCI is equal to the 8 LSB of the
intended Destination Layer-2 ID and Destination Layer-1 ID of the SCI is
equal to the 16 LSB of the intended Source Layer-2 ID and the cast type
indicator in the SCI is set to unicast:

4\> start or restart *sl-drx-InactivityTimer* for the corresponding
Source Layer-2 ID and Destination Layer-2 ID pair in the first slot
after SCI reception.

3\> if Destination Layer-1 ID of the SCI (i.e., 2^nd^ stage SCI) is
equal to the 16 LSB of the intended Destination Layer-2 ID and the cast
type indicator in the SCI is set to groupcast:

4\> start or restart *sl-DRX-GC-InactivityTimer* for the corresponding
Destination Layer-2 ID in the first slot after SCI reception.

2\> if the SCI indicates an SL transmission:

3\> if a next retransmission opportunity is indicated in the SCI:

4\> derive the *sl-drx-HARQ-RTT-Timer* from the retransmission resource
timing of the next retransmission resource in the SCI.

3\> else if PSFCH resource is configured for the SL grant associated to
the SCI:

4\> set the *sl-drx-HARQ-RTT-Timer* based on *sl-drx-HARQ-RTT-Timer1*
configured by upper layer if the cast type associated with the SCI is
unicast or *sl-DRX-GC-HARQ-RTT-Timer1* configured by upper layer if the
cast type associated with the SCI is groupcast when HARQ feedback is
enabled, or based on *sl-drx-HARQ-RTT-Timer2* configured by upper layer
if the cast type associated with the SCI is unicast or
*sl-DRX-GC-HARQ-RTT-Timer2* configured by upper layer if the cast type
associated with the SCI is groupcast when HARQ feedback is disabled, for
resource pool configured with PSFCH.

3\> else (i.e., if PSFCH resource is not configured for the SL grant
associated to the SCI):

4\> set the *sl-drx-HARQ-RTT-Timer* as 0 slots.

> 3\> if PSFCH resource is not configured for the SL grant associated to
> the SCI:

4\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the slot following the end of PSSCH transmission (i.e.,
currently received PSSCH).

> 3\> if PSFCH resource is configured for the SL grant associated to the
> SCI:

4\> if HARQ feedback is enabled by the SCI and the cast type associated
with the SCI is unicast:

5\> if *sl-NumPSFCH-Occasions* is configured as specified in TS 38.331
\[5\]:

6\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the first slot after the end of corresponding PSFCH
transmission carrying the SL HARQ Feedback when the SL HARQ feedback is
successfully transmitted in one of PSFCH occasions from
*sl-NumPSFCH-Occasions*; or

6\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the first slot after the end of the last PSFCH occasion for
the SL HARQ Feedback when the SL HARQ feedback is not transmitted in all
PSFCH occasions from *sl-NumPSFCH-Occasions*.

5\> else:

6\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the first slot after the end of the corresponding PSFCH
transmission carrying the SL HARQ feedback; or

6\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the first slot after the end of the corresponding PSFCH
resource for the SL HARQ feedback when the SL HARQ feedback is not
transmitted due to UL/SL prioritization or SL LBT failure.

4\> if HARQ feedback is enabled by the SCI and the cast type associated
with the SCI is groupcast and positive-negative acknowledgement is
selected:

5\> if *sl-NumPSFCH-Occasions* is configured as specified in TS 38.331
\[5\]:

6\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the first slot after the end of the last PSFCH occasion for
the SL HARQ Feedback.

5\> else:

6\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the first slot after the end of the corresponding PSFCH
transmission carrying the SL HARQ feedback; or

6\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the first slot after the end of the corresponding PSFCH
resource for the SL HARQ feedback when the SL HARQ feedback is not
transmitted due to UL/SL prioritization.

4\> if HARQ feedback is enabled by the SCI and the cast type associated
with the SCI is groupcast and negative-only acknowledgement is selected;

5\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the first slot after the end of the corresponding PSFCH
transmission carrying the SL HARQ feedback; or

5\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the first slot after the end of the corresponding PSFCH
resource for the SL HARQ feedback when the SL HARQ feedback is not
transmitted due to UL/SL prioritization; or

5\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the first slot after the end of the corresponding PSFCH
resource for the SL HARQ feedback when the SL HARQ feedback is a
positive acknowledgement.

4\> if HARQ feedback is disabled by the SCI and the resource(s) for one
or more retransmission opportunities is not scheduled in the SCI:

5\> if *sl-NumPSFCH-Occasions* is configured as specified in TS 38.331
\[5\]:

6\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the first slot after the end of the last PSFCH occasion.

5\> else:

6\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the slot following the end of PSFCH resource.

4\> if HARQ feedback is disabled by the SCI and the resource(s) for one
or more retransmission opportunities is scheduled in the SCI:

5\> start the *sl-drx-HARQ-RTT-Timer* for the corresponding Sidelink
process in the slot following the end of PSSCH transmission (i.e.,
currently received PSSCH).

NOTE: Void.

> 3\> stop the
> *sl-drx-RetransmissionTimer*/*sl-DRX-GC-RetransmissionTimer* for the
> corresponding Sidelink process.

1\> if an SL DRX Command MAC CE is received for the Source Layer-2 ID
and Destination Layer-2 ID pair of a unicast:

2\> stop *sl-drx-onDurationTimer* for the Source Layer-2 ID and
Destination Layer-2 ID pair of a unicast;

2\> stop *sl-drx-InactivityTimer* for the Source Layer-2 ID and
Destination Layer-2 ID pair of a unicast.