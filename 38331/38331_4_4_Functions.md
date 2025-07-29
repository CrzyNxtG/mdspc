## 4.4 Functions

The RRC protocol includes the following main functions:

\- Broadcast of system information:

\- Including NAS common information;

\- Information applicable for UEs in RRC_IDLE and RRC_INACTIVE (e.g.
cell (re-)selection parameters, neighbouring cell information) and
information (also) applicable for UEs in RRC_CONNECTED (e.g. common
channel configuration information);

\- Including ETWS notification, CMAS notification;

\- Including positioning assistance data.

\- RRC connection control:

\- Paging;

\- Establishment/modification/suspension/resumption/release of RRC
connection, including e.g. assignment/modification of UE identity
(C-RNTI, fullI-RNTI, etc.),
establishment/modification/suspension/resumption/release of SRBs (except
for SRB0);

\- Access barring;

\- Initial AS security activation, i.e. initial configuration of AS
integrity protection (SRBs, DRBs) and AS ciphering (SRBs, DRBs);

\- RRC connection mobility including e.g. intra-frequency and
inter-frequency handover, path switch from a PCell to a target L2 U2N
Relay UE or from a L2 U2N Relay UE to a target PCell or from a source L2
U2N Relay UE to a target L2 U2N Relay UE, associated AS security
handling, i.e. key/algorithm change, specification of RRC context
information transferred between network nodes;

\- Establishment/modification/suspension/resumption/release of RBs
carrying user data (DRBs/MRBs);

\- Radio configuration control including e.g. assignment/modification of
ARQ configuration, HARQ configuration, DRX configuration;

\- In case of DC, cell management including e.g. change of PSCell,
addition/modification/release of SCG cell(s);

\- In case of CA, cell management including e.g.
addition/modification/release of SCell(s);

\- In case of MP, path management including e.g.
addition/modification/release of indirect path;

\- QoS control including assignment/ modification of semi-persistent
scheduling (SPS) configuration and configured grant configuration for DL
and UL respectively, assignment/ modification of parameters for UL rate
control in the UE, i.e. allocation of a priority and a prioritised bit
rate (PBR) for each RB of UE and logical channel of IAB-MT.

\- Recovery from radio link failure.

\- Inter-RAT mobility including e.g. AS security activation, transfer of
RRC context information;

\- Measurement configuration and reporting:

\- Establishment/modification/release of measurement configuration (e.g.
intra-frequency, inter-frequency and inter- RAT measurements);

\- Setup and release of measurement gaps;

\- Measurement reporting.

\- Configuration of BAP entity and BH RLC channels for the support of
IAB-node.

\- Configuration of SRAP entity and Uu/PC5 Relay RLC channels for the
support of L2 U2N relay.

\- Configuration of SRAP entity and PC5 Relay RLC channels for the
support of L2 U2U relay operation.

\- Other functions including e.g. generic protocol error handling,
transfer of dedicated NAS information, transfer of UE radio access
capability information.

\- Support of self-configuration and self-optimisation.

\- Support of measurement logging and reporting for network performance
optimisation, as specified in TS 37.320 \[61\];

\- Support of transfer of application layer measurement configuration
and reporting.

\- Configuration of side control information for NCR-node.