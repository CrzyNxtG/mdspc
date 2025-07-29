### 6.2.2 UE DM-RS transmission procedure

The DM-RS transmission procedures for PUSCH scheduled by PDCCH with DCI
format 0_1 described in this clause equally apply to PUSCH scheduled by
PDCCH with DCI format 0_2, by applying the parameters of
*dmrs-UplinkForPUSCH-MappingTypeA-DCI-0-2* and
*dmrs-UplinkForPUSCH-MappingTypeB-DCI-0-2* instead of
*dmrs-UplinkForPUSCH-MappingTypeA* and
*dmrs-UplinkForPUSCH-MappingTypeB*. The DM-RS transmission procedures
for PUSCH scheduled by PDCCH with DCI format 0_1 described in this
clause equally apply to PUSCH scheduled by PDCCH with DCI format 0_3.

When transmitted PUSCH is neither scheduled by DCI format 0_1/0_2 with
CRC scrambled by C-RNTI, CS-RNTI, SP-CSI-RNTI or MCS-C-RNTI, nor
corresponding to a configured grant, nor being a PUSCH for Type-2 random
access procedure, the UE shall use single symbol front-loaded DM-RS of
configuration type 1 on DM-RS port 0 and the remaining REs not used for
DM-RS in the symbols are not used for any PUSCH transmission except for
PUSCH with allocation duration of 2 or less OFDM symbols with transform
precoding disabled, additional DM-RS can be transmitted according to the
scheduling type and the PUSCH duration as specified in Table 6.4.1.1.3-3
of \[4, TS 38.211\] for frequency hopping disabled and as specified in
Table 6.4.1.1.3-6 of \[4, TS 38.211\] for frequency hopping enabled, and

If frequency hopping is disabled:

\- The UE shall assume *dmrs-AdditionalPosition* equals to \'pos2\' and
up to two additional DM-RS can be transmitted according to PUSCH
duration, or

If frequency hopping is enabled:

\- The UE shall assume *dmrs-AdditionalPosition* equals to \'pos1\' and
up to one additional DM-RS can be transmitted according to PUSCH
duration.

When transmitted PUSCH is scheduled by activation DCI format 0_0 with
CRC scrambled by CS-RNTI, the UE shall use single symbol front-loaded
DM-RS of configuration type provided by higher layer parameter
*dmrs-Type* in *DMRS-UplinkConfig* on DM-RS port 0 and the remaining REs
not used for DM-RS in the symbols are not used for any PUSCH
transmission except for PUSCH with allocation duration of 2 or less OFDM
symbols with transform precoding disabled, and additional DM-RS with
*dmrs-AdditionalPosition* from C*onfiguredGrantConfig* can be
transmitted according to the scheduling type and the PUSCH duration as
specified in Table 6.4.1.1.3-3 of \[4, TS 38.211\] for frequency hopping
disabled and as specified in Table 6.4.1.1.3-6 of \[4, TS 38.211\] for
frequency hopping enabled.

For the UE-specific reference signals generation as defined in Clause
6.4.1.1 of \[4, TS 38.211\], a UE can be configured by higher layers
with one or two scrambling identity(s), $n_{ID}^{DMRS,i}\ $*i* = 0,1
which are the same for both PUSCH mapping Type A and Type B.

When transmitted PUSCH is scheduled by DCI format 0_1 with CRC scrambled
by C-RNTI, CS-RNTI, SP-CSI-RNTI or MCS-C-RNTI, or corresponding to a
configured grant, or being a PUSCH for Type-2 random access procedure,

\- for a configured-grant based PUSCH transmission in RRC_INACTIVE
state, the UE is provided with a set of DM-RS port(s) by
*sdt-DMRS-Ports*. The DM-RS port for the PUSCH is determined by the
mapping between SS/PBCH block(s) and a PUSCH occasion and the associated
DM-RS resource as described in Clause 19.1 of \[6, TS 38.213\].

\- for a configured-grant based PUSCH transmission in NTN RACH-less
handover or in RACH-less LTM cell switch, the UE is provided with a set
of DM-RS port(s) by *rrc-DMRS-Ports*. The DM-RS port for the PUSCH is
determined by the mapping between SS/PBCH block(s) and a PUSCH occasion
and the associated DM-RS resource as described in Clause 22.1 or clause
21.1 of \[6, TS 38.213\], respectively.

\- the UE may be configured with higher layer parameter *dmrs-Type* in
*DMRS-UplinkConfig*, and the configured DM-RS configuration type is used
for transmitting PUSCH in as defined in Clause 6.4.1.1 of \[4, TS
38.211\].

\- the UE may be configured with the maximum number of front-loaded
DM-RS symbols for PUSCH by higher layer parameter *maxLength* in
*DMRS-UplinkConfig,* or by higher layer parameter *msgA-MaxLength* in
*msgA-DMRS-Config*,

\- if *maxLength* is not configured, single-symbol DM-RS can be
scheduled for the UE by DCI or configured by the configured grant
configuration, and the UE can be configured with a number of additional
DM-RS for PUSCH by higher layer parameter *dmrs-AdditionalPosition,*
which can be \'pos0\', \'pos1\', \'pos2\', \'pos3\'.

