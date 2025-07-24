# 🧠 Kubernetes CLI Cheatsheet

## 🚀 Cluster & Context Management

| # | Command | Description |
|--|--|--|
| 1 | `kubectl version` | Show client/server versions |
| 2 | `kubectl cluster-info` | Display cluster endpoints |
| 3 | `kubectl config view` | View kubeconfig details |
| 4 | `kubectl config get-contexts` | List available contexts |
| 5 | `kubectl config current-context` | Show current context |
| 6 | `kubectl config use-context <name>` | Switch context |
| 7 | `kubectl config set-context --current --namespace=<ns>` | Set default namespace |
| 8 | `kubectl config set-cluster <name>` | Define cluster in kubeconfig |
| 9 | `kubectl config set-credentials <user>` | Add user credentials |
| 10 | `kubectl config unset <property>` | Remove config entry |

## 🧠 Node Management

| # | Command | Description |
|--|--|--|
| 1 | `kubectl get nodes` | List all nodes |
| 2 | `kubectl describe node <name>` | Node details |
| 3 | `kubectl cordon <name>` | Mark node unschedulable |
| 4 | `kubectl uncordon <name>` | Mark node schedulable |
| 5 | `kubectl drain <name>` | Evict pods for maintenance |
| 6 | `kubectl top node` | Show node resource usage |
| 7 | `kubectl label node <name> key=value` | Add label to node |
| 8 | `kubectl taint nodes <name> key=value:NoSchedule` | Taint node |
| 9 | `kubectl get nodes -o wide` | Extended node info |
| 10 | `kubectl get nodes --show-labels` | Show node labels |

## 📦 Namespace Management

| # | Command | Description |
|--|--|--|
| 1 | `kubectl get namespaces` | List namespaces |
| 2 | `kubectl create namespace <name>` | Create namespace |
| 3 | `kubectl delete namespace <name>` | Delete namespace |
| 4 | `kubectl describe namespace <name>` | Namespace details |
| 5 | `kubectl edit namespace <name>` | Edit namespace |

## 📁 Resource Creation & Management

| # | Command | Description |
|--|--|--|
| 1 | `kubectl apply -f <file.yaml>` | Apply config |
| 2 | `kubectl create -f <file.yaml>` | Create from file |
| 3 | `kubectl create deployment <name> --image=<img>` | Create deployment |
| 4 | `kubectl create service clusterip <name> --tcp=80:80` | Create service |
| 5 | `kubectl explain <resource>` | Show resource schema |

## 🔍 Viewing & Describing Resources

| # | Command | Description |
|--|--|--|
| 1 | `kubectl get <resource>` | List resources |
| 2 | `kubectl get <resource> -o wide` | Extended info |
| 3 | `kubectl get <resource> -n <ns>` | In specific namespace |
| 4 | `kubectl get <resource> --all-namespaces` | Across all namespaces |
| 5 | `kubectl describe <resource> <name>` | Detailed info |
| 6 | `kubectl get <resource> -l key=value` | Filter by label |
| 7 | `kubectl get <resource> --field-selector=key=value` | Filter by field |
| 8 | `kubectl get events --sort-by=.metadata.creationTimestamp` | Recent events |
| 9 | `kubectl api-resources` | List resource types |
| 10 | `kubectl api-versions` | List API versions |

## 🧹 Deleting Resources

| # | Command | Description |
|--|--|--|
| 1 | `kubectl delete <resource> <name>` | Delete resource |
| 2 | `kubectl delete -f <file.yaml>` | Delete from file |
| 3 | `kubectl delete <resource> --all` | Delete all of type |
| 4 | `kubectl delete <resource> -l key=value` | Delete by label |
| 5 | `kubectl delete pod <name> --grace-period=0 --force` | Force delete pod |

## 🧬 Pod Management

| # | Command | Description |
|--|--|--|
| 1 | `kubectl get pods` | List pods |
| 2 | `kubectl describe pod <name>` | Pod details |
| 3 | `kubectl logs <pod>` | View logs |
| 4 | `kubectl logs -f <pod>` | Stream logs |
| 5 | `kubectl logs <pod> -c <container>` | Logs from container |
| 6 | `kubectl exec -it <pod> -- /bin/bash` | Shell into pod |
| 7 | `kubectl port-forward <pod> 8080:80` | Forward port |
| 8 | `kubectl attach <pod>` | Attach to pod |
| 9 | `kubectl delete pod <name>` | Delete pod |
| 10 | `kubectl get pod -n <ns>` | Pods in namespace |

## 📈 Deployment & Rollout

| # | Command | Description |
|--|--|--|
| 1 | `kubectl get deployments` | List deployments |
| 2 | `kubectl describe deployment <name>` | Deployment details |
| 3 | `kubectl rollout status deployment/<name>` | Rollout status |
| 4 | `kubectl rollout undo deployment/<name>` | Rollback |
| 5 | `kubectl set image deployment/<name> <container>=<image>` | Update image |
| 6 | `kubectl scale deployment <name> --replicas=<n>` | Scale deployment |
| 7 | `kubectl edit deployment <name>` | Edit deployment |
| 8 | `kubectl get rs` | List ReplicaSets |
| 9 | `kubectl get hpa` | List autoscalers |
| 10 | `kubectl autoscale deployment <name> --min=2 --max=5 --cpu-percent=80` | Create HPA |

## 🧪 Job & CronJob Management

| # | Command | Description |
|--|--|--|
| 1 | `kubectl create job <name> --image=<img> -- <cmd>` | Create job |
| 2 | `kubectl get jobs` | List jobs |
| 3 | `kubectl describe job <name>` | Job details |
| 4 | `kubectl delete job <name>` | Delete job |
| 5 | `kubectl create cronjob <name> --image=<img> --schedule="*/1 * * * *" -- <cmd>` | Create cronjob |
| 6 | `kubectl get cronjobs` | List cronjobs |
| 7 | `kubectl delete cronjob <name>` | Delete cronjob |

## 🔐 Secrets & ConfigMaps

| # | Command | Description |
|--|--|--|
| 1 | `kubectl create secret generic <name> --from-literal=key=value` | Create secret |
| 2 | `kubectl get secrets` | List secrets |
| 3 | `kubectl describe secret <name>` | Secret details |
| 4 | `kubectl create configmap <name> --from-file=<file>` | Create configmap |
| 5 | `kubectl get configmaps` | List configmaps |
| 6 | `kubectl describe configmap <name>` | Configmap details |
| 7 | `kubectl edit configmap <name>` | Edit configmap |
| 8 | `kubectl delete configmap <name>` | Delete configmap |

## 🌐 Services & Networking

| # | Command | Description |
|--|--|--|
| 1 | `kubectl get svc` | List services |
| 2 | `kubectl describe svc <name>` | Service details |
| 3 | `kubectl expose deployment <name> --port=80 --target-port=8080` | Expose deployment |
| 4 | `kubectl port-forward svc/<name> 8080:80` | Forward service port |
| 5 | `kubectl get endpoints` | List endpoints |
