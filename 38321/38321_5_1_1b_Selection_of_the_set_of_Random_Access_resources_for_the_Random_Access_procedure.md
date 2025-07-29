### 5.1.1b Selection of the set of Random Access resources for the Random Access procedure

The MAC entity shall:

1\> if the BWP selected for Random Access procedure is configured with
both set(s) of Random Access resources with *msg3-Repetitions* set to
*true* and set(s) of Random Access resources without *msg3-Repetitions*
set to *true* and the RSRP of the downlink pathloss reference is less
than *rsrp-ThresholdMsg3*; or

1\> if the BWP selected for Random Access procedure is only configured
with the set(s) of Random Access resources with *msg3-Repetitions* set
to *true*:

2\> assume Msg3 repetition is applicable for the current Random Access
procedure.

1\> else:

2\> assume Msg3 repetition is not applicable for the current Random
Access procedure.

1\> if contention-free Random Access Resources have been provided for
this Random Access procedure in the LTM Cell Switch Command MAC CE and a
non-zero Msg1 repetition number is indicated in the LTM Cell Switch
Command MAC CE:

2\> assume that Msg1 repetition is applicable and that the Msg1
repetition number applicable for the current Random Access procedure is
the Msg1 repetition number indicated in the LTM Cell Switch Command MAC
CE.

1\> else if contention-free Random Access Resources have been provided
for this Random Access procedure and a Msg1 repetition number is
indicated in *rach-ConfigDedicated*:

2\> assume Msg1 repetition is applicable and Msg1 repetition number
applicable for the current Random Access procedure is the Msg1
repetition number indicated in *rach-ConfigDedicated*.

1\> else if contention free Random Access Resources have not been
provided for this Random Access procedure and the BWP selected for the
Random Access procedure is configured with set(s) of Random Access
resources with *msg1-Repetitions* set to *true* and set(s) of Random
Access resources without *msg1-Repetitions* set to *true*:

2\> if the BWP selected for the Random Access procedure is configured
with set(s) of Random Access resources associated with Msg1 repetition
number 8 and the RSRP of the downlink pathloss reference is less than
*rsrp-ThresholdMsg1-RepetitionNum8*:

3\> assume Msg1 repetition is applicable and Msg1 repetition number
applicable for the current Random Access procedure includes 8.

2\> if the BWP selected for the Random Access procedure is configured
with set(s) of Random Access resources associated with Msg1 repetition
number 4 and the RSRP of the downlink pathloss reference is less than
*rsrp-ThresholdMsg1-RepetitionNum4*:

3\> assume Msg1 repetition is applicable and Msg1 repetition number
applicable for the current Random Access procedure includes 4.

2\> if the BWP selected for the Random Access procedure is configured
with set(s) of Random Access resources associated with Msg1 repetition
number 2 and the RSRP of the downlink pathloss reference is less than
*rsrp-ThresholdMsg1-RepetitionNum2*:

3\> assume Msg1 repetition is applicable and Msg1 repetition number
applicable for the current Random Access procedure includes 2.

2\> else if the RSRP of the downlink pathloss reference is not less than
any configured *rsrp-ThresholdMsg1-RepetitionNumX*:

3\> assume Msg1 repetition is not applicable for the current Random
Access procedure.

1\> else if the BWP selected for Random Access procedure is configured
only with the set(s) of Random Access resources with *msg1-Repetitions*
set to *true*:

2\> assume Msg1 repetition is applicable for the current Random Access
procedure;

2\> if at least one of *rsrp-ThresholdMsg1-RepetitionNumX* is
configured:

3\> if *rsrp-ThresholdMsg1-RepetitionNum8* is configured and the RSRP of
the downlink pathloss reference is less than
*rsrp-ThresholdMsg1-RepetitionNum8*;

4\> assume Msg1 repetition number applicable for the current Random
Access procedure includes 8.

3\> if *rsrp-ThresholdMsg1-RepetitionNum4* is configured and the RSRP of
the downlink pathloss reference is less than
*rsrp-ThresholdMsg1-RepetitionNum4*:

4\> assume Msg1 repetition number applicable for the current Random
Access procedure includes 4.

3\> if *rsrp-ThresholdMsg1-RepetitionNum2* is configured and the RSRP of
the downlink pathloss reference is less than
*rsrp-ThresholdMsg1-RepetitionNum2*:

4\> assume Msg1 repetition number applicable for the current Random
Access procedure includes 2.

