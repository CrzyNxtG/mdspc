### 8.1.7 UE procedure for determining the number of logical slots for a reservation period

A given resource reservation period $P_{\text{rsvp}}$ in milliseconds is
converted to a period $P_{rsvp}'$ in logical slots as:

$$P_{rsvp}' = \left\lceil \frac{{T'}_{\max}\ }{10240\ ms} \times P_{rsvp} \right\rceil$$

where ${T'}_{\max}$ is the number of slots that belong to a resource
pool as defined in Clause 8.