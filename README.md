# deploy x-ray

What is XRAY

JFrog Xray is a universal software composition analysis (SCA) solution that natively integrates with Artifactory, giving developers and DevSecOps teams an easy way to proactively identify vulnerabilities on open source and license compliance violations, before they manifest in production releases.

- Binary Scanning
- License Compliance
- Visibility and Impact Analysis

## Overview

This repository contains the complete setup for kubernetes deployed Xray instances for deployment in the SES Platform

## References

- [Initial Project](https://github.com/SQLHorizons/ses-k8s-azure-cluster/blob/main/projects/jFrog/deployments/x-ray/README.md)

## Deployment kustomize

```powershell
clear; $Project = "D:\.source\repos\x-ray\deployments\x-ray"
$NAMESPACE = "x-ray"
Push-Location $Project

##  kubectl kustomize $Project
clear; kubectl apply --kustomize $Project
##  kubectl delete --kustomize $Project
##  kubectl get pvc -n ${NAMESPACE} --output wide
##  kubectl delete pvc -l app.kubernetes.io/name=rabbitmq -n ${NAMESPACE}
```


## Repository Layout

```xml
.
├── .azuredevops   - folder containing application ADO resources
├── deployments
│   ├── deployment-a - a packaged set of resources to deploy as one
│   │   ├── kustomization.yaml  - main kustomization file
│   │   └── deployment.yml      - k8s resource definitions
│   ├── deployment-b - a packaged set of resources to deploy as one
│   └── ...
├── environments
│   ├── test    - test envioronment
│   ├── nonprod - nonprod envioronment
│   └── prod    - prod environment
│       ├── cluster-a - cluster a deployment definition
│       │   └── ...
│       ├── cluster-b - cluster b deployment definition
│       │   └── ...
│       ├── cluster-c - cluster c deployment definition
│       │   ├── patch-a.yml         - patch file to define patch to the core deployment for the specific cluster
│       │   ├── patch-b.yml         - patch file to define patch to the core deployment for the specific cluster
│       │   └── kustomization.yaml  - kustomization definitition for the application deployment to the specific cluster
│       └── ...
├── docs - folder that holds all application documentation
│   ├── _files      - folder containing static files for use in documentation
│   ├── _css        - folder for custom CSS to be included in the documentation
│   ├── folder-a    - sub folder for documentation files
│   │   ├── something.md        - documentation page file
│   │   └── ...
│   ├── folder-b    - sub folder for documentation files
│   │   ├── something-else.md   - documentation page file
│   │   └── ...
│   └── index.md    - Documentation main index file
├── .editorconfig       - Editor config (https://editorconfig.org/) file for defining code formatting standards. Install EditorConfig VSCode plugin to use.
├── catalog-info.yaml   - Backstage (https://backstage.io/) catalog information reference
├── mkdocs.yml          - MkDocs (https://www.mkdocs.org/) configuration file for application documentation generation
├── version.txt         - version file for the application
├── CHANGELOG.md        - Changelog
└── README.md           - This doc
```
