## 16.5 UE procedure for reporting HARQ-ACK on uplink

A UE can be provided PUCCH resources or PUSCH resources \[12, TS
38.331\] to report HARQ-ACK information that the UE generates based on
HARQ-ACK information that the UE obtains from PSFCH receptions, or from
absence of PSFCH receptions. The UE reports HARQ-ACK information on the
primary cell of the PUCCH group, as described in clause 9, of the cell
where the UE monitors PDCCH for detection of DCI format 3_0.

For SL configured grant Type 1 or Type 2 PSSCH transmissions by a UE
within a time period provided by *sl-PeriodCG*, the UE generates one
HARQ-ACK information bit in response to the PSFCH receptions to
multiplex in a PUCCH transmission occasion that is after a last time
resource, in a set of time resources.

For PSSCH transmissions scheduled by a DCI format 3_0, a UE generates
HARQ-ACK information in response to PSFCH receptions to multiplex in a
PUCCH transmission occasion that is after a last time resource in a set
of time resources provided by the DCI format 3_0.

From a number of PSFCH reception occasions, the UE generates HARQ-ACK
information to report in a PUCCH or PUSCH transmission. The UE can be
indicated by a SCI format to perform one of the following and the UE
constructs a HARQ-ACK codeword with HARQ-ACK information, when
applicable

\- for one or more PSFCH reception occasions associated with SCI format
2-A with Cast type indicator field value of \"10\"

\- generate HARQ-ACK information with same value as a value of HARQ-ACK
information the UE determines from the last PSFCH reception from the
number of PSFCH reception occasions corresponding to PSSCH transmissions
or, if the UE determines that a PSFCH is not received at the last PSFCH
reception occasion and ACK is not received in any of previous PSFCH
reception occasions, generate NACK

\- for one or more PSFCH reception occasions associated with SCI format
2-A with Cast type indicator field value of \"01\"

\- generate ACK if the UE determines ACK from at least one PSFCH
reception occasion, from the number of PSFCH reception occasions
corresponding to PSSCH transmissions, in PSFCH resources corresponding
to every identity $M_{\text{ID}}$ of the UEs that the UE expects to
receive the PSSCH, as described in clause 16.3; otherwise, generate NACK

\- for one or more PSFCH reception occasions associated with SCI format
2-B or SCI format 2-A with Cast type indicator field value of \"11\"

\- generate ACK when the UE determines absence of PSFCH reception for
the last PSFCH reception occasion from the number of PSFCH reception
occasions corresponding to PSSCH transmissions; otherwise, generate NACK

After a UE transmits PSSCHs and receives PSFCHs in corresponding PSFCH
resource occasions, the priority value of HARQ-ACK information is same
as the priority value of the PSSCH transmissions that is associated with
the PSFCH reception occasions providing the HARQ-ACK information.

The UE generates a NACK when, due to prioritization, as described in
clause 16.2.4, the UE does not receive PSFCH in any PSFCH reception
occasion associated with a PSSCH transmission in a resource provided by
a DCI format 3_0 and the UE transmitted PSSCH in the resource or, for a
configured grant, in a resource provided in a single period and for
which the UE is provided a PUCCH resource to report HARQ-ACK information
and the UE transmitted PSSCH in the resource. The priority value of the
NACK is same as the priority value of the PSSCH transmission.

The UE generates a NACK when, due to prioritization as described in
clause 16.2.4, or due to a failed channel access procedure \[15, TS
37.213\] for operation with shared spectrum channel access, the UE does
not transmit a PSSCH in any of the resources provided by a DCI format
3_0 or, for a configured grant, in any of the resources provided in a
single period and for which the UE is provided a PUCCH resource to
report HARQ-ACK information. The priority value of the NACK is same as
the priority value of the PSSCH that was not transmitted due to
prioritization or due to the failed channel access procedure.

The UE generates an ACK if the UE does not transmit a PSCCH with a SCI
format 1-A scheduling a PSSCH in any of the resources provided by a
configured grant in a single period and for which the UE is provided a
PUCCH resource to report HARQ-ACK information. The priority value of the
ACK is same as the largest priority value among the possible priority
values for the configured grant.

