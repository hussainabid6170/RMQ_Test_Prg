# RMQ_Test_Prg

Message flow in RabbitMQ
The producer publishes a message to an exchange. When creating an exchange, the type must be specified. This topic will be covered later on.
The exchange receives the message and is now responsible for routing the message. The exchange takes different message attributes into account, such as the routing key, depending on the exchange type.
Bindings must be created from the exchange to queues. In this case, there are two bindings to two different queues from the exchange. The exchange routes the message into the queues depending on message attributes.
The messages stay in the queue until they are handled by a consumer
The consumer handles the message.

Types of Exchanges:
Direct: The message is routed to the queues whose binding key exactly matches the routing key of the message. For example, if the queue is bound to the exchange with the binding key pdfprocess, a message published to the exchange with a routing key pdfprocess is routed to that queue.
Fanout: A fanout exchange routes messages to all of the queues bound to it.
Topic: The topic exchange does a wildcard match between the routing key and the routing pattern specified in the binding.
Headers: Headers exchanges use the message header attributes for routing.



Terminology:
Producer: Application that sends the messages.
Consumer: Application that receives the messages.
Queue: Buffer that stores messages.
Message: Information that is sent from the producer to a consumer through RabbitMQ.
Connection: A TCP connection between your application and the RabbitMQ broker.
Channel: A virtual connection inside a connection. When publishing or consuming messages from a queue - it's all done over a channel.
Exchange: Receives messages from producers and pushes them to queues depending on rules defined by the exchange type. To receive messages, a queue needs to be bound to at least one exchange.
Binding: A binding is a link between a queue and an exchange.
Routing key: A key that the exchange looks at to decide how to route the message to queues. Think of the routing key like an address for the message.
AMQP: Advanced Message Queuing Protocol is the protocol used by RabbitMQ for messaging.
Users: It is possible to connect to RabbitMQ with a given username and password. Every user can be assigned permissions such as rights to read, write and configure privileges within the instance. Users can also be assigned permissions for specific virtual hosts.
Vhost, virtual host: Provides a way to segregate applications using the same RabbitMQ instance. Different users can have different permissions to different vhost and queues and exchanges can be created, so they only exist in one vhost.
