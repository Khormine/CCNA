# CCNA 5 - Ethernet LAN Switching:

- Ethernet Frame:

- Preambule:
  - Allows devices to synchronize their reveiver clocks
  - `10101010` x 7
- Start Frame Delimiter:
  - Marks the end of the preambule and the beginning of the rest of the frame
  - `10101011` 
- Destination/Source:
  - destination and source MAC address (physical address)
- Type/Lenght:
  - a vaue of 1500 or less indicates the length of the encapsulated packets
  - a value of 1536 or greater indicates the type of the encapsulated packet (IPv4 = `0x0800`, IPv6 = `0x86DD`)
- Frame Check Sequence:
  - Detects corrupted data by running a CRC alogirthm on the received data

- MAC Address:
  - 6 bytes physical address assigned to the device when it is made
  - globally unique
  - first 3 bytes are the OUI (Organizationnnaly Unique Identifier), which is assigned to the compagny making the device
  - last 3 bytes are unique to the device itself

<!-- TODO IMG -->