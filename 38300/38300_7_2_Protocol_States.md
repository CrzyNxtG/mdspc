## 7.2 Protocol States

RRC supports the following states which can be characterised as follows:

**- RRC_IDLE**:

\- PLMN selection;

\- Broadcast of system information;

\- Cell re-selection mobility;

\- Paging for mobile terminated data is initiated by 5GC;

\- Transfer of MBS broadcast data to the UE over MRB(s);

\- DRX for CN paging configured by NAS.

\- **RRC_INACTIVE**:

\- PLMN selection;

\- Broadcast of system information;

\- Cell re-selection mobility;

\- Paging is initiated by NG-RAN (RAN paging);

\- RAN-based notification area (RNA) is managed by NG- RAN;

\- DRX for RAN paging configured by NG-RAN;

\- 5GC - NG-RAN connection (both C/U-planes) is established for UE;

\- The UE Inactive AS context is stored in NG-RAN and the UE;

\- NG-RAN knows the RNA which the UE belongs to;

\- Transfer of MBS multicast/broadcast data to the UE over MRB(s);

\- Transfer of unicast data and/or signalling to/from the UE over radio
bearers configured for SDT.

\- **RRC_CONNECTED**:

\- 5GC - NG-RAN connection (both C/U-planes) is established for UE;

\- The UE AS context is stored in NG-RAN and the UE;

\- NG-RAN knows the cell which the UE belongs to;

\- Transfer of unicast data to/from the UE;

\- Transfer of MBS multicast/broadcast data to the UE over MRB(s);

\- Network controlled mobility including measurements.