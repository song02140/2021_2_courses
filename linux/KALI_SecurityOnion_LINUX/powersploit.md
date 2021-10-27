#

# /usr/share/windows-resources
```
binaries  
dbd  
hyperion  
mimikatz  
powershell-empire  
powersploit  
sbd  
wce
```

##

- [使用 sbd 及 dbd 創建系統安全後門](https://github.com/Yehnn/kali/blob/master/kali%E5%90%8E%E9%97%A8%E6%8A%80%E6%9C%AF%E5%AE%9E%E6%88%98/03%E4%BD%BF%E7%94%A8%20sbd%20%E5%8F%8A%20dbd%20%E5%88%9B%E5%BB%BA%E7%B3%BB%E7%BB%9F%E5%AE%89%E5%85%A8%E5%90%8E%E9%97%A8.md)

## wce(Windows Credentials Editor)

Windows Credentials Editor (WCE) v1.3beta allows you to:

NTLM authentication:

- List logon sessions and add, change, list and delete associated credentials (e.g.: LM/NT hashes)
- Perform pass-the-hash on Windows natively
- Obtain NT/LM hashes from memory (from interactive logons, services, remote desktop connections, etc.) which can be used to authenticate to other systems. WCE can perform this task without injecting code, just by reading and decrypting information stored in Windows internal memory structures. 
- It also has the capability to automatically switch to code injection when the aforementioned method cannot be performed.

#
```
┌──(kali㉿kali)-[/usr/bin]
└─$ powersploit         
> powersploit ~ PowerShell Post-Exploitation Framework
/usr/share/windows-resources/powersploit
  |---AntivirusBypass
  |---CodeExecution
  |---Exfiltration
  |---Mayhem
  |---Persistence
  |---PowerSploit.psd1
  |---PowerSploit.psm1
  |---Privesc
  |---README.md
  |---Recon
  |---ScriptModification
  |---Tests
```
