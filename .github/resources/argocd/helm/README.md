

helm repo add argo-cd https://argoproj.github.io/argo-helm
helm dep update my-chart

k create ns gitops
helm uninstall argo-cd -n gitops
helm install argo-cd ./my-chart -f ./values.yaml -n gitops