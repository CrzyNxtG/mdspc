### 4.4.5 Bandwidth part

A bandwidth part is a subset of contiguous common resource blocks
defined in clause 4.4.4.3 for a given numerology ![](media/image48.wmf)
in bandwidth part ![](media/image17.wmf) on a given carrier. The
starting position $N_{\text{BWP},i}^{\text{start,}\mu}$ and the number
of resource blocks $N_{\text{BWP},i}^{\text{size,}\mu}$ in a bandwidth
part shall fulfil
$N_{\text{grid},x}^{\text{start},\mu} \leq N_{\text{BWP},i}^{\text{start},\mu} < N_{\text{grid},x}^{\text{start},\mu} + N_{\text{grid},x}^{\text{size},\mu}$
and
$N_{\text{grid},x}^{\text{start},\mu} < N_{\text{BWP},i}^{\text{start},\mu} + N_{\text{BWP},i}^{\text{size},\mu} \leq N_{\text{grid},x}^{\text{start},\mu} + N_{\text{grid},x}^{\text{size},\mu}$,
respectively. Configuration of a bandwidth part is described in clause
12 of \[5, TS 38.213\].

A UE can be configured with up to four bandwidth parts in the downlink
with a single downlink bandwidth part being active at a given time. The
UE is not expected to receive PDSCH, PDCCH, or CSI-RS (except for RRM)
outside an active bandwidth part.

A UE can be configured with up to four bandwidth parts in the uplink
with a single uplink bandwidth part being active at a given time. If a
UE is configured with a supplementary uplink, the UE can in addition be
configured with up to four bandwidth parts in the supplementary uplink
with a single supplementary uplink bandwidth part being active at a
given time. The UE shall not transmit PUSCH or PUCCH outside an active
bandwidth part. For an active cell, the UE shall not transmit SRS
configured by *SRS-Resource* outside an active bandwidth part.

Unless otherwise noted, the description in this specification applies to
each of the bandwidth parts. When there is no risk of confusion, the
index $\mu$ may be dropped from $N_{\text{BWP},i}^{\text{start},\mu}$,
$N_{\text{BWP},i}^{\text{size},\mu}$,
$N_{\text{grid},x}^{\text{start},\mu}$, and
$N_{\text{grid},x}^{\text{size},\mu}$.