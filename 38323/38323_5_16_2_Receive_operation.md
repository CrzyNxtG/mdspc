### 5.16.2 Receive operation

At reception of a PDCP SN gap report from lower layers, the receiving
PDCP entity shall:

\- consider each PDCP SDU, if any, with the bit in the discard bitmap
set to \'1\', or with the associated COUNT value equal to the value of
FDC field as discarded;

\- if RX_DELIV is less than or equal to the largest COUNT value
associated with the discarded PDCP SDUs:

\- if RX_NEXT \<= COUNT value associated with the last discarded PDCP
SDU indicated in the PDCP SN gap report:

\- update RX_NEXT to the largest COUNT value associated with the
discarded PDCP SDU + 1;

\- if RX_DELIV is equal to any COUNT value associated with the discarded
PDCP SDU(s):

\- deliver to upper layers in ascending order of the associated COUNT
value after performing header decompression, if not decompressed before:

\- all stored PDCP SDU(s) with consecutively associated COUNT values
starting from COUNT = RX_DELIV + 1, where consecutively associated COUNT
value(s) include COUNT value(s) of both the stored PDCP SDU(s) and PDCP
SDU(s) which are considered as discarded;

\- update RX_DELIV to the COUNT value of the first PDCP SDU which has
not been delivered to upper layers and is not considered as discarded,
with COUNT value \> RX_DELIV;

\- if *t-Reordering* is running, and if RX_DELIV \>= RX_REORD:

\- stop and reset *t-Reordering*;

\- if *t-Reordering* is not running (includes the case when
*t-Reordering* is stopped due to actions above), and RX_DELIV \<
RX_NEXT:

\- update RX_REORD to RX_NEXT;

\- start *t-Reordering*.