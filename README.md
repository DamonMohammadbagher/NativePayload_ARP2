# NativePayload_ARP2



# NativePayload_ARP2.sh help :

	Example Step1: (System A ) ./NativePayload_ARP2.sh -listen (Packet Number)
  
	Example Step2: (System B ) ./NativePayload_ARP2.sh -send TextFile.txt [VlanName] [vlan-Subnet/mask] [vlan-Broadcast]  -p [vlan-PingIPv4] [(wlan0,eth0,vboxnet0,etc.)]
  
  example Step1 (System A1 ) IPv4:192.168.56.101 : ./NativePayload_ARP2.sh -listen 176
  
  example Step1 (System A2 ) IPv4:192.168.56.102 : ./NativePayload_ARP2.sh -listen 176
  
  example  Step2 (System B ) IPv4:192.168.56.1 : ./NativePayload_ARP2.sh -send Test.txt vlan3 192.168.222.1/24 192.168.222.255 -p 192.168.222.2 vboxnet0
  
  Description: with Step1 this script will get packets from (system B) , with Step2 you will send textfile.txt to all systems in (LAN) via ARP Broadcast Traffic by "Vid Tag".
  
  Note: (System B) is "VM host or Physical Machine" and (System A1/A2) are "Virtual Machine"
  
  
  	Important Point about "switch -listen (Packet Number)" : 
  
  	your "PacketNumber" will be TextFile.txt Length * 4 it means :
  
  	for example this is our mytest.txt file :
  
		#cat mytest.txt | xxd -c 10
		0000000: 5365 6e64 696e 6720 4441  Sending DA
		000000a: 5441 2076 6961 2041 5250  TA via ARP
		0000014: 2042 726f 6164 6361 7374   Broadcast
		000001e: 2026 2056 4944 0a          & VID.
 
 	as you can see we have 36 Bytes so  (36 * 4 = 144) now your PacketNumber is 144
 
 		system A  , Step 1: ./NativePayload_ARP2.sh -listen 144
 
		 system B , Step 2: ./NativePayload_ARP2.sh -send mytest.txt vlan1 192.168.160.1/24 192.168.160.255 -p 192.168.160.2 eth0
	
  
  ![](https://github.com/DamonMohammadbagher/NativePayload_ARP2/blob/master/Pictures/step1.png)

  ![](https://github.com/DamonMohammadbagher/NativePayload_ARP2/blob/master/Pictures/step2.png)

  ![](https://github.com/DamonMohammadbagher/NativePayload_ARP2/blob/master/Pictures/step3.png)

  ![](https://github.com/DamonMohammadbagher/NativePayload_ARP2/blob/master/Pictures/final.png)
