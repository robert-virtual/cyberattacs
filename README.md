## Man-in-the-middle-attack

- network: 192.168.0.0/24
- default gateway: 192.168.0.1

```bash
nmap 192.168.0.0/24 -sn
```
> sn: ping scan

- target: 192.168.0.18

### enable packets forwarding

```bash
sysctl -w net.ipv4.ip_forward=1
```

