### 6.2.3a MAC payload for MSGB

The fallbackRAR is of fixed size as depicted in Figure 6.2.3a-1, and
consists of the following fields:

\- R: Reserved bit, set to 0;

\- TI: If two TAGs are configured for the SpCell, this field indicates
one of the two TAGs to which the Timing Advance Command is applied. If
*tag2-flag* is set to *true* by upper layers, the field set to 0
indicates the *tag2-Id* and the field set to 1 indicates the *tag-Id* of
the SpCell, otherwise the field set to 0 indicates the *tag-Id* and the
field set to 1 indicates the *tag2-Id* of the SpCell. If the SpCell is
not configured with two TAGs, the R bit is present instead;

\- Timing Advance Command: The Timing Advance Command field indicates
the index value *T~A~* used to control the amount of timing adjustment
that the MAC entity has to apply in TS 38.213 \[6\]. The size of the
Timing Advance Command field is 12 bits;

\- UL Grant: The Uplink Grant field indicates the resources to be used
on the uplink in TS 38.213 \[6\]. The size of the UL Grant field is 27
bits;

\- Temporary C-RNTI: The Temporary C-RNTI field indicates the temporary
identity that is used by the MAC entity during Random Access. The size
of the Temporary C-RNTI field is 16 bits.

The fallbackRAR is octet aligned.

![](media/image127.emf)

Figure 6.2.3a-1: fallbackRAR

The successRAR is of fixed size as depicted in Figure 6.2.3a-2, and
consists of the following fields:

\- UE Contention Resolution Identity: This field contains the UL CCCH
SDU. If the UL CCCH SDU is longer than 48 bits, this field contains the
first 48 bits of the UL CCCH SDU.

\- R: Reserved bit, set to 0;

\- ChannelAccess-CPext: The channel access type and CP extension for the
PUCCH resource containing the HARQ feedback for MSGB in shared spectrum
channel access as specified in TS 38.213 \[6\]. The field is only
present when the MSGB HARQ feedback is to be transmitted with shared
spectrum channel access as specified in TS 37.213 \[18\]. Otherwise, the
field is not present and R bits are present instead. The size of the
ChannelAccess-CPext field is 2 bits;

\- TPC: The TPC command for the PUCCH resource containing HARQ feedback
for MSGB, as specified in TS 38.213 \[6\]. The size of the TPC field is
2 bits;

\- HARQ Feedback Timing Indicator: The PDSCH-to-HARQ feedback timing
indicator field for MSGB HARQ feedback as specified in TS 38.213 \[6\].
The size of the HARQ Feedback Timing Indicator field is 3 bits;

\- PUCCH Resource Indicator: The PUCCH resource indicator for HARQ
feedback for MSGB, as specified in TS 38.213\[6\]. The size of the PUCCH
resource Indicator field is 4 bits;

\- Timing Advance Command: The Timing Advance Command field indicates
the index value *T~A~* used to control the amount of timing adjustment
that the MAC entity has to apply in TS 38.213 \[6\]. The size of the
Timing Advance Command field is 12 bits;

\- C-RNTI: The C-RNTI field indicates the identity that is used by the
MAC entity upon completion of Random Access. The size of the C-RNTI
field is 16 bits.

The successRAR is octet aligned.

![](media/image128.emf)

Figure 6.2.3a-2: successRAR