# 11 UE Power Saving

The PDCCH monitoring activity of the UE in RRC connected mode is
governed by DRX, BA, DCP and cell DTX (see clause 15.4.2.3).

When DRX is configured, the UE does not have to continuously monitor
PDCCH. DRX is characterized by the following:

\- **on-duration**: duration that the UE waits for, after waking up, to
receive PDCCHs. If the UE successfully decodes a PDCCH, the UE stays
awake and starts the inactivity timer;

\- **inactivity-timer**: duration that the UE waits to successfully
decode a PDCCH, from the last successful decoding of a PDCCH, failing
which it can go back to sleep. The UE shall restart the inactivity timer
following a single successful decoding of a PDCCH for a first
transmission only (i.e. not for retransmissions);

\- **retransmission-timer**: duration until a retransmission can be
expected;

\- **cycle**: specifies the periodic repetition of the on-duration
followed by a possible period of inactivity (see figure 11-1 below);

**- active-time**: total duration that the UE monitors PDCCH. This
includes the \"on-duration\" of the DRX cycle, the time UE is performing
continuous reception while the inactivity timer has not expired, and the
time when the UE is performing continuous reception while waiting for a
retransmission opportunity.

![](media/image59.emf)

Figure 11-1: DRX Cycle

A SL UE can be configured with DRX, in which case, PDCCH providing SL
grants can be send to the UE only during its active time.

When BA is configured, the UE only has to monitor PDCCH on the one
active BWP i.e. it does not have to monitor PDCCH on the entire DL
frequency of the cell. A BWP inactivity timer (independent from the DRX
inactivity-timer described above) is used to switch the active BWP to
the default one: the timer is restarted upon successful PDCCH decoding
and the switch to the default BWP takes place when it expires.

In addition, the UE may be indicated, when configured accordingly,
whether it is required to monitor or not the PDCCH during the next
occurrence of the on-duration by a DCP monitored on the active BWP. If
the UE does not detect a DCP on the active BWP, it does not monitor the
PDCCH during the next occurrence of the on-duration, unless it is
explicitly configured to do so in that case.

A UE can only be configured to monitor DCP when connected mode DRX is
configured, and at occasion(s) at a configured offset before the
on-duration. If short DRX cycle is configured, DCP is not applicable
when short DRX cycle is used. More than one monitoring occasion can be
configured before the on-duration. The UE does not monitor DCP on
occasions occurring during active-time, measurement gaps, BWP switching,
or when it monitors response for a CFRA preamble transmission for beam
failure recovery (see clause 9.2.6), in which case it monitors the PDCCH
during the next on-duration. If no DCP is configured in the active BWP,
UE follows normal DRX operation.

When CA is configured, DCP is only configured on the PCell and/or
PSCell.

One DCP can be configured to control PDCCH monitoring during on-duration
for one or more UEs independently.

Power saving in RRC_IDLE and RRC_INACTIVE can also be achieved by UE
relaxing neighbour cells RRM measurements when it meets the criteria
determining it is in low mobility and/or not at cell edge. When UE is
configured with both high speed measurements and RRM measurement
relaxation as specified in TS 38.331 \[12\], it is up to UE
implementation whether to apply the FR1 high speed RRM requirements or
the relaxed RRM requirements when the low mobility related criterion is
configured and fulfilled as specified in TS 38.133 \[13\].

UE power saving may be enabled by adapting the DL maximum number of MIMO
layers by BWP switching.

Power saving is also enabled during active-time via cross-slot
scheduling, which facilitates UE to achieve power saving with the
assumption that it won\'t be scheduled to receive PDSCH, triggered to
receive A-CSI or transmit a PUSCH scheduled by the PDCCH until the
minimum scheduling offsets K0 and K2. Dynamic adaptation of the minimum
scheduling offsets K0 and K2 is controlled by PDCCH.

Serving Cells of a MAC entity may be configured by RRC in two DRX groups
with separate DRX parameters. When RRC does not configure a secondary
DRX group, there is only one DRX group and all Serving Cells belong to
that one DRX group. When two DRX groups are configured, each Serving
Cell is uniquely assigned to either of the two groups. The DRX
parameters that are separately configured for each DRX group are
on-duration and inactivity-timer.

UE power saving in RRC_IDLE/RRC_INACTIVE may be achieved by providing
the configuration for TRS with CSI-RS for tracking in TRS occasions. The
TRS in TRS occasions may allow UEs in RRC_IDLE/RRC_INACTIVE to sleep
longer before waking-up for its paging occasion. The TRS occasions
configuration is provided in either SIB17 or SIB17bis. The availability
of TRS in the TRS occasions is indicated by L1 availability indication.
These TRSs may also be used by the UEs configured with eDRX.

UE power saving may be achieved by UE relaxing measurements for RLM/BFD.
When configured, UE determines whether it is in low mobility state
and/or whether its serving cell radio link quality is better than a
threshold. The configuration for low mobility and good serving cell
quality criterion is provided through dedicated RRC signalling.

RLM and BFD relaxation may be enabled/disabled separately through RRC
Configuration. Additionally, RLM relaxation may be enabled/disabled on
per Cell Group basis while BFD relaxation may be enabled/disabled on per
serving cell basis.

The UE is only allowed to perform RLM and/or BFD relaxation when relaxed
measurement criterion for low mobility and/or for good serving cell
quality is met. If configured to do so, the UE shall trigger reporting
of its RLM and/or BFD relaxation status through UE assistance
information if the UE changes its respective RLM and/or BFD relaxation
status while meeting the UE minimum requirements specified in TS 38.133
\[13\].

UE power saving may also be achieved through PDCCH monitoring adaptation
mechanisms when configured by the network, including skipping of PDCCH
monitoring and Search space set group (SSSG) switching. In this case UE
does not monitor PDCCH during the PDCCH skipping duration except for the
cases as specified in TS 38.213 \[38\], or monitors PDCCH according to
the search space sets applied in SSSG.