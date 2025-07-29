### 8.2.5 Resource grid

The resource grid for sidelink transmission is defined in clause 4.4.2.

For sidelink, the carrier bandwidth $N_{\text{grid}}^{\text{size},\mu}$
and the starting position $N_{\text{grid}}^{\text{start},\mu}$ for
subcarrier spacing configuration $\mu$ are obtained from the
higher-layer parameter *sl-SCS-SpecificCarrierList*.

For the sidelink, the higher-layer parameter
*sl-TxDirectCurrentLocation* indicates the location of the transmitter
DC subcarrier in the sidelink for each of the configured bandwidth
parts. Values in the range 0 -- 3299 represent the number of the DC
subcarrier, the value 3300 indicates that the DC subcarrier is located
outside the resource grid, and the value 3301 indicates that the
position of the DC subcarrier in the sidelink is undetermined. The DC
subcarrier location offset relative to the center of the indicated
subcarrier is given by $7.5 + 5N\ \text{kHz}$ if
*frequencyShift7p5khzSL* is provided and by $5N\ \text{kHz}$ otherwise,
where $N \in \left\{ - 1,0,1 \right\}$ is given by the higher-layer
parameter *valueN*.