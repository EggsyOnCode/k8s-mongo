# K8s-mongo
An exercise in building a minikube Kubernetes cluster comprising of 
- mongo-express
- mongodb

## Architecutre 
![image](https://github.com/EggsyOnCode/k8s-mongo/assets/77304003/46609c7e-6f8d-474e-a5c4-0f0875a2ae5c)

## Sequence Diagram
![image](https://github.com/EggsyOnCode/k8s-mongo/assets/77304003/a1d64141-33e1-49b4-801a-b8811d7da6c2)


## Steps to deploy
- Setup a mongo-secrets.yaml file having the follwoing format
```yaml
apiVersion: v1
kind: Secret
metadata:
  name: mongodb-secret
type: Opaque
data:
  # data needs to be inputted in base64 form
  # on unix; type echo -n 'textToBeEncoded' | base64
  mongo-root-username: # ur username
  mongo-root-password: # ur pwd
```
- Create the secrets file using
```bash
kubectl apply -f mongo-secrets.yaml
```
- Create mongo.yaml using kubectl apply
- Create mongo-configMap.yaml
- Create mongo-express.yaml
- Start minikube service using
```bash
minikube service mongo-express-service
```


## Connection and Execution
![image](https://github.com/EggsyOnCode/k8s-mongo/assets/77304003/f7c77f87-7094-4195-83bf-ae3916dfd1c7)
