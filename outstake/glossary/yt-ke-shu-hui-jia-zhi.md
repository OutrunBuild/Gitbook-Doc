---
description: YT Redeemable Value
---

# YT 可赎回价值

质押池中的生息代币的利息收益将会随着时间不断累积到对应的 Yield Pool，用户可以在任意时刻通过燃烧 YT 赎回 其对应的已积累利息收益。

YT 可赎回价值是指：每一个 YT 代币，在当前时间点上，可以从 Yield Pool 中兑换回多少实际的、已累积的收益。

其计算方式如下：

<p align="center"><span class="math">\text{YT 可赎回价值} = \frac{\text{YieldPool 已累积收益}}{\text{YT 总供应量}}</span></p>

* YieldPool 已累积收益：这是指质押池中所有生息资产到目前为止已累积到 Yield Pool 的总收益。这个数值是一个不断变化的量，会随着质押的生息资产利息收益不断增加，也会随着用户燃烧 YT 而减少。
* YT 总供应量：这是当前市场上流通的所有 YT 代币的总数量。

简单来说，YT 可赎回价值就是：如果现在就结算 Yield Pool 中的所有累积收益，然后按比例分给所有 YT 代币的持有者，那么每个 YT 代币能分到多少收益。
