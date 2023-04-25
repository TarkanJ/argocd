CLI

argocd app create --name test \
--repo https://github.com/ \
--dest-server https://kubernetes.default.svc \
--dest-namespace martino-project --path kubernetes

YAML

apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: test
  namespace: martino-project
spec:
  project: default
  source:
    repoURL: https://github.com/TarkanJ/argocd.git
    targetRevision: HEAD
    path: argo/example-app
  destination:
    server: https://kubernetes.default.svc
    namespace: 
