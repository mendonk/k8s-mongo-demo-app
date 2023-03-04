# k8s-mongo-demo-app
Mongo DB and Mongo Express with external loadbalancer. 

Just a demo app for my own learning.

Run it: 

# apply secrets
kubectl apply -f mongo-secret.yaml

# apply mongo-db as internal pod 
kubectl apply -f mongo.yaml

# apply configmap so mongo express (external) can talk to mongo-db (internal)
kubectl apply -f mongo-configmap.yaml

# apply mongo express with external loadbalancer
kubectl apply -f mongo-express.yaml

If you run it on minikube you should get an output as below, and you can access Mongo Express at the listed LoadBalancer URL. 

```
➜  minikube service mongo-express-service
|-----------|-----------------------|-------------|---------------------------|
| NAMESPACE |         NAME          | TARGET PORT |            URL            |
|-----------|-----------------------|-------------|---------------------------|
| default   | mongo-express-service |        8081 | http://192.168.49.2:30000 |
```
