used helm chart version 2.1.10

# Installation

## 1) add helm repo for argocd
```
helm repo add kyverno https://kyverno.github.io/kyverno/
helm repo update
```

## 2) generate argocd-base.yaml
```
helm template kyverno kyverno/kyverno --namespace kyverno > kyverno.yaml
```

## 3) generate installation menifest (you don't have to do this if you use argocd)
```
kk kustomize . > /tmp/keyverno-install.yaml
```

## 4) deploy argocd
```
kk create ns kyverno
kk create -f /tmp/kyverno-install.yaml
```

gagaaga