3\> else if the RSRP of the downlink pathloss reference is not less than
any configured *rsrp-ThresholdMsg1-RepetitionNumX*:

4\> assume Msg1 repetition number applicable for the current Random
Access procedure is the lowest Msg1 repetition number configured for
this BWP.

2\> else (none of *rsrp-ThresholdMsg1-RepetitionNumX* is configured):

3\> assume Msg1 repetition number applicable for the current Random
Access procedure is the Msg1 repetition number that configured for this
BWP.

NOTE 1: Void.

1\> if neither contention-free Random Access Resources nor Random Access
Resources for SI request have been provided for this Random Access
procedure and one or more of the features including (e)RedCap and/or
Slicing and/or SDT and/or MSG3 repetition and/or MSG1 repetition is
applicable for this Random Access procedure:

NOTE 2: The applicability of SDT is determined by MAC entity according
to clause 5.27. The applicability of *NSAG-ID* is determined by upper
layers when the Random Access procedure is initiated. The applicability
of (e)RedCap is also determined by upper layers when Random Access
procedure is initiated and it is applicable to the Random Access
procedures initiated by PDCCH orders and any Random Access procedure
initiated by the MAC entity.

NOTE 3: SDT is not applicable for the Random Access procedure initiated
by upper layers for MT-SDT.

2\> if none of the sets of Random Access resources are available for any
feature applicable to the current Random Access procedure (as specified
in clause 5.1.1c):

3\> select the set(s) of Random Access resources that are not associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

2\> else if there is one set of Random Access resources available which
can be used for indicating all features triggering this Random Access
procedure:

3\> select this set of Random Access resources for this Random Access
procedure.

2\> else if there are more than one set of Random Access resources
available which can be used for indicating all features triggering this
Random Access procedure and Msg1 repetition is applicable for this
Random Access procedure:

3\> select the set of Random Access resources that associated with
highest repetition number among the sets of Random Access resources.

2\> else (i.e. there are one or more sets of Random Access resources
available that are configured with indication(s) for a subset of all
features triggering this Random Access procedure):

3\> select a set of Random Access resources from the available set(s) of
Random Access resources based on the priority order indicated by upper
layers as specified in clause 5.1.1d for this Random Access Procedure.

1\> else if this Random Access procedure is initiated by PDCCH order
with the *PRACH association indicator* field in DCI set to 1 and
*SSB-MTC-AdditionalPCI* is configured by upper layers, as specified in
clause 7.3.1.2.1 of TS 38.212 \[9\]:

2\> select the set of Random Access resources corresponding to the
*additionalPCI* associated with active TCI states.

1\> else if this Random Access procedure is initiated by PDCCH order for
an LTM candidate cell:

2\> select the set of Random Access resources configured in
*EarlyUL-SyncConfig* corresponding to the carrier and the cell indicated
by the field *UL/SUL indicator* and the field *Cell indicator* in the
PDCCH order respectively, as specified in TS 38.212 \[9\].

1\> else if contention-free Random Access Resources have been provided
for this Random Access procedure by PDCCH order:

2\> if RedCap is applicable for the current Random Access procedure:

3\> if there is one set of Random Access resources available that is
only configured with RedCap indication:

4\> select this set of Random Access resources for this Random Access
procedure.

3\> else:

4\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

2\> else if eRedCap is applicable for the current Random Access
procedure:

3\> if there is one set of Random Access resources available that is
only configured with eRedCap indication:

4\> select this set of Random Access resources for this Random Access
procedure.

3\> else if there is one set of Random Access resources available that
is only configured with RedCap indication:

4\> select this set of Random Access resources for this Random Access
procedure.

3\> else:

4\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

2\> else:

3\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

1\> else if contention-free Random Access Resources have been provided
for this Random Access procedure in the LTM Cell Switch Command MAC CE:

2\> if RedCap is applicable for this Random Access procedure:

3\> if a non-zero Msg1 repetition number is indicated in the LTM Cell
Switch Command MAC CE:

4\> select the set of Random Access resources that is only configured
with RedCap indication and Msg1 repetition indication and associated
with the indicated Msg1 repetition number for this Random Access
procedure.

3\> else:

4\> if there is one set of Random Access resources available that is
only configured with RedCap indication:

5\> select this set of Random Access resources for this Random Access
procedure.

4\> else:

5\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

2\> else if eRedCap is applicable for this Random Access procedure:

3\> if a non-zero Msg1 repetition number is indicated in the LTM Cell
Switch Command MAC CE:

