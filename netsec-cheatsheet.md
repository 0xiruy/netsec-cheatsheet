
# 🛡️ Network Security Cheat Sheet by 0xiruy

A practical collection of commands, tools, and tips for Network+ and real-world security work.

---

## 📡 Networking Essentials

### IP Info & Interface
```bash
ip a             # Show IP addresses (Linux)
ipconfig         # Show IP (Windows)
ip route         # Show routing table
traceroute 8.8.8.8   # Trace route (Linux)
tracert 8.8.8.8      # Trace route (Windows)
```

### DNS & Host
```bash
nslookup google.com
dig google.com +short
host google.com
```

### Ping & Connectivity
```bash
ping -c4 1.1.1.1
ping 8.8.8.8
telnet <host> <port>   # Check open port
```

---

## 🔒 Security Tools

### Nmap – Scanning
```bash
nmap -sS -T4 192.168.1.0/24          # Stealth scan
nmap -sV -O -Pn target.com           # Service/version detection
nmap --script=vuln target.com        # Vuln scan
```

### Netcat – Network Swiss Army Knife
```bash
nc -v -n -z 192.168.1.10 1-1000      # Scan ports
nc -lvp 4444                        # Listen on port
```

### Tcpdump – Packet Sniffer
```bash
tcpdump -i eth0 port 80
tcpdump -nn -vv -i any 'port 53'
```

### Wireshark – GUI Sniffer
- Use filters like `http`, `dns`, `ip.addr == x.x.x.x`
- Export packet bytes, follow TCP streams

---

## 🔍 Log Analysis

### Linux Logs
```bash
cat /var/log/auth.log | grep "Failed"
journalctl -xe              # Systemd logs
```

### Windows Logs
- Open Event Viewer → Security Logs → Filter by Event ID (e.g., 4625 for failed logon)

---

## 🧰 Hardening Basics

### Linux
```bash
ufw enable && ufw status
sudo apt update && apt upgrade
chmod 600 ~/.ssh/authorized_keys
```

### Windows
- Enable Windows Defender / Antivirus
- Disable SMBv1, Unused Services
- Set secure GPO settings

---

## 💡 Tips
- Don’t expose SSH on port 22 — use 2222 or similar
- Disable unused interfaces/services
- Regularly rotate logs and check for anomalies
- Monitor login attempts, failed logins, and open ports

---

> _"Security is not a product, but a process." – Bruce Schneier_
