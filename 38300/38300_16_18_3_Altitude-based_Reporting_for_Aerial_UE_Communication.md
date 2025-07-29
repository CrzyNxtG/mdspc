### 16.18.3 Altitude-based Reporting for Aerial UE Communication

An Aerial UE can be configured with altitude-dependent, event-based
measurement reporting (i.e., *eventH1* and *eventH2* as defined in TS
38.331 \[12\]). An Aerial UE sends a measurement report when its
altitude becomes higher or lower than configured threshold. The UE
includes its altitude and location information in the measurement report
if configured to do so by NG-RAN.

The Aerial UE can also be configured to trigger measurement reporting
only when both an altitude-dependent condition and an
RSRP/RSRQ/SINR-based condition are met (i.e., *eventA3H1*, *eventA3H2*,
*eventA4H1*, *eventA4H2*, *eventA5H1* and *eventA5H2* in TS 38.331
\[12\], commonly denoted as *eventAxHy*). For the content of *eventAxHy*
measurement report, the same rules as described above for *eventH1* and
*eventH2* apply.