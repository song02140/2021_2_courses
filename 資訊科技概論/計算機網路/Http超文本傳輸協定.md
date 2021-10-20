## HTTP

- [Hypertext Transfer Protocol (HTTP)](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol)
- [超文本傳輸協定](https://zh.wikipedia.org/wiki/%E8%B6%85%E6%96%87%E6%9C%AC%E4%BC%A0%E8%BE%93%E5%8D%8F%E8%AE%AE)
  - HTTP是一種用於分佈式、協作式和超媒體訊息系統的`應用層`協定





![http](http.png)

## HTTP Request

![HTTP_Request](HTTP_Request.png)





###
- CRLF refers to the special character elements "Carriage Return" and "Line Feed." 
- These elements are embedded in HTTP headers and other software code to signify an End of Line (EOL) marker. 
- Many internet protocols, including MIME (e-mail), NNTP (newsgroups) and, more importantly, HTTP, use CRLF sequences to split text streams into discrete elements. 
- Web application developers split HTTP and other headers based on where CRLF is located. 
- CRLF injection attack ==> Exploits occur when an attacker is able to inject a CRLF sequence into an HTTP stream. 

### [HTTP Request method請求方法](https://zh.wikipedia.org/wiki/%E8%B6%85%E6%96%87%E6%9C%AC%E4%BC%A0%E8%BE%93%E5%8D%8F%E8%AE%AE)

https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods

## HTTP Response

![HTTP_Response](HTTP_Response.png)


### [HTTP Status Code(HTTP狀態碼)](https://zh.wikipedia.org/wiki/HTTP%E7%8A%B6%E6%80%81%E7%A0%81)

| 類別 |  簡述  | 說明 |
|  ---- |  -----  | -----  | 
| 1xx| 訊息| 請求已被伺服器接收，繼續處理|
| 2xx| 成功| 請求已成功被伺服器接收、理解、並接受|
| 3xx| 重新導向| 需要後續操作才能完成這一請求|
| 4xx| 客戶端錯誤| 請求含有詞法錯誤或者無法被執行|
| 5xx| 伺服器錯誤| 伺服器在處理某個正確請求時發生錯誤|

## 使用curl測試HTTP協定

## 使用python測試HTTP協定


# HTTP 認證

- [HTTP基本認證](https://zh.wikipedia.org/wiki/HTTP%E5%9F%BA%E6%9C%AC%E8%AE%A4%E8%AF%81)
- [HTTP摘要認證](https://zh.wikipedia.org/wiki/HTTP%E6%91%98%E8%A6%81%E8%AE%A4%E8%AF%81)  [Digest access authentication](https://en.wikipedia.org/wiki/Digest_access_authentication)


# [Hypertext Transfer Protocol Secure (HTTPS)](https://en.wikipedia.org/wiki/HTTPS)
