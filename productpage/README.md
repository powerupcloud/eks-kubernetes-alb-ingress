## BookInfo Application - ProductPage
> ProductPage is a Python microservice which calls the details and reviews to populate the page. It is the frontend of the application.
```
cd productpage
docker build -t productpage .
docker tag productpage ACCOUNT.dkr.ecr.ap-south-1.amazonaws.com/productpage:v1.0
docker push ACCOUNT.dkr.ecr.ap-south-1.amazonaws.com/productpage:v1.0
```
Update the image in the deployment manifest in k8s directory and execute the below command to deploy:
```
kubectl apply -f k8s
```
