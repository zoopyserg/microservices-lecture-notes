# Async call to microservice

## Types:
- Queue
- Worker Queue
- Publish Subscribe
- Topic
- RPC

### Queue
- Producer
- Queue
- Consumer

Producer pushes a query into a queue.
Queue waits when conditions are met.
Once they are met - consumer sends a push.

### Worker Queue
Queue, but many consumers.
Example: Sidekiq.
There Producer is some Sidekiq API.
Queue is Redis.
Consumers are workers.

### Publish/Subscribe
Producer
Several Queues
Each queue is serviced by its own consumer

E.g. payment APIs:
Queue 1: payments to process
Queue 2: stats

### Topic:

Producer
Several queues
Many consumers
Each consumer can subscribe to many queues.

Example:
Rabbit MQ

So consumer gets subscribed to a particular type of events from any queue.

### RPC
Producer
Queue
Consumer
Callback queue (that sends requests back to Producer)
(e.g. PDF Processor;
but PDF Processor I made via HTTP API;
and RPC can be done without HTTP API)

## Pros of Async
- Doesn't lock our app

# Message Brokers for async talking to microservices

## Popular names:
- RabbitMQ (Elang/OTP)
- EMQ X Broker (Elang/OTP)
- Apache Kafka (Java, Scala)
- NATS (Go)
- NSQ (Go)

Each of them uses its own protocol.

## RabbitMQ

### Pros
- Elang/Otp (very reliable for distributed systems)
- Supported protocols: AMQP, MQTT, STOMP (those protocols can be used by many clients, can be connected to Rabbit via Socket).
- Flexible routing of messages, persistance of messages
- Plugins
- Monitoring
- Distributed deploy to cluster
- Client libs (Ruby, Python, JavaScript, Go, Elixir, Java)

RabbitMQ is just one of the tools, if it doesn't work for you - you can try NSQ, etc.

### Architecture
- Producer
- Exchange
- Multiple queues subscribed to exchange via binding
- Consumers (that process items from queue)

### Clients on Ruby
- Bunny (everything that RabbitMQ needs, except high level stuff)
- Hutch (rules how microservices should talk to each other)
- Sneakers (similar to Sidekiq but uses RabbitMQ instead of Redis - so the microservice no longer needs Redis, your queue will be in RabbitMQ, and the client will be lightweight)

# Architecture
- RabbitMQ (the queue, the callback queue...)
- Clients (may crash and go up, rabbit doesn't care - so clients need to handle restarts, etc.)

# RPC
- Geocode
- Rabbit stores data in binary format, so no need to parse HTTP headers, etc.

# Code
- docker with image rabbitmq:3-management
````
docker run \
  --rm \
  --name rabbitmq \
  -p 5672:5672 \
  -p 15672:15672 \
  --hostname rabbitmq \
  -v rabbitmq:/var/lib/rabbitmq \
  rabbitmq:3-management
````
localhost:15672
guest/guest

producer.rb
consuer.rb

(basic examples of producer and consumer)

so use RabbitMQ to receive pushed data from many producers.

It can be persistent
it can havve app id
real time callbacks.

Puma locks socket on its own.
With bunny threads we need to lock it manually.
Usually to lock things (threads, connections, methods, etc) we use Mutex.

Create many channels (so that many consumers can work with the same queue).

You need to draw all the threads, queues, channels, what goes where, etc.

Course is taken from thinknetica.com
