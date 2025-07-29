## 5.1 PLMN selection and SNPN selection

In the UE not operating in SNPN access mode, the AS shall report
available PLMNs and any associated CAG-IDs to the NAS on request from
the NAS or autonomously. In the UE operating in SNPN access mode, the AS
shall report available SNPNs to the NAS on request from the NAS or
autonomously.

During PLMN selection, based on the list of PLMN identities in priority
order, the particular PLMN may be selected either automatically or
manually. Each PLMN in the list of PLMN identities is identified by a
\'PLMN identity\'. In the system information on the broadcast channel,
the UE can receive one or multiple \'PLMN identity\' in a given cell.
The result of the PLMN selection performed by NAS (see TS 23.122 \[9\])
is an identifier of the selected PLMN.

During SNPN selection, based on the list of SNPN identities, the
particular SNPN may be selected either automatically or manually. Each
SNPN in the list of SNPN identities is identified by a \'SNPN
identity\'. In the system information on the broadcast channel, the UE
can receive one or multiple \'SNPN identity\' in a given cell and
optionally may receive associated HRNNs; the UE may also optionally
receive indicators for whether an SNPN allows access using credentials
from a Credentials Holder, whether an SNPN allows registration attempts
from UEs that are not explicitly configured to select this SNPN, and
whether an SNPN allows onboarding; the UE may also optionally receive a
list of supported Group IDs for Network selection (see TS 38.331 \[3\]).
The result of the SNPN selection performed by NAS (see TS 23.122 \[9\])
is an identifier of the selected SNPN.