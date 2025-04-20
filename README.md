# 🛰️ traceroute — Trace the Path of Network Packets

**traceroute** is a CLI utility that shows the route your packets take from your computer to a target host. It helps identify network delays, hops, and possible bottlenecks along the path.

---

## ✅ Features

- Shows each hop between your system and the target host
- Displays IP addresses and response times per hop
- Useful for network diagnostics and troubleshooting
- Supports options like maximum hops, wait times, and more

---

## 🔧 Installation

### Debian/Ubuntu
```bash
sudo apt install traceroute
```

### Arch Linux
```bash
sudo pacman -S inetutils
```

### Fedora
```bash
sudo dnf install traceroute
```

---

## 🚀 Basic Usage

### Trace route to a domain or IP
```bash
traceroute example.com
```

### Trace with numeric IPs only (skip DNS lookup)
```bash
traceroute -n example.com
```

### Set maximum number of hops
```bash
traceroute -m 15 example.com
```

### Use TCP instead of UDP (more firewall-friendly)
```bash
traceroute -T example.com
```

### Set wait time per probe (default is 5 seconds)
```bash
traceroute -w 2 example.com
```

---

## 📊 Output Breakdown

Each line of the output represents a hop (router) between your system and the destination.

Example:
```txt
 1  192.168.1.1 (192.168.1.1)  1.123 ms  0.985 ms  1.001 ms
 2  10.0.0.1 (10.0.0.1)        2.304 ms  2.210 ms  2.151 ms
 3  * * *                     (timeout or blocked hop)
```

- First column = hop number
- IP address and hostname
- Three time measurements (in ms)

---

## 🧩 Tips

- Use `-I` for ICMP echo requests (similar to `ping`)
  ```bash
  traceroute -I google.com
  ```
- Combine with tools like `ping`, `dig`, or `mtr` for full network diagnosis.
- If `traceroute` is not available, try `tracepath` or `mtr`.

---

## 📚 More Info

- Run `man traceroute` for detailed options
- Official man page: [https://man7.org/linux/man-pages/man8/traceroute.8.html](https://man7.org/linux/man-pages/man8/traceroute.8.html)
