### 5.8.8 Sidelink communication transmission

A UE capable of NR sidelink communication that is configured by upper
layers to transmit NR sidelink communication and has related data to be
transmitted shall:

1\> if the conditions for NR sidelink communication operation as defined
in 5.8.2 are met:

2\> if the frequency used for NR sidelink communication is included in
*sl-FreqInfoToAddModList*/*sl-FreqInfoToAddModListExt* in
*sl-ConfigDedicatedNR* within *RRCReconfiguration* message or included
in *sl-ConfigCommonNR* within *SIB12*:

3\> if the UE is in RRC_CONNECTED and uses the frequency included in
*sl-ConfigDedicatedNR* within *RRCReconfiguration* message:

4\> if the UE acting as U2U Relay UE is performing U2U Relay
Communication with integrated Discovery as specified in TS 23.304\[65\]
and *sl-DiscConfig* is included in *RRCReconfiguration*, and if the NR
sidelink U2U Relay UE threshold conditions for integrated Discovery as
specified in 5.8.16.2 are met based on *sl-RelayUE-ConfigU2U*; or

4\> if the UE capable of U2U Remote UE is performing U2U Relay
Communication with integrated Discovery as specified in TS 23.304\[65\]
and *sl-DiscConfig* is included in *RRCReconfiguration*, and if the NR
sidelink U2U Remote UE threshold conditions for integrated Discovery as
specified in 5.8.17.2 are met based on *sl-RemoteUE-ConfigU2U*; or

4\> if the UE is performing NR sidelink communication other than U2U
Relay Communication with integrated Discovery:

NOTE 0: For U2U Relay UE, it can be up to UE implementation on
cross-layer interaction for the AS layer condition check for Direct
Communication Request message with integrated discovery forwarding.

5\> if the UE is configured with *sl-ScheduledConfig*:

6\> if T310 for MCG or T311 is running; and if *sl-TxPoolExceptional* is
included in *sl-FreqInfoList*/*sl-FreqInfoListSizeExt* for the concerned
frequency in *SIB12* or included in *sl-ConfigDedicatedNR* in
*RRCReconfiguration*; or

6\> if T301 is running and the cell on which the UE initiated RRC
connection re-establishment provides SIB12 including
sl-TxPoolExceptional for the concerned frequency; or

6\> if T304 for MCG is running and the UE is configured with
sl-TxPoolExceptional included in sl-ConfigDedicatedNR for the concerned
frequency in RRCReconfiguration:

7\> configure lower layers to perform the sidelink resource allocation
mode 2 based on random selection using the pool of resources indicated
by *sl-TxPoolExceptional* as defined in TS 38.321 \[3\];

6\> else:

7\> configure lower layers to perform the sidelink resource allocation
mode 1 for NR sidelink communication;

6\> if T311 is running, configure the lower layers to release the
resources indicated by rrc-ConfiguredSidelinkGrant (if any);

5\> if the UE is configured with *sl-UE-SelectedConfig*:

6\> if a result of full/partial sensing, if selected and is allowed by
*sl-AllowedResourceSelectionConfig*, on the resources configured in
*sl-TxPoolSelectedNormal* for the concerned frequency included in
*sl-ConfigDedicatedNR* within *RRCReconfiguration* is not available in
accordance with TS 38.214 \[19\];

7\> if *sl-TxPoolExceptional* for the concerned frequency is included in
*RRCReconfiguration*; or

