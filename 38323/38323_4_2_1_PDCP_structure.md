### 4.2.1 PDCP structure

Figure 4.2.1-1 represents one possible structure for the PDCP sublayer
for non-relay scenario. Figure 4.2.1-2 represents one possible structure
for the PDCP sublayer used in L2 U2N relay case, L2 U2U relay case, and
for the indirect path in the case of multi-path with SL indirect path.
Figure 4.2.1-3 represents one possible structure for the PDCP sublayer
used for the indirect path in the case of multi-path with N3C indirect
path. These structures should not restrict implementation. The figures
are based on the radio interface protocol architecture defined in TS
38.300 \[2\].

NOTE: The structure and interface of non-3GPP connection for the case of
multi-path with N3C indirect path is out of the scope of this
specification.

![](media/image3.emf)

Figure 4.2.1-1: PDCP layer, structure view (normal)

![](media/image4.emf)

Figure 4.2.1-2: PDCP layer, structure view (L2 U2N relay), L2 U2U relay
and SL indirect path in multi-path

![](media/image5.emf)

Figure 4.2.1-3: PDCP layer, structure view (N3C indirect path in
multi-path)

The PDCP sublayer is configured by upper layers TS 38.331 \[3\]. The
PDCP sublayer is used for RBs mapped on DCCH, DTCH, MTCH, SCCH, and STCH
type of logical channels. The PDCP sublayer is not used for any other
type of logical channels.

Each RB (except for SRB0 for Uu interface) is associated with one PDCP
entity. Each PDCP entity is associated with one, two, three, four, six,
or eight RLC entities depending on the RB characteristic (e.g.
uni-directional/bi-directional or split/non-split) or RLC mode:

\- For split bearers, each PDCP entity is associated with two UM RLC
entities (for same direction), four UM RLC entities (two for each
direction), or two AM RLC entities;

\- For RBs configured with PDCP duplication, each PDCP entity is
associated with N UM RLC entities (for same direction), 2 × N UM RLC
entities (N for each direction), or N AM RLC entities, where 2 \<= N \<=
4;

\- For DAPS bearers, each PDCP entity is associated with two UM RLC
entities (for same direction, one for source and one for target cell),
four UM RLC entities (two for each direction on source cell and target
cell), or two AM RLC entities (one for source cell and one for target
cell);

\- For UM MRBs, each PDCP entity is associated with one UM RLC entity
(for MTCH or for downlink DTCH), two UM RLC entities (one for MTCH and
one for downlink DTCH, or one for downlink DTCH and one for uplink
DTCH), or three UM RLC entities (one for MTCH, one for downlink DTCH,
and one for uplink DTCH);

\- For AM MRBs, each PDCP entity is associated with one AM RLC entity
(for downlink DTCH and uplink DTCH), or one UM RLC entity (for MTCH) and
one AM RLC entity (for downlink DTCH and uplink DTCH);

\- For MP split bearers with SL indirect path, each PDCP entity is
associated with one or more Uu RLC entities and one SRAP entity;

\- For MP split bearers with N3C indirect path, each PDCP entity is
associated with one or more Uu RLC entities and the N3C;

\- Otherwise, each PDCP entity is associated with one UM RLC entity, two
UM RLC entities (one for each direction), or one AM RLC entity.

For the case of L2 U2N relay, L2 U2U relay and SL indirect path of
multi-path, all PDCP entities are associated with one SRAP entity. For
the case of N3C indirect path for multi-path, all PDCP entities of the
MP remote UE are associated with the N3C.