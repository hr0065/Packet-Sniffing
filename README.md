# Packet Sniffing & Synflood Detection using Wireshark

## ABSTRACT
                                                                  
Packet sniffing is a method of tapping each packet as it flows across the network; i.e., it is a technique in which a user sniffs data belonging to other users of the network. \
Packet sniffers can operate as an administrative tool or for malicious purposes. It depends on the user's intent. Network administrators use them for monitoring and validating network traffic. Packet sniffers are basically applications. They are programs used to read packets that travel across the network layer of the Transmission Control Protocol/Internet Protocol (TCP/IP) layer. (Basically, the packets are retrieved from the network layer and the data is interpreted.) \
Packet sniffers are utilities that can be efficiently used for network administration. At the same time, it can also be used for nefarious activities. However, a user can employ a number of techniques to detect sniffers on the network and protect the data from sniffers. The technique behind packet sniffing on shared bus broadcast LANs is explained.




##                                                               INTRODUCTION
                                                               
A packet analyzer, also known as packet sniffer, protocol analyzer, or network analyzer, is a computer program or computer hardware such as a packet capture appliance, that can intercept and log traffic that passes over a computer network or part of a network. 
Packet capture is the process of intercepting and logging traffic. As data streams flow across the network, the analyzer captures each packet and, if needed, decodes the packet's raw data, showing the values of various fields in the packet, and analyzes its content according to the appropriate RFC or other specifications.\
A Denial-of-Service (DoS) attack is an attack meant to shut down a machine or network, making it inaccessible to its intended users. DoS attacks accomplish this by flooding the target with traffic, or sending it information that triggers a crash. In both instances, the DoS attack deprives legitimate users (i.e. employees, members, or account holders) of the service or resource they expected.




##                                                              REQUIREMENTS

### Operating System – Kali Linux OS

Kali Linux is a security distribution of Linux derived from Debian and specifically designed for computer forensics and advanced penetration testing. It was developed through rewriting of BackTrack by Mati Aharoni and Devon Kearns of Offensive Security. Kali Linux contains several hundred tools that are well-designed towards various information security tasks, such as penetration testing, security research, computer forensics and reverse engineering.


### Packet Analyzer - WIRESHARK

◈ Wireshark is a free and open-source packet analyzer. It is used for network troubleshooting, analysis, software and communications protocol development, and education. Originally named Ethereal, the project was renamed Wireshark in May 2006 due to trademark issues. \
◈ Wireshark is very similar to tcpdump, but has a graphical front-end and integrated sorting and filtering options.Wireshark lets the user put network interface controllers into promiscuous mode (if supported by the network interface controller), so they can see all the traffic visible on that interface including unicast traffic not sent to that network interface controller's MAC address.


### Metasploit Framework

◈ The Metasploit Framework is a Ruby-based, modular penetration testing platform that enables you to write, test, and execute exploit code. The Metasploit Framework contains a suite of tools that you can use to test security vulnerabilities, enumerate networks, execute attacks, and evade detection. At its core, the Metasploit Framework is a collection of commonly used tools that provide a complete environment for penetration testing and exploit development.


### Vulnerable Website

◈ We cannot attack just any website present on the internet even it be for demonstrating an attack and not actually intending a malicious attack. There are numerous websites on the internet which are specifically made to demonstrate an attack of some kind. As defined it is a intentionally vulnerable website. It can be hacked easily. Some examples can be testphp.vulnweb.com, testfire.net but we will be using the latter in our presentation.




                                                            
##                                                            IMPLEMENTATION & DEMONSTRATION

1)  - Opening Metasploitable Framework 
    - Command : msfconsole 
    - Permission required : Root 
      
<img width="476" alt="image" src="https://user-images.githubusercontent.com/110552885/204135609-8a8f967f-387c-401e-8f22-d77f87e72dc1.png">

 2) - Finding out the target’s ip address 
    - Pinging the website to see if it is running and extracting its ip address 
    - Command : ping 

<img width="476" alt="image" src="https://user-images.githubusercontent.com/110552885/204135644-cd8ea938-a8a1-4577-b49a-e11e9a76fb47.png">


3) - Opening the relevant metasploitable module to perform the attack 
   - Command : use auxiliary/dos/tcp/synflood 
   - Setting up the correct parameters for attack 
   - Command : show options 
   - Giving the attack module the target’s ip address 
   - Command : set RHOSTS [ipaddress] 

<img width="425" alt="image" src="https://user-images.githubusercontent.com/110552885/204135652-32f2dcbd-039f-4be8-b56b-13dbcba2413d.png">

4) - Attacking the website by flooding SYN packets to it 
   - Command : exploit 
   - Ctrl+C to terminate the operation 

<img width="454" alt="image" src="https://user-images.githubusercontent.com/110552885/204135657-1f6ba3b3-4154-4500-8f61-18bef47e37f6.png">

5) - Opening up Wireshark Application 
   - Start Capturing Packets 
   - Any single packet can be further examined by double clicking that particular packet. 

<img width="476" alt="image" src="https://user-images.githubusercontent.com/110552885/204135677-2521b6c7-fbef-4494-be23-728b103d0b1e.png">


## RESULT ANALYSIS
A DOS Attack was done on an intentionally vulnerable website. The attack was analysed through the help of packet sniffing application Wireshark; thousands of SYN packets were seen to be flooded to the target in a matter of seconds and were tracked using Wireshark.

<img width="476" alt="image" src="https://user-images.githubusercontent.com/110552885/204135686-90eddf0d-8cd0-48e5-9557-f3707b8dd4d9.png">




## CONCLUSION
Demonstration and Implementation of Packet Sniffing And Synflood Detection Using Wireshark was concluded successfully and all the Networking were followed for the same.
 



## REFERENCES
https://www.kali.org/docs/ \
https://www.wireshark.org/docs/ \
https://docs.rapid7.com/metasploit/metasploitable-2-exploitability-guide/ \
https://www.rapid7.com/db/modules/auxiliary/dos/tcp/synflood/ 
