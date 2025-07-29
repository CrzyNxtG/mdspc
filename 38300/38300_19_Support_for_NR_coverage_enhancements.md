# 19 Support for NR coverage enhancements

To improve NR uplink coverage for both FR1 and FR2, the following
enhancements on PUSCH, PUCCH, PRACH and MSG3 PUSCH are supported:

\- Enhanced aggregation of multiple slots with TB repetition is
supported for both PUSCH transmission with dynamic and configured grant.
In addition, counting based on available slots is supported. The maximum
number of aggregated slots for counting based on available slots and
counting based on physical slots are both 32.

\- TB processing over multiple slots with and without repetition is
supported for both PUSCH transmission with dynamic grant and configured
grant. For a single transmission of TB processing over multiple slots
PUSCH, the TB size is determined based on multiple slots.

\- DMRS bundling where the UE maintains phase continuity and power
consistency across PUSCH transmissions or PUCCH repetitions to enable
improved channel estimation is supported. Inter-slot frequency hopping
with DMRS bundling is supported.

\- Dynamic PUCCH repetition factor indication configured per PUCCH
resource is introduced, applicable to all PUCCH formats.

\- Aggregation of multiple slots with TB repetition for MSG3
transmission is supported on both NUL and SUL, applicable to CBRA with
4-step RA type. If configured, the UE requests MSG3 repetition via
separate RACH resources when the RSRP of DL path-loss reference is lower
than a configured threshold. BWP configured with RACH resources solely
for MSG3 repetition is also supported without the need to consider the
RSRP of DL path-loss reference by the UE.

\- MSG1 repetition with same beam is supported on both NUL and SUL for
4-step RA type. For CBRA, network broadcasts separate RSRP thresholds
for different repetition numbers. UE performs MSG1 repetition via RACH
resources that are different from RACH resources without MSG1
repetition. CFRA for MSG1 repetition for *ReconfigurationWithSync* is
supported and the network signals the MSG1 repetition number explicitly.
Fallback from lower number to higher number of MSG1 repetition is
supported among the set(s) of RACH resources associated with same
feature(s). Fallback from lower number to higher number of MSG1
repetition is not supported for MSG1-based SI request or if UE has
performed fallback from CFRA to CBRA. Fallback from CFRA with MSG1
repetition to 4-step CBRA with MSG1 repetition using the same MSG1
repetition number as the one used for CFRA is supported.

\- Dynamic switching between DFT-S-OFDM and CP-OFDM for PUSCH is
supported. The indication for switching between DFT-S-OFDM and CP-OFDM
for PUSCH is contained in DCI format 0_1/0_2, which is configured
separately for each BWP. PHR can be reported for current transmission of
PUSCH using one of the DFT-S-OFDM or CP-OFDM waveform and an assumed
transmission of PUSCH using the other waveform than the current one.

\- Frequency domain spectrum shaping without frequency extension is
supported for MPR/PAR reduction on the PUSCH transmission, and the
change value of UE power class is reported in the PHR.