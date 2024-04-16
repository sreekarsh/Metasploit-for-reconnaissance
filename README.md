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

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/5ec6332f-3813-4918-a462-ce407c05520e)



Invoke msfconsole:

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/806627c4-fc02-423b-ae08-da16593ed433)




Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/f4161b94-471a-46d5-ac4e-c80ffb02ea90)




## Port Scanning:

Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/579d8af8-7eec-4d63-a15f-c33e278d57cd)


step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/c607c272-e94e-4cec-bd1c-f05cecce879d)



Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l 

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/839a4f05-58c1-4f90-93df-b00d8608f503)



Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,

## OUTPUT

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/a9fc3c51-1233-4e9a-a9f9-e99c13767e37)



Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

## MYSQL ENUMERATION

Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/2620f6ad-2d26-41ad-ba75-13131f74f2ac)



Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/a6afe538-bdd1-4e2a-8adc-52eac1a0e920)


use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/f08f1533-3fb5-4986-acf5-6916599e44ea)




Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/53b7cdf1-ca42-488b-be3d-2f1e4c024ab6)



After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/f18cb6ce-62af-4f36-8221-5728d395738e)



set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/35827a98-84d2-476f-8f6c-26a9aef63c42)


![image](https://github.com/sreekarsh/Metasploit-for-reconnaissance/assets/139841918/a56b5577-9fab-490f-aade-a36f4b966a7d)




## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
