# ARPSpoofing
- ARP spoofing or poisoning is an attack in which attacker sends address resolution protocol(ARP) messages onto a local area network(LAN).
- ARP spoofing may allow an attacker to intercept data frames on a network, modify the traffic, or stop all traffic.
- This attack is also used as an opening for other attacks, such as denial of service , man in the middle, or session hijacker attacks.

![Image 14](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/14.png)
## Different types of ARP Attacks
- MITM Attack
- MAC Flooding
- Storms
- DOS

## MITM( Man in the Middle) Attack
A malicious user:
      1. Inserts his computer between the communications path of two target computers
      2. Forwards frames between the two target computers so communications are not interrupted
All Internet traffic could be intercepted if this was performed between the target and router

## MAC Flooding
Send spoofed ARP replies to a switch at an extremely rapid rate
Switch’s  port/MAC table will overflow
Results vary
Some switches will revert into broadcast mode, allowing sniffing to then be performed

## Storms
Poisoning caches with the broadcast address could cripple large networks

## Denial of Service(DOS) Attack
Update ARP caches with non-existent MAC addresses
- Causes frames to be dropped
- Could be sent out in a sweeping fashion to DoS all clients in the network
Possible side effect of post-MiM Attacks

## Detection of ARP Spoofing
We have used Kali Linux Environment and tools such as Wireshark and Ettercap.
We have identified hosts and selected a Victim using Ettercap tool by performing Unified sniffing.
Hosts are filtered using Victims IP Address in Wireshark and the captured packets are analysed

## Code of Simulation
1.	Install the VMware workstation and install the Linux operating system.
2.	Login into the Linux using username pass “root, root”.
3.	Make sure you are connected to local LAN and check the IP address by typing the command ifconfig in the terminal.

![Image 13](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/13.png)
4.	Open up the terminal and type “Ettercap –G” to start the graphical version of Ettercap.

![Image 1](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/1.png)
5.	Now click the tab “sniff” in the menu bar and select “unified sniffing” and click OK to select the interface. We are going to use “eth0” which means Ethernet connection.

![Image 2](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/2.png)
6.	Now click the “hosts” tab in the menu bar and click “scan for hosts”. It will start scanning the whole network for the alive hosts.

![Image 3](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/3.png)
7.	Next, click the “hosts” tab and select “hosts list” to see the number of hosts available in the network. This list also includes the default gateway address. We have to be careful when we select the targets.

![Image 4](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/4.png)
8.	Now we have to choose the targets. In MITM, our target is the host machine, and the route will be the router address to forward the traffic. In an MITM attack, the attacker intercepts the network and sniffs the packets. So, we will add the victim as “target 1” and the router address as “target 2.”
In VMware environment, the default gateway will always end with “2” because “1” is assigned to the physical machine.

![Image 5](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/5.png)
9.	So we will add target 1 as victim IP and target 2 as router IP.
10.	Now click on “MITM” and click “ARP poisoning”. Thereafter, check the option “Sniff remote connections” and click OK.

![Image 6](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/6.png)

![Image 7](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/7.png)
11.	Click “start” and select “start sniffing”. This will start ARP poisoning in the network which means we have enabled our network card in “promiscuous mode” and now the local traffic can be sniffed. 
Note − We have allowed only HTTP sniffing with Ettercap, so don’t expect HTTPS packets to be sniffed with this process.

![Image 8](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/8.png)

![Image 9](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/9.png)

![Image 10](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/10.png)
12.	Now  launch wireshark and select the lan connection from the list of connections. It will display the packets that go through the network. Before doing that we select the connection in the capture interface. Then the packets transferring in the network in between the connections is shown. We filter it based on the IP of victim. here we can see the packets being transferred and can see what the victim does. Now if the victim enter something to the page and we can see what details that he entered.

![Image 11](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/11.png)
13.	This result if our victim logged into some websites. You can see the results in the toolbar of Ettercap.

![Image 12](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/images/12.png)

## Poster and Technical Paper
Here is the poster for this Project 

![Image 15](https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/Final%20Poster.png)

The Technical Paper can be found here:
https://github.com/DivyaSamragniNadakuditi/ARPSpoofing/blob/master/project_paper.pdf





