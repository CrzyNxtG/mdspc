### 5.14.2 Configuration of UDC

The PDCP entities associated with DRBs can be configured by upper
layers, see TS 38.331 \[3\], to use UDC. If UDC is configured, the UE
shall apply UDC compression function (details see Annex B) to process
the received PDCP SDU from upper layers corresponding to the configured
DRB. The size of compression buffer is configured by upper layers via
*bufferSize*. If pre-defined dictionary is configured by upper layers,
the UE shall first set the compression buffer to all zeros and then
prefill the configured pre-defined dictionary in the compression buffer
upon configuration of UDC. If pre-defined dictionary is not configured
by upper layers, UE shall set the compression buffer to all zeros.