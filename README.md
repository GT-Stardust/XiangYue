# 想曰

[![GitHub stars](https://img.shields.io/github/stars/fzxx/XiangYue?style=social)](https://github.com/fzxx/XiangYue)   [![GitHub forks](https://img.shields.io/github/forks/fzxx/XiangYue?style=social&logo=github)](https://github.com/fzxx/XiangYue)   [![已关闭 Issues](https://img.shields.io/github/issues-closed/fzxx/XiangYue?label=已解决问题&color=green&logo=github)](https://github.com/fzxx/XiangYue/issues?q=is%3Aissue+is%3Aclosed)   [![许可证](https://img.shields.io/badge/License-私下研究专用许可-blue?logo=github)](https://github.com/fzxx/XiangYue/blob/main/main/License.txt)
[![级联算法](https://img.shields.io/badge/%E6%96%87%E6%9C%AC%E5%8A%A0%E5%AF%86%E9%A6%96%E4%B8%AA%E7%BA%A7%E8%81%94%E7%AE%97%E6%B3%95%E5%B7%A5%E5%85%B7-AES256%20CTR%20+%20ChaCha20%20Poly1305%20IETF-purple?logo=cryptpad&logoColor=white)](https://github.com/fzxx/XiangYue?tab=readme-ov-file#%EF%B8%8F-%E6%8A%80%E6%9C%AF%E7%BB%86%E8%8A%82)   [![多种密文](https://img.shields.io/badge/%E6%94%AF%E6%8C%81%E5%A4%9A%E7%A7%8D%E5%AF%86%E6%96%87-%E4%B8%AD%E6%96%87/Base64/Emoji/%E9%9B%B6%E5%AE%BD/%E6%97%A5%E8%AF%AD/%E9%9F%A9%E8%AF%AD-purple?logo=livechat&logoColor=white)](https://github.com/fzxx/XiangYue?tab=readme-ov-file#-%E7%89%B9%E7%82%B9)

<span style="color: Blue;"><strong><a href="https://github.com/fzxx/XiangYue" style="color: inherit;">想曰(yuē)</a></strong></span> 是基于现代加密技术的文本加密工具，使用**多算法级联加密**方案，确保数据在本地完成加密/解密，保护隐私安全。


## 🌟 特点

- ㊙️**密文**：支持 `中文/Base64/Emoji/零宽/日语/韩语` 密文
- 🔐**密钥**：`Argon2id + HKDF-SHA512`，有效抵御暴力破解
- 🔒**级联算法**：采用 `AES256-CTR` 与 `ChaCha20-Poly1305-IETF` 级联加密，**安全性极高**
- 📄**数据**：所有操作在本地完成，数据不离开设备

## 📋密文示例

以下密文使用 **默认密码** 加密

##### 中文密文

```plaintext
雷柜箱慕虎斜灯无羞站愁层梁条人岂解显无靠走峰抬旋吵所扶诉旗晃接勤哈袜方错美过晕盆拧奔随梦疏清跃蝶拍说海鸟房清烟月急压非片抖呱棒千说呱海晨也梯读盘压太甜旗狐向画颗得池厨又沉叉托茶暖峦虚小料叹门跨桂已闹李竖咯棒愿咯迷首馆
```

##### Base64 密文

```plaintext
J7ni11NnCUEe1+GtZcIWoJcKNgzsyN8K8BQBKnDn/1mLPkv2ul1VUcedyoIgZpXcNUKfy3HhZI6soaa54UcqLtJs52caSPuVo3EBOYvMqYS2
```

##### Emoji 密文

```plaintext
🍿⏫🐜🤕🚛🤧🎲▶️🦕🦢🛴🔣🏨💽⏹️🦴🐫🏓🔌🧂😚🚠🚢📷🪲🪃🚬🦋🤒🍏⏫♎️🦼📀📼😴⚜️👩👾🦇📟🍌🦏🕍⚱️😃🔭🧽🦍🍎🤫🌉🌆🥔🚔🍢😈😐🐌🏓🔋❣️💸🍑
```

##### 零宽密文（可藏在中文、网址、提取码、英文、Base64等可见字符中）

`https://github.com/fzxx/⁣⁡⁤؜⁣‍⁤⁣⁪⁡⁢‍⁤؜⁢⁭⁢⁯⁡⁢⁤⁯⁪⁢⁡‍⁤⁣⁤⁯⁤⁤⁢؜⁤⁮⁡⁠⁪‍⁣‍⁣⁣⁢⁬⁤͏⁤⁢⁣‌⁣⁪⁠⁮⁢⁯⁢⁮⁤⁠⁣⁣⁣‍⁣⁠⁤‍⁡‌⁤͏⁤⁡⁪⁬⁣⁫⁡⁠⁢⁢⁪‍⁢⁠⁤⁬⁡⁣⁤؜⁪⁢⁣⁪⁪‌⁢⁠⁪⁠⁣⁢⁪‍⁣⁫⁡⁬⁤⁭⁤⁠⁪‍⁢⁫⁢⁡⁡⁫⁣⁣⁡͏‌XiangYue`

##### 日语密文

```plaintext
ヷㇴょわㇿデぞズゆェピゆベナこマびむしヾノざュゝるスしニユダクぷすゾゔうゼダりち〴ㇹぐぁぇヘぷゼぺにづヂボゔㇲこぱミみぼメェだは
```

##### 韩语密文

```plaintext
퍼헬팁청쌀빠꽂뭇활현라골띤틀문헬룸로쿠텁완권ㅂ기멎끔해되릎펫닫궉뉴담답폼칼받듀릭맑일친끼죄루디ㄲ집멎블권대안지당톤사혐군즈꼭율한
```

## 🖥️在线与离线使用

[![在线页面](https://img.shields.io/badge/在线页面-想曰-yellow?logo=googlechrome&logoColor=white)](https://xyue.515188.xyz/)   [![免尴尬页面](https://img.shields.io/badge/免尴尬页面-想说-green?logo=firefox&logoColor=white)](https://xshuo.515188.xyz/)   [![Release](https://img.shields.io/github/v/release/fzxx/XiangYue?label=离线客户端&color=blue&logo=github)](https://github.com/fzxx/XiangYue/releases)

## 🔄️更新日志

[![更新日志](https://img.shields.io/badge/更新日志-gold?style=for-the-badge&logo=refinedgithub&logoColor=white)](https://github.com/fzxx/XiangYue/blob/main/CHANGELOG.md)

## 🛡️ 安全细节

[![安全细节](https://img.shields.io/badge/%E5%AE%89%E5%85%A8%E7%BB%86%E8%8A%82-gold?style=for-the-badge&logo=github&&logoColor=black)](https://github.com/fzxx/XiangYue/blob/main/SECURITY.md)

## 😕 疑问

#### 发送给多人如何管理多个密码？如何安全地传递密码？

- 使用可靠的密码管理器，例如：**KeePass**、KeePassXC、**Bitwarden**
- 使用**开源的阅后即焚文档**传递密码，例如：**PrivateBin**、pastebin

#### 少量文字也会生成较长的文本，能缩短吗？

- 因为**追求安全性**，所以添加了随机种子、校验标签参数，密文中存储这些参数导致的；去掉参数**追求短密文会削弱安全性**，目前已做到保障安全性的情况下最短了。

#### 感觉加密/解密慢？

- 使用**Argon2id算法(慢哈希算法)**的正常现象；Base64模式下，短文本理应1秒内加/解密完成，5M的文本（大约200万字）应3秒左右，这是可以接受的速度。

#### 支持加密/解密的最大容量？

- 不影响速度的情况下，**建议5M以下**（测试支持50M+）；超大的文本请使用压缩包或者其它方式加密。

#### 可以给密文再次加密？或者嵌入？

- `明文 → emoji密文 → 中文密文 → ......`  可以这样无限套娃加密，但不会增加安全性，安全性取决于你的密码，因此不建议这样做。
- **中文密文**嵌入**零宽密文**，会优先解密零宽，达成一文双解的效果，但并不能瞒过机器识别。

#### 经过某些软件发送密文后，解密错误？

- 是因为**某些软件喜欢折叠聊天内容**，或者发送过长的密文被截断，**安卓系统粘贴板有长度限制**，建议你检查密文的完整性；Eomij密文可能因为不同设备内置的表情不一导致解密错误，零宽密文有被某些平台过滤字符的可能。

#### 零宽密文只有两个字符？可见字符可以自定义？

- 密文总长度没有变，只是**转为不可见字符藏在两个可见字符中间**，是为了让人知道密文在哪，方便复制。
- 可以，只需**手动替换**密文中的可见字符（零宽密文**只是对人不可见**，机器是秒识别的，但识别不代表能解密）。

#### 有增加非对称加密的计划吗？

- 有，视Stars情况再考虑，太少人用没有增加的必要。

## 📖 许可证

[想曰](https://github.com/fzxx/XiangYue) - [私下研究专用许可](https://github.com/fzxx/XiangYue?tab=License-1-ov-file#)

[libsodium.js](https://github.com/jedisct1/libsodium.js/) - ISC 许可证

[pako](https://github.com/nodeca/pako) - MIT 许可证
