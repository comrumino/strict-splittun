# Strict Split Tunnel
Strictly split-tunnel over OpenVPN (ran with root/`UID 0`) and dropping traffic not owned by root. By dropping non-root traffic, if OpenVPN crashed then all non-root traffic within the network namespace would be dropped by iptables.
