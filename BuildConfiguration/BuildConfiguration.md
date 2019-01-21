
#  Build Configuration Hints
This is not a step-by-step guide. Instead it's a collection of screenshots which will help you complete the DevOpsHack challenges.
This is on purpose: We want you to explore and play with the different options of Azure DevOps. 

*Hint: While editing a build or release definition under the tab 'variables' you can define values which can be accessed during build/release time inside of your task with $(VariableName). There are a few standard variables documented [here for Build](https://www.visualstudio.com/en-us/docs/build/define/variables) and [here for Release](https://www.visualstudio.com/en-us/docs/build/concepts/definitions/release/variables)*
## Create Build Definition in Azure DevOps
![Build configuration step 1](/BuildConfiguration/images/initial_config.PNG)

![Build configuration step 2](/BuildConfiguration/images/visual_designer_build.PNG)

## Configure your build definition to build a docker container
![Configure your build definition to build a docker container](/BuildConfiguration/images/visual_designer_docker_build.PNG)

## Configure "Build an image" and "Push an image" tasks to use your Azure Subscription and your Azure Container Registry
![Configure "Build an image" and "Push an image" tasks](/BuildConfiguration/images/configure_docker_build.PNG)

## Add and configure "Install Helm" and "Helm package" tasks
![Add and configure "Install Helm" task](/BuildConfiguration/images/install_helm.PNG)

![Add and configure "Helm package" task](/BuildConfiguration/images/helm_package.PNG)

## Copy ARM templates
![Copy ARM templates](/BuildConfiguration/images/copy_arm_templates.PNG)

## Add Build Tasks to publish Artifacts
![Artifacts](/BuildConfiguration/images/publish_artifacts.PNG)

## Trigger CI Build on Push
![Trigger CI Build on Push](/BuildConfiguration/images/ci_trigger.PNG)

## Clone Build definition
![Clone Build definition](/BuildConfiguration/images/clone_build_definition.PNG)

## Set the trigger to Pull Request
![Set the trigger to Pull Request](/BuildConfiguration/images/trigger_pr_build.PNG)

## Task Group

Extract variable
![Task Group: Extract variable](/BuildConfiguration/images/acr_variable.PNG)

Create
![Task Group: Create](/BuildConfiguration/images/create_taskgroup.PNG)

![Task Group: Create 2](/BuildConfiguration/images/create_taskgroup_2.PNG)

Make Azure Subscription a variable
![Task Group: Configure Azure Subscription 1](/BuildConfiguration/images/task_group_variable_azure_sub_1.PNG)

![Task Group: Configure Azure Subscription 2](/BuildConfiguration/images/task_group_variable_azure_sub_2.PNG)




