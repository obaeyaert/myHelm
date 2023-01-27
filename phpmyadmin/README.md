helm install wordpress bitnami/wordpress

helm repo add wordpress https://charts.min.io/
helm repo update
helm search repo wordpress
helm show values bitnami/wordpress
helm show values bitnami/wordpress > values.yaml
helm install wordpress bitnami/wordpress -f values.yaml
kubectl logs -f  bitnami/wordpress
kubectl apply -f wordpress.routes.yaml

kubectl port-forward service/wordpress 3306:3307

helm upgrade wordpress bitnami/wordpress -f values.yaml