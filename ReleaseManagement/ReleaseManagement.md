
#  Release Management Hints
This is not a step-by-step guide. Instead it's a collection of screenshots which will help you complete the DevOpsHack challenges.
This is on purpose: We want you to explore and play with the different options of Azure DevOps.

***Hint: Before you switch windows or close your configuration, make sure you save your modification.***

## Create Release Definition in Azure DevOps
![Create Release Definition](/ReleaseManagement/images/dev_stage_create.PNG)

## Configure the Artifact
![Configure the Artifact](/ReleaseManagement/images/specify_artifact.PNG)

## Enable CD trigger
![Enable CD trigger](/ReleaseManagement/images/cd_trigger.PNG)

## Add task to deploy infrastructure on Azure
![Add task to deploy infrastructure on Azure](/ReleaseManagement/images/rg_deployment.PNG)

## Extract variables from ARM template output
```
$deploymentOutputs=(ConvertFrom-Json '$(deploymentOutputs)')
$applicationRoutingZone=$deploymentOutputs.applicationRoutingZone.value
$aiKey=$deploymentOutputs.aiKey.value
Write-Host "##vso[task.setvariable variable=applicationRoutingZone;]$applicationRoutingZone"
Write-Host "##vso[task.setvariable variable=aiKey;]$aiKey"
```

## Setup tiller
![Setup tiller](/ReleaseManagement/images/setup_tiller.PNG)

## Add "Helm tool installer" task to install Helm command line tool
![Install Helm](/ReleaseManagement/images/install_helm.PNG)

## Helm init
![Helm init](/ReleaseManagement/images/helm_init.PNG)

## Helm upgrade
![Helm upgrade](/ReleaseManagement/images/helm_upgrade.PNG)

## Helm upgrade arguments
```
--set image.repository=vislepakakslabacr.azurecr.io/akslab14c8 --set image.tag=$(Build.BuildId) --set ingress.enabled=true --set ingress.hostname=$(namespace)-sampleapp.$(applicationRoutingZone) --set applicationInsights.InstrumentationKey=$(aiKey)
```
