# Strict Split Tunnel
Strictly split-tunnel over OpenVPN (ran with root/`UID 0`) and dropping traffic not owned by root. By dropping non-root traffic, if OpenVPN crashed then all non-root traffic within the network namespace would be dropped by iptables. The intent is to expand and refactor as needed (optimistically on request). Among the many assumptions likely made when writing `bin/sspilttun`, the [setup](https://www.ivpn.net/setup/gnu-linux-terminal.html) relies on updating *.ovpn* to point to your credential file.    

**tl;dr** if TOR is ran using a non-root UID within the network namespace, then the user is safer---an attacker would have to bypass TOR and remotely execute code within the OpenVPN process to expose your host IP. Stay safe.
