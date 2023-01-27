# Helm
[![Build Status](https://ci2.h8l.io/api/badges/karbon/helm/status.svg?ref=refs/heads/master)](https://ci2.h8l.io/karbon/helm)

## Authors

* h8lio@karbonalpha.com 

## Commands example


helm install keycloak bitnami/keycloak

helm repo add keycloak https://charts.min.io/
helm repo update
helm search repo keycloak
helm show values bitnami/keycloak
helm show values bitnami/keycloak > values.yaml
helm install keycloak bitnami/keycloak -f values.yaml
kubectl logs -f  bitnami/keycloak
kubectl apply -f keycloak.routes.yaml

kubectl port-forward service/mariadb 3307:3306

## Upgrade values
helm upgrade keycloak bitnami/keycloak -f values.yaml
helm upgrade latex ./helm/api-platform --namespace=karbon-meta --install -f ./helm/api-platform/latex.values.yaml

## Get values
helm get values keycloak -o yaml > keycloak_values.yaml

## Docker commands
docker login registry.h8l.io
docker build -t registry.h8l.io/karbon/karbonalpha:latest .
docker push registry.h8l.io/karbon/php-laravel:8.1.23

docker push registry.h8l.io/karbon/php-laravel:3.0.9

docker image tag api-platform-docker-php:latest registry.h8l.io/karbon/api-platform-php:3.0.9
docker image tag api-platform-docker-caddy:latest registry.h8l.io/karbon/api-platform-daddy:3.0.9
docker image tag api-platform-docker-pwa:latest registry.h8l.io/karbon/api-platform-pwa:3.0.9

docker push registry.h8l.io/karbon/api-platform-php:3.0.9
docker push registry.h8l.io/karbon/api-platform-daddy:3.0.9
docker push registry.h8l.io/karbon/api-platform-pwa:3.0.9

## Kube context
kubectx

## Kube switch (ex.)
kubectl config use-context h8lio@karbon-odoo.h8l.io

docker image tag openlogs-node registry.h8l.io/karbon/openlogs-node:latest

## Debug Kubernetes pod
command:
    - /bin/bash
    - '-c'
    - '--'
    args:
    - while true; do sleep 30; done;

## htpassword
kind: Secret
apiVersion: v1
metadata:
  name: openlogs-user
data:
  users: a2FyYm9uYWxwaGE6JGFwcjEkMThoeTczNHEkb25waS9NNks0NFEuZjBRLzEyNEkyLw==

## PostgreSQL oOnnect & commands
psql -U postgres -d postgres

postgres=# create database latex;
CREATE DATABASE
postgres=# create user latex with encrypted password 't3Tlv3xE8mYpoPVI872h';
CREATE ROLE
postgres=# grant all privileges on database latex to latex;
GRANT
postgres=# \l


## Helm api-platform
helm upgrade latex ./helm/api-platform --namespace=karbon-meta --install -f ./helm/api-platform/latex.values.yaml

## Hack kubernetes = How can I keep a container running on Kubernetes ?
# https://stackoverflow.com/questions/31870222/how-can-i-keep-a-container-running-on-kubernetes
apiVersion: v1
kind: Pod
metadata:
  name: ubuntu
spec:
  containers:
  - name: ubuntu
    image: ubuntu:latest
    # Just spin & wait forever
    command: [ "/bin/bash", "-c", "--" ]
    args: [ "while true; do sleep 30; done;" ]


    	"php-cors-allow-origin": "^https?://.*?\\.karbonmeta\\.com$",

      {
	"mercure-public-url": "https://mercure.karbonmeta.com/.well-known/mercure",
	"mercure-url": "http://latex-api-platform/.well-known/mercure",
	"php-app-debug": "0",
	"php-app-env": "prod",
	"php-cors-allow-origin": "^https?://.*?\\.karbonmeta\\.com$",
	"php-trusted-hosts": "^127\\.0\\.0\\.1|localhost|.*\\.karbonmeta\\.com$",
	"php-trusted-proxies": "127.0.0.1,10.0.0.0/8,172.16.0.0/12,192.168.0.0/16"
}