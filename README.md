# collect-slowmist-detail

自己开这个repo主要是因为想基于慢雾slowmist的一些hacked记录，挑选自己感兴趣的部分去进行一些详细的记录分析，后面自己再回头看。


# 数据源
* 慢雾数据源：https://hacked.slowmist.io/zh/
* 慢雾安全团队知识库：https://github.com/slowmist/Knowledge-Base


# 事件记录

## 2025-02-21 Bybit交易所被盗14.6亿美元

### 事件时间线

* 2025-02-21，据链上侦探ZachXBT披露，Bybit平台发生大规模资金流出的情况。此次事件导致超14.6亿美元被盗。[暂无链接]
* 2025-02-21 23:44，Ben Zhou 发布一条 X，Bybit ETH 多重签名冷钱包向热钱包转账。[链接](https://x.com/benbybit/status/1892963530422505586)
* 2025-02-22 01:15，Ben Zhou 开启了 ETH 钱包的事件直播。[链接](https://x.com/Bybit_Official/status/1892986507113439328)
* 2025-02-22 据 @EmberCN 消息，已有 5 家机构/个人向 Bybit 提供总计 12 万枚 ETH（约 3.21 亿美元）的借款支援。Bitget：40,000 ETH（约 1.06 亿美元）；从币安提款的机构/鲸鱼：11,800 ETH（约 3102 万美元）；MEXC：12,652 stETH（约 3375 万美元）；币安或另一个从币安提款的机构/鲸鱼：36,000 ETH（约 9654 万美元）；0x327...45b 地址：20,000 ETH（约 5370 万美元）。[链接](https://mp.weixin.qq.com/s/Z-Wm-eYwdtSCz7Hemw3nbA)
* 2025-02-23 Bybit 经历了我们见过的最多的提款数量，总共有超过 35 万笔提款请求，到目前为止，大约有 2100 个提款请求有待处理。总体 99.994% 的提款已完成。[链接](https://mp.weixin.qq.com/s/Z-Wm-eYwdtSCz7Hemw3nbA)
* 2025-02-26 23:16，Safe 发布安全调查报告。[链接](https://x.com/safe/status/1894768522720350673)
* 2025-02-26 23:17，Ben Zhou 发布@sygnia_labsand 和 @Verichains 的安全调查报告。[链接](https://x.com/benbybit/status/1894768736084885929)
* 2025-03-04 09:04，黑客已经把从 Bybit 盗取的 49.9 万枚 ETH ($13.9 亿) 全部清洗完了，整个过程历时 10 天。[链接](https://x.com/EmberCN/status/1896728373340303440)


### 事件分析

* 攻击者先获取到 app.safe.global 的前端代码的控制权，然后针对 Bybit 的 Safe{Wallet} 钱包进行精准攻击。在 Bybit 的多签 Owner 使用 app.safe.global 进行签名时，让 Safe{Wallet} 的界面展示正常地址，实则在发起交易时已将交易内容替换成恶意的待签名数据，从而欺骗 Owner 签署了经过修改后的恶意待签名数据。最终，攻击者成功接管了 Bybit 的多签钱包的合约控制权，并实施盗币。[链接](https://mp.weixin.qq.com/s/FRah-8tZ9cI7Pc_u3JNXyg)
* 攻击链路
![攻击图片](https://mmbiz.qpic.cn/mmbiz_png/qsQ2ibEw5pLZJBtUlXow7INKOj3Bw8mEUdBxVTXmwh9dhic2QZQpBWibiafWqx54miaMt1sF2uMD4B1Rybk6BwibBdsg/640?wx_fmt=png&from=appmsg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)


