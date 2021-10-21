# [Public-key cryptography公開金鑰](https://en.wikipedia.org/wiki/Public-key_cryptography)

- 著名被廣泛運用的公開金鑰(Examples of well-regarded asymmetric key techniques for varied purposes)
  - Diffie–Hellman key exchange protocol
  - DSS (Digital Signature Standard), which incorporates the Digital Signature Algorithm
  - ElGamal
  - [Elliptic-curve cryptography橢圓曲線密碼學](https://en.wikipedia.org/wiki/Elliptic-curve_cryptography)
    - Elliptic Curve Digital Signature Algorithm (ECDSA)
    - Elliptic-curve Diffie–Hellman (ECDH)
    - Ed25519 and Ed448 (EdDSA)
    - X25519 and X448 (ECDH/EdDH)
  - Various password-authenticated key agreement techniques
  - Paillier cryptosystem
  - [RSA encryption algorithm (PKCS#1)RSA加密演算法](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
  - Cramer–Shoup cryptosystem
  - YAK authenticated key agreement protocol

- 著名但不被廣泛運用的公開金鑰 Examples of asymmetric key algorithms not yet widely adopted include:
  - NTRUEncrypt cryptosystem
  - McEliece cryptosystem

- 著名但不安全的公開金鑰(Examples of notable – yet insecure – asymmetric key algorithms)
  - Merkle–Hellman knapsack cryptosystem

- 使用公開金鑰的網路協定(Examples of protocols using asymmetric key algorithms)
  - S/MIME
  - GPG, an implementation of OpenPGP, and an Internet Standard
  - EMV, EMV Certificate Authority
  - IPsec
  - PGP
  - ZRTP, a secure VoIP protocol
  - Transport Layer Security(TLS) 及其前身 Secure Socket Layer(SSL)
  - SILC
  - SSH
  - Bitcoin
  - [Off-the-Record Messaging (OTR)](https://en.wikipedia.org/wiki/Off-the-Record_Messaging)

# [RSA公開金鑰](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
### Key generation(產生key pair)
- 隨意選擇兩個大的質數p和q[p不等於q]
- 計算n=pq
- 根據歐拉函數，求得 φ(n)=(p-1)(q-1)
- 選擇一個小於φ(n)的整數e，使e與φ(n)互質
- 求得e關於φ(n)的模反元素(module inverse)，命名為d {d*e mod φ(n) =1 }(模反元素存在，若且唯若e與 φ(n)互質）
- 公鑰pub={e,n}    私鑰pri={d,n}

### [英文版wiki](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
```
英文版wiki 使用  λ(n) Carmichael's totient function.
原始論文使用φ(n)=(p-1)(q-1)
兩者皆可:
any d satisfying d⋅e ≡ 1 (mod φ(n)) also satisfies d⋅e ≡ 1 (mod λ(n))
```
## RSA加解密

- 加密 使用公鑰pub={e,n}加密  ==> ciphertext = (plaintext)^e mod n

- 解密 使用私鑰pri={d,n}解密  ==>  plaintext = (ciphertext )^d mod n

<img src="https://render.githubusercontent.com/render/math?math=plaintext = (ciphertext )^{d} mod n">
<img src="https://render.githubusercontent.com/render/math?math=e^{i \pi} = -1">

## 範例說明
### Key generation(產生key pair)
```
(1)Select primes隨意選擇兩個大的質數p和q，p不等於q    p=17, q=11
(2)Compute n=pq=187
(3)Compute φ(n)=(p-1)(q-1)=160
(4)Select e=7  such that GCD(7,160)=1
(5)Compute d: d=23 ==> 7*23 mod 160=1 (use the extended Euclid’s algorithm)

公鑰pub={e,n}={7,187}
私鑰pri={d,n}={23,187}
```

### RSA加解密
```
明文M=88
加密(Encrypt): 88^7mod 187
88^7mod 187 =  11(密文C)

解密Decrypt C=11: 11^23mod 187
M=11^23 mod 187=88
```

# RSA的 安全基礎 ==> 質因數因數分解 

# 小n攻擊 [中文版wiki](https://en.wikipedia.org/wiki/RSA加密演算法)
- n太小 可很容易被質因數分解出
- n = p * q   15 = 5 * 3  187 = 17 * 11

- 1999年，RSA-155 (512 bits)被成功分解
  - 花了五個月時間（約8000 MIPS年）和224 CPU hours在一台有3.2G中央記憶體的Cray C916電腦上完成
  - RSA-155表示如下：
```
39505874583265144526419767800614481996020776460304936454139376051579355626529450683609
727842468219535093544305870490251995655335710209799226484977949442955603
= 3388495837466721394368393204672181522815830368604993048084925840555281177 ×
  11658823406671259903148376558383270818131012258146392600439520994131344334162924536139
```

- 2009年12月12日，編號為RSA-768（768 bits, 232 digits）數也被成功分解。
  - 這事件威脅了現通行的1024-bit金鑰的安全性，普遍認為使用者應儘快升級到2048-bit或以上。
  -  RSA-768表示如下：
```
123018668453011775513049495838496272077285356959533479219732245215172640050726
365751874520219978646938995647494277406384592519255732630345373154826850791702
6122142913461670429214311602221240479274737794080665351419597459856902143413

= 33478071698956898786044169848212690817704794983713768568912431388982883793878002287614711652531743087737814467999489   ×
  36746043666799590428244633799627952632279158164343087642676032283815739666511279233373417143396810270092798736308917
```




