# bashscripts
Various Bash Scripts - mainly used for DevOps pipelines

## key-vault-updater.sh
This Azure Key Vault script will take a number of parameters (switches) to populate Azure Key Vault secrets.

### Parameters/options


* **-s** Subscription: Azure Subscription Id hosting Key Vault.
<br>  *Example: -s "ad63434a-8a31-4d83-b617-06bc5c23ecbb"*

* **-u** Client Id: Azure AD Service Principle application id.
<br>  *Example: -u "52321ad9-b3ea-445e-3785-e22a8d8cc50e"*

* **-p** Client Secret: Azure AD Service Principle application/client secret.
<br>  *Example: -p "012e683ae-26ae-29a4-924f-14e2fe5a26e7"*

* **-t** Tenant Id: Azure AD Tenent Id hosting Key Vault.
<br>  *Example: -t "92fd84bf-83d1-41af-91a6-2d7dd0516be7"*

* **-k** Key Vault: Azure Key Vault resource name.
<br>  *Example: -k "mjs-security-dev-we-kv"*

* **-d** Delimiter: Delimiter used to identify multiple secrets in the items parameter.
<br>  *Example: -d "|||"*

* **-i** Items: Secrets to save in Key Vault. Delimited list of key/value elements. By default the delimiter is a new line but this can be overridden with any string or characters defined with the -d option.
<br>  *Example: -i "key1=helloworld|||key2=abc-123-abc-123==|||key3=anothersomething!"*

## Usage

`./key-vault-updater.sh -s "ad63434a-8a31-4d83-b617-06bc5c23ecbb" -u "52321ad9-b3ea-445e-3785-e22a8d8cc50e" -p "012e683ae-26ae-29a4-924f-14e2fe5a26e7" -t "92fd84bf-83d1-41af-91a6-2d7dd0516be7" -k "mjs-security-dev-we-kv" -d "|||" -i "AppInsightsKey=7cc4dee0-e8f5-43e0-92cc-12e736d85a1e1|||CosmosDbPrimaryMasterKey=7aizdEYGEOSFoSLTISySArfjGz2j0WJt5Lbs2v3ri4rhXJYLykSR2tSTII6aLgEQig44UOs6glXooB61COVQAA==|||AnotherKey=HelloWorld"`

## Dependencies

Only dependency should be the Azure CLI.
