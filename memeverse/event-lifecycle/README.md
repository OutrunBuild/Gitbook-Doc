# 事件生命周期

相比于 **FFLaunch** 事件生命周期，**Memeverse** 事件的生命周期更加简单，只有 2 个实体，4 个阶段。

#### 实体

1. 投资者
2. 创建者

#### 阶段

从**创世阶段**开始，**Memeverse** 的每次阶段转换需要手动调用 **MemeverseLauncher** 合约的 **changeStage** 方法

**1. 准备阶段**

* 创建者在 Memeverse 的**网站 UI** 上按照提示输入相关的信息设置创世 Memeverse 的所有规则，选择创世的区块链（单个或者多个区块链），在支付跨链验证费以及目标链交易 gas 费并发送交易后，等待验证节点确认并完成全链注册，注册完成后即可进入创世阶段。
* 需要注意的是，被注册的 Symbol 在**流动性锁定阶段**结束前或者被**取消注册**前将被锁定，无法被重复注册。

**2. 创世阶段**

* 在 Memeverse 的创世阶段，用户可以在该 Memeverse 所处的任何一条链上参与创世，为该链部署流动性。如果 Memeverse 在多条链上进行创世，则每一条链都会有最大资金参与限制。
* 用户可以向指定的 Memeverse 存入 [UPT](../../outstake/yield-tokenization/upt.md)，MemeverseLauncher 会记录每位投资者存入的 **GenesisFund**，其中 GenesisFund 的 **1/5** 为 **liquidProofFunds**，**3/5** 为 **memecoinFunds**，会分别累加到 **totalMemecoinFunds** 以及 **totalLiquidProofFunds**，剩余的 **1/5** 会在流动性锁定阶段直接进入 Memecoin DAO 国库。
* 为了防止 Memeverse 的创世泛滥以及保证**足够的流动性**，每条链创世阶段所积攒的资金量必须达到 **minTotalFunds** 才能进入下个阶段，否则将会进入**退款阶段**。

**3.1. 退款阶段**

* 当前阶段为创世阶段且区块时间大于 Memeverse 的 endTime 时，任何人都可以调用 changeStage 方法进行阶段转换，如果当前链上积累的创世资金**小于 minTotalFunds** 则会进入退款阶段。如果该 Memeverse 在所有链都进入退款阶段，则会调用注册中心取消注册，其 Symbol 重新进入可注册状态。
* 在退款阶段，用户可以赎回在该 Memeverse 创世阶段当前链上存入的所有 UPT。

**3.2. 流动性锁定阶段**

* 当前阶段为创世阶段且区块时间大于 Memeverse 的 endTime 时，任何人都可以调用 changeStage 方法进行阶段转换，如果当前链上积累的创世资金**大于等于 minTotalFunds** 则会进入流动性锁定阶段。此时合约会根据创世阶段的 totalMemecoinFunds 铸造对应数量的 Memecoin，这些 Memecoin 将会和数量等同于 totalMemecoinFunds 的 UPT 组成交易对并部署在 **OutrunAMM** 上，LP 代币将被锁定直到 unlockTime，同时铸造与 LP 代币数量一样的 [**POL**](../../fflaunch/proof-of-liquidity-token.md) 代币，**1/6** 数量的 POL 代币会与数量等同于 totalLiquidProofFunds 的 UPT 组成交易对，并**永久锁定**，剩余 **5/6** 的 POL 代币用户将可以手动领取。最后 25% 总供应量的 Memecoin 会直接进入 Memecoin DAO 国库（在注册时可以提前规定在创世成功后立即将国库里的 Memecoin 与创世资金添加流动性，铸造 POL 代币到国库）。
* 在流动性锁定阶段，锁定的 **Memecoin / UPT** 交易对的创世流动性产生的做市收益的 UPT 部分归属于 **Memecoin DAO 国库**，从而为 Memecoin 社区运营提供经济支持与激励，而做市收益的 Memecoin 部分将会进入 **Memecoin 收益金库**，为 **Memecoin Staking** 提供持续的收益。

**4. 流动性解锁阶段**

* 当前阶段为流动性锁定阶段且区块时间大于 Memeverse 的 unlockTime 时，任何人都可以调用 changeStage 方法进入流动性解锁阶段。
* 在流动性解锁阶段，用户可以销毁 POL 代币以赎回 Memecoin / UPT 交易对的流动性。
* 在区块时间到达 unlockTime 之后实施 24 小时的[**流动性保护期**](../../fflaunch/proof-of-liquidity-token.md)。

**这些阶段和实体共同定义了 Memeverse 事件的完整生命周期，确保 Memecoin 在整个生命周期中的安全性、透明度和合规性。**
