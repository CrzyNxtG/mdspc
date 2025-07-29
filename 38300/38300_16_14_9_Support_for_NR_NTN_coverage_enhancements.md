### 16.14.9 Support for NR NTN coverage enhancements

To improve NR uplink coverage in NTN, the following enhancements are
supported:

\- PUCCH repetition for Msg4 HARQ-ACK configured in system information
or dynamically in DCI for Msg4 when multiple repetition factors are
configured in the system information:

\- UEs reports the capability of PUCCH repetition for Msg4 HARQ-ACK in
Msg3 PUSCH;

\- When Msg4 HARQ-ACK is repeated, PUCCH repetition is applied for all
PUCCH transmission before dedicated PUCCH resource is provided.

\- Improved channel estimation by NTN-specific PUSCH DMRS bundling
enhancement that enables DMRS bundling in presence of timing drift,
where the UE maintains phase continuity by considering effects of
transmission delay variation between the UE and the uplink time
synchronization reference point.