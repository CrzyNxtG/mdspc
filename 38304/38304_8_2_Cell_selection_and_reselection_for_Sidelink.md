## 8.2 Cell selection and reselection for Sidelink

The requirements defined in this clause for sidelink operation
(including sidelink relay operations) apply for UEs in RRC_IDLE,
RRC_INACTIVE and in RRC_CONNECTED.

When UE is interested to perform NR sidelink communication/discovery and
ranging/sidelink positioning on non-serving frequency, it may perform
measurements on that frequency or the frequencies which can provide
inter carrier NR sidelink configuration for that frequency for cell
selection and reselection purpose in accordance with TS 38.133\[8\].
When UE is interested to perform V2X sidelink communication on
non-serving frequency, it may perform measurements on that frequency or
the frequencies which can provide inter carrier V2X sidelink
configuration for that frequency for cell selection and intra-frequency
reselection purpose in accordance with TS 38.133\[8\].

If the UE detects at least one cell on the frequency which UE is
configured to perform NR sidelink communication/discovery and
ranging/sidelink positioning on fulfilling the S criterion in accordance
with clause 8.2.1, it shall consider itself to be in-coverage for NR
sidelink communication/discovery and ranging/sidelink positioning on
that frequency. If the UE cannot detect any cell on that frequency
meeting the S criterion, it shall consider itself to be out-of-coverage
for NR sidelink communication/discovery and ranging/sidelink positioning
on that frequency.

If the UE detects at least one cell on the frequency which UE is
configured to perform V2X sidelink communication on fulfilling the S
criterion in accordance with clause 8.2.1, it shall consider itself to
be in-coverage for V2X sidelink communication on that frequency. If the
UE cannot detect any cell on that frequency meeting the S criterion, it
shall consider itself to be out-of-coverage for V2X sidelink
communication on that frequency.

If the UE has selected a cell on a non-serving frequency for V2X
sidelink communication, it shall perform additional intra-frequency
reselection process to select a better cell for sidelink operation on
that frequency in accordance with clause 8.2.1.

If the UE has selected a cell on a non-serving frequency for NR sidelink
communication/discovery, it shall perform additional reselection process
to select a better cell for sidelink operation in accordance with clause
8.2.1.

If the UE has selected a cell on a non-serving frequency for
Ranging/Sidelink Positioning, it shall perform additional reselection
process to select a better cell for sidelink operation in accordance
with clause 8.2.1.