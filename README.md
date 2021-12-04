# conf42

In this repo you can use vault, external-secrets and kubernetes for deploy and consume secrets from vault into your app

# Install external secrets in your kubernetes cluster (https://external-secrets.io/guides-getting-started/)

## Add repo into kubernetes cluster with helm
```bash
helm repo add external-secrets https://charts.external-secrets.io
```


## Install external secrets into kubernetes
```bash
helm install external-secrets external-secrets/external-secrets -n external-secrets    --create-namespace 
```
# Configure secret for Vault

## Config SecretStore for vault
```bash
kubectl apply -f 1.secretVault.yaml
``` 

## Config ExternalSecret for vault
```bash
kubectl apply -f 2.usingsecret.yaml
```

## Obtain ExternalSecret from Secret
```bash
kubectl apply -f 3.podusingsecret.yaml
```

