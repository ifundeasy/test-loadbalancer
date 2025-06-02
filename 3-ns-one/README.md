cd 3-ns-one
kubectl config use-context kind-locale
kubectl config current-context

kubectl apply -f namespace.yaml
kubectl apply -f grpc-server
kubectl apply -f grpc-client
kubectl apply -f grpc-client-balanced
kubectl scale deployment grpc-server --replicas=3 -n ns-one
kubectl get pods -n ns-one

kubectl delete -f grpc-server
kubectl delete -f grpc-client
kubectl delete -f grpc-client-balanced
kubectl delete -f namespace.yaml