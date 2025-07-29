### 5.7.2 Configuration of ROHC

PDCP entities associated with DRBs and MRBs can be configured by upper
layers TS 38.331 \[3\] to use ROHC. Each PDCP entity carrying user plane
data may be configured to use ROHC. PDCP entities associated with
sidelink DRBs can be configured to use ROHC for IP SDUs. For DRBs and
MRBs other than DAPS bearers, the PDCP entity uses at most one ROHC
compressor instance and at most one ROHC decompressor instance. For DAPS
bearers, the PDCP entity uses at most one ROHC compressor instance (i.e.
use the ROHC compressor instance for source cell before uplink data
switching, and use the ROHC compressor instance for target cell after
uplink data switching) and at most two ROHC decompressor instances.