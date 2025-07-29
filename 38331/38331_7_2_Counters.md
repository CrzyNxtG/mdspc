## 7.2 Counters

+---------+---------------------------+---------------------+---------------------+
| Counter | Reset                     | Incremented         | When reaching max   |
|         |                           |                     | value               |
+=========+===========================+=====================+=====================+
| N310    | Upon reception of         | Upon reception of   | Start timer T310    |
|         | \"in-sync\" indication    | \"out-of-sync\"     |                     |
|         | from lower layers;        | from lower layer    |                     |
|         |                           | while the timer     |                     |
|         | upon receiving            | T310 is stopped.    |                     |
|         | *RRCReconfiguration* with |                     |                     |
|         | *reconfigurationWithSync* |                     |                     |
|         | for that cell group;      |                     |                     |
|         |                           |                     |                     |
|         | upon initiating the       |                     |                     |
|         | connection                |                     |                     |
|         | re-establishment          |                     |                     |
|         | procedure.                |                     |                     |
+---------+---------------------------+---------------------+---------------------+
| N311    | Upon reception of         | Upon reception of   | Stop the timer      |
|         | \"out-of-sync\"           | the \"in-sync\"     | T310.               |
|         | indication from lower     | from lower layer    |                     |
|         | layers;                   | while the timer     |                     |
|         |                           | T310 is running.    |                     |
|         | upon receiving            |                     |                     |
|         | *RRCReconfiguration* with |                     |                     |
|         | *reconfigurationWithSync* |                     |                     |
|         | for that cell group;      |                     |                     |
|         |                           |                     |                     |
|         | upon initiating the       |                     |                     |
|         | connection                |                     |                     |
|         | re-establishment          |                     |                     |
|         | procedure.                |                     |                     |
+---------+---------------------------+---------------------+---------------------+