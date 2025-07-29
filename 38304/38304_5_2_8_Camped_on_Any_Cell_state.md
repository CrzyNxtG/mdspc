### 5.2.8 Camped on Any Cell state

This state is only applicable for RRC_IDLE state. In this state, the UE
shall perform the following tasks:

\- monitor Short Messages transmitted with P-RNTI over DCI as specified
in clause 6.5 in TS 38.331 \[3\];

\- monitor relevant System Information as specified in TS 38.331 \[3\];

\- perform necessary measurements for the cell reselection evaluation
procedure;

\- execute the cell reselection evaluation process on the following
occasions/triggers:

1\) UE internal triggers, so as to meet performance as specified in TS
38.133 \[8\];

2\) When information on the BCCH used for the cell reselection
evaluation procedure has been modified.

\- regularly attempt to find a suitable cell trying all frequencies of
all RATs that are supported by the UE. If a suitable cell is found, UE
shall move to *camped normally* state.

\- if the UE supports voice services, the UE is not in SNPN access mode,
and the current cell does not support IMS emergency calls as indicated
by the field *ims-EmergencySupport* in SIB1 as specified in TS 38.331
\[3\], the UE shall perform cell selection/reselection to an acceptable
cell that supports emergency calls in any supported RAT regardless of
priorities provided in system information from current cell, if no
suitable cell is found.

\- if the UE supports voice services, the UE is in SNPN access mode, and
the current cell does not support IMS emergency calls for any SNPN(s) as
indicated by the field *imsEmergencySupportForSNPN* in SIB1 as specified
in TS 38.331 \[3\], the UE shall perform cell selection/reselection to
an acceptable cell of any available SNPN that supports emergency calls,
if no suitable cell is found.