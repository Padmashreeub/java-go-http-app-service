# Go-Java-App

Used istio service mesh, configured to laodbalance traffic as per 70:30 rule, enabled addons like prometheus, grafana for monitoring and observability.
Added readiness and liveness probes, redirected homepage to ```/hotels``` page, added horozontal pod autscaler for autoscalling

## Deployemnt

1) Build docker files using the steps in the next section.
2) Install istio using ```https://istio.io/latest/docs/setup/getting-started/```
3) Deploy app using kubernetes manifests from ```kubernetes``` folder using ```kubectl create -f .```.


## Building Dockerfiles

Build dockerfiles from ```docker/go``` and ```docker/java``` by executing ```docker build -t golang-webserver:latest .``` and ```docker build -t java-webserver:latest .``` respectively

## Kubernetes Manifests

- java_deployment.yaml -> Deployment for java application
- go_deployment.yaml -> Deployment for go application
- go_service.yaml -> Service for go application
- java_service.yaml -> Service for java application
- autoscaler-java.yaml -> Autoscaler for java application
- autoscaler-go.yaml -> Autoscaler for go application
- http-app-gateway.yaml -> Gateway for both application in istio

## Directory structure

```bash
 |-docker
 | |-go
 | | |-golang-webserver
 | | |-Dockerfile
 | |-java
 | | |-Dockerfile
 | | |-java-webserver.jar
 |-kubernetes
 | |-autoscaler-go.yaml
 | |-docker
 | | |-go
 | | | |-golang-webserver
 | | | |-Dockerfile
 | | |-java
 | | | |-Dockerfile
 | | | |-java-webserver.jar
 | |-java_deployment.yaml
 | |-http-app-gateway.yaml
 | |-autoscaler-java.yaml
 | |-java_service.yaml
 | |-go_deployment.yaml
 | |-go_service.yaml
 ```

