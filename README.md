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

Execute the below command to apply the config:
```
kubectl apply -f alb-ingress-controller.yaml
```

### Updating microservices code to use HTTPS for accessing the other services:
The Services Endpoints are modified with HTTPS in the below files:
* reviews/reviews-application/src/main/java/application/rest/LibertyRestEndpoint.java
* productpage/productpage.py
* productpage/tests/unit/test_productpage.py

### Ingress
We have defined two ingress:
* One for the External Service which is the frontend and is exposed to the public.
* Another one for the Internal services where frontend will connect in the backend. The Internal services are not exposed to public.

Update the following values in both the ingress files:
* Subnets and Security Group IDs to attach to the LoadBalancer.
* ARN of the ACM Certificate that is issued to the domains.
* S3 Bucket Name to enable ALB access logs.
* Domain Names for the services.
```
kubectl apply -f external-ingress.yaml
kubectl apply -f internal-ingress.yaml
```
