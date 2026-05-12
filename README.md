# Imperative Management
```sh
# Create kubernetes object
$ kubectl create -f namafile.yaml
```

```sh
# Update kubernetes object
$ kubectl replace -f namafile.yaml
```

```sh
# View kubernetes object can be yaml or json
$ kubectl get -f namafile.yaml -o yaml
```

```sh
# Delete kubernetes object
$ kubectl delete -f namafile.yaml
```

# Declarative Management
```sh
# Create or update kubernetes object
$ kubectl apply -f namafile.yaml
```

# Kubernetes Rollout
```sh
# View history rollout
$ kubectl rollout history object name
```

```sh
# Mark as pause
$ kubectl rollout pause object name
```

```sh
# Resume pause
$ kubectl rollout resume object name
```

```sh
# Restart rollout
$ kubectl rollout restart object name
```

```sh
# View status rollout
$ kubectl rollout status object name
```

```sh
# Undo to rollout before
$ kubectl rollout undo object name
```

# Deployment Kubernetes Dashboard
```sh
$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml
```

# Check Pod Dashboard Running
```sh
$ kubectl get pods -n kubernetes-dashboard
```

# Run Proxy Dashboard from Browser
```sh
$ kubectl proxy
```

# Open to Browser
Link: http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#/workloads?namespace=_all

# Create User Kubernetes
```sh
$ kubectl apply -f admin-user.yaml
```

# Cluster Role Binding
```sh
$ kubectl create clusterrolebinding admin-user-binding --clusterrole=cluster-admin --serviceaccount=kubernetes-dashboard:admin-user
```

# Get Token Kubernetes
```sh
$ kubectl -n kubernetes-dashboard create token admin-user
```

# Get Token Kubernetes with Describe Secret
```sh
$ kubectl describe secret admin-user-secret -n kubernetes-dashboard
```