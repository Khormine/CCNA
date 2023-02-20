# CCNA 3 - OSI Model

- OSI Model:
  - 'Open Systems Interconnection' model
  - A conceptual model that categorizes and standardizes the different functions in a network
  - Created by the 'International Organization for Standardization' (ISO)
  - Functions are divided into 7 layers
  - These layers work together to make the network works

| 7  | Application   |
|----|---------------|
| 6  | Presentation  |
| 5  | Session       |
| 4  | Transport     |
| 3  | Network       |
| 2  | Data Link     |
| 1  | Physical      |

- Application layer:
  - closest to the end user
  - interacts with software applications
  - Ex: HTTP, HTTPS, ...
  - Functions of layer 7 include:
    - identifying communications partners
    - synchronizing communications
- Presentation layer:
  - Data in the application layer is in 'application format'
  - It needs to be translated to a different format to be sent over the network
  - Its job is to translate between application and network formats
  - Ex: encryption/decryption
- Session layer:
  - Control diaogues (sessions) between communications hosts
  - Establishes, manages and terminates connections between the local application and the remote application
- Transport layer:
  - Segments and reassembles data for communications between end hosts
  - Break large pieces of data into smaller segments which can be more easily sent over the network and are less likely to cause transimission problemes if errors occur
  - Provide host-to-host communications
- Network layer:
  - Provides connectivity between end hosts on different networks
  - Provides logical addressing (IP address)
  - Provides path selection between source and destination
  - Routers operate at Layer 3
- Data Link layer:
  - Provides node-to-node connectivity and data transfer
  - Defines how data is formatted for transmission over a physical medium
  - Detects and (possibly) corrects Physical layer error
  - Uses Layer 2 addressing, separate from Layer 3 addressing
  - Switches operate at Layer 2

- Encapsulation:
<!-- TODO IMG -->

-Data Flow:
<!-- TODO IMG -->