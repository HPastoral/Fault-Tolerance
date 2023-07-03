# Fault-Tolerance

Fault-tolerance in packet switching helps maintain reliable communication by providing mechanisms to handle and recover from failures. It ensures that packets are delivered accurately and efficiently, even in the presence of faults. By implementing fault-tolerant measures, packet-switched networks can prevent data loss, maintain optimal performance, and uphold the quality of service expected by users.

Strategies for Achieving Fault-Tolerance in Packet Switching

Several strategies and techniques are employed to achieve fault-tolerance in packet-switched networks:

Redundancy: Redundancy involves duplicating critical network components, such as links, routers, or switches. By creating backup paths or resources, redundancy allows packets to be rerouted in case of failures, minimizing disruptions and ensuring continuous data transmission.

![Snag_f1d472](https://github.com/HPastoral/Fault-Tolerance/assets/135756003/334c2067-2a71-4e94-825f-6c563ff941dc)

Packet switching, the fundamental technology behind the Internet, involved breaking down data into small packets and routing them independently across a network. This approach allowed for more efficient use of network resources, better reliability, and the ability to adapt to network failures. These characteristics made packet switching well-suited for the Cold War context, where maintaining communication during a crisis or attack was crucial.

# A Fault-tolerant Network

![Snag_f700f8](https://github.com/HPastoral/Fault-Tolerance/assets/135756003/4ab0d3b0-c445-44be-8de2-0473d3f49731)

In this project, I embarked on showcasing the paramount significance of fault-tolerance in computer networks by implementing a robust and resilient network infrastructure. To demonstrate this concept, I utilized three Cisco routers, each carefully configured with various essential components such as Access Control Lists (ACLs), subnets, Virtual LANs (VLANs), Dynamic Host Configuration Protocol (DHCP), and routing protocols.

The implementation of ACLs allowed for granular control over network traffic by defining specific rules and permissions. By configuring ACLs on the routers, I could regulate the flow of data based on source and destination IP addresses, ports, and other parameters. This fine-grained control not only enhanced security but also contributed to fault-tolerance by mitigating potential threats and preventing unauthorized access.

Subnetting, a technique that divides a larger network into smaller subnetworks, played a pivotal role in optimizing network performance and facilitating fault-tolerance. By subnetting the network, I created smaller and more manageable segments, enabling efficient resource allocation and reducing the risk of network congestion. Additionally, subnetting enhances fault-tolerance by isolating network issues within specific subnets, preventing them from affecting the entire network.

![Snag_1050133](https://github.com/HPastoral/Fault-Tolerance/assets/135756003/1f55f411-cb09-43f1-a59d-abafdd7f32c2)


The implementation of VLANs further enhanced fault-tolerance by logically segmenting the network into virtual networks. By creating separate broadcast domains, VLANs provided increased network security, improved bandwidth utilization, and simplified network management. In the event of a failure or disruption within one VLAN, the impact on other VLANs would be minimized, ensuring uninterrupted communication and enhancing fault-tolerance.

![Snag_106a619](https://github.com/HPastoral/Fault-Tolerance/assets/135756003/a8ec132f-4293-4079-8c98-b7c8221b2c74)

DHCP, a protocol used to automatically assign IP addresses to devices on a network, played a vital role in ensuring fault-tolerance and efficient network management. By configuring DHCP on the routers, devices could dynamically obtain IP addresses, eliminating manual IP address assignment and reducing the chances of conflicts. DHCP also facilitated fault-tolerance by allowing for the rapid reconfiguration and reallocation of IP addresses in the event of network changes or failures.

Routing protocols, such as OSPF (Open Shortest Path First), were configured on the routers to enable efficient and dynamic routing of network traffic. These protocols allowed the routers to exchange information, compute optimal paths, and adapt to network changes in real-time. By employing fault-tolerant routing protocols, the network could quickly adapt to failures, reroute traffic, and maintain continuous connectivity.

This project effectively showcased the significance of fault-tolerance in computer networks through the implementation of a robust network infrastructure using three Cisco routers. By configuring ACLs, subnets, VLANs, DHCP, and routing protocols, the network demonstrated enhanced security, optimized performance, and the ability to withstand failures. The project highlighted the critical role of fault-tolerance in ensuring uninterrupted communication and reliable network operation, reinforcing the importance of implementing resilient network architectures in various real-world scenarios.

# Cisco Routers and Switches from Ebay
![Snag_111b6cd](https://github.com/HPastoral/Fault-Tolerance/assets/135756003/cba326e7-014d-4e01-adf1-459ccf5e3e5f)

**Hardware and Software Requirements:**

- 3x Cisco 1921 Routers<br>
- 2x Catalyst 3750 Series Switch<br>
- 7x Ethernet cables<br>
- 1x Serial console cable<br>
- 1x Linux Mint 20 (Apache Web Server)<br>
  - Installed Software:
  - Apache Tomcat Webserver <br>
- 1x Linux Mint 20 Client/Pentester <br>
  - Installed Software:
  - Nmap
  - Wireshark
  - Metasploit Framework
  - Ettercap
- 1x Windows 10 Client
  - Putty



# Configuration Time!!
![Snag_111c0df](https://github.com/HPastoral/Fault-Tolerance/assets/135756003/26051e9f-4729-4576-84af-5b0d30476120)

# Configurations:
Proper hardware and software configurations must be followed and understood for this network 
to function as intended. Certain changes to a configuration may be made to accommodate some 
fixed hardware configurations such as interface names within a router or a switch. As long as 
there is an understanding of how these network devices function and are configured, some 
changes can be made to these configurations to accommodate these differences.
<br>

# Network Cable Configurations: (Work Inprogress..needs editing)
**Router1 to Router2:** 
<br>
Connect Router1’s interface G0/0 to Router2’s interface G0/0 with an ethernet cable. 
<br>
**Router1 to Router3:** <br>
Connect Router1’s interface G0/1 to Router3’s interface G0/1 with an ethernet cable.<br>
**Router2 to Router3:** <br>
Connect Router2’s interface S0/0/1:0 to Router3’s interface S0/0/1:0 with an ethernet cable.<br>
**Router2 to Serverside Switch:** <br>
Connect Router2’s interface G0/1 to Serverside Switch’s interface F2/0/1 with an ethernet cable.<br>
**Serverside Switch to Linux Mint (Apache Web Server):** <br>
Connect Serverside Switch’s interface F2/0/2 to the Web Server’s network card with an ethernet 
cable.<br>
Router3 to Clientside Switch:<br>
Connect Router3’s interface G0/1 to Clientside Switch’s interface F6/0/48 with an ethernet 
cable.<br>
Clientside Switch to Linux Mint Client/Pentester:
Connect Clientside Switch’s interface F6/0/2 to the Linux Mint’s network card with an ethernet 
cable.<br>
Clientside Switch to Windows 10 Client:<br>
Connect Clientside Switch’s interface F6/0/1 to the Windows 10’s network card with an ethernet 
cable.<br>
# Router Configurations:
To configure the routers, Putty must be installed in the Windows 10 Computer and connect the 
serial console cable to the Router’s console port. The following configuration must be programmed 
to each router as specified or depending on the hardware interfaces as need.
Router1 Configuration:
Configure Hostname and IPs on Router1’s Interfaces
Commands:
1. Enable
2. Configuration Terminal
Senior Cybersecurity Project: Project Description
3. Hostname Router1
4. Interface G0/0
5. IP address 172.16.6.1 255.255.255.252
6. No shutdown
7. Interface G0/1
8. IP address 172.16.5.2 255.255.255.252
9. No shutdown
10. Exit
Configure OSPF on Router1
Commands:
1. Router OSPF 1
2. Network 172.16.6.0 0.0.0.3 area 0
3. Network 172.16.5.0 0.0.0.3 area 0
4. Exit
Configure ACL’s on Router1
Commands:
1. Access-list 110 deny tcp 10.10.5.0 0.0.0.255 any 21
2. Access-list 110 deny tcp 10.10.5.0 0.0.0.255 any 22
3. Access-list 110 deny tcp 10.10.5.0 0.0.0.255 any 23
4. Access-list 110 deny tcp 10.10.10.0 0.0.0.255 any 21
Senior Cybersecurity Project: Project Description
5. Access-list 110 deny tcp 10.10.10.0 0.0.0.255 any 22
6. Access-list 110 deny tcp 10.10.10.0 0.0.0.255 any 23
7. Access-list 110 permit tcp any any
8. Access-list 110 permit ip any any
9. Exit
Configure SSH on Router 1
Commands:
1. Ip domain-name faultolerant.com
2. Ip ssh version 2
3. Crypto key gen rsa
4. 2048
5. Ip ssh authentication-retries 3
6. Line vty 0 15
7. Transport input ssh
8. Login local
9. Exit
Basic Hardening
1. service password-encryption
2. Line con 0
3. Password password
4. Login 
Senior Cybersecurity Project: Project Description
5. Exit
6. Enable secret password
7. Username Admin password password
8. line aux 0
9. Password password
10. exit
Router2 Configuration:
Configure Hostname and IPs on Router2’s Interfaces
Commands:
1. Enable
2. Configuration Terminal
3. Hostname Router2
4. Interface G0/0
5. IP address 172.16.6.2 255.255.255.252
6. No shutdown
7. Interface G0/1
8. IP address 192.168.8.1 255.255.255.248
9. No shutdown
10. Interface S0/0/1:0
11. IP address 172.16.7.1 255.255.255.252
12. No shutdown
13. Exit
Senior Cybersecurity Project: Project Description
Configure OSPF on Router2
Commands:
1. Router OSPF 1
2. Network 172.16.6.0 0.0.0.3 area 0
3. Network 172.16.7.0 0.0.0.3 area 0
4. Network 192.168.8.1 0.0.0.7 area 0
5. Exit
Configure ACL’s on Router2
Commands:
1. Access-list 110 deny tcp 10.10.5.0 0.0.0.255 any 21
2. Access-list 110 deny tcp 10.10.5.0 0.0.0.255 any 22
3. Access-list 110 deny tcp 10.10.5.0 0.0.0.255 any 23
4. Access-list 110 deny tcp 10.10.10.0 0.0.0.255 any 21
5. Access-list 110 deny tcp 10.10.10.0 0.0.0.255 any 22
6. Access-list 110 deny tcp 10.10.10.0 0.0.0.255 any 23
7. Access-list 110 permit tcp any any
8. Access-list 110 permit ip any any
9. Exit
Configure SSH on Router 2
Commands:
Senior Cybersecurity Project: Project Description
1. Ip domain-name faultolerant.com
2. Ip ssh version 2
3. Crypto key gen rsa
4. 2048
5. Ip ssh authentication-retries 3
6. Line vty 0 15
7. Transport input ssh
8. Login local
9. Exit
Basic Hardening
Commands:
1. service password-encryption
2. Line con 0
3. Password password
4. Login 
5. Exit
6. Enable secret password
7. Username Admin password password
Router3 Configuration:
Configure Hostname and IPs on Router3’s Interfaces
Senior Cybersecurity Project: Project Description
Commands:
1. Enable
2. Configuration Terminal
3. Hostname Router3
4. Interface G0/1
5. IP address 172.16.5.1 255.255.255.252
6. No shutdown
7. Interface S0/0/1:0
8. IP address 172.16.7.2 255.255.255.252
9. No shutdown
10. Interface G0/0.5 10.10.5.1 255.255.255.240
11. encapsulation dot1Q 5
12. No shutdown
13. Interface G0/0.10 10.10.10.1 255.255.255.192
14. Encapsulation dot1Q 10
15. No shutdown 
16. Exit
Configure OSPF on Router3
Commands:
1. Router OSPF 1
2. Network 172.16.5.0 0.0.0.3 area 0
3. Network 172.16.7.0 0.0.0.3 area 0
Senior Cybersecurity Project: Project Description
4. Network 10.10.5.0 0.0.0.15 area 0
5. Network 10.10.10.0 0.0.0.63 area 0
6. Exit
Configure SSH on Router 3
Commands:
1. Ip domain-name faultolerant.com
2. Ip ssh version 2
3. Crypto key gen rsa
4. 2048
5. Ip ssh authentication-retries 3
6. Line vty 0 15
7. Transport input ssh
8. Login local
9. Exit
Basic Hardening
Commands:
1. service password-encryption
2. Line con 0
3. Password password
4. Login 
5. Exit
Senior Cybersecurity Project: Project Description
6. Enable secret password
7. Username Admin password password
Switch Configurations:
To configure the Switches, Putty must be installed in the Windows 10 Computer and connect the 
serial console cable to the Switch’s console port. The following configuration must be 
programmed to each switch as specified or depending on the hardware interfaces as need.
ServerSide Switch:
Basic Hardening
Commands:
1. Enable
2. Configuration Terminal
3. Hostname ServerSide
4. service password-encryption
5. Line con 0
6. Password password
7. Login
8. Enable secret password
9. Username Admin password password
10. Interface range F2/0/6-48
11. Shutdown
Senior Cybersecurity Project: Project Description
ClientSide Switch:
Basic Hardening
Commands:
1. Enable
2. Configuration Terminal
3. Hostname ClientSide
4. service password-encryption
5. Line con 0
6. Password password
7. Login
8. Enable secret password
9. Username Admin password password
10. Interface range F2/0/17-47
11. Shutdown
12. Exit
Configure VLAN 5
1. Interface range F6/0/1-5
2. switchport access vlan 5
3. switchport mode access
4. exit
Configure VLAN 10
Senior Cybersecurity Project: Project Description
1. Interface range F6/0/6-16
2. Switchport mode vlan 10
3. Switchport mode access
4. Exit
Configure Switchport Trunk
1. Interface F6/0/48
2. Switchport mode trunk
Computer Configurations:
Linux Mint 20 (Apache Tomcat Web Server)
Using the Command-line interface follow the commands to install and configure the Apache 
Tomcat Web server.
CLI Commands:
1. sudo apt update
2. sudo apt upgrade
3. sudo apt install -y openjdk-11-jdk
4. sudo groupadd tomcat
5. sudo mkdir /opt/tomcat
6. sudo useradd -g tomcat -d /opt/tomcat -s /usr/sbin/nologin tomcat
(Note: If the link does not work download it from the official Apache Tomcat website)
Senior Cybersecurity Project: Project Description
7. wget https://downloads.apache.org/tomcat/tomcat-9/v9.0.36/bin/apache-tomcat 9.0.36.tar.gz
8. sudo tar -zxvf apache-tomcat-*.tar.gz
9. sudo mv apache-tomcat-*/* /opt/tomcat/
10. sudo chown -R tomcat:tomcat /opt/tomcat/
Run Tomcat:
1. sudo update-java-alternatives -l
2. sudo systemctl daemon-reload
3. sudo systemctl start tomcat
a. (Note ensure that the tomcat service is running by using the command below)
4. sudo systemctl status tomcat
Configure Tomcat:
1. sudo nano /opt/tomcat/conf/tomcat-users.xml
(Note: add or uncomment the following line right before the last line”</tomcat-users>”)
2. <rolename="admin-gui,manager-gui"/>
<user username="admin" password="vagrant" roles="manager-gui,admin-gui"/>
<user username="tomcat" password="s3cret" roles="manager-gui,admin-gui"/>
<user username="role1" password="root" roles="manager-gui,admin-gui"/>
3. Then save and exit the file.
Senior Cybersecurity Project: Project Description
Enable Remote Access to Tomcat:
(Note: Edit the following files to allow remote access to Tomcat’s managerial page)
1. sudo nano /opt/tomcat/webapps/manager/META-INF/context.xml
2. sudo nano /opt/tomcat/webapps/host-manager/META-INF/context.xml
(Note: Edit the line near the bottom with the following)
3. allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1|.*" />
(Note: Save both file and restart the Tomcat service by using the command below)
4. sudo systemctl restart tomcat
Access the Tomcat default page:
Open a web browser and enter the Linux Mint IP address and add “:8080” to its IP, this should 
show the Tomcat default page. Example: 192.168.8.3:8080
Linux Mint 20 (Client/Pentester)
The Linux Mint 20 Client/Pentester should have the following programs installed in its system. 
The installation instructions will be as follows using the Command-line interface:
Senior Cybersecurity Project: Project Description
Nmap Installation:
Commands:
Sudo apt install nmap -y
Wireshark Installation:
Commands:
sudo apt install Wireshark -y
(Note: if prompt to allow non-root user to use Wireshark select no)
Metasploit Framework Installation:
Commands:
1. sudo apt update
2. sudo apt upgrade -y
3. sudo reboot
4. cd /tmp
(Note: the two lines below should be entered as one line)
5. curl https://raw.githubusercontent.com/rapid7/metasploit omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > 
msfinstall
6. chmod +x msfinstall
7. sudo ./msfinstall
8. msfdb init
Senior Cybersecurity Project: Project Description
(Note: to run Metasploit Framework enter the command below)
9. msfconsole
Ettercap Installation
Commands:
Sudo apt install Ettercap-graphical
Windows 10 (Client)
Putty should be installed in windows 10 to configure the Cisco Routers and the Switches via the 
console port.
Putty Installation
Download the appropriate software in the Putty website: 
https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html
Activate the installer and follow the prompts to finish the installation.
Senior Cybersecurity Project: Project Description
Connectivity Verification:
To ensure that the network is configured correctly and is functioning as intended, testing the 
connectivity of each interface must be established. Using the Server and Client Computers an 
ICMP or ping command may be used to establish connectivity to all the interfaces within the 
network. A more detailed version of this connectivity verification may be reviewed in the Testing 
Documentation of this project. 
Windows 10 Client:
Commands:
(Note: Using the command prompt, type in these commands and ensure that a successful ping 
command is issued)
Router 1
Ping 172.16.6.1
Ping 172.16.5.2
Router 2
Ping 192.168.8.1
Ping 172.16.6.2
Ping 172.16.7.1
Router 3
Ping 172.16.7.2
Ping 172.16.5.1
Ping 10.10.5.1
Ping 10.10.10.1
Senior Cybersecurity Project: Project Description
Linux Mint Apache Web Server
(Note: Ensure that the IP address of the Server is accurate due to the DHCP)
Ping 192.168.8.2
Linux Mint 20 Client/Pentester (Vlan 10)
(Note: Ensure that the IP address of the Linux Mint is accurate due to the DHCP)
Ping 10.10.10.2
Linux Mint Apache Webserver:
Commands:
(Note: Using the CLI, type in these commands and ensure that a successful ping command is 
issued. A CTR+Z may be used to interrupt the command once satisfied with the results)
Router 1
ping 172.16.6.1
ping 172.16.5.2
Router 2
ping 192.168.8.1
ping 172.16.6.2
ping 172.16.7.1
Router 3
ping 172.16.7.2
ping 172.16.5.1
ping 10.10.5.1
ping 10.10.10.1
Senior Cybersecurity Project: Project Description
Windows 10 Client (Vlan 5)
(Note: Ensure that the IP address of the Windows 10 Client is accurate due to the DHCP)
ping 10.10.5.2
Linux Mint 20 Client/Pentester (Vlan 10)
(Note: Ensure that the IP address of the Linux Mint is accurate due to the DHCP)
Ping 10.10.10.2
Linux Mint 20 Client/Pentester:
Commands:
(Note: Using the CLI, type in these commands and ensure that a successful ping command is 
issued. A CTR+Z may be used to interrupt the command once satisfied with the results)
Router 1
ping 172.16.6.1
ping 172.16.5.2
Router 2
ping 192.168.8.1
ping 172.16.6.2
ping 172.16.7.1
Router 3
ping 172.16.7.2
ping 172.16.5.1
ping 10.10.5.1
ping 10.10.10.1
Senior Cybersecurity Project: Project Description
Windows 10 Client (Vlan 5)
(Note: Ensure that the IP address of the Windows 10 Client is accurate due to the DHCP)
ping 10.10.5.2
Linux Mint Apache Webserver 
(Note: Ensure that the IP address of the Linux Mint Apache Web Server is accurate due to the 
DHCP)