\- if *maxLength* is configured, either single-symbol DM-RS or double
symbol DM-RS can be scheduled for the UE by DCI or configured by the
configured grant configuration, and the UE can be configured with a
number of additional DM-RS for PUSCH by higher layer parameter
*dmrs-AdditionalPosition,* which can be \'pos0\' or \'pos1\'.

\- for MsgA PUSCH for Type-2 random access procedure the UE can be
configured with a number of additional DM-RS for PUSCH by higher layer
parameter *msgA-DMRS-AdditionalPosition,* which can be \'pos0\',
\'pos1\', \'pos2\', \'pos3\' for single-symbol DM-RS or \'pos0\',
\'pos1\' for double-symbol DM-RS.

\- and, the UE shall transmit a number of additional DM-RS as specified
in Table 6.4.1.1.3-3 and Table 6.4.1.1.3-4 in -Clause 6.4.1.1.3 of \[4,
TS 38.211\].

If a UE transmitting PUSCH scheduled by DCI format 0_2 is configured
with the higher layer parameter *phaseTrackingRS* in
*dmrs-UplinkForPUSCH-MappingTypeA-DCI-0-2* or
*dmrs-UplinkForPUSCH-MappingTypeB-DCI-0-2*, or a UE transmitting PUSCH
scheduled by DCI format 0_0, 0_1 or 0_3 is configured with the higher
layer parameter *phaseTrackingRS* in *dmrs-UplinkForPUSCH-MappingTypeA*
or *dmrs-UplinkForPUSCH-MappingTypeB*, the UE may assume that the
following configurations are not occurring simultaneously for the
transmitted PUSCH

\- any DM-RS ports among

4-7 or 6-11 for DM-RS configurations type 1 and type 2, respectively, or

4-7 or 12-15 for DM-RS configuration enhanced type 1, or

6-11 or 18-23 for DM-RS configuration enhanced type 2,

are scheduled for the UE and PT-RS is transmitted from the UE.

For PUSCH scheduled by DCI format 0_1, by activation DCI format 0_1 with
CRC scrambled by CS-RNTI, or configured by configured grant Type 1
configuration, the UE shall assume the DM-RS CDM groups indicated in
Tables 7.3.1.1.2-6 to 7.3.1.1.2-23D and Tables 7.3.1.1.2-38 to
7.3.1.1.2-69 of Clause 7.3.1.1 of \[5, TS 38.212\] are not used for data
transmission, where \"1\", \"2\" and \"3\" for the number of DM-RS CDM
group(s) correspond to CDM group 0, {0,1}, {0,1,2}, respectively.

For PUSCH scheduled by DCI format 0_0 or by activation DCI format 0_0
with CRC scrambled by CS-RNTI, the UE shall assume the number of DM-RS
CDM groups without data is 1 which corresponds to CDM group 0 for the
case of PUSCH with allocation duration of 2 or less OFDM symbols with
transform precoding disabled, the UE shall assume that the number of
DM-RS CDM groups without data is 3 which corresponds to CDM group
{0,1,2} for the case of PUSCH scheduled by activation DCI format 0_0 and
the *dmrs-Type* in *DMRS-UplinkConfig* equal to \'type2\' and the PUSCH
allocation duration being more than 2 OFDM symbols, and the UE shall
assume that the number of DM-RS CDM groups without data is 2 which
corresponds to CDM group {0,1} for all other cases.

For MsgA PUSCH transmission, if the UE is not configured with
*msgA-PUSCH-DMRS-CDM-group,* the UE shall assume that 2 DM-RS CDM groups
are configured. Otherwise, *msgA-PUSCH-DMRS-CDM-group* indicates which
DM-RS CDM group to use from the set of {0,1}.

For MsgA PUSCH transmission, if the UE is not configured with
*msgA-PUSCH-NrofPorts,* the UE shall assume that 4 ports are configured
per DM-RS CDM group for double-symbol DM-RS. Otherwise,
*msgA-PUSCH-NrofPorts* with value of 0 indicates the first port per
DM-RS CDM group, while a value of 1 indicates the first two ports per
DM-RS CDM group.

For uplink DM-RS with PUSCH, the UE may assume the ratio of PUSCH EPRE
to DM-RS EPRE (![](media/image3.wmf) \[dB\]) is given by Table 6.2.2-1
according to the number of DM-RS CDM groups without data. The DM-RS
scaling factor ![](media/image777.wmf) specified in clause 6.4.1.1.3 of
\[4, TS 38.211\] is given by ![](media/image778.wmf).

Table 6.2.2-1: The ratio of PUSCH EPRE to DM-RS EPRE

  -----------------------------------------------------------------------
  Number of DM-RS CDM  DM-RS configuration type 1 DM-RS configuration
  groups without data  and enhanced type 1        type 2 and enhanced
                                                  type 2
  -------------------- -------------------------- -----------------------
  1                    0 dB                       0 dB

  2                    -3 dB                      -3 dB

  3                    \-                         -4.77 dB
  -----------------------------------------------------------------------

For PUSCH repetition Type B, the DM-RS transmission procedure is applied
for each actual repetition separately based on the allocation duration
of the actual repetition. A UE is not expected to be indicated with an
antenna port configuration that is invalid for the allocated duration of
any actual repetition.