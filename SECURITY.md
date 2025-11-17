## 🛡️对称加密流程

```plaintext
明文 → 压缩 → AES256-CTR加密 → ChaCha20-Poly1305加密 → Base64编码 → 密文
                                                         ↳ 映射 中文/Emoji/零宽... → 密文
```

### 密钥、IV、Nonce派生流程

#### v1.3.0.0及以上

```plaintext
（密码 + 随机Seed）Argon2id 
                     ↳（MasterKey + Seed）HKDF-SHA512
                                              ↳ 派生AES-CTR密钥(256位)
                                              ↳ 派生ChaCha20密钥(256位)
                                              ↳ 派生AES-CTR IV(16字节)
                                              ↳ 派生ChaCha20 Nonce(12字节)
```
#### v0.7.0.0 - v1.2.3.0版本

```plaintext
（密码 + 随机Salt）PBKDF2-SHA256 → HKDF-SHA256
                                     ↳ 派生AES-CTR密钥(256位)
                                     ↳ 派生ChaCha20密钥(256位)
IV(16字节)、Nonce(12字节)，随机
```

### 数据结构

#### v1.3.0.0及以上

```plaintext
[中文、Emoji、零宽.../Base64 密文]
        ↳ 映射→解码/解码
              ↳[二进制数据]
                   ↳ Seed + ChaCha20密文
                          ↳ 解密 → AES-CTR密文
                                 ↳ 解密 → Deflate-raw解压 → [明文]
```
#### v0.7.0.0 - v1.2.3.0版本

```plaintext
[中文、Emoji、零宽.../Base64 密文]
       ↳ 映射→解码/解码
            ↳[二进制数据]
                ↳ Salt + ChaCha20 Nonce + ChaCha20密文
                     ↳ 解密 → AES-CTR IV + AES-CTR密文
                           ↳ 解密 → Deflate解压 → [明文]
```



## 🛡️非对称加密流程

```plaintext
光文本 → 压缩||暗文本 → 压缩
            ↳ 分别进行 AES256-CTR加密 → ChaCha20-Poly1305加密 → Base64编码 → 密文
                                                         ↳ 映射 中文/Emoji/零宽... → 密文
```

### 密钥、IV、Nonce派生流程

#### v2.0.0.0及以上

```
（Shared Secret + 随机Seed）Argon2id 
                     ↳（MasterKey + Seed）HKDF-SHA512
                                              ↳ 派生AES-CTR密钥(256位)
                                              ↳ 派生ChaCha20密钥(256位)
                                              ↳ 派生AES-CTR IV(16字节)
                                              ↳ 派生ChaCha20 Nonce(12字节)
```

### 数据结构

#### v2.0.0.0及以上

```
[中文、Emoji、零宽.../Base64 密文]
        ↳ 映射→解码/解码
              ↳[光密文||暗密文]
                   ↳ Seed + ChaCha20密文
                          ↳ 解密 → AES-CTR密文
                                 ↳ 解密 → Deflate-raw解压 → [光文本/暗文本]
```

## 🎭安全要素

| 要素           | 长度    | 方式            | 用途                     |
| -------------- | ------- | --------------- | ------------------------ |
| 加密算法       | -       | 级联            | 增强数据安全性           |
| 密钥派生       | -       | Argon2id + HKDF | 防止暴力破解、彩虹表攻击 |
| 种子 (Seed)    | 16字节  | 随机生成        | 初始的安全随机数         |
| 盐 (Salt)      | 16 字节 | 随机种子派生    | 确保每次加密生成唯一密钥 |
| AES-CTR IV     | 16 字节 | 随机种子派生    | 计数器初始值             |
| ChaCha20 Nonce | 12 字节 | 随机种子派生    | 一次性随机数             |
| Shared Secret | 98 字节 | X25519 + P521 |共享密钥|

- 设备需保证安全，无病毒木马、无可疑的窃听软件
- 包括不限于**不受信任的浏览器、输入法、杀毒软件**

## 🗣️漏洞报告

如需私密提交，请用作者的公钥加密，**并附上你的公钥**

```key
📢:FXzJX6BENBPuvG17hxrkSh+k31SvVD4mgZ7qkbIHWXEEAEH5NfpF/e/banniB9ZfWEG5qHRp6jHZL5Wfjv0KimZFiSP/56eX42mIKkRtGyOBF/5jPQ2Ul2EZr8ule303wH0xAWw3nma2ymOz+VqSfkR/uVe3Ca/AeN7WULXH8uZSLOsb1D/IsmTL1ZMCo5ua5XhTmtHHR5c+kQci87S77UTcRAu0
```

[![漏洞报告](https://img.shields.io/badge/%E6%BC%8F%E6%B4%9E%E6%8A%A5%E5%91%8A-gold?style=for-the-badge&logo=github&&logoColor=black)](https://github.com/fzxx/XiangYue/security/advisories/new)
