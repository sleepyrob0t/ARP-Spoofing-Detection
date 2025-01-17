# ARP-Spoofing-Detection

This script detects ARP spoofing attacks by comparing the actual MAC address of a device with the one provided in ARP replies. If a discrepancy is found, it warns the user.

## What is ARP Spoofing?

Address Resolution Protocol (ARP) is used to map IP addresses to MAC addresses within a local network. ARP spoofing (or poisoning) is an attack where a malicious actor sends fake ARP messages to associate their MAC address with the IP address of another device, such as the network gateway. This allows them to intercept, modify, or disrupt network traffic, potentially leading to data theft or denial of service.

## Requirements

- Python 3
- Scapy library

### Install Scapy

```sh
pip install scapy
```

## Usage

Run the script with the network interface you want to monitor:

```sh
python arp_spoof_detector.py eth0
```

If no interface is provided, it will default to the system's main interface.

## How It Works

1. It listens for ARP replies on the network.
2. When an ARP reply is received, it fetches the real MAC address of the sender.
3. It compares the real MAC with the one provided in the ARP reply.
4. If they don’t match, it raises an alert.

## Example Output

```sh
[!] You are under attack, REAL-MAC: 00:1A:2B:3C:4D:5E, FAKE-MAC: 11:22:33:44:55:66
```

## Notes

- Run this script with administrative privileges (e.g., `sudo` on Linux/Mac).
- It may not work properly if your firewall blocks ARP requests.

## Disclaimer

This script is for educational purposes only. Use it responsibly!

