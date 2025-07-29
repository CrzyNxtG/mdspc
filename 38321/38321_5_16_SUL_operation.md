## 5.16 SUL operation

The Supplementary UL (SUL) carrier can be configured as a complement to
the normal UL (NUL) carrier. Switching between the NUL carrier and the
SUL carrier means that the UL transmissions move from one carrier to the
other carrier, which is done by:

\- an indication in DCI;

\- the Random Access procedure as specified in clause 5.1.1;

\- the SDT procedure as specified in clause 5.27.

If the MAC entity receives a UL grant indicating an SUL switch while a
Random Access procedure is ongoing, the MAC entity shall ignore the UL
grant.

The Serving Cell configured with *supplementaryUplink* belongs to a
single TAG.