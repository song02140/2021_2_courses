
# wfuzz

- wfuzz 是一款Python開發的Web安全模糊測試工具。
- [官方網址https://github.com/xmendez/wfuzz ](https://github.com/xmendez/wfuzz)
- 功能特點
  - 模組化 框架 可編寫外掛
  - 介面 可處理BurpSuite所抓的請求和響應報文
  - 可執行 `請求(http request)`引數類的模糊測試 
  - Web目錄掃描(web directory travel|list)。

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
