# CCNA 7+8 - IPv4 Addressing:

- IPv4 Address Classes:

| Class         | First octet |First octet numeric range  | Prefix Length  | Number of Networks  | Addresses per network |
|---------------|-------------|---------------------------|----------------|---------------------|-----------------------|
| A             | 0xxxxxxx    | 0-127                     | /8             | 2^7                 | 2^24                  |
| B             | 10xxxxxx    | 128-191                   | /16            | 2^14                | 2^16                  |
| C             | 110xxxxx    | 92-223                    | /24            | 2^11                | 2^8                   |
| D (multicast) | 1110xxxx    | 224-239                   |                |                     |                       |
| E (reserved)  | 1111xxxx    |240-255                    |                |                     |                       |

- Netmask:

| Class  | Netmask        |
|--------|----------------|
| A /8   | 255.0.0.0      |
| B /16  | 255.255.0.0    |
| C /24  | 255.255.255.0  |

- Network Address:
  - Host portion of the address is all `0`s
  - The network addres can't be assigned to a host
- Broadcast Address:
  - Host portion of the address is all `1`s
  - The broadcast address can't be assigned to a host

- Configuration:
```
R1# show ip interface brief # administratively down: interface disabled with the 'shutdown' command
                            # default status of Cisco router interfacers
                            # Cisco switch interfaces are not administratively down by default
R1(config)# interface int
R1(config-if)# ip address 10.255.255.254 255.0.0.0
R1(config-if)# no shutdown  # enable interface
R1(config-if)# do sh ip int br
```