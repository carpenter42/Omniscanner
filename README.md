# Omniscanner
Network forensic tool

## Requirements
Need WinPcap(or Npcap) and TShark installed 

For windows please install Tshark(Wireshark) using choco 

`choco install wireshark `

## Packages needed
GeoIP2 pyshark scapy 
* Install:  
`$ pip install geoip2  `   
`$ pip install scapy  `   
`$ pip install pyshark  `   

## Inspiration:
[1] [Psutil](https://github.com/giampaolo/psutil/)  
[2] [Python Network Scanner](https://www.tutorialspoint.com/python_penetration_testing/python_penetration_testing_network_scanner.html)  
[3] [Pcap2csv](https://github.com/vnetman/pcap2csv)  
[4] [PcapXray](https://github.com/Srinivas11789/PcapXray)  

## Instruction:
*	Check the network information.  
python Omniscanner.py [-i]  
Ex:  `python Omniscanner.py -i`  
*	Check geographic information for a specific IP address.  
python Omniscanner.py [-g] [IP address]  
Ex:  `python Omniscanner.py -g 202.108.22.5`  
*	Scan ports  
python Omniscanner.py [-s] [IP address]  
Ex:  `python Omniscanner.py -s 108.46.177.19`  
Then choose 1 of the 3 option:  
[1] Input 1 to scan common ports.   
[2] Input 2 to scan a sequence of ports.   
[3] Input 3 for a single port scan.  
*	Several Ping methods  
python Omniscanner.py [-p] [IP address] [-m] [method(arp/icmp/tcp/udp)] [(tcp)--port] [port]  
Ex:  `python Omniscanner.py -p 192.168.1.0/24 -m arp`  
Ex:  `python Omniscanner.py -p 192.168.1.1-254 -m icmp`  
Ex:  `python Omniscanner.py -p 192.168.1.1-254 -m tcp --port 80`  
Ex:  `python Omniscanner.py -p 192.168.*.1-10 -m udp`  
*	Capture packets and save to a pcap file every 300 packets captured. The number of packets is set to 300 default, but you set any number you want.  
python Omniscanner.py [-c] [--packet] [number]  
Ex:  `python Omniscanner.py -c (If you do not set – packet, it will be 300)`  
Ex:  `python Omniscanner.py -c --packet 50`  
*	Transfer the pcap file to a csv file with header.  
python Omniscanner.py [--pcap2csv] [The name of the file you want to transfer]  
Ex:  `python Omniscanner.py --pcap2csv capture-50-2020-05-11-205901.pcap`  
*	Transfer the csv generated by this program to a sqlite file.   
python Omniscanner.py [--csv2sql] [The name of the file you want to transfer]  
Ex:  `python Omniscanner.py --csv2sql capture-50-2020-05-11-205901.csv`  
