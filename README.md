# iac-digitalocean

## modo de uso:

crie um arquivo de variáveis: terraform.tfvars

```yaml
do_token = "<seu_token>"
k8s_name = "<Nome_do_cluster>"
region   = "<Região>"
```

agora rode os comandos

```bash
terraform validate #valida seus arquivos de configuração
terraform fmt # acerta formatação
terraform init # baixa os resources utilizados
terraform plan # mostra o que será feito na cloud
terraform apply # aplica
```

acesse seu cluster
```bash
# o comando abaixo sobrepoe qualquer configuração de outros cluster que estejam configurados no seu ambiente
cp kube_config.yaml ~/.kube/config

kubectl get nodes
```

aplique o manifesto da aplicação
```bash
kubectl apply -f kube-news/k8s/deployment.yaml
```

Tudo Ok

=========================================

destrua tudo !!!! (se quiser é claro)


```bash
kubectl delete -f kube-news/k8s/deployment.yaml
terraform destroy
```


===================================

Para rodar no Github Actions, mantenha seu cluster no ar e crie as secrets no Github

```
DOCKERHUB_PWD
DOCKERHUB_USER
K8S_CONFIG
```
