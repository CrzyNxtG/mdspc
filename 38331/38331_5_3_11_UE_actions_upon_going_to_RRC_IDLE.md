### 5.3.11 UE actions upon going to RRC_IDLE

The UE shall:

1\> reset MAC;

1\> if the UE is NCR-MT:

2\> indicate to NCR-Fwd to cease forwarding;

1\> set the variable *pendingRNA-Update* to *false*, if that is set to
*true*;

1\> if going to RRC_IDLE was triggered by reception of the *RRCRelease*
message including a *waitTime*:

2\> if T302 is running:

3\> stop timer T302;

2\> start timer T302 with the value set to the *waitTime*;

2\> inform upper layers that access barring is applicable for all access
categories except categories \'0\' and \'2\'.

1\> else:

2\> if T302 is running:

3\> stop timer T302;

3\> perform the actions as specified in 5.3.14.4;

1\> if T390 is running:

2\> stop timer T390 for all access categories;

2\> perform the actions as specified in 5.3.14.4;

1\> if the UE is leaving RRC_INACTIVE:

2\> if going to RRC_IDLE was not triggered by reception of the
*RRCRelease message*:

3\> if stored, discard the cell reselection priority information
provided by the *cellReselectionPriorities*;

3\> stop the timer T320, if running;

2\> if SDT procedure is ongoing:

3\> stop timer T319a, if running;

3\> consider SDT procedure is not ongoing;

1\> stop all timers that are running except T302, T320, T325, T330,
T331, T400 and T430;

1\> discard the UE Inactive AS context, if any;

1\> release the *suspendConfig*, if configured;

1\> release the *aerial-Config*, if configured;

1\> perform LTM configuration release procedure for the MCG and SCG as
specified in clause 5.3.5.18.7;

1\> remove all the entries within the MCG and the SCG
*VarConditionalReconfig*, if any;

1\> remove the *servingSecurityCellSetId* within the
*VarServingSecurityCellSetID*, if any;

1\> for each *measId*, if the associated *reportConfig* has a
*reportType* set to *condTriggerConfig*:

2\> for the associated *reportConfigId*:

3\> remove the entry with the matching *reportConfigId* from the
*reportConfigList* within the *VarMeasConfig*;

2\> if the associated *measObjectId* is only associated to a
*reportConfig* with *reportType* set to *condTriggerConfig*:

3\> remove the entry with the matching *measObjectId* from the
*measObjectList* within the *VarMeasConfig*;

2\> remove the entry with the matching *measId* from the *measIdList*
within the *VarMeasConfig*;

1\> discard the K~gNB~ key, the S-K~gNB~ key, the S-K~eNB~ key, the
K~RRCenc~ key, the K~RRCint~ key, the K~UPint~ key and the K~UPenc~ key,
if any;

1\> if SL indirect path is configured:

2\> release cell identity and relay UE ID configured in
*sl-IndirectPathAddChange*;

2\> indicate upper layers to trigger PC5 unicast link release of the SL
indirect path;

1\> if N3C indirect path is configured:

2\> release *n3c-IndirectPathAddChange*;

2\> consider the non-3GPP connection is not used;

1\> if the UE is acting as a N3C relay UE:

2\> release *n3c-IndirectPathConfigRelay*;

2\> consider the non-3GPP connection is not used;

1\> release all radio resources, including release of the RLC entity,
the BAP entity, the MAC configuration and the associated PDCP entity and
SDAP for all established RBs (except for broadcast MRBs), BH RLC
channels, Uu Relay RLC channels, PC5 Relay RLC channels and SRAP entity;

NOTE 0: A L2 U2N Relay UE may re-establish the SL-RLC0, SL-RLC1 and SRAP
entity after release.

1\> indicate the release of the RRC connection to upper layers together
with the release cause;

1\> for each application layer measurement configuration without
*appLayerIdleInactiveConfig* configured:

2\> forward the *measConfigAppLayerId* and inform upper layers about the
release of the application layer measurement configuration;

2\> release the application layer measurement configuration;

2\> discard any application layer measurement reports which were not yet
fully submitted to lower layers for transmission;

2\> consider itself not to be configured to send application layer
measurement reports for the *measConfigAppLayerId*;

1\> for each application layer measurement configuration with
*appLayerIdleInactiveConfig* configured:

2\> forward the *measConfigAppLayerId* and inform upper layers about the
release of the RAN visible application layer measurement configuration;

2\> discard any RAN visible application layer measurement reports
received from upper layers;

2\> initiate the procedure in 5.5b.1.2;

1\> discard any segments of segmented RRC messages stored according to
5.7.6.3;

1\> except if going to RRC_IDLE was triggered by inter-RAT cell
reselection while the UE is in RRC_INACTIVE or RRC_IDLE or when
selecting an inter-RAT cell while T311 was running or when selecting an
E-UTRA cell for EPS fallback for IMS voice as specified in 5.4.3.5:

2\> if the UE is capable of L2 U2N Remote UE:

3\> enter RRC_IDLE, and perform either cell selection as specified in TS
38.304 \[20\], or relay selection as specified in clause 5.8.15.3, or
both;

2\> else:

3\> enter RRC_IDLE and perform cell selection as specified in TS 38.304
\[20\];

NOTE 1: Whether to release the PC5 unicast link is left to L2 U2N Remote
UE\'s implementation.

NOTE 2: It is left to UE implementation whether to stop T430, if
running, when going to RRC_IDLE.