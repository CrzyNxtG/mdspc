## 9.1 PRS reception procedure for RTT-based propagation delay compensation

The DL PRS resource set for RTT-based propagation delay compensation
consists of K≥1 DL PRS resource(s) where each has an associated spatial
transmission filter. Each DL PRS resource is configured via higher layer
parameters *NR-DL-PRS-Resource* and is uniquely defined by
*nr-DL-PRS-ResourceID*. The subcarrier spacing and the cyclic prefix of
the DL PRS resources are defined by the subcarrier spacing and the
cyclic prefix of the DL active bandwidth part of the serving cell.

The DL PRS resource set for RTT-based propagation delay compensation is
configured by *nr-DL-PRS-PDC-ResourceSet*, consists of one or more DL
PRS resource(s) and it is defined by:

*- periodicityAndOffset* defines the DL PRS resource periodicity and
takes values
$T_{\text{per}}^{\text{PRS}} \in 2^{\mu}\left\{ 4,\ 5,\ 8,\ 10,\ 16,\ 20,\ 32,\ 40,\ 64,\ 80,\ 160,\ 320,\ 640,\ 1280,\ 2560,\ 5120,\ 10240 \right\}\ $slots,
where $\mu = 0,\ 1,\ 2,\ 3\ $for 15, 30, 60 and 120 kHz subcarrier
spacing respectively and the slot offset for DL PRS resource set with
respect to SFN0 slot 0. All the DL PRS resources are configured with the
same DL PRS resource periodicity.

*- repetitionFactor* defines how many times each DL-PRS resource is
repeated for a single instance of the DL-PRS resource set and takes
values
$T_{\text{rep}}^{\text{PRS}} \in \left\{ 1,\ 2,\ 4,\ 6,\ 8,\ 16,\ 32 \right\}$.
All the DL PRS resources within the resource set have the same resource
repetition factor.

*- timeGap* defines the offset in number of slots between two repeated
instances of a DL PRS resource with the same *nr-DL-PRS-ResourceID*
within a single instance of the DL PRS resource set. The UE only expects
to be configured with *timeGap* if *repetitionFactor* is configured with
value greater than 1. The time duration spanned by one instance of a
*nr-DL-PRS-ResourceSet* is not expected to exceed the configured value
of DL PRS periodicity. All the DL PRS resources within the resource set
have the same value of *timeGap.*

*- resourceList* determines the DL PRS resources that are contained
within the DL PRS resource set.

*- dl-PRS-ResourceBandwidth* defines the number of resource blocks
configured for DL PRS transmission. The parameter has a granularity of 4
PRBs with a minimum of 24 PRBs and a maximum of 272 PRBs. All the DL PRS
resources within the resource set have the same value of
*dl-PRS-ResourceBandwidth.*

*- dl-PRS-StartPRB* defines the starting PRB index of the DL PRS
resource with respect to subcarrier 0 in common resource block 0. The
starting PRB index has a granularity of one PRB with a minimum value of
0 and a maximum value of 2176 PRBs. All the DL PRS resources within the
resource set have the same value of *dl-PRS-StartPRB.*

*- numSymbols* defines the number of symbols of the DL PRS resource
within a slot where the allowable values are given in Clause 7.4.1.7.3
of \[4, TS 38.211\]. All the DL PRS resources within the resource set
have the same value of *numSymbols.*

A DL PRS resource is defined by:

*- nr-DL-PRS-ResourceID* determines the DL PRS resource configuration
identity. All DL PRS resource IDs are locally defined within the DL PRS
resource set.

*- dl-PRS-SequenceID* is used to initialize c~init~ value used in pseudo
random generator as described in Clause 7.4.1.7.2 of \[4, TS 38.211\]
for generation of DL PRS sequence for a given DL PRS resource.

*- dl-PRS-CombSizeN-AndReOffset* defines the comb size of a DL PRS
resource, where the allowable values are given in Clause 7.4.1.7.3 of
\[4, TS 38.211\], and the starting RE offset of the first symbol within
a DL PRS resource in frequency. The UE may expect the same comb size to
be configured for all DL PRS resources of the PRS resource set. The
relative RE offsets of the remaining symbols within a DL PRS resource
are defined based on the initial offset and the rule described in Clause
7.4.1.7.3 of \[4, TS 38.211\].

*- dl-PRS-ResourceSlotOffset* determines the starting slot of the DL PRS
resource with respect to corresponding DL PRS resource set slot offset.

*- dl-PRS-ResourceSymbolOffset* determines the starting symbol of a slot
configured with the DL PRS resource.

*- dl-PRS-QCL-Info* defines any quasi co-location information of the DL
PRS resource with other reference signals. The DL PRS may be configured
with QCL \'typeD\' with a DL PRS in the same PRS resource set, or with
*rs-Type* set to \'typeC\', \'typeD\', or \'typeC-plus-typeD\' with a
SS/PBCH Block from the serving cell.

The UE assumes constant EPRE is used for all REs of a given DL PRS
resource.

The UE assumes that the DL PRS from the serving cell is not mapped to
any symbol that contains SS/PBCH block from the serving cell.

The UE does not expect to be scheduled or configured for reception of
any downlink channel or any other downlink signal(s) in the OFDM
symbol(s) and PRBs of the DL PRS resource for RTT-based propagation
delay compensation to be received.

The UE is expected to receive the DL PRS for RTT-based propagation delay
compensation only in RRC_CONNECTED state and within the DL active
bandwidth part of the serving cell.