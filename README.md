
# K8S + .NET 

A simple project to apply the basics of Kubernetes.

## How to start

Clone

```bash
  git clone https://github.com/SauloAlmeida/kubernetes-dotnet
```

Go to directory

```bash
  cd kubernetes-dotnet
```

Go to api folder and build the image

```bash
  cd src
  docker build -t <docker_hub_account>/k8s-dotnet .
```

Push to container registry

```bash
  docker push <docker_hub_account>/k8s-dotnet
```

Go to K8S folder

```bash
  cd ..
  cd K8S
  kubectl apply -f api-deploy.yaml
```

To delete
```bash
  kubectl delete deployment api-deployment
```