### 16.1.8 PUCCH cell switching for TDD cells

To reduce the delay for HARQ-ACK feedback for TDD operation with URLLC
services, PUCCH cell switching for TDD cells is supported. The UE can be
provided in each PUCCH group with a PUCCH switching SCell (PUCCH sSCell)
that can be used for PUCCH transmission in addition to PCell / PSCell /
PUCCH SCell. The applicable cell for PUCCH transmission to be either on
PCell /PSCell / PUCCH SCell or the PUCCH sSCell at a time is either
defined by:

\- a higher layer configured semi-static time-domain pattern of the
applicable cell for PUCCH transmission; or

\- dynamic indication of the cell for PUCCH transmission through a PDCCH
scheduling a PUCCH transmission.

The PUCCH cell switching is applicable to all UCI types when using the
higher layer configured time-domain pattern, but is only applicable to
HARQ feedback for the dynamic indication of the cell for PUCCH
transmission through a PDCCH scheduling PUCCH.