### 6.1.2 MAC PDU (DL-SCH and UL-SCH except transparent MAC and Random Access Response)

A MAC PDU consists of one or more MAC subPDUs. Each MAC subPDU consists
of one of the following:

\- A MAC subheader only (including padding);

\- A MAC subheader and a MAC SDU;

\- A MAC subheader and a MAC CE;

\- A MAC subheader and padding.

The MAC SDUs are of variable sizes.

Each MAC subheader corresponds to either a MAC SDU, a MAC CE, or
padding.

A MAC subheader except for fixed sized MAC CE, padding, and a MAC SDU
containing UL CCCH consists of the header fields R/F/LCID/(eLCID)/L. A
MAC subheader for fixed sized MAC CE and padding consists of the header
fields R/LCID/(eLCID). A MAC subheader for a MAC SDU containing UL CCCH
consists of the header fields (LX)/R/LCID.

![](media/image6.emf)

![](media/image7.emf)

![](media/image8.emf)

Figure 6.1.2-1: R/F/LCID/(eLCID)/L MAC subheader with 8-bit L field

![](media/image9.emf)

![](media/image10.emf)

![](media/image11.emf)

Figure 6.1.2-2: R/F/LCID/(eLCID)/L MAC subheader with 16-bit L field

![](media/image12.emf)

![](media/image13.emf)

Figure 6.1.2-3: (LX)/R/LCID/(eLCID) MAC subheader

MAC CEs are placed together. DL MAC subPDU(s) with MAC CE(s) is placed
before any MAC subPDU with MAC SDU and MAC subPDU with padding as
depicted in Figure 6.1.2-4. UL MAC subPDU(s) with MAC CE(s) is placed
after all the MAC subPDU(s) with MAC SDU and before the MAC subPDU with
padding in the MAC PDU as depicted in Figure 6.1.2-5. The size of
padding can be zero.

![](media/image14.emf)

Figure 6.1.2-4: Example of a DL MAC PDU

![](media/image15.emf)

Figure 6.1.2-5: Example of a UL MAC PDU

A maximum of one MAC PDU can be transmitted per TB per MAC entity.