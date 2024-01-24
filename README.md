# Publisher Subscriber Pattern

What happens if the client loses connection with the server? What happens to messages if the server dies? Will the client still be able to receive messages after connection is reestablished?

PubSub is used when asynchronous operations need to be performed and some persistent message storage is needed. There are four key components in this architecture:  

Publishers are servers that publish data to the topic.  

Topics are channels with specific information. You publish one type of data in topic one, another type of data in topic two, and so on. 

The subscribers are clients that listen to different topics. Subscribers can subscribe to multiple topics.  

Messages are data or operations being sent through the channels (topics).  

Messages are stored in the topics and messages are guaranteed to be delivered at least once. The publisher publishes messages with some index or id representing the subscriber. When messages are received, a "received" flag is flipped.

Idemponency  
A message can be considered an idempotent operation. No matter how many times the message is sent, the result is the same. Idempotency of messages is important in pubsub design since messages get delivered at least once. 

Queueed messages 
Messages are sent in a first in first out manner.

Multiple Topics  
There are multiple topics, where each topic stores different kinds of data.  

# gRPC  

There can be multiple microservices in the backend and communication between them uses gRPC. 

gRPC benefits:  
-brings significant improvements in convenience and scalability  
-generates code (protocol buffers)  
Side Note: In the proto files, you can define the schema for the data or messages being sent. You can set which fields are optional, what datatypes are expected, etc. You also define what procedures you want to expose for other microservices to make remote procedure calls or RPC to. When you run the proto file against a compiler, it generates source code in your respective language.  
-performance is high because protocol buffers are serialized and sent as binaries rather than memory intensive key-value pairs like in json  




