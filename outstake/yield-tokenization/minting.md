# 铸造

当用户在将资金存入收益来源时，会获得生息资产。例如，在 Lista 中抵押的 BNB 将得到 _slisBNB_; StakeStone 中质押的 ETH 将得到 _Stone_。

_slisBNB_ 和 _Stone_ 就是**生息代币**的示例。

在 OutStake 中，生息代币可以拆分为三个部分：**Staked Position Token (SP)**、**Yield Token (YT)**&#x548C;**Points Yield Token (PYT)**。

同时，**SP**可以进一步拆分为**本金通证（PT）**&#x548C;**不可转让的 SP**，也可以重新合成回可转让的**SP**。

每个令牌代表的含义如下：

* **SP** 代表锁定头寸的本金到期赎回的权利。
* **PT** 代表底层生息代币的初始本金部分。
* **YT** 代表对该资产所有利息收益的权利。
* **PYT** 代表该头寸的外部积分收益。

用户可以把生息资产（例如 stETH）质押在 OutStake 来铸造 PT，YT 以及 PYT。基础资产（例如ETH）将在质押之前，自动转换为生息资产。

例如，ETH → wstETH → SY-wstETH → (SP-wstETH + YT-wstETH + PYT-wstETH)，SP-wstETH <=> PT-wstETH(UETH)。
