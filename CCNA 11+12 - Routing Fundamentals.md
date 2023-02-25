# CCNA 11 + 12 - Routing Fundamentals:

- Routing:
  - Process that routers use to determine the path that IP packets should take over a network to reach their destination.
  - Routers store routes to all of their known destination in a routing table.
  - When router receive a packets, they look in the routing table to find the best route to forward packets.

- Dynamic Routing:
  - Share routing information with each other automatically and build their routing table
  - OSPF, BGP, ...

- Static Routing: manually configures routers on the router

- Route: tells the router to send a packet to a destination X, you should send the packet to next-hop Y

- Pre-configuration:
```
R1 (config)# interface int
R1 (config-if)# ip address 192.168.0.1 255.255.255.0
R1 (config-if)# no shutdown
```

- Routing table:
```
R1# show ip route
```

- Default gateway:
  - To send packets to destinations outside the local network, hosts must send the packets to their default gateway
  - The default gateway configuration is also called default route : `0.0.0.0/0`

- Static route configuration:
```
R1 (config)# ip route <IP> <netmask> [next-hop] [exit-interface]
R1 (config)# do show ip route
```

- Default route:
  - Route to `0.0.0.0/0`
  - If the router doesn't have any more specific routes that match a packet's destination address IP, the router will forward the packet using the default route.
  - Often useed to direct traffic to the internet.
```
R1 (config)# ip route 0.0.0.0 0.0.0.0 [next-hop] [exit-interface]
```