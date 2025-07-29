### 5.1.1c Availability of the set of Random Access resources

The MAC entity shall for each set of configured Random Access resources:

1\> if *eRedCap* is set to *true* for a set of Random Access resources:

2\> consider the set of Random Access resources as not available for a
Random Access procedure for which eRedCap is not applicable.

1\> if *redCap* is set to *true* for a set of Random Access resources:

2\> consider the set of Random Access resources as not available for a
Random Access procedure for which RedCap is not applicable.

1\> if *smallData* is set to *true* for a set of Random Access
resources:

2\> consider the set of Random Access resources as not available for the
Random Access procedure which is not triggered for RA-SDT by MO-SDT as
specified in TS 38.331 \[5\].

1\> if *NSAG-List* is configured for a set of Random Access resources:

2\> consider the set of Random Access resources as not available for the
Random Access procedure unless it is triggered for any one of the
*NSAG-ID*(s) in the *NSAG-List*.

1\> if *msg3-Repetitions* is set to *true* for a set of Random Access
resources:

2\> consider the set of Random Access resources as not available for the
Random Access procedure if Msg3 repetition is not applicable.

1\> if *msg1-Repetitions* is set to *true* for a set of Random Access
resources:

2\> if Msg1 repetition is not applicable to the current Random Access
procedure; or

2\> if the set of Random Access resources is not associated with any of
the Msg1 repetition number that is applicable to the current Random
Access procedure:

3\> consider the set of Random Access resources as not available for the
Random Access procedure.

1\> if a set of Random Access resources is not configured with
*FeatureCombination*:

2\> consider the set of Random Access resources to not associated with
any feature.