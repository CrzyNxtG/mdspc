### 4.4.2 Resource grid

For each numerology and carrier, a resource grid of
![](media/image42.wmf) subcarriers and
$N_{\text{symb}}^{\text{subframe},\mu}$ OFDM symbols is defined,
starting at common resource block ![](media/image43.wmf) indicated by
higher-layer signalling. There is one set of resource grids per
transmission direction (uplink, downlink, or sidelink) with the
subscript$\ x$ set to DL, UL, and SL for downlink, uplink, and sidelink,
respectively. When there is no risk for confusion, the subscript $x$ may
be dropped. There is one resource grid for a given antenna port $p$,
subcarrier spacing configuration $\mu$, and transmission direction
(downlink, uplink, or sidelink).

For uplink and downlink, the carrier bandwidth
$N_{\text{grid}}^{\text{size},\mu}$ for subcarrier spacing configuration
$\mu$ is given by the higher-layer parameter *carrierBandwidth* in the
*SCS-SpecificCarrier* IE. The starting position
$N_{\text{grid}}^{\text{start},\mu}$ for subcarrier spacing
configuration $\mu$ is given by the higher-layer parameter
*offsetToCarrier* in the *SCS-SpecificCarrier* IE.

The frequency location of a subcarrier refers to the center frequency of
that subcarrier.

For the downlink, the higher-layer parameter *txDirectCurrentLocation*
in the *SCS-SpecificCarrier* IE indicates the location of the
transmitter DC subcarrier in the downlink for each of the numerologies
configured in the downlink. Values in the range 0 -- 3299 represent the
number of the DC subcarrier and the value 3300 indicates that the DC
subcarrier is located outside the resource grid.

For the uplink, the higher-layer parameter *txDirectCurrentLocation* in
the *UplinkTxDirectCurrentBWP* IE indicates the location of the
transmitter DC subcarrier in the uplink for each of the configured
bandwidth parts, including whether the DC subcarrier location is offset
by 7.5 kHz relative to the center of the indicated subcarrier or not.
Values in the range 0 -- 3299 represent the number of the DC subcarrier,
the value 3300 indicates that the DC subcarrier is located outside the
resource grid, and the value 3301 indicates that the position of the DC
subcarrier in the uplink is undetermined.