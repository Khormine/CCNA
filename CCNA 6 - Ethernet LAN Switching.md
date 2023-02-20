# CCNA 6 - Ethernet LAN Switching:

- Ethernet Frame:
  - The preambule and SFD is usually not considered part of the Ethernet header
  - The size of the Ethernet header and trailer is 16 bytes (6 + 6 + 2 + 4)
  - The minimum size for an Ethernet frame (header + payload + trailer) is 64 bytes
  - The minimum payload size is 46 bytes
  - If the payload is less than 46 bytes, padding bytes are added

- ARP: Address Resolution Protocol
  - Used to discover layer 2 address (MAC address) of a known layer 2 address (IP address)
  - consists of two messages:
    - ARP request: is broadcast
    - ARP reply: is unicast

- ARP request:
```
SRC IP  : 192.168.1.1
DST IP  : 192.168.1.3
SRC MAC : AAAA:AA00:0001
DST MAC : FFFF:FFFF:FFFF
```

- ARP reply:
```
SRC IP  : 192.168.1.3
DST IP  : 192.168.1.1
SRC MAC : AAAA:AA00:0003
DST MAC : AAAA:AA00:0001
```

- ARP table: on Windows/Linux
```
$ arp -a
```

- Ping: 
  - Test reachability
  - Measures round-trip time
  - Uses two messages:
    - ICMP echo request
    - ICMP echo reply

- MAC Address Table:
```
sw1# show mac address-table
```

- Clearing the MAC Address Table:
```
sw1# clear mac address-table dynamic
sw1# clear mac address-table dynamic address <adrMac>
sw1# clear mac address-table dynamic interface <int>
```