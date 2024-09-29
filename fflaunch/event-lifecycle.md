# 事件生命周期

在 **FFLaunch** 事件的生命周期中一共有 3 个实体，6 个阶段。

#### 实体

1. 投资者
2. **Outrun** 审核团队
3. 项目团队

#### 阶段

**1. 申请阶段**

* 项目团队编写 TokenGenerator, Token 以及 TimeLockVault 合约，TokenGenerator 合约需要实现 ITokenGenerator 接口，Token 合约需要继承 FFT 合约（可重写部分方法），TimeLockVault 合约为 LaunchPool 之外的剩余代币的锁定金库合约（剩余 Token 生成阶段之前可以向 Outrun 审核团队申请更新 **TimeLockVault** 合约地址）。
* 项目团队向 Outrun 团队申请上线 FFLauncher，需要提交项目与团队详细资料以及 TokenGenerator\*\*,\*\* Token\*\*,\*\* TimeLockVault 合约，并持续与 Outrun 审核团队交流。

**2. 审核阶段**

* Outrun 审核团队将详细审核项目团队提交的相关资料。
* Outrun 审核团队将审计项目团队提交的 **TokenGenerator, Token** 以及 **TimeLockVault 合约**，检查是否安全和合规。
* Outrun 审核团队将**检查 Token 的释放情况，确保在 LP 锁定期间不会释放新的代币**。
* 若审核未通过，Outrun 审核团队将会对项目团队提出相关反馈，项目团队需要重新申请。
* 若审核通过，Outrun 审核团队将会向 FFLauncher 注册新的 LaunchPool.

**3. Deposit 阶段**

* 当区块时间在已注册的 LaunchPool 的 startTime 与 endTime 之间时，投资者可以调用 FFLauncher 合约的 **deposit** 方法，向该 LaunchPool 存入**原生收益代币**，原生收益代币将质押到 **Outstake** 中以获取 [**PT**](../outstake/yield-tokenization/pt.md)，同时会调用项目团队注册的 **TokenGenerator** 合约生成对应数量的 Token，一部分 Token 会与 PT 在 **Outrun AMM** 上添加流动性，LP 将会锁定在 FFLauncher 合约中，**另一部分 Token 会直接发送给用户**。与此同时，还会铸造**流动性证明代币**作为用户添加的流动性的证明代币，该代币也可以**自由交易**。
* 当区块时间在已注册的 LaunchPool 的 endTime 之后时，此时已经是**流动性锁定阶段**，用户无法再通过质押原生收益代币铸造 Token。

**4. 流动性锁定阶段**

* **Deposit** 阶段结束后，**任何人**都可以调用 FFLauncher 的 **enablePoolTokenTransfer** 方法打开交易开关，此时 Token 可以自由交易。
* 在这个阶段期间，锁定在 FFLauncher 合约中的 LP 所产生的**做市收益归项目团队所有**，即项目团队募集到的持续现金流。

**5. 流动性解锁阶段**

* 当流动性锁定时间到期后，用户可以调用 FFLauncher 合约的 **claimPoolLiquidity** 方法燃烧**流动性证明代币**，将锁定的 LP 提取出来。
* **项目团队不再获取 LP 的做市收益**。

**6. 剩余代币生成阶段**

* 在 LP 解锁阶段持续 **7** 天之后进入此阶段，此时项目团队可以调用 FFLauncher 合约的 **generateRemainingTokens** 方法**向 TimeLockVault 合约铸造剩余代币**。
* **如果 Token 是初始全流通的，则无法再铸造更多的 Token**.

**这些阶段和实体共同定义了 FFLaunch 事件的完整生命周期，确保项目在整个执行过程中的安全性、透明度和合规性。**
