### 16.2.0 Support for IMS voice

For IMS voice support in NG-RAN, the following is assumed:

\- Network ability to support IMS voice sessions, i.e. ability to
support QoS flows with 5QI for voice and IMS signalling (see clause 12
and TS 23.501 \[3\]), or through EPC System fallback;

\- UE capability to support \"IMS voice over PS\", see TS 24.501 \[28\].

The capabilities indications check is handled at NAS layer. To maintain
the voice service in NG-RAN, the UE provides additional capabilities
over RRC (see TS 38.331 \[12\]), that are used to determine accurate NR
voice support options.

Further MMTEL IMS voice and video enhancements are facilitated by the
mechanisms described in the following clauses.