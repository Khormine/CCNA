# CCNA 4 - Command Line Interface

- User EXEC Mode:
  - Very limited
  - Users can look at some things, but can't make any changes to the configuration
  - called `user mode`
```
ROUTER> ...
```

- Priviliged EXEC Mode:
  - Provides complete access to view the device's configuration, restart the device, ...
  - Can't change the configuration, but can change the time on the device, save the configuration file, ...
```
ROUTER> enable
ROUTER# ...
ROUTER# ? #available commands
```

- Configuration Mode:
```
ROUTER> enable
ROUTER# configure terminal
ROUTER(config)# ...
```

- Enable password:
```
ROUTER(config)# enable password TOTO
```

- Running Configuration: current, active configuration file on the device
- Startup Configuration: configuration file that will be loaded upon restart of the device
```
ROUTER# show running-config
ROUTER# show startup-config
```
- Saving the configuration:
```
ROUTER# write                                               #OR
ROUTER# write memory                                        #OR
ROUTER# copy running-configuration startup-configuration    #OR
```

- Hostname:
```
ROUTER(config)# hostname R1
R1(config)# ...
```

- Service password encryption:
  - current password encrypted
  - future password encrypted
  - enable secret will not be affected
```
ROUTER# conf t
ROUTER(config)# service password-encryption
```

- Enable secret:
```
ROUTER(config)# enable secret PWD
```

- Remove command:
```
ROUTER(config)# no cmd
```