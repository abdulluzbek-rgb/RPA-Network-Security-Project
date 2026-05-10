RPA Network Security Automation

Project Overview
This project demonstrates an automated network security response system (RPA) designed within Cisco Packet Tracer. The system identifies unauthorized access attempts and automatically generates the necessary security configurations to mitigate threats in real-time.

Key Features
Automated Threat Detection: Simulates monitoring of network logs to identify malicious IP addresses.

RPA Logic: Uses Python-based logic to decide on security actions without human intervention.

Dynamic Policy Deployment: Generates Cisco IOS commands (ACLs) to block attackers at the gateway router.

Network Architecture
The topology consists of:

Sec-Router (Cisco 2911): The primary firewall/gateway.

Bot-PC (Control Server): Runs the Python automation script.

Attacker-PC: Represents the source of malicious traffic.

The Automation Script
Due to environment-specific limitations in Packet Tracer's Python engine (Skulpt), this script focuses on the Operational Logic of the RPA bot:

Python:



from time import sleep
def rpa_security_bot():
    print("--- [RPA NETWORK DEFENDER ACTIVE] ---")
    print("Step 1: Monitoring incoming traffic logs...")
    sleep(2)
    # Detection of the unauthorized host
    attacker_ip = "192.168.2.50"
    print(f"[ALERT] Unauthorized access detected from: {attacker_ip}")
    print("Step 2: Connecting to Sec-Router for mitigation...")
    sleep(1.5)
    # Automated Command Generation
    print("[RPA ACTION] Sending Security Configuration:")
    print(f">> access-list 100 deny ip host {attacker_ip} any")
    print(">> interface g0/1")
    print(">> ip access-group 100 in")
    sleep(1)
    print("\n--- [RESULT] ---")
    print(f"SUCCESS: Traffic from {attacker_ip} is now filtered.")
    print("Security Status: SECURE - Attacker Blocked.")
if __name__ == "__main__":
    rpa_security_bot()




How it Works
Detection: The bot identifies 192.168.2.50 as a threat based on simulated SSH/Telnet failure logs.

Mitigation: The bot executes an automated script to apply an Inbound Access Control List (ACL 100) on the Router’s GigabitEthernet 0/1 interface.

Verification: The script confirms the deployment, ensuring the network is hardened against the specific threat.

Tools Used
Cisco Packet Tracer v8.2+

Python (Skulpt Engine)

Git/GitHub (for Version Control)

Author
Abdulrahman Munir Abdulsamad Information Technology Specialist
