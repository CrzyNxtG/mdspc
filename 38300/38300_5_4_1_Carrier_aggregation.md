### 5.4.1 Carrier aggregation

In Carrier Aggregation (CA), two or more Component Carriers (CCs) are
aggregated. A UE may simultaneously receive or transmit on one or
multiple CCs depending on its capabilities:

\- A UE with single timing advance capability for CA can simultaneously
receive and/or transmit on multiple CCs corresponding to multiple
serving cells sharing the same timing advance (multiple serving cells
grouped in one TAG);

\- A UE with multiple timing advance capability for CA can
simultaneously receive and/or transmit on multiple CCs corresponding to
multiple serving cells with different timing advances (multiple serving
cells grouped in multiple TAGs). NG-RAN ensures that each TAG contains
at least one serving cell;

\- A non-CA capable UE can receive on a single CC and transmit on a
single CC corresponding to one serving cell only (one serving cell in
one TAG).

CA is supported for both contiguous and non-contiguous CCs. When CA is
deployed frame timing and SFN are aligned across cells that can be
aggregated, or an offset in multiples of slots between the SpCell and an
SCell is configured to the UE.