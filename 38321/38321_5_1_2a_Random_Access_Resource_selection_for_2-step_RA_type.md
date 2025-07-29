### 5.1.2a Random Access Resource selection for 2-step RA type

If the selected *RA_TYPE* is set to *2-stepRA*, the MAC entity shall:

1\> if the Random access procedure was not initiated for recovering
using an LTM candidate configuration as specified in TS 38.331 \[5\]
clause 5.3.7.3 and if the contention-free 2-step RA type Resources
associated with SSBs have been explicitly provided in
*rach-ConfigDedicated* and at least one SSB with SS-RSRP above
*msgA-RSRP-ThresholdSSB* amongst the associated SSBs is available:

2\> select an SSB with SS-RSRP above *msgA-RSRP-ThresholdSSB* amongst
the associated SSBs;

2\> set the *PREAMBLE_INDEX* to a *ra-PreambleIndex* corresponding to
the selected SSB.

1\> else (i.e. for the contention-based Random Access Preamble
selection):

2\> if at least one of the SSBs with SS-RSRP above
*msgA-RSRP-ThresholdSSB* is available:

3\> select an SSB with SS-RSRP above *msgA-RSRP-ThresholdSSB*.

2\> else:

3\> select any SSB.

2\> if contention-free Random Access Resources for 2-step RA type have
not been configured and if Random Access Preambles group has not yet
been selected during the current Random Access procedure:

3\> if Random Access Preambles group B for 2-step RA type is configured:

4\> if the potential MSGA payload size (UL data available for
transmission plus MAC subheader and, where required, MAC CEs) is greater
than the *ra-MsgA-SizeGroupA* and the pathloss is less than *PCMAX* (of
the Serving Cell performing the Random Access Procedure) --
*msgA-PreambleReceivedTargetPower* -- *msgA-DeltaPreamble* --
*messagePowerOffsetGroupB*; or

4\> if the Random Access procedure was initiated for the CCCH logical
channel and the CCCH SDU size plus MAC subheader is greater than
*ra-MsgA-SizeGroupA*:

5\> select the Random Access Preambles group B.

4\> else:

5\> select the Random Access Preambles group A.

3\> else:

4\> select the Random Access Preambles group A.

2\> else if contention-free Random Access Resources for 2-step RA type
have been configured and if Random Access Preambles group has not yet
been selected during the current Random Access procedure:

3\> if Random Access Preambles group B for 2-step RA type is configured;
and

3\> if the transport block size of the MSGA payload configured in the
*rach-ConfigDedicated* corresponds to the transport block size of the
MSGA payload associated with Random Access Preambles group B:

4\> select the Random Access Preambles group B.

3\> else:

4\> select the Random Access Preambles group A.

2\> else (i.e. Random Access preambles group has been selected during
the current Random Access procedure):

3\> select the same group of Random Access Preambles as was used for the
Random Access Preamble transmission attempt corresponding to the earlier
transmission of MSGA.

2\> select a Random Access Preamble randomly with equal probability from
the 2-step RA type Random Access Preambles associated with the selected
SSB and the selected Random Access Preambles group;

2\> set the *PREAMBLE_INDEX* to the selected Random Access Preamble.

1\> determine the next available PRACH occasion from the PRACH occasions
corresponding to the selected SSB permitted by the restrictions given by
the *msgA-SSB-SharedRO-MaskIndex* if configured, or
*ra-ssb-OccasionMaskIndex* if configured, or *ssb-SharedRO-MaskIndex* if
configured (the MAC entity shall select a PRACH occasion randomly with
equal probability among the consecutive PRACH occasions allocated for
2-step RA type according to clause 8.1 of TS 38.213 \[6\] regardless the
FR2 UL gap, corresponding to the selected SSB; the MAC entity may take
into account the possible occurrence of measurement gaps and MUSIM gaps
when determining the next available PRACH occasion corresponding to the
selected SSB);

1\> if the Random Access Preamble was not selected by the MAC entity
among the contention-based Random Access Preamble(s):

2\> select a PUSCH occasion from the PUSCH occasions configured in
*msgA-CFRA-PUSCH* corresponding to the PRACH slot of the selected PRACH
occasion, according to *msgA-PUSCH-Resource-Index* corresponding to the
selected SSB;

2\> determine the UL grant and the associated HARQ information for the
MSGA payload in the selected PUSCH occasion;

2\> deliver the UL grant and the associated HARQ information to the HARQ
entity.

1\> else:

2\> select a PUSCH occasion corresponding to the selected preamble and
PRACH occasion according to clause 8.1A of TS 38.213 \[6\];

2\> determine the UL grant for the MSGA payload according to the PUSCH
configuration associated with the selected Random Access Preambles group
and determine the associated HARQ information;

2\> if the selected preamble and PRACH occasion is mapped to a valid
PUSCH occasion as specified in clause 8.1A of TS 38.213 \[6\]:

3\> deliver the UL grant and the associated HARQ information to the HARQ
entity.

1\> perform the MSGA transmission procedure (see clause 5.1.3a).

NOTE 1: To determine if there is an SSB with *SS-RSRP* above
*msgA-RSRP-ThresholdSSB*, the UE uses the latest unfiltered *L1-RSRP*
measurement.

NOTE 2: If an (e)RedCap UE in RRC_IDLE or RRC_INACTIVE mode is
configured with a BWP indicated by *initialDownlinkBWP-RedCap* which is
not associated with any SSB, SS-RSRP measurement is performed based on
the SSB associated with the BWP indicated by *initialDownlinkBWP*. If an
(e)RedCap UE in RRC_INACTIVE mode is configured with SDT and with a BWP
indicated by *initialDownlinkBWP-RedCap* which is associated with
NCD-SSB, SS-RSRP measurement can also be performed based on this NCD-SSB
during SDT.

NOTE 3: If an (e)RedCap UE in RRC_IDLE or RRC_INACTIVE mode is
configured with a BWP indicated by *initialDownlinkBWP-RedCap* which is
not associated with any SSB for RACH, it is up to the UE implementation
to perform a new RSRP measurements before Msg1/MsgA retransmission.