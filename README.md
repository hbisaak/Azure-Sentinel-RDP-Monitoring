# Azure-Sentinel-RDP-Monitoring

## Project Overview
This project demonstrates how to set up a virtual machine on Azure, deploy Microsoft Sentinel, and configure it to monitor Remote Desktop Protocol (RDP) login events. The tutorial covers the steps from VM creation to Sentinel configuration and setting up alert rules for security monitoring.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Setup Guide](#setup-guide)
- [Configuration](#configuration)
- [Monitoring and Alerts](#monitoring-and-alerts)
- [Troubleshooting](#troubleshooting)

## Prerequisites
- An Azure account
- Basic knowledge of Azure and Sentinel
- Familiarity with RDP and security monitoring concepts

## Setup Guide
1. **Create an Azure Virtual Machine**
   - Navigate to Azure Portal.
   - Create a new virtual machine with Windows Pro.
   - Configure username and password.
   - Default settings for disks and networking.

  2. **Deploy Microsoft Sentinel**
   - Search for and create a new Microsoft Sentinel instance.
   - Select the appropriate resource group and region.
   - you want to make sure it is collecting all security events

   ![collect them all](https://github.com/user-attachments/assets/e02cd5ea-f5ac-4fec-ba64-826ab24add1a)

3. **Add the Virtual Machine to Sentinel**
   - Go to the Log Analytics workspace.
   - Add the VM and configure data connectors.

   ![Step 3: Add VM]![data connector](https://github.com/user-attachments/assets/358fb3da-0324-46ed-b54b-b070a6034a82)

4. **Set Up Data Collection Rules**
   - Create a data collection rule for Windows events.
![content hub events monitor agent](https://github.com/user-attachments/assets/3b916ec9-59da-4d83-9813-6a5fd235c1d9)
   - Configure it to monitor RDP sign-in events.

   ![Step 4: Data Collection Rules]![making a rule 1](https://github.com/user-attachments/assets/17c83255-a3b6-43b9-a0d9-90a1d58e0247)

4. **Create and Configure Sentinel Alerts**
   - Define an alert rule for successful local RDP logins.
   - Make sure the alert rule is running

   ![Step 5: Create Alerts]![its running](https://github.com/user-attachments/assets/76274548-9be8-4de5-970e-ee0dc46a769b)



## Monitoring and Alerts
- Check the Sentinel dashboard for real-time alerts and incidents.
- Log in to your virtual machine and make sure the alert triggers. 
- Review generated alerts and incident details.

   ![Monitoring and Alerts]!![also me loggin in](https://github.com/user-attachments/assets/57471a6d-5acf-445c-8810-71a8d1530750)

## Troubleshooting
- # Troubleshooting Guide

This guide addresses common issues encountered during the 
setup and operation of the Azure Sentinel RDP Monitoring project.

## 1. Azure Virtual Machine Creation Fails
- **Issue:** The VM creation process fails or errors out.!

- **Solution:** 

  - **Check Resource Quotas:** Ensure you have not exceeded your subscription’s resource quotas.
  - **Verify Configuration:** Double-check your VM configuration settings, including size, region, and network settings.
  - **Review Error Messages:** Look at the detailed error messages in the Azure Portal for specific guidance.

## 2. Unable to Connect to the VM via RDP
- **Issue:** You can't establish an RDP connection to the VM.
- **Solution:**
  - **Check Network Security Group (NSG) Rules:** Ensure that inbound rules for RDP (port 3389) are properly configured.
  - **Verify Public IP Assignment:** Confirm that the VM has a public IP address and that it's correctly assigned.
  - **Check VM Status:** Make sure the VM is running and hasn’t encountered any issues during startup.

## 3. Microsoft Sentinel Deployment Issues
- **Issue:** Problems occur when setting up or deploying Microsoft Sentinel.
- **Solution:**
  - **Verify Resource Group and Region:** Ensure you are using the correct resource group and region.
  - **Check Permissions:** Confirm that your Azure account has sufficient permissions to create and configure Sentinel.
  - **Review Sentinel Documentation:** Consult the official Microsoft Sentinel documentation for troubleshooting tips.

## 4. Data Collection Rule Not Receiving Logs
- **Issue:** The data collection rule fails to collect or send logs from the VM to Sentinel.
- **Solution:**
  - **Check Data Connector Configuration:** Ensure that the data connector is correctly set up and that it’s connected to the VM.
  - **Verify Agent Installation:** Make sure the Azure Monitor Agent is installed and running on the VM.
  - **Review Collection Rules:** Confirm that the data collection rule is correctly configured to capture the desired event logs.

## 5. Sentinel Alerts Not Triggering
- **Issue:** Alerts configured in Sentinel are not being triggered as expected.
- **Solution:**
  - **Validate Alert Query:** Ensure that the query used to define the alert rule is accurate and matches the log data format.
  - **Check Alert Rules Configuration:** Review the alert rule settings, including the frequency of checks and alert thresholds.
  - **Examine Log Data:** Verify that the log data is being collected and contains the information needed to trigger the alert.

## 6. High Cost for Azure Resources
- **Issue:** Unexpectedly high costs are incurred for running the VM or Sentinel.
- **Solution:**
  - **Monitor Resource Usage:** Use Azure Cost Management tools to track and analyze your spending.
  - **Optimize Resource Configuration:** Review and adjust VM size and storage settings to better fit your needs.
  - **Set Up Alerts for Costs:** Configure cost alerts to receive notifications if spending exceeds a certain threshold.

## 7. Slow Performance or Delays in Data Processing
- **Issue:** Data processing or alert generation is slower than expected.
- **Solution:**
  - **Check Resource Limits:** Ensure that your VM and Sentinel setup are not hitting performance bottlenecks or resource limits.
  - **Optimize Data Collection:** Review and optimize the volume of logs being collected to reduce processing time.
  - **Scale Resources:** Consider scaling up your VM or adjusting Sentinel settings to improve performance.

## 8. Incorrect Alert or Log Data Format
- **Issue:** Alerts are not formatted correctly, or log data appears inconsistent.
- **Solution:**
  - **Review Documentation:** Check the Microsoft Sentinel and Azure Monitor documentation for proper log formats and configurations.
  - **Adjust Parsing Rules:** If necessary, update parsing rules or configurations to align with the expected log formats.

## 9. Authentication or Access Issues
- **Issue:** Problems with user authentication or access to Azure resources.
- **Solution:**
  - **Verify Credentials:** Ensure that you are using the correct credentials and that your account has appropriate roles assigned.
  - **Check Multi-Factor Authentication (MFA):** If MFA is enabled, ensure that it’s configured and functioning correctly.
  - **Review Azure AD Settings:** Make sure that Azure Active Directory settings and permissions are correctly configured.


## License
This project is licensed under the MIT License.
