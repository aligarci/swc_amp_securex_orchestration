# swc_amp_securex_orchestration
Workflow of SecureX Action Orchestrator module.
 
# Authors:
Hanna Jabbour
Alicia Garcia Sastre
Remi Vacher
 

# Motivation
The goal of this workflow is to trigger an automated response when we receive an email with an alarm triggered in Stealthwatch Cloud. Leveraging AMP for endpoints API, we will isolate the host and hence, protect our network.

Having a SOC analyst reviewing the event and then taking a decision about the required mitigation is not fast enough. 
We need to isolate the host from the network to reduce the threat ability to spread. 

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
