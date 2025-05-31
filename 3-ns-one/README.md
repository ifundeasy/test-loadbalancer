kubectl apply -f namespace.yaml
kubectl delete -f grpc-server
kubectl delete -f grpc-client-balanced
kubectl apply -f grpc-server
kubectl apply -f grpc-client-balanced
kubectl scale deployment grpc-server --replicas=2 -n ns-one
kubectl get pods -n ns-one
