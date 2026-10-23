# Proxmox VE — Installation and Initial Verification

## 1. Installation

- Platform: Proxmox Virtual Environment
- Installation status: Completed
- Hostname: `proxserv.home`
- Management IP address: `192.168.1.10/24`
- Management bridge: `vmbr0`
- Physical network interface: `nic0`
- Web management interface: HTTPS, port `8006`

## 2. Network Configuration

- Network subnet: `192.168.1.0/24`
- Default gateway: `192.168.1.1`
- Management interface: `vmbr0`
- Management IP: `192.168.1.10`
- Wi-Fi interface: `wlo1` (DOWN)
- DNS server: `192.168.1.1`

## 3. Initial Verification

| Check | Result |
|---|---|
| IP address assigned to `vmbr0` | Confirmed |
| Management bridge state | UP |
| Hostname resolution command | Returned `proxserv.home` |
| Route selection to `8.8.8.8` | Via `192.168.1.1`, using `vmbr0` |
| Proxmox web interface | Accessible |
| Router connectivity | Passed - Router `192.168.1.1` Reachable |
| Internet connectivity | Passed - `8.8.8.8` Reachable |
| DNS resolution | Passed - `wp.pl` resolved successfully |

## 4. Findings

The Proxmox host has an active management bridge configured with the address `192.168.1.10/24`.

The route lookup for `8.8.8.8` selects the gateway `192.168.1.1` and the source address `192.168.1.10`.

The web management interface is accessible and administrator login is successful.

## 5. Next Steps

- Review the network configuration
- Review storage and node health
- Plan virtual machines and backups
- Plan the first virtual machine
- Configure a backup strategy
