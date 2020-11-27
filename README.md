# hydra-synchron-svcs
A [Hydra-based](https://github.com/pnxtech/hydra) Synchronization Service.

Supporting delayed message dispatching for periodic task seqeuencing and job scheduling. Backed by MongoDB.

<img src="documentation/assets/synchron.png" width="300px" />

## Intended use

The Synchron service is intended for use in its docker container form and deployed to a Docker Swarm or Kubernetes cluster. Available container images are hosted on [Docker Hub](https://hub.docker.com/repository/docker/pnxtech/hydra-synchron-svcs).

## Raison d'être

This service exists to solve the following key distributed computing problem.

> "How does a microservice type (with many instances) perform singular periodic tasks while avoiding the duplication of work?"

Consider:
  * If you put a timer inside of a microservice so that it can execute periodic tasks - then how do you prevent multiple instances of that service for each performing the same periodic task?
  * How do you ensure that the scheduled task executes on time?

Why not just use a job service? With Hydra, job / task queuing is present by default.  So microservices can queue tasks for themselves or each other - at will.  The problem this service solves is one of the creation and management of system-wide periodic orchestration events.

### See full [documentation](./documentation/README.md)
