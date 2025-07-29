### 16.3.3a Slice-based cell reselection

Slice-based cell reselection information can be included in SIB16 and in
*RRCRelease* messages. The slice-based cell reselection information may
include reselection priorities per NSAG per frequency and corresponding
list(s) of cells where the slices of the NSAG are supported or not
supported. The UE determines the NSAG(s) and their priorities to be
considered during cell reselection as specified in TS 23.501 \[3\], and
in TS 38.304 \[10\].

When a UE supports slice-based cell reselection, and when slice-based
cell reselection information is provided to the UE, then the UE uses the
slice-based cell reselection information. Valid cell reselection
information provided in *RRCRelease* always has a priority over cell
reselection information provided in SIB messages. When no slice-based
cell reselection information is provided for any NSAG that was
determined to be considered during cell reselection (as specified in TS
23.501 \[3\]), then the UE uses the general cell reselection
information, i.e., without considering the NSAG(s) and their priorities.