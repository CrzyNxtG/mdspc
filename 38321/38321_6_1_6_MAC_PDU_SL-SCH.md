### 6.1.6 MAC PDU (SL-SCH)

A MAC PDU consists of one SL-SCH subheader and one or more MAC subPDUs.
Each MAC subPDU consists of one of the following:

\- A MAC subheader only (including padding);

\- A MAC subheader and a MAC SDU;

\- A MAC subheader and a MAC CE;

\- A MAC subheader and padding.

The MAC SDUs are of variable sizes.

Each MAC subheader except SL-SCH subheader corresponds to either a MAC
SDU, a MAC CE, or padding.

The SL-SCH subheader is of a fixed size and consists of the seven header
fields V/R/R/R/R/SRC/DST.

![](media/image124.emf)

Figure 6.1.6-1: SL-SCH MAC subheader

A MAC subheader except for fixed-sized MAC CE and padding consists of
the four header fields R/F/LCID/L as depicted in Figure 6.1.2-1 (with
8-bit L field) and Figure 6.1.2-2 (with 16-bit L field). A MAC subheader
for fixed-sized MAC CE and padding consists of the two header fields
R/LCID as depicted in Figure 6.1.2-3.

SL MAC subPDU(s) with MAC SDU(s) is placed after the SL-SCH subheader
and before the MAC subPDU with a MAC CE and the MAC subPDU with padding
in the MAC PDU as depicted in Figure 6.1.6-2. SL MAC subPDU with a MAC
CE is placed after all the MAC subPDU(s) with MAC SDU and before the MAC
subPDU with padding in the MAC PDU as depicted in Figure 6.1.6-2. The
size of padding can be zero.

![](media/image125.emf)

Figure 6.1.6-2: Example of an SL MAC PDU

A maximum of one MAC PDU can be transmitted per TB per MAC entity.