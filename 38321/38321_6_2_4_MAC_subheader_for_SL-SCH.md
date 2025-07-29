### 6.2.4 MAC subheader for SL-SCH

The MAC subheader consists of the following fields:

\- V: The MAC PDU format version number field indicates which version of
the SL-SCH subheader is used. In this version of the specification, the
V field is set to 0. The size of the V field is 4 bits;

\- SRC: The SRC field carries the 16 most significant bits of the Source
Layer-2 ID set to the identifier provided by upper layers as defined in
TS 23.287 \[19\] or TS 23.304 \[26\]. The length of the field is 16
bits;

\- DST: The DST field carries the 8 most significant bits of the
Destination Layer-2 ID set to the identifier provided by upper layers as
defined in TS 23.287 \[19\] or TS 23.304 \[26\]. The length of the field
is 8 bits;

\- LCID: The Logical Channel ID field identifies the logical channel
instance of the corresponding MAC SDU or the type of the corresponding
MAC CE within the scope of one Source Layer-2 ID and Destination Layer-2
ID pair or padding as described in Tables 6.2.4-1 for SL-SCH. There is
one LCID field per MAC subheader except for SL-SCH subheader. The values
of LCID from 21 to 36 identify the logical channels used to send
duplicated RLC SDUs from logical channels of which the values of LCID
from 4 to 19 respectively in sequential order. The size of the LCID
field is 6 bits;

\- L: The Length field indicates the length of the corresponding MAC SDU
or variable-sized MAC CE in bytes. There is one L field per MAC
subheader except for SL-SCH subheader and subheaders corresponding to
the fixed-sized MAC CE or padding. The size of the L field is indicated
by the F field;

\- F: The Format field indicates the size of the Length field. There is
one F field per MAC subheader except for SL-SCH subheader and subheaders
corresponding to the fixed-sized MAC CE or padding. The size of the F
field is 1 bit. The value 0 indicates 8 bits of the Length field. The
value 1 indicates 16 bits of the Length field;

\- R: Reserved bit, set to 0.

The MAC subheader is octet aligned.

Table 6.2.4-1: Values of LCID for SL-SCH

  -----------------------------------------------------------------------
  Index            LCID values
  ---------------- ------------------------------------------------------
  0                SCCH carrying PC5-S messages that are not protected

  1                SCCH carrying PC5-S messages \"Direct Security Mode
                   Command\" and \"Direct Security Mode
                   Complete\",\"ProSe direct link security mode command\"
                   and \"ProSe direct link security mode complete\"

  2                SCCH carrying other PC5-S messages that are protected

  3                SCCH carrying PC5-RRC messages

  4--19            Identity of the logical channel

  20               SCCH carrying PC5-S messages (\"Direct Security Mode
                   Command\" and \"Direct Security Mode Complete\") which
                   is used for duplication

  21               SCCH carrying other PC5-S messages that are protected
                   which is used for duplication

  22               SCCH carrying PC5-RRC messages which is used for
                   duplication

  23-38            Identity of the logical channel which is used for
                   duplication

  39--52           Reserved

  53               Enhanced Sidelink Inter-UE Coordination Request

  54               Enhanced Sidelink Inter-UE Coordination Information

  55               SCCH carrying end-to-end SL-SRB0/1/2/3 messages
                   delivered via SL-U2U-RLC as specified in TS 38.331
                   \[5\]

  56               SCCH carrying RRC messages delivered via SL-RLC0 as
                   specified in TS 38.331 \[5\]

  57               SCCH carrying RRC message delivered via SL-RLC1 as
                   specified in TS 38.331 \[5\]

  58               SCCH for Sidelink Discovery Messages

  59               Sidelink Inter-UE Coordination Request

  60               Sidelink Inter-UE Coordination Information

  61               Sidelink DRX Command

  62               Sidelink CSI Reporting

  63               Padding
  -----------------------------------------------------------------------