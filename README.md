# 【Security】常見的加密方式

本文整理了常見的安全算法，包括MD5、SHA、DES、AES、RSA等。

## ㄧ、數字（訊息）摘要演算法
        數字摘要也稱作訊息摘要，它是藉由一個單向的 Hash 函數對訊息進行計算後產生一個固定長度的值。
        當訊息在傳輸過程中改變的話，接受者可以對過收到的訊息用同樣的 Hash 函數和值去做比對，就可以知道是否在傳輸過程中有改變。
        因此確保訊息的正確性和完整性。這串計算過後的值，也稱作數字指紋。

      1. MD5（Message Digest Algorithm 5）
         MD5 是數字摘要演算法一種實現，用於確保信息傳輸完整性和一致性，摘要長度為128位（16 byte）。 
         MD5由 MD4、 MD3、 MD2 改進而來，主要增強算法複雜度和不可逆性，該算法因其普遍、穩定、快速的特點，在產業界得到了極為廣泛的使用，目前主流的編程語言普遍都已有MD5算法實現。
         但是在 2009 年謝濤和馮登國僅用了 2e20.96 的碰撞演算法複雜度，破解了MD5的碰撞抵抗，該攻擊在普通電腦上執行只需要數秒鐘。參考資料

      2.SHA（Secure Hash Algorithm）
        SHA 是安全雜湊演算法。 1993年，SHA 由美國國家安全局（NSA）所設計，並由美國國家標準與技術研究院（NIST）發布，並作為聯邦信息處理標準(FIPS PUB 180)公佈， 1995 年又發布了一個修訂版 FIPS PUB 180-1，通常稱之為 SHA-1。
        SHA-1 是基於 MD4 算法的，現在已成為公認的最安全的散列算法之一，並被廣泛使用。 
        SHA-1 算法生成的摘要信息的長度為 160 位，由於生成的摘要信息更長，運算的過程更加複雜，在相同的硬件上， SHA-1 的運行速度比 MD5 更慢，但是也更為安全。2017 年 Google 攻破 SHA-1 加密技術，目前最新的版本是 SHA-3 。


## 二、對稱密鑰加密
        對稱密鑰加密（英語：Symmetric-key algorithm）又稱為對稱加密、私鑰加密、共享密鑰加密，是密碼學中的一類加密演算法。
        這類演算法在加密和解密時使用相同的密鑰，或是使用兩個可以簡單地相互推算的密鑰。
        實務上，這組密鑰成為在兩個或多個成員間的共同祕密，以便維持專屬的通訊聯繫。
        與公開密鑰加密相比，要求雙方取得相同的密鑰是對稱密鑰加密的主要缺點之一。
        在對稱加密算法中，數據發送方將明文(原始數據)和加密密鑰一起經過特殊加密算法處理後，生成複雜的加密密文進行發送，數據接收方收到密文後，若想讀取原文，則需要使用加密使用的密鑰及相同算法的逆算法對加密的密文進行解密，才能使其恢復成可讀明文。
        在對稱加密算法中，使用的密鑰只有一個，發送和接收雙方都使用這個密鑰對數據進行加密和解密，這就要求加密和解密方事先都必須知道加密的密鑰。
        常見的對稱加密算法有DES、3DES、AES、Blowfish、IDEA、RC5、RC6。對稱加密的速度比公鑰加密快很多，在很多場合都需要對稱加密。


DES（Data Encryption Standard）
          DES 資料加密標準。1973 年，美國國家標準局(NBS)在認識到建立數據保護標準既明顯又急迫的情況下，開始徵集聯邦數據加密標準的方案。 1975 年3月17日， NBS 公佈了 IBM 公司提供的密碼算法，以標準建議的形式在全國內徵求意見。經過兩年多的公開討論之後， 1977 年7月15日， NBS 宣布接受這建議，作為聯邦信息處理標準 46 號數據加密標準(Data Encryptin Standard)，即 DES 正式頒布，供商業界和非國防性政府部門使用。 DES 算法屬於對稱加密算法，明文按 64 位進行分組，密鑰長 64 位，但事實上只有 56 位參與DES
