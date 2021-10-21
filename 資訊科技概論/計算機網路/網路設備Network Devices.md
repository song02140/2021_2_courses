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
### [VLAN(Virtual Local Area Network)](https://en.wikipedia.org/wiki/Virtual_LAN) [虛擬區域網路](https://zh.wikipedia.org/wiki/%E8%99%9A%E6%8B%9F%E5%B1%80%E5%9F%9F%E7%BD%91)

- VLAN是一種將區域網設備從`邏輯`上劃分成一個個不同的網段，從而實現虛擬工作組的新興數據交換技術。
- 這種新興技術主要應用於`交換機`
- IEEE於1999年頒布了用以標準化VLAN實現方案的802.1Q協議標準草案。-  - VLAN技術的出現，使得管理員根據實際應用需求，把同一物理區域網內的不同用戶邏輯地劃分成不同的廣播域，每個VLAN都包含一組有著相同需求的計算機工作站，與物理上形成的LAN有著相同的屬性。由於是從邏輯上劃分，而不是從物理上劃分，所以同一個VLAN內的各個工作站沒有限制在同一個物理範圍內，即這些工作站可以在不同物理LAN網段。
- 由VLAN的特點可知，一個VLAN內部的廣播和單播流量都不會轉發到其他VLAN中，從而有助於控制量、減少設備投資、簡化網路管理、提高網路的安全性。交換技術的發展，也加快了新的交換技術(VLAN)的應用速度。通過將企業網路劃分為虛擬網路VLAN的網段，可以強化網路管理和網路安全，控制不必要的數據廣播。
- V-LAN是一種建構於`區域網路交換技術（LAN Switch）`的網路管理的技術，網管人員可以藉此透過控制交換器有效分派出入區域網的封包到正確的出入埠，達到對不同實體區域網中的裝置進行邏輯分群（Grouping）管理，並降低區域網內大量資料流通時，因無用封包過多導致壅塞的問題，以及提昇區域網的資訊安全保障。

## [Ethernet hub](https://en.wikipedia.org/wiki/Ethernet_hub)  [集線器](https://zh.wikipedia.org/wiki/%E9%9B%86%E7%B7%9A%E5%99%A8)
- 將多條乙太網路雙絞線或光纖集合連接在同一段物理媒介下的裝置
- 集線器是運作在OSI模型中的實體層，可以讓其連結的裝置工作在同一網段。
- 集線器上有多個I/O埠，訊號從任意一個埠進入後，會從其他埠出現。
- 中繼器（Repeater hub）也會參與衝突檢測（collision detection），在檢測到衝突時向所有通訊埠轉發擁塞訊號。
- 除了標準的8P8C（「RJ45」）水晶頭，一些集線器也支援BNC或AUI（附加單元介面）來連接傳統10BASE2或10BASE5網路。

- 由於集線器會把收到的任何數位訊號，經過`再生`或`放大(amplification)`，再從集線器的所有埠送出，這會造成訊號之間碰撞的機會很大，而且訊號也可能被竊聽
- 所有連到集線器的裝置，都是屬於同一個碰撞網域(collision domain)以及廣播網域(braodcast domain)，因此大部份集線器(超便宜)已被交換機(貴很多)取代。