The UE generates an ACK if the UE does not transmit a PSCCH with a SCI
format 1-A scheduling a PSSCH in any of the resources provided by a DCI
format 3_0 and for which the UE is provided a PUCCH resource to report
HARQ-ACK information. The priority value of the ACK is same as the
largest priority value among the possible priority values for the
dynamic grant.

For reporting HARQ-ACK information on uplink corresponding to one or
multiple PSSCH transmissions with a corresponding SCI format with the
field \'HARQ feedback enabled/disabled indicator\' set to disabled, the
UE generates HARQ-ACK information with the contents instructed by higher
layer. The priority value of the HARQ-ACK information is same as the
priority value of the PSSCH transmission.

A UE does not expect to be provided PUCCH resources or PUSCH resources
to report HARQ-ACK information that start earlier than $T_{prep} =$
$(N + 1) \bullet (2048 + 144) \bullet \kappa \bullet 2^{- \mu} \bullet T_{c}$
after the end of a last symbol of a last PSFCH reception occasion if
*sl-NumPSFCH-Occasions* is not (pre-)configured, or of a last candidate
PSFCH reception occasion if *sl-NumPSFCH-Occasions* is (pre-)configured,
from a number of PSFCH reception occasions if *sl-NumPSFCH-Occasions* is
not (pre-)configured, or from a number of candidate PSFCH reception
occasions if *sl-NumPSFCH-Occasions* is (pre-)configured, that the UE
generates HARQ-ACK information to report in a PUCCH or PUSCH
transmission, where

\- $\kappa$ and $T_{c}$ are defined in \[4, TS 38.211\]

\- $\mu = min(\mu_{SL},\mu_{UL})$, where $\mu_{SL}$ is the SCS
configuration of the SL BWP and $\mu_{UL}$ is the SCS configuration of
the active UL BWP on the primary cell

\- $N$ is determined from $\mu$ according to Table 16.5-1

Table 16.5-1: Values of $\mathbf{N}$

  -----------------------------------------------------------------------
  $$\mathbf{\mu}$$                    $$\mathbf{N}$$
  ----------------------------------- -----------------------------------
  0                                   14

  1                                   18

  2                                   28

  3                                   32
  -----------------------------------------------------------------------

For DCI format 3_0, if present, the PSFCH-to-HARQ feedback timing
indicator field values map to values for a set of number of slots
provided by *sl-PSFCH-ToPUCCH* as defined in Table 16.5-2.

Table 16.5-2: Mapping of PSFCH-to-HARQ feedback timing indicator field
values to numbers of slots

+-------------+-------------+-------------+-------------------------------------------------------+
| PSFCH-to-HARQ feedback timing indicator | Number of slots                                       |
|                                         | ![](media/image193.wmf){width="0.10416666666666667in" |
|                                         | height="0.19791666666666666in"}                       |
+-------------+-------------+-------------+-------------------------------------------------------+
| 1 bit       | 2 bits      | 3 bits      |                                                       |
+-------------+-------------+-------------+-------------------------------------------------------+
| \'0\'       | \'00\'      | \'000\'     | 1^st^ value provided by *sl-PSFCH-ToPUCCH*            |
+-------------+-------------+-------------+-------------------------------------------------------+
| \'1\'       | \'01\'      | \'001\'     | 2^nd^ value provided by *sl-PSFCH-ToPUCCH*            |
+-------------+-------------+-------------+-------------------------------------------------------+
|             | \'10\'      | \'010\'     | 3^rd^ value provided by *sl-PSFCH-ToPUCCH*            |
+-------------+-------------+-------------+-------------------------------------------------------+
|             | \'11\'      | \'011\'     | 4^th^ value provided by *sl-PSFCH-ToPUCCH*            |
+-------------+-------------+-------------+-------------------------------------------------------+
|             |             | \'100\'     | 5^th^ value provided by *sl-PSFCH-ToPUCCH*            |
+-------------+-------------+-------------+-------------------------------------------------------+
|             |             | \'101\'     | 6^th^ value provided by *sl-PSFCH-ToPUCCH*            |
+-------------+-------------+-------------+-------------------------------------------------------+
|             |             | \'110\'     | 7^th^ value provided by *sl-PSFCH-ToPUCCH*            |
+-------------+-------------+-------------+-------------------------------------------------------+
|             |             | \'111\'     | 8^th^ value provided by *sl-PSFCH-ToPUCCH*            |
+-------------+-------------+-------------+-------------------------------------------------------+

