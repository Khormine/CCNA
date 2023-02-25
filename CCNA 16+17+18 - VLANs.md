# CCNA 16+17+18 - VLANs:

- LAN Broadcast Domain:
<!-- TODO IMG -->

- Performance: Lots of unnecessary broadcast traffic can reduce network performance.
- Security: 
  - Even within the same office, you want to limit who has access to what.
  - You can apply security policy on a router/firewall.
  - Inside a LAN, PCs can reach each other directly, without passing through the router.
  
- Segmenting at layer 3 (subnets) and layer 2 (VLANs):
<!-- TODO IMG -->

  - A switch will not forward traffic VLANs including broadcast/unknown unicast traffic
  - The switch does not perform inter-VLAN routing. It must send the traffic through the router
  - VLANs:
    - are configured on swithces on a per-interface basis
    - logically separate end hosts at layer 2

- VLAN configuration:
```
SW1 # show vlan brief
SW1 (config)# interface range g1/0-3
SW1 (config-if-range)# switchport mode access
SW1 (config-if-range)# switchport access VLAN 10
SW1 (config-if-range)# exit
SW1 (config)# do show vlan brief
SW1 (config)# vlan 10
SW1 (config-vlan)# name ENGINEERING
```

- Trunk Ports:
  - In a small network with few VLANs, it is possible to use a separate interface for each VLAN when connecting switches to switches and switches to routers.
  - However, when the number of VLANs increases, it will result in wasted interfaces, and often routers won't have enough interfaces for each VLAN
  - You can use trunk ports to carry traffic from multiple VLANs over a single interface.
  - Switches will tag all frames that the send over a trunk link. This allows the receiving switch to know which VLAN the frame belongs to:
    - Trunks ports : tagged ports
    - Access ports : untagged ports

- VLAN tagging:
  - Two main trunking protocols : ISL and IEEE 802.1Q
  - ISL is unsupported by modern routers

- 802.1Q Tag & Ethernet:
  - 802.1Q tag is inserted in the Ethernet Frame
  - The tag is 4 bytes long
  - It consists of two main fields:
    - Tag Protocol Identifier (TPID)
    - Tag Control Information (TCI)
<!-- TODO IMG -->

- 802.1q tag format:
<!-- TODO IMG -->

- TPID: always set to `0x8100` to indicate that the frame is 802.1Q-tagged

- Priority Code Point: Used for Class of Service (CoS), which prioritizes important traffic in congested networks.

- Drop Eligible Indication: Used to indicate frame that can be dropped if the network is congested.
  
- VLAN ID:
  - Identifies the VLAN the frame belongs to
  - Range of `0-4095`
  - VLANs `0` and `4095` are reserved

- VLAN Ranges:
  - Normal VLANs: `1-1005`
  - Extended VLANs: `1006-4094`

- Trunk configuration:
```
SW1 (config)# interface g0/0
SW1 (config-if)# switchport mode trunk      #risque marche pas car supporte ISL
SW1 (config-if)# switchport trunk encapsulation dot1q
SW1 (config-if)# switchport mode trunk

SW1# show interface trunk

SW1 (config)# int g0/0
SW1 (config-if)# switchport trunk allowed vlan 10,30
SW1 (config-if)# switchport trunk allowed vlan add 20
SW1 (config-if)# switchport trunk native vlan 1001
```

- Router On A Stick (ROAS): used to route between VLANs using a single interface on the router and switch.
```
R1 (config)# if g0/0
R1 (config-if)# no shutdown
R1 (config-if)# interface g0/0.10
R1 (config-subif)# encapsulation dot1q 10
R1 (config-subif)# ip address 192.168.1.62 255.255.255.192
```

- Native VLAN on Router:
```
R1 (config)# if g0/0.10
R1 (config-subif)# encapsulation dot1q 10
```

- Layer 3 (Multilayer) switches:
  - A multilayer switch is capable of both switching AND routing.
  - It is 'layer 3 aware'.
  - You can assign IP addresses to its interfaces, like a router.
  - You can create virtual interfaces for each VLAN, and assign IP addresses to those interfaces.
  - You can configure routes on it, like a router.
  - It can be used for inter-VLAN routing.