### 5.3.2 Unified access control

The information on cell access restrictions associated with Access
Categories and Identities is broadcast in *SIB1* as part of Unified
Access Control as specified in TS 38.331 \[3\].

The UE shall ignore Access Category and Identity related cell access
restrictions for cell reselection. A change of the indicated access
restriction shall not trigger cell reselection by the UE.

The UE shall consider Access Category and Identity related cell access
restrictions for NAS initiated access attempts and RNAU as specified in
TS 38.331 \[3\].

A L2 U2N Relay UE does not need to perform the Unified Access Control as
specified in TS 38.331 \[3\], due to the U2N Remote UE access attempt.