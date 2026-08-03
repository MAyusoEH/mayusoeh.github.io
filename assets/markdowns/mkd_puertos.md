[[mkd_ejpt]]

-------------

### 1. Puertos Bien Conocidos (0-1023)

| Puerto  | Protocolo/s      | Servicio             | Descripción                                              |
| ------- | ---------------- | -------------------- | -------------------------------------------------------- |
| 7       | TCP - UDP        | Echo                 | Echo Service                                             |
| 19      | TCP - UDP        | CHARGEN              | Character Generator Protocol                             |
| **20**  | TCP - SCTP       | **FTP data**         | File Transfer Protocol Data Transfer                     |
| **21**  | TCP - UDP - SCTP | **FTP**              | File Transfer Protocol Command Control                   |
| **22**  | TCP - UDP - SCTP | **SSH / SCP / SFTP** | Secure Shell / Secure Logins / File Transfers            |
| **23**  | TCP              | **TELNET**           | TELetype NETwork (control remoto)                        |
| 25      | TCP              | SMTP                 | Simple Mail Transfer Protocol                            |
| 42      | TCP - UDP        | WINS Rep.            | Microsoft Windows Internet Name Service                  |
| 43      | TCP - UDP        | WHOIS                | Whois Service                                            |
| 49      | TCP - UDP        | TACACS               | Terminal Access Controller Access-Control System         |
| **53**  | TCP - UDP        | **DNS**              | Domain Name System                                       |
| 67      | UDP              | DHCP / BOOTP         | Dynamic Host Configuration Protocol                      |
| 68      | UDP              | DHCP / BOOTP         | Dynamic Host Configuration Protocol                      |
| 69      | UDP              | TFTP                 | Trivial File Transfer Protocol                           |
| 70      | TCP              | Gopher               | Comms Protocol (documents in Internet Protocol networks) |
| 79      | TCP              | Finger               | Finger protocol                                          |
| **80**  | TCP - UDP - SCTP | **HTTP**             | Hypertext Transfer Protocol (web sites)                  |
| 88      | TCP - UDP        | Kerberos             | Network Authentication System                            |
| 102     | TCP              | ME ISO-TSAP          | Microsoft Exchange ISO Transport Service Access Point    |
| **110** | TCP              | **POP3**             | Post Office Protocol (version 3)                         |
| 113     | TCP              | Ident                | Identification Protocol                                  |
| 119     | TCP              | NNTP                 | Network News Transfer Protocol                           |
| 123     | UDP              | NTP                  | Network Time Protocol                                    |
| 135     | TCP - UDP        | MS RPC EPMAP         | Microsoft Remote Procedure Call Endpoint Mapper          |
| 137     | TCP - UDP        | NetBIOS-ns           | NetBIOS Name Service                                     |
| 138     | TCP - UDP        | NetBIOS-dgm          | NetBIOS Datagram Service                                 |
| 139     | TCP - UDP        | NetBIOS-ssn          | NetBIOS Session Service                                  |
| 143     | TCP - UDP        | IMAP                 | Internet Message Access Protocol                         |
| **156** | -                | **SQL**              | Structured Query Language                                |
| 161     | UDP              | SNMP-agents          | Simple Network Management Protocol (agents)              |
| 162     | UDP              | SNMP-trap            | Simple Network Management (traps)                        |
| 177     | UDP              | XDMCP                | X Display Manager Control Protocol                       |
| 179     | TCP              | BGP                  | Border Gateway Protocol                                  |
| **194** | UDP              | **IRC**              | Internet Relay Chat                                      |
| 201     | TCP - UDP        | AppleTalk            | AppleTalk Routing Maintenance                            |
| 264     | TCP - UDP        | BGMP                 | Border Gateway Multicast Protocol                        |
| 318     | TCP - UDP        | TSP                  | Time Stamp Protocol                                      |
| 381     | TCP - UDP        | HP Openview          | HP performance data collector                            |
| 383     | TCP - UDP        | HP Openview          | HP data alarm manager                                    |
| 389     | TCP - UDP        | LDAP                 | Lightweight Directory Access Protocol                    |
| 411     | TCP - UDP        | multiuse             | Direct Connect Hub                                       |
| 412     | TCP - UDP        | multiuse             | Direct Connect Client-to-Client                          |
| 427     | TCP - UDP        | SLP                  | Service Location Protocol                                |
| **443** | TCP - UDP - SCTP | **HTTPS**            | Hypertext Transfer Protocol Secured                      |
| 445     | TCP - UDP        | MS DS SMB            | Microsoft Directory Services / SMB                       |
| 464     | TCP - UDP        | Kerberos             | Kerberos Password settings                               |
| 465     | TCP              | SMTPS                | Authenticated SMTP over TLS/SSL                          |
| 497     | TCP - UDP        | Dantz Retro          | Software for Operating System backup                     |
| 500     | UDP              | IPSec                | Internet Protocol Security                               |
| 512     | TCP              | rexec                | Remote Process Execution                                 |
| 513     | TCP              | rlogin               | Unix program rlogin                                      |
| 514     | UDP              | syslog               | Syslog Protocol                                          |
| 515     | TCP              | LPD / LPR            | Line Printer Daemon Protocol                             |
| 520     | UDP              | RIP                  | Routing Information Protocol                             |
| 521     | UDP              | RIPng                | Routing Information Protocol (IPv6)                      |
| 540     | TCP              | UUCP                 | Unix-to-Unix Copy Protocol                               |
| **546** | UDP              | **DHCPv6**           | DHCPv6 Clients                                           |
| **547** | UDP              | **DHCPv6**           | DHCPv6 Agents                                            |
| 548     | TCP              | AFP                  | Apple Filing Protocol                                    |
| 554     | TCP - UDP        | RTSP                 | Real Time Streaming Protocol                             |
| 560     | TCP - UDP        | rmonitor             | Remote Monitor                                           |
| 563     | TCP              | NNTPS                | NNTP with encryption                                     |
| 587     | TCP              | SMTP Submission      | Email message submission via SMTP                        |
| 591     | TCP - UDP        | FileMaker            | FileMaker Web Companion                                  |
| 593     | UDP              | MS DCOM              | Distributed Component Object Model                       |
| 596     | TCP - UDP        | SMSD                 | SysMan Station Daemon                                    |
| 631     | TCP              | IPP                  | Internet Printing Protocol                               |
| 636     | TCP              | LDAPS                | LDAP over TLS/SSL                                        |
| 639     | TCP - UDP        | MSDP                 | Multicast Source Discovery Protocol                      |
| 646     | TCP - UDP        | LDP                  | Label Distribution Protocol (MPLS)                       |
| 691     | TCP              | MS Exchange          | Microsoft Exchange Routing                               |
| 860     | TCP - UDP        | iSCSI                | Internet Small Computer System Interface                 |
| 873     | TCP              | rsync                | rsync file synchronization protocol                      |
| 902     | TCP              | VMware Server        | VMware ESXi                                              |
| **989** | TCP              | **FTPS**             | FTP data over TLS/SSL                                    |
| **990** | TCP              | **FTPS**             | FTP control over TLS/SSL                                 |
| **993** | TCP              | **IMAPS**            | IMAP over TLS/SSL                                        |
| **995** | TCP - UDP        | POP3S****            | POP3 over TLS/SSL                                        |

