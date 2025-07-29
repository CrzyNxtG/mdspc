### 5.8.7 Sidelink communication reception

A UE capable of NR sidelink communication that is configured by upper
layers to receive NR sidelink communication shall:

1\> if the conditions for NR sidelink communication operation as defined
in 5.8.2 are met:

2\> if the frequency used for NR sidelink communication is included in
*sl-FreqInfoToAddModList*/*sl-FreqInfoToAddModListExt* in
*RRCReconfiguration* message or
*sl-FreqInfoList*/*sl-FreqInfoListSizeExt* included in *SIB12*:

3\> if the UE is configured with *sl-RxPool* included in
*RRCReconfiguration* message with *reconfigurationWithSync* (i.e.
handover):

4\> configure lower layers to monitor sidelink control information and
the corresponding data using the pool(s) of resources indicated by
*sl-RxPool*;

3\> else if the cell chosen for NR sidelink communication provides
*SIB12*:

4\> configure lower layers to monitor sidelink control information and
the corresponding data using the pool(s) of resources indicated by
*sl-RxPool in SIB12*;

2\> else:

3\> configure lower layers to monitor sidelink control information and
the corresponding data using the pool(s) of resources that were
preconfigured by *sl-RxPool* in *SL-PreconfigurationNR*, as defined in
clause 9.3.