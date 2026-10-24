# Network Diagram

## Current Homelab Architecture

```text
                    Internet
                       |
                       |
              VMware NAT Gateway
                 192.168.154.2
                       |
              -------------------
              |                 |
              |                 |
          QE-DC01          QE-WIN11-01
      192.168.154.10      192.168.154.20
       Windows Server       Windows 11 Pro
        AD DS + DNS         Domain Client
              |
              |
      quantumedge.local
```
## Network Details

- VMware Network: NAT / VMnet8
- Subnet: `192.168.154.0/24`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `192.168.154.2`
- Domain Controller: `192.168.154.10`
- Windows Client: `192.168.154.20`
- Active Directory Domain: `quantumedge.local`

## DNS Configuration

`QE-WIN11-01` uses the Domain Controller as its DNS server.

- Client DNS Server: `192.168.154.10`
- DNS Server Host: `QE-DC01`
- Active Directory Domain: `quantumedge.local`

This allows the Windows client to resolve internal Active Directory records while still resolving public internet domains through the Domain Controller.
