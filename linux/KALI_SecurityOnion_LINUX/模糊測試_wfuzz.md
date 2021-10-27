#

- [webFuzz: Grey-Box Fuzzing for Web Applications](European Symposium on Research in Computer Security ESORICS 2021: Computer Security – ESORICS 2021 pp 152-172)


# wfuzz

- wfuzz 是一款Python開發的Web安全模糊測試工具。
- [官方網址https://github.com/xmendez/wfuzz ](https://github.com/xmendez/wfuzz)
- 功能特點
  - 模組化 框架 可編寫外掛
  - 介面 可處理BurpSuite所抓的請求和響應報文
  - 可執行 `請求(http request)`引數類的模糊測試 
  - Web目錄掃描(web directory travel|list)。
- [](https://sectools.tw/wfuzz/)
- [WFUZZ使用教程](https://www.twblogs.net/a/5c8e8a3cbd9eee35cd6b1462)
## 簡單測試
```
wfuzz -w 字典 位址
```
```
┌──(kali㉿kali)-[~]
└─$ wfuzz -w test_dict.txt http://www.slime.com.tw/
 /usr/lib/python3/dist-packages/wfuzz/__init__.py:34: UserWarning:Pycurl is not compiled against Openssl. Wfuzz might not work correctly when fuzzing SSL sites. Check Wfuzz's documentation for more information.
 /usr/lib/python3/dist-packages/wfuzz/wfuzz.py:78: UserWarning:Fatal exception: FUZZ words and number of payloads do not match!                                                           
```

## 模組架構
- [Wfuzz初上手](https://www.gushiciku.cn/pl/2sgl/zh-tw)
- []()
```
5種類型分別是： 
payloads 
encoders 
iterators 
printers 
scripts
```
## wfuzz -e payloads
```
Available payloads:
  Name            | Summary                                                                           
------------------------------------------------------------------------------------------------------
  guitab          | 從視覺化的標籤欄中讀取請求                                
  dirwalk         | 遞迴獲得本地某個資料夾中的檔名                            
  file            | 獲取一個檔案當中的每個詞                                                    
  autorize        | 獲取autorize的測試結果Returns fuzz results' from autororize.                                            
  wfuzzp          | 從之前儲存的wfuzz會話中獲取測試結果的URL                   
  ipnet           | 獲得一個指定網路的IP地址清單                                        
  bing            | 獲得一個使用bing API搜尋的URL清單 (需要 api key).                   
  stdin           | 獲得從標準輸入中的條目                                                
  list            | 獲得一個清單中的每一個元素，清單用以 - 符號分格                       
  hexrand         | 從一個指定的範圍中隨機獲取一個hex值                                  
  range           | 獲得指定範圍內的每一個數值                                          
  names           | 從一個以 - 分隔的列表中，獲取以組合方式生成的所有usernames值
  burplog         | 從BurpSuite的記錄中獲得測試結果                                             
  permutation     | 獲得一個在指定charset和length時的字元組合                             
  buffer_overflow | 獲得一個包含指定個數個A的字串.                    
  hexrange        | 獲得指定範圍內的每一個hex值                                   
  iprange         | 獲得指定IP範圍內的IP地址清單                                 
  burpstate       | 從BurpSuite的狀態下獲得測試結果
```

## wfuzz -e encoders
```
Available encoders:
  Category      | Name                      | Summary                                                                           
------------------------------------------------------------------------------------------------------------------------
  url_safe, url | urlencode                 | 用`%xx`的方式替換特殊字元， 字母/數字/下劃線/半形點/減號不替換
  url_safe, url | double urlencode             | 用`%25xx`的方式替換特殊字元， 字母/數字/下劃線/半形點/減號不替換
  url              | uri_double_hex            | 用`%25xx`的方式將所有字元進行編碼
  html          | html_escape                | 將`&`，`<`，`>`轉換為HTML安全的字元
  html            | html_hexadecimal             | 用 `&#xx;` 的方式替換所有字元
  hashes         | base64                    | 將給定的字串中的所有字元進行base64編碼
  url             | doble_nibble_hex             | 將所有字元以`%%dd%dd`格式進行編碼
  db             | mssql_char                | 將所有字元轉換為MsSQL語法的`char(xx)`形式
  url             | utf8                        | 將所有字元以`\u00xx` 格式進行編碼
  hashes         | md5                         | 將給定的字串進行md5加密
  default         | random_upper                | 將字串中隨機字元變為大寫
  url             | first_nibble_hex          | 將所有字元以`%%dd?` 格式進行編碼
  default         | hexlify                    | 每個資料的單個位元轉換為兩個位元表示的hex表示
  url             | second_nibble_hex         | 將所有字元以`%?%dd` 格式進行編碼
  url             | uri_hex                     | 將所有字元以`%xx` 格式進行編碼
  default         | none                         | 不進行任何編碼
  hashes         | sha1                        | 將字串進行sha1加密
  url             | utf8_binary                | 將字串中的所有字元以 `\uxx` 形式進行編碼
  url             | uri_triple_hex             | 將所有字元以`%25%xx%xx` 格式進行編碼
  url             | uri_unicode                | 將所有字元以`%u00xx` 格式進行編碼
  html             | html_decimal                | 將所有字元以 `&#dd; ` 格式進行編碼
  db             | oracle_char                | 將所有字元轉換為Oracle語法的`chr(xx)`形式
  db             | mysql_char                 | 將所有字元轉換為MySQL語法的`char(xx)`形式

```
## wfuzz -e scripts
```
Available scripts:
  Category                   | Name          | Summary
----------------------------------------------------------------------------------------------------
  default, passive           | cookies       | 查詢新的cookies
  default, passive           | errors        | 查詢錯誤資訊
  passive                    | grep          | HTTP response grep
  active                     | screenshot    | 用linux cutycapt tool 進行螢幕抓取 
  default, active, discovery | links         | 解析HTML並查詢新的內容
  default, active, discovery | wc_extractor  | 解析subversion的wc.db檔案
  default, passive           | listing       | 查詢列目錄漏洞
  default, passive           | title         | 解析HTML頁面的title
  default, active, discovery | robots        | 解析robots.txt檔案來查詢新內容
  default, passive           | headers       | 查詢伺服器的返回頭
  default, active, discovery | cvs_extractor | 解析 CVS/Entries 檔案
  default, active, discovery | svn_extractor | 解析 .svn/entries 檔案
  active, discovery          | backups       | 查詢已知的備份檔名
  default, active, discovery | sitemap       | 解析 sitemap.xml 檔案
```
## wfuzz -e printer
```
Usage:  wfuzz [options] -z payload,params <url>

        FUZZ, ..., FUZnZ  wherever you put these keywords wfuzz will replace them with the values of the specified payload.
        FUZZ{baseline_value} FUZZ will be replaced by baseline_value. It will be the first request performed and could be used as a base for filtering.


Examples:
        wfuzz -c -z file,users.txt -z file,pass.txt --sc 200 http://www.site.com/log.asp?user=FUZZ&pass=FUZ2Z
        wfuzz -c -z range,1-10 --hc=BBB http://www.site.com/FUZZ{something not there}
        wfuzz --script=robots -z list,robots.txt http://www.webscantest.com/FUZZ

Type wfuzz -h for further information or --help for advanced usage.
 /usr/lib/python3/dist-packages/wfuzz/wfuzz.py:78: UserWarning:Fatal exception: Unknown category. Valid values are: payloads, encoders, iterators, printers or scripts.
```
## wfuzz -e iterators
```
 /usr/lib/python3/dist-packages/wfuzz/__init__.py:34: UserWarning:Pycurl is not compiled against Openssl. Wfuzz might not work correctly when fuzzing SSL sites. Check Wfuzz's documentation for more information.

Available iterators:

  Name    | Summary                                                                           
----------------------------------------------------------------------------------------------
  chain   | Returns an iterator returns elements from the first iterable until it is exhaust  
          | ed, then proceeds to the next iterable, until all of the iterables are exhausted  
          | .                                                                                 
  product | Returns an iterator cartesian product of input iterables.                         
  zip     | Returns an iterator that aggregates elements from each of the iterables.
```
## 
```
┌──(kali㉿kali)-[/usr/bin]
└─$ wfuzz -h                                                           1 ⨯
 /usr/lib/python3/dist-packages/wfuzz/__init__.py:34: UserWarning:Pycurl is not compiled against Openssl. Wfuzz might not work correctly when fuzzing SSL sites. Check Wfuzz's documentation for more information.
********************************************************
* Wfuzz 3.1.0 - The Web Fuzzer                         *
*                                                      *
* Version up to 1.4c coded by:                         *
* Christian Martorella (cmartorella@edge-security.com) *
* Carlos del ojo (deepbit@gmail.com)                   *
*                                                      *
* Version 1.4d to 3.1.0 coded by:                      *
* Xavier Mendez (xmendez@edge-security.com)            *
********************************************************

Usage:  wfuzz [options] -z payload,params <url>

        FUZZ, ..., FUZnZ  wherever you put these keywords wfuzz will replace them with the values of the specified payload.
        FUZZ{baseline_value} FUZZ will be replaced by baseline_value. It will be the first request performed and could be used as a base for filtering.


Options:
        -h                        : This help
        --help                    : Advanced help
        --version                 : Wfuzz version details
        -e <type>                 : List of available encoders/payloads/iterators/printers/scripts

        -c                        : Output with colors
        -v                        : Verbose information.
        --interact                : (beta) If selected,all key presses are captured. This allows you to interact with the program.

        -p addr                   : Use Proxy in format ip:port:type. Repeat option for using various proxies.
                                    Where type could be SOCKS4,SOCKS5 or HTTP if omitted.

        -t N                      : Specify the number of concurrent connections (10 default)
        -s N                      : Specify time delay between requests (0 default)
        -R depth                  : Recursive path discovery being depth the maximum recursion level (0 default)
        -D depth                  : Maximum link depth level (4 default)
        -L, --follow              : Follow HTTP redirections

        -u url                    : Specify a URL for the request.
        -z payload                : Specify a payload for each FUZZ keyword used in the form of type,parameters,encoder.
                                    A list of encoders can be used, ie. md5-sha1. Encoders can be chained, ie. md5@sha1.
                                    Encoders category can be used. ie. url
                                    Use help as a payload to show payload plugin's details (you can filter using --slice)
        -w wordlist               : Specify a wordlist file (alias for -z file,wordlist).
        -V alltype                : All parameters bruteforcing (allvars and allpost). No need for FUZZ keyword.
        -X method                 : Specify an HTTP method for the request, ie. HEAD or FUZZ

        -b cookie                 : Specify a cookie for the requests
        -d postdata               : Use post data (ex: "id=FUZZ&catalogue=1")
        -H header                 : Use header (ex:"Cookie:id=1312321&user=FUZZ")
        --basic/ntlm/digest auth  : in format "user:pass" or "FUZZ:FUZZ" or "domain\FUZ2Z:FUZZ"

        --hc/hl/hw/hh N[,N]+      : Hide responses with the specified code/lines/words/chars (Use BBB for taking values from baseline)
        --sc/sl/sw/sh N[,N]+      : Show responses with the specified code/lines/words/chars (Use BBB for taking values from baseline)
        --ss/hs regex             : Show/Hide responses with the specified regex within the content
```
