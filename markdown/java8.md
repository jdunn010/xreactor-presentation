### Java 8 Streams

     List<Integer> transactionsIds = 
       transactions.stream()
                .filter(t -> t.getType() == Transaction.GROCERY)
                .sorted(comparing(Transaction::getValue).reversed())
                .map(Transaction::getId)
                .collect(toList());


### Java 8 Parallel Streams

     List<Integer> transactionsIds = 
       transactions.parallelStream()
                .filter(t -> t.getType() == Transaction.GROCERY)
                .sorted(comparing(Transaction::getValue).reversed())
                .map(Transaction::getId)
                .collect(toList());


![Image of java 8 pipeline](images/java8pipeline.jpg)


### Java 8 Streams Provide:

  * Pipelining -- Stream Ops That Return Stream
  * Iteration Handled Internally
  * Parallel Processing Handled Internally
  * Intermediate Storage/Accumulation Handled Internally
  * Lambdas and Method References


### Legacy XRE Apps Have All Migrated to Java 8

  Sports, Weather, Stocks, etc. migrated Spring 2015
  
  Seamless Transition -- Just Worked

  Using XRE Platform 1.50.x and 1.51.x

