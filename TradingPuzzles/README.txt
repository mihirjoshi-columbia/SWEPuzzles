Problem Statement

Complete the following functions

recordLog(logId, timestamp): Records a new log entry
- Each log is represented as an object with a logId and timestamp. The
logId is an identifier for each log and the timestamp is an integer in seconds
representing when the log was sent

- Ignore logs with timestamps earlier than the latest log received

- The logId is not guaranteed to be unique - the same logId can be used for 
different logs.

getLogs(): Returns a comma seperated string of the latest m logIds from the last hour in theorder they were received.
- Retrun a string of the form "logId1, logId2, logId3, logId4" where logId4 is the most
recently received log and logId1 is the earliest log received < 1 hour before logId4's 
timestamp

getLogCount(): Returns the total number of logs received < 1 hour from the most recently
stored log timestamp. In the event of more than m logs have been received still return 
the full count of logs

Input Format:

The first line contains a single integer, m denoting the maximum number of logs `getLogs()` should return.
The second line contains a single integer, q denoting the number of queries. Each of the next q lines contains a query in one of the following formats:

* `RECORD logId timestamp` – this query represents a call to `recordLog(logId, timestamp)`.
* `GET_LOGS` – this query represents a call to `getLogs()`.
* `COUNT` – this query represents a call to `getLogCount()`.

Constraints:

* 1 ≤ m ≤ 1000
* 1 ≤ q ≤ 10^6
* `logId` is an integer
* `timestamp` is an integer representing a timestamp in seconds

Output Format:
For each `GET_LOGS` and `COUNT` query, print the result of `getLogs()` or `getLogCount()` 
on a new line. For `GET_LOGS` queries, print a comma-separated string of log IDs. For `COUNT` queries, print an integer.

---

Sample Input

```
100
10
RECORD 1 0
RECORD 2 300
GET_LOGS
COUNT
RECORD 3 1200
RECORD 1 1800
GET_LOGS
COUNT
RECORD 4 3900
GET_LOGS
```

Sample Output
```
1,2
2
1,2,3,1
4
3,1,4
```



