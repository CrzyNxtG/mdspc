## 16.6 UE procedure for LTE sidelink transmission

If the UE detects a DCI format 3_1 with CRC scrambled by SL
Semi-Persistent Scheduling V-RNTI in slot $n$, the DCI format 3_1
activates or releases an LTE sidelink SPS configuration that is
indicated by a SL SPS configuration index field \[5, TS 38.212\]. If the
DCI format 3_1 activates an SL SPS configuration, the UE procedure for
transmitting a PSCCH and a PSSCH is as described in \[13, TS 36.213\]
except that a transmission starts no earlier than
$T_{DCI} - \frac{N_{TA}}{2} \times T_{C} \times 10^{3} + X + (4 + m)$
ms, where $T_{DCI}$ is a start time of slot $n$, $N_{TA}$ and $T_{C}$
are defined in \[4, TS 38.211\], $X$ is a value indicated by a Timing
offset field in DCI format 3_1, and $m$ is a value indicated by SL index
field in DCI format 3_1 if the SL index field is present; otherwise,
$m = 0$.