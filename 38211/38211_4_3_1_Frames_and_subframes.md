### 4.3.1 Frames and subframes

Downlink, uplink, and sidelink transmissions are organized into frames
with ![](media/image34.wmf) duration, each consisting of ten subframes
of ![](media/image35.wmf) duration. The number of consecutive OFDM
symbols per subframe is
$N_{\text{symb}}^{\text{subframe},\mu} = N_{\text{symb}}^{\text{slot}}N_{\text{slot}}^{\text{subframe},\mu}$.
Each frame is divided into two equally-sized half-frames of five
subframes each with half-frame 0 consisting of subframes 0 -- 4 and
half-frame 1 consisting of subframes 5 -- 9.

There is one set of frames in the uplink and one set of frames in the
downlink on a carrier.

Uplink frame number ![](media/image36.wmf) for transmission from the UE
shall start
$T_{\text{TA}} = \left( N_{\text{TA}} + N_{\text{TA,offset}} + N_{\text{TA,adj}}^{\text{common}} + N_{\text{TA,adj}}^{\text{UE}} \right)T_{\text{c}}$
before the start of the corresponding downlink frame at the UE where

\- $N_{\text{TA}}$ and $N_{\text{TA,offset}}$ are given by clause 4.2 of
\[5, TS 38.213\], except for msgA transmission on PUSCH where
$N_{\text{TA}} = 0$ shall be used;

\- $N_{\text{TA,adj}}^{\text{common}}$ given by clause 4.2 of \[5, TS
38.213\] is derived from the higher-layer parameters *ta-Common*,
*ta-CommonDrift*, and *ta-CommonDriftVariant* if configured, otherwise
$N_{\text{TA,adj}}^{\text{common}} = 0$;

\- $N_{\text{TA,adj}}^{\text{UE}}$ given by clause 4.2 of \[5, TS
38.213\] is computed by the UE based on UE position and
serving-satellite-ephemeris-related higher-layers parameters if
configured, or is computed by the UE based on UE position and gNB
location provided by *atg-gNB-Location* if configured, otherwise
$N_{\text{TA,adj}}^{\text{UE}} = 0$.

![](media/image37.emf)

Figure 4.3.1-1: Uplink-downlink timing relation.