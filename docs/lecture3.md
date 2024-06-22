How to stracture the app (since we don't get Rails structure anymore)

Don't stick to Rails structure.
Do just enough to solve the goal.

Things to solve:
- Code structure
- Endpoints
- DB connection
- Configs
- Testing

Usual tools:
- Sinatra (basic app)
- dry-rb (validations of controller params, etc)
- config (store app settings in yml files)
- sequel (minimalistic activerecord replacement)
- fastjson_api (generating fast responses)

Demo of writing the microservice.

Since we don't have Rails - we don't have "automagic" stuff.
We have to write a lot of system things on our own.
