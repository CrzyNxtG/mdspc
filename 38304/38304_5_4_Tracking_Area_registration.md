## 5.4 Tracking Area registration

In the UE, the AS shall report tracking area information to the NAS.

If the UE reads more than one PLMN identity in the current cell, the UE
shall report the found PLMN identities that make the cell suitable in
the tracking area information to NAS.

If the UE operating in SNPN access mode reads more than one SNPN
identity in the current cell, the UE shall report the found SNPN
identities that make the cell suitable in the tracking area information
to NAS.

The AS of an L2 U2N Remote UE in RRC_IDLE or in RRC_INACTIVE may report
the tracking area information to NAS based on the system information
received from the connected L2 U2N Relay UE.

The NAS part of the location registration process is specified in TS
23.122 \[9\].