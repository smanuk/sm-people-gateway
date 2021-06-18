# sm-people-gateway

Gateway for routing client calls to services.  Security will be implemented at this edge node.
* it depends on the sm-people-facade
---
###API Documentation

`curl -s http://localhost:20000/peopleModule/people`

This will give you a list of all the people from the facade,  not there is no API version here as it is controlled bu the gateway.

Another call is:

`curl -s http://localhost:20000/peopleModule/people/23`

There are 4 calls on the facade that you can call from the gateway.


---
