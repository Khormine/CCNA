# CCNA 13+14 - Subnetting:

- IPv4 Address Assignment:
  - IANA assignes IPv4 addressesz to companies based on their size.
  - Company X needs IP addressing for 5000 hosts. A class B network will be assigned but 60000 addresses are wasted.

- CIDR : Classless Inter-Domain Routing:
  - Introduced by the IETF in 1993 to replace classful addressing system
  - Allowed larger network to be split into smaller
  - These smaller networks are called `subnets` 
  - $2^n - 2$ usable addresses with $n$ the number of host bits
  - Ex: $/27 \Rightarrow 2^5-2 = 30$ usable addresses

- Subnetting scenario:
<!-- TODO IMG -->