### 5.2.2 Physical-layer processing for physical downlink shared channel

The downlink physical-layer processing of transport channels consists of
the following steps:

\- Transport block CRC attachment;

\- Code block segmentation and code block CRC attachment;

\- Channel coding: LDPC coding;

\- Physical-layer hybrid-ARQ processing;

\- Rate matching;

\- Scrambling;

\- Modulation: QPSK, 16QAM, 64QAM, 256QAM, and 1024QAM;

\- Layer mapping;

\- Mapping to assigned resources and antenna ports.

The UE may assume that at least one symbol with demodulation reference
signal is present on each layer in which PDSCH is transmitted to a UE,
and up to 3 additional DMRS can be configured by higher layers.

Phase Tracking RS may be transmitted on additional symbols to aid
receiver phase tracking.

The DL-SCH physical layer model is described in TS 38.202 \[20\].