### 6.4.1 Services and Functions

The main services and functions of the PDCP sublayer include:

\- Transfer of data (user plane or control plane);

\- Maintenance of PDCP SNs;

\- Header compression and decompression using the ROHC protocol;

\- Header compression and decompression using EHC protocol;

\- Compression and decompression of uplink PDCP SDUs: DEFLATE based UDC
only;

\- Ciphering and deciphering;

\- Integrity protection and integrity verification;

\- Timer based SDU discard;

\- For split bearers, routing;

\- Duplication;

\- Reordering and in-order delivery;

\- Out-of-order delivery;

\- Duplicate discarding.

Since PDCP does not allow COUNT to wrap around in DL and UL, it is up to
the network to prevent it from happening (e.g. by using a release and
add of the corresponding radio bearer or a full configuration).