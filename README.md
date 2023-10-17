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
# PROGRAM:
Find out the ip address of the attackers system

# OUTPUT:
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/f6540a47-63b8-4680-b2d7-20cd3c7c0875)

# Invoke msfconsole:
# OUTPUT:
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/37ce66dc-8cb7-492f-a57a-8e4dcd6c7067)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

# OUTPUT:
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/276b2681-66d8-455e-b6d4-d423c23b2e37)
Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

# OUTPUT:
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/b125f758-ac79-4a55-bcca-ffc1b824b46c)
# Step4:
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

# OUTPUT:
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/81339067-13fd-46d0-9caf-6f9aa1379b32)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

# OUTPUT:
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/65993ac2-f15e-4b4e-a21a-05eebd820e1f)
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/ff130ff1-cfea-40ac-afc7-1349e5b54c10)
Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/83637b83-8c83-4590-b636-bc9bb05ff42b)
The info command provides information regarding a module or platform
# OUTPUT:
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/040bbed7-58f9-49e8-b544-a496b5207426)
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/35b7a073-b61c-441e-83c6-df854540064f)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/3e2db11e-8961-4938-99ea-092377338661)
use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/168d7dcf-9680-468b-b123-025c476ca8c1)
Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/ae1b444e-2fb8-480e-9ae5-556169e47772)
After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/35b6798a-59a8-4e53-8d84-f5e885ac2e86)
set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![image](https://github.com/sachinezhilmaran/Metasploit-for-reconnaissance/assets/128135351/72869b27-646c-4d5e-8353-5bfbbdc3309c)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
