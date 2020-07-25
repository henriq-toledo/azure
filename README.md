# azure
Azure CLI scripts

## Setup

- [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)

## Azure CLI commands

### Azure Web App

```
az group create --name <resource_group_name> --location eastus

az appservice plan create --name <api_plan_name> --resource-group <resource_group_name> --is-linux --location eastus --sku B1

az webapp create --name <webapp_name> --resource-group <resource_group_name> --plan <api_plan_name> --deployment-container-image-name kennethreitz/httpbin:latest

az webapp start --name <webapp_name> --resource-group <resource_group_name>

az webapp show --name <webapp_name> --resource-group <resource_group_name>

az group delete --name <resource_group_name> --no-wait --yes
```

### Azure VM

```
az group create --name myResourceGroup --location eastus

az vm create --resource-group myResourceGroup --name myVM --admin-username azureuser --license-type Windows_Client --image MicrosoftWindowsDesktop:Windows-10:19h1-ent:18362.720.2003120536

az vm open-port --port 80 --resource-group myResourceGroup --name myVM
```

### Azure Storage

```
az group create --name <resource_group_name> --location eastus

az storage account create --name <storage_account_name> --resource-group <resource_group_name> --location eastus --access-tier Hot --kind StorageV2 --sku Standard_RAGRS

az storage account show-connection-string --name <storage_account_name> --resource-group <resource_group_name>

az group delete --name <resource_group_name> --no-wait --yes
```

### Azure SQL Database

```
az group create --name <resource_group_name> --location eastus

az sql server create --name <sql_server_name> --resource-group <resource_group_name> --location eastus --admin-user <sql_admin_user_name> --admin-password <sql_admin_password>

az sql server firewall-rule create --resource-group <resource_group_name> --server <sql_server_name> -n AllowYourIp --start-ip-address <start_ip_address> --end-ip-address <end_ip_address>

az sql db create --resource-group <resource_group_name> --server <sql_server_name> --name <database_name> --edition Basic --zone-redundant false --license-type BasePrice

az sql db show-connection-string --server <sql_server_name> --name <database_name> --client ado.net

az sql db show --resource-group <resource_group_name> --server <sql_server_name>

az sql server show --resource-group <resource_group_name> --name <sql_server_name>

az group delete --name <resource_group_name> --no-wait --yes
```