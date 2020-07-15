# EKS Canary

This repo contains sample for creating a canary without the need of a service mesh. We will leverage AWS Application load balancer + ALB ingress controller to split traffic into multiple Youservices.

## Prerequisite

Please install (ALB ingress controller)<https://kubernetes-sigs.github.io/aws-alb-ingress-controller/guide/walkthrough/echoserver/> if that isn't already part of your cluster.

## How to use

We will identify echoserver as our production deployment.
[Prod](./echoserver.yaml)

And canary as our canary environment.
[Canary](./echoserver-canary.yaml)

Apply them to your cluster.

```bash
kubectl apply -f ./echoserver.yaml
kubectl apply -f ./echoserver-canary.yaml
```

Check that they are working by checking pods are in Running state and all services have endpoints

```bash
kubectl get pods
kubectl get endpoints
```
[podsandservicestatus](./images/podssvcstatus.png)
