![License: CISCO](https://img.shields.io/badge/License-CISCO-blue.svg)

# swc_amp_securex_orchestration
Workflow of SecureX Action Orchestrator module.
 
# Authors:
- Hanna Jabbour
- Alicia Garcia Sastre
- Remi Vacher
 

# Motivation
The goal of this workflow is to trigger an automated response when we receive an email with an alarm triggered in Stealthwatch Cloud. Leveraging AMP for endpoints API, we will isolate the host and hence, protect our network.

Having a SOC analyst reviewing the event and then taking a decision about the required mitigation is not fast enough. 
We need to isolate the host from the network to reduce the threat ability to spread. 

https://youtu.be/3dW6_CYSGR4

![alt text](https://github.com/aligarci/swc_amp_securex_orchestration/blob/master/orchestration.png) 



# Scenario
- Remote or local worker connected to the network.
- The end device has AnyConnect and AMP for endpoint installed for endpoint security and connectivity
- AnyConnect is integrated with SWE to share process information and flow information
- Stealthwatch is monitoring the network end to end
- Stealthwatch is integrated with CTR, SecureX and AO

![alt text](https://github.com/aligarci/swc_amp_securex_orchestration/blob/master/scenario.png) 



# Workflow steps
1. Device initiate a suspicious behavior
2. SWC triggers an alert on this communication and sends a notification to the admin
3. Action Orchestrator (AO) parsing constantly email events. 
4. When the alarm email is received, it will trigger the response workflow
5. Parsing of endpoint IP from email
6. Find AMP GUID that is the source of the malicious behavior
7. Isolate host with AMP GUID

![alt text](https://github.com/aligarci/swc_amp_securex_orchestration/blob/master/steps.png) 

![alt text](https://github.com/aligarci/swc_amp_securex_orchestration/blob/master/workflow.png) 



# How to use it
- Log into Action Orchestration 
- Click on workflow tab
- Click on import
- Import from: "browse"
- Paste JSON file content into text box
- Check "import as a new workflow (clone)
- Click on import
- Now the workflow is imported. You can click on it and will be able to modify it:
![alt text](https://github.com/aligarci/swc_amp_securex_orchestration/blob/master/workflow2.png) 

- On the right pannel, you will be able to add the target and account keys of your AMP4E endpoints.
![alt text](https://github.com/aligarci/swc_amp_securex_orchestration/blob/master/amp.png) 

- Click now on "Wait for SMC email", and modify the target id to match your email credentials
![alt text](https://github.com/aligarci/swc_amp_securex_orchestration/blob/master/email.png) 



