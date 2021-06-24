# Cognitive Services Language SDK for Python

This is the AutoRest configuration file the Cognitive Services Language SDK for Python.

> see https://aka.ms/autorest

## Common Python Settings

```yaml $(python)
python:
  namespace: azure.ai.language.questionanswering
  package-name: azure-ai-language-questionanswering
  license-header: MICROSOFT_MIT_NO_VERSION
  credential-default-policy-type: AzureKeyCredentialPolicy
  credential-key-header-name: Ocp-Apim-Subscription-Key
  add-credential: true
  package-version: 1.0.0b1
  basic-setup-py: true
  clear-output-folder: true

directive:
  - from: swagger-document
    where: '$.paths["/:query-knowledgebases"].post'
    transform: >
      $["operationId"] = "QueryKnowledgebase";
  - from: swagger-document
    where: '$.paths["/:query-text"].post'
    transform: >
      $["operationId"] = "QueryText";
  - from: swagger-document
    where: '$.paths["/query-knowledgebases/projects"].get'
    transform: >
      $["operationId"] = "ListProjects";
  - from: swagger-document
    where: '$.paths["/query-knowledgebases/projects/{projectName}"].get'
    transform: >
      $["operationId"] = "GetProjectDetails";
  - from: swagger-document
    where: '$.paths["/query-knowledgebases/projects/{projectName}"].put'
    transform: >
      $["operationId"] = "CreateProject";
  - from: swagger-document
    where: '$.paths["/query-knowledgebases/projects/{projectName}"].delete'
    transform: >
      $["operationId"] = "DeleteProject";
  - from: swagger-document
    where: '$.paths["/query-knowledgebases/projects/{projectName}/:export"].post'
    transform: >
      $["operationId"] = "ExportProject";
  - from: swagger-document
    where: '$.paths["/query-knowledgebases/projects/{projectName}/:import"].post'
    transform: >
      $["operationId"] = "ImportProject";
  - from: swagger-document
    where: '$.paths["/query-knowledgebases/projects/{projectName}/deployments/{deploymentName}"].put'
    transform: >
      $["operationId"] = "DeployProject";
  - reason: Don't expose the get status endpoint, as this will be used internally by poller.
    remove-operation: QuestionAnsweringProjects_GetExportStatus
  - reason: Don't expose the get status endpoint, as this will be used internally by poller.
    remove-operation: QuestionAnsweringProjects_GetImportStatus
  - reason: Don't expose the get status endpoint, as this will be used internally by poller.
    remove-operation: QuestionAnsweringProjects_GetDeployStatus
```

### Tag: 2021-05-01-preview-questionanswering

These settings apply only when `--tag=release_2021_05_01_preview_questionanswering` is specified on the command line.

``` yaml $(tag) == 'release_2021_05_01_preview_questionanswering'
input-file:
- preview/2021-05-01-preview/questionanswering.json
title:
  QuestionAnsweringClient
modelerfour:
  lenient-model-deduplication: true
```

### Tag: 2021-05-01-preview-knowledgebaseauthoring

These settings apply only when `--tag=release_2021_05_01_preview_questionanswering` is specified on the command line.

``` yaml $(tag) == 'release_2021_05_01_preview_knowledgebaseauthoring'
input-file:
- preview/2021-05-01-preview/questionanswering-authoring.json
title:
  KnowledgebaseAuthoringClient
modelerfour:
  lenient-model-deduplication: true
```
