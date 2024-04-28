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
## OUTPUT:
Find out the ip address of the attackers system
![exp 5 1](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/48c327b9-c239-4e8a-8a0d-8ffdd48c1d2e)

Invoke msfconsole:
![exp 5 2](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/c0fa6b72-aa6c-491b-b4a4-d167d0dda6c8)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![exp 5 3](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/c8509d44-93b3-459e-8170-c583309320c8)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
![exp 5 4](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/cf26b65f-b0c0-4ebb-a40f-7023e9389a12)

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.
scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
![exp 5 5](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/1c0c52b2-21af-4a13-8ed8-20bd18352bc9)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
![exp 5 6](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/0311539e-adf5-41f7-a521-ffd6d6ad0833)

![exp 5 7](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/f06ffa29-035d-4003-b996-3e8f7804a419)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
![exp 5 8](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/56cd3041-6816-4fd4-b0b7-0f84148cae35)

The info command provides information regarding a module or platform
![exp 5 9](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/65f53018-0b2b-4ad6-9091-25dd8f40a509)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![exp 5 10](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/ede02c64-bf75-45d6-a2d5-027552bffc00)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![exp 5 11](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/55d8a848-9f08-40f2-a88c-4a776c5322ad)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![exp 5 12](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/d5dbf9ea-4684-4778-8928-5a712f6d9e85)

Use the set rhosts command to set the parameter and run the module, as follows:
![exp 5 13](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/f43f9842-9f9f-4792-9662-f93ad950ce99)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![exp 5 14](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/575b85a0-9631-40a5-a162-13a9dac81149)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![exp 5 15](https://github.com/keerthanaa10/Metasploit-for-reconnaissance/assets/132996371/26c4a92b-d01c-4ebb-ab29-e801e0026e76)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
