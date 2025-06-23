# 铸造

当用户在将资金存入收益来源时，会获得生息资产。例如，在 Lista 中抵押的 BNB 将得到 _slisBNB_; StakeStone 中质押的 ETH 将得到 _Stone_。

_slisBNB_ 和 _Stone_ 就是**生息代币**的示例。

在 OutStake 中，生息代币可拆分为三个部分：**本金代币 (PT)**，**收益代币 (YT)** 以及**积分收益代币 (PYT)**，同时将 PT 和**头寸质押代币(SP)**&#x53EF;以相互转换。PT 代表底层生息代币的本金部份，YT 代表该资产的全部利息收益的权益，PYT 代表头寸的外部积分收益，而 SP 则代表锁定头寸的本金到期赎回权。

用户可以把生息资产（例如 stETH）质押在 OutStake 来铸造 PT，YT 以及 PYT。基础资产（例如ETH）将在质押之前，自动转换为生息资产。

例如，ETH → wstETH → SY-wstETH → (SP-wstETH + YT-wstETH + PYT-wstETH)，SP-wstETH <=> PT-wstETH(UETH)。
