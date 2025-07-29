### 5.4.5 Buffer Status Reporting

The Buffer Status reporting (BSR) procedure is used to provide the
serving gNB with information about UL data volume in the MAC entity.

RRC configures the following parameters to control the BSR:

\- *periodicBSR-Timer*;

\- *retxBSR-Timer*;

\- *logicalChannelSR-DelayTimerApplied*;

\- *logicalChannelSR-DelayTimer*;

\- *logicalChannelSR-Mask*;

\- *logicalChannelGroup*, *logicalChannelGroupIAB-Ext*;

\- *sdt-LogicalChannelSR-DelayTimer*;

\- *additionalBS-TableAllowed*.

Each logical channel may be allocated to an LCG using the
*logicalChannelGroup*. The maximum number of LCGs is eight except for
IAB-MTs configured with *logicalChannelGroupIAB-Ext*, for which the
maximum number of LCGs is 256.

The MAC entity determines the amount of UL data available for a logical
channel according to the data volume calculation procedure in TSs 38.322
\[3\] and 38.323 \[4\].

A BSR shall be triggered if any of the following events occur for
activated cell group:

\- UL data, for a logical channel which belongs to an LCG, becomes
available to the MAC entity; and either

\- this UL data belongs to a logical channel with higher priority than
the priority of any logical channel containing available UL data which
belong to any LCG; or

\- none of the logical channels which belong to an LCG contains any
available UL data.

in which case the BSR is referred below to as \'Regular BSR\';

\- UL resources are allocated and number of padding bits is equal to or
larger than the size of the Buffer Status Report MAC CE plus its
subheader, in which case the BSR is referred below to as \'Padding
BSR\';

\- *retxBSR-Timer* expires, and at least one of the logical channels
which belong to an LCG contains UL data, in which case the BSR is
referred below to as \'Regular BSR\';

\- *periodicBSR-Timer* expires, in which case the BSR is referred below
to as \'Periodic BSR\'.

NOTE 1: When Regular BSR triggering events occur for multiple logical
channels simultaneously, each logical channel triggers one separate
Regular BSR.

For Regular BSR, the MAC entity shall:

1\> if the BSR is triggered for a logical channel for which
*logicalChannelSR-DelayTimerApplied* with value *true* is configured by
upper layers and SDT procedure is not ongoing according to clause 5.27:

2\> start or restart the *logicalChannelSR-DelayTimer*.

1\> else if BSR is triggered for a logical channel for which
*logicalChannelSR-DelayTimerApplied* with value *true* is configured by
upper layers and SDT procedure is ongoing according to clause 5.27:

2\> start or restart *logicalChannelSR-DelayTimer* with the value as
configured by the *sdt-LogicalChannelSR-DelayTimer*, if configured.

1\> else:

2\> if running, stop the *logicalChannelSR-DelayTimer*.

For Regular and Periodic BSR, the MAC entity for which
*logicalChannelGroupIAB-Ext* is not configured by upper layers shall:

1\> if for at least one LCG configured with *additionalBS-TableAllowed,*
the amount of UL data available for transmission when the MAC PDU
containing the BSR is to be built is within the buffer sizes specified
in Table 6.1.3.1-3:

2\> report Refined Long BSR for all LCGs which have data available for
transmission;

1\> else:

2\> if more than one LCG has data available for transmission when the
MAC PDU containing the BSR is to be built:

3\> report Long BSR for all LCGs which have data available for
transmission.

2\> else if one LCG has data available and is configured with
*additionalBS-TableAllowed* and the amount of UL data available for
transmission when the MAC PDU containing the BSR is to be built is
greater than the largest buffer size specified in Table 6.1.3.1-3:

3\> report Long BSR.

2\> else:

3\> report Short BSR.

For Regular and Periodic BSR, the MAC entity for which
*logicalChannelGroupIAB-Ext* is configured by upper layers shall:

1\> if more than one LCG has data available for transmission when the
MAC PDU containing the BSR is to be built:

2\> if the maximum LCG ID among the configured LCGs is 7 or lower:

3\> report Long BSR for all LCGs which have data available for
transmission.

2\> else:

3\> report Extended Long BSR for all LCGs which have data available for
transmission.

1\> else:

2\> report Extended Short BSR.

For Padding BSR, the MAC entity for which *logicalChannelGroupIAB-Ext*
is not configured by upper layers shall:

1\> if the number of padding bits is equal to or larger than the size of
the Short BSR plus its subheader but smaller than the size of the Long
BSR plus its subheader:

2\> if more than one LCG has data available for transmission when the
BSR is to be built:

3\> if the number of padding bits is equal to the size of the Short BSR
plus its subheader:

4\> report Short Truncated BSR of the LCG with the highest priority
logical channel with data available for transmission.

3\> else:

