# 7 UE procedures for transmitting and receiving on a carrier with intra-cell guard bands

For operation with shared spectrum channel access for FR1, when the UE
is configured with any of *IntraCellGuardBandsPerSCS* for UL carrier and
for DL carrier and *sl-IntraCellGuardBandsSL-List* for SL carrier with
SCS configuration $\mu$, the UE is provided with $\ N_{RB - set,x} - 1$
intra-cell guard bands on a carrier with $\mu$, each defined by start
CRB and size in number of CRBs, $GB_{\ s,x}^{start,\mu}\ $ and
$GB_{\ s,x}^{size,\mu}\ $, provided by higher layer parameters
*startCRB* and *nrofCRBs*, respectively, where
$s \in \left\{ 0,1,\ldots,N_{\text{RB-set},x} - 2 \right\}$. The
subscript *x* is set to DL, UL, or SL for the downlink, uplink, or
sidelink, respectively. Where there is no risk of confusion, the
subscript *x* can be dropped. The intra-cell guard bands separate
$N_{RB - set,x}\ $RB sets, each defined by start and end CRB,
$RB_{\ s,x}^{start,\mu}\ $and $RB_{\ s,x}^{end,\mu}$, respectively. The
UE does not expect that *nrofCRBs* is configured with non-zero value
smaller than the applicable intra-cell guard bands as specified in \[8,
TS 38.101-1\] corresponding to $\mu$ and carrier size
$N_{\text{grid,x}}^{\text{size},\mu}$. The UE determines the start and
end CRB indices for
$s \in \left\{ 0,1,\ldots,N_{\text{RB-set},x} - 1 \right\}$ as

${RB}_{\ s,x}^{\text{start,}\mu} = N_{\text{grid,}x}^{\text{start},\mu} + \left\{ \begin{matrix}
0 & s = 0 \\
GB_{\ s - 1,x}^{\text{start},\mu} + GB_{\ s - 1,x}^{\text{size},\mu} & \text{otherwise}
\end{matrix} \right.\ $

and

${RB}_{\ s,x}^{\text{end,}\mu} = N_{\text{grid},x}^{\text{start},\mu} + \left\{ \begin{matrix}
N_{\text{grid},x}^{\text{size},\mu} - 1 & s = N_{\text{RB-set},x} - 1 \\
GB_{\ s,x}^{\text{start},\mu} - 1 & \text{otherwise}
\end{matrix} \right.\ $

The RB set with index $s$ consists of $RB_{s,x}^{size,\mu}$ resource
blocks where
$\ RB_{s,x}^{size,\mu} = RB_{\ s,x}^{end,\mu} - RB_{\ s,x}^{start,\mu} + 1$.
When the UE is not configured with *IntraCellGuardBandsPerSCS* for UL
carrier and for DL carrier with SCS configuration $\mu$, or is not
configured with *sl-IntraCellGuardBandsSL-List* for SL carrier with SCS
configuration $\mu$, the UE determines the CRB indices for the
intra-cell guard band(s), if any, and corresponding RB set(s) according
to the nominal intra-cell guard band and RB set pattern as specified in
\[8, TS 38.101-1\] corresponding to $\mu$ and carrier size
$N_{\text{grid,}x}^{\text{size},\mu}$. For any one or more of DL, UL,
SL, if the nominal intra-cell guard band and RB set pattern as specified
in \[8, TS 38.101-1\] contains no intra-cell guard bands, the number of
RB sets for the carrier is $N_{RB\text{-}set,x} = 1$.

For a carrier with $\mu$, the UE expects
$\ \ N_{\ \text{BWP},i}^{start,\mu} = {RB}_{\ s0,x}^{start,\mu}$ and
$N_{\ \text{BWP},i}^{size,\mu} = {RB}_{\ s1,x}^{end,\mu} - {RB}_{\ s0,x}^{start,\mu} + 1\ $
where $0 \leq s0 \leq s1 \leq N_{RB\text{-}set,x} - 1$ for a BWP *i*
configured by *initialDownlinkBWP* or *BWP-Downlink* for the DL BWP, or
*initialUplinkBWP* or *BWP-Uplink* for the UL BWP, or configured by
*SL-BWP-Config* for the SL BWP. Within the BWP *i*, RB sets are numbered
in increasing order from 0 to $N_{RB\text{-}set,x}^{\text{BWP}} - 1\ $
where $N_{RB\text{-}set,x}^{\text{BWP}}\ $ is the number of RB sets
contained in the BWP *i* and RB set 0 within the BWP *i* corresponds to
RB set $s0$ in the carrier and RB set
$N_{RB\text{-}set,x}^{\text{BWP}} - 1$ within the BWP *i* corresponds to
RB set $s1$ in the carrier.

When a UE is provided with *nrofCRBs =* 0 for all intra-cell guard
band(s) on a carrier with $\mu$, the UE is indicated that no intra-cell
guard-bands are configured for the carrier and expects
$N_{RB - set,x} > 1$. For $\mu = 0$, the UE expects the number of RBs
within a RB set is between 100 and 110. For $\mu = 1$, the UE expects
the number of RBs within a RB set is between 50 and 55 except for at
most one RB set which may contain 56 RBs.