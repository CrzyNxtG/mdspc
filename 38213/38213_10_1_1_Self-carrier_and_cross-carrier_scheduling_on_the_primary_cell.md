### 10.1.1 Self-carrier and cross-carrier scheduling on the primary cell

A UE can be configured for scheduling on the primary cell from the
primary cell and from a secondary cell \[12, TS 38.331\]. The UE is
either not provided *monitoringCapabilityConfig* for the primary cell or
for the secondary cell, or the UE is provided only
*monitoringCapabilityConfig* = *r15monitoringcapability* for the primary
cell and for the secondary cell. The UE is not provided
*coresetPoolIndex* on the primary cell or on the secondary cell.

The SCS configuration $\mu_{P}$ for the active DL BWP on the primary
cell is smaller than or equal to the SCS configuration $\mu_{S}$ for the
active DL BWP on the secondary cell.

If a UE indicates capability *disablingScalingFactorDeactSCell* \[18, TS
38.306\] and the secondary cell is deactivated, or if the UE indicates
capability *disablingScalingFactorDormantSCell* \[18, TS 38.306\] and
the active DL BWP of the secondary cell is a dormant DL BWP for the UE,
$\alpha = 1$ applies for the procedures described in the remaining of
this clause. If $\mu_{P} < \mu_{S}$, the UE determines
$M_{\text{PDCCH}}^{\text{total,slot,}\mu_{P}}$ and
$C_{\text{PDCCH}}^{\text{total,slot,}\mu_{P}}$, and determines
$M_{\text{PDCCH}}^{\text{total,slot,}\mu_{S}}$ and
$C_{\text{PDCCH}}^{\text{total,slot,}\mu_{S}}$, by including the primary
cell only in the $N_{\text{cells,0}}^{\text{DL,}\mu_{P}}$ downlink cells
in
$\sum_{j = 0}^{3}\left( N_{\text{cells,0}}^{\text{DL,}j} + \gamma \bullet N_{\text{cells,1}}^{\text{DL,}j} \right)$,
as described in clause 10.1. If $\mu_{P} = \mu_{S} = \mu$, the UE
determines $M_{\text{PDCCH}}^{\text{total,slot,}\mu}$ and
$C_{\text{PDCCH}}^{\text{total,slot,}\mu}$ by including the primary cell
once in the $N_{\text{cells,0}}^{\text{DL,}\mu}$ downlink cells in
$\sum_{j = 0}^{3}\left( N_{\text{cells,0}}^{\text{DL,}j} + \gamma \bullet N_{\text{cells,1}}^{\text{DL,}j} \right)$,
as described in clause 10.1.

For scheduling on the primary cell from the primary cell, the UE is not
required to monitor more than
$\left\lfloor \alpha \bullet \min\left( M_{\text{PDCCH}}^{\text{max,slot,}\mu_{P}},M_{\text{PDCCH}}^{\text{total,slot,}\mu_{P}} \right) \right\rfloor\ $
PDCCH candidates per slot or more than
$\left\lfloor \alpha \bullet \min\left( C_{\text{PDCCH}}^{\text{max,slot,}\mu_{P}},C_{\text{PDCCH}}^{\text{total,slot,}\mu_{P}} \right) \right\rfloor$
non-overlapping CCEs per slot on the active DL BWP of the primary cell,
where $\alpha$ is provided by *ccs-BlindDetectionSplit*.

For scheduling on the primary cell from the secondary cell, the UE is
not required to monitor on the active DL BWP of the secondary cell more
than

\- $M_{\text{PDCCH}}^{\text{max,slot,}\mu_{S}}$ PDCCH candidates per
slot or more than $C_{\text{PDCCH}}^{\text{max,slot,}\mu_{S}}$
non-overlapping CCEs per slot of the active DL BWP of the secondary cell

\-
$\min\left( M_{\text{PDCCH}}^{\text{max,slot,}\mu_{P}},M_{\text{PDCCH}}^{\text{total,slot,}\mu_{P}} \right) - \left\lfloor {\alpha \bullet \min}\left( M_{\text{PDCCH}}^{\text{max,slot,}\mu_{P}},M_{\text{PDCCH}}^{\text{total,slot,}\mu_{P}} \right) \right\rfloor$
PDCCH candidates per slot or more than
$\min{\left( C_{\text{PDCCH}}^{\text{max,slot,}\mu_{P}},C_{\text{PDCCH}}^{\text{total,slot,}\mu_{P}} \right) -}\left\lfloor {\alpha \bullet \min}\left( C_{\text{PDCCH}}^{\text{max,slot,}\mu_{P}},C_{\text{PDCCH}}^{\text{total,slot,}\mu_{P}} \right) \right\rfloor$
non-overlapping CCEs per slot of the active DL BWP of the primary cell

If $\mu_{P} < \mu_{S}$, the UE does not count PDCCH candidates and
non-overlapping CCEs that the UE monitors for scheduling on the primary
cell from the secondary cell towards
$M_{\text{PDCCH}}^{\text{total,slot,}\mu_{S}}$ and
$C_{\text{PDCCH}}^{\text{total,slot,}\mu_{S}}$, respectively.

If $\mu_{P} < \mu_{S}$, the UE counts PDCCH candidates and
non-overlapping CCEs that the UE monitors for scheduling on the primary
cell from the secondary cell towards
$M_{\text{PDCCH}}^{\text{total,slot,}\mu_{P}}$ and
$C_{\text{PDCCH}}^{\text{total,slot,}\mu_{P}}$, respectively.

For allocation of PDCCH candidates and non-overlapping CCEs to search
space sets for scheduling on the primary cell from the primary cell, the
UE applies the procedure in clause 10.1 using
$\left\lfloor \alpha \bullet \min\left( M_{\text{PDCCH}}^{\text{max,slot,}\mu},M_{\text{PDCCH}}^{\text{total,slot,}\mu} \right) \right\rfloor$
instead of
$\min\left( M_{\text{PDCCH}}^{\text{max,slot,}\mu},M_{\text{PDCCH}}^{\text{total,slot,}\mu} \right)$,
and using
$\left\lfloor \alpha \bullet \min\left( C_{\text{PDCCH}}^{\text{max,slot,}\mu},C_{\text{PDCCH}}^{\text{total,slot,}\mu} \right) \right\rfloor$
instead of
$\min\left( C_{\text{PDCCH}}^{\text{max,slot,}\mu},C_{\text{PDCCH}}^{\text{total,slot,}\mu} \right)$
for the primary cell.