運算(第8、 16、 24、 32、 40、 48、 56、 64位是校驗位，使得每個密鑰都有奇數個1)，分組後的明文和 56 位的密鑰按位替代或交換的方法形成密文。由於計算機運算能力的增強，原版DES 密碼的密鑰長度變得容易被暴力破解，因此演變出了 3DES 算法。 3DES 是 DES 向 AES 過渡的加密算法，它使用 3 條 56 位的密鑰對數據進行三次加密，是 DES 的一個更安全的變形。
        DES 現在已經不是一種安全的加密方法，主要因為它使用的 56 位金鑰過短。1999 年 1 月，distributed.net 與電子前哨基金會合作，在 22 小時 15 分鐘內即公開破解了一個 DES 金鑰。也有一些分析報告提出了該演算法的理論上的弱點，雖然在實際中難以應用。為了提供實用所需的安全性，可以使用 DES 的衍生演算法 3DES 來進行加密，雖然 3DES 也存在理論上的攻擊方法。在 2001 年，DES 作為一個標準已經被高階加密標準（AES）所取代。另外， DES 已經不再作為國家標準科技協會（前國家標準局）的一個標準。

      2. AES（Advanced Encryption Standard）
          AES 是進階加密標準，又稱 Rijndael 加密算法，是美國聯邦政府採用的一種對稱加密標準，這個標準用來替代原先的 DES 算法，已經廣為全世界所使用，已然成為對稱加密算法中最流行的算法之一。 AES 算法作為新一代的數據加密標準匯聚了強安全性、高性能、高效率、易用和靈活等優點，設計有三個密鑰長度：128、92、256 位，比 DES 算法的加密強度更高，更為安全。
        2005 年 10 月，Eran Tromer 和另外兩個研究員發表了一篇論文，展示了數種針對 AES 的緩存時序攻擊法。

## 三、公開金鑰加密
        公開密鑰加密算法又稱為非對稱加密算法，它需要兩個密鑰，一個稱為公開密鑰(public key)，即公鑰，另一個稱為私有密鑰(private key)，即私鑰。公鑰與私鑰需要配對使用，如果用公鑰對數據進行加密，只有用對應的私鑰才能進行解密，而如果使用私鑰對數據進行加密，那麼只有用對應的公鑰才能進行解密。因為加密和解密使用的是兩個不同的密鑰，所以這種算法稱為非對稱加密算法。非對稱加密算法實現機密信息交換的基本過程是：甲方生成一對密鑰並將其中的一把作為公鑰向其它人公開，得到該公鑰的乙方使用該密鑰對機密信息進行加密後再發送給甲方，甲方再使用自己保存的另一把專用密鑰，即私鑰，對加密後的信息進行解密。
        常見的公鑰加密演算法有：RSA、ElGamal、背包演算法、Rabin（RSA的特例）、迪菲－赫爾曼金鑰交換協定中的公鑰加密演算法、橢圓曲線加密演算法（英語：Elliptic Curve Cryptography, ECC）。使用最廣泛的是 RSA 演算法（由發明者 Rivest、Shmir 和 Adleman 姓氏首字母縮寫而來）是著名的公開秘鑰加密演算法，ElGamal 是另一種常用的非對稱加密演算法。
      1. RSA
         RSA 非對稱加密算法是 1977 年由 Ron Rivest、 Adi Shamirh 和 LenAdleman 開發的， RSA 取名來自開發他們三者的名字。 RSA是目前最有影響力的非對稱加密算法，它能夠抵抗到目前為止已知的所有密碼攻擊，已被 ISO 推薦為公鑰數據加密標準。 RSA 算法基於一個十分簡單的數論事實：將兩個大整數相乘十分容易，但反過來想要對其乘積進行因式分解卻極其困難，因此可以將乘積公開作為加密密鑰。假如有人找到一種快速因數分解的演算法的話，那麼用 RSA 加密的訊息的可靠性就肯定會極度下降。但找到這樣的演算法的可能性是非常小的。今天只有短的 RSA 鑰匙才可能被強力方式破解。到目前為止，世界上還沒有任何可靠的攻擊 RSA 演算法的方式。只要其鑰匙的長度足夠長，用 RSA 加密的訊息實際上是不能被破解的。

