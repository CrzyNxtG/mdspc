### 4.2.1 UE states and state transitions including inter RAT

A UE is either in RRC_CONNECTED state or in RRC_INACTIVE state when an
RRC connection has been established. If this is not the case, i.e. no
RRC connection is established, the UE is in RRC_IDLE state. The RRC
states can further be characterised as follows:

**- RRC_IDLE**:

\- A UE specific DRX may be configured by upper layers;

\- At lower layers, the UE may be configured with a DRX for PTM
transmission of MBS broadcast;

\- UE controlled mobility based on network configuration;

\- The UE:

\- Monitors Short Messages transmitted with P-RNTI over DCI (see clause
6.5);

\- Monitors a Paging channel for CN paging using 5G-S-TMSI, except if
the UE is acting as a L2 U2N Remote UE;

\- If configured by upper layers for MBS multicast reception, monitors a
Paging channel for CN paging using TMGI;

\- Performs neighbouring cell measurements and cell (re-)selection;

\- Performs measurements on L2 U2N Relay UEs and relay (re-)selection;

\- Acquires system information and can send SI request (if configured);

\- Performs logging of available measurements together with location and
time for logged measurement configured UEs;

\- Performs idle/inactive measurements for idle/inactive measurement
configured UEs;

\- If configured by upper layers for MBS broadcast reception, acquires
MCCH change notification and MBS broadcast control information and data.

**- RRC_INACTIVE**:

\- A UE specific DRX may be configured by upper layers or by RRC layer;

\- At lower layers, the UE may be configured with a DRX for PTM
transmission of MBS broadcast and/or a DRX for PTM transmission of MBS
multicast;

\- UE controlled mobility based on network configuration;

\- The UE stores the UE Inactive AS context;

\- A RAN-based notification area is configured by RRC layer;

\- Transfer of unicast data and/or signalling to/from UE over radio
bearers configured for SDT.

\- The UE:

\- Monitors Short Messages transmitted with P-RNTI over DCI (see clause
6.5);

\- While T319a is running, monitors control channels associated with the
shared data channel to determine if data is scheduled for it;

\- While SDT procedure is ongoing and T319a is not running, if CG-SDT is
selected and if extended CG-SDT periodicity is configured (i.e.
*cg-SDT-PeriodicityExt* is configured), monitors a Paging channel for CN
paging using 5G-S-TMSI and RAN paging using fullI-RNTI except if the UE
is acting as a L2 U2N Remote UE;

\- While SDT procedure is not ongoing, monitors a Paging channel for CN
paging using 5G-S-TMSI and RAN paging using fullI-RNTI, except if the UE
is acting as a L2 U2N Remote UE;

\- If configured by upper layers for MBS multicast reception, while SDT
procedure is not ongoing, monitors a Paging channel for paging using
TMGI;

\- Performs neighbouring cell measurements and cell (re-)selection;

\- Performs measurements on L2 U2N Relay UEs and relay (re-)selection;

\- Performs RAN-based notification area updates periodically and when
moving outside the configured RAN-based notification area;

\- Acquires system information and, while SDT procedure is not ongoing,
can send SI request (if configured);

\- While SDT procedure is not ongoing, performs logging of available
measurements together with location and time for logged measurement
configured UEs;

\- While SDT procedure is not ongoing, performs idle/inactive
measurements for idle/inactive measurement configured UEs;

\- If configured by upper layers for MBS broadcast reception, acquires
MCCH change notification and MBS broadcast control information and data;

\- If configured for MBS multicast reception in RRC_INACTIVE, acquires
multicast MCCH change notification and MBS multicast control information
and data;

\- Transmits SRS for Positioning.

**- RRC_CONNECTED:**

\- The UE stores the AS context;

\- Transfer of unicast data to/from UE;

\- Transfer of MBS multicast data to UE;

\- At lower layers, the UE may be configured with a UE specific DRX;

\- At lower layers, the UE may be configured with a DRX for PTM
transmission of MBS broadcast and/or a DRX for MBS multicast;

\- At lower layers, the UE may be configured with a cell specific cell
DTX/DRX;

\- For UEs supporting CA, use of one or more SCells, aggregated with the
SpCell, for increased bandwidth;

\- For UEs supporting DC, use of one SCG, aggregated with the MCG, for
increased bandwidth;

\- Network controlled mobility within NR, to/from E-UTRA, and to
UTRA-FDD;

\- Network controlled mobility (path switch) between a serving cell and
a L2 U2N Relay UE, or vice versa, or between a source L2 U2N Relay UE
and a target L2 U2N Relay UE;

\- Network controlled MP operation.

\- The UE:

\- Monitors Short Messages transmitted with P-RNTI over DCI (see clause
6.5), if configured;

\- Monitors control channels associated with the shared data channel to
determine if data is scheduled for it;

\- Provides channel quality and feedback information;

\- Performs neighbouring cell and/or L2 U2N relay measurements and
measurement reporting;

\- Acquires system information;

\- Performs immediate MDT measurement together with available location
reporting;

\- If configured by upper layers for MBS broadcast reception, acquires
MCCH change notification and MBS broadcast control information and data.

Figure 4.2.1-1 illustrates an overview of UE RRC state machine and state
transitions in NR. A UE has only one RRC state in NR at one time.

![](media/image3.emf)

Figure 4.2.1-1: UE state machine and state transitions in NR

Figure 4.2.1-2 illustrates an overview of UE state machine and state
transitions in NR as well as the mobility procedures supported between
NR/5GC, E-UTRA/EPC and E-UTRA/5GC.

![](media/image4.emf)

Figure 4.2.1-2: UE state machine and state transitions between NR/5GC,
E-UTRA/EPC and E-UTRA/5GC

Figure 4.2.1-3 illustrates the mobility procedure supported between
NR/5GC and UTRA-FDD.

![](media/image5.emf)

Figure 4.2.1-3: Mobility procedure supported between NR/5GC and UTRA-FDD