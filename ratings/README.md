## BookInfo Application - Ratings
> Ratings is a Javascript microservice which fetches ratings from a MySQL Database.
Update the root password variable in the Dockerfile and create a docker image.
```
cd ratings/mysql
docker build -t ratings-mysql .
docker tag ratings-mysql ACCOUNT.dkr.ecr.ap-south-1.amazonaws.com/ratings-mysql:v1.0
docker push ACCOUNT.dkr.ecr.ap-south-1.amazonaws.com/ratings-mysql:v1.0
```
Push the docker image for ratings as well. Update the deployment manifests with the Database Credentials.
```
cd ratings
docker build -t ratings .
docker tag ratings-mysql ACCOUNT.dkr.ecr.ap-south-1.amazonaws.com/ratings:v1.0
docker push ACCOUNT.dkr.ecr.ap-south-1.amazonaws.com/ratings:v1.0
```
Update the images in deployment manifest in k8s directory and execute the below command to deploy.
```
kubectl apply -f k8s/mysql-deployment.yaml
kubectl apply -f k8s/mysql-service.yaml
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```
