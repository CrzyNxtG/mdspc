### 16.18.8 BRID and DAA Support via A2X Communication

The Aerial UE supports A2X communication, as defined in 3.2. BRID relies
on broadcasting while DAA can be provided either via unicast or
broadcast transmissions in NR sidelink. BRID and DAA message
transmission is supported in both in-coverage and out-of-coverage
scenarios and relies on UE autonomous resource selection for NR sidelink
communication.

BRID and DAA follow the QoS framework defined for NR sidelink and
dedicated A2X PQI values are specified in table 6.2.4.1-1 of TS 23.256
\[60\]. The NG-RAN can configure separate SL Tx resource pool(s) for
BRID and/or DAA. The procedure for SL Tx pool selection for A2X is
described in TS 38.321 \[6\], clause 5.22.