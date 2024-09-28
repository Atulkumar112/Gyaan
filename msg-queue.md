## RabbitMQ
RabbitMQ is an open-source message broker software that uses AMQP(Advanced Message Queuing Protocol) to transmit transfer data, meaning RabbitMQ accepts messages from producers and delivers them to consumers. So RabbitMQ is middleware that reduces loads and delivery time on web application servers. It gives your applications a common platform to send and receive messages and your messages a safe place to live until they are received through a queue handler.

### Basic concepts of RabbitMQ:
RabbitMQ consists of 4 basic components:

- Producer
- Exchange
- Queue
- Consumer                                                                                                  |-----------|
  								      Routing Key |-----------|    |------->| Consumer  |
									|-------> |  Queue 1  |    |        |-----------|
                                                                        |         |-----------|    |
			|-----------|		|------------------|	|         |-----------|    |        |-----------|
			| Producer  |---------->|     Exchange     |----|-------> |  Queue 2  |----|------->| Consumer  |
			|-----------|		|------------------|	|         |-----------|    |	    |-----------| 
									|-------> |  Queue 3  |    |
										  |-----------|    |        |-----------|
												   |------->| Consumer  |
												            |-----------|	

### Producer
Producing means nothing else than sending messages. A program that sends messages is called a Producer.

### Exchange
The exchange receives a message from the producer and routes it to zero or more queues. The routing algorithm depends on the Exchange type and the binding rules.

There are the following types of Exchange in RabbitMQ:
- Direct exchange:- Messages are forwarded to a queue only if the value of a certain key (routing key) matches between them.
- Fanout exchange:- When we want to distribute our message so that each queue can receive the message.
- Topic exchange:- Unlike a direct exchange, this uses patterns instead of an exact key.
- Header exchange:- The header’s value is the same as the value specified in the routing key.

### Queue
A queue is a message store found in RabbitMQ. Although messages flow through RabbitMQ and your applications, they can only be stored within a queue.

### Consumer
Consume has a similar meaning to Receive. A consumer is a program that primarily waits to receive messages. Our consumer waits for messages from RabbitMQ.
To consume messages, a queue must exist. When a new consumer is added, delivery starts immediately, provided messages are already in the queue.
