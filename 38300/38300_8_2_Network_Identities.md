## 8.2 Network Identities

The following identities are used in NG-RAN for identifying a specific
network entity:

\- AMF Name: used to identify an AMF.

\- NR Cell Global Identifier (NCGI): used to identify NR cells globally.
The NCGI is constructed from the PLMN identity the cell belongs to and
the NR Cell Identity (NCI) of the cell. The PLMN ID included in the NCGI
should be the first PLMN ID within the set of PLMN IDs associated to the
NR Cell Identity in SIB1, following the order of broadcast.

NOTE 1: How to manage the scenario where a different PLMN ID has been
allocated by the operator for an NCGI is left to OAM and/or
implementation.

\- gNB Identifier (gNB ID): used to identify gNBs within a PLMN. The gNB
ID is contained within the NCI of its cells.

\- Global gNB ID: used to identify gNBs globally. The Global gNB ID is
constructed from the PLMN identity the gNB belongs to and the gNB ID.
The MCC and MNC are the same as included in the NCGI.

NOTE 2: It is not precluded that a cell served by a gNB does not
broadcast the PLMN ID included in the Global gNB ID.

\- Tracking Area identity (TAI): used to identify tracking areas. The
TAI is constructed from the PLMN identity the tracking area belongs to
and the TAC (Tracking Area Code) of the Tracking Area.

\- Single Network Slice Selection Assistance information (S-NSSAI):
identifies a network slice.

\- Network Slice AS Group (NSAG): identifies an association to a slice
or a set of slices. An NSAG is defined within a TA, used for slice-based
cell reselection and/or slice-based RACH configuration. Values of NSAG
IDs associated with different slice or set of slices shall be unique
within a TA, also when slice-based cell reselection and slice-based RACH
configuration are both supported in the TA.

\- Network Identifier (NID): identifies an SNPN in combination with a
PLMN ID.

\- Closed Access Group Identifier: identifies a CAG within a PLMN.

\- Local NG-RAN Node Identifier: used as reference to the NG-RAN node in
the I-RNTI.