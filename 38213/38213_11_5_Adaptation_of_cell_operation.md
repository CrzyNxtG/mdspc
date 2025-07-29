## 11.5 Adaptation of cell operation

A UE configured for operation on a serving cell according to one or both
of a cell DTX operation and a cell DRX operation by
c*ellDTRX-DCI-Config* for the serving cell \[11, TS 38.321\], can be
additionally provided by *dci-Format2-9* a Type3-PDCCH CSS set to
monitor PDCCH for detection of DCI format 2_9 as described in clause
10.1 during Active Time \[11, TS 38.321\], and a location in DCI format
2_9 by *positionInDCI-cellDTRX* of a cell DTX/DRX indication field for
the serving cell and/or a NES-mode indication field for the PCell

\- if the UE is configured with both cell DTX operation and cell DRX
operation for the serving cell and if *cellDTX-DRX-L1activation* is
provided, the cell DTX/DRX indication field includes two bits where the
first bit indicates the cell DTX operation and the second bit indicates
the cell DRX operation

\- if the UE is configured with only one of the cell DTX operation and
cell DRX operation for the serving cell and if
*cellDTX-DRX-L1activation* is provided, the cell DTX/DRX indication
field includes one bit indicating one of the cell DTX operation and cell
DRX operation, respectively, for the serving cell

\- a \'0\' value for a bit of the cell DTX/DRX indication field
indicates deactivation of cell DTX or of cell DRX

\- a \'1\' value for a bit of the cell DTX/DRX indication field
indicates activation of cell DTX or of cell DRX

\- if the serving cell is configured with a SUL carrier, the cell
DTX/DRX indication field indication for activation or deactivation of
cell DRX applies to both the UL carrier and the SUL carrier

\- if *nesEvent* is configured, the NES-mode indication field includes
one bit indicating NES-specific CHO execution condition, as described in
\[12, TS 38.331\]

\- a \'0\' value for the NES-mode indication field indicates
NES-specific CHO execution condition is disabled

\- a \'1\' value for the NES-mode indication field, indicates
NES-specific CHO execution condition is enabled

A UE does not expect to monitor PDCCH for detection of DCI format 2_9 on
more than one serving cells of one cell group.

When a UE not provided with *cellSpecificKoffset* receives in slot $m$
on the active DL BWP of a first serving cell a PDCCH providing DCI
format 2_9 that indicates a change in activation or deactivation of a
current cell DTX operation or cell DRX operation for a second serving
cell, the UE operates on the second serving cell according to the
indicated cell DTX operation or cell DRX operation starting from the
first slot on the active DL BWP or on the active UL BWP of the second
serving cell, respectively, that does not begin before the beginning of
the slot $m + d$ on the active DL BWP of the first serving cell where
$d$ is a number of slots for the SCS of the active DL BWP of the first
serving cell in Table 11.5-1.

When a UE provided with *cellSpecificKoffset* receives in slot $m$ on
the active DL BWP of a serving cell a PDCCH providing DCI format 2_9
that indicates a change in activation or deactivation of a current cell
DTX operation for the serving cell, the UE operates on the serving cell
according to the indicated cell DTX operation starting from the first
slot on the active DL BWP that does not begin before the beginning of
the slot $m + d$ on the active DL BWP of the serving cell, where $d$ is
a number of slots for the SCS of the active DL BWP of the serving cell
in Table 11.5-1.

When a UE provided with *cellSpecificKoffset* receives in slot $m$ on
the active DL BWP of a serving cell a PDCCH providing DCI format 2_9
that indicates a change in activation or deactivation of a current cell
DRX operation for the serving cell, the UE operates on the serving cell
according to the indicated cell DRX operation starting from slot
$\left\lfloor (m + d) \cdot \frac{2^{\mu_{UL}}}{2^{\mu_{DL}}} \right\rfloor + K_{cell,offset} \cdot 2^{\mu_{UL}}$
on the active UL BWP where $d$ is a number of slots for the SCS of the
active DL BWP of the cell in Table 11.5-1, $K_{cell,offset}\ $is the
*cellSpecificKoffset*, $\mu_{DL}$ *and* $\mu_{UL}$are the SCS
configurations of the active DL BWP and the active UL BWP of the cell,
respectively.

Table 11.5-1: Minimum time gap value $\mathbf{d}$

  -----------------------------------------------------------------------
         **SCS (kHz)**             **[Number of slots]{.underline}**
  ---------------------------- ------------------------------------------
               15                                  3

               30                                  6

               60                                  12

              120                                  24

              480                                  96

              960                                 192
  -----------------------------------------------------------------------