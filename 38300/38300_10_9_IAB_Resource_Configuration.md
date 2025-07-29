## 10.9 IAB Resource Configuration

If the IAB-DU and the IAB-MT of an IAB-node are subject to a half-duplex
constraint, correct transmission/reception by one cannot be guaranteed
during transmission/reception by the other and vice versa, e.g., when
collocated and operating in the same frequency. If an IAB-node supports
enhanced frequency or spatial multiplexing capabilities, additional
multiplexing modes can be supported, i.e., simultaneous operation of
IAB-MT Rx / IAB-DU Rx, IAB-MT Tx / IAB-DU Tx, IAB-MT Rx / IAB-DU Tx,
IAB-MT Tx / IAB-DU Rx. An IAB-node can report its duplexing constraints
between the IAB-MT and the collocated IAB-DU via F1AP. An IAB-node can
indicate via F1AP whether or not FDM is required for an enhanced
multiplexing operation.

The scheduler on an IAB-DU or IAB-donor-DU complies with the gNB-DU
resource configuration received via F1AP, which defines the usage of
scheduling resources to account for the aforementioned duplexing
constraint.

The resource configuration assigns an attribute of hard, soft or
unavailable to each symbol of each DU cell. Transmission/reception can
occur for symbols configured as hard, whereas scheduling cannot occur,
except for some special cases, for symbols configures as unavailable.
For symbols configured as soft, scheduling can occur conditionally on an
explicit indication of availability by the parent node via DCI format
2_5, or on an implicit determination of availability by the IAB-node.
The implicit determination of availability is determined by the IAB-node
depending on whether or not the operation of the IAB-DU would have an
impact on the collocated IAB-MT.

The resource configuration can be shared among neighbouring IAB-nodes
and IAB-donors to facilitate interference management, dual connectivity,
and enhanced multiplexing.

To facilitate transitioning from IAB-MT to IAB-DU operation and vice
versa, guard symbols can be used to overcome potentially misaligned
symbol boundaries between the IAB-MT operation and the IAB-DU operation
(e.g., IAB-MT Rx boundaries are not aligned with the IAB-DU Tx
boundaries). Specifically, an IAB-node can indicate to a parent node a
number of desired guard symbols, while the parent node can indicate to
the IAB-node the number of actually provided guard symbols for specific
transitions.

An IAB-node supporting enhanced multiplexing capabilities, i.e., IAB-MT
Rx / IAB-DU Rx, IAB-MT Tx / IAB-DU Tx, IAB-MT Rx / IAB-DU Tx, IAB-MT Tx
/ IAB-DU Rx, can provide via MAC-CE to a parent node information to
facilitate scheduling for enhanced multiplexing operation by the
IAB-node, specifically:

\- recommended IAB-MT\'s Tx/Rx beams;

\- desired IAB-MT Tx PSD range;

\- desired parent node\'s IAB-DU Tx power adjustment;

\- required IAB-MT\'s uplink transmission timing mode.

Correspondingly, the parent node can provide information via MAC-CE to
the IAB-node to facilitate enhanced multiplexing at the IAB-node and/or
at the parent node:

\- restricted IAB-DU Tx beams;

\- actual parent node\'s IAB-DU Tx power adjustment;

\- IAB-MT\'s uplink transmission timing mode.