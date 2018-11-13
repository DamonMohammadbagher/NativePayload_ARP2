# NativePayload_ARP2



# NativePayload_ARP2.sh help :

	Example Step1: (System A ) ./NativePayload_ARP2.sh -listen (Packet Number)
  
	Example Step2: (System B ) ./NativePayload_ARP2.sh -send TextFile.txt [VlanName] [vlan-Subnet/mask] [vlan-Broadcast]  -p [vlan-PingIPv4] [(wlan0,eth0,vboxnet0,etc.)]
  
  example Step1 (System A1 ) IPv4:192.168.56.101 : ./NativePayload_ARP2.sh -listen 176
  
  example Step1 (System A2 ) IPv4:192.168.56.102 : ./NativePayload_ARP2.sh -listen 176
  
  example  Step2 (System B ) IPv4:192.168.56.1 : ./NativePayload_ARP2.sh -send Test.txt vlan3 192.168.222.1/24 192.168.222.255 -p 192.168.222.2 vboxnet0
  
  Description: with Step1 this script will get packets from (system B) , with Step2 you will send textfile.txt to all systems in (LAN) via ARP Broadcast Traffic by "Vid Tag".
  
  Note: (System B) is "VM host or Physical system" and (Sytem A1/A2) are "Virtual systems"
  
	
  
  
	
  
  ![](https://github.com/DamonMohammadbagher/NativePayload_ARP2/blob/master/Pictures/step1.png)

  ![](https://github.com/DamonMohammadbagher/NativePayload_ARP2/blob/master/Pictures/step2.png)

  ![](https://github.com/DamonMohammadbagher/NativePayload_ARP2/blob/master/Pictures/step3.png)

  ![](https://github.com/DamonMohammadbagher/NativePayload_ARP2/blob/master/Pictures/final.png)
