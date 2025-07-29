### 16.18.5 Interference Detection and Mitigation for Aerial UE Communication

For interference detection, an Aerial UE can be configured with RRM
event A3, A4, A5 or AxHy that triggers measurement report when
individual (per cell) RSRP/RSRQ/SINR values (for events A3, A4, A5) or
RSRP/RSRQ/SINR and measured Aerial UE\'s altitude (for events AxHy) for
a configured number of cells fulfil the configured event. Once such
condition is met and a measurement report is sent, the list of triggered
cells is updated when subsequent cell(s) fulfil the event. However,
further measurement reports are not sent while the list of triggered
cells remains larger than or equal to the configured number of cells
unless *reportOnLeave* is configured (see TS 38.331 \[12\] for details).