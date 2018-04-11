# Manual Network configuration

Network configuration is done using the `iproute2` tools package and preferred
over older `ifconfig` and `route`.

## Collecting Information

- To list the available interfaces use :
  `ip link`
  Take a note of the interfaces and currently connected interface.
- To see the current interface and connections : 
  `ip addr`
  This list the current interface address.
- To see the current routing table
  `ip route show`
   This prints the current routing table
- To see current DNS settings
  `cat /etc/resolv.conf`

   _Save all these just in case anything goes wrong_