7\> if the PCell provides *SIB12* including *sl-TxPoolExceptional* in
*sl-FreqInfoList*/*sl-FreqInfoListSizeExt* for the concerned frequency:

8\> configure lower layers to perform the sidelink resource allocation
mode 2 based on random selection using the pool of resources indicated
by *sl-TxPoolExceptional* as defined in TS 38.321 \[3\];

6\> else, if the *sl-TxPoolSelectedNormal* for the concerned frequency
is included in the *sl-ConfigDedicatedNR* within *RRCReconfiguration*:

7\> configure lower layers to perform the sidelink resource allocation
mode 2 based on resource selection operation according to
*sl-AllowedResourceSelectionConfig* (as defined in TS 38.321 \[3\] and
TS 38.214 \[19\]) using the pools of resources indicated by
*sl-TxPoolSelectedNormal* for the concerned frequency;

3\> else:

4\> if the cell chosen for NR sidelink communication transmission
provides *SIB12*:

5\> if the UE acting as U2U Relay UE is performing U2U Relay
communication with integrated Discovery as specified in TS 23.304\[65\],
and if the NR sidelink U2U Relay UE threshold conditions for integrated
Discovery as specified in 5.8.16.2 are met based on
*sl-RelayUE-ConfigCommonU2U* in *SIB12*; or

5\> if the UE capable of U2U Remote UE is performing U2U Relay
Communication with integrated Discovery as specified in TS 23.304\[65\],
and if the NR sidelink U2U Remote UE threshold conditions for integrated
Discovery as specified in 5.8.17.2 are met based on
*sl-RemoteUE-ConfigCommonU2U* in *SIB12*; or

5\> if the UE is performing NR sidelink communication other than U2U
Relay Communication with integrated Discovery:

6\> if *SIB12* includes *sl-TxPoolSelectedNormal* for the concerned
frequency, and a result of full/partial sensing, if selected and is
allowed by *sl-AllowedResourceSelectionConfig*, on the resources
configured in the *sl-TxPoolSelectedNormal* is available in accordance
with TS 38.214 \[19\] or random selection, if allowed by
*sl-AllowedResourceSelectionConfig*, is selected:

7\> configure lower layers to perform the sidelink resource allocation
mode 2 based on resource selection operation according to
*sl-AllowedResourceSelectionConfig* using the pools of resources
indicated by *sl-TxPoolSelectedNormal* for the concerned frequency as
defined in TS 38.321 \[3\];

6\> else if *SIB12* includes *sl-TxPoolExceptional* for the concerned
frequency:

7\> from the moment the UE initiates RRC connection establishment or RRC
connection resume, until receiving an *RRCReconfiguration* including
*sl-ConfigDedicatedNR*, or receiving an *RRCRelease* or an *RRCReject*;
or

7\> if a result of full/partial sensing, if selected and is allowed by
*sl-AllowedResourceSelectionConfig*, on the resources configured in
*sl-TxPoolSelectedNormal* for the concerned frequency in *SIB12* is not
available in accordance with TS 38.214 \[19\]:

8\> configure lower layers to perform the sidelink resource allocation
mode 2 based on random selection (as defined in TS 38.321 \[3\]) using
the pool of resources indicated by *sl-TxPoolExceptional* for the
concerned frequency;

2\> else:

3\> if the UE acting as U2U Relay UE is performing U2U Relay
communication with integrated Discovery as specified in TS 23.304\[65\],
and if the NR sidelink U2U Relay UE threshold conditions for integrated
Discovery as specified in 5.8.16.2 are met based on
*sl-RelayUE-PreconfigU2U* in *SidelinkPreconfigNR*; or

3\> if the UE capable of U2U Remote UE is performing U2U Relay
Communication with integrated Discovery as specified in TS 23.304\[65\],
and if the NR sidelink U2U Remote UE threshold conditions for integrated
Discovery as specified in 5.8.17.2 are met based on
*sl-RemoteUE-PreconfigU2U* in *SidelinkPreconfigNR*; or

3\> if the UE is performing NR sidelink communication other than U2U
Relay Communication with integrated Discovery:

4\> configure lower layers to perform the sidelink resource allocation
mode 2 based on resource selection operation according to
*sl-AllowedResourceSelectionConfig* (as defined in TS 38.321 \[3\] and
TS 38.214 \[19\]) using the pools of resources indicated by
*sl-TxPoolSelectedNormal* in *SidelinkPreconfigNR* for the concerned
frequency.

NOTE 1: The UE continues to use resources configured in
*rrc-ConfiguredSidelinkGrant* (while T310 is running) until it is
released (i.e. until T310 has expired). The UE does not use sidelink
configured grant type 2 resources while T310 is running.

NOTE 2: In case of RRC reconfiguration with sync, the UE uses resources
configured in *rrc-ConfiguredSidelinkGrant* (while T304 on the MCG is
running) if provided by the target cell.

NOTE 3: It is up to UE implementation to determine, in accordance with
TS 38.321\[3\], which resource pool to use if multiple resource pools
are configured, and which resource allocation scheme is used in the AS
based on UE capability (for a UE in RRC_IDLE/RRC_INACTIVE) and the
allowed resource schemes *sl-AllowedResourceSelectionConfig* in the
resource pool configuration.

NOTE 4: In case that the network does not provide resource pools in
*SIB12*, a UE which is out of coverage, will be unable to obtain
sidelink resources to send the first UL RRC message.

If configured to perform sidelink resource allocation mode 2, the UE
capable of NR sidelink communication that is configured by upper layers
to transmit NR sidelink communication shall perform resource selection
operation according to *sl-AllowedResourceSelectionConfig* on all pools
of resources which may be used for transmission of the sidelink control
information and the corresponding data. The pools of resources are
indicated by *SidelinkPreconfigNR*, *sl-TxPoolSelectedNormal* in
*sl-ConfigDedicatedNR*, or *sl-TxPoolSelectedNormal* in *SIB12* for the
concerned frequency, as configured above.