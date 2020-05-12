# Nest
```
# Nmap 7.70 scan initiated Mon May 11 02:09:57 2020 as: nmap -sC -sV -o scan.nmap 10.1
0.10.178                                                                              
Nmap scan report for 10.10.10.178
Host is up (0.015s latency).
Not shown: 999 filtered ports
PORT    STATE SERVICE       VERSION
445/tcp open  microsoft-ds?
```
### Enumerate
- nmap --script smb-vuln* -p 445 10.10.10.178
- nmap --script smb-* -p 445 10.10.10.178
- enum4linux -L 10.10.10.178
- smbmap -H 10.10.10.178

```
smbclient -L /10.10.10.178
WARNING: The "syslog" option is deprecated
Enter WORKGROUP\root's password: 

        Sharename       Type      Comment
        ---------       ----      -------
        ADMIN$          Disk      Remote Admin
        C$              Disk      Default share
        Data            Disk      
        IPC$            IPC       Remote IPC
        Secure$         Disk      
        Users           Disk      
```
