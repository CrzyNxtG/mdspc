## 4.5 Carrier aggregation

Transmissions in multiple cells can be aggregated. Unless otherwise
noted, the description in this specification applies to each of the
serving cells.

For carrier aggregation of cells with unaligned frame boundaries, the
slot offset $N_{\text{slot, offset}}^{\text{CA}}$ between a PCell/PScell
and an SCell is determined by higher-layer parameter *ca-SlotOffset* for
the SCell. The quantity $\mu_{\text{offset}}$ is defined as the maximum
of the lowest subcarrier spacing configuration among the subcarrier
spacings given by the higher-layer parameters *scs-SpecificCarrierList*
configured for PCell/PSCell and the SCell, respectively. The slot offset
$N_{\text{slot, offset}}^{\text{CA}}$ fulfills

\- when the lowest subcarrier spacing configuration among the subcarrier
spacings configured for the cell is $\mu = 2$ for both cells or
$\mu = 3$ for both cells, the start of slot 0 for the cell whose point A
has a lower frequency coincides with the start of slot
${qN}_{\text{slot, offset}}^{\text{CA}}\text{ mod }N_{\text{slot}}^{\text{frame},\mathbf{\mu}_{\text{offset}}}$
for the other cell where $q = - 1$ if point A of the PCell/PSCell has a
frequency lower than the frequency of point A for the SCell, otherwise
$q = 1$;

\- otherwise, the start of slot 0 for the cell with the lower subcarrier
spacing of the lowest subcarrier spacing given by the higher-layer
parameters *scs-SpecificCarrierList* configured for the two cells, or
the Pcell/PSCell if both cells have the same lowest subcarrier spacing
given by the higher-layer parameters *scs-SpecificCarrierList*
configured for the two cells, coincides with the start of slot
${qN}_{\text{slot, offset}}^{\text{CA}}\text{ mod }N_{\text{slot}}^{\text{frame},\mathbf{\mu}_{\text{offset}}}$
for the other cell where $q = - 1$ if the lowest subcarreier spacing
configuration given by *scs-SpecificCarrierList* of the PCell/PSCell is
smaller than or equal to the lowest subcarrier spacing given by
*scs-SpecificCarrierList* for the SCell, otherwise $q = 1$.