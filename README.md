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

2. Network Analysis

In order to test the network analysis capabilities of NixGuard, a brute force Hydra attack exercise using Kali Linux was conducted. First, each VM was set configured to be accessible to the network and to get a static IP which the Kali VM can use to attack the Ubuntu VM with.

![image](https://github.com/user-attachments/assets/e39593d6-d332-46da-bfdb-481e675ff6c6)

Installed SSHServer on the Ubuntu VM:

![image](https://github.com/user-attachments/assets/f7596f69-c94c-4c85-9e5f-c0fd58e6bf49)

Enabled SSH and created a new user to be used as a target by the Kali VM:

![image](https://github.com/user-attachments/assets/046a2b3c-36e7-47d0-b9e4-84df6fd2bec2)

After opening up the SSH port on the Ubuntu Virtual Machine the agent is installed on, NixGuard logged the network changes in the Ubuntu VM’s settings and created an alert depicting the timestamp (March 5, 2025 at 4:39:46 PM EST) and port number (22).

![image](https://github.com/user-attachments/assets/c8122044-3023-43a0-8934-c9ffe38e1361)

Used the Nix AI to analyze the log and get a deeper dive on what caused this alert, confirming if it is a false-positive. The log depicts that port 22 was opened or closed.

![image](https://github.com/user-attachments/assets/eb2b4997-591b-4c3a-affc-1a48e65f4271)

After enabling SSH, a new alert appeared in NixGuard:

![image](https://github.com/user-attachments/assets/152bf315-3e84-4ad4-9ad8-578277c8c894)

The installation of SSH Server and enablement of SSH caused NixGuard to log it as a possible kernel level rootkit:

![image](https://github.com/user-attachments/assets/a96862eb-a824-4c69-9438-3c3c6625ae7c)

Penetration Test:
-	Hydra Attack exercise: The Hydra tool within Kali Linux was used to attempt brute force login on the Ubuntu VM by using the command hydra -l hydratest -P /usr/share/wordlists/rockyou.txt.gz ssh://"target IP"

![image](https://github.com/user-attachments/assets/9cdbbcad-982b-4f29-a753-1f0e8f19cbef)
Note: Hydra tested passwords from the rockyou.txt.gz file to obtain the hydratest user login.

-	NixGuard did not detect any new event regarding the Kali Linux attack on the Ubuntu VM on which NixGuard is installed on.

![image](https://github.com/user-attachments/assets/f335740d-c5a2-4d01-b94e-496868d91bdc)

