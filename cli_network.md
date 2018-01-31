# Commands To Get Started With Networking

## If some commands fail to execute try executing them as root user.

`sudo su`

>After executing `sudo su` the user may continue with the commands below just to be sure that all the commands will work properly. But that is totally upto the user.

## Check the ip adresses of  all the interfaces detected in the network.

`ip a` or `ip addr`

## Display information for all interfaces.

`ip l` or `ip link` or `ifconfig`

## Check the ip address of the default gateway(if at all specified) ,mainly for troubleshooting purposes.

`ip r` or `ip route`

## Assign ip to a specific interface.

`ip addr add <ip> dev <interface name>`

## Remove an ip address of a specific interface.

`ip addr del <ip> dev <interface name>`

## Enable a network interafce.

`ip addr del <ip> dev <interface name>`

## Disable a network interface.

`ip link set <interface name> down`

## List devices,their type,state and connection status.

`nmcli dev`

## Using nmcli as network manager to connect wifi.

`nmcli dev wifi connect <ssid> password <pswd>`

## Set up coonnection for a specified interface.

`nmcli con <interface name> up`

## Disconnect a specified interface.

`nmcli con <interface name> down`

## Reload connection after modifications.

`nmcli con reload`

## Text user interface as network manager.It gives optons for adding, editing(Add a hostname,ip adress,dns server,gateway etc) or deleting a network

`nmtui`

## Edit configuration file of a specified network.

`vi /etc/sysconfig/network-scripts/ifcfg-<connection/interface name>`

## Check connectivity of specified network.

`ping <ip>`

## To check the number of hops taken to reach destination also determine packets travelling path:

### If there is an error command not found then first install traceroute then execute the command.

`traceroute <ip>`

## The command mainly use to troubleshoot DNS related query. (DIG- domain information groper or nslookup):

`dig <webiste name>`
		or
`nslookup <website name>`

## To show and manipulate ip routing table:

`route`

### To add route:
`route add -net <ip address> gw <gateway address>`
### To delete route:
`route del -net <ip address> gw <gateway address>`
### To add a default gateway:
`route add default gw <gateway address>`

## To find name to IP or IP to name in IPv4 or IPv6 and also query DNS records:

`host <domain name>`

## To view setting speed and duplex of Network Interface Card (NIC).

`ethtool <Interface name>`
#### Interface name can be found by the command ifconfig. The name listed on the leftmost side.

## To find the hostname of the system.

`hostname`

## Capture packets to/from eth0 and record to file

`tcpdump -i eth0 -v -s 65535 -w capture.cap`
#### Extra arguments explained [here](https://www.rationallyparanoid.com/articles/tcpdump.html)

## Print information from capture file

`capinfos capture.cap`
#### Extra arguments explained [here](https://www.wireshark.org/docs/wsug_html_chunked/AppToolscapinfos.html)

## Proxy Settings in commandline

### For a perticular session

`export http_proxy="http://<proxy_sever_ip>:<port>/"`

`export https_proxy="http://<proxy_sever_ip>:<port>/"`

`export ftp_proxy="http://<proxy_sever_ip>:<port>/"`
#### In shortcut - if all Proxies are same

`export {http,https,ftp}_proxy="http://<proxy_sever_ip>:<port>/"`

### To see the Proxy Settings

`env | grep -i proxy`

### Excluding sites from Proxy Settings

`export no_proxy="hostname,.hostname2,hostname3"`

### To set these variables parmanently

`sudo vi /etc/bash.bashrc`
##### Now append these lines in bash.bashrc file

`export {http,https,ftp}_proxy="http://<proxy_sever_ip>:<port>/"`

### To disable Proxy Settings

`unset {http,https,ftp}_proxy`
