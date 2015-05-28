##XReactor Implementation


###Overall Architecture

Separate TCP and JSON/XRE Away From Other Components


###Akka Actor Refs For TCP Server

    //Initialize Runtime Environment
    ActorSystem system = ActorSystem.create("XReactor", ConfigFactory.load());

    //Initialize TCP Server and bind to port 10022
    ActorRef tcpManager = Tcp.get(getContext().system()).manager();
    tcpManager.tell(TcpMessage.bind(getSelf(),
                      new InetSocketAddress(10022), 0), getSelf());

    //Register Incoming Connection Handler with TCP Server
    ActorRef tcpReceiverActor = getContext().actorOf
		     (Props.create(TcpReceiverActor.class, sender()));
    getSender().tell(TcpMessage.register(tcpReceiverActor), getSelf());


###Boon Serialization Codecs -- JSON Parsing

Once TCP connection is established, feed contents to JSON parser.

Is Boon fastest parser available? Who cares, it's JSON, it's going to be slow. 


###XReactor Library Functionality -- Delegate to App

XRE Protocol basics in shared, reusable library (onConnect, activate, etc.)

Separate Out TCP Connection Management from Application.


###Akka Experience

Very gentle learning curve (for Java)

Great online documentation

Naturally leads to small, easy to test/debug classes

Negative -- untyped messages (a feature?)


###Performance Test Status

XreBoss load test tool

https://github.comcast.com/agerho000/xreboss

Written in GO, next iteration support for 10K XRE clients per process.
