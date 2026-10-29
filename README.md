🔐 Cybersecurity Lab Environment Setup
Building an isolated virtual lab for penetration testing and ethical hacking practice

           
# 📌Project overview 
This project documents the deployment and initial configuration of kali linux virtual machine.     it spans through the creation of a functional environment for hands-on cybersecurity learning, configuring virtual networking, verify connectivity, and create a snapshot to preserve a known working state.       it also documents the configuration process, verification steps, and practical lessons learned along the way.
# 🎯Project objective
The objectives of the project is to:   
- Deploy and configure a kali linux virtual machine.
- Establish a virtual network using virtualBox NAT Network.
- Assign a consistent IP address to the Kali VM.
- Inspect IP addressing and routing information.
- Test network connectivity.
- Create a virtual machine snapshot for recovery.
- Document the complete setup process.
- Prepare the environment for future cybersecurity projects.
# 🛡️Purpose of the lab
The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis 
- Web security testing 
- Exploitation practice
- Security-tool experimentation
# 🏗️ Lab Architecture
<img width="1346" height="616" alt="1-screenshot-Lab -Architecture (1)" src="https://github.com/user-attachments/assets/c5c4584e-e488-4204-af42-158207b85c34" />


# ⚙️Lab Configuration
|🧩Component |⚙️Configuration |
|---|---|
|🖥️ Host OS |  Windows 11 pro |
|🧠 Host | RAM 8 GB |
|⚡ Processor | Intel Core i5 |
|🧰 Hypervisor | VirtualBox 7.2 |
|🐉 Security OS | Kali Linux 2026.3 |
|🧠 Kali RAM | 2048 MB |
|🌐 Virtual Network	| NAT Network |
|📡 Network Address | 10.0.0.0/24 |
|🐧 Kali IP Address	| 10.0.0.2/24 |
|🚪 Default Gateway | 10.0.0.1 |
|🌍 DNS Server	 | 8.8.8.8 |
# 🪜 Lab Setup Procedure
# Step1. Install 7zip
7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a .7z archive. used to extract the files from both the virtualBox and kali installed

<img width="75" height="87" alt="2-screenshot-7zip-app" src="https://github.com/user-attachments/assets/e62b2da1-89c4-4dce-87d9-d872a4db18b0" />


Tool: 7-Zip
# Step 2. Install VirtualBox
VirtualBox was installed as the hypervisor.
# Step 3. Create the NAT Network
A dedicated NAT Network was created in VirtualBox.

Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled
<img width="1366" height="718" alt="3-screenshot-virtualBox-network-settings" src="https://github.com/user-attachments/assets/6b7a6bd3-174e-4140-a460-2c14830ed55c" />



A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.
# Step 4. Import Kali Linux
The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:
```
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```
The VM was allocated:
```
RAM: 2048 MB
```
<img width="1366" height="643" alt="4-screenshot-Kali-Linux" src="https://github.com/user-attachments/assets/2c54b2b4-f0d0-46a5-b72d-d4c2db3b8171" />

A shared folder was also configured for transferring required files between the host operating system and the Kali VM.
# Step 5. Configure the Kali Linux Network
The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:
```
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```
A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.
<img width="1366" height="643" alt="5-Screenshot-Kali-network-settings" src="https://github.com/user-attachments/assets/d0fe872d-c7ac-495f-b620-830bfd26b198" />

# step 6. checking the network connectivity
Checked the network connection if it works perfectly well

I did it by pinging google.com and also searching network walks on firefox
<img width="1366" height="643" alt="6-Screenshot_Google-Ping" src="https://github.com/user-attachments/assets/9be84edd-790f-430c-b24d-3d4ed79efb25" /> <img width="1366" height="643" alt="7-Screenshot-firefox-search" src="https://github.com/user-attachments/assets/d6771383-0d65-4142-a8be-8e3a502667b4" />



# Step 7. Create a Clean VM Snapshot
After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:
```
Clean Kali - Network Setup
```
The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

