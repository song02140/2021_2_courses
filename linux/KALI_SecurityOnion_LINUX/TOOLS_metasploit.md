#


## Metasploit
- Metasploit項目最初由HD Moore 在2003年夏季創立
- 目標是成為滲透攻擊研究與代碼開發的一個開放資源
- 起初v1.0發布之後並沒有太多回響
- 2004年8月在拉斯維加斯舉辦的BlackHat全球黑客大會上發布Metasploit v2.2站上演講台，題目”Hacking Like in the Movies”演講與Demo過程中，全場掌聲數次
- 2006年SecToole網站最受歡迎100個安全工具

## 系統架構與模組

- Exploits
  - Metasploit currently has over 2074 exploits
  - organized under the following platforms: AIX, Android, BSD, BSDi, Cisco, Firefox, FreeBSD, HP-UX, Irix, Java, JavaScript, Linux, mainframe, multi (applicable to multiple platforms), NetBSD, NetWare, nodejs, OpenBSD, macOS, PHP, Python, R, Ruby, Solaris, Unix, and Windows

- Payloads
  - Metasploit currently has over 592 payloads. Some of them are:
  - Command shell enables users to run collection scripts or run arbitrary commands against the host.
    - Meterpreter (the Metasploit Interpreter) enables users to control the screen of a device using VNC and to browse, upload and download files.
    - Dynamic payloads enable users to evade anti-virus defense by generating unique payloads.
    - Static payloads enable static IP address/port forwarding for communication between the host and the client system.
- Auxiliary Modules輔助模組
  - The Metasploit Framework includes hundreds of auxiliary modules that can perform scanning, fuzzing, sniffing, and much more. 
  - There are three types of auxiliary modules namely scanners, admin and server modules.
  - Metasploit為滲透測試的資訊蒐集環節提供了大量的輔助模組支援
  - 包括針對各種網路服務的掃描與檢查、構建偽造服務收集登錄密碼、密碼猜測破解、漏洞訊息探勘、查尋漏洞息訊洩露、Fuzz測試發掘漏洞、實施網路協議欺騙等模組，
  - Metasploit輔助模組中還包含一些無須加載攻擊特徵，同時往往不是取得目標系統遠端控制權的滲透攻擊，例如拒絕服務攻擊等。


## 參考書籍 

- [METASPLOIT UNLEASHED](https://www.offensive-security.com/metasploit-unleashed/)
- 
