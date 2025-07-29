### 5.1.2 PDCP entity re-establishment

When upper layers request a PDCP entity re-establishment, the UE shall
additionally perform once the procedures described in this clause for Uu
or PC5 interface. After performing the procedures in this clause, the UE
shall follow the procedures in clause 5.2.

When upper layers request a PDCP entity re-establishment, the
transmitting PDCP entity shall:

\- for UM DRBs and AM DRBs, reset the ROHC protocol for uplink and start
with an IR state in U-mode (as defined in RFC 3095 \[8\] and RFC 4815
\[9\]) if *drb-ContinueROHC* is not configured in TS 38.331 \[3\];

\- for UM DRBs and AM DRBs, reset the EHC protocol for uplink if
*drb-ContinueEHC-UL* is not configured in TS 38.331 \[3\];

\- for AM DRBs, reset the UDC compression buffer to all zeros and
prefill the dictionary if *drb-ContinueUDC* is not configured in TS
38.331 \[3\];

\- for SRBs and UM DRBs, set TX_NEXT to the initial value;

\- for SRBs, discard all stored PDCP SDUs and PDCP PDUs;

\- apply the ciphering algorithm and key provided by upper layers during
the PDCP entity re-establishment procedure;

\- apply the integrity protection algorithm and key provided by upper
layers during the PDCP entity re-establishment procedure;

\- for UM DRBs, for each PDCP SDU already associated with a PDCP SN but
for which a corresponding PDU has not previously been submitted to lower
layers, and;

\- for AM DRBs for Uu interface whose PDCP entities were suspended, from
the first PDCP SDU for which the successful delivery of the
corresponding PDCP Data PDU has not been confirmed by lower layers, for
each PDCP SDU already associated with a PDCP SN:

\- consider the PDCP SDUs as received from upper layer;

\- perform transmission of the PDCP SDUs in ascending order of the COUNT
value associated to the PDCP SDU prior to the PDCP re-establishment
without restarting the *discardTimer* or the
*discardTimerForLowImportance*, as specified in clause 5.2.1;

\- for AM DRBs whose PDCP entities were not suspended, from the first
PDCP SDU for which the successful delivery of the corresponding PDCP
Data PDU has not been confirmed by lower layers, perform retransmission
or transmission of all the PDCP SDUs already associated with PDCP SNs in
ascending order of the COUNT values associated to the PDCP SDU prior to
the PDCP entity re-establishment as specified below:

\- perform header compression of the PDCP SDU using ROHC as specified in
the clause 5.7.4 and/or using EHC as specified in the clause 5.12.4;

\- If *drb-ContinueUDC* is configured and if the PDCP SDU has been
compressed before:

\- submit the PDCP SDU previously compressed to integrity protection and
ciphering function;

\- else:

\- perform uplink data compression of the PDCP SDU as specified in
clause 5.14.4, and submit the PDCP SDU to integrity protection and
ciphering function;

\- perform integrity protection and ciphering of the PDCP SDU using the
COUNT value associated with this PDCP SDU as specified in the clause 5.9
and 5.8;

\- submit the resulting PDCP Data PDU to lower layer, as specified in
clause 5.2.1.

When upper layers request a PDCP entity re-establishment, the receiving
PDCP entity shall:

\- process the PDCP Data PDUs that are received from lower layers due to
the re-establishment of the lower layers, as specified in the clause
5.2.2.1;

\- for SRBs, discard all stored PDCP SDUs and PDCP PDUs;

\- for SRBs, UM DRBs and UM MRBs, if *t-Reordering* is running:

\- stop and reset *t-Reordering*;

\- for UM DRBs and UM MRBs, deliver all stored PDCP SDUs to the upper
layers in ascending order of associated COUNT values after performing
header decompression;

\- for AM DRBs and AM MRBs for Uu interface, perform header
decompression using ROHC for all stored PDCP SDUs if *drb-ContinueROHC*
is not configured in TS 38.331 \[3\];

\- for AM DRBs for PC5 interface, perform header decompression using
ROHC for all stored PDCP IP SDUs;

\- for AM DRBs and AM MRBs for Uu interface, perform header
decompression using EHC for all stored PDCP SDUs if *drb-ContinueEHC-DL*
is not configured in TS 38.331 \[3\];

\- for UM DRBs, AM DRBs, UM MRBs and AM MRBs, reset the ROHC protocol
for downlink and start with NC state in U-mode (as defined in RFC 3095
\[8\] and RFC 4815 \[9\]) if *drb-ContinueROHC* is not configured in TS
38.331 \[3\];

\- for UM DRBs, AM DRBs, UM MRBs and AM MRBs, reset the EHC protocol for
downlink if *drb-ContinueEHC-DL* is not configured in TS 38.331 \[3\];

\- for SRBs and UM DRBs, set RX_NEXT and RX_DELIV to the initial value;

\- for UM MRBs and AM MRBs, set RX_NEXT and RX_DELIV to the initial
value if *initialRX-DELIV* is configured in TS 38.331 \[3\];

\- apply the ciphering algorithm and key provided by upper layers during
the PDCP entity re-establishment procedure;

\- apply the integrity protection algorithm and key provided by upper
layers during the PDCP entity re-establishment procedure.

NOTE 1: After PDCP re-establishment on a sidelink ‎SRB/DRB, UE determines
when to transmit and receive with the new key and discard the old key as
specified in TS ‎‎33.536 \[14\].‎

NOTE 2: At PDCP re-establishment, the MRB type (i.e. UM MRB or AM MRB)
is determined by the target configuration.‎