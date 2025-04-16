# NixGuard

## Objective

The following report involves the set up, testing and automation of NixGuard features and capabilities with the intent of investigating suspicious activities on a network. In order to fully asses NixGuard’s capabilities, the report is structured within the focus areas of Network Analysis, Threat Detection and Incident Response Planning.

### Skills Learned

- ✅ API Integration – Gained hands-on experience integrating the NixGuard API into automated workflows using n8n for real-time threat intelligence and data ingestion.
- ⚙️ Security Automation – Designed and implemented automated detection and response workflows to analyze network traffic, detect anomalies, and trigger mitigation steps.
- 🧠 Threat Analysis – Conducted in-depth analysis of suspicious activity including brute-force attacks, malicious file detections, and open port exploitation using security tools and NixGuard logs.
- 🛡️ Incident Response Planning – Created structured response plans covering containment, eradication, recovery, and mitigation for real-world attacks like rootkits and brute-force attempts.
- 📊 Workflow Design with n8n – Developed scalable, low-code workflows to automate repetitive SOC analyst tasks, demonstrating efficiency in operationalizing incident detection and response.

### Tools Used

- NixGuard – AI-powered cybersecurity tool used for threat detection, log analysis, and identifying suspicious network activity.
- n8n – Low-code workflow automation platform used to build and orchestrate automated threat response workflows.
- Virtual Lab Environment – Simulated real-world network using Ubuntu and Kali Linux VMs for testing intrusion scenarios and monitoring system behavior.

## Steps
1. Environment Setup
-	Signed up for the free version of NixGuard at https://thenex.world/security/subscribe
-	Set up a Ubuntu Virtual Machine in VirtualBox
-	Executed the following command to install NixGuard on the Ubuntu Virtual Machine:

![image](https://github.com/user-attachments/assets/984a5dd0-5e08-4db6-8b13-84f8b7c8f4a6)

Succesfully set up NixGuard in the Ubuntu Virtual Machine and clicked “Done” on the NixGuard website.

![image](https://github.com/user-attachments/assets/2a2b4870-a36b-4092-bf34-2692a9770076)

NixGuard interface launched after the successful onboarding of the agent.

![image](https://github.com/user-attachments/assets/0bf92f28-0e14-42ce-b74c-0f1f83b14ad9)

After initial setup, I conducted the [Penetration Testing Exercise](https://github.com/andcoa)

*Ref 1: Network Diagram*
