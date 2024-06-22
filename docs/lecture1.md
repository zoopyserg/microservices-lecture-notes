Why is this needed for business

Monolith first

Tools for microservices:
- Sinatra
- Hanami

Useful when you need to be able to do this:
Parts of the systems can crash, while others keep working.

Microservice data storage:
- can have a separate database
- can have no separate database

Architecture is:
- Blocks of importance of task solutokns

Reasons to make a microservice block:
- Cost of changes into a block of importance.
- Scaling (during increase of load).
- Reliability of blocks of importance.
- Support.
- Separation of concerns (create/count/push/notify messages)
- Separation of responsibility.
- Group of features on one part of the app.
- Isolate performance of group of features.
- Complex logging of a part of the system.
- Data storage needs different structures.
- Monitoring of a part of the app needs to be separate.
- Separate database.
- When we have a separate support department for just debugging a part of the app.
- When it needs to work on its own subtasks in background jobs.
- Its subtasks are related to the responsibilities of this service.
- When it needs its own load balancer.
- When it needs its own complex caching.
- When it needs its own very specialized security requirements (e.g. a payment processing microservice with its own API)
- When it has its own models (and there's no need to ever access those models from the rest of the app).
- When users need to use a part of the app more often then the rest of the app (esp. with higher requirements to reliability or speed).

Types of architecture:
- Client-Server
- Distributed
- Monolith
- Microservice
- MVC

Each service gets deployed separately.

# Code separation.

Monolith:
- One codebase
- One database
- One deploy

# Monolith First Principle
- Faster development
- More understandable

Microservices:
- Splitted codebase
- Splitted database
- Separate deploy

How many microservices:
< 10 is normal
< 50 is OK if you're very good at it and very big
more is crazy

Communication:
API or GraphQL

With Microservice you need a DevOpts guy in the team.
Because of complex deploys.
