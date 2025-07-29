### 8.1.5A UE procedure for determining slots and resource blocks indicated by a preferred or non-preferred resource set

The set of slots and resource blocks indicated by a set of preferred or
non-preferred resource(s) is determined as described below.

If the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH*
is not provided, or it is set to 'contiguousRB\', the set of preferred
or non-preferred resources $\left\{ r_{0},r_{1},r_{2},\ldots \right\}$,
is indicated by a reference slot $t_{ref}$ and $M$ tuples
$({TRIV}_{m},{FRIV}_{m},P_{rsvp,m})$, $1 \leq m \leq M$ indicated by the
\'resource combination\' field, where for each tuple ${TRIV}_{m}$ is
indicated by the 9 MSBs, followed by ${FRIV}_{m}$ and $P_{rsvp,m}$ (if
present).

If the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH*
is set to 'interlaceRB\', the set of preferred or non-preferred
resources $\left\{ r_{0},r_{1},r_{2},\ldots \right\}$, is indicated by a
reference slot $t_{ref}$ and $M$ tuples
$({TRIV}_{m},{FRIV}_{m},{FRIV}_{RBset,m},P_{rsvp,m})$, $1 \leq m \leq M$
indicated by the \'resource combination\' field, where for each tuple
${TRIV}_{m}$ is indicated by the 9 MSBs, followed by ${FRIV}_{m}$,
${FRIV}_{RBset,m}$ and $P_{rsvp,m}$ (if present).

The reference slot $t_{ref}$ is indicated by the \'Reference slot
location\' field as a combination of DFN index and slot index \[5, TS
38.212\], with the 10 MSBs indicating the DFN index. ${TRIV}_{m}$,
${FRIV}_{m}$ and ${FRIV}_{RBset,m}$ if any are interpreted according to
clause 8.1.5, with the following modifications:

\- the value of *sl-MaxNumPerReserve* is fixed to 3.

\- \"slot where SCI format 1-A was received\" is replaced by slot
indicated as the first resource location of a ${TRIV}_{m}$.

\- the first resource location of each ${TRIV}_{m}$ for $m > 1$ is
indicated by a slot offset $t_{m}$ in logical slots with respect to the
reference slot $t_{ref}$; the slot offset $t_{m}$ is indicated by the
\'first resource location\' field; the first resource location of
${TRIV}_{1}$ is at slot offset 0 with respect to the reference slot.

\- \"the received SCI format 1-A, except the resource in the slot where
SCI format 1-A was received\" is replaced by \"each tuple\".

\- the starting sub-channel $n_{subCH,0}^{start}$ of the first resource
of each tuple is separately indicated.

\- if the higher layer parameter
*sl-TransmissionStructureForPSCCHandPSSCH* is set to 'interlaceRB\', the
starting RB set $n_{RBset,0}^{start}$ of the first resource of each
tuple is separately indicated.

The starting sub-channel $n_{subCH,0}^{start}$ of the first resource of
each tuple is indicated by the \'Lowest subChannel indices\' field. The
starting RB set $n_{RBset,0}^{start}$ of the first resource of each
tuple, if any, is indicated by the \'Lowest RB set indices\' field. The
resource reservation period $P_{rsvp,m}$ is encoded as in SCI format
1-A.

If the set is indicated by an SCI format 2-C, the number of tuples is
$M = 2$.

If the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH*
is not provided, or it is set to 'contiguousRB\', a UE forms the union
of the subsets indicated by each tuple
$({TRIV}_{m},{FRIV}_{m},P_{rsvp,m})$ to obtain the set
$\left\{ r_{0},r_{1},r_{2},\ldots \right\}$.

If the higher layer parameter *sl-TransmissionStructureForPSCCHandPSSCH*
is set to 'interlaceRB\', a UE forms the union of the subsets indicated
by each tuple
$\left( {TRIV}_{m},{FRIV}_{m},{FRIV}_{RBset,m},P_{rsvp,m} \right)$ to
obtain the set $\left\{ r_{0},r_{1},r_{2},\ldots \right\}$.