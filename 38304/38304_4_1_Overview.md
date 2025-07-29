## 4.1 Overview

The RRC_IDLE state and RRC_INACTIVE state tasks can be subdivided into
three processes:

\- PLMN selection (for UE not operating in SNPN access mode) or SNPN
selection (for UE operating in SNPN access mode);

\- Cell selection and reselection;

\- Location registration and RNA update.

PLMN selection, SNPN selection, cell reselection procedures, and
location registration are common for both RRC_IDLE state and
RRC_INACTIVE state. RNA update is only applicable for RRC_INACTIVE
state. When UE selects a new PLMN or SNPN, UE transitions from
RRC_INACTIVE to RRC_IDLE, as specified in TS 24.501 \[14\].

When a UE is switched on, a public land mobile network (PLMN) or a SNPN
is selected by NAS. For the selected PLMN/SNPN, associated RAT(s) may be
set, as specified in TS 23.122 \[9\]. The NAS shall provide a list of
equivalent PLMNs or a list of equivalent SNPNs, if available, that the
AS shall use for cell selection and cell reselection.

With cell selection, the UE searches for a suitable cell of the selected
PLMN or selected SNPN, chooses that cell to provide available services,
and monitors its control channel. This procedure is defined as \"camping
on the cell\".

The UE shall, if necessary, then register its presence, by means of a
NAS registration procedure, in the tracking area of the chosen cell. As
an outcome of a successful Location Registration, the selected PLMN/SNPN
then becomes the registered PLMN/SNPN, as specified in TS 23.122 \[9\].

If the UE finds a more suitable cell, according to the cell reselection
criteria, it reselects onto that cell and camps on it. If the new cell
does not belong to at least one tracking area to which the UE is
registered, location registration is performed. In RRC_INACTIVE state,
if the new cell does not belong to the configured RNA, an RNA update
procedure is performed.

If necessary, the UE shall search for higher priority PLMNs at regular
time intervals as described in TS 23.122 \[9\] and search for a suitable
cell if another PLMN has been selected by NAS.

For UE not operating in SNPN access mode, search of available CAGs may
be triggered by NAS to support manual CAG selection. The AS shall report
available CAG-ID(s) together with their HRNN (if broadcast) and PLMN(s)
to the NAS.

NAS may also provide the network slice(s) and Network Slice AS Group
(NSAG) information, which contains NSAG(s), their applicable TA(s) if
present and their priorities, to be considered by the UE during cell
reselection (as specified in TS 23.501 \[10\], TS 24.501 \[14\]).

If the UE loses coverage of the registered PLMN/SNPN, either a new
PLMN/SNPN is selected automatically (automatic mode), or an indication
of available PLMNs/SNPNs is given to the user so that a manual selection
can be performed (manual mode). As part of manual SNPN selection, the AS
shall report available SNPN identifiers together with their HRNN (if
broadcast) to the NAS.

Registration is not performed by UEs only capable of services that need
no registration.

The UE may perform NR sidelink communication and/or V2X sidelink
communication while in-coverage or out-of-coverage for sidelink, as
specified in clause 8.

The U2N Remote UE, the U2N Relay UE, the U2U Remote UE, or the U2U Relay
UE may perform sidelink discovery transmissions while in-coverage for
the purposes of sidelink relay operations, as specified in clause 8. In
addition, the U2N Remote UE, the U2U Remote UE, or the U2U Relay UE can
also perform sidelink discovery transmissions while out-of-coverage for
the purposes of sidelink relay operations.

An L2 U2N Remote UE in RRC_IDLE or in RRC_INACTIVE may perform all the
relevant procedures (e.g., acquiring system information and paging
message) via the L2 U2N Relay UE. An L2 U2N Remote UE may choose not to
perform any procedures related to cell selection and reselection.

The UE may perform NR sidelink discovery transmissions while in-coverage
or out-of-coverage for the purpose of sidelink non-relay operations, as
specified in clause 8.

The UE may perform ranging/sidelink positioning while in-coverage or
out-of-coverage, as specified in clause 8.

The purpose of camping on a cell in RRC_IDLE state and RRC_INACTIVE
state is as follows:

a\) It enables the UE to receive system information from the PLMN or the
SNPN.

b\) When registered and if the UE wishes to establish an RRC connection
or resume a suspended RRC connection, it can do this by initially
accessing the network on the control channel of the cell on which it is
camped.

c\) If the network needs to send a message or deliver data to the
registered UE, it knows (in most cases) the set of tracking areas (in
RRC_IDLE state) or RNA (in RRC_INACTIVE state) in which the UE is
camped. It can then send a \"paging\" message for the UE on the control
channels of all the cells in the corresponding set of areas. The UE will
then receive the paging message and can respond.

d\) It enables the UE to receive ETWS and CMAS notifications.

e\) It enables the UE to receive MBS broadcast services.

f\) It enables the UE to receive MBS multicast services in RRC_INACTIVE
state.

When the UE is in RRC_IDLE state, upper layers may deactivate AS layer
when MICO mode is activated as specified in TS 24.501 \[14\]. When MICO
mode is activated, the AS configuration (e.g. priorities provided by
dedicated signalling) is kept and all running timers continue to run but
the UE need not perform any idle mode tasks. If a timer expires while
MICO mode is activated it is up to the UE implementation whether it
performs the corresponding action immediately or the latest when MICO
mode is deactivated. When MICO mode is deactivated, the UE shall perform
all idle mode tasks.