### 5.3.3 Physical uplink control channel

Physical uplink control channel (PUCCH) carries the Uplink Control
Information (UCI) from the UE to the gNB. Five formats of PUCCH exist,
depending on the duration of PUCCH and the UCI payload size:

\- Format #0: Short PUCCH of 1 or 2 symbols with small UCI payloads of
up to two bits with UE multiplexing capacity of up to 6 UEs with 1-bit
payload in the same PRB;

\- Format #1: Long PUCCH of 4-14 symbols with small UCI payloads of up
to two bits with UE multiplexing capacity of up to 84 UEs without
frequency hopping and 36 UEs with frequency hopping in the same PRB;

\- Format #2: Short PUCCH of 1 or 2 symbols with large UCI payloads of
more than two bits with no UE multiplexing capability in the same PRBs;

\- Format #3: Long PUCCH of 4-14 symbols with large UCI payloads with no
UE multiplexing capability in the same PRBs;

\- Format #4: Long PUCCH of 4-14 symbols with moderate UCI payloads with
multiplexing capacity of up to 4 UEs in the same PRBs.

The short PUCCH format of up to two UCI bits is based on sequence
selection, while the short PUCCH format of more than two UCI bits
frequency multiplexes UCI and DMRS. The long PUCCH formats
time-multiplex the UCI and DMRS. Frequency hopping is supported for long
PUCCH formats and for short PUCCH formats of duration of 2 symbols.
Short and long PUCCH formats can be repeated over multiple slots or
sub-slots, where the repetition factor is either indicated dynamically
in the DCI or semi-statically in an RRC configuration.

For operation with shared spectrum channel access in FR1, PUCCH Format
#0, #1, #2, #3 are extended to use resource in one PRB interlace (up to
two interlaces for Format #2 and Format #3) in one RB Set. PUCCH Format
#2 and #3 are enhanced to support multiplexing capacity of up to 4 UEs
in the same PRB interlace when one interlace is used.

For operation in FR2-2, PUCCH Format #0, #1, #4 are extended to use
resource in configurable number of continuous PRBs, up to 16 PRBs.

Up to two PUCCH configurations can be configured for a UE per PUCCH
group (see TS 38.331 \[12\]), where the first PUCCH configuration is
associated with a PUCCH of priority index 0 (low) and the second PUCCH
configuration is associated with a PUCCH of priority index 1 (high).

UCI multiplexing in PUCCH is supported when PUCCH transmissions of UCIs
coincide in time, and are associated with the same priority (high/low).
In addition, multiplexing of HARQ-ACK of priority index 0 (low) and UCI
of priority index 1 (high) in PUCCH of priority index 1 (high) is
supported when PUCCH transmissions of HARQ-ACK of priority index 0 and
UCI of priority index 1 (high) coincide in time.

UCI multiplexing in PUSCH is supported when UCI and PUSCH transmissions
coincide in time, either due to transmission of a UL-SCH transport block
or due to triggering of A-CSI transmission without UL-SCH transport
block, and are associated with the same priority (high/low). In
addition, HARQ-ACK multiplexing of a certain priority in PUSCH of a
different priority is supported when HARQ-ACK and PUSCH transmissions
coincide in time, either due to transmission of a UL-SCH transport block
or due to triggering of A-CSI transmission without UL-SCH transport
block:

\- UCI carrying HARQ-ACK feedback with 1 or 2 bits is multiplexed by
puncturing PUSCH;

\- In all other cases UCI is multiplexed by rate matching PUSCH.

UCI consists of the following information:

\- CSI;

\- ACK/NAK;

\- Scheduling request.

Simultaneous transmission of PUCCH and PUSCH associated with different
priorities on cells of different bands in a PUCCH group is supported,
where UCI multiplexing in the PUCCH associated with a priority in
combination of UCI multiplexing in a PUSCH associated with a different
priority is supported if the UCI multiplexed on PUSCH is of same
priority as the PUSCH.

Simultaneous transmission of PUCCH and PUSCH associated with same
priority on cells of different bands in a PUCCH group is supported (see
clause 9 of TS 38.213 \[38\]).

For operation with shared spectrum channel access, multiplexing of
CG-UCI and PUCCH carrying HARQ-ACK feedback can be configured by the
gNB. If not configured, when PUCCH overlaps with PUSCH scheduled by a
configured grant within a PUCCH group and PUCCH carries HARQ ACK
feedback, PUSCH scheduled by configured grant is skipped.

QPSK and π/2 BPSK modulation can be used for long PUCCH with more than 2
bits of information, QPSK is used for short PUCCH with more than 2 bits
of information and BPSK and QPSK modulation can be used for long PUCCH
with up to 2 information bits.

Transform precoding is applied to PUCCH Format #3 and Format #4.

Channel coding used for uplink control information is described in table
5.3.3-1.

Table 5.3.3-1: Channel coding for uplink control information

  -----------------------------------------------------------------------
  Uplink Control Information size      Channel code
  including CRC, if present            
  ------------------------------------ ----------------------------------
  1                                    Repetition code

  2                                    Simplex code

  3-11                                 Reed Muller code

  \>11                                 Polar code
  -----------------------------------------------------------------------