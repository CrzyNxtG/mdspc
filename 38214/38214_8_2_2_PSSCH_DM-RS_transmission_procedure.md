### 8.2.2 PSSCH DM-RS transmission procedure

The UE selects the DM-RS time domain pattern out of the patterns
configured using the higher layer parameter
*sl-PSSCH-DMRS-TimePatternList* for the resource pool on which the PSSCH
is to be transmitted. If more than one DM-RS time domain pattern is
configured, the selected pattern is indicated by the \'*DMRS pattern*\'
field in the SCI format 1-A associated with the PSSCH transmission.

If PSSCH DM-RS and PSCCH are mapped to the same OFDM symbol, then this
mapping within a single sub-channel is only supported if higher layer
parameter *sl-SubchannelSize* \>= 20, i.e. the sub-channel size is at
least 20 PRBs.

When a sub-channel size is less than 20 PRBs and the size of PSCCH is
less than the sub-channel size, a UE is not expected to choose a PSSCH
DM-RS pattern to be transmitted in the same OFDM symbol with PSCCH.