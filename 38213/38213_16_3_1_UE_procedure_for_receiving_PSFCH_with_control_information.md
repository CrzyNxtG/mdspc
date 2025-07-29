### 16.3.1 UE procedure for receiving PSFCH with control information

A UE that transmitted a PSSCH scheduled by a SCI format 2-A/2-B/2-C that
indicates HARQ feedback enabled, attempts to receive associated PSFCHs
with HARQ-ACK information according to PSFCH resources determined as
described in clause 16.3.0. The UE determines an ACK or a NACK value for
HARQ-ACK information provided in each PSFCH resource as described in
\[8-4, TS 38.101-4\]. The UE does not determine both an ACK value and a
NACK value at a same time for a PSFCH resource.

For each PSFCH reception occasion, from a number of PSFCH reception
occasions, the UE generates HARQ-ACK information to report to higher
layers. For operation with shared spectrum channel access, the UE
attempts to receive PSFCH on $N_{occasion}^{PSFCH}$ PSFCH occasion(s),
as described in clause 16.3.0, until the UE detects one PSFCH from each
UE expected to transmit a PSFCH, or the UE attempts to receive PSFCH on
all the $N_{occasion}^{PSFCH}$ PSFCH occasion(s). For generating the
HARQ-ACK information, the UE can be indicated by a SCI format to perform
one of the following

\- if the UE receives a PSFCH associated with a SCI format 2-A with Cast
type indicator field value of \"10\" or a SCI format 2-C

\- report to higher layers HARQ-ACK information with same value as a
value of HARQ-ACK information that the UE determines from the PSFCH
reception for operation without shared spectrum channel access, or from
the PSFCH reception(s) on $N_{occasion}^{PSFCH}$ PSFCH reception
occasion(s), as described in clause 16.3.0, for operation with shared
spectrum channel access

\- if the UE receives a PSFCH associated with a SCI format 2-A with Cast
type indicator field value of \"01\"

\- report an ACK value to higher layers if the UE determines an ACK
value from at least one PSFCH reception occasion from the number of
PSFCH reception occasions in PSFCH resources corresponding to every
identity $M_{\text{ID}}$ of UEs that the UE expects to receive
corresponding PSSCHs as described in clause 16.3; otherwise, report a
NACK value to higher layers

\- if the PSFCH reception occasion is associated with a SCI format 2-B
or a SCI format 2-A with Cast type indicator field value of \"11\"

\- report to higher layers an ACK value if the UE determines absence of
PSFCH reception for the PSFCH reception occasion; otherwise, report a
NACK value to higher layers

A UE that transmitted SCI format 1-A, indicating one or more reserved
resources in a resource pool enabled by
*sl-InterUE-CoordinationScheme2*, attempts to receive associated PSFCH
with conflict information in the resource pool with PSFCH resources that
the UE determines as described in clause 16.3.0. If the UE determines
presence of a resource conflict based on conflict information in a PSFCH
reception, the UE reports the resource conflict to higher layers

\- if *sl-SlotLevelResourceExclusion* is not provided, the UE reports
resources overlapping with a next in time reserved resource indicated by
the SCI format 1-A

\- if *sl-SlotLevelResourceExclusion* is provided, the UE reports
resources in a slot of a next in time reserved resource indicated by the
SCI format 1-A

If a UE receives a PSFCH with conflict information corresponding to a
reserved resource indicated in an SCI format 1-A, the UE receives the
PSFCH in the resource pool in a slot determined based on
*sl-PSFCH-Occasion*

\- if sl-PSFCH-Occasion = \'0\',

\- for operation without shared spectrum channel access, the UE receives
the PSFCH in a first slot that includes PSFCH resources and is at least
a number of slots, provided by *sl-MinTimeGapPSFCH*, of the resource
pool after a slot of a PSCCH transmission that provides the SCI format
1-A. The PSFCH resource is in a slot that is at least $T_{3}$ slots \[6,
TS 38.214\] before the resource associated with the conflict
information; otherwise, the UE does not receive the PSFCH with conflict
information

\- for operation with shared spectrum channel access, the UE attempts to
receive the PSFCH on a number of first $N_{occasion}^{PSFCH}$ slots,
provided by *sl-NumPSFCH-Occasions* and indexed from 1 to
$N_{occasion}^{PSFCH}$ in ascending order in time, that include PSFCH
resources and are at least a number of slots, provided by
*sl-MinTimeGapPSFCH*, of the resource pool after a last slot of a PSCCH
reception that provides the SCI format 1-A, until the UE detects one
PSFCH with conflict information, or the UE attempts to receive PSFCH on
all $N_{occasion}^{PSFCH}$ PSFCH occasions. If the PSFCH resource is in
a slot that is at least $T_{3}$ slots before the resource associated
with the conflict information, the UE can attempt to receive the PSFCH
with conflict information in the slot; otherwise, the UE does not
receive the PSFCH with conflict information in the slot

\- if sl-PSFCH-Occasion = \'1\',

\- for operation without shared spectrum channel access, the UE receives
the PSFCH in a latest slot that includes PSFCH resources and is at least
$T_{3}$ slots of the resource pool before a slot of the resource
associated with conflict information. The PSFCH resource is in a slot
that is at least *sl-MinTimeGapPSFCH* slots after a slot of a PSCCH
transmission that provides the SCI format 1-A; otherwise, the UE does
not receive the PSFCH with conflict information

\- for operation with shared spectrum channel access, the UE attempts to
receive the PSFCH on a number of latest $N_{occasion}^{PSFCH}$ slots,
provided by *sl-NumPSFCH-Occasions* and indexed from 1 to
$N_{occasion}^{PSFCH}$ in ascending order in time, that include PSFCH
resources and are at least $T_{3}$ slots of the resource pool before a
slot of the resource associated with conflict information, until the UE
detects one PSFCH with conflict information, or the UE attempts to
receive PSFCH on all $N_{occasion}^{PSFCH}$ PSFCH occasions. If the
PSFCH resource is in a slot that is at least *sl-MinTimeGapPSFCH* slots
after a slot of a PSCCH transmission that provides the SCI format 1-A,
the UE can attempt to receive the PSFCH with conflict information in the
slot; otherwise, the UE does not receive the PSFCH with conflict
information in the slot.