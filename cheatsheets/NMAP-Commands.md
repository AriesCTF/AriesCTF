# 🧠 Nmap CLI Cheatsheet

## 🔍 Basic Scanning

| # | Command | Description |
|--|--|--|
| 1 | `nmap <target>` | Default scan (no options) |
| 2 | `nmap -p 80 <target>` | Scan specific port |
| 3 | `nmap -p 1-65535 <target>` | Full port scan |
| 4 | `nmap -F <target>` | Fast scan (predefined top ports) |
| 5 | `nmap -v <target>` | Verbose output |

## 🕵️ Service & Version Detection

| # | Command | Description |
|--|--|--|
| 1 | `nmap -sV <target>` | Detect service versions |
| 2 | `nmap -p 80,443 -sV <target>` | Service/version scan on specific ports |

## 📦 OS & Host Discovery

| # | Command | Description |
|--|--|--|
| 1 | `nmap -O <target>` | OS detection |
| 2 | `nmap -Pn <target>` | Skip host discovery (treat hosts as up) |
| 3 | `nmap -sn <target>` | Ping scan (host discovery only) |
| 4 | `nmap -PS/PA/PU/PY <target>` | TCP SYN/ACK, UDP, SCTP discovery |
| 5 | `nmap --traceroute <target>` | Trace network path |

## 💣 Aggressive & All-In-One Scans

| # | Command | Description |
|--|--|--|
| 1 | `nmap -A <target>` | Aggressive scan (OS, version, script, traceroute) |
| 2 | `nmap -T4 -A <target>` | Aggressive scan with faster timing |
| 3 | `nmap -p- -A <target>` | Aggressive full port scan |

## 🔍 Output Formatting

| # | Command | Description |
|--|--|--|
| 1 | `nmap -oN output.txt <target>` | Normal output |
| 2 | `nmap -oX output.xml <target>` | XML format |
| 3 | `nmap -oG output.gnmap <target>` | Grepable format |
| 4 | `nmap -oA allformats <target>` | Output in all formats (adds .nmap, .xml, .gnmap) |

## 🧬 Scripting (NSE)

| # | Command | Description |
|--|--|--|
| 1 | `nmap --script default <target>` | Run default scripts |
| 2 | `nmap --script vuln <target>` | Run known vulnerability scripts |
| 3 | `nmap --script-help <script>` | Get script info |
| 4 | `nmap -p 80 --script=http-enum <target>` | Run specific HTTP script on port 80 |

## 🛡 Firewall & Evasion Techniques

| # | Command | Description |
|--|--|--|
| 1 | `nmap -f <target>` | Fragment packets |
| 2 | `nmap --data-length 200 <target>` | Add random payload data |
| 3 | `nmap -D RND:10 <target>` | Decoy scan with 10 random IPs |
| 4 | `nmap --source-port 53 <target>` | Spoof source port (e.g., DNS) |
| 5 | `nmap -S <spoofed IP> <target>` | Spoof your IP (requires configuration) |

---
