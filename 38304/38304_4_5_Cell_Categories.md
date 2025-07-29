## 4.5 Cell Categories

The cells are categorised according to which services they offer:

**acceptable cell:**

An \"acceptable cell\" is a cell on which the UE may camp to obtain
limited service (originate emergency calls and receive ETWS and CMAS
notifications). Such a cell shall fulfil the following requirements,
which is the minimum set of requirements to initiate an emergency call
and to receive ETWS and CMAS notification in an NR network:

\- The cell is not barred, see clause 5.3.1;

\- The cell selection criteria are fulfilled, see clause 5.2.3.2.

**suitable cell:**

For UE not operating in SNPN Access Mode, a cell is considered as
suitable if the following conditions are fulfilled:

\- The cell is part of either the selected PLMN or the registered PLMN
or PLMN of the Equivalent PLMN list, and for that PLMN either:

\- The PLMN-ID of that PLMN is broadcast by the cell with no associated
CAG-IDs and CAG-only indication in the UE for that PLMN (TS 23.501
\[10\]) is absent or false;

\- Allowed CAG list in the UE for that PLMN (TS 23.501 \[10\]) includes
a CAG-ID broadcast by the cell for that PLMN;

\- The cell selection criteria are fulfilled, see clause 5.2.3.2.

According to the latest information provided by NAS:

\- The cell is not barred, see clause 5.3.1;

\- The cell is part of at least one TA that is not part of the list of
\"Forbidden Tracking Areas for Roaming\" (TS 22.011 \[18\]), which
belongs to a PLMN that fulfils the first bullet above.

For UE operating in SNPN Access Mode, a cell is considered as suitable
if the following conditions are fulfilled:

\- The cell is part of the selected SNPN or the registered SNPN or SNPN
of the Equivalent SNPN list of the UE;

\- The cell selection criteria are fulfilled, see clause 5.2.3.2;

According to the latest information provided by NAS:

\- The cell is not barred, see clause 5.3.1;

\- The cell is part of at least one TA that is not part of the list of
\"Forbidden Tracking Areas for Roaming\" which belongs to the selected
SNPN or the registered SNPN or SNPN of the Equivalent SNPN list of the
UE.

**barred cell:**

A cell is barred if it is so indicated in the system information, as
specified in TS 38.331 \[3\].

**reserved cell:**

A cell is reserved if it is so indicated in system information, as
specified in TS 38.331 \[3\].

Following exception to these definitions are applicable for UEs:

\- if a UE has an ongoing emergency call, all acceptable cells of that
PLMN/SNPN are treated as suitable for the duration of the emergency
call.

\- camped on a cell that belongs to a tracking area that is forbidden
for regional provision of service; a cell that belongs to a tracking
area that is forbidden for regional provision service (TS 23.122 \[9\],
TS 24.501 \[14\]) is suitable but provides only limited service.

\- if the UE in RRC_IDLE fulfils the conditions to support NR sidelink
communication/discovery or V2X sidelink communication in limited service
state as specified in TS23.287 \[16\] clause 5.7, the UE may perform NR
sidelink communication/discovery or V2X sidelink communication.

> NOTE: UE is not required to support manual search and selection of
> PLMN or CAG or SNPN while in RRC CONNECTED state. The UE may use local
> release of RRC connection to perform manual search if it is not
> possible to perform the search while RRC connected.