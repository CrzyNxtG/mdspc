### 5.2.6 Selection of cell at transition to RRC_IDLE or RRC_INACTIVE state

At reception of *RRCRelease* message to transition the UE to RRC_IDLE or
RRC_INACTIVE, UE shall attempt to camp on a suitable cell according to
*redirectedCarrierInfo* if included in the *RRCRelease* message. If the
UE cannot find a suitable cell, the UE is allowed to camp on any
suitable cell of the indicated RAT. If the *RRCRelease* message does not
contain the *redirectedCarrierInfo,* UE shall attempt to select a
suitable cell on an NR carrier. If no suitable cell is found according
to the above, the UE shall perform cell selection using stored
information in order to find a suitable cell to camp on.

When returning to RRC_IDLE state after UE moved to RRC_CONNECTED state
from *camped on any cell* state, UE shall attempt to camp on an
acceptable cell according to *redirectedCarrierInfo*, if included in the
*RRCRelease* message. If the UE cannot find an acceptable cell, the UE
is allowed to camp on any acceptable cell of the indicated RAT. If the
*RRCRelease* message does not contain *redirectedCarrierInfo* UE shall
attempt to select an acceptable cell on an NR frequency. If no
acceptable cell is found according to the above, the UE not in SNPN
Access Mode shall continue to search for an acceptable cell of any PLMN
in state *any cell selection*. If no acceptable cell is found according
to the above, the UE in SNPN access mode shall continue to search for an
acceptable cell of any SNPN in state *any cell selection*.