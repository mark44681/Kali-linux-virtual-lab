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

-Network reconnaissance

-Port scanning

-Vulnerability assessment

-Packet analysis 

-Web security testing 

-Exploitation practice

-Security-tool experimentation

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

<img width="75" height="87" alt="{C929BA1D-0EBF-49C3-8857-DB7650F425F0}" src="https://github.com/user-attachments/assets/d9d2d73d-73cc-489a-b0d1-e1851b09393e" />

Tool: 7-Zip
# Step 2. Install VirtualBox
VirtualBox was installed as the hypervisor.
# Step 3. Create the NAT Network
A dedicated NAT Network was created in VirtualBox.

Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled

<img width="1366" height="718" alt="{A9DA1587-808F-4270-A113-B08341FD9CBF}" src="https://github.com/user-attachments/assets/098d5fa7-bc1d-414a-af9c-a8f9013d14af" />

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
<img width="1366" height="643" alt="Screenshot_2026-10-27_10_14_11" src="https://github.com/user-attachments/assets/1e309383-a849-4416-a41d-0e29a023b1f8" />
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
<img width="1366" height="643" alt="Screenshot_2026-10-27_11_02_08" src="https://github.com/user-attachments/assets/001237bc-d33a-4bd5-9c6e-12023fc7688c" />
# step 6. checking the network connectivity
Checked the network connection if it works perfectly well

I did it by pinging google.com and also searching network walks on firefox
<img width="1366" height="643" alt="Screenshot_2026-10-27_12_04_27" src="https://github.com/user-attachments/assets/7f7fb02b-21db-4cb9-b812-2861a4b59fad" /> <img width="1366" height="643" alt="Screenshot_2026-10-27_12_03_37" src="https://github.com/user-attachments/assets/b0c147f4-a267-4a65-96e9-de1059bdd405" />

# Step 7. Create a Clean VM Snapshot
After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:
```
Clean Kali - Network Setup
```
The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

