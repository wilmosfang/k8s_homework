# k8s_homework

## create env

```
kubectl create namespace dev
kubectl create namespace uat
kubectl create namespace prod
```
## deploy in dev or uat env

```
cd dockercoins_dev_uat/
helm install ./ --name <chatname> --set environment=<dev|uat> --set image.name=<worker|rng|redis|hasher|webui>
```

eg.

```
cd dockercoins_dev_uat/
helm install ./ --name worker-dev --set environment=dev --set image.name=worker  --dry-run --debug
helm install ./ --name worker-dev --set environment=dev --set image.name=worker
```

## deploy in prod env

```
cd dockercoins
helm install ./ 
```

eg.

```
cd dockercoins/
helm install ./  --dry-run --debug
helm install ./ 
```

## access url


* dev-webui.192.168.33.101.nip.io
* uat-webui.192.168.33.101.nip.io
* webui.192.168.33.101.nip.io

```
root@master01:~/fz/dockercoins# kubectl get ingress
NAME                HOSTS                             ADDRESS   PORTS   AGE
dev-webui-ingress   dev-webui.192.168.33.101.nip.io             80      29m
uat-webui-ingress   uat-webui.192.168.33.101.nip.io             80      128m
webui-ingress       webui.192.168.33.101.nip.io                 80      34s
root@master01:~/fz/dockercoins# 
```
