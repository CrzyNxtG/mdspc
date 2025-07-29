### 6.2.1 Services and Functions

The main services and functions of the MAC sublayer include:

\- Mapping between logical channels and transport channels;

\- Multiplexing/demultiplexing of MAC SDUs belonging to one or different
logical channels into/from transport blocks (TB) delivered to/from the
physical layer on transport channels;

\- Scheduling information reporting;

\- Error correction through HARQ (one HARQ entity per cell in case of
CA);

\- Priority handling between UEs by means of dynamic scheduling;

\- Priority handling between logical channels of one UE by means of
logical channel prioritisation;

\- Priority handling between overlapping resources of one UE;

\- Padding.

A single MAC entity can support multiple numerologies, transmission
timings and cells. Mapping restrictions in logical channel
prioritisation control which numerology(ies), cell(s), and transmission
timing(s) a logical channel can use (see clause 16.1.2).