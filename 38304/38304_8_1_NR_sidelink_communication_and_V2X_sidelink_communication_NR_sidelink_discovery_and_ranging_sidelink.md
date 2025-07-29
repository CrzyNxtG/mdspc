## 8.1 NR sidelink communication, and V2X sidelink communication, NR sidelink discovery, and ranging/ sidelink positioning

The UE may transmit or receive NR sidelink communication/discovery if it
fulfils the condition(s) defined in TS 38.331 \[3\], clause 5.8.2. When
UE is in-coverage for sidelink operation as defined in clause 8.2, the
UE may perform NR sidelink communication/discovery according to *SIB12,*
and when out-of-coverage for sidelink, the UE may perform NR sidelink
communication/discovery according to *SL-PreconfigurationNR* or
according to *SIB12* of the cell on the frequency which provides
inter-carrier NR sidelink configuration, or according to *SIB12*
received from the connected L2 U2N Relay UE as specified in TS 38.331
\[3\]. The UE shall not perform NR sidelink communication/discovery
according to *SL-PreconfigurationNR* if the UE detects a cell providing
NR sidelink configuration or inter-carrier NR sidelink configuration for
the frequency UE is interested to perform NR sidelink
communication/discovery on, or if the UE is a L2 U2N Remote UE and has
received *SIB12* from the connected L2 U2N Relay UE.

The UE may transmit or receive V2X sidelink communication if it fulfills
the condition(s) defined in TS 36.331\[6\], clause 5.10.1d. When UE is
in-coverage for sidelink operation as defined in clause 8.2, the UE may
perform V2X sidelink communication according to *SIB13/ SIB14* of the
cell on an NR frequency.

The UE may transmit or receive SL-PRS for ranging/sidelink positioning
if it fulfils the conditions defined in TS 38.331 \[3\].

The U2N Remote UE, the U2N Relay UE, the U2U Remote UE, or the U2U Relay
UE may transmit NR sidelink relay discovery (i.e., as specified in TS
23.304 \[22\]) if it fulfills the condition(s) defined in TS 38.331
\[3\].

For NR sidelink broadcast and groupcast, the UE may obtain SL DRX
configuration from *SIB12* (for in-coverage UE, as defined in clause
8.2, in RRC_IDLE and RRC_INACTIVE state; or for out-of-coverage UE, as
defined in clause 8.2, on the frequency which the UE is configured to
perform NR sidelink communication/discovery and which is included in
*sl-FreqInfoList*/*sl-FreqInfoListSizeExt* in *SIB12*) or
*SL-PreconfigurationNR* (for out-of-coverage UE, as defined in clause
8.2, on the frequency which the UE is configured to perform NR sidelink
communication/discovery and which is not included in
*sl-FreqInfoList*/*sl-FreqInfoListSizeExt* in *SIB12*), if *SIB12* is
available.

For inter-UE coordination (IUC) information configuration, the UE may
obtain it from *SIB12* (for in-coverage UE, as defined in clause 8.2, in
RRC_IDLE and RRC_INACTIVE state; or for out-of-coverage UE, as defined
in clause 8.2, on the frequency which UE is configured to perform NR
sidelink communication and which is included in
*sl-FreqInfoList*/*sl-FreqInfoListSizeExt* in *SIB12*) or
*SL-PreconfigurationNR* (for out-of-coverage UE, as defined in clause
8.2, on the frequency which UE is configured to perform NR sidelink
communication and which is not included in
*sl-FreqInfoList*/*sl-FreqInfoListSizeExt* in *SIB12*).

For ranging/sidelink positioning, the UE may obtain the configuration
from *SIB12* or *SIB23* (for in-coverage UE, as defined in clause 8.2,
in RRC_IDLE and RRC_INACTIVE state) or *SL-PreconfigurationNR* (for
out-of-coverage UE, as defined in clause 8.2).