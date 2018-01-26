# drqik

## Overview
This is a sample project for preparing a development environment for a ruby on rails applications using docker.

The environment also includes PostgreSQL, Redis Databases and Sidekiq configured to work alongside with the rails application.

Running this project you will end-up with 4 containers for each of the components.

## Prerequisites
* Docker
* Docker Compose

## Running the Environment
1. Clone the project into your workspace.
2. Create the following volumes for PostgreSQL and Redis:
    > docker volume create --name drkiq-postgres
    > docker volume create --name drkiq-redis
3. Start the environment with docker-compose:
    > docker-compose up

## Development Keys
* Generating a new controller:
    > docker-compose run --user "$(id -u):$(id -g)" drkiq rails g controller Pages home
* Adding new job:
    > docker-compose run --user "$(id -u):$(id -g)" drkiq rails g job counter

## Modifying the Environment
To modify the environment you may need to modify the following components:
* `Dockerfile`: the basic docker module that holds the rails application and sidekiq.
* `docker-compose.yml`: the basic module for running all 4 components.


