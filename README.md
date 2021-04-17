## nsq_kubernetes

# Installation
```
kubectl apply -f nsqd-deployment.yaml
kubectl apply -f nsqd-service.yaml
kubectl apply -f nsqlookupd-deployment.yaml
kubectl apply -f nsqlookupd-service.yaml
kubectl apply -f nsqdadmin-deployment.yaml
kubectl apply -f nsqdadmin-service.yaml
kubectl apply -f ingress.yaml
```

# Testing
```
kubectl run curl --image=radial/busyboxplus:curl -i --tty
curl -d 'hello world 1' 'nsqd-service.default.svc.cluster.local:4151/pub?topic=test'
```

Check the NSQ Admin page for results
```
kubectl get svc,ingress
```
Enter *ingress_address* into internet browser
