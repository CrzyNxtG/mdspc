### 5.16.1 Transmit operation

For UM DRBs and AM DRBs configured by upper layers to send a PDCP SN gap
report in the uplink (*sn-GapReport* in TS 38.331 \[3\]), the
transmitting PDCP entity shall trigger a PDCP SN gap report when:

\- PDCP SDU(s) are discarded as specified in clause 5.3; and

\- there is at least one stored PDCP SDU(s) which is associated with a
COUNT value larger than the COUNT value associated to the discarded PDCP
SDU(s); and

\- the discarded PDCP SDU(s) have not been submitted by any RLC entity
to lower layers.

If a PDCP SN gap report is triggered for these discarded PDCP SDU(s),
the transmitting PDCP entity shall:

\- compile a PDCP SN gap report as indicated below by:

\- setting the FDC field to the smallest COUNT value among the COUNT
values associated with these discarded PDCP SDU(s);

\- if more than one PDCP SDU is discarded:

\- allocating a Discard Bitmap field of length in bits equal to the
number of COUNT values from and not including the first of these
discarded PDCP SDU(s) up to and including the last of these discarded
PDCP SDU(s), rounded up to the next multiple of 8, or up to and
including a PDCP SDU for which the resulting PDCP Control PDU size is
equal to 9000 bytes, whichever comes first;

\- setting in the discard bitmap field as \'1\' for these discarded PDCP
SDU(s);

\- setting in the discard bitmap field as \'0\' for all other PDCP
SDU(s).

\- submit the PDCP SN gap report to lower layers as specified in clause
5.2.1 for Uu interface.

NOTE: It is up to UE implementation how to limit the frequency of PDCP
SN gap reporting.