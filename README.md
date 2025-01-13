Kubernetes Load Balancer Project

This project demonstrates how to create a Kubernetes-based load balancer using Minikube. The setup includes two backend services (Backend 1 and Backend 2), an Nginx-based load balancer, and external access via a Kubernetes LoadBalancer service.
Project Architecture

Components:

Backend Deployments:

backend1 and backend2 deployments each have a single pod.

Pods respond with Hello from Backend 1 or Hello from Backend 2 respectively.

ClusterIP Services:

backend1-service and backend2-service expose the backend deployments internally.

Nginx Load Balancer:

A Deployment with a single Nginx pod.

Configured using a ConfigMap to load balance traffic between the backend services.

LoadBalancer Service:

Exposes the Nginx pod to external traffic.

Prerequisites

Minikube installed and running.

Kubernetes CLI (kubectl) installed.

Basic understanding of Kubernetes concepts.

kubectl apply -f backend1.yaml
kubectl apply -f backend2.yaml

kubectl apply -f nginx-config.yaml
kubectl apply -f nginx-load-balancer.yaml
kubectl apply -f nginx-load-balancer-service.yaml

minikube service nginx-load-balancer-service
