## What is Tosca

Tosca is an AI based no code automation tool for end to end test automation

## Steps
- Tosca scans your application and obtain information on control eleents
- Saves this information into modules
- Modules are building blocks of oyur test containing technical info tosca needs 
  - modules you create by scanning your test application
  - module created by tricentis tosca e.g url module


## Benefits
- Create automated test cases by scanning the app
- 


## Perequisite
- Windows OS required
- Tosca browser extension

## Installation
Download the application
Install the license server )selfhosted only)
Install the tosca commander 
Install tosca extension in your browser

## Disadvantages
Tosca does not support MacOs/Linux
No integration with Git

## My Sumamry

- Tosca scans your test application and genertaes modules from scanning it. 

## Usage
- After download and installtion
- Install tosca extension in your browser
- scan the application to auto generate test modules


## CI Integration
- Go to the execution list level
- Under test configuration, create a test configuration parameter
- Name it : "ContinuosIntgerationBuildRootFolder" and set value = "True"
- Again, under test configuration, create a test configuration parameter
- Name it : "ContinuosIntgeration" and set value = "True"
- Navigate to Prografiles/Tricentis/ToscaTestuite/ToscaCi
- Open file ToscaCIRemoteExecutionService.exe.config
- Edit the value for workspace path (put in your own path)
- Open file ToscaCIClient.exe.config
- Edit the value for workspace path (put in your own path)
- Create new freestyle job in Jenkins
- Select build type as execute windows batch command
- Enter the command provided <path> - local -r <path>/result.xml
