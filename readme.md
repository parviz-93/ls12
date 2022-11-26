Create cred for private dockerhub rep

`kubectl create secret generic doccred \
    --from-file=.dockerconfigjson=<path/to/.docker/config.json> \
    --type=kubernetes.io/dockerconfigjson`

`kubectl create secret generic doccred --from-file=.dockerconfigjson=<path/to/.docker/config.json> --type=kubernetes.io/dockerconfigjson`

Encode base64
`echo -n 'my-string' | base64`
`base64 /path/to/file`

Get resource
`kubectl get secret doccred --output=yaml`


Get networkd
`docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' d05a6a7ee2da`

Create link
`docker network connect --alias alias_name network_name container_id`
`docker network connect --alias k8s minikube d05a6a7ee2da`
