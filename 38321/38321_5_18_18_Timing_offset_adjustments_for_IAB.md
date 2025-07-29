### 5.18.18 Timing offset adjustments for IAB

For IAB operation, in order to achieve time-domain synchronization
across multiple backhaul hops, a timing adjustment may be provided to an
IAB node by its parent node. Two different values may be provided,
related to Case-1/Case-6, and Case-7 timing modes respectively. The
Timing Delta MAC CE carries T~delta~ which is used to determine the
IAB-DU DL Tx timing adjustment for the Case-1 timing mode, and to
determine the IAB-DU DL Tx and IAB-MT UL Tx timing adjustment for the
Case-6 timing mode. The Case-7 Timing advance offset MAC CE carries
T~offset,2~ which is used to determine the IAB-MT UL Tx timing
adjustment for the Case-7 timing mode.

Upon reception of a Timing Delta MAC CE the IAB node shall:

\- apply the value of T~delta~ as specified in TS 38.213 \[6\].

Upon reception of a Case-7 Timing advance offset MAC CE the IAB node
shall:

\- apply the value of T~offset,2~ as specified in TS 38.213 \[6\].