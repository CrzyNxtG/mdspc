## 8.1 Sidelink broadcast channel

The processing for SL-BCH transport channel follows the BCH according to
clause 7.1, with the following changes:

\- In Clause 7.1, \'maximum of one transport block every 80ms\' is
replaced with \'maximum of one transport block\'.

\- Clause 7.1.1 for PBCH payload generation is not performed.

\- Clause 7.1.2 for scrambling is not performed.

\- In clause 7.1.5, the rate matching output sequence length E = 1386
when higher layer parameter *cyclicPrefix* is configured, otherwise, E =
1782.