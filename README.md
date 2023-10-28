## Project : MongoDB & MongoExpress 

### Create mongoDB Deployment & Service 

Create secrets to access mongodb 
  - echo -n 'username' | base64
  - echo -n 'password' | base64
Secret must be created before deployment
 - kubectl apply -f mongo-secret.yaml
 - kubectl get secret
 - Reference the secrets in deployment 

deploy mongodb pod
 -  kubectl apply -f mongodb-deployment.yaml 
 -  kubectl get pod --watch
 -  kubectl describe pod <pod-name>


Create Mongodb internal service so that other components can talk to mongo db

k apply -f mongodb-deployment.yaml
k get service
k describe service mongodb-service & verify service end pointsIP address with pod ip 
k get pod -o wide
k get all | grep mongodb

Create ConfigMap
k apply -f mongo-configmap.yaml

Deploy Mongo express 
k apply -f mongo-express.yaml
k get pod
k logs <pod-name>  to check if the connection is extablished 



Access Mongo Express from browser 
Create external service for mongo express 

