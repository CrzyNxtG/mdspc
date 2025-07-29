### 8.2.4 SL PRS transmission procedure

The following parameters for SL PRS transmission are associated with
each SL PRS resource:

\- SL PRS resource ID provided by *sl-PRS-ResourceID* indicates an
identity of a SL PRS resource. The SL PRS resource is identified by the
SL PRS resource ID that is unique within a slot of a dedicated SL PRS
resource pool. For a shared SL PRS resource pool, a SL PRS resource is
uniquely identified by a combination of the SL PRS resource ID, SL PRS
frequency domain allocation within a slot indicated by "frequency
resource assignment" field in the associated SCI format 1-A, and a
starting symbol within the slot as determined by clause 8.2.4.1.1.

\- *sl-CombSize* and *sl-PRS-comb-offset* indicates a comb offset and a
comb size of the SL PRS resource in a dedicated SL PRS resource pool.
*sl-PRS-CombSizeN-AndReOffset* indicates a comb offset and a comb size
of the SL PRS resource in a shared SL PRS resource pool.

\- *sl-PRS-starting-symbol* and *sl-NumberOfSymbols* indicates the
starting symbol index and the number of symbols of the SL PRS resource
within a slot in a dedicated SL PRS resource pool. *mNumberOfSymbols*
indicates the number of symbols of the SL PRS resource within a slot in
a shared SL PRS resource pool.

For a dedicated SL PRS resource pool, SL PRS resources for a same
$\left\{ L_{SL - PRS},K_{comb}^{SL - PRS} \right\}$ combination of
number of SL PRS symbols $L_{SL - PRS}$ and comb size
$K_{comb}^{SL - PRS}\ $can be mapped to a set of consecutive symbols in
a slot. SL PRS resources for different
$\left\{ L_{SL - PRS},K_{comb}^{SL - PRS} \right\}$ combinations shall
be mapped to non-overlapping sets of consecutive symbols in a slot. Up
to four non-overlapping sets of consecutive symbols within a slot can be
used to map SL PRS resources for same or different
$\left\{ L_{SL - PRS},K_{comb}^{SL - PRS} \right\}$ combinations, where
the case of four non-overlapping sets of consecutive symbols only
applies when $K_{comb}^{SL - PRS} = 2$ for all the
$\left\{ L_{SL - PRS},K_{comb}^{SL - PRS} \right\}$ combinations.

In the case of dedicated SL PRS resource pool, that PSCCH carries the
SCI format 1-B associated with the SL PRS transmission.

The UE may report the association information between the already
transmitted SL PRSs of SL PRS resources and UE Tx ARP ID. The
association information includes ARP ID(s) indicated by
*sl-POS-ARP-ID-Tx*, SL PRS transmission timestamp(s) indicated by
*sl-TimeStamp*, and optional SL PRS resource ID(s) indicated by
*sl-PRS-ResourceID*.