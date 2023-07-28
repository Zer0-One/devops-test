# Hello World

## Dependencies

- [Kind](https://kind.sigs.k8s.io/)
- [Docker](https://docs.docker.com/engine/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)

## Setup

First, build the container image for the application:
```
docker build -t hello-world:v1.0.0 .
```

Next, create a k8s cluster with Kind:
```
kind create cluster --config cluster.yml
```

Load the container image:
```
kind load docker-image hello-world:v1.0.0 -n static
```

Apply the deployment and service configurations:
```
kubectl apply -f site-deployment.yml
kubectl apply -f site-service.yml
```

## Usage

Point your browser to `localhost:30950` and be amazed. Remember to take breaks.
