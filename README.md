# EKS Canary

This repo contains sample for creating a canary without the need of a service mesh. We will leverage AWS Application load balancer + ALB ingress controller to split traffic into multiple services.

# How to use

We will identify echoserver as our production deployment. [deployment](./echoserver.yaml) [service](service.yaml)
And canary as our canary environment. [deployment](./echoserver-canary.yaml) [service](service-canary.yaml)

Apply them to your cluster.

```bash
kubectl apply -f ./*
```
