### 5.1.5 PDCP entity reconfiguration

When upper layers reconfigure the PDCP entity to configure DAPS, the UE
shall:

\- establish a ciphering function for the radio bearer and apply the
ciphering algorithm and key provided by upper layers for the ciphering
function;

\- establish an integrity protection function for the radio bearer and
apply the integrity protection algorithm and key provided by upper
layers for the integrity protection function;

\- establish a header compression protocol for the radio bearer and
apply the header compression configuration provided by upper layers for
the header compression protocol.

When upper layers reconfigure the PDCP entity to release DAPS, the UE
shall:

\- release the ciphering function associated to the released RLC entity
for the radio bearer;

\- release the integrity protection function associated to the released
RLC entity for the radio bearer;

\- release the header compression protocol associated to the released
RLC entity for the radio bearer.

NOTE 1: The state variables which control the transmission and reception
operation should not be reset, and the timers including *t-Reordering,*
*discardTimer*, and *discardTimerForLowImportance* keep running during
PDCP entity reconfiguration procedure.

NOTE 2: Before releasing the header compression protocol associated to
the released RLC entity, how to handle all stored PDCP SDUs received
from the released RLC entity is left up to UE implementation.

NOTE 3: No special handling for the header compression protocol is
defined to avoid potential security issue (e.g. keystream reuse) for
DAPS handover with no security key change.