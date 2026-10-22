
>[!tldr] Simple network level firewall. Operates as a front end for `ip-tables`

**Using UFW**
- `ufw enable`: Enable ufw
- `ufw disable`: Disable ufw
- `ufw reset`: 
- `ufw status verbose` -> Show firewall status and rules
```shell
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), deny (routed)
New profiles: skip
```
- Understanding status output:
	- `Status`: states if the firewall is on or note
	- `Logging`: Logs packets to `/var/log/ufw.log`
		- `low`: Only log packets that are blocked by the firewall rules
	- `Default`: 
		- `deny (incoming)`: Blocks + All packets into the machine (people might lock themselves out from a VPS)
		- `allow (outgoing)`: Allow + Machine can request data

>[!danger] Docker won't Listen
>Docker bypasses UFW (Uncomplicated Firewall) rules by default allowing published container ports to be accessible from outside, regardless of UFW settings. This occurs because Docker manipulates iptables directly, which takes precedence over UFW rules.

**Allowing Common Applications**
- `ufw allow ssh`: A shortcut to allow certain applications ("ssh")
- `ufw app list`: Premade rules for applications
	- `vim /etc/ufw/applications.d/<profile_name>`: Add ufw rules to create a custom profile
- `ufw app info 'Nginx Full'`: Info on specified application ("Nginx Full")