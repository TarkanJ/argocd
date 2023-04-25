CLI

argocd app create --name first-argo-app \
--repo https://github.com/TarkanJ/argocd \
--dest-server https://kubernetes.default.svc \
--dest-namespace first-argo-app  --path kubernetes

YAML

apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: test
  namespace: first-argo-app
spec:
  project: martino-project
  source:
    repoURL: https://github.com/TarkanJ/argocd.git
    targetRevision: HEAD
    path: argo/first-argo-app
  destination:
    server: https://kubernetes.default.svc
    namespace: first-argo-app
