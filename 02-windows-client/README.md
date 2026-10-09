# Windows 11 Domain Client

## Objective

Deploy a Windows 11 Pro virtual machine, configure network connectivity, and join it to the `quantumedge.local` Active Directory domain.

## System Information

- Hostname: `QE-WIN11-01`
- Operating System: Windows 11 Pro
- IPv4 Address: `192.168.154.20`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `192.168.154.2`
- DNS Server: `192.168.154.10`

## Domain Configuration

The workstation was joined to:

`quantumedge.local`

The client uses the Domain Controller as its DNS server so it can locate Active Directory services.

## Validation

The following tests were performed:

- Confirmed connectivity to the VMware NAT gateway
- Confirmed connectivity to the Domain Controller
- Confirmed internet connectivity
- Confirmed internal DNS resolution
- Successfully joined the workstation to the Active Directory domain

## Lessons Learned

- Domain clients should use the Domain Controller for DNS.
- A client must be able to resolve the AD domain before joining it.
- Local Windows accounts and domain accounts are separate authentication contexts.
- VMware NAT provides internet access while allowing the client and server VMs to communicate on the same virtual network.
