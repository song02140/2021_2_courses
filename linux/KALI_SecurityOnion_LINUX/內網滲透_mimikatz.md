## [內網滲透_mimikatz使用方法](https://www.cnblogs.com/sfsec/p/15184337.html)
```
內網滲透_mimikatz使用方法
Mimikatz簡介
Mimikatz 是一款功能強大的羽量級調試神器，通過它你可以提升進程許可權注入進程讀取進程記憶體，
當然他最大的亮點就是他可以直接從 lsass.exe進程中獲取當前登錄系統用戶名的密碼， 
lsass是微軟Windows系統的安全機制它主要用於本地安全和登陸策略，
通常我們在登陸系統時輸入密碼之後，密碼便會儲存在 lsass記憶體中，
經過其 wdigest 和 tspkg 兩個模組調用後，對其使用可逆的演算法進行加密並存儲在記憶體之中

mimikatz 正是通過對lsass逆算獲取到純文字密碼
也就是說只要你不重啟電腦，就可以通過他獲取到登陸密碼，只限當前登陸系統！
```
```
┌──(kali㉿kali)-[/usr/share/windows-resources/mimikatz]
└─$  mimikatz -h
> mimikatz ~ Uses admin rights on Windows to display passwords in plaintext
/usr/share/windows-resources/mimikatz
  |---kiwi_passwords.yar
  |---mimicom.idl
  |---Win32
  |----mimidrv.sys
  |----mimikatz.exe
  |----mimilib.dll
  |----mimilove.exe
  |----mimispool.dll
  |---x64
  |----mimidrv.sys
  |----mimikatz.exe
  |----mimilib.dll
  |----mimispool.dll
                                                                                                  
```
```
cls：清屏
standard：標準模組，基本命令
crypto：加密相關模組
sekurlsa：與證書相關的模組
kerberos：kerberos模組
privilege：提權相關模組
process：進程相關模組
serivce：服務相關模組
lsadump：LsaDump模組
ts：終端伺服器模組
event：事件模組
misc：雜項模組
token：權杖操作模組
vault：Windows 、證書模組
minesweeper：Mine Sweeper模組
dpapi：DPAPI模組（通過API或RAW訪問）[資料保護應用程式設計發展介面]
busylight：BusyLight Module
sysenv：系統環境值模組
sid：安全性識別碼模組
iis：IIS XML配置模組
rpc：mimikatz的RPC控制
sr98：用於SR98設備和T5577目標的RF模組
rdm：RDM（830AL）器件的射頻模組
acr：ACR模組
version：查看版本
exit：退出
```
