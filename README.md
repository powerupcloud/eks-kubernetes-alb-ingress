<img src="https://github.com/piu28/eks-kubernetes-network-policy/blob/master/images/amazon-eks.png" align="right" />

# eks-kubernetes-alb-ingress
> More Info on ALB Ingress Controller: https://github.com/kubernetes-sigs/aws-alb-ingress-controller

### RBAC:
```
kubectl apply -f rbac-role.yaml
```

### ALB-Ingress-Controller:
Update the following variables in the alb-ingress-controller.yaml:
* EKS_CLUSTER_NAME
* VPC ID
* REGION where EKS cluster exists.
* Subnets and Security Group IDs to attach to the LoadBalancer.

Execute the below command to apply the config:
```
kubectl apply -f alb-ingress-controller.yaml
```

### Updating microservices code to use HTTPS for accessing the other services:

