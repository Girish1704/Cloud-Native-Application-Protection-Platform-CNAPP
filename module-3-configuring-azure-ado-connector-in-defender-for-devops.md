# Module: Configuring Azure ADO Connector in Defender for DevOps

### Estimated Duration: 90 Minutes

## Overview

In this module, you will learn how to configure the Azure ADO Connector in Microsoft Defender for DevOps. This integration enhances security insights and risk management within CI/CD pipelines, providing you with tools to monitor and remediate vulnerabilities across your development lifecycle seamlessly.

## Lab Objectives: 

You will be able to complete the following exercises:

- Configuring Azure ADO Connector
- Configure the Microsoft Security DevOps Azure DevOps Extension
- Install Free extension SARIF SAST Scans Tab
- Create a Hosted Build Agent and Pipeline
- Configure your pipeline using YAML

### Exercise 1: Configuring Azure ADO Connector
In this exercise you will create a new Azure DevOps organization.

1. Navigate to **Azure DevOps** using the following URL and login using the following credentials:

    ```
    https://dev.azure.com
    ```

    * Email:  **<inject key="AzureAdUserEmail" enableCopy="true"/>** 
    * Temporary Access Pass:  **<inject key="AzureAdUserPassword" enableCopy="true"/>**

1. After signing in, you will be taken to the **We need a few more details** page where the details are already prefilled, then click **Continue**.

    ![](images/prot-dev-ops-d3-g1.png)

1. On the **Get started with Azure DevOps** page, click **Create new organization**.

    ![](images/prot-dev-ops-d3-g2.png)

1. On the **Get started with Azure DevOps** page, click **Continue**.

    ![](images/prot-dev-ops-d3-g3.png)

1. Verify that the Azure subscription is selected under **Select an Azure subscription for billing (1)**, and then click **Continue (2)**.

    ![](images/prot-dev-ops-d3-g4.png)

1. Click on **Organization settings**. 

    ![](images/cnn-glab3-fd-ex1-g1.png)

1. Under **Security**, select **Policies (1)**, and then enable **Third-party application access via OAuth (2)**.

    ![](images/cnn-glab3-fd-ex1-g2.png)

1. Select **Azure DevOps (1)** to navigate to the home page, in the **Create a project to get started** pane enter **ODL_User_<inject key="Deployment ID" enableCopy="false"/>** in **Project name (2)**, and then select **+ Create project (3)**.

    ![](images/cnn-glab3-fd-ex1-g3.png)

1. Navigate and log in to GitHub using the following URL on the **Labvm**, by fetching the details from **Environment Details (1)** page on the right tab, click on **Licenses (2)** tab, and copy the **GitHub credentials (3)**.

      ```
      https://github.com/
      ```

      ![](images/cnn-glab4-dvr-ex1-g1.png)

1. For **Device Verification Code**, use the same credentials as in the previous step, open a private browser window, sign in with the same username and password used for the GitHub account login, copy the verification code, and then paste it into **Device verification**.

      ```
      http://outlook.office.com/
      ```

      ![](images/email-verify.png)

1. Navigate to following Git Repository **(1)** and click on **Fork (2)**.
   
      ```
      https://github.com/Azure/Microsoft-Defender-for-Cloud/tree/main
      ```
     
    ![](images/m4-img22.png)

1. In **Create a new fork**, verify the **Owner (1)** selection, disable **Copy the main branch only (2)**, and then select **Create fork (3)**.

      ![](images/cnn-glab4-dvr-ex1-g2.png)   

1. On the **Microsoft-Defender-for-cloud** repository,click on **Settings**.

      ![](images/cnn-glab4-dvr-ex1-g3.png) 

1. Expand **Actions (1)**, and then select **General (2)**.

      ![](images/cnn-glab4-dvr-ex1-g4.png) 

1. Under **Workflow permissions**, select **Read and write permissions (1)**, and then choose **Save (2)**.

      ![](images/cnn-glab4-dvr-ex1-g5.png) 

1. Go to the Azure portal by using the following URL.

      ```
      http://portal.azure.com/
      ```

1. Search for **Microsoft Defender for Cloud (1)**, and then select it from the search results **(2)**.

      ![](images/cnn-glab4-dvr-ex1-g6.png) 

1. In the left navigation pane, expand **Management (1)**, select **Environment settings (2)**, choose **Add environment (3)**, and then select **GitHub (4)**.

      ![](images/cnn-glab4-dvr-ex1-g7.png)

1. In the **GitHub connection** page, configure the following settings:

      - Enter `CNAPP-Devops` in **Connector name (1)**.
      - Select your **Subscription (2)**.
      - Select **asclab (3)** as the **Resource group**.
      - Select any **Location (4)**.
      - Select **Next: Select capabilities > (5)** to continue.

          ![](images/cnn-glab4-dvr-ex1-g8.png)
        
1. In **Select capabilities**, enable **Defender CSPM (1)**, and then select **Next : Configure access > (2)**.

      ![](images/cnn-glab4-dvr-ex1-g9.png)

1. In **Configure access**, select **Authorize** under **Authorize DevOps security**.

      ![](images/cnn-glab4-dvr-ex1-g10.png)

1. In the pop-up window, select **Authorize**.

      ![](images/cnn-glab4-dvr-ex1-g11.png)

1. Under **Install DevOps security app**, select **Install**.

      ![](images/cnn-glab4-dvr-ex1-g12.png)

1. In **Install Microsoft Security DevOps**, select the **cloudlabsuser** GitHub account.

      ![](images/cnn-glab4-dvr-ex1-g13.png)

1. In **Install Microsoft Security DevOps**, select **All repositories (1)**, and then choose **Install (2)**.
  
      ![](images/cnn-glab4-dvr-ex1-g14.png)

1. After the DevOps security app installation is completed, select **Next: Review and generate >**.

      ![](images/cnn-glab4-dvr-ex1-g15.png)

1. Review the configuration settings, and then select **Create**.

      ![](images/cnn-glab4-dvr-ex1-g16.png)

1. In the left navigation pane, expand **Management (1)**, select **Environment settings (2)**, refresh the page by selecting **Refresh (3)**, and verify that the **CNAPP-git (4)** GitHub connector is displayed.

      ![](images/cnn-glab4-dvr-ex1-g17.png)

      > **Note:** It may take 5–10 minutes for the GitHub connector to appear.
    

   <validation step="1bdfcec7-cc4e-4c87-ad14-bb67c4034367" />    

   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
   - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
   - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

This exercise involves configuring the Azure DevOps (ADO) connector to integrate and manage DevOps resources within your environment.
     
### Exercise 2: Configure the Microsoft Security DevOps Azure DevOps Extension

In this exercise, you will configure the Microsoft Security DevOps Azure DevOps Extension to enhance security integrations and capabilities within your DevOps environment.

1. Navigate back to [Azure DevOps](https://dev.azure.com) tab open in your browser. In the right corner, click in the **Shopping bag icon (1)** and click **Browse marketplace (2)** option.

       ![](images/cnn-glab3-fd-ex1-g5.png)

1. In the marketplace search and select **Microsoft Security DevOps** extension.  

       ![](images/m3-img11.png)

1. Next click on **Get it free**.

       ![](images/m3-img12.png)

1. Choose your **Organization (1)** from the dropdown menu, select **Install (2)**.

       ![](images/cnn-glab3-fd-ex1-g6.png)

       >**Note:** If this is already installed, directly move to next exercise and continue further.

1. Click on **Proceed to Organization**. 

       ![](images/m3-img14.png)

1. On the Azure DevOps home page, select **Organization settings**.

       ![](images/cnn-glab3-fd-ex1-g7.png)

1. Click on **Extensions (1)** under **Installed (2)** extensions you can view the **Microsoft Security DevOps (3)** extension that is installed. 

       ![](images/m3-img15.png)

       >**Note** Admin privileges to the Azure DevOps organization are required to install the extension. If you don’t have access to install the extension, you must request access from your Azure DevOps organization’s administrator during the installation process.

This exercise involves setting up the Microsoft Security DevOps Azure DevOps Extension to integrate security features and improve DevOps processes.

### Exercise 3: Install Free extension SARIF SAST Scans Tab

In this exercise, In order to view the scan results (when you execute the pipelines), in an easier and readable format, install this free extension in your Azure DevOps organization.

1. In **Azure DevOps** from the right corner, click in the **Shopping bag icon (1)** and click **Browse marketplace (2)** option.

       ![](images/m3-img10.png)
     
1. In the marketplace search and select **SARIF SANST Scans Tab** extension.

       ![](images/cnn-glab3-fd-ex1-g8.png)

1. Next click on **Get it free**.

       ![](images/m3-img17.png)

1. Choose your **Organization (1)** from the dropdown menu, select **Install (2)**.

       ![](images/cnn-glab3-fd-ex1-g9.png)

1. Click on **Proceed to Organization**. 

       ![](images/m3-img19.png)

1. On the Azure DevOps home page, select **Organization settings**.

       ![](images/cnn-glab3-fd-ex1-g7.png)

1. Click on **Extensions (1)** under **Installed (2)** extensions you can view the **SARIF SANST Scans (3)** extension that is installed. 

       ![](images/m3-img20.png)

This exercise involves installing the free SARIF SAST Scans Tab extension to enable static application security testing and integrate it into your development environment.

### Exercise 4: Create a Hosted Build Agent and Pipeline

In this exercise, you will create a hosted build agent and pipeline to automate and manage your build processes in a DevOps environment.

1. In the **Azure Portal**, click in the search bar, type **vmss** and then click **Virtual machine scale sets**. 

       ![](images/cnn-glab3-fd-ex1-g10.png)

1. Click **Create** button.

       ![](images/cnn-glab3-fd-ex1-g11.png)

1. In the **Create a Virtual Machine Scale Set (VMSS)** page, configure the following settings:
      - Select your **Subscription (1)**.
      - Select **asclab (2)** as the **Resource group**.
      - Enter **build-agent** in **Virtual machine scale set name (3)**.
      - Select **<inject key="Resource group Location" enableCopy="false" /> (4)** for **Region**.

        ![](images/cnn-glab3-fd-ex1-g12.png)

1. In the **Create a Virtual Machine Scale Set (VMSS)** page, configure the following settings:
      - Select **Uniform (1)** for **Orchestration mode**.
      - Verify **Standard (2)** is selected for **Security type**.
      - Select **Manually update the capacity (3)** for **Scaling mode**.
      - Select **See all images (4)** under **Image**.

        ![](images/cnn-glab3-fd-ex1-g13.png)

1. In **Select an image**, search for **Windows Server (1)**, and then select the **Select (2)** drop-down for the **Windows Server** image.

       ![](images/cnn-glab3-fd-ex1-g14.png)

1. From the image list, select **Windows Server 2022 Datacenter: Azure Edition - x64 Gen 2**.

       ![](images/cnn-glab3-fd-ex1-g41.png)

1. In the same page, configure the following settings for **VMSS**:

      - Verify **Standard D2s v3 (1)** is selected for **Size**.
      - Enter `demouser` in **Username (2)**.
      - Enter `demo!pass123` in **Password (3)**.
      - Enter `demo!pass123` in **Confirm password (4)**.

        ![](images/cnn-glab3-fd-ex1-g16.png)

1. Scroll up to the top of the page, and then select the **Networking** tab.

       ![](images/cnn-glab3-fd-ex1-g17.png)

1. Under **Network interface**, select **Edit** for the network interface.

       ![](images/cnn-glab3-fd-ex1-g18.png)

1. In **Edit network interface**, enable **Public IP address (1)**, and then select **OK (2)**.

       ![](images/cnn-glab3-fd-ex1-g19.png)
 
1. Once you are back on the **Networking** tab click **Review + Create**.

       ![](images/cnn-glab3-fd-ex1-g20.png)

1. In the next page, you should see that all the validation are passed and now you can click **Create** button. The deployment will take a few minutes to complete.

       ![](images/cnn-glab3-fd-ex1-g42.png)

1. Once the deployment is completed, click on **Go to resource** button.

       ![](images/cnn-glab3-fd-ex1-g22.png)
 
1. In the **build-agent** page, click on **Instances** option in the left. Confirm that the build-agents are **Running**. 

        ![](images/cnn-glab3-fd-ex1-g23.png)

1. In **build-agent | Network settings**, expand **Networking (1)**, select **Network settings (2)**, choose **+ Create port rule (3)**, and then select **Inbound port rule (4)**.

        ![](images/addport1.png)

1. In **Add inbound security rule**, configure the following settings:

      - Enter **3389** in **Destination port ranges (1)**.
      - Enter **AllowRDP** in **Name (1)**.
      - Select **Add (2)**.

        ![](images/cnn-glab3-fd-ex1-g26.png)

        ![](images/cnn-glab3-fd-ex1-g27.png)

1. In the left navigation pane, select **Instances (1)**, and then select **build-agent_1 (2)**.

        ![](images/cnn-glab3-fd-ex1-g28.png)

1. From the **Overview (1)** page, copy the **Public IP address (2)** and paste in a text editor like ***Notepad***.
   
        ![](images/cnn-glab3-fd-ex1-g29.png)

1. On your **Labvm**, search for **rdp** in windows search and select **Remote Desktop Connection**.

        ![](images/rdplog.png)
 
1. Enter the **IP** you copied earlier and click **Connect**.

        ![](images/ip.png)

1. Enter the following credentials and click **OK**.

      - **Username**: `.\demouser` 
      - **Password**: `demo!pass123`

         ![](images/userpwd.png)

1. In the Windows search bar, enter **powershell ISE (1)**, and then select **Run as administrator (2)** for **Windows PowerShell ISE**.

        ![](images/cnn-glab3-fd-ex1-g32.png)

1. In **Windows PowerShell ISE (x86)**, select **New Script**.

        ![](images/cnn-glab3-fd-ex1-g33.png)

1. Paste the following commands to install ***nodejs (1)*** and click on **Run (2)** button. 

        ```
        #Install nodejs v16.8.0
        $WebClient = New-Object System.Net.WebClient
        $WebClient.DownloadFile("https://nodejs.org/download/release/v16.8.0/node-v16.8.0-x64.msi","C:\node-v16.8.0-x64.msi")
        $arguments = "/i `"C:\node-v16.8.0-x64.msi`" /quiet"
        Start-Process msiexec.exe -ArgumentList $arguments -Wait
        sleep 5
        ```
        ![](images/nodejs1.png)
     
1. Paste the following commands to install ***dotnet* (1)** and click on **Run (2)** button.

        ```
        $WebClient = New-Object System.Net.WebClient 
        $WebClient.DownloadFile("https://download.visualstudio.microsoft.com/download/pr/34d3e426-9f3c-45a6-8496-f21b3adbbf5f/475aec17378cc8ab0fcfe535e84698f9/aspnetcore-runtime-8.0.2-win-x64.exe","C:\aspnetcore-runtime-8.0.2-win-x64.exe")
        $arguments = "/install /quiet /norestart"
        Start-Process "C:\aspnetcore-runtime-8.0.2-win-x64.exe" -ArgumentList $arguments -Wait
        sleep 5
        ```
        ![](images/dotnet-runtime.png)

        ```
        $WebClient = New-Object System.Net.WebClient
        $WebClient.DownloadFile("https://download.visualstudio.microsoft.com/download/pr/ab5e947d-3bfc-4948-94a1-847576d949d4/bb11039b70476a33d2023df6f8201ae2/dotnet-sdk-8.0.201-win-x64.exe","C:\dotnet-sdk-8.0.201-win-x64.exe")
        $arguments = "/install /quiet /norestart"
        Start-Process "C:\dotnet-sdk-8.0.201-win-x64.exe" -ArgumentList $arguments -Wait
        sleep 5
        ```
        ![](images/dotnet-sdk.png)

1. Next, in the windows search bar type ***cmd*** and select **Command Prompt**.

        ![](images/cmd1.png)

1. In the command prompt, run the following npm command.

        ```
        npm.cmd install --loglevel error eslint@7.32.0 typescript@4.3.2 @microsoft/eslint-plugin-sdl@0.1.7 eslint-plugin-react@7.24.0 eslint-plugin-security@1.4.0 @typescript-eslint/typescript-estree@4.27.0 @typescript-eslint/parser@4.27.0 @typescript-eslint/eslint-plugin@4.27.0 @microsoft/eslint-formatter-sarif@2.1.5 eslint-plugin-node@11.1.0 --prefix C:\a\_msdo\packages\node_modules\eslint –global
        ```
     
        ![](images/npm1.png)

1. Close the **RDP** session by clicking on **X**.

        ![](images/close.png)

1. Navigate to [Azure DevOps](https://dev.azure.com), in the main page, click on your **Project**.

        ![](images/m3-img28.png)

1. In the bottom of left navigation page, click **Project settings** option.

        ![](images/cnn-glab3-fd-ex1-g34.png)

1. In the left navigation page, under **Pipelines** section, click **Agent pools (1)** option. From the top right corner of the page, click **Add pool (2)** button.

        ![](images/m3-img30.png)

1. In **Add agent pool**, select **New (1)**, and then choose **Azure virtual machine scale set (2)**.

        ![](images/cnn-glab3-fd-ex1-g35.png)
 
1. Select your **subscription (1)** and click **Authorize (2)** button.

        ![](images/m3-img32.png)

1. After the authorization is done, click on the virtual machine scale set drop-down list and select **build-agent (1)**. Under the **Name** field, enter **windows-build-agents (2)**.

        ![](images/m3-img33.png)

        >**Note: You may get an error about client not allowed, click button with circle (refresh) to fix**.

1. Enter `1` under **Maximum number of virtual machines in the scale set (1)** and **Number of agents to keep on standby (2)** fields then check the box next to **Grant access permission to all pipelines (3)** and click **Create (4)**.

        ![](images/m3-img52.png)

1. In the **Agent pools** page, you can view newly created pool.

        ![](images/m3-img35.png)

1. Navigate back to **Azure Portal**, on the **VMSS** page click on **Instances (1)** from the left menu, select both the **Build Agents (2)** and click **Upgrade (3)**.

        ![](images/cnn-glab3-fd-ex1-g36.png)

   <validation step="07bc50d1-a0f3-4fba-81c2-385606d6d5f3" />

   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
   - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
   - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

This exercise involves setting up a hosted build agent and pipeline to automate and streamline your build and deployment processes.

### Exercise 5: Configure your pipeline using YAML 

The purpose of this exercise is to allow you to see how the extension used by Defender for DevOps will check your pipeline.

1. On the repository click on **Code (1)** and copy the **URL (2)**. Paste into any text editor like *Notepad*.

        ![](images/giturl.png)

1. Login to the **Azure DevOps**(https://dev.azure.com) and open your **Project**.

        ![](images/m3-img28.png)

1. From the left pane, click on **Repos (1)** and click **Import (2)** under **Import a repository**.

        ![](images/importrepo.png)

1. On the **Import a Git repository** pane, for **Clone URL (1)** paste the **URL** you copied the previous, then click **Import (2)**.

        ![](images/gitimport.png)

1. Next, in the left navigation pane, click **Pipelines (1)**. In the right pane, click **Create Pipeline (2)** button.

        ![](images/cnn-glab3-fd-ex1-g37.png)

1. In the **Where is your code?** page, click **Azure Repos Git**.

        ![](images/m3-img37.png)

1. Click on the existing **Repository**.

        ![](images/m3-img38.png)

1. In the **Review your pipeline** page, replace the **YAML code (1)** for the one below and click **Save and run (2)** :

        ```
        # Starter pipeline
        # Start with a minimal pipeline that you can customize to build and deploy your code.
        # Add steps that build, run tests, deploy, and more:
        # https://aka.ms/yaml
        trigger: none
        pool: windows-build-agents
        steps:
        - task: UseDotNet@2
          displayName: 'Use dotnet'
          inputs:
            version: 3.1.x
        - task: UseDotNet@2
          displayName: 'Use dotnet'
          inputs:
            version: 5.0.x
        - task: UseDotNet@2
          displayName: 'Use dotnet'
          inputs:
            version: 6.0.x
        - task: MicrosoftSecurityDevOps@1
          displayName: 'Microsoft Security DevOps'
        ```
     
        ![](images/m3-img39.png)

        > **Note**: Observe that the pool is pointing to windows-build-agents, which is the VMSS that you created.

1. Click the **Save and run** button again.

       ![](images/m3-img40.png)

       > **Note**: At this point the job will queue up to run. This step may take some time to spin up a build agent in the VMSS. During this time, if you go back to VMSS dashboard you will see that the instance is getting created.

1. In a few more minutes, the job will start to have some activity as shown the example below:

       ![](images/m3-img44.png)

1. Once it finishes you can see scan done by Defender for DevOps. To do that click **Microsoft Security DevOps** section in the left and you will see the output of the actions that were done as shown below:

       ![](images/m3-img45.png)

   <validation step="847540fb-759b-44cd-b6ca-b2b88f5ce8e9" />

   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
   - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
   - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

1. Note the Azure DevOps organization name displayed at the top of the page.

        ![](images/cnn-glab3-fd-ex1-g38.png)

1. On the Azure DevOps home page, select **Organization settings**.

       ![](images/cnn-glab3-fd-ex1-g7.png)

1. In the left navigation pane, select **Billing (1)**, and then choose **Change billing (2)**.

       ![](images/cnn-glab3-fd-ex1-g43.png)

1. In **Change billing**, select **Remove billing (1)**, and then choose **Save (2)**.

       ![](images/cnn-glab3-fd-ex1-g44.png)

This exercise focuses on configuring your pipeline using YAML to observe how the Defender for DevOps extension evaluates and checks the pipeline.

## Summary

This module covers setting up a secure DevOps environment by configuring the Azure ADO Connector and Microsoft Security DevOps Azure DevOps Extension. It includes installing the SARIF SAST Scans Tab extension, creating a hosted build agent and pipeline, and configuring the pipeline using YAML to integrate and manage security checks effectively.


