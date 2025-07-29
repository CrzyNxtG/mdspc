### 8.1.4A UE procedure for determining a set of preferred or non-preferred resources for another UE\'s transmission

When this procedure is triggered, the following parameters are provided
by the higher layer:

\- the resource pool from which the preferred or non-preferred resources
are to be determined;

\- the resource selection window $\lbrack n + T_{1},n + T_{2}\rbrack$
within which the preferred or non-preferred resources are to be
determined;

\- the resource set type (either preferred or non-preferred resource
set);

\- if the resource set type indicates preferred set, then the higher
layer additionally provides the following parameters:

\- L1 priority, $prio_{TX}$;

\- the number of sub-channels to be used for the PSSCH/PSCCH
transmission in a slot, $L_{\text{subCH}}$;

\- If the higher layer parameter
*sl-TransmissionStructureForPSCCHandPSSCH* is set to \'interlaceRB\',
the number of used RB sets for one PSCCH/PSSCH transmission, *L~RBset~*;

\- the resource reservation period, $P_{\text{rsvp\_TX}}$, if present.

The value of $C_{resel}$ is determined by the UE according to clause
8.1.5.

When this procedure is triggered by another UE\'s explicit request, the
fields in the request are interpreted as follows:

> \- The field \'Resource selection window location\' is the
> concatenation of the starting time location and the ending time
> location of the resource selection window. The starting and ending
> time locations of the resource selection window are each encoded in
> the same way as the reference slot as described in clause 8.1.5A.
>
> \- The field \'Resource reservation period\' is encoded in the same
> way as the field of the same name in SCI format 1-A.

When determining a preferred resource set, the UE applies the procedure
described in clause 8.1.4, it is up to UE implementation whether to use
information determined by the E-UTRA radio access in case of dynamic
co-channel coexistence of LTE sidelink and NR sidelink, with the above
parameters and the following modifications:

\- Step 6a) The UE excludes candidate single-slot resource(s) belonging
to slot(s) where the UE does not expect to perform SL reception of a TB
due to half-duplex operation, if all the following conditions are met:

\- the UE is a destination UE of the TB for whose transmission the
preferred resource set is being determined;

\- the higher layer parameter *sl-Condition1-A-2* is not set to
\'Disabled\'.

When determining a non-preferred resource set, the UE considers any
resource(s) within the resource selection window, if indicated by a
received explicit request, and satisfying at least one of the following
conditions as non-preferred resource(s):

\- resource(s) indicated by a received SCI format 1-A, satisfying at
least one of the following criteria:

\- the RSRP measurement performed, according to clause 8.4.2.1, for the
received SCI format 1-A, is higher than $Th\left( prio_{RX} \right)$
where $prio_{RX}$ is the value of the priority field in the received SCI
format 1-A. The internal parameter $Th(p_{i})$ is set to the
corresponding value of RSRP threshold indicated by the *k*-th field in
*sl-ThresholdRSRP-Condition1-B-1-Option1List*, where $k = p_{i}$.

\- the UE is a destination UE of a TB associated with the received SCI
format 1-A and the RSRP measurement performed, according to clause
8.4.2.1 for the received SCI format 1-A, is lower than
$Th'\left( prio_{RX} \right)$ where $prio_{RX}$ is the value of the
priority field in the received SCI format 1-A. The internal parameter
$Th'(p_{i})$ is set to the corresponding value of RSRP threshold
indicated by the *k*-th field in
*sl-ThresholdRSRP-Condition1-B-1-Option2List*, where $k = p_{i}$.

\- resources(s) in slot(s) in which the UE does not expect to perform SL
reception due to half duplex operation, if the UE is a destination UE of
a TB for whose transmission the non-preferred resource set is being
determined.