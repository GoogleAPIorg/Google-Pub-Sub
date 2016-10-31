# Google Pub/Sub API

## Cloud Pub/Sub = Publish-Subscribe Channel and Competing Consumers

Google Pub/Sub API comes with a quota of 10,000 messages per second across up to 10,000 topics.  At the nucleus of the Google Cloud Pub/Sub is Publish-Subscribe Channel.  It delivers a single messages published to it to multiple subscribers.  One of the advantages of this pattern is that adding subscribers is side-effect free.  In reality, Google Cloud Pub/Sub API implements both the Publish-Subscribe Channel and Competing Consumer patterns.

Use cases for Pub/Sub API:
 * Balancing workload
 * Distributing event notifications
 * Logging to multiple systems
 * Data streaming
 
### Topics and Subscriptions

The Pub/Sub implementation separates the concepts of topic and subscription, only one of them will receive a message.  
 * []() Topics - represent the pub-sub aspect of the system: if multiple subscribers subscribe to the same topic, each of them    will receive a copy of the message published to the topic.
 * Subscriptions represent the competing consumers aspect of the system: if multiple subscribers pull messages from the same      subscription, only one of them will receive the message.
 
 Separating topics and messages is a way to provide both Publish-Subscribe Channel and Point-to-Point Channel semantics through a single API.  
 
 
### REST API

 * Cloud Pub/Sub is accessed through a set of REST APIs.  Resource names for topics and subscriptions must follow the 


### Messaging Systems (Message-oriented Middleware)

Channels - Messaging applications transmit data through a Message Channel, a virtual pipe that connects a sender to a receiver.

Messages - A Message is an atomic packet of data that can be transmitted on a channel.  To transmit data, a message must break the data into one or more packets, wrap each packet as a message, and then send the message on a channel.  A receiver application receives a message and must extract the data from the message to process it.  The message system will try repeatedly to deliver the message until it succeeds.

Pipe and Filters - 

Messaging - One application publishes a message to a common message channel.  Other applications can read the message from the channel at a later time.  The applications must agree on a channel as well as on the format of the message.  The communication is asyncronous.

Remote Procedure Invocation - One application exposes some of its functionality so that it can be accessed remotely by other applications as a remote procedure.  The communication occurs in real time and synchronously.

