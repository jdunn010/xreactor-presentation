##XReactor Implementation


###Overall Architecture


###Akka Actor Refs For TCP Server

`//Initialize Runtime Environment
ActorSystem system = ActorSystem.create("XReactor", ConfigFactory.load());

//Initialize TCP Server and bind to port 10022
ActorRef tcpManager = Tcp.get(getContext().system()).manager();
tcpManager.tell(TcpMessage.bind(getSelf(),
                      new InetSocketAddress(10022), 0), getSelf());

//Register Incoming Connection Handler with TCP Server
ActorRef tcpReceiverActor = getContext().actorOf
		     (Props.create(TcpReceiverActor.class, sender()));
getSender().tell(TcpMessage.register(tcpReceiverActor), getSelf());`

###Boon Serialization Codecs -- JSON Parsing


###Performance Status

* XreBoss load test tool
* AWS experimentation


###Single Host vs. Distributed Actors
