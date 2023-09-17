# ADR-002: Use of an API layer as the externally accessible interface to the system

The proposed architecture for The Road Warrior consists of a set of cohesive services exposing interfaces to be consumed by client applications as well as other services. We define a consumer to be external if it is invoked from outside the boundaries of the network where the service is hosted (on premises LAN, VPN or the network of a single cloud services provider).

## Status
Accepted

## Decision
The Road Warrior platform is meant to be accessed primarily via web browsers and mobile apps by external users. The architecture consists of containerized services encapsulating multiple components , each with their own interfaces. Only a subset of these interfaces are meant to be consumed by external users. Instead of each service exposing it's functionality directly to external users, we need to make those relevant interfaces accessible only through the API layer.

## Consequences
The API layer can be used to cross cutting concerns like load balancing, logging and monitoring, authentication and allows us to decouple the UI from backend services

However this comes with a development overhead of creating and maintaining an additional service. There is also the possibility of increased latency due to API layer having to route requests to target service