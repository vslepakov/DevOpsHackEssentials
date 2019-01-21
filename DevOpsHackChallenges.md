## What is Azure DevOps? ##
Think of Azure DevOps as an integrated solution to support you throughout development and deployment of software. It covers a lot of tasks which typically can be found in distributed tools in a central place which can make your live easier but which also allows easy combination of artifacts and data and simplifies maintainance.
* An Azure DevOps organization is reflected by an URL like https://dev.azure.com/[myorg name]. For huge companies it can make sense to have multiple Azure DevOps organizations. Often a single Azure DevOps organization is sufficient as one organization can be used for a huge number of projects.
* A Project is created within an Azure DevOps organization and is used to wrap all kinds of artifacts which are somehow are related to the development of a single software solution. Sharing artifacts across projects is limited. 
* A Project can host an unlimited number of Source Code repositories, work items for work planning, build and release definitions etc. 
* A Project can host several teams - a number of persons working on a specific set of tasks. It is possible to put a single person into mutlipe teams.
* A Project is always based on a process template - a definition of what working in this Project looks like. A process template defines e.g. whether a "bug" is called "bug", "issue" or "defect" and which states it can be in.
* Ideally an Azure DevOps organization is backed by an Azure Active Directory which eases user management.
* Azure DevOps is not limited in the kind of applications you want to create - it works with any kind of source code, can trigger builds and deployments from and to Linux, Windows and Mac OS (and others) and supports working with containers and all kinds of clouds.

# DevOps Challenge \#1 - Azure DevOps Project Setup #
In this challenge we assume that already have an Azure DevOps organization. You will invite users, set up a project and create a team with your colleagues. If you need help check out the [:blue_book: hints for this challenge](/FirstSteps/FirstSteps.md).
If an Azure DevOps organization has already been set up for you, skip the corresponding steps.

## Achievements ##
| # | Achievement   |
|-|-|
|1.| Give your colleagues access to your organization
|2.| Create a Project called HelloWorld
|3.| Create a team named "Frontend" and a team named "Backend"
|4.| Add team members to your teams
|5.| Create a Wiki with an "Overview" page

# DevOps Challenge \#2 - Work Management #
In this challenge, you will configure Azure DevOps to trace and plan your work.
If you need help check out the [:blue_book: WorkItem Management Hints](/WorkItemManagement/WorkManagement.md) plus the [:blue_book: Dashboard customization Hints](/Dashboard/Dashboard.md).

## What you get ##
Azure DevOps brings Work Management in a default way and very often it is not necessary to apply customizations. After this challenge you will have learned about how to customize some areas of work management in Azure DevOps. You'll also modify some of the display options of work Azure Boards and learn about linkning work items and using the dashboard.

## Achievements ##
| # | Achievement   |
|-|-|
|1.| Create sample work items with releationships (e.g. parent/child). Create them in a hierarchical manner. Start at Feature / Epic level and build up the whole tree down to Task level. Create the hierarchy using the "Frontend" and/or "Backend" areas. Create a bug.
|2.| Customize your board to display product backlog items which are done in green
|3.| Create a style rule to display features which have effort estimation greater then 10 in red
|4.| Add a custom state Testing for your product backlog items
|5.| Link work items, view history
|6.| Plan and display team capacity for a srint
|7.| Modify dashboard to show team members, sprint capacity, your current workitems, sprint burndown

# DevOps Challenge \#3 - Version Control #
In this challenge, you will set up version control, upload code and configure policies.
If you need help check out the [:blue_book: Version Control Hints](/VersionControl/VersionControl.md).
## What you get ##
You probably are alread working with Version Control today. Maybe you're using Git already - but maybe it's hosted in GitLab, GitHub, Bitbucket or in another system. These existing external systems could be integrated, however Azure DevOps supports working with Git directly as well. After this challenge you'll have set up a Git repository in Azure DevOps which can be accessed from Git clients (e.g. git.exe). You'll also learn how to create some policies around Git in Azure DevOps and enforce the pull request workflow.

