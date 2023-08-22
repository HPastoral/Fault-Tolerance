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
### Router1 Configuration:

#### Configure Hostname and Interfaces:
Enable
Configuration Terminal
Hostname Router1

Interface G0/0
IP address 172.16.6.1 255.255.255.252
No shutdown

Interface G0/1
IP address 172.16.5.2 255.255.255.252
No shutdown
Exit

#### Configure OSPF:
Configure OSPF on Router1 Commands: <br>
Router OSPF 1 <br>
Network 172.16.6.0 0.0.0.3 area 0 <br>
Network 172.16.5.0 0.0.0.3 area 0 <br>
Exit <br>

#### Configure ACLs:
Configure ACL’s on Router1 Commands:<br>
Access-list 110 deny tcp 10.10.5.0 0.0.0.255 any 21 <br>
Access-list 110 deny tcp 10.10.5.0 0.0.0.255 any 22 <br>
Access-list 110 deny tcp 10.10.5.0 0.0.0.255 any 23 <br>
Access-list 110 deny tcp 10.10.10.0 0.0.0.255 any 21 <br>
Access-list 110 deny tcp 10.10.10.0 0.0.0.255 any 22 <br>
Access-list 110 deny tcp 10.10.10.0 0.0.0.255 any 23 <br>
Access-list 110 permit tcp any any <br>
Access-list 110 permit ip any any <br>
Exit <br>

#### Configure SSH:
Configure SSH on Router 1 Commands: <br>
Ip domain-name faultolerant.com <br>
Ip ssh version 2 <br>
Crypto key gen rsa <br>
2048 <br>
Ip ssh authentication-retries 3 <br>
Line vty 0 15 <br>
Transport input ssh <br>
Login local <br>
Exit <br>

### Router2 Configuration:

#### Configure Hostname and Interfaces:
Enable <br>
Configuration Terminal <br>
Hostname Router2 <br>

Interface G0/0 <br>
IP address 172.16.6.2 255.255.255.252 <br>
No shutdown <br>

Interface G0/1 <br>
IP address 192.168.8.1 255.255.255.248 <br>
No shutdown <br>

Interface S0/0/1:0 <br>
IP address 172.16.7.1 255.255.255.252 <br>
No shutdown <br>
Exit <br>

#### Configure OSPF:
Configure OSPF on Router2 Commands: <br>
Router OSPF 1 <br>
Network 172.16.6.0 0.0.0.3 area 0 <br>
Network 172.16.7.0 0.0.0.3 area 0 <br>
Network 192.168.8.1 0.0.0.7 area 0 <br>
Exit <br>

#### Configure ACLs:
Configure ACL’s on Router2 Commands: <br>
Access-list 110 deny tcp 10.10.5.0 0.0.0.255 any 21 <br>
Access-list 110 deny tcp 10.10.5.0 0.0.0.255 any 22 <br>
Access-list 110 deny tcp 10.10.5.0 0.0.0.255 any 23 <br>
Access-list 110 deny tcp 10.10.10.0 0.0.0.255 any 21 <br>
Access-list 110 deny tcp 10.10.10.0 0.0.0.255 any 22 <br>
Access-list 110 deny tcp 10.10.10.0 0.0.0.255 any 23 <br>
Access-list 110 permit tcp any any <br>
Access-list 110 permit ip any any <br>
Exit <br>

#### Configure SSH:
Configure SSH on Router 2 Commands: <br>
Ip domain-name faultolerant.com <br>
Ip ssh version 2 <br>
Crypto key gen rsa <br>
2048 <br>
Ip ssh authentication-retries 3 <br>
Line vty 0 15 <br>
Transport input ssh <br>
Login local <br>
Exit <br>

(Continue with Router3 and subsequent configurations in a similar manner...)

### ServerSide Switch Configuration:

#### Basic Hardening Commands:
Enable <br>
Configuration Terminal <br>
Hostname ServerSide <br>
service password-encryption <br>
Line con 0 <br>
Password password <br>
Login <br>
Enable secret password <br>
Username Admin password password <br>
Interface range F2/0/6-48 <br>
Shutdown <br>

### ClientSide Switch Configuration:

#### Basic Hardening Commands:
Enable <br>
Configuration Terminal <br>
Hostname ClientSide <br>
service password-encryption <br>
Line con 0 <br>
Password password <br>
Login <br>
Enable secret password <br>
Username Admin password password <br>
Interface range F2/0/17-47 <br>
Shutdown <br>
Exit <br>
Configure VLAN 5 <br>
Interface range F6/0/1-5 <br>
switchport access vlan 5 <br>
switchport mode access <br>
Exit <br>

### Linux Mint 20 (Apache Tomcat Web Server) Configuration:

#### CLI Commands:
sudo apt update <br>
sudo apt upgrade <br>
sudo apt install -y openjdk-11-jdk <br>
sudo groupadd tomcat <br>
sudo mkdir /opt/tomcat <br>
sudo useradd -g tomcat -d /opt/tomcat -s /usr/sbin/nologin tomcat <br>
wget https://downloads.apache.org/tomcat/tomcat-9/v9.0.36/bin/apache-tomcat-9.0.36.tar.gz <br>
sudo tar -zxvf apache-tomcat-9.0.36.tar.gz <br>
sudo mv apache-tomcat-9.0.36 /opt/tomcat/ <br>
sudo chown -R tomcat:tomcat /opt/tomcat/ <br>
sudo update-java-alternatives -l <br>
sudo systemctl daemon-reload <br>
sudo systemctl start tomcat <br>
sudo systemctl status tomcat <br>
sudo nano /opt/tomcat/conf/tomcat-users.xml (add or uncomment the following line right before the last line) <br>
<rolename="admin-gui,manager-gui"/> <br>
