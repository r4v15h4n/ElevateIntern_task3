# ElevateIntern_task3
Task 3 - Perform a Basic Vulnerability Scan on Your PC.
installed Nessus Essential and scanned the 192.168.0.1
found some vulnerabilities and repoorts attached as screenshot

1. vulnerabilities Description :- 
The remote host has IP forwarding enabled. An attacker can exploit this to route packets through the host and potentially bypass some firewalls / routers / NAC filtering.
Unless the remote host is a router, it is recommended that you disable IP forwarding.


Solution
On Linux, you can disable IP forwarding by doing :
echo 0 > /proc/sys/net/ipv4/ip_forward
On Windows, set the key 'IPEnableRouter' to 0 under
HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Tcpip\Parameters
On Mac OS X, you can disable IP forwarding by executing the command :
sysctl -w net.inet.ip.forwarding=0

2. vulnerabilities Description :- 
This script contacts the remote DHCP server (if any) and attempts to retrieve information about the network layout.
Some DHCP servers provide sensitive information such as the NIS domain name, or network layout information such as the list of the network web servers, and so on.
It does not demonstrate any vulnerability, but a local attacker may use DHCP to become intimately familiar with the associated network.

Solution
Apply filtering to keep this information off the network and remove any options that are not in use.