## Achievements ##
| # | Achievement   |
|-|-|
|1.| Create a new Git repository in your Team Project
|2.| Import our sample repository found [here](https://github.com/vslepakov/DevOpsHackSample) to your new Azure DevOps Repository
|3.| Modify your repo to require a pull request to merge code into your master branch
|4.| Modify your repo to require a Work Item linked to a pull request
|5.| Configure your repo to require at least one of your colleagues as approver
|6.| Create a new Branch. Check it out and modify code locally changing the displayed title of the Demo Website. Commit the change, then initiate and complete a pull request. Link a work item and follow the review process.
|7.| Investigate the history of the file committed following the trace from the work item
|8.| Revisit this challenge after you have successfully created a Build definition and change the Branch Policie to also require a successful build. Create a Pull Request to see it working.

# DevOps Challenge \#4 - Build Configuration for CI #
In this challenge, you will set up a build definition for your project and configure it for continuous integration. 
If you need help check out the [:blue_book: Build Configuration Hints](/BuildConfiguration/BuildConfiguration.md).
## What you get ##
After this challenge you'll have a system set up where you can trigger a new build with every code change on a specific branch. This is the first step towards a full Continuous Integration / Continuous Deployment (CI/CD) pipeline. You'll learn how to modify build definitions, how to set triggers and how to add tasks which gives you a basic understanding of configuration options for Azure DevOps. If you're working with CI already you might have set up a similar definition already in another tool like Jenkins or Bamboo. While it's always possible to trigger external systems or to integrate steps to activate e.g. Jenkins, in this challenge you'll set up a definition for usage of cloud builds orchestrated via Azure DevOps.

## Achievements ##
| # | Achievement   | Maximum score |
|-|-|-|
|1| Create a new build definition "CI Build" | 10 |
|1| Configure your build definition to build the ASP.NET Core website. Choose *Hosted Linux Preview* as agent or add make sure your agent has the correct .NET SDK installed. (2.0.0 should work!) | 10 |
|1| Modify your build definiton for CI - so set the trigger to build with every new push to the master branch| 10 |
|1| Clone your build definition, call the clone "PR Build" and set the trigger to Pull Request (see Branch Policies) | 10 |
|1| Modify your source code locally, push the code, trigger a PR and follow the Pipeline in the UI. You will be able to see the build output realtime-like. | 10 |
|1| Add another Build Task to copy the ARM-Templates to make them accessible for the release definitions. Use "Publish Build Artifacts" task.| 10 |


## Bonus Goals ##
| # | Bonus Goal | Maximum score |
|-|-|-|
|1| Create a private build agent (e.g. on your local machine or any VM) and spin it up so it is connected to your account. (You can find the required agent application in your Azure DevOps portal for download). | 10 |
|1| Modify your CI build to create a work item on failure. | 10 |



# DevOps Challenge \#5 - Release Management #
In this challenge, you will release your application to Azure. If you need help check out the [:blue_book: Release Management Hints](/ReleaseManagement/ReleaseManagement.md).
## What you get ##
After this challenge you'll be able to deploy the sample application to an environment hosted in the cloud automatically. You'll be able to target different environments based on a single configuration so that you avoid inconsistencies between dev, test and production environments. You'll be using "infrastructure as code" approaches to specify the required infrastructure - in this case you'll be using ARM (Azure Resource Manager) templates. Maybe you have a similar system running today which might be based on e.g. Chef, Puppet, Octopus. While - again - it's possible to integrate those tools this challenge will help you learn about the integrated automation in Azure DevOps. 

## Achievements ##
| # | Achievement   | Maximum score |
|-|-|-|
|1| Create a release definition which will be triggered automatically after a successful build of "CI build". *Hint: Use the Azure Resource Group Deployment Task* | 30 |
|1| Add a task to deploy the required infrastructure on Azure. Use the ARM Template provided  in /env/Templates/FullEnvironmentSetupMerged.json and also use the provided parameters file in the same folder. Overwrite the parameters as required. Make sure you're using globally unique values by e.g. adding a random string at the end. Otherwise you might run into collisions.  (See hints.)  | 10 |
|1| Modify your release definition to deploy your application. Use task "Azure Deploy App Service". Use your the name of your website as App Service Name. Pick to deploy to slot "Dev". *Hint: You can use variables for the values provided. Typically you'd work with values provided by a dropdown list. In our case those values might not exisit yet, so we have to provide them manually.*| 10 |
|1| Modify your code locally, push the code and watch the pipeline. | 10 |
|1| After a successful release investigate the information in the release's overview - see how you can navigate between releases, corresponding builds, source code artifacts, pull request and related work items via linked items. | 10 |
|1| Create another release environment which deploys to another deployment slot. | 10 |

## Bonus Goals ##
| # | Bonus Goal   | Maximum score |
|-|-|-|
|1|Add a 3rd deployment slot called "Test" by modifiying your ARM template accordingly.|50|



# CONGRATULATIONS #
Congrats! You've passed the essential challenges. Now take a step back, relax and explore: Azure DevOps automatically combines all the information you provide - see if you can find an easy way to figure out which features have been implemented newly in your latest release compared to the release 2 releases ago?

Take your time to explore Azure DevOps and all the other options available - whether it's Wiki or the Test Hub. If you have some time left, here are even more challenges.


# DevOps Bonus Challenge #6 - Automated Testing #
In this challenge, you will integrate automated tests into your application.
If you need help check out the [:blue_book: Auto Test Hints](/AutoTest/AutoTest.md).
## What you get ##
After this challenge you'll be running a test on your newly deployed application whenever it's been updated.
## Achievements ##
| # | Achievement   | Maximum score |
|-|-|-|
|1|  Create an automated performance test for the start page of your website which will be executed after deploying to environment "Dev". Configure it to simulate 100 users over 2 minutes. Configure it to fail if response times are larger then 5 seconds. *Hint: There's a task which will help you.*| 10 |

## Bonus Goals ##
| # | Bonus Goal   | Maximum score |
|-|-|-|
|1| Create a (multi-step) cloud based load test for your website which will be executed after release to test environment.Use the loadtest provided. | 10 |
|1| Visual Studio users only: Use VS to record a new webtest and use it during release. | 10 |




