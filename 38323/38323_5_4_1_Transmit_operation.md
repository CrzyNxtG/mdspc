### 5.4.1 Transmit operation

For AM DRBs configured by upper layers to send a PDCP status report in
the uplink (*statusReportRequired* in TS 38.331 \[3\]), the receiving
PDCP entity shall trigger a PDCP status report when:

\- upper layer requests a PDCP entity re-establishment;

\- upper layer requests a PDCP data recovery;

\- upper layer requests a uplink data switching;

\- upper layer reconfigures the PDCP entity to release DAPS and
*daps-SourceRelease* is configured in TS 38.331 \[3\].

For UM DRBs configured by upper layers to send a PDCP status report in
the uplink (*statusReportRequired* in TS 38.331 \[3\]), the receiving
PDCP entity shall trigger a PDCP status report when:

\- upper layer requests a uplink data switching.

For AM DRBs in the sidelink, the receiving PDCP entity shall trigger a
PDCP status report when:

\- upper layer requests a PDCP entity re-establishment.

For AM MRBs configured by upper layers to send a PDCP status report in
the uplink (*statusReportRequired* in TS 38.331 \[3\]), the receiving
PDCP entity shall trigger a PDCP status report when:

\- upper layer requests a PDCP entity re-establishment;

\- upper layer requests a PDCP data recovery.

If a PDCP status report is triggered, the receiving PDCP entity shall:

\- compile a PDCP status report as indicated below by:

\- setting the FMC field to RX_DELIV;

\- if RX_DELIV \< RX_NEXT:

\- allocating a Bitmap field of length in bits equal to the number of
COUNTs from and not including the first missing PDCP SDU up to and
including the last out-of-sequence PDCP SDUs, rounded up to the next
multiple of 8, or up to and including a PDCP SDU for which the resulting
PDCP Control PDU size is equal to 9000 bytes, whichever comes first;

\- setting in the bitmap field as \'0\' for all PDCP SDUs that have not
been received, and optionally PDCP SDUs for which decompression have
failed;

\- setting in the bitmap field as \'1\' for all PDCP SDUs that have been
received;

\- submit the PDCP status report to lower layers as the first PDCP PDU
for transmission via the transmitting PDCP entity as specified in clause
5.2.1 for Uu interface and in clause 5.2.3 for PC5 interface.