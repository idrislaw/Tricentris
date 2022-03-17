## What is Tricentis Tosca

Tosca is an AI based no code automation tool for end to end automation testing

## Architecture
 
- Tosca Commander/Components

- Repository Setup
    - Single User: Local storage
    - Multi User : MySQL, SQlite, DB2

- Licensing
   - Cloud License
   - OnPremise/Concurrent License
        - Online
        - Offline
   - Local Machine/NodeLock License

- User Management


## Benefits
- No coding required
- Create automated test cases by scanning the app
- Offers 14-days trial period


## Pre-requisite
- Windows OS required
- Tosca browser extension


## Installation
- Log into your tosca account to download the installation file [here](https://www.tricentis.com/software-testing-tool-trial-demo/tosca-trial/)
- Click [How to Install Tosca](https://documentation.tricentis.com/tosca/1410/en/content/installation_tosca/installation_gui.html) for detailed installation 
- Install the tosca commander 
- Install tosca extension in your browser


## Usage Summary
- Open the sample web application to be tested in a browser
- Launch the tosca commander application and go to the **Modules** tab. 
- Scan your sample web application and select controls to be tested, this process will generate your **Test_Modules**
- Navigate to the **TestCases** tab and create a new **TestCase** folder for your sample app
- Drag the scanned **Test_Modules** into your **TestCase** folder to create your **TestCase** and **Test_Steps**
- Navigate to the **Execution** tab and create a new **Execution_List_Folder** for your sample app
- Drag the ceated **TestCases** into your **ExcutionListFolder** to create your **Execution_List**
- You can run the **Execution_list** manually by hitting ```F6``` or automate it using **Jenkins**


# CI Integration with Jenkins

## Setup on Tosca Side
1. Go to Tosca Execution tab
2. At the execution list folder level, add new configuration parameter ``` "ContinuousIntegrationBuildRootFolder" ``` and set value to ``` "True" ``` 
3. At the execution list level, add new configuration parameter "ContinuousIntegration" and set value as "True" 
4. Navigate to folder ``` "C:\Program Files (x86)\TRICENTIS\Tosca Testsuite\ToscaCommander\ToscaCI\Client" ```
5. Open the ``` "ToscaCIClient.exe.config" ``` file with a text editor
6. Edit the workspace path to your project workspace (for example: ``` "C:\Tosca_Projects\Tosca_Workspaces\Sample_App\Sample_App.tws" ```)

   ***The following steps are required only For Remote or Distributed Executions***

7. Navigate to folder ```"C:\Program Files (x86)\TRICENTIS\Tosca Testsuite\ToscaCommander\ToscaCI\"```
8. Run the windows exeutable file as an admininstrator ``` "ToscaCIRemoteExecutionService.exe" ```


## Setup on Jenkins Side (Local Execution)
1. Launch your Jenkins instance
3. Create a new Jenkins job
4. On the build step, select **Execute Windows batch command**
5. Enter code as shown below

```"C:\Program Files (x86)\TRICENTIS\Tosca Testsuite\ToscaCommander\ToscaCI\Client\ToscaCIClient.exe" -m local -r "C:\Users\Administrator\AppData\Local\Jenkins\.jenkins\workspace\**Sample_App**\result.xml"```

   <img width="939" alt="image" src="https://user-images.githubusercontent.com/92812029/158637209-df1d9b82-5b4c-48b8-896d-d252938374f4.png">


## Setup on Jenkins Side (Remote Execution)
1. Launch your Jenkins instance
2. Install the tricentis continuous integration plugin in Jenkins
3. Create a new Jenkins job
4. On the build step, select *Tricentis Continuos Integration* plugin
5. Enter code as below

``` C:\Program Files (x86)\TRICENTIS\Tosca Testsuite\ToscaCommander\ToscaCI\Client\ToscaCIClient.exe ```

``` http://servername:8732/TOSCARemoteExecutionService/ ```
  
  <img width="945" alt="image" src="https://user-images.githubusercontent.com/92812029/158646325-981c14e7-56e7-477c-9454-3fb04d9fa87c.png">
.
.
.


Click to learn more about [Tosca CI](https://documentation.tricentis.com/tosca/1430/en/content/continuous_integration/concept.html)

Click to learn more about [Tosca CI with Jenkins](https://support-hub.tricentis.com/open?id=kb_article_view&sys_kb_id=c52c6bbdb7413c0b53310284b96198b)

