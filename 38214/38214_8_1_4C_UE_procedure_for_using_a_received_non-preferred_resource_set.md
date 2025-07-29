### 8.1.4C UE procedure for using a received non-preferred resource set

A UE configured with the higher layer parameter
*sl-InterUE-CoordinationScheme1* uses a received non-preferred resource
set as follows when performing resource (re-)selection:

\- the UE excludes in Step 6b) of clause 8.1.4 resource(s) overlapping
with the non-preferred resource set.

If it is not possible to meet the requirement that the number of
candidate single-slot resources remaining in the set $S_{A}$ be at least
$X \cdot M_{\text{total}}$ after excluding resource(s) overlapping with
the received non-preferred resource set, it is up to UE implementation
whether or not to take into account the received non-preferred resource
set to meet such requirement.

The UE is not required to use any resource from the non-preferred
resource set in its resource (re-)selection if that resource is earlier
than ($T_{proc,0}^{SL}$+ $T_{proc,1}^{SL}$+ $T_{proc,2}^{SL}$) after the
resource of inter-UE coordination information transmission, where
$T_{proc,2}^{SL}$ is equal to ($T_{proc,0}^{SL}$+ $T_{proc,1}^{SL}$)
when only MAC CE is used for inter-UE coordination information
transmission, or $T_{proc,2}^{SL}$ is equal to $T_{proc,0}^{SL}$ when
MAC CE and SCI format 2-C are both used for inter-UE coordination
information transmission.

The case when $T_{proc,2}^{SL}$ is equal to $T_{proc,0}^{SL}$ is
assuming that SCI format 2-C is received.