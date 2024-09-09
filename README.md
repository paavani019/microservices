# Microservices Assignment : Setup & Deployment
This project involves setting up 2 microservices using Visual Studio Code, Spring Tool Suite, Docker and Kubernetes. The services were built, containerized, and deployed on a local Kubernetes cluster using Minikube.

**Setup and Installations**
Programming Language & Framework: Java with Spring Boot.
Tools: JDK, Maven, Spring Tool Suite 4 IDE.
Version Control: Git repository for source code management.

**Microservices Creation**
- Generated starter projects for Hello and World services using Spring Initializr.
_Hello Service Implementation:_
Endpoint: /hello
Functionality: Returns the string "Hello."
Implementation: Created HelloController.java with a hello() method using @GetMapping("/hello").
Testing: Added JUnit tests in CheckHTTPResponse.java.

_World Service Implementation:_
Endpoint: /world
Functionality: Returns the string "World."
Implementation: Created WorldController.java with a world() method using @GetMapping("/world").
Testing: Implemented JUnit tests similar to the Hello Service.

_Local Testing_
Compiled and ran both services locally on ports 9095 (Hello) and 8095 (World).
Verified the output through local testing.
Containerization with Docker

_Docker Setup_
Created Dockerfiles for Hello and World services, exposing ports 9095 and 8095, respectively.
Built the Docker images using:
bash
Copy code
docker build -t hello .
docker build -t world .
Ran the Docker images locally:
bash
Copy code
docker run -p 9090:8080 hello:latest
docker run -p 9091:8081 world:latest
Tested the Docker images independently on ports 9090 (Hello) and 9091 (World).

_Push to Docker Hub_
Pushed the images to Docker Hub using:
bash
Copy code
docker tag hello:latest <dockerhub-username>/hello
docker tag world:latest <dockerhub-username>/world
docker push <dockerhub-username>/hello
docker push <dockerhub-username>/world
Deployment on Kubernetes
Google Kubernetes Engine (GKE) Setup
Acquired a free Google Cloud subscription and created Kubernetes clusters for Hello and World services.
Created k8s-hello.yaml and k8s-world.yaml for deployment and service configuration.
Deployed both services to GKE using:
bash
Copy code
kubectl apply -f k8s-hello.yaml
kubectl apply -f k8s-world.yaml
Verified the services were externally accessible:
Hello Service: http://34.172.139.242:8080/hello
World Service: http://34.134.15.68:8081/world
Creation of HelloWorld Service, Integration, and Testing

**Service Integration**
Integrated Hello and World services into a single service within the Hello microservice.
Created HelloWorldService with a /helloworld endpoint that returns "Hello World."
Configuration

Added a RestTemplate bean in AppConfig class to facilitate REST calls.
Defined external service URLs in application.properties for the Hello microservice.
Deployment

Rebuilt and pushed the updated Docker image to Docker Hub.
Redeployed the Hello service on GKE.

**Conclusion**
This project demonstrates a microservices architecture using Spring Boot, Docker, and Kubernetes.
Both Hello and World services were successfully containerized and deployed on GKE, showcasing microservices communication and cloud deployment.
Repository and Docker Hub Links

## Docker Images
are available in Docker Hub at : -
Hello Microservice: https://hub.docker.com/repository/docker/paavanikaruturi/hello-microservice/general

World Microservice: https://hub.docker.com/repository/docker/paavanikaruturi/world-microservice/general

![image](https://github.com/user-attachments/assets/ec7b8734-1245-4534-9c1d-49b01cc5fc20)

![image](https://github.com/user-attachments/assets/6e60564f-e7a9-48cb-91c0-b9bb39eb84ed)


# Docker images
![image](https://github.com/user-attachments/assets/189cf172-680e-466c-90ff-9a804f167d8b)
