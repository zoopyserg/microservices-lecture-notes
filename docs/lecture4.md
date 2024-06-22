# Microservice interaction

## Syncronous
- http
- rpc
- grpc
- Rabbit MQ

### Consider:
- Thread Locking (so that many requests can be worked on at the same time)

### When
- When client needs a response immediately after sending the request.

Gems:
- faraday
- faraday_middleware

# Postman
A good client for testing APIs.
