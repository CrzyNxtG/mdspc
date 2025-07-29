### 5.7.20 Actions related to Transmission of SRS for Positioning in a validity area in RRC_INACTIVE

When configured with *srs-PosRRC-InactiveValidityAreaPreConfigList*, the
UE shall:

1\> upon receiving *RRCRelease* message after sending the
*RRCResumeRequest* message with the *resumeCause* set to
*srs-PosConfigOrActivationReq*:

2\> if the current camped cell is included in any
*srs-PosConfigValidityArea* in the
*srs-PosRRC-InactiveValidityAreaPreConfigList*:

3\> apply the corresponding preconfigured SRS for positioning available
in *srs-PosRRC-InactiveValidityAreaPreConfigList* and instruct lower
layers to initiate SRS for Positioning transmission.