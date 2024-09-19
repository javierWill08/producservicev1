# REST Product-Service
```
Construye la imagen Docker:

```
docker build -t product-service .
```
Ejecuta el contenedor Docker:
```
docker run -d --name product-service -p 3000:3000 --env-file .env product-service
```

## Uso de la API

1. Test Health

URL: http://localhost:3000/api/health
Método: get
Body: JSON (raw)


minikube config set insecure-registry "localhost.local:5000"
minikube start --driver=docker --insecure-registry="localhost.local:5000" --listen-address="0.0.0.0"
minikube docker-env
minikube -p minikube docker-env
minikube image build -t product-service:test001 .
kubectl port-forward deployment.apps/product-service  13000:3000

docker build --tag=product-service:test002 .
kubectl create deployment product-service002 --image=product-service:test002
kubectl expose pod "product-service002" --type=NodePort --port=8080


docker run -d -p 5000:5000 --restart=always --volume ~/.registry/storage:/var/lib/registry registry:2
https://gist.github.com/trisberg/37c97b6cc53def9a3e38be6143786589

docker container ls
docker build -t product-service .
docker build -t localhost.local:5000/product-service:latest .
docker tag product-service localhost.local:5000/product-service
docker push localhost.local:5000/product-service
docker push localhost.local:5000/product-service:latest
docker run -d -p 3000:3000 --env-file .env --name product-service localhost.local:5000/product-service:latest

http://localhost:5000/v2/_catalog

minikube image ls | grep localhost.local:5000/product-service
minikube image load localhost.local:5000/product-service:latest
minikube image load localhost.local:5000/product-service

kubectl create deployment product-service --image=localhost.local:5000/product-service:test001
kubectl scale deploy product-service --replicas=5

kubectl run product-service-pod --image=product-service:latest

kubectl expose pod product-service-pod --port=3000 --name=product-service-pod-svc --type="NodePort"
http://<minikube-ip>:<NodePort>.
curl http://192.168.49.2:31232