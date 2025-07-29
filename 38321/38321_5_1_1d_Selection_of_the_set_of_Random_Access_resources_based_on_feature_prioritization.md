### 5.1.1d Selection of the set of Random Access resources based on feature prioritization

The MAC entity shall:

1\> among the available sets of Random Access resources for this Random
Access procedure (as specified in clause 5.1.1c), identify those
configured with a feature which has the highest priority assigned in
*featurePriorities* among all the features applicable to this Random
Access procedure as specified in TS 38.331 \[5\].

1\> if a single set of Random Access resources is identified:

2\> select this set of Random Access resources.

1\> else if more than one set of Random Access resources is identified:

2\> if all the identified sets of Random Access resources are configured
with Msg1 repetition indication and the same *featureCombination*:

3\> select the set of Random Access resources that associated with
highest Msg1 repetition number among the identified sets of Random
Access resources.

2\> else:

3\> repeat the procedure taking as an input the identified sets of
Random Access resources and the feature applicable to the current Random
Access procedure with the highest priority assigned in
*featurePriorities* among all the features applicable to this Random
Access procedure, except the features considered already.

1\> else (i.e. no set of Random Access resources is identified):

2\> repeat the procedure taking as an input the previous identified
available sets of Random Access resources and the feature applicable to
the current Random Access procedure with the highest priority assigned
in *featurePriorities* among all the features applicable to this Random
Access procedure, except the features considered already.