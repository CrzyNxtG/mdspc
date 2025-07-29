### 5.3.1 Application delay of the minimum scheduling offset restriction

When the UE is scheduled with DCI format 0_1, 0_3, 1_1 or 1_3 with a
\'*Minimum applicable scheduling offset indicator*\' field in slot *n*,
it shall determine the *K*~0min~ and *K*~2min~ values, if configured
respectively, to be applied, while the previously applied *K*~0min~
and/or *K*~2min~ values are applied until the new values take effect. If
the DCI in slot *n* also indicates an active DL (UL) BWP change for a
serving cell, the indicated *K*~0min~ (*K*~2min~) value in the new
active DL (UL) BWP, if configured, is applied from the slot indicated by
the slot offset value of the time domain resource assignment field in
the DCI. Otherwise, change of applied minimum scheduling offset
restriction indication carried by DCI in slot *n*, shall be applied in
slot *n*+*X* of the scheduling cell. The UE does not expect to be
scheduled with DCI format 0_1, 0_3, 1_1 or 1_3 with \'*Minimum
applicable scheduling offset indicator*\' field indicating another
change to *K*~0min~ or *K*~2min~ for the same active BWP of the
scheduled cell before slot *n+X* of the scheduling cell.

When the DCI format 0_1, 0_3, 1_1 or 1_3 with \'*Minimum applicable
scheduling offset indicator*\' field indicating a change to the applied
*K*~0min~ or *K*~2min~ is contained within the first three symbols of
slot *n*, the value of application delay *X* is determined by,
$X = \max\left( \left\lceil K_{0minOld} \bullet \frac{2^{\mu_{PDCCH}}}{2^{\mu_{PDSCH}}} \right\rceil,Z_{\mu} \right)\ $where
*K*~0minOld~ is the currently applied *K*~0min~ value of the active DL
BWP in the scheduled cell and is zero, if *minimumSchedulingOffsetK0* is
not configured for the active DL BWP in the scheduled cell, *Z~µ~* is
determined by the subcarrier spacing of the active DL BWP in the
scheduling cell in slot *n*, and given in Table 5.3.1-1, and *µ*~PDCCH~
and *µ*~PDSCH~ are the sub-carrier spacing configurations for PDCCH of
the active DL BWP in the scheduling cell and PDSCH of the active DL BWP
in the scheduled cell, respectively, in slot *n*. After indication of a
change to the applied *K*~0min~ or *K*~2min~ of the scheduled cell in
slot *n* of the scheduling cell, if there is an active DL BWP change in
the scheduling cell before slot *n+X*, the new *K*~0min~ and/or
*K*~2min~ values are applied from the first slot no earlier than the
start of slot *n+X* based on the sub-carrier spacing configuration of
the active DL BWP in the scheduling cell in slot *n*.

When the DCI format 0_1, 0_3, 1_1 or 1_3 with \'*Minimum applicable
scheduling offset indicator*\' field is received outside the first three
symbols of the slot, value of *Z~µ~* from Table 5.3.1-1 is incremented
by one before determining the application delay *X*. When the PDCCH
reception includes two PDCCH candidates from two respective search space
sets, as described in clause 10.1 of \[6, TS 38.213\], for the purpose
of determining \'*Minimum applicable scheduling offset indicator*\'
field is received outside the first three symbols of the slot, the PDCCH
candidate that ends later in time is used.

Table 5.3.1-1: Definition of *Z~µ~*

  -----------------------------------------------------------------------
  *µ*                                 *Z~µ~*
  ----------------------------------- -----------------------------------
  0                                   1

  1                                   1

  2                                   2

  3                                   2

  5                                   8

  6                                   16
  -----------------------------------------------------------------------