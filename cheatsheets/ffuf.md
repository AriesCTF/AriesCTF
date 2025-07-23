---

# 🧭 FFUF Cheatsheet – Quick Recon for AriesCTF

### 🔹 Basic Usage

- Show Commands
    
    ```
    ffuf -u http://target/FUZZ -w wordlist.txt
    ```
    
    - `u`: Target URL with placeholder
    - `w`: Wordlist file path

### 🔹 Directory & File Discovery

- Dir & File Scan Options
    
    **Simple Dir Bruteforce**
    
    ```
    ffuf -u http://target/FUZZ -w /usr/share/wordlists/dirb/common.txt
    ```
    
    **Recursive Scan**
    
    ```
    ffuf -u http://target/FUZZ -w wordlist.txt -recursion
    ```
    
    **File Extension Scan**
    
    ```
    ffuf -u http://target/FUZZ -w wordlist.txt -e .php,.html,.txt
    ```
    
    **Custom Headers**
    
    ```
    ffuf -u http://target/FUZZ -w wordlist.txt -H "Host: vhost.target"
    ```
    

### 🔹 Sub-Domain Discovery

- Sub-Domain
    
    ```bash
    ffuf -w wordlist.txt:FUZZ -u [https://FUZZ.hackthebox.eu/](https://fuzz.hackthebox.eu/)
    ```
    

### 🔹 VHost Discovery

- VHost
    
    ```bash
    ffuf -w wordlist.txt:FUZZ -u http://academy.htb:PORT/ -H 'Host: [FUZZ.academy.htb](http://fuzz.academy.htb/)' -fs xxx
    ```
    

### 🔹 Parameter Fuzzing

- GET & POST Fuzzing
    
    **GET Parameter**
    
    ```
    ffuf -u "http://target/page.php?FUZZ=value" -w params.txt
    ```
    
    **POST Parameter**
    
    ```
    ffuf -u http://target -X POST -d "username=FUZZ&password=test" -w usernames.txt
    ```
    

### 🔹 Authentication

- Cookie & Auth Injection
    
    **Cookie Injection**
    
    ```
    ffuf -u http://target/FUZZ -w wordlist.txt -H "Cookie: session=xyz"
    ```
    
    **Basic Auth**
    
    ```
    ffuf -u http://target/FUZZ -w wordlist.txt -H "Authorization: Basic "
    ```
    

### 🔹 Filtering Results

- Filter Settings
    
    **By Status Code**
    
    ```
    fc 404 # Hide 404s
    ```
    
    **By Response Size**
    
    ```
    fs 1234 # Hide size 1234
    ```
    
    **By Regex**
    
    ```
    mr "password|flag"
    ```
    

### 🔹 Advanced Usage

- Multi-Fuzzing & Rate Controls
    
    **Multiple Fuzzing Points**
    
    ```
    ffuf -u http://target/FUZZ/page/FUZ2Z -w wordlist1.txt:FUZZ -w wordlist2.txt:FUZ2Z
    ```
    
    **Rate Limiting**
    
    - rate 50
    -delay 0.2
    
    **Timeout**
    
    - timeout 5

### 📦 Recommended Wordlists

| Purpose | Example Path |
| --- | --- |
| Directories | `/usr/share/wordlists/dirb/common.txt` |
| Files | `SecLists/Discovery/Web-Content/raft-small-files.txt` |
| Parameters | `SecLists/Discovery/Web-Content/burp-params.txt` |
| Extensions | `.php`, `.txt`, `.bak`, `.old` |

### 🧠 Tactical Tips

- Use `ffuf -mode batch` for cleaner logs
- Always filter results with `fc` or `fs` to reduce noise
- Combine `ffuf` scans with `Burp Suite`, `nmap`, and manual inspection
