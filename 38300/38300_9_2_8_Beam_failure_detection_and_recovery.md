### 9.2.8 Beam failure detection and recovery

For beam failure detection, the gNB configures the UE with beam failure
detection reference signals (SSB or CSI-RS) and the UE declares beam
failure when the number of beam failure instance indications from the
physical layer reaches a configured threshold before a configured timer
expires. For beam failure detection in multi-TRP operation, the gNB
configures the UE with two sets of beam failure detection reference
signals, and the UE declares beam failure for a TRP / BFD-RS set when
the number of beam failure instance indications associated with the
corresponding set of beam failure detection reference signals from the
physical layer reaches a configured threshold before a configured timer
expires.

SSB-based Beam Failure Detection is based on the CD-SSB associated to
the initial DL BWP and can be configured for the initial DL BWPs, for DL
BWPs containing the CD-SSB associated to the initial DL BWP, and, if
supported, for DL BWPs not containing the CD-SSB associated to the
initial DL BWP. Besides, SSB-based Beam Failure Detection can be also
performed based on the non-cell defining SSB, if configured for the
active DL BWP. Beam Failure Detection can be also performed based on
CSI-RS, if configured for the active DL BWP.

After beam failure is detected on SpCell, the UE:

\- triggers beam failure recovery by initiating a Random Access
procedure on the SpCell;

\- selects a suitable beam to perform beam failure recovery (if the gNB
has provided dedicated Random Access resources for certain beams, those
will be prioritized by the UE).

\- includes an indication of a beam failure on SpCell in a BFR MAC CE if
the Random Access procedure involves contention-based random access.

Upon completion of the Random Access procedure, beam failure recovery
for SpCell is considered complete.

After beam failure is detected on an SCell, the UE:

\- triggers beam failure recovery by initiating a transmission of a BFR
MAC CE for this SCell;

\- selects a suitable beam for this SCell (if available) and indicates
it along with the information about the beam failure in the BFR MAC CE.

Upon reception of a PDCCH indicating an uplink grant for a new
transmission for the HARQ process used for the transmission of the BFR
MAC CE, beam failure recovery for this SCell is considered complete.

After beam failure is detected for a BFD-RS set of a Serving Cell, the
UE:

\- triggers beam failure recovery by initiating a transmission of a BFR
MAC CE for this BFD-RS set;

\- selects a suitable beam for this BFD-RS set (if available) and
indicates whether the suitable (new) beam is found or not along with the
information about the beam failure in the BFR MAC CE for this BFD-RS
set.

Upon reception of a PDCCH indicating an uplink grant for a new
transmission for the HARQ process used for the transmission of the BFR
MAC CE for this BFD-RS set, beam failure recovery for this BFD-RS set is
considered complete.

After beam failure is detected for both BFD-RS sets of SpCell
concurrently, the UE:

\- triggers beam failure recovery by initiating a Random Access
procedure on the SpCell;

\- selects a suitable beam for each failed BFD-RS set (if available) and
indicates whether the suitable (new) beam is found or not along with the
information about the beam failure in the BFR MAC CE for each failed
BFD-RS set;

\- upon completion of the Random Access procedure, beam failure recovery
for both BFD-RS sets of SpCell is considered complete.