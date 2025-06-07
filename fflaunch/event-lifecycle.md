# 事件生命周期

在 **FFLaunch** 事件的生命周期中一共有 3 个实体，6 个阶段。

#### 实体

1. 投资者
2. **Outrun** 审核团队
3. 项目团队

#### 阶段

从**创世阶段**开始，**LaunchPool** 的每次阶段转换需要手动调用 **FFLauncher** 合约的 **changeStage** 方法

**1. 申请阶段**

* 项目团队编写 TokenGenerator, Token 以及 TimeLockVault 合约，TokenGenerator 合约需要实现 ITokenGenerator 接口，Token 合约需要继承 FFT 合约（可重写部分方法），TimeLockVault 合约为 LaunchPool 之外的剩余代币的锁定金库合约（剩余 Token 生成阶段之前可以向 Outrun 审核团队申请更新 **TimeLockVault** 合约地址）。
* 项目团队向 Outrun 团队申请上线 FFLauncher，需要提交项目与团队详细资料以及 **Token**, **TokenGenerator**, **TimeLockVault** 合约，并持续与 Outrun 审核团队交流。

**2. 审核阶段**

* Outrun 审核团队将详细审核项目团队提交的相关资料。
* Outrun 审核团队将审计项目团队提交的 **TokenGenerator, Token** 以及 **TimeLockVault 合约**，检查是否安全和合规。
* Outrun 审核团队将**检查 Token 的释放情况，确保在 LP 锁定期间不会释放新的代币**。
* 若审核未通过，Outrun 审核团队将会对项目团队提出相关反馈，项目团队需要重新申请。
* 若审核通过，Outrun 审核团队将会向 FFLauncher 注册新的 LaunchPool.

{% hint style="info" %}
FFLaunch 未来将推出两种模式：一种基于人工申请与审核的 **Pro** 模式，另一种为基于 [TokenTable Unlocker](https://docs.tokentable.xyz/for-founders/tokentable-unlocker) 的**无许可**模式。
{% endhint %}

***

**3. 创世阶段**

* 当前区块时间处于 LaunchPool 的 startTime 与 endTime 之间时，任何人可以调用 changeStage 方法进入创世阶段。
* 在创世阶段，投资者可以向正在进行中的 LaunchPool 存入 [**UPT**](../outstake/yield-tokenization/pt.md)，FFLauncher 会记录每位投资者存入的 **GenesisFund**，其中 GenesisFund 的 **1/3** 会划分为 **liquidProofFunds**, **2/3** 划分为 **tokenFund**，会分别累加到 **totalTokenFunds** 以及 **totalLiquidProofFunds**.

**4. 流动性锁定阶段**

* 当前阶段为创世阶段且区块时间处于 LaunchPool 的 endTime 与 unlockTime 之间时，任何人都可以调用 changeStage 方法进入流动性锁定阶段。同时会调用项目团队注册的**代币生成器**根据 totalTokenFunds 铸造对应数量的项目代币，这些项目代币将会和数量等同于 totalTokenFunds 的 UPT 组成交易对并部署在 **Outrun AMM** 上，LP 代币将被锁定直到 **unlockTime**，同时铸造与 LP 代币数量相等的 [**POL**](proof-of-liquidity-token.md) 代币，**1/4** 数量的 POL 代币会与数量等同于 totalLiquidProofFunds 的 UPT 组成交易对，并锁定流动性直到 unlockTime，剩余 **3/4** 的 POL 代币用户将可以手动领取。
* 在流动性锁定阶段，锁定的项目代币交易对流动性产生的做市收益归项目团队所有，即项目团队募集到的持续现金流。而锁定的 POL 代币交易对流动性产生的做市收益则归属于协议收入。

**5. 流动性解锁阶段**

* 当前阶段为流动性锁定阶段且区块时间大于 LaunchPool 的 unlockTime 时，任何人都可以调用 changeStage 方法进入流动性解锁阶段。
* 在流动性解锁阶段，投资者可以按自己在创世阶段存入资金的比例赎回 **POL / UPT** 交易对的流动性，同时还可以销毁 POL 代币以赎回 **ProjectToken / UPT** 交易对的流动性
* 在区块时间到达 unlockTime 之后实施 24 小时的[**流动性保护期**](proof-of-liquidity-token.md)。

**6. 剩余代币生成阶段**

* 在流动性解锁阶段持续 **14** 天之后进入此阶段，任何人都可以调用 changeStage 方法进入剩余代币生成阶段。
* 在剩余代币生成阶段，项目团队可以调用 FFLauncher 合约的 **generateRemainingTokens** 方法**向 TimeLockVault 合约铸造剩余代币**。
* **如果 Token 是初始全流通的，则无法再铸造更多的 Token**.

**这些阶段和实体共同定义了 FFLaunch 事件的完整生命周期，确保项目在整个执行过程中的安全性、透明度和合规性。**
