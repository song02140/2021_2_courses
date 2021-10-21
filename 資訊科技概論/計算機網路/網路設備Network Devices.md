# 網路設備Network Devices

![網路設備Network Devices](網路設備.png)


## [router 路由器](https://zh.wikipedia.org/wiki/%E8%B7%AF%E7%94%B1%E5%99%A8)

- 路由器是屬於OSI`第三層`的產品，交換器是OSI第二層的產品
- 路由器就是連接兩個以上個別網路(段)的裝置 ==>  左網段(192.168.1.0/24)---路由器---右網段(192.165.8.0/24)
- [cisco 路由器](https://www.cisco.com/c/en/us/products/routers/900-series-integrated-services-routers-isr/index.html)


## [Network switch](https://en.wikipedia.org/wiki/Network_switch) [網路交換器](https://zh.wikipedia.org/wiki/%E7%B6%B2%E8%B7%AF%E4%BA%A4%E6%8F%9B%E5%99%A8)
- 交換器工作於OSI參考模型的第二層，即資料鏈路層。 已取代早期的 `橋接器(bridge)`
- 交換器內部的CPU會在每個埠成功連接時，通過將MAC位址和埠對應，形成一張MAC表。
- 在今後的通訊中，發往該MAC位址的封包將僅送往其對應的埠，而不是所有的埠。因此交換器可用於劃分資料鏈路層廣播，即衝突域(collision domain)；但它不能劃分網路層廣播，即廣播域(braodcast domain)。

## [Ethernet hub](https://en.wikipedia.org/wiki/Ethernet_hub)  [集線器](https://zh.wikipedia.org/wiki/%E9%9B%86%E7%B7%9A%E5%99%A8)
- 將多條乙太網路雙絞線或光纖集合連接在同一段物理媒介下的裝置
- 集線器是運作在OSI模型中的實體層，可以讓其連結的裝置工作在同一網段。
- 集線器上有多個I/O埠，訊號從任意一個埠進入後，會從其他埠出現。
- 中繼器（Repeater hub）也會參與衝突檢測（collision detection），在檢測到衝突時向所有通訊埠轉發擁塞訊號。
- 除了標準的8P8C（「RJ45」）水晶頭，一些集線器也支援BNC或AUI（附加單元介面）來連接傳統10BASE2或10BASE5網路。

- 由於集線器會把收到的任何數位訊號，經過`再生`或`放大(amplification)`，再從集線器的所有埠送出，這會造成訊號之間碰撞的機會很大，而且訊號也可能被竊聽
- 所有連到集線器的裝置，都是屬於同一個碰撞網域(collision domain)以及廣播網域(braodcast domain)，因此大部份集線器(超便宜)已被交換機(貴很多)取代。
