### 6.3.2 Frequency hopping for PUSCH repetition Type B

For PUSCH repetition Type B (as determined according to procedures
defined in Clause 6.1.2.1 for scheduled PUSCH, or Clause 6.1.2.3 for
configured PUSCH), a UE is configured for frequency hopping by the
higher layer parameter *frequencyHoppingDCI-0-2* in *pusch-Config* for
PUSCH transmission scheduled by DCI format 0_2, by
*frequencyHoppingDCI-0-1* provided in *pusch-Config* for PUSCH
transmission scheduled by DCI format 0_1, and by
*frequencyHoppingPUSCH-RepTypeB* provided in *rrc-ConfiguredUplinkGrant*
for Type 1 configured PUSCH transmission. The frequency hopping mode for
Type 2 configured PUSCH transmission follows the configuration of the
activating DCI format. One of two frequency hopping modes can be
configured:

\- Inter-repetition frequency hopping

\- Inter-slot frequency hopping

For operation with shared spectrum channel access in FR1, the UE does
not expect that two hops of a PUSCH transmission are in different RB
sets.

In case of resource allocation type 1, whether or not transform
precoding is enabled for PUSCH transmission, the UE may perform PUSCH
frequency hopping, if the frequency hopping field in a corresponding
detected DCI format is set to 1, or if for a Type 1 PUSCH transmission
with a configured grant the higher layer parameter
*frequencyHoppingPUSCH-RepTypeB* is provided, otherwise no PUSCH
frequency hopping is performed. When frequency hopping is enabled for
PUSCH, the RE mapping is defined in clause 6.3.1.6 of \[4, TS 38.211\].

For a PUSCH scheduled by DCI format 0_1 or a PUSCH based on a Type 2
configured UL grant activated by DCI format 0_1 and for resource
allocation type 1, frequency offsets are configured by higher layer
parameter *frequencyHoppingOffsetLists* in *pusch-Config*. For a PUSCH
scheduled by DCI format 0_2 or a PUSCH based on a Type 2 configured UL
grant activated by DCI format 0_2 and for resource allocation type 1,
frequency offsets are configured by higher layer parameter
*frequencyHoppingOffsetListsDCI-0-2* in *pusch-Config*.

\- When the size of the active BWP is less than 50 PRBs, one of two
higher layer configured offsets is indicated in the UL grant.

\- When the size of the active BWP is equal to or greater than 50 PRBs,
one of four higher layer configured offsets is indicated in the UL
grant.

For PUSCH based on a Type1 configured UL grant the frequency offset is
provided by the higher layer parameter *frequencyHoppingOffset* in
*rrc-ConfiguredUplinkGrant*.

In case of inter-repetition frequency hopping, the starting RB for an
actual repetition within the *n*-th nominal repetition (as defined in
Clause 6.1.2.1) is given by:

![](media/image801.png){width="3.0586132983377077in"
height="0.4653313648293963in"},

where RB~start~ is the starting RB within the UL BWP, as calculated from
the resource block assignment information of resource allocation type 1
(described in Clause 6.1.2.2.2) and RB~offset~ is the frequency offset
in RBs between the two frequency hops.

In case of inter-slot frequency hopping, the starting RB during slot
![](media/image796.wmf) follows that of inter-slot frequency hopping for
PUSCH Repetition Type A in Clause 6.3.1.