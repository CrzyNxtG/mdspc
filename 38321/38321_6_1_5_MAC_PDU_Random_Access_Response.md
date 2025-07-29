### 6.1.5 MAC PDU (Random Access Response)

A MAC PDU consists of one or more MAC subPDUs and optionally padding.
Each MAC subPDU consists one of the following:

\- a MAC subheader with Backoff Indicator only;

\- a MAC subheader with RAPID only (i.e. acknowledgment for SI request);

\- a MAC subheader with RAPID and MAC RAR.

A MAC subheader with Backoff Indicator consists of five header fields
E/T/R/R/BI as described in Figure 6.1.5-1. A MAC subPDU with Backoff
Indicator only is placed at the beginning of the MAC PDU, if included.
\'MAC subPDU(s) with RAPID only\' and \'MAC subPDU(s) with RAPID and MAC
RAR\' can be placed anywhere between MAC subPDU with Backoff Indicator
only (if any) and padding (if any).

A MAC subheader with RAPID consists of three header fields E/T/RAPID as
described in Figure 6.1.5-2.

Padding is placed at the end of the MAC PDU if present. Presence and
length of padding is implicit based on TB size, size of MAC subPDU(s).

![](media/image116.emf)

Figure 6.1.5-1: E/T/R/R/BI MAC subheader

![](media/image117.emf)

Figure 6.1.5-2: E/T/RAPID MAC subheader

![](media/image118.emf)

Figure 6.1.5-3: Example of MAC PDU consisting of MAC RARs