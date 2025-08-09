# 铸造

当用户在将资金存入收益来源时，会获得生息资产。例如，在 Lista 中抵押的 BNB 将得到 _slisBNB,_ Lido 中质押的 ETH 将得到 _stETH_。

_slisBNB_ 和 _stETH_ 就是**生息代币**的示例。

在 OutStake 中，生息代币可以拆分为两个部分：**Staked Position Token (SP)** 和 **Yield Token (YT)**。

同时，**SP** 可以进一步拆分为**全链通用本金代币（UPT ）**&#x548C;**不可转让的 SP**，也可以重新合成回可转让的 **SP**。

每个令牌代表的含义如下：

* **SP** 代表锁定头寸的本金到期赎回的权利。
* **UPT** 代表底层生息代币的初始本金部分。
* **YT** 代表对该资产所有利息收益的权利。

用户可以通过在 **OutStake** 质押生息资产（例如 stETH）来铸造 SP，YT 以及 UPT。底层基础资产（例如 ETH）将在质押之前，自动转换为生息资产。

例如，ETH → wstETH → SY-wstETH → (SP-wstETH + YT-wstETH)，SP-wstETH <=> UETH。
