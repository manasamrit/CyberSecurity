# (WiFi) Network Attack: Intrusion, Reconnaissance, Monitoring


## Project Overview
In this project I will be demonstrating a Network Attack with my home wifi; the intruder will find my network, gain access, scan my local devices, and start tapping the outbound traffic of a target device through ARP Poisoning.





##
### 1. Setup 
For this project I will be using Parrot OS combined with a network adapter and the tools below.

- airodump-ng
- aireplay-ng
- hashcat
- nmap
- ettercap
- wireshark


#
### 2. Reconnaissance
- Set the adapter in monitor mode and use airodump-ng to monitor networks within range. Target a network and get their BSSID and operating channel.
- Use airodump to associate clients with a given access point, get the client MAC address, and set a dumpfile to start collecting their network traffic/comms.
  #
![Screenshot at 2023-08-06 20-30-47](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Recon1.png)
![Screenshot at 2023-08-06 20-30-56](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Recon2.png)
![Screenshot at 2023-08-06 20-36-00](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Recon3.png)




  #
### 3. De-authentication Attack
- use aireplay-ng to target a client, and send deauthentication packets to disassociate them with the AP, knocking them off the network.
   #
![Screenshot at 2023-08-06 20-39-04](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Deauth%20attk1.png)
![Screenshot at 2023-08-06 20-39-18](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Deauth%20attk2.png)





  #
### 4. Capture EAPOL Handshake
- As the device reconnects to their trusted network, airodump will capture the WPA handshake between the client and the AP; you can verify all parts of the EAPOL message in Wireshark.
   #
![Screenshot at 2023-08-06 20-39-33](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Capture%20EAPOL%20Handshake1.png)
![Screenshot at 2023-08-06 20-40-54](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Capture%20EAPOL%20Handshake2.png)



  #
### 5. Hashcat Password Attack
- Convert the file to be used with hashcat, and use a dictionary attack with a well known wordlist 'rockyou', combined with a rule list 'best64'.
- Weak or previously breached passwords will be cracked, and written out with the associated hash.
  #
![Screenshot at 2023-08-06 20-48-22](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Hashcat%20Password%20Attack1.png)
![Screenshot at 2023-08-06 20-48-47](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Hashcat%20Password%20Attack2.png)



  #
### 6. Reconnaissance
- Access the network with the cracked password, run ifconfig to get local IP, use nmap to scan the network.
- nmap can be used to scan for vulnerabilities, scan hosts, and choose a weak target.
   #
![Screenshot at 2023-08-06 20-57-53](https://github.com/blwhit/Network-Intrusion-and-Sniffing/assets/141170960/b7c8905a-3d65-41d8-ac47-24f49c8b4f75)



  #
### 7. Arp Poisoning, MiTM
- Use ettercap to create a man-in-the-middle attack, I am now sitting inbetween the router and the client, secretly forwarding & capturing the traffic.
  #
![Screenshot at 2023-08-06 20-58-56](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Arp%20Poisoning%2C%20MiTM.png)



  #
### 8. Packet Analysis
- Wireshark can be used for detailed packet capture and packet analysis.
- online tools can be used to analyze .pcap for ease of use.
  #
![Screenshot at 2023-08-06 21-02-03](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Packet%20Analysis1.png)
![Screenshot at 2023-08-06 21-07-13](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Packet%20Analysis2.png)
![Capture](https://github.com/manasamrit/CyberSecurity/blob/main/network%20Analyzer%20(Intrusion-sniffing/Screenshots/Packet%20Analysis3.png)
  #





