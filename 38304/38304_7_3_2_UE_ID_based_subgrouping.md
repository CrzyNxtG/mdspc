### 7.3.2 UE_ID based subgrouping

Paging with UE_ID based subgrouping is used in the cell which supports
UE_ID based subgrouping, as described in clause 7.3.0.

If the UE is not configured with a CN assigned subgroup ID, or if the UE
configured with a CN assigned subgroup ID is in a cell supporting only
UE_ID based subgrouping, the subgroup ID of the UE is determined by the
formula below:

SubgroupID = (floor(UE_ID/(N\*Ns)) mod subgroupsNumForUEID) +
(subgroupsNumPerPO - subgroupsNumForUEID),

where:

N: number of total paging frames in T, which is the DRX cycle of
RRC_IDLE state as specified in clause 7.1

Ns: number of paging occasions for a PF

UE_ID: 5G-S-TMSI mod X, where X is 32768, if eDRX is applied; otherwise,
X is 8192

subgroupsNumForUEID: number of subgroups for UE_ID based subgrouping in
a PO, which is broadcasted in system information

In RRC_INACTIVE state with CN configured PTW the SubgroupID used outside
CN PTW is the same as the SubgroupID used inside CN PTW.

The UE belonging to the SubgroupID monitors its associated PEI which
indicates the paged subgroup(s) as specified in clause 7.2.