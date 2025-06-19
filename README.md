# python-port-scanner
A fast, multi-threaded TCP connect port scanner written in Python. This tool helps identify open ports on a target host by attempting full TCP connections to a specified range of ports.

Features:

TCP Connect Scan: Performs a standard TCP three-way handshake to determine if a port is open.
Multi-threaded: Utilizes Python's concurrent.futures.ThreadPoolExecutor to scan multiple ports concurrently, significantly speeding up the scanning process.
Service Banner Grabbing: Attempts to retrieve service banners from open ports to identify running applications.
Real-time Progress: Displays live progress updates in the console during scanning.
Colorized Output: Uses ANSI escape codes to highlight open ports and banners for better readability.

Ethical Considerations:

IMPORTANT:
Port scanning, especially on networks or hosts you do not own or have explicit permission to scan, can be considered illegal and unethical. This tool is developed purely for educational purposes, network administration on your own networks, and ethical security research with explicit authorization. Always obtain proper consent before scanning any system. Misuse of this tool is strictly your responsibility.

Installation:

1.Clone the repository:git clone https://github.com/jagadaprarthana/python-port-scanner.git
cd python-port-scanner
2.Install dependencies (if any):This project primarily uses built-in Python libraries (socket, concurrent.futures, sys). No external pip installations are typically required for the core functionality.

Usage:

Run the port_scanner.py script from your terminal:
python port_scanner.py
The script will then prompt you to enter the target IP address or hostname, the starting port, and the ending port for the scan.

Example:
Enter your target IP or hostname: scanme.nmap.org
Enter the start port: 1
Enter end port: 100
Starting scan on host: 45.33.32.180
Progress: 100/100 ports scanned
Port Scan Results:
Port     Service         Status
-------------------------------------------------------------------------------------
22       ssh             Open
        SSH-2.0-OpenSSH_7.7 (protocol 2.0)
80       http            Open
        Apache/2.4.6 (CentOS) OpenSSL/1.0.2k-fips mod_fcgid/2.3.9 PHP/5.4.16
9929     nping-e            Open
9988     unknown         Open

How It Works:

This scanner uses Python's socket library to perform TCP connect scans. For each port in the specified range, it attempts to establish a full TCP connection. If the connection is successful, the port is identified as open. The concurrent.futures.ThreadPoolExecutor allows multiple connection attempts to run in parallel, significantly reducing the total scan time. Additionally, it attempts to fetch service banners from open ports to provide more information about the running services.

Contributing:

Feel free to open issues or submit pull requests for any improvements or bug fixes.

License:

This project is licensed under the MIT License.
