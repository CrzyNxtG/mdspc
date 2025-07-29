### 16.9.7 Power Savings Resource Allocation

The SL UE in Mode 2 can support partial sensing-based resource
allocation and random resource selection as power saving resource
allocation methods. A SL mode 2 TX resource pool can be (pre)configured
to allow full sensing only, partial sensing only, random selection only,
or any combination(s) thereof. A UE decides which resource allocation
scheme(s) can be used in the AS based on its capability (for a UE in
RRC_IDLE/RRC_INACTIVE/OOC) and the allowed resource schemes in the
resource pool configuration.

Random resource selection is applicable to both periodic and aperiodic
traffic.

A UE capable for partial sensing can perform periodic-based partial
sensing and/or contiguous partial sensing for resource (re)selection.
Periodic-based partial sensing can only be performed if periodic
resource reservation is configured in the resource pool. In
periodic-based partial sensing, the UE monitors slots in periodic
sensing occasion(s) for a given resource reservation periodicity.
Contiguous partial sensing is performed by a UE capable of partial
sensing when resource (re)selection is triggered by a UE in a TX pool
configured with partial sensing. In contiguous partial sensing, the UE
monitors slots in a contiguous sensing window which occur prior to the
selected transmission resource.