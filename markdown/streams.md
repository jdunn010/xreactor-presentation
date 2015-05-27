###Everything Is A Stream
![Image of a stream](images/stream.jpg)


##Stream Is Central Metaphor of Reactive Programming


##Stream Evokes Other Related Metaphors
Flow, Pipes, Pipelines, Channels, Filters, Sequences, Series, etc.


### Channels
![Image of NBC Peacock](images/nbcpeacock.jpg)


### Pipelines
    netstat -na|grep 10022|wc -l
>"The UNIX philosophy is often quoted as "everything is a file", but that
really means "everything is a stream of bytes"." 

Linus Torvalds


### Java 8 Streams

     List<Integer> transactionsIds = 
       transactions.stream()
                .filter(t -> t.getType() == Transaction.GROCERY)
                .sorted(comparing(Transaction::getValue).reversed())
                .map(Transaction::getId)
                .collect(toList());


The Reactive Streams Specification

http://www.reactive-streams.org/
