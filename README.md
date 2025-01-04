# Network Packet Sniffer

## Overview
This project is a Python-based packet sniffer tool that captures and decodes various network protocol packets at the raw socket level. It can be used to filter and display detailed information about multiple network protocols, including **ICMP**, **TCP**, **UDP**, **HTTP**, **FTP**, **SMTP**, and more.

The tool supports the following features:
- Capture and analyze raw network traffic.
- Decode and display detailed information about network packets.
- Filter packets by protocol (e.g., ICMP, TCP, UDP, etc.).
- Save captured packet data to a backup file with timestamps.
- Provides color-coded output for easier interpretation.

## Features
1. **Packet Capture**: The sniffer listens to network traffic using raw sockets and captures various network packets.
2. **Protocol Decoding**: It supports decoding and displaying details about various protocols including:
    - **Ethernet**: MAC addresses and protocol type.
    - **IPv4**: Version, header length, TTL, and source/destination IP addresses.
    - **ICMP**: Type, code, checksum, and payload.
    - **TCP**: Source/destination ports, sequence/acknowledgment numbers, flags, and payload.
    - **UDP**: Source/destination ports, length, checksum, and payload.
    - **HTTP/FTP/SMTP**: Display HTTP/FTP/SMTP messages in decoded form.
    - **Other Protocols**: Supports multiple other protocols like **SCTP**, **DNS**, **BGP**, **DHCP**, **IGMP**, **EIGRP**, **GRE**, **ESP**, **AH**, and **SKIP**.
3. **Backup File**: Saves captured packets to a timestamped backup file for future reference.
4. **Multi-line Output Formatting**: Large payload data is split into multiple lines for better readability.
5. **Interactive Filtering**: The user can specify a protocol to filter packet captures, or use 'all' to capture all protocols.

## Requirements
To run this tool, you need:
- Python 3.x
- `colorama` library for colored output. Install it via pip:
  ```
  pip install colorama
  ```

## Usage
1. **Run the Sniffer**:
   To start the sniffer, simply execute the Python script:
   ```bash
   python packet_sniffer.py
   ```
2. **Filtering by Protocol**:
   After launching the program, you'll be prompted to specify the protocol you'd like to capture. Available protocols are:
   - **ICMP**
   - **TCP**
   - **UDP**
   - **HTTP**
   - **FTP**
   - **SMTP**
   - **HTTPS**
   - **SSH**
   - **SCTP**
   - **DNS**
   - **BGP**
   - **DHCP**
   - **IGMP**
   - **IGRP**
   - **GRE**
   - **ESP**
   - **AH**
   - **SKIP**
   - **EIGRP**
   - **OSPF**
   - **ALL** (Capture all packets)

   Example prompt:
   ```
   => HTTP
   ```
   You can enter `'all'` to capture all protocols or specify a specific protocol like `TCP`, `ICMP`, etc.

3. **Viewing Packet Information**:
   After capturing packets, the tool will display the details for the selected protocol(s). For instance, if you chose to capture **ICMP** packets, the output might look like this:
   ```
   Ethernet Frame:
   Destination: 00:14:22:01:23:45, Source: 00:14:22:67:89:AB, Protocol: IPv4

   IPv4 Packet:
   Version: 4, Header Length: 20 bytes, TTL: 64
   Protocol: ICMP, Source: 192.168.0.1, Target: 192.168.0.2

   ICMP Packet:
   Type: 8, Code: 0, Checksum: 0x1d52
   Payload:
   <Payload data here>
   ```

4. **Backup Files**:
   The program generates backup files for saved packets with a timestamped filename. The backup file is saved in the script's directory as `sniffer_backup_YYYYMMDD_HHMMSS.txt`.

5. **Stopping the Sniffer**:
   You can stop the sniffer by pressing `Ctrl+C` in the terminal.

## Example Output
- **Ethernet Frame**: Displays the source and destination MAC addresses and the Ethernet protocol.
- **IPv4 Packet**: Shows the IP version, header length, TTL, protocol, and source/target IP addresses.
- **ICMP Packet**: Provides ICMP type, code, checksum, and payload information.
- **TCP/UDP**: Displays the port numbers, sequence/acknowledgment numbers, flags (for TCP), and payload.
- **Message Protocols (HTTP/FTP/SMTP)**: Displays the HTTP/FTP/SMTP message contents.

## Class Definitions
- **DualOutput**: A custom class that redirects output to both the console and a file, enabling simultaneous logging.
- **Various protocol functions**: Functions to parse and display data for each supported protocol, such as `icmp_segment`, `tcp_segment`, `dns_segment`, etc.

## Contributing
If you wish to contribute to this project, feel free to fork it and submit pull requests for new protocol support or improvements.

## License
This project is open-source and available under the [MIT License](LICENSE).
