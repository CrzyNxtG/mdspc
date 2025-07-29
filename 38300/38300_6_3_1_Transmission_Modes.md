### 6.3.1 Transmission Modes

The RLC sublayer supports three transmission modes:

\- Transparent Mode (TM);

\- Unacknowledged Mode (UM);

\- Acknowledged Mode (AM).

The RLC configuration is per logical channel with no dependency on
numerologies and/or transmission durations, and ARQ can operate on any
of the numerologies and/or transmission durations the logical channel is
configured with.

For SRB0, paging and broadcast system information, TM mode is used. For
other SRBs AM mode used. For DRBs, either UM or AM mode are used.