### 5.18.29 Timing case indication for IAB

Timing Case Indication MAC CE is used by an IAB-DU or an IAB-donor-DU to
indicate to its child node timing modes which should apply to time
resources indicated via RRC.

Upon reception of a Timing Case Indication MAC CE the IAB-node shall:

\- apply the configuration signalled in the MAC CE to the time slots
indicated in *IAB-ResourceConfig* which contains *iab-ResourceConfigID*
parameter (as specified in TS 38.331 \[5\]) which matches the Resource
Configuration ID field of the MAC CE.