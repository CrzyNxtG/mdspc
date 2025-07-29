### 6.2.2a MAC subheader for MSGB

The MAC subheader consists of the following fields:

\- E: The Extension field is a flag indicating if the MAC subPDU
including this MAC subheader is the last MAC subPDU (other than MAC
subPDU for MAC SDU) or not in the MAC PDU. The E field is set to 1 to
indicate at least another MAC subPDU (other than MAC subPDU for MAC SDU)
follows. The E field is set to 0 to indicate that the MAC subPDU
including this MAC subheader is the last MAC subPDU (other than MAC
subPDU for MAC SDU) in the MAC PDU;

\- T1: The T1 field is a flag indicating whether the MAC subheader
contains a Random Access Preamble ID or T2. The T1 field is set to 1 to
indicate the presence of a Random Access Preamble ID field in the
subheader (RAPID). The T1 field is set to 0 to indicate the presence of
T2 field in the subheader;

\- T2: The T2 field is a flag indicating whether the MAC subheader
contains a Backoff Indicator (BI) or a MAC SDU indicator (S). The T2
field is set to 0 to indicate the presence of a Backoff Indicator field
in the subheader. The T2 field is set to 1 to indicate the presence of
the S field in the subheader;

\- S: This field indicates whether \'MAC subPDU(s) for MAC SDU\' follow
the MAC subPDU including this MAC subheader or not; The S field is set
to 1 to indicate presence of \'MAC subPDU(s) for MAC SDU\'. The S field
is set to 0 to indicate absence of \'MAC subPDU(s) for MAC SDU\';

\- R: Reserved bit, set to 0;

\- BI: The Backoff Indicator field identifies the overload condition in
the cell. The size of the BI field is 4 bits;

\- RAPID: The Random Access Preamble IDentifier field identifies the
transmitted Random Access Preamble (see clause 5.1.3). The size of the
RAPID field is 6 bits.

The MAC subheader is octet aligned.