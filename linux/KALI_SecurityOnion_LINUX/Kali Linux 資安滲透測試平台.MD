
# 資安滲透測試平台-Kali Linux 
- Kali Linux是基於Debian的Linux發行版，設計用於數位取證和滲透測試。
- Kali Linux預裝了許多滲透測試軟體，包括nmap (埠掃描器)、Wireshark (封包分析器)、John the Ripper (密碼破解器),以及Aircrack-ng (一套用於對無線區域網路進行滲透測試的軟體) 。
- Metasploit的Metasploit Framework支援Kali Linux，Metasploit一套針對遠端主機進行開發和執行Exploit原始碼的工具。
- Kali Linux的repositories(知識庫)每天會與Debian官方的repositories同步 4 次，以確保所有的套件更新至最新的版本。
- 使用者可透過硬碟、live CD或live USB執行Kali Linux。且還基於ARM架構的映像，可用於樹莓派(Raspberry Pi) 這種超小型的電腦和三星的ARMChromebook.安装Kali期間可設root密碼，如果是live、i386、amd64、VMware或ARM的image時，root的預設密碼是toor。
- Kali Linux 內建就有預載已經分門別類好的近 300 套滲透測試工具。

## Kali Linux資安測試工具集

- [Kali Tools](https://www.kali.org/tools/)
```
Kali Linux將300多種資安測試工具整理成以下14種工具集
1.	Information Gathering(資訊蒐集工具集)
2.	Vulnerability Analysis(漏洞分析工具集)
3.	Web Applications(網站應用程式分析工具集)
4.	Password Attacks(密碼破解工具集)
5.	Wireless Attacks(無線網路攻擊工具集)
6.	Exploitation Tools(特殊攻擊工具集)
7.	Sniffing/Spoofing(漏洞攻擊工具集)
8.	Maintaining Access	(存取維持與持續控制工具集)
9.	Reverse Engineering(逆向工程與破解工具集)
10.	Stress Testing(壓力測試工具集)
11.	Hardware Hacking(硬體攻擊工具集)
12.	Forensics	(資安鑑識工具集)
13.	Reporting Tools(報表工具集)
14.	 System Services(系統重大服務工具集)
```
## 1.	Information Gathering(資訊工具集)
```
資訊收集是網路攻擊最重要的環節之一，進行各類型資訊蒐集，資訊收集得越多，成功的機率越高，
包括目標系統的作業系統與其版本、是否存在有IDS/IPS資安設備都能使用下列工具集進行偵測與分析。

1-1.	DNS Analysis 【DNS名稱協定分析】工具集
1-2.	IDS/IPS Identification【IDS/IPS資安設備偵測】工具集
1-3.	Live Host Identification 【即時主機辨識】工具集
1-4.	Network Scanners【網路掃描】工具集
1-5.	OS Fingerprinting【作業系統與其版本偵測】工具集
1-6.	OSINT Analysis 【公開來源情報】分析
1-7.	Route Analysis 【路由分析】工具集
1-8.	Service Fingerprinting【應用軟體(服務)與其版本偵測】工具集
1-9.	SMB(Server Message Block) Analysis【伺服器訊息區攻擊】工具集
1-10.	SMTP Analysis【Email寄信協定SMTP分析】工具集
1-11.	SNMP Analysis 【網管協定SNMP分析】工具集
1-12.	SSL(Secure Socket Layer)Analysis 【安全套接層SSL分析】工具集
1-13.	Telephony Analysis【電話攻擊】工具集
1-14.	Traffic Analysis【流量分析】工具集
1-15.	VoIP Analysis【網路電話VoIP協定分析】工具集
1-16.	VPN Analysis【VPN協定分析】工具集
```
## 2.	Vulnerability Analysis(漏洞分析工具集)
```
2-1.	Cisco Tools 【CISCO設備分析】工具集
2-2.	Database Assessment【資料庫測試與攻擊】工具集
2-3.	Fuzzing Tools【模糊技術的高自動化弱點測試工具】工具集
2-4.	 Misc Scanners【一般用途的掃瞄】工具集
2-5.	Open Source Assessment【開放原始碼評估與測試】工具集
2-6.	OpenVAS【漏洞掃描】工具集，詳細資料，請參考附件
```
## Web Applications(網站應用程式分析工具集)
```
3-1.	CMS Identification【内容管理系统鑑定】工具集
3-2.	Database Exploitation【攻擊資料庫】工具集
3-3.	IDS/IPS Identification【IDS/IPS鑑定】工具集
3-4.	Web Application Fuzzers【網頁模糊測試】工具集
3-5.	Web Application Proxies【網頁應用程序代理】工具集
3-6.	Web Crawlers【網路爬蟲】工具集
3-7.	Web Vulnerability Scanners【網站漏洞掃描】工具集
```
## Password Attacks(密碼破解工具集)
```
4-1.	GPU Tools【圖形化處理器】工具集
4-2.	Offline Attacks【離線破解】工具集
4-3.	Online Attacks【線上破解】工具集
4-4.	Passing the Hash【Hash破解】工具集
```
## Wireless Attacks(無線網路攻擊工具集)
```
5-1.	802.11 Wireless Tools【無線區域網路802.11攻擊】工具集
5-2.	Bluetooth Tools【藍芽協定攻擊】工具集
5-3.	Other Wireless Tools【其他無線】工具集
5-4.	RFID/NFC Tools【RFID/NFC】工具集
5-5.	Software Defined Radio【軟體定義無線電】工具集
```
## Exploitation Tools(特殊攻擊工具集)
```
6-1.	BeEF XSS Framework【瀏覽器攻擊】工具集
6-2.	Cisco Attacks【思科攻擊】工具集
6-3.	Exploit Database【攻擊工具資料庫】工具集
6-4.	Exploit Development Tools【攻擊開發】工具集
6-5.	Metasploit【弱點攻擊】工具集, 詳細資料，請參考附件
6-6.	Network Exploitation【網路攻擊】工具集
6-7.	Social Engineering Toolkit【社交工程攻擊】工具集
```
## Sniffing/Spoofing(竊聽與欺騙工具集)
```
7-1.	Network Sniffers【網路竊聽】工具集
7-2.	Network Spoofing【網路欺騙攻擊】工具集
7-3.	Voice and Surveillance【語音監控】工具集
7-4.	VoIP Tools 【語音位址故障排除】工具集
7-5.	Web Sniffers【網站竊聽】工具集
```
## Maintaining Access(存取維持與持續控制工具集)
```
8-1.	OS Backdoors 【作業系統後門】工具集
8-2.	Tunneling Tools【隧道工具】工具集
8-3.	Web Backdoors【網站後門】工具集
```
## Reverse Engineering(逆向工程與破解工具集)
```
9-1.	Debuggers【除錯軟體】工具集
9-2.	Disassembly【反組譯】工具集
9-3.	Misc RE Tools【其他逆向工程與破解】工具集
```
## Stress Testing(壓力測試工具集)
```
10-1.	Network Stress Testing【網路壓力測試】工具集
10-2.	VOIP Stress Testing【網路電話協定VoIP壓力測試】工具集
10-3.	Web Stress Testing【網站壓力測試】工具集
10-4.	WLAN Stress Testing【無線網路的壓力測試】工具集
```
## Hardware Hacking(硬體攻擊工具集)
```
11-1.	Android Tools【Android硬體攻擊】工具集
11-2.	Arduino Tools【Arduino硬體攻擊】工具集
```
## Forensics(資安鑑識工具集)
```
12-1.	Anti-Virus Forensics Tools【防毒鑑識】工具集
12-2.	Digital Anti Forensics【數位反鑑識】工具集
12-3.	Digital Forensics【數位鑑識】工具集
12-4.	Forensic Analysis Tools【鑑識分析】工具集
12-5.	Forensic Carving Tools【鑑識】工具集
12-6.	Forensic Hashing Tools【HASH鑑識】工具集
12-7.	Forensic Imaging Tools【影像鑑識】工具集
12-8.	Forensic Suites【鑑識】工具集
12-9.	Network Forensics【網路鑑識】工具集
12-10.	Password Forensics Tools【密碼鑑識】工具集
12-11.	PDF Forensics Tools【PDF 檔案鑑識】工具集
12-12.	RAM Forensics Tools【RAM鑑識】工具集
```
## Reporting Tools(報表工具集)
```
13-1.	Documentation【文檔】工具集
13-2.	Evidence Management【證據管理】工具集
13-3.	Media Capture【媒體捕獲】工具集
```
## System Services(系統重大服務工具集)
```
14-1.	BeEF【瀏覽器攻擊】工具集
14-2.	Dradis【數據庫工具】
14-3.	HTTP 【Apache伺服器】
14-4.	Metasploit【弱點測試】工具集，詳細資料，請參考附件
14-5.	MySQL【Mysql資料庫伺服器】
14-6.	OpenVas【漏洞掃瞄】工具集，詳細資料，請參考附件
14-7.	SSH【Secure Shell 安全連線伺服器】
```
