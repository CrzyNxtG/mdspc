## 5.5 Data recovery

For AM DRBs, when upper layers request a PDCP data recovery for a radio
bearer, the transmitting PDCP entity shall:

\- perform retransmission of all the PDCP Data PDUs previously submitted
to re-established or released AM RLC entities in ascending order of the
associated COUNT values for which the successful delivery has not been
confirmed by lower layers, following the data submission procedure in
clause 5.2.1.

After performing the above procedures, the transmitting PDCP entity
shall follow the procedures in clause 5.2.1.