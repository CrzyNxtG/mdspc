## 4.1 Power allocation for downlink

The gNB determines the downlink transmit EPRE.

For the purpose of SS-RSRP, SS-RSRQ and SS-SINR measurements, the UE may
assume downlink EPRE is constant across the bandwidth. For the purpose
of SS-RSRP, SS-RSRQ and SS-SINR measurements, the UE may assume downlink
EPRE is constant over SSS carried in different SS/PBCH blocks. For the
purpose of SS-RSRP, SS-RSRQ and SS-SINR measurements, the UE may assume
that the ratio of SSS EPRE to PBCH DM-RS EPRE is 0 dB.

For the purpose of CSI-RSRP, CSI-RSRQ and CSI-SINR measurements, the UE
may assume downlink EPRE of a port of CSI-RS resource configuration is
constant across the configured downlink bandwidth and constant across
all configured OFDM symbols.

The downlink SS/PBCH SSS EPRE can be derived from the SS/PBCH downlink
transmit power given by the parameter *ss-PBCH-BlockPower* provided by
higher layers. The downlink SSS transmit power is defined as the linear
average over the power contributions (in \[W\]) of all resource elements
that carry the SSS within the operating system bandwidth.

The downlink CSI-RS EPRE can be derived from the SS/PBCH block downlink
transmit power given by the parameter *ss-PBCH-BlockPower* and CSI-RS
power offset given by the parameter *powerControlOffsetSS* provided by
higher layers if the SS/PBCH block is associated with serving cell PCI,
or derived from *ss-PBCH-BlockPower-r17* in *SSB-MTC-AdditionalPCI-r17*
and *powerControlOffsetSS* provided by higher layers if the SS/PBCH
block is associated with additional PCI different from serving cell PCI,
where the CSI-RS is QCLed with the SS/PBCH block. The downlink
reference-signal transmit power is defined as the linear average over
the power contributions (in \[W\]) of the resource elements that carry
the configured CSI-RS within the operating system bandwidth.

For downlink DM-RS associated with PDSCH, the UE may assume the ratio of
PDSCH EPRE to DM-RS EPRE (![](media/image3.wmf) \[dB\]) is given by
Table 4.1-1 according to the number of DM-RS CDM groups without data as
described in Clause 5.1.6.2. The DM-RS scaling factor
![](media/image4.wmf) specified in Clause 7.4.1.1.2 of \[4, TS 38.211\]
is given by ![](media/image5.wmf).

Table 4.1-1: The ratio of PDSCH EPRE to DM-RS EPRE

  -----------------------------------------------------------------------
  Number of DM-RS CDM  DM-RS configuration type 1 DM-RS configuration
  groups without data  and enhanced type 1        type 2 and enhanced
                                                  type 2
  -------------------- -------------------------- -----------------------
  1                    0 dB                       0 dB

  2                    -3 dB                      -3 dB

  3                    \-                         -4.77 dB
  -----------------------------------------------------------------------

When the UE is scheduled with one or two PT-RS ports associated with the
PDSCH,

\- if the UE is configured with the higher layer parameter *epre-Ratio*,
the ratio of PT-RS EPRE to PDSCH EPRE per layer per RE for each PT-RS
port (![](media/image6.wmf)) is given by Table 4.1-2 or Table 4.1-2A
according to the *epre-Ratio*, the PT-RS scaling factor
![](media/image7.wmf)specified in clause 7.4.1.2.2 of \[4, TS 38.211\]
is given by![](media/image8.wmf).

\- otherwise, the UE shall assume *epre-Ratio* is set to state \'0\' in
Table 4.1-2 or Table 4.1-2A if not configured.

Table 4.1-2: PT-RS EPRE to PDSCH EPRE per layer per RE
(![](media/image9.wmf)), if *dmrs-TypeEnh* is not configured in
*DMRS-DownlinkConfig*

+--------------+-----------------------------------------------------------------------------------------+
| *epre-Ratio* | The number of PDSCH layers with DM-RS associated to the PT-RS port                      |
|              +--------------+--------------+--------------+--------------+--------------+--------------+
|              | 1            | 2            | 3            | 4            | 5            | 6            |
+==============+==============+==============+==============+==============+==============+==============+
| 0            | 0            | 3            | 4.77         | 6            | 7            | 7.78         |
+--------------+--------------+--------------+--------------+--------------+--------------+--------------+
| 1            | 0            | 0            | 0            | 0            | 0            | 0            |
+--------------+--------------+--------------+--------------+--------------+--------------+--------------+
| 2            | reserved                                                                                |
+--------------+-----------------------------------------------------------------------------------------+
| 3            | reserved                                                                                |
+--------------+-----------------------------------------------------------------------------------------+

Table 4.1-2A: PT-RS EPRE to PDSCH EPRE per layer per RE
(![](media/image9.wmf)), if *dmrs-TypeEnh* is configured in
*DMRS-DownlinkConfig*

+------------------+-----------------------------------------------------------------------------------------------------------------------+
| ***epre-Ratio*** | **The number of PDSCH layers with DM-RS associated to the PT-RS port**                                                |
|                  +--------------+--------------+--------------+--------------+--------------+--------------+--------------+--------------+
|                  | **1**        | **2**        | **3**        | **4**        | **5**        | **6**        | **7**        | **8**        |
+==================+:============:+:============:+:============:+:============:+:============:+:============:+:============:+:============:+
| 0                | 0            | 3            | 4.77         | 6            | 7            | 7.78         | 8.45         | 9            |
+------------------+--------------+--------------+--------------+--------------+--------------+--------------+--------------+--------------+
| 1                | 0            | 0            | 0            | 0            | 0            | 0            | 0            | 0            |
+------------------+--------------+--------------+--------------+--------------+--------------+--------------+--------------+--------------+
| 2                | > reserved                                                                                                            |
+------------------+-----------------------------------------------------------------------------------------------------------------------+
| 3                | > reserved                                                                                                            |
+------------------+-----------------------------------------------------------------------------------------------------------------------+

For link recovery, as described in clause 6 of \[6, TS 38.213\] the
ratio of the PDCCH EPRE to NZP CSI-RS EPRE is assumed as 0 dB.