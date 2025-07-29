### 5.8.12 DFN derivation from GNSS

When the UE selects GNSS as the synchronization reference source, the
DFN, the subframe number within a frame and slot number within a frame
used for NR sidelink communication/discovery are derived from the
current UTC time, by the following formulae:

*DFN*= Floor (0.1\*(*Tcurrent* --*Tref--OffsetDFN*)) mod 1024

*SubframeNumber*= Floor (*Tcurrent* --*Tref--OffsetDFN*) mod 10

*SlotNumber*= Floor ((*Tcurrent* --Tref--*OffsetDFN*)\*2^μ^) mod
(10\*2^μ^)

Where:

***Tcurrent*** is the current UTC time obtained from GNSS. This value is
expressed in milliseconds;

***Tref*** is the reference UTC time 00:00:00 on Gregorian calendar date
1 January, 1900 (midnight between Thursday, December 31, 1899 and
Friday, January 1, 1900). This value is expressed in milliseconds;

***OffsetDFN*** is the value *sl-OffsetDFN* if configured, otherwise it
is zero. This value is expressed in milliseconds.

μ=0/1/2/3 corresponding to the 15/30/60/120 kHz of SCS for SL,
respectively.

NOTE 1: In case of leap second change event, how UE obtains the
scheduled time of leap second change to adjust *Tcurrent*
correspondingly is left to UE implementation. How UE handles to avoid
the sudden discontinuity of DFN is left to UE implementation.

NOTE 2: Void.