### 6.1.5a MAC PDU (MSGB)

A MAC PDU consists of one or more MAC subPDUs and optionally padding.
Each MAC subPDU consists one of the following:

\- a MAC subheader with Backoff Indicator only;

\- a MAC subheader and fallbackRAR;

\- a MAC subheader and successRAR;

\- a MAC subheader and MAC SDU for CCCH, DCCH or DTCH;

\- a MAC subheader and padding.

A MAC subheader with Backoff Indicator consists of five header fields
E/T1/T2/R/BI as described in Figure 6.1.5a-1. A MAC subPDU with Backoff
Indicator only is placed at the beginning of the MAC PDU, if included.

A MAC subheader for fallbackRAR consists of three header fields
E/T1/RAPID as described in Figure 6.1.5a-2. A MAC subheader for
successRAR consists of eight header fields E/T1/T2/S/R/R/R/R as
described in Figure 6.1.5a-3. A MAC subheader for MAC SDU consists of
the four header fields R/F/LCID/L as described in Figure 6.1.2-1 and
Figure 6.1.2-2.

At most one \'MAC subPDU for successRAR\' indicating presence of \'MAC
subPDU(s) for MAC SDU\' is included in a MAC PDU. MAC subPDU(s) for MAC
SDU are placed immediately after the \'MAC subPDU for successRAR\'
indicating presence of \'MAC subPDU(s) for MAC SDU\'.

If MAC PDU includes MAC subPDU(s) for MAC SDU, the last MAC subPDU for
MAC SDU is placed before MAC subPDU with padding as depicted in Figure
6.1.5a-4. Otherwise, the last MAC subPDU in MAC PDU is placed before
padding as depicted in Figure 6.1.5a-5. The MAC subPDU with padding
includes R/R/LCID MAC subheader as described in Figure 6.1.2-3 and
padding. The size of padding in the MAC subPDU with padding can be zero.
The length of padding is implicit based on TB size, size of MAC
subPDU(s).

![](media/image119.emf)

Figure 6.1.5a-1: BI MAC subheader

![](media/image120.emf)

Figure 6.1.5a-2: FallbackRAR MAC subheader

![](media/image121.emf)

Figure 6.1.5a-3: SuccessRAR MAC subheader

![](media/image122.emf)

Figure 6.1.5a-4: Example of a MSGB MAC PDU with MAC SDU(s)

![](media/image123.emf)

Figure 6.1.5a-5: Example of a MSGB MAC PDU without MAC SDU(s)