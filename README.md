#Three microservices - used Python, Django, Java, Spring, Redis, RabbitMQ

## App1:
Coded with Python and Django Framework. An application provide /post [POST] endpoint which accepts all JSONs. If request is correct, it returns JSON's data, else it returns status code - 400.
When data is parsed, producer sends it to the RabbitMQ query.

## App2:
Consumer - coded with Python and Django framework. It waits for a message to be send to query and adds new key to the Redis database. Liveness probe set to 60 s.

## App3:
Coded with Java and Spring Framework. An application provide /get [GET] endpoint which returns the number of all keys in Redis database.
