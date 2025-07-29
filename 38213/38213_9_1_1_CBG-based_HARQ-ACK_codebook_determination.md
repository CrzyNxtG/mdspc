### 9.1.1 CBG-based HARQ-ACK codebook determination

If a UE is provided *PDSCH-CodeBlockGroupTransmission* for a serving
cell, the UE receives a PDSCH scheduled by DCI format 1_1, that includes
code block groups (CBGs) of a transport block. The UE is also provided
*maxCodeBlockGroupsPerTransportBlock* indicating a maximum number
$N_{HARQ - ACK}^{CBG/TB,\max}$ of CBGs for generating respective
HARQ-ACK information bits for a transport block reception for the
serving cell.

For a number of $C$ code blocks (CBs) in a transport block, the UE
determines a number of CBGs $M$ according to clause 5.1.7.1 of \[6, TS
38.214\] and determines a number of HARQ-ACK bits for the transport
block as $N_{HARQ - ACK}^{CBG/TB} = M$.

The UE generates an ACK for the HARQ-ACK information bit of a CBG if the
UE correctly received all code blocks of the CBG and generates a NACK
for the HARQ-ACK information bit of a CBG if the UE incorrectly received
at least one code block of the CBG. If the UE receives two transport
blocks, the UE concatenates the HARQ-ACK information bits for CBGs of
the second transport block after the HARQ-ACK information bits for CBGs
of the first transport block.

The HARQ-ACK codebook includes the $N_{HARQ - ACK}^{CBG/TB,\max}$
HARQ-ACK information bits in ascending order of CBG index and, if
${N_{HARQ - ACK}^{CBG/TB} < N}_{HARQ - ACK}^{CBG/TB,\max}$ for a
transport block, the UE generates a NACK value for the last
$N_{HARQ - ACK}^{CBG/TB,\max} - N_{HARQ - ACK}^{CBG/TB}$ HARQ-ACK
information bits for the transport block in the HARQ-ACK codebook.

If the UE generates a HARQ-ACK codebook in response to a retransmission
of a transport block, corresponding to a same HARQ process as a previous
transmission of the transport block, the UE generates an ACK for each
CBG that the UE correctly decoded in a previous transmission of the
transport block.

If a UE correctly detects each of the $N_{HARQ - ACK}^{CBG/TB}$ CBGs and
does not correctly detect the transport block for the
$N_{HARQ - ACK}^{CBG/TB}$ CBGs, the UE generates a NACK value for each
of the $N_{HARQ - ACK}^{CBG/TB}$ CBGs.