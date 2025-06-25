# This project has two microservices behind nginx reverse proxy containerized using Docker compose



# Prerequisites:
-Docker

# To run the project use:
docker-compose up --build



# How routing works:

Nginx acts as a reverse proxy and routes traffic based on URL path prefixes:

http://localhost:8080/service1/hello or /ping is routed to service_1 (Go based)

http://localhost:8080/service2/hello or /ping is routed to service_2 (uv based)

# Have set up service healthchecks:

http://localhost:8080/service1/health ---> service1 healthchecks

http://localhost:8080/service2/health ---> service2 healthchecks




