# azure-pipeline-templates

A real sample with best practices on how you can quickly manage CICD pipeline with Azure DevOps Pipeline

### Prerequisite

* Azure subscription account - You have account on https://devops.azure.com/. If not, register first.
* [Service connection](https://docs.microsoft.com/en-us/azure/devops/pipelines/library/service-endpoints?view=azure-devops&tabs=yaml) - Create a service connection between pipeline and Azure subscription, so you can access and deploy resources to it. create with Azure resource manager, type is subscription.
* [Azure Key Vault](https://azure.microsoft.com/en-au/services/key-vault/) - create a Azure Key Vault named `keyvault69c14bbf`, post-fix is the first 8 bit of its Subscription ID.

In this key vault, you need two keys:

```
Azure-Client-Id
Azure-Client-Secret
```

* Resource group - create nominated resource group. Otherwise, make sure you need create it in pipeline.

### Features in this pipeline

* auto define which environment file to be choiced. For non-prod env, using dev.yaml. For prod env, using prod.yaml.
* only auto trigger build on develop branch, if new commit is pushed
* no need save secrets in source codes, reference with its Azure KeyVault name.
$ create tasks via its assistant when you edit the pipeline on Azure DevOps UI to save your typing.
