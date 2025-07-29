### 8.1.6 Sidelink congestion control in sidelink resource allocation mode 2

If a UE is configured with higher layer parameter *sl-CR-Limit* and
transmits PSSCH in slot *n*, the UE shall ensure the following limits
for any priority value k;

$\sum_{i \geq k}^{}{CR(i)} \leq CR_{Limit}(k)$

where $CR(i)$ is the CR evaluated in slot *n*-*N* for the PSSCH
transmissions with \'*Priority*\' field in the SCI set to *i*, and
$CR_{Limit}(k)$ corresponds to the high layer parameter *sl-CR-Limit*
that is associated with the priority value *k* and the CBR range which
includes the CBR measured in slot *n*-*N*, where *N* is the congestion
control processing time.

The congestion control processing time *N* is based on µ of Table
8.1.6-1 and Table 8.1.6-2 for UE processing capability 1 and 2
respectively, where µ corresponds to the subcarrier spacing of the
sidelink channel with which the PSSCH is to be transmitted. A UE shall
only apply a single processing time capability in sidelink congestion
control.

Table 8.1.6-1: Congestion control processing time for processing timing
capability 1

  ------------------------------------------------------------------------
   **µ**           Congestion control processing time N \[slots\]
  ------- ----------------------------------------------------------------
     0                                   2

     1                                   2

     2                                   4

     3                                   8
  ------------------------------------------------------------------------

Table 8.1.6-2: Congestion control processing time for processing timing
capability 2

  ------------------------------------------------------------------------
   **µ**           Congestion control processing time N \[slots\]
  ------- ----------------------------------------------------------------
     0                                   2

     1                                   4

     2                                   8

     3                                   16
  ------------------------------------------------------------------------

It is up to UE implementation how to meet the above limits, including
dropping the transmissions in slot *n*.