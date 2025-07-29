## 7.3 Sounding reference signals

For SRS,

\- if a UE is provided *nrofSRS-Ports-n8* = \'ports8tdm\' for an SRS
resource with 8 ports in an SRS resource set with usage \'codebook\' or
\'antennaSwitching\', the UE splits a linear value
${\widehat{P}}_{\text{SRS},b,f,c}(i,q_{s},l)$ of the transmit power
$P_{\text{SRS},b,f,c}(i,q_{s},l)$ on active UL BWP $b$ of carrier $f$ of
serving cell $c$ equally across the SRS ports of an SRS resource of an
SRS resource set on each symbol for SRS transmission.

\- else, a UE splits a linear value
${\widehat{P}}_{\text{SRS},b,f,c}(i,q_{s},l)$ of the transmit power
$P_{\text{SRS},b,f,c}(i,q_{s},l)$ on active UL BWP $b$ of carrier $f$ of
serving cell $c$ equally across the SRS ports of each SRS resource of an
SRS resource set in a symbol for SRS transmission.