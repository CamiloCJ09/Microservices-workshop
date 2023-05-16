Start the infrastructure
This workshop requires a couple of extra technical services (databases, kafka…​). Start them using the docker-compose.yaml file located in the infrastructure directory:

$ cd infrastructure
$ docker compose up


Running the complete system
Run the infrastructure and build the complete system as explained above.

In a new terminal, run the heroes microservice

$ cd rest-heroes
$ mvn clean compile quarkus:dev
In a new terminal, run the villains microservice

$ cd rest-villains
$ mvn clean compile quarkus:dev
In a new terminal, run the fights microservice

$ cd rest-fights
$ mvn clean compile quarkus:dev
In a new terminal, run the fights microservice

$ cd event-statistics
$ mvn clean compile quarkus:dev

Run the front

docker run -p 8080:8080 -e API_BASE_URL=http://localhost:8082 quay.io/quarkus-super-heroes/ui-super-heroes:latest