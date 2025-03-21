# PortScanner
Simple python code to scan for the status of specific ports on a given IP address.

```
import socket 
def port_scanner(target, ports): 
  print(f"Scanning {target}...") 
  for port in ports:
    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
      socket.setdefaulttimeout(1) 
      result = s.connect_ex((target, port)) 
      if result == 0: 
        print(f"Port {port} is open") 
      else: print(f"Port {port} is closed") 
target_ip = "127.0.0.1" # Replace with your target IP 
ports_to_scan = [22, 80, 443, 8080] 
port_scanner(target_ip, ports_to_scan)
```