---

### 2. Puertos Registrados (1024-49151)

| Puerto         | Protocolo/s | Servicio        | Descripción                                  |
| -------------- | ----------- | --------------- | -------------------------------------------- |
| 1025           | TCP - UDP   | Microsoft RPC   | Microsoft Remote Procedure Call              |
| 1026-1029      | UDP         | MSN popup       | Windows Messenger popup spam                 |
| **1080**       | TCP - UDP   | **SOCKS proxy** | Socket Secure                                |
| 1080           | TCP         | MyDoom          | Computer Virus                               |
| 1194           | TCP - UDP   | OpenVPN         | OpenVPN                                      |
| 1214           | TCP         | KAZAA           | Peer-to-Peer sharing protocol                |
| 1311           | TCP         | Dell OpenManage | Dell EMC OpenManage Server Administrator     |
| 1337           | TCP         | WASTE           | Peer-to-Peer encrypted file-sharing          |
| 1589           | TCP - UDP   | Cisco VQP       | Cisco VLAN Query Protocol                    |
| 1720           | TCP         | H.323           | H.323 Call Control Signaling (VoIP)          |
| 1723           | TCP - UDP   | Microsoft PPTP  | Point-to-Point Tunneling Protocol            |
| 1725           | UDP         | Steam           | Valve Steam Client                           |
| 1741           | TCP         | CiscoWorks SNMS | CiscoWorks Small Network Management Solution |
| 1755           | TCP - UDP   | MMS             | Microsoft Media Server                       |
| 1863           | TCP - UDP   | multiuse        | MSN Messenger / Xbox Live                    |
| 1900           | UDP         | UPnP            | Universal Plug and Play                      |
| 1985           | UDP         | Cisco HSRP      | Hot Standby Router Protocol                  |
| 2000           | TCP         | Cisco SCCP      | Skinny Client Control Protocol               |
| 2002           | TCP         | Cisco ACS       | Access Control Server                        |
| 2049           | UDP         | NFS             | Network File Sharing                         |
| 2082           | TCP - UDP   | cPanel          | cPanel default                               |
| 2100           | TCP         | amiganetfs      | Amiga Network Filesystem                     |
| 2222           | TCP         | DirectAdmin     | Graphical web hosting control panel          |
| 2302           | UDP         | Gaming          | Gaming port (HALO)                           |
| **2483**       | TCP - UDP   | **Oracle**      | Oracle database (insecure)                   |
| **2484**       | TCP - UDP   | **Oracle SSL**  | Oracle database (SSL)                        |
| 2967           | TCP - UDP   | Symantec AV     | Symantec System Center agent                 |
| 3050           | TCP - UDP   | Interbase DB    | Borland Interbase database                   |
| 3074           | TCP - UDP   | XBOX Live       | Xbox Live and Games for Windows              |
| **3128**       | TCP         | **HTTP Proxy**  | Common web proxy server                      |
| 3222           | TCP - UDP   | GLBP            | Gateway Load Balancing Protocol              |
| 3260           | TCP - UDP   | iSCSI target    | Microsoft iSCSI Target Server                |
| **3306**       | TCP         | **MySQL**       | MySQL database system                        |
| **3389**       | TCP         | **RDP**         | Windows Remote Desktop Protocol              |
| 3690           | TCP - UDP   | SVN             | Apache Subversion                            |
| 4333           | TCP         | mSQL            | Mini SQL server                              |
| 4444           | TCP - UDP   | Blaster         | Computer worm                                |
| 4500           | UDP         | IPSec NAT       | IPSec Network Address Translation Traversal  |
| 4664           | TCP         | Google Desktop  | Google Desktop HTTP server                   |
| 4899           | TCP         | Radmin          | Remote computer control software             |
| **5000**       | TCP         | **UPnP**        | Universal Plug and Play                      |
| 5060           | TCP - UDP   | SIP             | Session Initiation Protocol                  |
| 5061           | TCP         | SIP-TLS         | Session Initiation Protocol over TLS         |
| 5353           | UDP         | MDNS            | Multicast DNS                                |
| **5432**       | TCP         | PostgreSQL****  | PostgreSQL database system                   |
| 5900-5999      | TCP - UDP   | VNC             | VNC Remote Frame Buffer                      |
| **6379**       | TCP         | **Redis**       | Redis (NoSQL)                                |
| 6588****       | TCP         | **HTTP Proxy**  | Common web proxy server                      |
| **6665-6669**  | TCP         | IRC**           | Internet Relay Chat                          |
| 6679, 6697**** | TCP         | IRC SSL****     | Internet Relay Chat over SSL                 |
| 7000           | TCP         | Cassandra       | Apache Cassandra inter-node                  |
| 7001           | TCP         | Cassandra SSL   | Apache Cassandra SSL inter-node              |
| 7199           | TCP         | Cassandra JMX   | Java Management Extension (Cassandra)        |
| 8000           | TCP         | Internet Radio  | Commonly used with HTTP                      |
| **8080**       | TCP         | **HTTP Proxy**  | Common web proxy / alternative HTTP          |
| 8086           | TCP         | Kaspersky AV    | Kaspersky AV Control Center                  |
| 8087           | TCP         | Kaspersky AV    | Kaspersky AV Control Center                  |
| 11371          | UDP         | OpenPGP         | OpenPGP HTTP Keyserver                       |
| 12345          | TCP - UDP   | NetBus          | Remote administration (Trojan)               |
| **27017**      | TCP         | **MongoDB**     | MongoDB (NoSQL)                              |
| 33434+         | UDP         | **traceroute**  | Utility for displaying paths                 |
