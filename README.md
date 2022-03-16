## What is Tosca

Tosca is an AI based no code automation tool for end to end test automation

## Architecture
- Licenses
   - Cloud License
   - OnPremise/Concurrent License
        - Online
        - Offline
   - Local Machine/NodeLock License
   
- Tosca Commander/Components
- Repository Setup
    - Single User
    - Multi User

- User Management

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
### Setup on Tosca Side
1. Go to Tosca Execution tab
2. At the execution list folder level, add new configuration parameter ``` "ContinuousIntegrationBuildRootFolder" ``` and set value to ``` "True" ``` 
3. At the execution list level, add new configuration parameter "ContinuousIntegration" and set value as "True" 
4. Navigate to folder ``` "C:\Program Files (x86)\TRICENTIS\Tosca Testsuite\ToscaCommander\ToscaCI\Client" ```
5. Open the ``` "ToscaCIClient.exe.config" ``` file with a text editor
6. Edit the workspace path to your project workspace (for example: ``` "C:\Tosca_Projects\Tosca_Workspaces\Sample_App\Sample_App.tws" ```)

*(Required) For Remote or Distributed Executions*
7. Navigate to folder ```"C:\Program Files (x86)\TRICENTIS\Tosca Testsuite\ToscaCommander\ToscaCI\"```
8. Run the windows exeutable file as an admininstrator ``` "ToscaCIRemoteExecutionService.exe" ```

### Setup on Jenkins Side
- Launch your Jenkins instance
- Install the tricentis continuous integration plugin in Jenkins
- Create a new Jenkins freestyle job
- On the build step, select *Tricentis Continuos Integration* plugin
- For remote execution, use these settings below

  <img width="928" alt="image" src="https://user-images.githubusercontent.com/92812029/158610676-76403b61-78ad-45f2-aa11-a12d82aa0592.png">



- Select build type as execute windows batch command
- Enter the command provided <path> - local -r <path>/result.xml
