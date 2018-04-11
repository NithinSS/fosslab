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

## Manually configuring 

- To change the address of the interface
  `ip addr add ip_address dev interface_name`
  _NOTE: This changes after system reboot_
- Now enable network interface
  `ip link set interface_name up`
- To set the routing table
    _Example:_
   `ip route add 10.10.20.0/24 via 192.168.50.100 dev eth0`
- To set the default gateway
    _Example:_
    `ip route add default via 192.168.50.100`
 
Where the first routing command let your system access any device in your local network.
And the gateway allows the system to connect to devices beyond the local network.
That is now internet is available. But no nameserver has been specified and hence DNS won't work.

## Manually changing DNS 

To change DNS change the content of `/etc/resolv.conf`
Add the following
`nameserver 8.8.8.8`

Now the DNS has been setup and names will be resolved.


  
