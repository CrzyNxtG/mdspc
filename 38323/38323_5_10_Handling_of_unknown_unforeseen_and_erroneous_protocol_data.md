## 5.10 Handling of unknown, unforeseen, and erroneous protocol data

When a PDCP PDU that contains reserved or invalid values is received,
the receiving PDCP entity shall:

\- discard the received PDU.

NOTE: For NR sidelink communication for unicast, the invalid values
include the invalid value of K~NRP-sess~ ID.