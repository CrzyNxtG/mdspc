### 16.15.5 Non-Homogeneous support of PDU set based handling in NG-RAN

During a handover from a gNB supporting PDU Set based handling to
another gNB, the source gNB signals the PDU Set Information over Xn-U if
the target node has signalled the support of PDU Set based handling in
the Xn Handover Request Acknowledge message.

During a handover, transition from RRC_INACTIVE to RRC_CONNECTED or RRC
re-establishment from a gNB not supporting PDU Set based handling to a
gNB supporting PDU Set based handling, the target/new serving gNB may
indicate the support of PDU Set based handling to the SMF during the
Path Switch Request procedure or Handover Resource Allocation procedure
(in case of NG handover), the SMF will act as specified in TS
23.501\[3\]. If the indication is absent, the SMF infers that PDU Set
based handling is not supported by the target/new serving gNB node, then
the SMF will act as specified in TS 23.501\[3\].

During a handover, transition from RRC_INACTIVE to RRC_CONNECTED or RRC
re-establishment from a gNB node not supporting PDU Set based handling
to a gNB node supporting PDU Set based handling, the target/new serving
gNB node may receive unmarked PDU(s) (i.e. PDU(s) without PDU Set
Information Container) forwarded from the source/last serving gNB, node
and marked PDU(s) (i.e. PDU(s) with PDU Set Information Container) from
UPF, how the target/new serving gNB node handles the marked and unmarked
PDUs for the same QoS flow is up to implementation.