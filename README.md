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