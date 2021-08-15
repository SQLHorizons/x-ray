# deploy x-ray

What is XRAY

JFrog Xray is a universal software composition analysis (SCA) solution that natively integrates with Artifactory, giving developers and DevSecOps teams an easy way to proactively identify vulnerabilities on open source and license compliance violations, before they manifest in production releases.

- Binary Scanning
- License Compliance
- Visibility and Impact Analysis

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
