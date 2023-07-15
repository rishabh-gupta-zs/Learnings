
# Create secret 


## Step 1: Create an Azure Key Vault

    - Resource group  :  rg-ngpgms-sanda91-eastus2

    - Key vault name  :  ngpgms-sandbox-key-vault

    - Region  :  East US2

    >> Review + Create


## Step 2: Add secret

    >> Open created key vault       >> Secrets    >> Generate/import

    - Name : cosmos_db_endpoint    (this will be <secret name>)

    - Secret value : https://example.cosmos.db.url/some_id

    >> Create  (it will create a secret)

    >> open secret  

    >> open current version (it will some id)

    >> note secret uri  (https://<key-vault-name>.vault.azure.net/secrets/<secret-name>/<version-id>)

# Set access policy ( set permissions )

    >> key vault

    >> Access policies

    >> Create

    - add permission (want to give a perticur user/app)

    >> Principal - add user/app

    >> Review/create



# Add secrets

## step 1: Create azure function

## step 2: Add secrets in azure function configuration (enviroment)

    >> open azure function

    >> Configuration

    >> New application setting

    - name : COSMOS__ENDPOINT   -> (enviroment variable name)

    - value : @Microsoft.KeyVault(SecretUri=<secret uri>)


# Accessing values in app

## function app

`string valu_e = System.getenv("ENV__VARIABLE")`

## local project 

note : we need to add AZURE_CLIENT_ID , AZURE_CLIENT_SECRET , AZURE_TENANT_ID , AZURE_SUBSCRIPTION_ID , AZURE_CLOUD_NAME in enviroment 

### Step 1: Add Azure Key Vault Java SDK Dependency


`<dependency>`

`  <groupId>com.azure</groupId>`

`  <artifactId>azure-security-keyvault-secrets</artifactId>`

`  <version>4.1.0</version>`

`</dependency>`
`<dependency>`

`  <groupId>com.azure</groupId>`

`  <artifactId>azure-identity</artifactId>`

`  <version>1.2.0</version>`

`</dependency>`


### Step 2: Retrieve Secrets in Azure Function
  
    - Create a secret client

`SecretClient secretClient = new SecretClientBuilder()
    .vaultUrl("https://<YOUR-KEY-VAULT-NAME>.vault.azure.net/")
    .credential(new DefaultAzureCredentialBuilder().build())
    .buildClient()`

    - Retrieve the secret from Key Vault

`KeyVaultSecret mySecret = secretClient.getSecret("<YOUR-SECRET-NAME>")`

    - Use the secret in your Azure Function logic

`String secretValue = mySecret.getValue();`

---


