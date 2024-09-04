---
description: 仓位期权代币
---

# POT

POT(Position Options Token) 代表仓位的到期赎回权，用户在质押锁定原生收益资产时除了会铸造 PT 与 YT 以外，还会铸造 POT 封装用户的仓位。

POT 允许持有者在未来，也就是仓位锁定时间到期时，销毁固定数量的 PT 赎回固定数量的原生收益代币，通过交易 POT 可以交易获得固定利率的权利，而无需交易 PT 本身。

POT 由 [ERC1155](https://eips.ethereum.org/EIPS/eip-1155) 标准支持，将仓位分割为和 PT 铸造数量一样的份额，允许用户交易仓位的部分赎回权利。