4\> select the set of Random Access resources that is only configured
with eRedCap indication and Msg1 repetition indication and associated
with the indicated Msg1 repetition number for this Random Access
procedure.

3\> else:

4\> if there is one set of Random Access resources available that is
only configured with eRedCap indication:

5\> select this set of Random Access resources for this Random Access
procedure.

4\> else if there is one set of Random Access resources available that
is only configured with RedCap indication:

5\> select this set of Random Access resources for this Random Access
procedure.

4\> else:

5\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

2\> else:

3\> if a non-zero Msg1 repetition number is indicated in the LTM Cell
Switch Command MAC CE:

4\> select the set of Random Access resources that is only configured
with Msg1 repetition indication and associated with the indicated Msg1
repetition number for this Random Access procedure.

3\> else:

4\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

1\> else if contention-free Random Access Resources have been provided
for this Random Access procedure in *rach-ConfigDedicated*:

2\> if RedCap is applicable for this Random Access procedure:

3\> if Msg1 repetition number is indicated in *rach-ConfigDedicated*:

4\> select the set of Random Access resources that is only configured
with RedCap indication and Msg1 repetition indication and associated
with the indicated Msg1 repetition number for this Random Access
procedure.

3\> else:

4\> if there is one set of Random Access resources available that is
only configured with RedCap indication:

5\> select this set of Random Access resources for this Random Access
procedure.

4\> else:

5\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

2\> else if eRedCap is applicable for this Random Access procedure:

3\> if Msg1 repetition number is indicated in *rach-ConfigDedicated*:

4\> select the set of Random Access resources that is only configured
with eRedCap indication and Msg1 repetition indication and associated
with the indicated Msg1 repetition number for this Random Access
procedure.

3\> else:

4\> if there is one set of Random Access resources available that is
only configured with eRedCap indication:

5\> select this set of Random Access resources for this Random Access
procedure.

4\> else if there is one set of Random Access resources available that
is only configured with RedCap indication:

5\> select this set of Random Access resources for this Random Access
procedure.

4\> else:

5\> select the set of Random Access resources that not is associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

2\> else:

3\> if Msg1 repetition number is indicated in *rach-ConfigDedicated*:

4\> select the set of Random Access resources that is only configured
with Msg1 repetition indication and associated with the indicated Msg1
repetition number for this Random Access procedure.

3\> else:

4\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

1\> else if contention-free Random Access Resources have been provided
for this Random Access procedure in the *BeamFailureRecoveryConfig*:

2\> if RedCap is applicable for this Random Access procedure:

3\> if there is one set of Random Access resources available that is
only configured with RedCap indication:

4\> select this set of Random Access resources for this Random Access
procedure.

3\> else:

4\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

2\> else if eRedCap is applicable for this Random Access procedure:

3\> if there is one set of Random Access resources available that is
only configured with eRedCap indication:

4\> select this set of Random Access resources for this Random Access
procedure.

3\> else if there is one set of Random Access resources available that
is only configured with RedCap indication:

4\> select this set of Random Access resources for this Random Access
procedure.

3\> else:

4\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

2\> else:

3\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for this
Random Access procedure.

1\> else if Random Access resources for SI request have been provided
for this Random Access procedure:

2\> if Random Access Resources associated with Msg1 repetition for SI
request and Msg1 repetition number have been provided for this Random
Access procedure:

3\> if the BWP selected for Random Access procedure is indicated by
*initialUplinkBWP-RedCap*:

4\> if RedCap is applicable for the current Random Access procedure:

5\> select the set of Random Access Resources that is only configured
with RedCap indication and Msg1 repetition indication and associated
with the indicated Msg1 repetition number for this Random Access
procedure.

4\> else if eRedCap is applicable for the current Random Access
procedure:

5\> if there is one set of Random Access resources available that is
only configured with RedCap indication and Msg1 repetition indication
and associated with the indicated Msg1 repetition number:

6\> select this set of Random Access resources for this Random Access
procedure.

5\> else:

6\> select the set of Random Access Resources that is only configured
with eRedCap indication and Msg1 repetition indication and associated
with the indicated Msg1 repetition number for this Random Access
procedure.

3\> else:

4\> select the set of Random Access resources that is only configured
with Msg1 repetition indication and associated with the indicated Msg1
repetition number for this Random Access procedure.

2\> else:

3\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for the
current Random Access procedure.

1\> else:

2\> select the set of Random Access resources that is not associated
with any feature indication (as specified in clause 5.1.1c) for the
current Random Access procedure.