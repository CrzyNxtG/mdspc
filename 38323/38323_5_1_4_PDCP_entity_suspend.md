### 5.1.4 PDCP entity suspend

When upper layers request a PDCP entity suspend, the transmitting PDCP
entity shall:

\- set TX_NEXT to the initial value;

\- discard all stored PDCP PDUs;

When upper layers request a PDCP entity suspend, the receiving PDCP
entity shall:

\- if t-*Reordering* is running:

\- stop and reset *t-Reordering*;

\- deliver all stored PDCP SDUs to the upper layers in ascending order
of associated COUNT values after performing header decompression;

\- set RX_NEXT and RX_DELIV to the initial value, except for MRB.