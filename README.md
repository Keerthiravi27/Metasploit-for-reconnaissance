# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system
## OUTPUT:

<img width="695" height="558" alt="image" src="https://github.com/user-attachments/assets/31ed73e7-a912-4ee7-8c40-0d8905889e96" />

Invoke msfconsole:
## OUTPUT:
<img width="1116" height="586" alt="VirtualBox_kali linux_15_05_2026_09_27_15" src="https://github.com/user-attachments/assets/d95d8764-0039-465e-95a3-f5d5fd8adfc3" />

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.


<img width="894" height="733" alt="image" src="https://github.com/user-attachments/assets/d9eb3101-bde4-4654-a407-8ba4f9d1db09" />



Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000).
msf >  nmap -sT 192.168.1810/24 -p1-1000  (Replace with appropriate IP Address)
## OUTPUT:

<img width="926" height="163" alt="image" src="https://github.com/user-attachments/assets/d680dbee-d0ce-44a5-a6fc-9c3a3cc95ab3" />

step4:
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows.
msf > db_nmap 192.168.181.0/24
## OUTPUT:

<img width="1031" height="506" alt="image" src="https://github.com/user-attachments/assets/be928e0e-58a1-4a1e-8da7-bcad2c473c4e" />





Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules.
cd /usr/share /metasploit-framework/modules/auxiliary
kali > ls -l
## OUTPUT:

<img width="685" height="465" alt="image" src="https://github.com/user-attachments/assets/f97fa648-4a75-44d7-9871-cd1accd5afc0" />


Search is a powerful command in Metasploit that you can use to find what you want to locate. 
msf >search name:Microsoft type:exploit
## OUTPUT:


<img width="958" height="783" alt="image" src="https://github.com/user-attachments/assets/4aea26cd-97c7-4c5e-87b4-35605c47a139" />

The info command provides information regarding a module or platform,


## MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port.
db_nmap -sV -sC -p 3306 <metasploitable_ip_address>


## Output

searchtype:auxilary mysql

searchtype:auxiliary mysql – Used to search MySQL related auxiliary modules in Metasploit Framework

<img width="1034" height="509" alt="image" src="https://github.com/user-attachments/assets/9559027d-e881-427d-8e87-51f88fb85469" />

searchtype:auxilary mysql

searchtype:auxiliary mysql – Used to search MySQL related auxiliary modules in Metasploit Framework

<img width="931" height="603" alt="image" src="https://github.com/user-attachments/assets/5b9c5688-bb63-4a10-9f13-6e821c97ca55" />

use 11

Selects and loads the module with index number 11 from the search results

<img width="954" height="409" alt="image" src="https://github.com/user-attachments/assets/a03387a8-380a-4f85-9f2d-898e000a079c" />

set RHOSTS

Sets the target IP address or range of systems to scan or attack.

<img width="688" height="157" alt="image" src="https://github.com/user-attachments/assets/386a2597-5e41-460d-a452-24e3174bcceb" />

use auxiliary/scanner/mysql/mysql_login

Loads the MySQL login scanner module used to test MySQL username and password combinations.

<img width="928" height="551" alt="image" src="https://github.com/user-attachments/assets/a798b35f-052d-43a3-8c14-9d20918c0a52" />

set PASS_FILE /usr/share/wordlists/rockyou.txt

set RHOSTS

set BLANK_PASSWORDS true

set verbose no

run

set PASS_FILE /usr/share/wordlists/rockyou.txt – Specifies the password wordlist file that will be used for password attempts.

set BLANK_PASSWORDS true – Enables testing of accounts with empty passwords.

set VERBOSE no – Disables detailed output and shows only important results.

run – Executes the selected module with the configured settings.

<img width="1036" height="504" alt="image" src="https://github.com/user-attachments/assets/35d6058c-de76-4f42-b1a0-3a15e967b12c" />


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
