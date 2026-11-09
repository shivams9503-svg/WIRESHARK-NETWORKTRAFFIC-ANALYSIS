Wireshark Network Traffic Analysis -
A simple project where I captured live Wi-Fi traffic using Wireshark and studied DNS, TCP (port 443) and TLS traffic using display filters.

Theory-
Wireshark is a free tool that captures network packets and shows what is happening on a network. It is used for troubleshooting and security analysis.
Term
Meaning
DNS
Converts a website name (like bing.com) into an IP address
A / AAAA record
A = IPv4 address, AAAA = IPv6 address
CNAME
A name that points to another name
TCP
Reliable connection between two devices
Port 443
The port used by HTTPS (secure websites)
Keep-Alive
Small packets that keep a connection open
Dup ACK
Same acknowledgement sent again, may mean packet loss
RST
Resets (suddenly closes) a TCP connection
TLS
Encrypts data so others cannot read it
Client Hello
First TLS packet sent to start a secure connection
SNI
Website name shown inside Client Hello
QUIC
Modern protocol over UDP, used by Google services
ICMP Port Unreachable
Message saying the port is not open
Filters Used
Filter
What it shows dns
DNS queries and responses
tcp.port == 443
HTTPS traffic
tls.handshake.type == 1
TLS Client Hello packets

What I Found-
DNS: The device asks DNS for the IP of sites like bing.com and microsoft.com before connecting. Both IPv4 and IPv6 were requested. One ICMP "Port unreachable" message was also seen.
TCP 443: Many Keep-Alive packets keep connections open. A few Dup ACK packets and one RST packet were seen.
TLS: Client Hello packets show the website name (SNI) even though the data is encrypted. TLS 1.2, TLS 1.3 and QUIC were all seen.

What I Learned-
How to capture and filter packets in Wireshark
How DNS, TCP and TLS work together when opening a website
How to spot normal and unusual network behaviour

Tools Used- Wireshark
Windows 10

Author-
Shivams9503-svg