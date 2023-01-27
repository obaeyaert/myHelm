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



Mexico travel poster, lucha libre, wrestling, lucha libre mask, palm trees, Spanish-colonial architecture, rough cut outs, collage, trippy, grain, screen print, block colours, secondary colours, Jesse draxler, Quentin Jones, Andrew mcgranaham, neon pastel colours, ripped paper, mixed media, screen print —w 1920 —h 1080

People playing bowling, wine bottles instead of skittles, old french poster style --ar 3:2

giant bottle of wine in the center of a vineyard, skittle on bottle label, ghibli style, sun in blue sky, pines and oaks, --ar 3:2