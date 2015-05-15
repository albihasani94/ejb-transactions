# ejb-transactions

To run: mvn wildfly:run

Output is
```
21:56:42,509 INFO  [stdout] (ServerService Thread Pool -- 50) 1
21:56:42,514 INFO  [stdout] (ServerService Thread Pool -- 50) Start Checked exception catched
21:56:42,514 INFO  [stdout] (ServerService Thread Pool -- 50) 2
21:56:42,517 INFO  [stdout] (ServerService Thread Pool -- 50) Start unchecked exception catched
21:56:42,517 INFO  [stdout] (ServerService Thread Pool -- 50) 2
```


Because unchecked exception is @ApplicationException(rollback=false) why insert action is rolled back?

##### Answer: incorrect transaction annotations: should be javax.ejb.TransactionAttribute
