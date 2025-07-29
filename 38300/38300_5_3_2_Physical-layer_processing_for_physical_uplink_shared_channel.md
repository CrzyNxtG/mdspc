### 5.3.2 Physical-layer processing for physical uplink shared channel

The uplink physical-layer processing of transport channels consists of
the following steps:

\- Transport Block CRC attachment;

\- Code block segmentation and Code Block CRC attachment;

\- Channel coding: LDPC coding;

\- Physical-layer hybrid-ARQ processing;

\- Rate matching;

\- Scrambling;

\- Modulation: π/2 BPSK (with transform precoding only), QPSK, 16QAM,
64QAM and 256QAM;

\- Layer mapping, transform precoding (enabled/disabled by
configuration), and pre-coding;

\- Mapping to assigned resources and antenna ports.

The UE transmits at least one symbol with demodulation reference signal
on each layer on each frequency hop in which the PUSCH is transmitted,
and up to 3 additional DMRS can be configured by higher layers.

Phase Tracking RS may be transmitted on additional symbols to aid
receiver phase tracking.

The UL-SCH physical layer model is described in TS 38.202 \[20\].

For configured grants operation with shared spectrum channel access,
described in clause 10.3, a CG-UCI (Configured Grant Uplink Control
Information) can be transmitted in PUSCH scheduled by configured uplink
grant.