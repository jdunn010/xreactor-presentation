## Current Work


###Single Host vs. Distributed Actors

Split Application Off to Separate Host

Communication via Stream via Database

Current: DynamoDB and DynamoDB Streams (Beta AWS product)


### Database Schema

2 Separate DynamoDB Tables: 
  * Events
  * Commands


####TCP Acceptor Process
  * Writes to Events
  * Listens for Commands


####Application Process
  * Writes to Commands
  * Listens for Events
