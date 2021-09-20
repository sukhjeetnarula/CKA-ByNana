### All context commands
kubectl config --help

#### Show all contexts
kubectl config get-contexts

#### Show current context
kubectl config current-context

#### Switch to another context
kubectl set-context context-name

#### Change user or cluter name for any context
kubectl config set-context --help
kubectl config set-context context-name --user=user_name --cluster=cluster_name

#### Change user or cluster for current context
kubectl config set-context --current --user=user_name --cluster=cluster_name

#### Change default namespace
kubectl get pod
kubectl config set-context --current --namespace=myapp
kubectl get pod

