# Prometheus Avalanche load testing - local vs m3db

### Before installing

Make sure you have the following installed (required for running locally)

* docker (mandatory)
* minikube (mandatory)
* kubectl (mandatory)
* socat (required for port forwarding)

I would advise to run minikube directly over docker without the need of additional Hypervisor layer
```sh
$ sudo minikube start --vm-driver=none
```


### Installation

Please execute in the following order

```sh
$ kubectl apply -f ./k8s/prometheus-operator/
$ kubectl apply -f ./k8s/avalanche-standalone/
$ kubectl apply -f ./k8s/prometheus-standalone-local/
$ kubectl -n apps port-forward prometheus-prometheus-standalone-local-0 9090
```
Targets should be populated and visible avalanche via Service Discovery.

## TODO M3DB k8s descriptors
## TODO k8s prometheus-standalone-remote on top of m3db remote
## TODO Grafana remote m3db metrics with 2 data sources
