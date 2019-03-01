## BookInfo Application - Reviews
> Review is a Java Microservice whch contains book reviews. It calls the ratings microservice.
Ensure to install java and gradle on the server before proceeding with the deployment.
```
cd reviews
gradle clean build
cd reviews-wlpcfg
docker build -t reviews .
docker tag productpage ACCOUNT.dkr.ecr.ap-south-1.amazonaws.com/reviews:v1.0
docker push ACCOUNT.dkr.ecr.ap-south-1.amazonaws.com/reviews:v1.0
```
Update the image in the deployment manifest in k8s directory and execute the below command to deploy:
```
kubectl apply -f k8s
```
