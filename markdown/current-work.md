## Current Work


###Single Host vs. Distributed Actors

Split Application Off to Separate Host

Communication via Stream via Database

Current: DynamoDB and DynamoDB Streams (Beta AWS product)


### Database Schema

2 Separate DynamoDB Tables: 
  * Events
  * Commands


###Event Table

GUID  | EVENTID |  TIMESTAMP | JSON | SOURCEID

Primary Key = GUID + EVENT_ID


###Command Table

GUID | CMDID  | TIMESTAMP | JSON | SOURCEID

Primary Key = GUID + CMD_ID


####TCP Acceptor Process
  * Writes to Events
  * Listens for Commands


####Application Process
  * Writes to Commands
  * Listens for Events


## THIS MEANS COMMANDS ARE A STREAM TOO!
  * Commands No Longer Just Responses to Events
  * Commands Come Whenever, From Wherever 
  * Proposed Demos: Jabber, Chess, etc.
  * Leave the "Web Age" Behind