4\> report Long Truncated BSR of the LCG(s) with the logical channels
having data available for transmission following a decreasing order of
the highest priority logical channel (with or without data available for
transmission) in each of these LCG(s), and in case of equal priority, in
increasing order of LCGID.

2\> else:

3\> report Short BSR.

1\> else if for at least one LCG configured with
*additionalBS-TableAllowed*, the amount of UL data available for
transmission when the MAC PDU containing the BSR is to be built is
within the buffer sizes specified in Table 6.1.3.1-3 and the number of
padding bits is equal to or larger than the size of the Refined Long BSR
plus its subheader:

2\> report Refined Long BSR for all LCGs which have data available for
transmission.

1\> else if the number of padding bits is equal to or larger than the
size of the Long BSR plus its subheader:

2\> report Long BSR for all LCGs which have data available for
transmission.

For Padding BSR, the MAC entity for which *logicalChannelGroupIAB-Ext*
is configured by upper layers shall:

1\> if the number of padding bits is equal to or larger than the size of
the Extended Short BSR plus its subheader but smaller than the size of
the Extended Long BSR plus its subheader:

2\> if more than one LCG has data available for transmission when the
BSR is to be built:

3\> if the number of padding bits is smaller than the size of the
Extended Long Truncated BSR with zero Buffer Size field plus its
subheader:

4\> report Extended Short Truncated BSR of the LCG with the highest
priority logical channel with data available for transmission.

3\> else:

4\> report Extended Long Truncated BSR of the LCG(s) with the logical
channels having data available for transmission following a decreasing
order of the highest priority logical channel (with or without data
available for transmission) in each of these LCG(s), and in case of
equal priority, in increasing order of LCGID.

2\> else:

3\> report Extended Short BSR.

1\> else if the number of padding bits is equal to or larger than the
size of the Extended Long BSR plus its subheader:

2\> report Extended Long BSR for all LCGs which have data available for
transmission.

For BSR triggered by *retxBSR-Timer* expiry, the MAC entity considers
that the logical channel that triggered the BSR is the highest priority
logical channel that has data available for transmission at the time the
BSR is triggered.

The MAC entity shall:

1\> if the Buffer Status reporting procedure determines that at least
one BSR has been triggered and not cancelled:

2\> if UL-SCH resources are available for a new transmission and the
UL-SCH resources can accommodate the BSR MAC CE plus its subheader as a
result of logical channel prioritization:

3\> instruct the Multiplexing and Assembly procedure to generate the BSR
MAC CE(s) as defined in clause 6.1.3.1;

3\> start or restart *periodicBSR-Timer* except when all the generated
BSRs are long or short Truncated or Extended long or short Truncated
BSRs;

3\> start or restart *retxBSR-Timer*.

2\> if a Regular BSR has been triggered and
*logicalChannelSR-DelayTimer* is not running:

3\> if there is no UL-SCH resource available for a new transmission; or

3\> if the MAC entity is configured with configured uplink grant(s) and
the Regular BSR was triggered for a logical channel for which
*logicalChannelSR-Mask* is set to *false*; or

3\> if the UL-SCH resources available for a new transmission do not meet
the LCP mapping restrictions (see clause 5.4.3.1) configured for the
logical channel that triggered the BSR:

4\> trigger a Scheduling Request.

NOTE 2: UL-SCH resources are considered available if the MAC entity has
an active configured grant, or receives, or determines an uplink grant.
If the MAC entity has determined at a given point in time that UL-SCH
resources are available, this need not imply that UL-SCH resources are
available for use at that point in time.

A MAC PDU shall contain at most one BSR MAC CE, even when multiple
events have triggered a BSR. The Regular BSR and the Periodic BSR shall
have precedence over the padding BSR.

The MAC entity shall restart *retxBSR-Timer* upon reception of a grant
for transmission of new data on any UL-SCH.

All triggered BSRs may be cancelled when the UL grant(s) can accommodate
all pending data available for transmission but is not sufficient to
additionally accommodate the BSR MAC CE plus its subheader. All BSRs
triggered prior to MAC PDU assembly shall be cancelled when a MAC PDU is
transmitted and this PDU includes a Long, Refined Long, Extended Long,
Short, or Extended Short BSR MAC CE which contains buffer status up to
(and including) the last event that triggered a BSR prior to the MAC PDU
assembly.

NOTE 3: MAC PDU assembly can happen at any point in time between uplink
grant reception and actual transmission of the corresponding MAC PDU.
BSR and SR can be triggered after the assembly of a MAC PDU which
contains a BSR MAC CE, but before the transmission of this MAC PDU. In
addition, BSR and SR can be triggered during MAC PDU assembly.

NOTE 4: Void

NOTE 5: If a HARQ process is configured with *cg-RetransmissionTimer*
and if the BSR is already included in a MAC PDU for transmission on
configured grant by this HARQ process, but not yet transmitted by lower
layers, it is up to UE implementation how to handle the BSR content.