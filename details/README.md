## BookInfo Application - Details
> Details is a Ruby microservice which contains book information.
```
cd details
docker build -t details .
docker tag details ACCOUNT.dkr.ecr.ap-south-1.amazonaws.com/details:v1.0
docker push ACCOUNT.dkr.ecr.ap-south-1.amazonaws.com/details:v1.0
```
Update the image in the deployment manifest in k8s directory and execute the below command to deploy:
```
kubectl apply -f k8s
```
