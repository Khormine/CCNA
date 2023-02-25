# CCNA 19 - DTV & VTP:

## DTP: Dynamic Trunking Protocol

- DTP:
  - DTP is a Cisco proprietary protocol that allows Cisco switches to dynamically determine their interface status (**access** or **trunk**) without manual configuration.
  - DTP is enabled by default on all Cisco switch interfaces.
  - For security purposes, manual configuration is recommended. DTP should be disabled on all switchports.

```
SW2(config-if)# switchport mode ?
SW2(config-if)# switchport mode dynamic ?
```

- DTP modes:
  - A switchport in **dynamic desirable** mode will actively try to form a trunk with other Cisco switches. It will form a trunk if connected to another switchport in the following modes
    - `switchport mode trunk`
    - `switchport mode dynamic desirable`
    - `switchport mode dynamic auto`
<!-- TODO IMG -->
  
  - A switchport in **dynamic auto** mode will **NOT** actively try to form a trunk with other Cisco switches, however it will form a trunk if the switch connected to it is actively trying to form a trunk. It will form a trunk with a switchport in the following modes:
    - `switchport mode trunk`
    - `switchport mode dynamic desirable`

<!-- TODO IMG -->

- DTP Mode Chart:
<!-- TODO IMG -->

- Disabling DTP:
  - On older switches, `switchport mode dynamic desirable` is the default administrative mode.
  - On newer switches, `switchport mode dynamic auto` is the default administrative mode.
  - You can disable DTP negotiation on an interface: `switchport nonegotiate`
  - Configuring an access port with `switchport mode access` also disables DTP negotiation on an interface.

- Trunk encapsulation negotiation  via DTP:
  - Switches that support both 802.1Q and ISL trunk encapsulation can use DTP to negotiate the encapsulation they will use.
  - This negotiation is enabled by default, as the default trunk encapsulation mode is: `switchport trunk encapsulation negotiate`
  - ISl is favored over 802.1Q, so if both switches support ISL, it will be selected.
  - DTP frames are sent in VLAN1 when using ISL, or in the native VLAN when using 802.1Q


## VTP: VLAN trunking Protocol

- VTP:
  - VTP allows you to configure VLANs on a central VTP server switch, and other switches (VTP clients) will synchronize their VLAN database to the server.
  - It is designed for large networks with many VLANs, so that you don't have to configure each VLAN on every switch.
  - It is rarely used, and it is recommended that it is not used.
  - There are 3 VTP versions: 1, 2 and 3.
  - There are 3 VTP modes: server, clienta and transparent.
  - Cisco switches operate in VTP server mode by default.
