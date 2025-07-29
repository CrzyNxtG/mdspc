### 5.7.19 Satellite switch with resynchronization

A UE capable of hard satellite switch with resynchronization in
RRC_CONNECTED initiates the procedure when *SatSwitchWithReSync* and
*t-Service* are included in *SIB19*.

Upon initiating the procedure, the UE shall:

1\> if *t-ServiceStart* is included in *SIB19* and the UE supports soft
satellite switch with resynchronization:

2\> start acquiring DL synchronization with the SpCell served by the
satellite indicated by *ntn-Config* in *SatSwitchWithReSync* between the
time indicated by *t-ServiceStart* and the time indicated by *t-Service*
for the serving cell;

1\> upon the time indicated by *t-Service:*

2\> stop timer T430 if running;

2\> inform lower layers that UL synchronisation is lost due to satellite
switch with resynchronization;

2\> synchronise to the DL of the SpCell served by the satellite
indicated by *ntn-Config* in *SatSwitchWithReSync*, if the UE has not
previously synchronized to the DL of the SpCell;

2\> start timer T430 with the timer value set to
*ntn-UlSyncValidityDuration* from the subframe indicated by *epochTime*
in *ntn-Config* in *SatSwitchWithReSync*;

2\> inform lower layers when UL synchronisation is obtained.

NOTE: UE should attempt to re-acquire *SIB19* after satellite switch
with resynchronization. The exact time is left to UE implementation.