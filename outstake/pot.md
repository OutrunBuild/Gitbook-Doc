# Position Options Token

**Position Token** 是代表仓位的 **Token**，用户在质押锁定原生收益资产时除了会铸造 **PT** 与 **YT** 以外，还会铸造 **Position Token** 代表用户的仓位。

由于 **Position Token** 可交易的特性，因此也可以将其视为一种**期权**，该 **Token** 代表原生收益代币的锁定时间到期赎回权，我们将其称之为 **Position Options Token**。

**Position Options Token** 允许持有者在未来，也就是**仓位锁定时间到期时**，销毁固定数量的 **PT** 赎回固定数量的原生收益资产，通过它可以**交易获得固定利率的权利**，而无需交易 **PT** 本身。

**Position Options Token** 由 **ERC1155** 标准支持，将单个仓位分割为多份，允许用户交易仓位的部分赎回权利。

此外 **Position Options Token** 的持有者还可以选择强制赎回提前赎回质押的原生资产，强制赎回需要销毁与提前时间相关数量的 **YT**，并且会收取少量的手续费。
