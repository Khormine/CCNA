# CCNA 9 - Switch Interfaces:

- CLI:
```
sw1# sh ip int br
sw1# sh int status
sw1(config)# int f0/1
sw1(config-if)# speed 100                   # configure speed
sw1(config-if)# duplex full                 # configure duplex
sw1(config-if)# description '## To R1 ##'   # configure description
sw1(config)# interface range f0/5 - 10
sw1(config-if-range)# description '## Not in Use ##'
sw1(config-if-range)# shutdown
```

- Duplex:
  - Half duplex: the device can't send and receive data at the same time. If it is receiving a frame, it must wait beofre sending a frame
  - Full duplex: the device can send and receive data at the same time

- Hubs: half-duplex
<!-- TODO IMG -->

- CSMA/CD: Carrier Sense Multiplex Access with Collision Detection
  - Before sending frames, devices listen to the collision domain until they detect that other devices are not sending
  - If a collision does occur, the device sends a jamming signal to infor the other devices that a collision happened
  - Each device will wait a rando period of time before sending frames again
  - The process repeats

- Speed/Duplex Autonegociation:
  - Interfaces that can run at different speeds have default settings of speed and duplex to auto.
  - Interfaces 'advertise' their capabilities to the neighboring device, and they negotiate the best speed and duplex settings they have both capable of.
  - If autonegociation is disabled on the device connected to the switch:
    - SPEED : the switch will try to sence the speed that the other device is operating at. If it fails, it will use the slowest supported speed.
    - DUPLEX: If the speed is `10` or `100` Mbps, the switch will use half-duplex. If the speed is `1000` Mbps or greater, it will use full-duplex.

- Interface errors:
  - Runts: frames smaller than the minimum frame size (64 bytes)
  - Giants: frames that are larger than the maximum frame size (1518bytes)
  - CRC: frames that failed the CRC check
  - Frame: frames that have an incorrect format
  - Input errors: total of various counters
  - Output errors: frames the switch tried to send but failed due to an error