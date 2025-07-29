## 8.1 UE Identities

In this clause, the identities used by NR connected to 5GC are listed.
For scheduling at cell level, the following identities are used:

\- C-RNTI: unique UE identification used as an identifier of the RRC
Connection and for scheduling;

\- CG-SDT-CS-RNTI: unique UE identification used for Configured
Grant-based SDT in the uplink;

\- CI-RNTI: identification of cancellation in the uplink;

\- CS-RNTI: unique UE identification used for Semi-Persistent Scheduling
in the downlink or configured grant in the uplink;

\- INT-RNTI: identification of pre-emption in the downlink;

\- MCS-C-RNTI: unique UE identification used for indicating an
alternative MCS table for PDSCH and PUSCH;

\- P-RNTI: identification of Paging and System Information change
notification in the downlink;

\- SI-RNTI: identification of Broadcast and System Information in the
downlink;

\- SP-CSI-RNTI: unique UE identification used for semi-persistent CSI
reporting on PUSCH.

For power and slot format control, the following identities are used:

\- SFI-RNTI: identification of slot format;

\- TPC-PUCCH-RNTI: unique UE identification to control the power of
PUCCH;

\- TPC-PUSCH-RNTI: unique UE identification to control the power of
PUSCH;

\- TPC-SRS-RNTI: unique UE identification to control the power of SRS.

During the random access procedure, the following identities are also
used:

\- RA-RNTI: identification of the Random Access Response in the
downlink;

\- MSGB-RNTI: identification of the Random Access Response for 2-step RA
type in the downlink;

\- Temporary C-RNTI: UE identification temporarily used for scheduling
during the random access procedure;

\- Random value for contention resolution: UE identification temporarily
used for contention resolution purposes during the random access
procedure.

For NR connected to 5GC, the following UE identity is used at NG-RAN
level:

\- I-RNTI: used to identify the UE context in RRC_INACTIVE.

For UE power saving purpose, the following identities are used:

\- PS-RNTI: used to determine if the UE needs to monitor PDCCH on the
next occurrence of the connected mode DRX on-duration;

\- PEI-RNTI: used to determine if the UE needs to monitor the associated
PO.

For IAB the following identity is used:

\- AI-RNTI: identification of the DCI carrying availability indication
for soft symbols of an IAB-DU.

For Network-Controlled Repeater the following identity is used:

\- NCR-RNTI: identification of the DCI carrying side control
information.

For MBS, the following identities are used:

\- G-RNTI: Identifies dynamically scheduled PTM transmissions of
MTCH(s);

\- G-CS-RNTI: Identifies configured scheduled PTM transmissions of
MTCH(s) scheduled with configured grant;

\- MCCH-RNTI: Identifies transmissions of MCCH and MCCH change
notification for broadcast reception.

\- Multicast MCCH-RNTI: Identifies transmissions of MCCH and MCCH change
notification for multicast reception in RRC_INACTIVE state.

For sidelink, the following identities are used:

\- SL-RNTI: unique UE identification used for NR sidelink communication
scheduling;

\- SL-CS-RNTI: unique UE identification used for configured sidelink
grant for NR sidelink communication;

\- SL Semi-Persistent Scheduling V-RNTI: unique UE identification used
for semi-persistent scheduling for V2X sidelink communication;

\- SL-PRS-RNTI: unique UE identification used for SL-PRS transmission
scheduling on dedicated SL-PRS resource pool;

\- SL-PRS-CS-RNTI: unique UE identification used for configured sidelink
grant for SL-PRS transmission on dedicated SL-PRS resource pool.

For network energy saving purpose, the following identity is used:

\- cellDTRX-RNTI: identification used for network energy saving
indication.