With reference to slots for PUCCH transmissions and for a number of
PSFCH reception occasions if *sl-NumPSFCH-Occasions* is not
(pre-)configured, or candidate PSFCH reception occasions if
*sl-NumPSFCH-Occasions* is (pre-)configured, ending in slot $n$, the UE
provides the generated HARQ-ACK information in a PUCCH transmission
within slot $n + k$, subject to the overlapping conditions in clause
9.2.5, where $k$ is a number of slots indicated by a PSFCH-to-HARQ
feedback timing indicator field, if present, in a DCI format indicating
a slot for PUCCH transmission to report the HARQ-ACK information, or $k$
is provided by *sl-PSFCH-ToPUCCH* for a transmission scheduled by a DCI
format or for a SL configured grant type 2, or by
*sl-PSFCH-ToPUCCH-CG-Type1* for a SL configured grant type 1. $k = 0$
corresponds to a last slot for a PUCCH transmission that would overlap
with the last PSFCH reception occasion if *sl-NumPSFCH-Occasions* is not
(pre-)configured, or the last candidate PSFCH reception occasion if
*sl-NumPSFCH-Occasions* is (pre-)configured, assuming that the start of
the sidelink frame is same as the start of the downlink frame \[4, TS
38.211\].

For a PSSCH transmission by a UE that is scheduled by a DCI format, or
for a SL configured grant Type 2 PSSCH transmission activated by a DCI
format, the DCI format indicates to the UE that a PUCCH resource is not
provided when a value of the PUCCH resource indicator field is zero and
a value of PSFCH-to-HARQ feedback timing indicator field, if present, is
zero. For a SL configured grant Type 2 PSSCH transmission without a
corresponding PDCCH, the DCI format activating the SL configured grant
Type 2 indicates to the UE that a PUCCH resource is not provided when a
value of the PUCCH resource indicator field is zero and a value of
PSFCH-to-HARQ feedback timing indicator field, if present, is zero. For
a SL configured grant Type 1 PSSCH transmission, a PUCCH resource can be
provided by *sl-N1PUCCH-AN* and *sl-PSFCH-ToPUCCH-CG-Type1*. For
transmission of HARQ-ACK information corresponding only to a SL
configured grant Type 2 PSSCH transmission, including the PSSCH
transmission(s) associated with the corresponding activation DCI format
3[\_]{.underline}0, a UE can be provided a PUCCH resource by
*sl-N1PUCCH-AN-Type2*. If a PUCCH resource is not provided, the UE does
not transmit a PUCCH with generated HARQ-ACK information from PSFCH
reception occasions.

For a PUCCH transmission with HARQ-ACK information, a UE determines a
PUCCH resource after determining a set of PUCCH resources from up to
four PUCCH resource sets provided by *sl-PUCCH-Config*, for $O_{UCI}$
HARQ-ACK information bits, as described in clause 9.2.1. The PUCCH
resource determination is based on a PUCCH resource indicator field \[5,
TS 38.212\] in a last DCI format 3_0, excluding DCI format 3_0 for the
SL configured grant Type 2 activation, among the DCI formats 3_0 that
have a value of a PSFCH-to-HARQ feedback timing indicator field
indicating a same slot for the PUCCH transmission, that the UE detects
and for which the UE transmits corresponding HARQ-ACK information in the
PUCCH where, for PUCCH resource determination, detected DCI formats are
indexed in an ascending order across PDCCH monitoring occasion indexes.

The PUCCH resource indicator field values map to values of a set of
PUCCH resource indexes, as described in clause 9.2.3.

A UE transmits a PUCCH with HARQ-ACK information using PUCCH format 0 or
PUCCH format 1 or PUCCH format 2 or PUCCH format 3 or PUCCH format 4 as
described in clause 9.2.3.

A UE does not expect to multiplex HARQ-ACK information for more than one
SL configured grants in a same PUCCH.

A priority value of a PUCCH transmission with one or more sidelink
HARQ-ACK information bits is the smallest priority value for the one or
more HARQ-ACK information bits.

In the following, the CRC for DCI format 3_0 is scrambled with a SL-RNTI
or a SL-CS-RNTI.